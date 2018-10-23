---
title: Administration af Power BI – ofte stillede spørgsmål
description: Find svar på ofte stillede spørgsmål om tilmelding til Power BI, lejeradministration og andre administrative opgaver.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: b77d20b8c9705e4b4cd811ea8dfa3008908a4438
ms.sourcegitcommit: a764e4b9d06b50d9b6173d0fbb7555e3babe6351
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/22/2018
ms.locfileid: "49641674"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>Administration af Power BI – ofte stillede spørgsmål

Denne artikel omhandler ofte stillede spørgsmål om Power BI-administration. Du kan finde en oversigt over Power BI-administration under [Hvad er Power BI-administration?](service-admin-administering-power-bi-in-your-organization.md)

## <a name="whats-in-this-article"></a>I denne artikel
**Tilmeld dig Power BI**

* [Hvordan tilmelder brugerne sig Power BI?](#how-do-users-sign-up-for-power-bi)
* [Hvordan tilmelder individuelle brugere i min organisation sig?](#how-do-individual-users-in-my-organization-sign-up)
* [Hvordan kan jeg forhindre brugere i at tilmelde sig min eksisterende Office 365-lejer?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [Hvordan kan jeg forhindre brugere i at tilmelde sig min eksisterende Office 365-lejer?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [Hvordan bekræfter jeg, om blokering er aktiveret i lejeren?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)
* [Hvordan kan jeg forhindre mine eksisterne brugere i at begynde at bruge Power BI?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [Hvordan kan jeg tillade mine eksisterende brugere at tilmelde sig Power BI?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Administration af Power BI**

* [Hvordan vil dette ændre den måde, jeg administrerer identiteter for brugerne i organisationen på i dag?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Hvordan administrerer vi Power BI?](#how-do-we-manage-power-bi)
* [Hvad er processen til administration af en lejer, der er oprettet af Microsoft for brugerne?](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
* [Kan jeg kontrollere den Office 365-lejer, som brugerne er føjet til, hvis jeg har flere domæner?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)
* [Hvordan fjerner jeg Power BI for brugere, der allerede er tilmeldt?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [Hvordan får jeg besked, når nye brugere tilmelder sig min lejer?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [Er der andre yderligere ting, jeg skal være forberedt på?](#are-there-any-additional-things-i-should-be-prepared-for)
* [Hvor findes min Power BI-lejer?](#where-is-my-power-bi-tenant-located)
* [Hvad er Power BI SLA (Serviceniveauaftale)?](#what-is-the-power-bi-sla)

**Sikkerhed i Power BI**

* [Opfylder Power BI nationale, regionale og branchespecifikke overholdelseskrav?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Hvordan fungerer sikkerhed i Power BI?](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>Tilmeld dig Power BI
### <a name="how-do-users-sign-up-for-power-bi"></a>Hvordan tilmelder brugerne sig Power BI?
Du kan tilmelde dig Power BI på [Power Bi-webstedet](https://powerbi.microsoft.com). Du kan også tilmelde dig på siderne til køb af tjenesten i Office 365 Administration. Når en administrator tilmelder sig Power BI, kan vedkommende tildele brugerlicenser til brugere, der bør have adgang.

Individuelle brugere i din organisation kan derudover muligvis tilmelde sig Power BI på [Power BI-webstedet](https://powerbi.microsoft.com). Når en bruger i organisationen tilmelder sig Power BI, tildeles brugeren automatisk en Power BI-licens. [Få mere at vide](service-self-service-signup-for-power-bi.md)

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>Hvordan tilmelder individuelle brugere i min organisation sig?
Der er tre scenarier, der kan gøre sig gældende for brugere i din organisation:

1. scenarie: Din organisation har allerede et Office 365-miljø, og brugeren, der tilmelder sig Power BI, har allerede en Office 365-konto.
Hvis en bruger allerede har en arbejds- eller skolekonto i lejeren (f.eks. contoso.com), men endnu ikke har Power BI, aktiverer Microsoft i dette scenarie ganske enkelt planen for den pågældende konto, og brugeren får automatisk besked om, hvordan Power BI-tjenesten bruges.

2. scenarie: Din organisation har allerede et Office 365-miljø, og brugeren, der tilmelder sig Power BI, har ikke en Office 365-konto.
I dette scenarie har brugeren en mailadresse i organisationens domæne (f.eks.: contoso.com), men har endnu ikke en Office 365-konto. I dette tilfælde kan brugeren tilmelde sig Power BI og får automatisk en konto. Dette giver brugeren adgang til Power BI-tjenesten. Hvis en medarbejder, der hedder Nancy, f.eks. bruger sin arbejdsmailadresse (f.eks. Nancy@contoso.com) til at tilmelde sig, tilføjer Microsoft automatisk Nancy som en bruger i Contosos Office 365-miljø og aktiverer Power BI for den konto.

3. scenarie: Din organisation ikke har et Office 365-miljø, der er sluttet til dit maildomæne.
Din organisation skal ikke udføre nogle administrative handlinger for at kunne nyde godt af Power BI. Brugerne føjes til en ny brugermappe udelukkende for cloudmiljøet, og du får mulighed for at overtage administrationen af lejeren og administrere dem.

> [!IMPORTANT]
> Hvis organisationen har flere maildomæner, og du foretrækker, at alle mailadresseudvidelser er i den samme lejer, skal du føje alle mailadressedomæner til en Azure Active Directory-lejer, før nogen brugere tilmelder sig. Der er ikke en automatiseret mekanisme, der kan flytte brugerne på tværs af lejere, når de først er blevet oprettet. Få flere oplysninger om denne proces ved at se [Kan jeg kontrollere den Office 365-lejer, som brugerne er føjet til, hvis jeg har flere domæner?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) senere i denne artikel og [Føj dit domæne til Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) online.
> 
> 

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>Hvordan kan jeg forhindre brugere i at tilmelde sig min eksisterende Office 365-lejer?
Som administrator kan du tage forholdsregler for at forhindre brugere i at tilmelde sig din eksisterende Office 365-lejer. Hvis du blokerer dette, vil brugernes forsøg på at tilmelde sig mislykkes, og de får besked om at kontakte administratoren for deres organisation. Du skal ikke gentage denne proces, hvis du allerede har deaktiveret automatisk licensdistribution (f.eks. Office 365 for Education til studerende, undervisere og ansatte).

Disse trin kræver brug af Windows PowerShell. Kom i gang med Windows PowerShell ved at se [Introduktion til PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=286814).

Du skal installere den seneste 64-bit version af [Azure Active Directory Module til Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) for at udføre følgende trin.

Når du har valgt linket, skal du vælge **Kør** for at køre installationspakken.

**Disable automatic tenant join**: Brug denne Windows PowerShell-kommando til at forhindre, at nye brugere tilmelder sig en administreret lejer:

* Sådan deaktiveres automatisk tilmelding til lejer for nye brugere:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
* Sådan aktiveres automatisk tilmelding til lejer for nye brugere:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

> [!NOTE]
> Denne blokering forhindrer, at nye brugere i din organisation kan tilmelde sig Power BI. Brugere, der tilmelder sig Power BI før deaktivering af nye tilmeldinger, vil stadig have deres licenser. Se afsnittet [Hvordan kan jeg fjerne licenser?] for at få vejledning til, hvordan du kan fjerne adgang til Power BI for brugere, der tidligere har tilmeldt sig tjenesten.
> 
> 

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>Hvordan kan jeg forhindre brugere i at tilmelde sig min eksisterende Office 365-lejer?
Tillad brugere at tilmelde sig din lejer ved at køre den modsatte kommando som beskrevet i ovenstående spørgsmål.

Du skal installere den seneste 64-bit version af [Azure Active Directory Module til Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) for at udføre følgende trin.

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Hvordan bekræfter jeg, om blokering er aktiveret i lejeren?
Brug følgende PowerShell-script.

Du skal installere den seneste 64-bit version af [Azure Active Directory Module til Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) for at udføre følgende trin.

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Get-MsolCompanyInformation | fl allow*

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Hvordan kan jeg forhindre mine eksisterne brugere i at begynde at bruge Power BI?
Som administrator kan du tage forholdsregler for at forhindre brugere i at tilmelde sig Power BI. Hvis du blokerer dette, vil brugernes forsøg på at tilmelde sig mislykkes, og de får besked om at kontakte administratoren for deres organisation. Du skal ikke gentage denne proces, hvis du allerede har deaktiveret automatisk licensdistribution (f.eks. Office 365 for Education til studerende, undervisere og ansatte). [Få mere at vide](service-admin-licensing-organization.md#enable-or-disable-individual-user-sign-up-in-azure-active-directory)

AAD-indstillingen, der styrer dette, er **AllowAdHocSubscriptions**. For de fleste lejere vil denne indstilling være indstillet til sand, hvilket betyder, at den er aktiveret. Hvis du har købt Power BI via en partner, kan denne indstilling som standard være indstillet til falsk, hvilket betyder, at den er deaktiveret.

Du skal installere den seneste 64-bit version af [Azure Active Directory Module til Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) for at udføre følgende trin.

1. Du skal først logge på Azure Active Directory ved hjælp af dine legitimationsoplysninger til Office 365. Den første linje beder dig om dine legitimationsoplysninger. Den anden linje opretter forbindelse til Azure Active Directory.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Når du er logget på, kan du udstede følgende kommando for at se, hvad din lejer i øjeblikket er konfigureret til.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Du kan bruge denne kommando til at aktivere ($true) eller deaktivere ($false) AllowAdHocSubscriptions.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> AllowAdHocSubscriptions-flaget bruges til at kontrollere flere brugeregenskaber i organisationen, herunder muligheden for at brugere kan tilmelde sig Azure Rights Management Service. Alle disse egenskaber påvirkes, hvis flaget ændres.
> 
> 

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Hvordan kan jeg tillade mine eksisterende brugere at tilmelde sig Power BI?
Tillad dine eksisterne brugere at tilmelde sig Power BI ved at køre kommandoen angivet for ovenstående spørgsmål, men brug true i stedet for false.

Du skal installere den seneste 64-bit version af [Azure Active Directory Module til Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) for at udføre følgende trin.

1. Du skal først logge på Azure Active Directory ved hjælp af dine legitimationsoplysninger til Office 365. Den første linje beder dig om dine legitimationsoplysninger. Den anden linje opretter forbindelse til Azure Active Directory.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Når du er logget på, kan du udstede følgende kommando for at se, hvad din lejer i øjeblikket er konfigureret til.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Du kan bruge denne kommando til at aktivere ($true) eller deaktivere ($false) AllowAdHocSubscriptions.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> AllowAdHocSubscriptions-flaget bruges til at kontrollere flere brugeregenskaber i organisationen, herunder muligheden for at brugere kan tilmelde sig Azure Rights Management Service. Alle disse egenskaber påvirkes, hvis flaget ændres.
> 
> 

## <a name="administration-of-power-bi"></a>Administration af Power BI
### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Hvordan vil dette ændre den måde, jeg administrerer identiteter for brugerne i organisationen på i dag?
Hvis organisationen allerede har et eksisterende Office 365-miljø, og alle brugerne i organisationen har Office 365-konti, ændres identitetsstyringen ikke.

Hvis organisationen allerede har et eksisterende Office 365-miljø, men det ikke er alle brugerne i organisationen, der har Office 365-konti, opretter vi en bruger i lejeren og tildeler licenser på baggrund af brugernes arbejds- eller skolemailadresser. Det betyder, at antallet af brugere, som du administrerer på et givent tidspunkt, vil vokse, efterhånden som brugerne i organisationen tilmelder sig tjenesten.

Hvis din organisation ikke har et Office 365-miljø, der er sluttet til dit maildomæne, er der ingen ændring i, hvordan du administrerer identiteter. Brugerne føjes til en ny brugermappe udelukkende for cloudmiljøet, og du får mulighed for at overtage lejeradministrationen og administrere dem.

### <a name="how-do-we-manage-power-bi"></a>Hvordan administrerer vi Power BI?
Power BI har en administratorportal, der giver dig mulighed for at se brugsstatistik, den indeholder et link til Office 365 Administration for at administrere brugere og grupper, og du kan kontrollere indstillinger på tværs af lejere. 

> [!NOTE]
> Din konto skal være markeret som en **Global administrator** i Office 365 eller Azure Active Directory, eller den skal være tildelt Power BI-tjenesteadministratorrollen for at få adgang til Power BI-administrationsportalen. Du kan finde flere oplysninger om Power BI-tjenesteadministratorrollen under [Beskrivelse af rollen som Power BI-administrator](service-admin-role.md).
> 
> 

Se [Power BI-administrationsportalen](service-admin-portal.md), hvis du vil have mere at vide.

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Hvad er processen til administration af en lejer, der er oprettet af Microsoft for brugerne?
Hvis en lejer blev oprettet af Microsoft, kan du gøre krav på og administrere den pågældende lejer vha. følgende trin:

1. Deltag i lejeren ved at tilmelde dig Power BI med et mailadressedomæne, der stemmer overens med det lejerdomæne, du vil administrere. Hvis Microsoft f.eks. oprettede lejeren contoso.com, skal du forbinde lejeren med en mailadresse, der slutter med @contoso.com.
2. Få administratorkontrol ved at bekræfte ejerskabet over domænet: Når du har adgang til lejren, kan du forfremme dig selv til *Global Administrator* ved at bekræfte ejerskabet over domænet. Det gør du ved at gennemgå disse trin:
   
   1. Gå til [https://portal.office.com](https://portal.office.com).
   2. Vælg ikonet for appstarteren i øverste venstre hjørne, og vælg derefter **Administrator**.
   3. Læs instruktionerne på siden **Bliv administrator**, og vælg derefter **Ja, jeg vil være administratoren**.
      
      > [!NOTE]
      > Hvis denne indstilling ikke vises, er der allerede en Office 365-administrator.
      > 
      > 

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Kan jeg kontrollere den Office 365-lejer, som brugerne er føjet til, hvis jeg har flere domæner?
Hvis du ikke foretager dig noget, oprettes der en lejer for hvert brugermaildomæne og underdomæne.

Hvis du ønsker, at alle brugerne skal være i samme lejer uanset deres mailadresseudvidelser:

* Opret en destinationslejer på forhånd, eller brug en eksisterende lejer, og tilføj alle eksisterende domæner og underdomæner, som du vil samle i lejeren. Derefter deltager alle brugerne med mailadresser, der slutter med de pågældende domæner og underdomæner, automatisk i destinationslejeren, når de tilmelder sig.

> [!IMPORTANT]
> Der er ikke en understøttet automatiseret mekanisme, der kan flytte brugerne på tværs af lejere, når de først er blevet oprettet. Hvis du vil have mere at vide om tilføjelse af domæner til en enkelt Office 365-lejer, skal du se [Føj dine brugere og domæner til Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
> 
> 

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Hvordan fjerner jeg Power BI for brugere, der allerede er tilmeldt?
Hvis en bruger har tilmeldt sig Power BI, men du ikke længere ønsker, at vedkommende skal have adgang til Power BI, kan du fjerne Power BI-licensen fra brugeren.

1. Naviger til Office 365 Administration.
2. I navigationspanelet til venstre skal du vælge **Brugere** og derefter vælge  > **Aktive brugere**.
3. Find den bruger, du vil fjerne licensen fra, og vælg derefter vedkommendes navn > **Rediger**.
4. På siden med brugeroplysninger skal du vælge **Licenser** i det venstre navigationspanel.
5. Fjern markeringen i afkrydsningsfeltet **Power BI (gratis)**, eller **Power BI Pro**, afhængigt af hvilken licens der er gældende for vedkommendes konto.
6. Vælg **Gem**.

> [!NOTE]
> Du kan administrere mange licenser for brugere. Gør dette ved at vælge mange brugere og vælge **Rediger**.
> 
> 

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Hvordan får jeg besked, når nye brugere slutter sig til min lejer?
Brugere, der har tilmeldt sig lejeren som en del af dette program, tildeles en unik licens, som du kan filtrere efter i din aktive brugerrude i administratordashboardet.

Opret denne nye visning i Office 365 Administrator ved at gå til **Brugere** > **Aktive brugere** og i menuen **Vælg en visning** vælge **Ny visning**. Navngiv din nye visning, og under **Tildel licens** skal du vælge **Power BI (gratis)** eller **Power BI Pro**. Du kan kun have en licens pr. valgt visning. Hvis du har både **Power BI (gratis)**- og **Power BI Pro**-licenser i organisationen, skal du oprette to visninger. Når den nye visning er blevet oprettet, kan du se alle brugerne i lejeren, der er tilmeldt dette program.

### <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Er der andet jeg skal være forberedt på?
Du oplever måske en stigning i anmodninger om nulstilling af adgangskode. Se [Nulstil en brugers adgangskode](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c) for at få flere oplysninger om denne proces.

Du kan fjerne en bruger fra lejeren vha. standardprocessen i Office 365 Administration. Men hvis brugeren stadig har en aktiv mailadresse fra organisationen, kan vedkommende tilmelde sig igen, medmindre du blokerer alle brugere fra at tilmelde sig.

### <a name="where-is-my-power-bi-tenant-located"></a>Hvor er min Power BI-lejer placeret?
Lær, hvordan du finder ud af, hvor din Power BI-lejer er, også kendt som dataregion, ved at se [Hvor findes min Power BI-lejer?](service-admin-where-is-my-tenant-located.md)

### <a name="what-is-the-power-bi-sla"></a>Hvad er Power BI SLA?
Hvis du vil have oplysninger om Power BI SLA (Serviceniveauaftale), skal du konsultere artiklen [Licensvilkår og dokumentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) i sektionen **Licenser** på webstedet Microsoft Licensing.

## <a name="security-in-power-bi"></a>Sikkerhed i Power BI
### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Opfylder Power BI nationale, regionale og branchespecifikke overholdelseskrav?
Få mere at vide om Power BI-overholdelse ved at se [Microsoft Center for sikkerhed og rettighedsadministration](http://go.microsoft.com/fwlink/?LinkId=785324).

### <a name="how-does-security-work-in-power-bi"></a>Hvordan fungerer sikkerhed i Power BI?
Power BI er bygget på grundlag af Office 365, der igen er bygget på Azure-tjenester som Azure Active Directory. Se en oversigt over Power BI-arkitektur i [Sikkerhed i Power BI](service-admin-power-bi-security.md). 

## <a name="next-steps"></a>Næste trin
[Power BI-administrationsportal](service-admin-portal.md)  
[Beskrivelse af rollen som Power BI-administrator](service-admin-role.md)  
[Tilmelding via selvbetjening til Power BI](service-self-service-signup-for-power-bi.md)  
[Køb Power BI Pro](service-admin-purchasing-power-bi-pro.md)  
[Hvad er Power BI Premium?](service-premium.md)  
[Sådan køber du Power BI Premium](service-admin-premium-purchase.md)  
[Administration af brugerkonto i Office 365](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Administration af gruppe i Office 365](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  
[Administrer din gruppe i Power BI og Office 365](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Hvidbog om Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

Flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)