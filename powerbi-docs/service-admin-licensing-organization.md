---
title: Power BI-licenser i din organisation
description: 'De forskellige licenstyper, der er tilgængelige i Power BI, er: gratis licenser, Power BI Pro og Power BI Premium.'
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 4fa28e828df2765bb128ad5fb6e8eee73b6eb2a2
ms.sourcegitcommit: 833cf1252807721fb1b3000487bd032bfd6c8c98
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/04/2018
ms.locfileid: "48272334"
---
# <a name="power-bi-licensing-in-your-organization"></a>Power BI-licenser i din organisation

I Power BI-tjenesten har brugerne definerede funktioner, der er baseret på to typer licenser:

* Gratis licenser **pr. bruger** -  *samt Power BI Pro-licenser*. En gratis licens giver adgang til nogle af funktionerne i Power BI-tjenesten. En Pro-licens giver adgang til alt indhold og alle funktioner i Power BI-tjenesten, herunder muligheden for at dele indhold og samarbejde med andre Pro-brugere. Det er kun Pro-brugere, der kan udgive og forbruge indhold fra apparbejdsområder, dele dashboards og abonnere på dashboards og rapporter. Se [Funktioner i Power BI-tjenesten efter licenstype](service-features-license-type.md) for at få flere oplysninger.

* **Kapacitetsbaserede** - *Power BI Premium-licenser*. Premium indeholder dedikeret kapacitet til at levere en mere ensartet ydeevne og understøtter større datamængder i Power BI. For individuelle brugere muliggør Premium også omfattende distribution af indhold for Pro-brugere uden at kræve Pro-licenser i forbindelse med visning af indholdet. Du kan finde flere oplysninger i [Hvad er Power BI Premium?](service-premium.md).

I denne artikel fokuseres der på licenser pr. bruger fra et administratorperspektiv.

## <a name="manage-power-bi-pro-licenses"></a>Administrer Power BI Pro-licenser

Som administrator kan du købe og tildele Power BI Pro-licenser, og du kan tilmelde dig en Power BI Pro-prøveversion til din organisation. Enkeltpersoner kan også tilmelde sig en Power BI Pro-prøveversion.

### <a name="purchasing-power-bi-pro"></a>Køb Power BI Pro

Du kan købe Power BI Pro-licenser gennem Microsoft Office 365 eller gennem en certificeret Microsoft-partner. Når du køber licenserne, kan du tildele dem til individuelle brugere. Du kan finde flere oplysninger i [Køb og tildel Power BI Pro-licenser](service-admin-purchasing-power-bi-pro.md).

### <a name="power-bi-pro-trial-for-individuals"></a>Power BI Pro-prøveversion til enkeltpersoner

Enkeltpersoner i din organisation kan tilmelde sig en Power BI Pro-prøveversion. Du kan flere oplysninger i [Tilmelding til Power BI som enkeltperson](service-self-service-signup-for-power-bi.md).

Brugere, der benytter sig af Power BI Pro (prøveversion) inde i produktet, vises ikke i Office 365-administrationsportalen som Power BI Pro-prøveversionsbrugere (de vises som Power BI (gratis)-brugere). De vises dog som brugere af Power BI Pro (prøveversion) på siden Administrer lager i Power BI.

### <a name="power-bi-pro-trial-for-organizations"></a>Power BI Pro-prøveversion til organisationer

Hvis du vil hente og installere Power BI-prøvelicenser til flere brugere i din organisation, uden at de enkelte brugere skal acceptere vilkårene, kan du tilmelde dig en Power BI Pro-prøveversion til din virksomhed.

Vær opmærksom på følgende, før du følge trinnene for at tilmelde dig:

* For at kunne tilmelde dig skal du være medlem af rollen [**Global administrator** eller **Faktureringsadministrator**](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) i Office 365.

* Der er en grænse på én organisationsprøveversion pr. lejer. Det betyder, at hvis en person allerede har anvendt Power BI Pro (prøveversion) på din lejer, kan du ikke gøre det igen. Hvis du har brug for hjælp til dette, kan du kontakte [Office 365-faktureringssupport](https://support.office.microsoft.com/en-us/article/contact-support-for-business-products-admin-help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b?CorrelationId=552bbf37-214f-4202-80cb-b94240dcd671&ui=en-US&rs=en-US&ad=US).

1. Naviger til [Office 365 Administration](https://portal.office.com/adminportal/home#/homepage).

1. Vælg **Fakturering** og derefter **Abonnementer** i den venstre navigationsrude.

   ![Fakturering og abonnementer](media/service-admin-licensing-organization/service-power-bi-pro-in-your-organization-05.png)

1. Vælg **Tilføj abonnementer** i højre side.

   ![Tilføj abonnementer](media/service-admin-licensing-organization/service-power-bi-pro-in-your-organization-06.png)

1. Hold musemarkøren over ellipsen (**…**) under **Andre planer** for at vælge Power BI Pro, og vælg **Start gratis prøveversion**.

   ![Start gratis prøveversion](media/service-admin-licensing-organization/service-power-bi-pro-in-your-organization-07.png) 

1. Vælg **Prøv nu** i skærmbilledet med ordrebekræftelsen.

1. Vælg **Fortsæt** på ordrekvitteringen.

Nu kan du [tildele licenser i Office 365](https://support.office.com/article/assign-licenses-to-users-in-office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="manage-power-bi-free-licenses"></a>Administrer Power BI (gratis)-licenser

Brugerne i organisationen kan få adgang til Power BI (gratis)-licenser på to forskellige måder. De kan selv tilmelde sig Power BI, eller du kan tildele dem en Power BI-licens på Office 365-administrationsportalen.

Det betyder mindre arbejde for organisationens administratorer, hvis de brugere, der er interesseret i Power BI, selv tilmelder sig.

Deaktivering af individuel brugertilmelding giver dig imidlertid mere kontrol, og det er en god mulighed, hvis du vil overvåge brug af tjenesten.

### <a name="power-bi-free-for-individuals"></a>Power BI (gratis) til enkeltpersoner

Enkeltpersoner i din organisation kan som standard tilmelde sig en Power BI (gratis)-licens. Du kan flere oplysninger i [Tilmelding til Power BI som enkeltperson](service-self-service-signup-for-power-bi.md).

Hvis du vil blokere individuel tilmelding, skal du se [Aktivér eller deaktiver individuel brugertilmelding i Azure Active Directory](service-admin-licensing-organization.md#enable-or-disable-individual-user-sign-up-in-azure-active-directory) senere i denne artikel.

### <a name="requesting-and-assigning-free-licenses"></a>Anmodning om og tildeling af gratis licenser

Hvis du vil administrere licensanmodninger og -tildelinger centralt, skal du først kontrollere, om du allerede har den ubegrænsede Power BI (gratis)-licensblok.

Denne licensblok bliver tilgængelig, når en person første gang har tilmeldt sig Power BI som enkeltperson. Under denne proces knyttes licensblokken til din organisation, og der tildeles en licens til den bruger, der tilmelder sig.

1. Kontroller, om **ubegrænset** er angivet, under **Fakturering** > **Licenser** i Office 365 Administration.

    ![Ubegrænset gratis licensblok](media/service-admin-licensing-organization/unlimited-licenses.png)

1. Hvis blokken er tilgængelig, kan du nu [tildele licenser i Office 365](https://support.office.com/article/assign-licenses-to-users-in-office-365-for-business-997596b5-4173-4627-b915-36abac6786dc). Hvis blokken er ikke tilgængelig, har du to valgmuligheder:

    * Få et medlem af din organisation til at tilmelde sig individuelt, hvilket udløser oprettelsen af den ubegrænsede blok.

    * Gå til den næste fremgangsmåde, hvor du kan tilmelde dig et fast antal licenser.

Hvis den ubegrænsede licensblok Power BI (gratis) ikke er tilgængelig, og du ikke vil foretage en individuel tilmelding, kan du følge denne fremgangsmåde.

1. Naviger til [Office 365 Administration](https://portal.office.com/admin/default.aspx).

1. Vælg **Fakturering** > **Abonnementer** i den venstre navigationsrude.

1. Vælg **Tilføj abonnementer +** i højre side.

1. Hold musemarkøren over ellipsen (**…**) under **Andre planer** for at vælge Power BI (gratis), og vælg **Køb nu**.

    ![Køb nu – Power BI (gratis)](media/service-admin-licensing-organization/buy-powerbi-free.png)

1. Angiv det antal licenser, du vil tilføje, og vælg derefter **Gå til kassen nu** eller **Føj til indkøbskurv**.

1. Angiv de nødvendige oplysninger, når du går til kassen.

    Der er ikke noget køb, når denne fremgangsmåde benyttes, selvom du enten skal angive kreditkortoplysninger til fakturering eller vælge at blive faktureret.

1. Nu kan du [tildele licenser i Office 365](https://support.office.com/article/assign-licenses-to-users-in-office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

1. Hvis du beslutter senere, at du vil tilføje flere licenser, kan du gå tilbage til **Tilføj abonnementer** og vælge **Rediger licensantal** til Power BI (gratis).

    ![Skift antal licenser](media/service-admin-licensing-organization/change-license-quantity.png)

### <a name="enable-or-disable-individual-user-sign-up-in-azure-active-directory"></a>Aktivér eller deaktiver individuel brugertilmelding i Azure Active Directory

Som administrator kan du vælge at aktivere eller deaktivere individuelle brugertilmeldinger gennem Azure Active Directory (AAD). I dette afsnit af artiklen vises det, hvordan du administrerer tilmeldinger med PowerShell-kommandoer. Du kan finde flere oplysninger om Azure PowerShell, under [Oversigt over Azure PowerShell](/powershell/azure/overview).

Den AAD-indstilling, der styrer tilmelding, er **AllowAdHocSubscriptions**. For de fleste lejere er denne indstilling indstillet til *sand*, hvilket betyder, at den er aktiveret. Hvis du har købt Power BI via en partner, kan denne være indstillet til *falsk*, hvilket betyder, at den er deaktiveret. Hvis du ændrer indstillingen fra *sand* til *falsk*, blokeres individuel tilmelding for nye brugere i din organisation. Brugere, der har tilmeldt sig Power BI før ændringen af indstillingen bevarer deres licens.

1. Log på Azure Active Directory ved hjælp af dine legitimationsoplysninger til Office 365. I den første linje i følgende PowerShell-script bliver du bedt om dine legitimationsoplysninger. Den anden linje opretter forbindelse til Azure Active Directory.

    ```powershell
     $msolcred = get-credential
     connect-msolservice -credential $msolcred
    ```

   ![Azure Active Directory-logon](media/service-admin-licensing-organization/aad-signin.png)

1. Når du er logget på, skal du køre følgende kommando for at se, hvordan din lejer i øjeblikket er konfigureret.

    ```powershell
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
    ```
1. Kør følgende kommando for at aktivere ($true) eller deaktivere ($false) **AllowAdHocSubscriptions**.

    ```powershell
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true
    ```

## <a name="next-steps"></a>Næste trin

[Tilmelding via selvbetjening til Power BI](service-self-service-signup-for-power-bi.md)  

[Køb og tildel Power BI Pro-licenser](service-admin-purchasing-power-bi-pro.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)