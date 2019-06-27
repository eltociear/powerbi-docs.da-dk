---
title: Brug dine egne krypteringsnøgler til Power BI (prøveversion)
description: Få mere at vide om, hvordan du kan bruge dine egne krypteringsnøgler i Power BI Premium.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 06/10/2019
LocalizationGroup: Premium
ms.openlocfilehash: 7adcfeec771796aa9fe322512f8ca8584559cea0
ms.sourcegitcommit: c122c1a8c9f502a78ccecd32d2708ab2342409f0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/11/2019
ms.locfileid: "66829382"
---
# <a name="bring-your-own-encryption-keys-for-power-bi-preview"></a>Medbring dine egne krypteringsnøgler til Power BI (prøveversion)

Power BI krypterer _inaktive_ og _igangværende_ data. Power BI bruger som standard Microsoft-administrerede nøgler til kryptering af dine data. Du kan også bruge dine egne nøgler i Power BI Premium til igangværende data, der importeres til et datasæt (se [Overvejelser vedrørende datakilde og -lager](#data-source-and-storage-considerations) for at få flere oplysninger). Denne fremgangsmåde beskrives ofte som _BYOK_ (Bring Your Own Key – medbring din egen nøgle).

## <a name="why-use-byok"></a>Hvorfor bruge BYOK?

BYOK gør det nemmere at imødekomme kravene til overholdelse af angivne standarder, som angiver nøgleordninger med cloudtjenesteudbyderen (i dette tilfælde Microsoft). Med BYOK skal du angive og styre krypteringsnøglerne til dine inaktive Power BI data på programniveau. Du har derfor kontrol over adgangen og kan tilbagekalde din organisations nøgler, hvis du beslutter at afslutte tjenesten. Når nøglerne tilbagekaldes, kan tjenesten ikke læse dataene.

## <a name="data-source-and-storage-considerations"></a>Overvejelser vedrørende datakilde og -lager

Hvis du vil bruge BYOK, skal du uploade data til Power BI-tjenesten fra en PBIX-fil (Power BI Desktop). Når du opretter forbindelse til datakilder i Power BI Desktop, skal du angive en lagringstilstand for import. Du kan ikke bruge BYOK i følgende scenarier:

- DirectQuery
- Direkte Analysis Services-forbindelse
- Excel-projektmapper (medmindre data importeres først i Power BI Desktop)
- Push-datasæt

I næste afsnit kan du lære, hvordan du konfigurerer Azure Key Vault, som er det sted, du gemmer krypteringsnøgler til BYOK.

## <a name="configure-azure-key-vault"></a>Konfigurer Azure Key Vault

Azure Key Vault er et værktøj til sikker lagring og adgang til hemmelige oplysninger, som krypteringsnøgler. Du kan bruge en eksisterende key vault til at gemme krypteringsnøgler, eller du kan oprette en ny specielt til brug sammen med Power BI.

I vejledningen i dette afsnit antages det, at du har grundlæggende viden om Azure Key Vault. Du kan finde flere oplysninger under [Hvad er Azure Key Vault?](/azure/key-vault/key-vault-whatis). Konfigurer din nøgleboks på følgende måde:

1. Tilføj Power BI-tjenesten som en tjenesteprincipal til key vault med tilladelse til ombrydning og fjernelse af ombrydning.

1. Opret en RSA-nøgle med en længde på 4096-bit (eller brug en eksisterende nøgle af denne type) med tilladelse til ombrydning og fjernelse af ombrydning.

1. Anbefalet: Kontrollér, at din key vault har indstillingen til _blød sletning_ aktiveret.

### <a name="add-the-service-principal"></a>Tilføj tjenesteprincipalen

1. Under **Adgangspolitikker** i din key vault i Microsoft Azure-portal skal du vælge **Tilføj ny**.

1. Søge efter og vælg Microsoft.Azure.AnalysisServices under **Vælg principal**.

1. Under **Key permissions** (Nøgletilladelser) skal du vælge **Unwrap Key** (Fjern ombrydning af nøgle) og **Wrap Key** (Ombryd nøgle).

    ![Komponenter i PBIX-fil](media/service-encryption-byok/service-principal.png)

1. Vælg **OK** og derefter **Gem**.

### <a name="create-an-rsa-key"></a>Opret en RSA-nøgle

1. I din key vault under **Nøgler** skal du vælge **Generér/Importér**.

1. Vælg en **nøgletype** for RSA og en **RSA-nøglestørrelse** på 4096.

    ![Komponenter i PBIX-fil](media/service-encryption-byok/create-rsa-key.png)

1. Vælg **Opret**.

1. Under **Nøgler** skal du vælge den nøgle, du har oprettet.

1. Vælg GUID'et for den **aktuelle version** af nøglen.

1. Kontrollér, at **Wrap Key** (Ombryd nøgle) og **Unwrap Key** (Fjern ombrydning af nøgle) begge er markeret. Kopiér den **nøgleidentifikator**, der skal bruges, når du aktiverer BYOK i Power BI.

    ![Komponenter i PBIX-fil](media/service-encryption-byok/key-properties.png)

### <a name="soft-delete-option"></a>Indstilling til blød sletning

Vi anbefaler, at du aktiverer [blød sletning](/azure/key-vault/key-vault-ovw-soft-delete) i din key vault for at beskytte mod datatab i tilfælde af, at en nøgle – eller en key vault – ved et uheld bliver slettet. Du skal bruge [PowerShell til at aktivere egenskaben for "blød sletning"](/azure/key-vault/key-vault-soft-delete-powershell) i din key vault, fordi denne indstilling endnu ikke er tilgængelig fra Microsoft Azure-portalen.

Når Azure Key Vault er konfigureret korrekt, er du klar til at aktivere BYOK på din lejer.

## <a name="enable-byok-on-your-tenant"></a>Aktivér BYOK i din lejer

Du aktiverer BYOK på lejerniveau med PowerShell ved først at registrere de krypteringsnøgler, du har oprettet og gemt i Azure Key Vault, i Power BI-lejeren. Derefter kan du tildele disse krypteringsnøgler til hver Premium-kapacitet til kryptering af indhold i kapaciteten.

### <a name="important-considerations"></a>Vigtige overvejelser

Før du aktiverer BYOK, skal du overveje følgende:

- På dette tidspunkt kan du ikke deaktivere BYOK, når funktionen er aktiveret. Afhængigt af, hvordan du angiver parametre for `Add-PowerBIEncryptionKey`, kan du styre, hvordan du kan bruge BYOK til en eller flere af dine kapaciteter. Du kan imidlertid ikke fortrydes registreringen af nøgler i din lejer. Du kan finde flere oplysninger under [Aktivér BYOK](#enable-byok).

- Du kan ikke _direkte_ flytte et arbejdsområde, der bruger BYOK, fra en dedikeret kapacitet i Power BI Premium til delt kapacitet. Du skal først flytte arbejdsområdet til en dedikeret kapacitet, der ikke har BYOK aktiveret.

### <a name="enable-byok"></a>Aktivér BYOK

Hvis du vil aktivere BYOK, skal du være lejeradministrator af Power BI-tjenesten og være logget på med cmdlet'en `Connect-PowerBIServiceAccount`. Brug derefter `Add-PowerBIEncryptionKey` at aktivere BYOK som vist i følgende eksempel:

```powershell
Add-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
```

Cmdlet'en accepterer tre switchparametre, der påvirker kryptering for aktuelle og fremtidige kapaciteter. Som standard er ingen af parametrene angivet:

- `-Activate`: Angiver, at denne nøgle bruges til alle eksisterende kapaciteter i lejeren.

- `-Default`: Angiver, at denne nøgle nu er standard for hele lejeren. Når du opretter en ny kapacitet, arver kapaciteten denne nøgle.

- `-DefaultAndActivate`: Angiver, at denne nøgle bruges til alle eksisterende kapaciteter og eventuelle nye kapaciteter, du opretter.

Hvis du angiver `-Default` eller `-DefaultAndActivate`, krypteres alle de kapaciteter, der er oprettet i denne lejer herefter med den nøgle, du angiver (eller en opdateret standardnøgle). Du kan ikke fortryde standardhandlingen, så mister du muligheden for at oprette en Premium-kapacitet, der ikke bruger BYOK i din lejer.

Du kan styre, hvordan du bruger BYOK på tværs af din lejer. Hvis du f.eks. vil kryptere en enkelt kapacitet, skal du kalde `Add-PowerBIEncryptionKey` uden `-Activate`, `-Default` eller `-DefaultAndActivate`. Kald derefter `Set-PowerBICapacityEncryptionKey` for den kapacitet, hvor du vil aktivere BYOK.

## <a name="manage-byok"></a>Administrer BYOK

Power BI omfatter yderligere cmdlet'er, der hjælpe med at administrere BYOK i din lejer:

- Brug `Get-PowerBIEncryptionKey` til at få den nøgle, din lejer aktuelt bruger:

    ```powershell
    Get-PowerBIEncryptionKey
    ```

- Brug `Get-PowerBIWorkspaceEncryptionStatus` at se, om datasættene i et arbejdsområde er krypteret, og om deres krypteringsstatus er synkroniseret med arbejdsområdet:

    ```powershell
    Get-PowerBIWorkspaceEncryptionStatus -Name'Contoso Sales'
    ```

    Bemærk, at kryptering er aktiveret på kapacitetsniveau, men du får krypteringsstatus på datasætniveau for det angivne arbejdsområde.

- Brug `Set-PowerBICapacityEncryptionKey` til at opdatere krypteringsnøglen for Power BI-kapaciteten:

    ```powershell
    Set-PowerBICapacityEncryptionKey-CapacityId 08d57fce-9e79-49ac-afac-d61765f97f6f -KeyName 'Contoso Sales'
    ```

- `Use Switch-PowerBIEncryptionKey` for at skifte (eller _rotere_) den nøgle, der er aktuelt bruges til kryptering. Cmdlet'en opdaterer blot `-KeyVaultKeyUri` for en nøgle `-Name`:

    ```powershell
    Switch-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
    ```