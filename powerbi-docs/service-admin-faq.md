---
title: Administration af Power BI – ofte stillede spørgsmål
description: Få mere at vide svar på ofte stillede spørgsmål om Power BI – tilmelding, lejeradministration og andre administrative opgaver.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 2e51017333a940bd9d7838e6a903c1a66ce2e342
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100762"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>Administration af Power BI – ofte stillede spørgsmål

Denne artikel omhandler ofte stillede spørgsmål om Power BI-administration. Du kan finde en oversigt over Power BI-administration under [Hvad er Power BI-administration?](service-admin-administering-power-bi-in-your-organization.md)

## <a name="whats-in-this-article"></a>I denne artikel

### <a name="sign-up-for-power-bi-section"></a>Tilmeld dig afsnittet Power BI

* [Brug af PowerShell](#using-powershell)
* [Hvordan tilmelder brugerne sig Power BI?](#how-do-users-sign-up-for-power-bi)
* [Hvordan tilmelder individuelle brugere i min organisation sig?](#how-do-individual-users-in-my-organization-sign-up)
* [Hvordan kan jeg forhindre brugere i at tilmelde sig min eksisterende Office 365-lejer?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [Hvordan kan jeg forhindre brugere i at tilmelde sig min eksisterende Office 365-lejer?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [Hvordan jeg tjekke, om jeg har blokken på i lejeren?](#how-do-i-check-if-i-have-the-block-on-in-the-tenant)
* [Hvordan kan jeg forhindre mine eksisterne brugere i at begynde at bruge Power BI?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [Hvordan kan jeg tillade mine eksisterende brugere at tilmelde sig Power BI?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

### <a name="administration-of-power-bi-section"></a>Administration af afsnittet Power BI

* [Hvordan vil dette ændre den måde, jeg administrerer identiteter for brugerne i organisationen på i dag?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Hvordan administrerer vi Power BI?](#how-do-we-manage-power-bi)
* [Hvad er processen til administration af en lejer, der er oprettet af Microsoft for brugerne?](#what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users)
* [Hvis jeg har flere domæner, kan jeg kontrollere den Office 365-lejer, som brugerne få føjet til?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to)
* [Hvordan fjerner jeg Power BI for brugere, der allerede er tilmeldt?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [Hvordan får jeg besked, når nye brugere tilmelder sig min lejer?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [Er der andre yderligere ting, jeg skal forberedelse til?](#are-there-any-additional-things-i-should-prepare-for)
* [Hvor findes min Power BI-lejer?](#where-is-my-power-bi-tenant-located)
* [Hvad er Power BI SLA (Serviceniveauaftale)?](#what-is-the-power-bi-sla)
* [Hvordan håndterer Power BI høj tilgængelighed og failover?](#how-does-power-bi-handle-high-availability-and-failover)

### <a name="security-in-power-bi-section"></a>Sikkerhed i afsnittet Power BI

* [Opfylder Power BI nationale, regionale og branchespecifikke overholdelseskrav?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Hvordan fungerer sikkerhed i Power BI?](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>Tilmeld dig Power BI

### <a name="using-powershell"></a>Brug af PowerShell

Nogle af procedurerne i dette afsnit kræver Windows PowerShell-scripts. Hvis du ikke er bekendt med PowerShell, anbefaler vi [Introduktion til PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=286814). For at køre scripts skal du først installere den nyeste 64-bit version af [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/).

### <a name="how-do-users-sign-up-for-power-bi"></a>Hvordan tilmelder brugerne sig Power BI?

Som administrator, du kan tilmelde sig Power BI via den [Power BI-webstedet](https://powerbi.microsoft.com) eller [køb tjenester](https://admin.microsoft.com/AdminPortal/Home#/catalog) side på Microsoft 365 admin center. Når en administrator, der tilmelder sig Power BI, kan vedkommende tildele brugerlicenser til brugere, der skal have adgang.

Individuelle brugere i din organisation kan derudover muligvis tilmelde sig Power BI på [Power BI-webstedet](https://powerbi.microsoft.com). Når en bruger i din organisation, der tilmelder sig Power BI, tildeles tjenesten automatisk en Power BI-licens til brugeren. Du kan finde flere oplysninger, i [tilmelding til Power BI som enkeltperson](service-self-service-signup-for-power-bi.md) og [Power BI-licenser i din organisation](service-admin-licensing-organization.md).

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>Hvordan tilmelder individuelle brugere i min organisation sig?

Der er tre scenarier, der kan gøre sig gældende for brugere i din organisation:

* **Scenarie 1**: Din organisation har allerede et Office 365-miljø, og brugeren, der tilmelder sig Power BI, har allerede en Office 365-konto.
    I dette scenarie, hvis en bruger allerede har en arbejds- eller skolekonto i lejeren (f.eks, contoso.com), men ikke endnu har Power BI, planen Microsoft ganske enkelt for den pågældende konto. Brugeren får automatisk besked med oplysninger om, hvordan du bruger Power BI-tjenesten.

* **Scenarie 2**: Din organisation har allerede et Office 365-miljø, men brugeren, der tilmelder sig Power BI, har ikke en Office 365-konto.
    I dette scenarie kan brugeren har en mailadresse i organisationens domæne (f.eks, contoso.com), men endnu har ikke en Office 365-konto. I dette tilfælde kan brugeren tilmelde sig Power BI og får automatisk en konto. Denne handling giver brugeradgang til Power BI-tjenesten. F.eks, hvis en medarbejder med navnet Nancy bruger sin arbejdsmailadresse (f.eks. nancy@contoso.com) for at tilmelde dig Microsoft automatisk tilføjer Nancy som en bruger i Contosos Office 365-miljø og aktiverer Power BI for den pågældende konto.

* **Scenarie 3**: Din organisation har ikke et Office 365-miljø, der er sluttet til dit maildomæne.
    Der er ingen administrative handlinger, der kræves til din organisation for at drage fordel af Power BI. Tjenesten føjer brugere til en ny, udelukkende brugermappe. Du kan også vælge at overtage administrationen af lejeren og administrere dem.

> [!IMPORTANT]
> Hvis organisationen har flere maildomæner, og du foretrækker, at alle mailadresseudvidelser er i den samme lejer, skal du føje alle mailadressedomæner til en Azure Active Directory-lejer, før nogen brugere tilmelder sig. Når du har oprettet brugere, er der ingen automatiseret mekanisme, der kan flytte brugerne på tværs af lejere. Du kan finde flere oplysninger om denne proces, i [Hvis jeg har flere domæner, kan jeg kontrollere den Office 365-lejer, som brugerne få føjet til?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to) senere i denne artikel og [tilføje et domæne til Office 365](/office365/admin/setup/add-domain/).

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>Hvordan kan jeg forhindre brugere i at tilmelde sig min eksisterende Office 365-lejer?

Som administrator kan du tage forholdsregler for at forhindre brugere i at tilmelde sig din eksisterende Office 365-lejer. Hvis du blokerer adgang, brugernes forsøg på at tilmelde dig mislykkes, og der vises en meddelelse, der sender dem til at kontakte organisationens administrator. Du behøver ikke at gentage denne proces, hvis du allerede har deaktiveret automatisk licensdistribution (f.eks, via Office 365 for Education til studerende, undervisere og ansatte).

Brug følgende PowerShell-script til at forhindre, at nye brugere tilmelder sig en administreret lejer. [Få mere at vide om PowerShell][1].

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
```

> [!NOTE]
> Blokering af adgangen forhindrer, at nye brugere i din organisation kan tilmelde sig Power BI. Brugere, der tilmelder sig Power BI før deaktivering af nye tilmeldinger, beholder deres licenser. Hvis du vil fjerne en bruger, skal du se [Hvordan fjerner jeg Power BI for brugere, der allerede er tilmeldt?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) senere i denne artikel.

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>Hvordan kan jeg forhindre brugere i at tilmelde sig min eksisterende Office 365-lejer?

Brug følgende PowerShell-script til at give nye brugere, Deltag i en administreret lejer. [Få mere at vide om PowerShell][1].

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $true
```

### <a name="how-do-i-check-if-i-have-the-block-on-in-the-tenant"></a>Hvordan jeg tjekke, om jeg har blokken på i lejeren?

Brug følgende PowerShell-script til at kontrollere indstillingerne. *AllowEmailVerifiedUsers* skal være falsk. [Få mere at vide om PowerShell][1].

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Get-MsolCompanyInformation | fl allow*
```

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Hvordan kan jeg forhindre mine eksisterne brugere i at begynde at bruge Power BI?

Den Azure AD-indstilling, der styrer dette, er **AllowAdHocSubscriptions**. De fleste lejere har denne indstillet til true, hvilket betyder, at den er aktiveret. Hvis du har købt Power BI via en partner, kan dette være angivet til false, hvilket betyder, at den er deaktiveret.

Brug følgende PowerShell-script til at deaktivere ad hoc-abonnementer. [Få mere at vide om PowerShell][1].

1. Log på Azure Active Directory ved hjælp af dine legitimationsoplysninger til Office 365. I den første linje i følgende PowerShell-script bliver du bedt om dine legitimationsoplysninger. Den anden linje opretter forbindelse til Azure Active Directory.

    ```powershell
     $msolcred = get-credential
     connect-msolservice -credential $msolcred
    ```

   ![Skærmbillede af Azure Active Directory-logon via PowerShell](media/service-admin-licensing-organization/azure-ad-sign-in.png)

1. Når du logger på, køre følgende kommando for at se, hvordan din lejer i øjeblikket er konfigureret.

    ```powershell
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
    ```

1. Kør følgende kommando for at aktivere (`$true`) eller deaktivere (`$false`) **AllowAdHocSubscriptions**.

    ```powershell
     Set-MsolCompanySettings -AllowAdHocSubscriptions $false
    ```

> [!NOTE]
> Brug den **AllowAdHocSubscriptions** flag for at kontrollere flere brugeregenskaber i organisationen, herunder muligheden for brugere at tilmelde sig Azure Rights Management Service. Alle disse egenskaber påvirkes, hvis flaget ændres.

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Hvordan kan jeg tillade mine eksisterende brugere at tilmelde sig Power BI?

Hvis du vil tillade dine eksisterende brugere at tilmelde sig Power BI kan køre kommandoen angivet for det forrige spørgsmål, men sender `$true` i stedet for `$false` i det sidste trin.

## <a name="administration-of-power-bi"></a>Administration af Power BI

### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Hvordan vil dette ændre den måde, jeg administrerer identiteter for brugerne i organisationen på i dag?

Der er tre scenarier, der kan gøre sig gældende for brugere i din organisation:

* **Scenarie 1**: Hvis organisationen allerede har et eksisterende Office 365-miljø, og alle brugere i organisationen har Office 365-konti, er der ingen ændring i, hvordan du administrerer identiteter.

* **Scenarie 2**: Hvis organisationen allerede har et eksisterende Office 365-miljø, men ikke alle brugere i organisationen har Office 365-konti, kan vi oprette en bruger i lejeren og tildeler licenser på baggrund af brugernes arbejds- eller skolemailadresser.

    Som et resultat heraf stiger antallet af brugere, som du administrerer på et givent tidspunkt, som brugere i din organisation, der tilmelder sig tjenesten.

* **Scenarie 3**: Hvis din organisation ikke har et Office 365-miljø, der er sluttet til dit maildomæne, er der ingen ændring i, hvordan du administrerer identiteter.

    Tjenesten føjer brugere til en ny, udelukkende brugermappe. Du kan også vælge at overtage administrationen af lejeren og administrere dem.

### <a name="how-do-we-manage-power-bi"></a>Hvordan administrerer vi Power BI?

Powerbi giver en administratorportal, der gør det muligt at se brugsstatistik, indeholder et link til Microsoft 365 administration til at administrere brugere og grupper, og gør muligheden at styre indstillingerne for hele lejeren.

Hvis du vil bruge Power BI-administrationsportalen, skal du markere din konto som et **Global administrator** i Office 365 eller Azure Active Directory eller en person skal tildele Power BI-tjenesten administratorrollen for din brugerkonto. Du kan finde flere oplysninger, i [beskrivelse af rollen som Power BI-administrator](service-admin-role.md) og [Power BI-administrationsportalen](service-admin-portal.md).

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Hvad er processen til administration af en lejer, der er oprettet af Microsoft for brugerne?

Når en bruger med selvbetjening, der tilmelder sig en cloudtjeneste, der bruger Azure AD, tjenesten føjer dem til en ikke-administreret Azure AD-katalog, der er baseret på deres maildomæne. Du kan gøre krav på og administrere lejeren, en anden har oprettet ved hjælp af en proces, der er kendt som en *administrator Overtag*. Typen af Overtag, som du gør, afhænger af om der er en eksisterende administreret lejer, der er knyttet til dit domæne:

* Brug en *intern overtagelse* til at oprette en ny administreret lejer for domænet.

* Brug en *ekstern overtagelse* til at flytte domænet til en eksisterende administreret lejer.

Du kan finde flere oplysninger, i [overtage en ikke-administrerede mappe som administrator i Azure Active Directory](/azure/active-directory/users-groups-roles/domains-admin-takeover).

Når du gør en ekstern Overtag, tjenesten placerer Power BI indhold, der blev oprettet før Overtag i en [arkiveret arbejdsområde i Power BI](service-admin-power-bi-archived-workspace.md). Du skal manuelt overføre det indhold, du vil bruge i den nye lejer.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to"></a>Hvis jeg har flere domæner, kan jeg kontrollere den Office 365-lejer, som brugerne få føjet til?

Hvis du foretager dig noget, opretter tjenesten en lejer for hvert brugermaildomæne og underdomæne. Hvis du ønsker, at alle brugerne skal være i samme lejer uanset deres mailadresseudvidelser: Opret en destinationslejer, eller brug en eksisterende lejer. Tilføj derefter alle eksisterende domæner og underdomæner, som du vil samle i lejeren. Alle brugere med mailadresser, der slutter med de pågældende domæner og underdomæner, automatisk destinationslejeren, når de tilmelder.

> [!IMPORTANT]
> Når du har oprettet brugere, er der ingen understøttede automatiserede metode til at flytte brugerne på tværs af lejere. Hvis du vil have mere at vide om tilføjelse af domæner til en enkelt Office 365-lejer, skal du se [Føj dine brugere og domæner til Office 365](/office365/admin/setup/add-domain/).

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Hvordan fjerner jeg Power BI for brugere, der allerede er tilmeldt?

Hvis en bruger er tilmeldt Power BI, men du ikke længere ønsker, at vedkommende skal have adgang til Power BI, kan du fjerne Power BI-licensen fra brugeren.

1. Gå til [Microsoft 365 Administration](https://admin.microsoft.com/AdminPortal/Home#/homepage).

1. I navigationspanelet til venstre skal du vælge **Brugere** og derefter vælge  > **Aktive brugere**.

1. Find den bruger, du vil fjerne licensen fra, og vælg derefter vedkommendes navn.

    Du kan administrere mange licenser for brugere. Gør dette ved at vælge mange brugere og derefter vælge **Rediger produktlicenser**.

1. Ud for **Produktlicenser** på siden med brugerdetaljer skal du vælge **Rediger**.

1. Afhængigt af hvad du har licens gældende for vedkommendes konto, skal du angive **Power BI (gratis)** eller **Power BI Pro** til **fra**.

1. Vælg **Gem**.

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Hvordan får jeg besked, når nye brugere slutter sig til min lejer?

Brugere, der har tilmeldt sig lejeren som en del af dette program få tildelt en unik licens, som du kan filtrere efter i din aktive brugerrude i administratordashboardet. Følg disse trin for at oprette denne nye visning.

1. Naviger til [Microsoft 365 Administration](https://admin.microsoft.com/AdminPortal/Home#/homepage).

1. I navigationspanelet til venstre skal du vælge **Brugere** og derefter vælge  > **Aktive brugere**.

1. I menuen **Visninger** skal du vælge **Tilføj brugerdefineret visning**.

1. Navngiv din nye visning. Under **Tildel produktlicens** vælger du herefter **Power BI (gratis)** eller **Power BI Pro**.

    Du kan kun have en licens pr. valgt visning. Hvis du har både **Power BI (gratis)** - og **Power BI Pro**-licenser i organisationen, kan du oprette to visninger.

1. Angiv alle de andre betingelser, du ønsker, og vælg derefter **Tilføj**.

1. Når du opretter den nye visning, det er tilgængeligt fra den **visninger** menu.

### <a name="are-there-any-additional-things-i-should-prepare-for"></a>Er der andre yderligere ting, jeg skal forberedelse til?

Du oplever måske en stigning i anmodninger om nulstilling af adgangskode. Du kan finde oplysninger om denne proces, i [Nulstil en brugers adgangskode](/office365/admin/add-users/reset-passwords).

Du kan fjerne en bruger fra lejeren vha. standardprocessen i Microsoft 365 Administration. Men hvis brugeren stadig har en aktiv mailadresse fra organisationen, kan vedkommende tilmelde sig igen, medmindre du blokerer alle brugere fra at tilmelde sig.

### <a name="where-is-my-power-bi-tenant-located"></a>Hvor er min Power BI-lejer placeret?

Du kan finde oplysninger om, hvilke dataområdet din Power BI-lejer er på, i [hvor er min Power BI-lejer placeret?](service-admin-where-is-my-tenant-located.md).

### <a name="what-is-the-power-bi-sla"></a>Hvad er Power BI SLA?

Du kan finde oplysninger om Power BI SLA (serviceniveauaftale), under den [licensvilkår og dokumentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) artiklen i den **Licensing** afsnit på webstedet Microsoft Licensing.

### <a name="how-does-power-bi-handle-high-availability-and-failover"></a>Hvordan håndterer Power BI høj tilgængelighed og failover?

Du kan finde oplysninger om høj tilgængelighed og failover, under [Power BI høj tilgængelighed, failover og it-katastrofeberedskab ofte stillede spørgsmål om](service-admin-failover.md).

## <a name="security-in-power-bi"></a>Sikkerhed i Power BI

### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Opfylder Power BI nationale, regionale og branchespecifikke overholdelseskrav?

Få mere at vide om Power BI-overholdelse ved at se [Microsoft Center for sikkerhed og rettighedsadministration](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/default.aspx).

### <a name="how-does-security-work-in-power-bi"></a>Hvordan fungerer sikkerhed i Power BI?

Microsoft har indbygget Power BI på grundlag af Office 365, som igen er bygget på Azure-tjenester som Azure Active Directory. Se en oversigt over Power BI-arkitektur i [Sikkerhed i Power BI](service-admin-power-bi-security.md).

## <a name="next-steps"></a>Næste trin

[Power BI-administrationsportal](service-admin-portal.md)  
[Beskrivelse af rollen som Power BI-administrator](service-admin-role.md)  
[Tilmelding via selvbetjening til Power BI](service-self-service-signup-for-power-bi.md)  
[Køb Power BI Pro](service-admin-purchasing-power-bi-pro.md)  
[Hvad er Power BI Premium?](service-premium-what-is.md)  
[Sådan køber du Power BI Premium](service-admin-premium-purchase.md)  
[Hvidbog om Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[Administrer din gruppe i Power BI og Office 365](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Administration af brugerkonto i Office 365](/office365/servicedescriptions/office-365-platform-service-description/user-account-management/)  
[Administration af gruppe i Office 365](/office365/admin/email/create-edit-or-delete-a-security-group/)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

[1]: https://docs.microsoft.com/powershell/scripting/overview