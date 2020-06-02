---
title: Power BI-administrationsportal
description: Administrationsportalen giver adgang til lejeradministration af Power BI i virksomheden. Den indeholder elementer såsom metrikværdier, adgang til Microsoft 365 Administration og indstillinger.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 05/12/2020
ms.author: kfollis
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 605d35d55f3191b230d9c4a8d118e2c238283ff2
ms.sourcegitcommit: c1f05254eaf5adb563f8d4f33c299119134c7d1f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/21/2020
ms.locfileid: "83733576"
---
# <a name="administering-power-bi-in-the-admin-portal"></a>Administrer Power BI på administrationsportalen

På administrationsportalen kan du administrere en Power BI-*lejer* for din organisation. Portalen indeholder elementer såsom metrikværdier, adgang til Microsoft 365 Administration og indstillinger.

Hele administrationsportalen kan tilgås af alle brugere, som er globale administratorer, eller som er blevet tildelt rollen som administrator af Power BI-tjenesten. Hvis du ikke har en af disse roller, kan du kun se **Kapacitetsindstillinger** på portalen. Du kan finde flere oplysninger om Power BI-tjenesteadministratorrollen under [Beskrivelse af rollen som Power BI-administrator](service-admin-role.md).

## <a name="how-to-get-to-the-admin-portal"></a>Sådan finder du vej til administrationsportalen

Din konto skal være markeret som **Global administrator** i Microsoft 365 eller Azure AD (Azure Active Directory), eller den skal være tildelt rollen som administrator af Power BI-tjenesten, før du kan få adgang til Power BI-administrationsportalen. Du kan finde flere oplysninger om Power BI-tjenesteadministratorrollen under [Beskrivelse af rollen som Power BI-administrator](service-admin-role.md). Benyt følgende fremgangsmåde for at tilgå Power BI-administrationsportalen.

1. Vælg tandhjulet Indstillinger i øverste højre hjørne af Power BI-tjenesten.

1. Vælg **Administrationsportal**.

    ![Indstillinger på administrationsportalen](media/service-admin-portal/powerbi-admin-settings.png)

Der er ni faner på portalen. Resten af denne artikel indeholder oplysninger om hver af disse faner.

![Navigation på administrationsportalen](media/service-admin-portal/powerbi-admin-landing-page.png)

* [Forbrugsdata](#usage-metrics)
* [Brugere](#users)
* [Overvågningslogge](#audit-logs)
* [Lejerindstillinger](#tenant-settings)
* [Kapacitetsindstillinger](#capacity-settings)
* [Integrer koder](#embed-codes)
* [Visualiseringer til virksomheder](#organizational-visuals)
* [Dataflowlager (eksempelvisning)](#dataflowStorage)
* [Arbejdsområder](#workspaces)
* [Brugerdefineret branding](#custom-branding)

## <a name="usage-metrics"></a>Forbrugsdata

Med **Forbrugsdata** kan du overvåge Power BI-forbruget i organisationen. Den giver dig også mulighed for at se, hvilke brugere og grupper, der er mest aktive i Power BI i virksomheden. 

> [!NOTE]
> Første gang du tilgår dashboard'et, eller når du besøger det igen efter en lang periode uden at åbne dashboard'et, så får du sandsynligvis vist indlæsningsskærmen, mens vi indlæser dashboard'et.

Når dashboardet er indlæst, får du vist to afsnit med felter. Det første afsnit indeholder forbrugsdata for individuelle brugere, og det andet afsnit har lignende oplysninger for grupper i din organisation.

Nedenfor er en oversigt over indholdet i hvert felt:

* Specifik optælling af alle dashboards, rapporter og datasæt i brugerarbejdsområdet.
  
    ![Særskilt optælling af dashboards, rapporter og datasæt](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* Mest brugte dashboard efter antallet af brugere, der har adgang til det. Hvis du f.eks. har et dashboard, som du har delt med tre brugere, og du også har føjet det til en indholdspakke med to forskellige brugere tilsluttet, så er antallet 6 (1 + 3 + 2).
  
    ![Mest anvendte dashboards](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* Det mest populære indhold, som brugere har oprettet forbindelse til. Dette vil være alt vilkårligt indhold, som brugere kan tilgå gennem Hent data-processen, dvs. Saas-indholdspakker, organisatoriske indholdspakker, filer eller databaser.
  
    ![Mest anvendte pakker](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* En visning af dine vigtigste brugere baseret på, hvor mange dashboards de har, både dashboards de selv har oprettet, og dashboards der er delt med dem.
  
    ![Topbrugere – dashboards](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* En visning af dine vigtigste brugere baseret på, hvor mange rapporter de har.
  
    ![Topbrugere – rapporter](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

Det andet afsnit viser den samme type oplysninger, men baseret på grupper. Her kan du se, hvilke grupper i organisationen der er mest aktive, og hvilken slags indhold de bruger.

Med disse oplysninger kan du få reel indsigt i, hvordan personer bruger Power BI på tværs af organisationen, og du kan holde styr på, hvilke af de pågældende brugere og grupper der er meget aktive i organisationen.

## <a name="control-usage-metrics"></a>Kontrollér forbrugsdata

Rapporter med forbrugsdata er en funktion, som Power BI- eller Microsoft 365-administratoren kan slå til eller fra. Administratorer har detaljeret kontrol over, hvilke brugere der har adgang til forbrugsdata. Det er slået **Til** som standard for alle brugere i organisationen.

Administratorer kan også bestemme, om oprettere af indhold kan se brugerspecifikke data i forbrugsdata. 

Få mere at vide om selve rapporterne under [Overvåg forbrugsdata for dashboards og rapporter](../collaborate-share/service-usage-metrics.md).

### <a name="usage-metrics-for-content-creators"></a>Forbrugsdata for oprettere af indhold

1. På administrationsportalen skal du vælge **Lejerindstillinger** > **Forbrugsdata for oprettere af indhold**.

    ![Forbrugsdata i lejerindstillingerne på administrationsportalen](media/service-admin-portal/power-bi-admin-usage-metrics.png)

1. Aktivér (eller deaktiver) forbrugsdata > **Anvend**.

    ![Forbrugsdata er aktiveret](../collaborate-share/media/service-usage-metrics/power-bi-tenant-settings-updated.png)


### <a name="per-user-data-in-usage-metrics"></a>Brugerspecifikke data i forbrugsdata

Brugerspecifikke data er som standard aktiveret for forbrugsdata, og kontooplysninger om forbrugere af indhold indgår i rapporten med forbrugsdata. Hvis du ikke vil medtage disse oplysninger for nogle eller alle brugere, kan du deaktivere funktionen for nærmere angivne sikkerhedsgrupper eller for en hel organisation. Kontooplysninger vises derefter i rapporten som *Ikke-navngivet*.

![Brugerspecifikke forbrugsdata](media/service-admin-portal/power-bi-admin-per-user-usage-data.png)

### <a name="delete-all-existing-usage-metrics-content"></a>Slet alt eksisterende forbrugsdataindhold

Når administratorer deaktiverer forbrugsdata for hele organisationen, kan de kan også vælge en af eller begge disse indstillinger:

- **Slet alt eksisterende forbrugsdataindhold** til at slette alle eksisterende rapporter og dashboardfelter, der blev oprettet ved hjælp af forbrugsdatarapporter og -datasæt. Denne indstilling fjerner al adgang til forbrugsdata for alle brugere i organisationen, som muligvis allerede anvender dem. 
- **Slet alle eksisterende brugerspecifikke data i det aktuelle forbrugsdataindhold** Denne indstilling fjerner al adgang til forbrugsdata for alle brugere i organisationen, som muligvis allerede anvender dem. 

Vær forsigtig med at gøre dette, da sletning af eksisterende forbrugsdataindhold og brugerspecifikke data ikke kan fortrydes.

## <a name="users"></a>Brugere

Du kan administrere Power BI-brugere, -grupper og -administratorer i Microsoft 365 Administration. Fanen **Brugere** indeholder et link til Administration for din lejer.

![Gå til Microsoft 365 Administration](media/service-admin-portal/powerbi-admin-manage-users.png)

## <a name="audit-logs"></a>Overvågningslogge

Du kan administrere Power BI-overvågningslogge i Office 365 Security & Compliance Center. Fanen **Overvågningslogge** indeholder et link til Security & Compliance Center for din lejer. [Få mere at vide](service-admin-auditing.md)

Hvis du vil bruge overvågningslogs, skal du sørge for, at indstillingen [**Opret overvågningslogs til overvågning af intern aktivitet og overholdelse af angivne standarder**](#create-audit-logs-for-internal-activity-auditing-and-compliance) er aktiveret.

## <a name="tenant-settings"></a>Lejerindstillinger

Fanen **Lejerindstillinger** giver dig detaljeret kontrol over de funktioner, der er til rådighed for din organisation. Hvis du har bekymringer om følsomme data, kan det være, at nogle af vores funktioner ikke er passende for din organisation, eller du vil måske kun have, at en bestemt funktion er tilgængelig for en bestemt gruppe.

På følgende billede ses flere indstillinger under fanen **Lejerindstillinger**.

![Lejerindstillinger](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> Det kan tage op til 10 minutter, før indstillingen træder i kraft for alle i din lejer.

Indstillingerne kan have tre tilstande:

* **Deaktiveret for hele organisationen**: Ingen i din organisation kan bruge denne funktion.

    ![Indstilling deaktiveret for alle](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

* **Aktiveret for hele organisationen**: Alle i din organisation kan bruge denne funktion.

    ![Indstilling aktiveret for alle](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

* **Aktiveret for en del af organisationen**: Et bestemt undersæt af brugere eller grupper i organisationen kan bruge denne funktion.

    Du kan aktivere funktionen for hele organisationen med undtagelse af en bestemt gruppe brugere.

    ![Indstilling aktiveret for en delmængde](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

    Du kan også aktivere funktionen udelukkende for en bestemt gruppe af brugere og deaktivere den for nogle brugere. Med denne tilgang sikrer du, at visse brugere ikke har adgang til funktionen, selvom de er medlemmer af den tilladte gruppe.

    ![Indstilling aktiveret med undtagelse](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

De næste par afsnit giver et overblik over de forskellige typer af lejerindstillinger.

## <a name="help-and-support-settings"></a>Indstillinger for hjælp og support

### <a name="publish-get-help-information"></a>Publicer "Få hjælp"-oplysninger

Brugere i organisationen kan gå til interne hjælp- og supportressourcer i Power BI-menuen Hjælp. Funktionaliteten for disse parametre ændres specifikt for menupunkterne Lær, Community og Få hjælp.

Når du angiver en URL-adresse til licensanmodninger, tilpasser du også destinationens URL-adresse for knappen **Opgrader konto**. Brugere uden en Power BI Pro-licens kan se denne knap i dialogboksen **Opdater til Power BI Pro** samt på siden **Administrer personligt lager**. Desuden tilbyder Power BI ikke længere knappen **Prøv Pro gratis** i denne dialogboks eller på lagersiden. Dette sikrer, at Power BI på en pålidelig måde hjælper dine brugere gennem de processer, der er defineret i din organisation, via løsningen til licensstyring.

![Indstilling aktiveret med undtagelse](media/service-admin-portal/powerbi-admin-tenant-settings-gethelp.png)

### <a name="receive-email-notifications-for-service-outages-or-incidents"></a>Modtag mails ved tjenesteafbrydelser eller -hændelser

Mailaktiverede sikkerhedsgrupper modtager mails, hvis lejeren påvirkes af en tjenesteafbrydelse eller -hændelse. Få mere at vide om [Meddelelser om tjenesteafbrydelser](service-interruption-notifications.md).

## <a name="workspace-settings"></a>Indstillinger for arbejdsområde

I **lejerindstillinger** har administrationsportalen to afsnit til at styre arbejdsområder:

- Opret den nye arbejdsområdeoplevelse.
- Brug datasæt på tværs af arbejdsområder.

### <a name="create-the-new-workspaces"></a>Opret de nye arbejdsområder

Arbejdsområder er steder, hvor brugerne kan samarbejde om dashboards, rapporter og andet indhold. Administratorer bruger indstillingen **Opret arbejdsområder (ny arbejdsområdeoplevelse)** til at angive, hvilke brugere i organisationen der kan oprette arbejdsområder. Administratorer kan give alle eller ingen i en organisation tilladelse til at oprette arbejdsområder i den nye arbejdsområdeoplevelse. De kan også begrænse oprettelse til medlemmer af bestemte sikkerhedsgrupper. Få mere at vide om [arbejdsområder](../collaborate-share/service-new-workspaces.md).

:::image type="content" source="media/service-admin-portal/power-bi-admin-workspace-settings.png" alt-text="Opret de nye arbejdsområdeoplevelser":::

I forbindelse med klassiske arbejdsområder, der er baseret på Microsoft 365 Grupper, finder administrationen fortsat sted på administrationsportalen og i Azure Active Directory.

> [!NOTE]
> Indstillingen **Opret arbejdsområder (i den nye arbejdsområdeoplevelse)** er som standard angivet til kun at give de brugere, der kan oprette Microsoft 365-grupper, tilladelse til at oprette nye arbejdsområder i Power BI. Sørg for at angive en værdi i Power BI-administrationsportalen for at sikre, at relevante brugere kan oprette arbejdsområder.

**Liste over arbejdsområder**

Administrationsportalen indeholder en anden sektion med indstillinger for arbejdsområderne i din lejer. I denne sektion kan du sortere og filtrere listen over arbejdsområder og få vist detaljerne for hvert arbejdsområde. Se [Arbejdsområder](#workspaces) i denne artikel for at få flere oplysninger.

**Publicer indholdspakker og apps**

I administrationsportalen kan du også styre, hvilke brugere der har tilladelse til at distribuere apps til organisationen. Se [Publicer indholdspakker og apps til hele organisationen](#publish-content-packs-and-apps-to-the-entire-organization) i denne artikel for at få flere oplysninger.

### <a name="use-datasets-across-workspaces"></a>Brug datasæt på tværs af arbejdsområder

Administratorer kan styre, hvilke brugere i organisationen der kan bruge datasæt på tværs af arbejdsområder. Når denne indstilling er aktiveret, skal brugerne stadig bruge den påkrævede Build-tilladelse til et bestemt datasæt.

:::image type="content" source="media/service-admin-portal/power-bi-admin-datasets-workspaces.png" alt-text="Brug datasæt på tværs af arbejdsområder":::

Du kan få flere oplysninger under [Introduktion til datasæt på tværs af arbejdsområder](../connect-data/service-datasets-across-workspaces.md).


## <a name="export-and-sharing-settings"></a>Indstillinger for eksport og deling

### <a name="share-content-with-external-users"></a>Del indhold med eksterne brugere

Brugere i organisationen kan dele dashboards, rapporter og apps med brugere uden for organisationen. Få mere at vide om [ekstern deling](../collaborate-share/service-share-dashboards.md#share-a-dashboard-or-report-outside-your-organization).

![Indstilling for eksterne brugere](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

På følgende billede ses den meddelelse, som vises, når du deler med en ekstern bruger.

![Deling med ekstern bruger](media/service-admin-portal/powerbi-admin-sharing-external.png)  

> [!IMPORTANT]
> Denne indstilling styrer, om brugere i Power BI kan invitere eksterne brugere til at blive Azure AD B2B-gæstebrugere (Azure Active Directory B2B) i din organisation via Power BI. Når denne funktion er aktiveret, kan brugere, der har rollen Kan invitere gæster i Azure AD, tilføje eksterne mailadresser ved deling af rapporter, dashboards og Power BI-apps. Den eksterne modtager inviteres til at deltage i din organisation som en Azure AD B2B-gæstebruger. Det er vigtigt at bemærke, at når denne indstilling deaktiveres, vises eksterne brugere, der allerede er Azure AD B2B-gæstebrugere i din organisation, stadig på grænseflader med personvælgere i Power BI og kan få tildelt adgang til elementer, arbejdsområder og apps.

### <a name="publish-to-web"></a>Publicer på internettet

Som administrator for en Power BI-lejer giver indstillingen **Publicer på internettet** dig mulighed for at vælge, hvilke brugere der kan oprette integreringskoder til udgivelse af rapporter på internettet. Denne funktion gør rapporten og de data, den indeholder, tilgængelige for alle på internettet. Få mere at vide om [publicering på internettet](../collaborate-share/service-publish-to-web.md).

> [!NOTE]
> Det er kun Power BI-administratorer, der kan tillade oprettelse af nye integreringskoder til publicering på internettet. Organisationer kan have eksisterende integreringskoder. Se afsnittet [Integreringskoder](service-admin-portal.md#embed-codes) i administrationsportalen for at gennemse de aktuelt udgivne rapporter.

På følgende billede ses menuen **Flere indstillinger (...)** for en rapport, når indstillingen **Publicer på internettet** er aktiveret.

![Publicer på internettet i menuen Flere indstillinger](media/service-admin-portal/power-bi-more-options-publish-web.png)

Indstillingen **Publicer på internettet** i administrationsportalen gør det muligt at angive, hvilke brugere der kan oprette integreringskoder.

![Indstillingen Publicer på internettet](media/service-admin-portal/powerbi-admin-publish-to-web-setting.png)

Administratorer kan indstille **Publicer på internettet** til **Aktiveret** og **Vælg, hvordan integreringskoder fungerer** til **Tillad kun eksisterende integreringskoder**. I dette tilfælde kan brugerne oprette integreringskoder, men de skal kontakte Power BI-administratoren for at få tilladelse til at gøre det.

![Prompten Publicer på internettet](../collaborate-share/media/service-publish-to-web/publish_to_web_admin_prompt.png)

Brugere kan se forskellige indstillinger på brugergrænsefladen afhængigt af indstillingen **Publicer på internettet**.

|Funktion |Aktiveret for hele organisationen |Deaktiveret for hele organisationen |Specifikke sikkerhedsgrupper   |
|---------|---------|---------|---------|
|**Publicer på internettet** i menuen **Flere indstillinger (...)** for rapporten|Aktiveret for alle|Ikke synligt for alle|Kun synligt for godkendte brugere eller grupper.|
|**Håndter integreringskoder** under **Indstillinger**|Aktiveret for alle|Aktiveret for alle|Aktiveret for alle<br><br>Indstillingen * **Slet** er kun synlig for godkendte brugere eller grupper.<br>* **Hent koder** er aktiveret for alle.|
|**Integrer koder** i administrationsportalen|Status afspejler et af følgende:<br>* Aktiv<br>* Ikke understøttet<br>* Blokeret|Status viser **Deaktiveret**|Status afspejler et af følgende:<br>* Aktiv<br>* Ikke understøttet<br>* Blokeret<br><br>Hvis en bruger ikke er godkendt på grund af indstillingen af lejeren, vises status som **Krænkelse**.|
|Eksisterende publicerede rapporter|Alle aktiveret|Alle deaktiveret|Rapporter fortsætter med at gengive for alle.|

### <a name="export-data"></a>Eksportér data

Brugere i virksomheden kan eksportere data fra et felt eller en visualisering. Dette styrer, Analysér i Excel, eksport til. csv, overførsler af datasæt (. pbix) og funktionerne i Power BI Service Live Connect. Få mere at vide om [eksport af data fra et felt eller en visualisering](../visuals/power-bi-visualization-export-data.md).

>[!NOTE]
> Før introduktionen af indstillingen Eksportér til Excel styrede denne indstilling også eksport af data til Excel-filer. Du finder flere oplysninger i [noten under Eksportér til Excel](#export-to-excel).

![Indstillingen Eksportér data](media/service-admin-portal/powerbi-admin-portal-export-data-setting.png)

På følgende billede ses indstillingen for at eksportere data fra et felt.

![Eksportér data fra et felt](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> Hvis **Eksportér data** deaktiveres, kan brugere ikke anvende funktionen [Analysér i Excel](../collaborate-share/service-analyze-in-excel.md) og heller ikke bruge Power BI-tjenestens direkte forbindelse.

### <a name="export-to-excel"></a>Eksportér til Excel

Brugere i organisationen kan eksportere dataene fra en visualisering til en Excel-fil.

![Indstillingen Eksportér til Excel](media/service-admin-portal/powerbi-admin-portal-export-to-excel-setting.png)

>[!IMPORTANT]
> Før introduktionen af indstillingen Eksportér til Excel styrede indstillingen Eksportér data eksport til en Excel-fil. I de lejere, der fandtes før introduktionen af indstillingen Eksportér to Excel, kan lejeradministratorerne derfor se, at der er *Ikke-anvendte ændringer*, første gang de ser indstillingen Eksportér til Excel. De skal anvende disse ændringer, før den nye indstilling træder i kraft. I modsat fald styres eksporten til en Excel-fil fortsat af indstillingen Eksportér data.

### <a name="export-reports-as-powerpoint-presentations-or-pdf-documents"></a>Eksportér rapporter som PowerPoint-præsentationer eller PDF-dokumenter

Brugere i organisationen kan eksportere Power BI-rapporter som PowerPoint-filer eller PDF-dokumenter. [Få mere at vide](../consumer/end-user-powerpoint.md)

På følgende billede ses menuen **Filer** for en rapport, når indstillingen **Eksportér rapporter som PowerPoint-præsentationer eller PDF-dokumenter** er aktiveret.

![Eksportér rapporter som PowerPoint-præsentationer](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Udskriv dashboards og rapporter

Brugere i virksomheden kan udskrive dashboards og rapporter. [Få mere at vide](../consumer/end-user-print.md)

På følgende billede ses indstillingen for at udskrive et dashboard.

![Udskriv dashboard](media/service-admin-portal/powerbi-admin-print-dashboard.png)

På følgende billede ses menuen **Filer** for en rapport, når indstillingen **Udskriv dashboards og rapporter** er aktiveret.

![Udskriv rapport](media/service-admin-portal/powerbi-admin-print-report.png)

### <a name="allow-external-guest-users-to-edit-and-manage-content-in-the-organization"></a>Tillad, at eksterne brugere kan redigere og administrere indhold i organisationen

Azure AD B2B-gæstebrugere kan redigere og administrere indhold i organisationen. [Få mere at vide](service-admin-azure-ad-b2b.md)

På følgende billede vises indstillingen Tillad, at eksterne brugere kan redigere og administrere indhold i organisationen.

![Tillad, at eksterne brugere kan redigere og administrere indhold i organisationen](media/service-admin-portal/powerbi-admin-tenant-settings-b2b-guest-edit-manage.png)

I administrationsportalen kan du også styre, hvilke brugere der har tilladelse til at invitere eksterne brugere til organisationen. Se [Del indhold med eksterne brugere](#export-and-sharing-settings) i denne artikel for at få flere oplysninger.

### <a name="email-subscriptions"></a>Mailabonnementer
Brugere i organisationen kan oprette mailabonnementer. Få mere at vide om [abonnementer](../collaborate-share/service-publish-to-web.md).

![Aktivér mailabonnementer](media/service-admin-portal/power-bi-manage-email-subscriptions.png)

### <a name="featured-content"></a>Fremhævet indhold

Gør det muligt for nogle af eller alle rapportforfattere i din organisation at fremhæve deres indhold i afsnittet Udvalgte Power BI Start. Nye brugere kan se fremhævet indhold øverst på deres Power BI Start-side. Fremhævet indhold flyttes ned på startsiden, efterhånden som brugerne tilføjer **favoritter**, **ofte viste**og **seneste viste**. 

Vi anbefaler, at du starter med et lille antal promotorer. Det kan gøre det svært at holde styr på alt det fremhævede indhold, hvis hele organisationen har mulighed for at fremhæve indhold på startsiden. 

Når du har gjort det muligt at fremhæve indhold, kan du også administrere det i administrationsportalen. Se [Administrer fremhævet indhold](#manage-featured-content) i denne artikel for at få mere at vide om, hvordan du styrer fremhævet indhold i dit domæne.

## <a name="content-pack-and-app-settings"></a>Indholdspakke og appindstillinger

### <a name="publish-content-packs-and-apps-to-the-entire-organization"></a>Publicer indholdspakker og apps til hele organisationen

Administratorer bruger denne indstilling til at bestemme, hvilke brugere i organisationen der kan publicere indholdspakker og apps til hele organisationen frem for kun til specifikke grupper. Få mere at vide om [publicering af apps](../collaborate-share/service-create-distribute-apps.md).

På følgende billede vises indstillingen **Hele min organisation**, når du opretter en indholdspakke.

![Publicer indholdspakke til organisation](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-apps-and-organizational-content-packs"></a>Opret skabelonbaserede apps og indholdspakker for organisationen

Brugere i virksomheden kan oprette skabelonbaserede apps og indholdspakker for organisationen, der bruger datasæt baseret på én datakilde i Power BI Desktop. Få mere at vide om [skabelonapps](../connect-data/service-template-apps-create.md).

### <a name="push-apps-to-end-users"></a>Push apps til slutbrugere

Rapportoprettere kan dele apps direkte med slutbrugere uden at kræve installation fra [AppSource](https://appsource.microsoft.com). Få mere at vide om [automatisk installation af apps til slutbrugere](../collaborate-share/service-create-distribute-apps.md#automatically-install-apps-for-end-users).

## <a name="integration-settings"></a>Integrationsindstillinger

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Brug Analysér i Excel med datasæt i det lokale miljø

Brugere i virksomheden kan bruge Excel til at se og interagere med Power BI-datasæt i det lokale miljø. [Få mere at vide](../collaborate-share/service-analyze-in-excel.md)

> [!NOTE]
> Hvis **Eksportér data** deaktiveres, kan brugere heller ikke anvende funktionen **Analysér i Excel**.

### <a name="use-arcgis-maps-for-power-bi"></a>Brug ArcGIS Maps for Power BI

Brugere i organisationen kan anvende ArcGIS Maps for Power BI-visualiseringen fra Esri. [Få mere at vide](../visuals/power-bi-visualization-arcgis.md)

### <a name="use-global-search-for-power-bi-preview"></a>Brug global søgning til Power BI (prøveversion)

Brugere i organisationen kan bruge eksterne søgefunktioner, der bruger Azure Search.

## <a name="featured-tables-settings"></a>Udvalgte tabelindstillinger

Lejerindstillingen **Tillad forbindelser til udvalgte tabeller** under **Lejerindstillinger** gør det muligt for Power BI-administratorer at styre, hvem der i organisationen kan bruge udvalgte tabeller i Excel-datatypegalleriet. 

:::image type="content" source="media/service-admin-portal/admin-allow-connections-featured-tables.png" alt-text="Alle forbindelser til udvalgte tabeller":::

Forbindelser til udvalgte tabeller deaktiveres også, hvis lejerindstillingen **Eksportér data** er angivet til **Deaktiveret**.

Læs mere om [Udvalgte Power BI-tabeller i Excel](../collaborate-share/service-excel-featured-tables.md).

## <a name="power-bi-visuals-settings"></a>Indstillinger for Power BI-visuals

### <a name="add-and-use-power-bi-visuals"></a>Tilføj og brug Power BI-visuals

Brugerne i organisationen kan interagere med og dele brugerdefinerede Power BI-visuals. [Få mere at vide](../developer/visuals/power-bi-custom-visuals.md)

> [!NOTE]
> Denne indstilling kan anvendes på hele organisationen, eller den kan begrænses til specifikke grupper.

Fra marts 2019 understøtter Power BI Desktop brugen af **Gruppepolitik** til at deaktivere brugen af Power BI-visuals på tværs af de computere, der er installeret i en organisation.

<table>
<tr><th>Attribut</th><th>Værdi</th>
</tr>
<td>key</td>
    <td>Software\Policies\Microsoft\Power BI Desktop\</td>
<tr>
<td>valueName</td>
<td>EnableCustomVisuals</td>
</tr>
</table>

En værdi på 1 (decimal) aktiverer brugen af Power BI-visuals i Power BI (dette er standarden).

En værdi på 0 (decimal) deaktiverer brugen af Power BI-visuals i Power BI.

### <a name="allow-only-certified-visuals"></a>Tillad kun certificerede visualiseringer

Brugere i organisationen, som er tildelt tilladelser til at tilføje og bruge Power BI-visuals med indstillingen "Tilføj og brug Power BI-visuals", kan kun bruge [certificerede Power BI-visuals](https://go.microsoft.com/fwlink/?linkid=2002010) (de ikke-certificerede visuals blokeres, og der vises en fejlmeddelelse, når de bruges). 


Fra marts 2019 understøtter Power BI Desktop brugen af **Gruppepolitik** til at deaktivere brugen af ikke-certificerede Power BI-visuals på tværs af de computere, der er installeret i en organisation.

<table>
<tr><th>Attribut</th><th>Værdi</th>
</tr>
<td>key</td>
    <td>Software\Policies\Microsoft\Power BI Desktop\</td>
<tr>
<td>valueName</td>
<td>EnableUncertifiedVisuals</td>
</tr>
</table>

En værdi på 1 (decimal) aktiverer brugen af ikke-certificerede Power BI-visuals i Power BI (dette er standarden).

En værdi på 0 (decimal) deaktiverer brugen af ikke-certificerede Power BI-visuals i Power BI (denne indstilling aktiverer kun brugen af [certificerede Power BI-visuals](https://go.microsoft.com/fwlink/?linkid=2002010)).

## <a name="r-visuals-settings"></a>R visuals – indstillinger

### <a name="interact-with-and-share-r-visuals"></a>Interager med og del R-visualiseringer

Brugere i virksomheden kan interagere med og dele visuelle elementer oprettet med R-scripts. [Få mere at vide](../visuals/service-r-visuals.md)

> [!NOTE]
> Denne indstilling gælder for hele organisationen og kan ikke begrænses til bestemte grupper.

## <a name="audit-and-usage-settings"></a>Indstillinger for overvågning og brug

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>Opret overvågningslogge for intern aktivitetsovervågning og overholdelse

Brugere i virksomheden kan overvåge handlinger, der udføres i Power BI af andre brugere i virksomheden. [Få mere at vide](service-admin-auditing.md)

Denne indstilling skal være aktiveret, for at overvågningslogposter bliver registreret. Der kan være op til 48 timers forsinkelse, fra at du aktiverer overvågning, til at du får vist data i overvågningsloggen. Hvis du ikke får vist data med det samme, skal du tjekke overvågningsloggene senere. Der kan være en lignende forsinkelse mellem at få tilladelse til at få vist overvågningslogge og til at kunne åbne logfilerne.

> [!NOTE]
> Denne indstilling gælder for hele organisationen og kan ikke begrænses til bestemte grupper.

### <a name="usage-metrics-for-content-creators"></a>Forbrugsdata for oprettere af indhold

Brugere i organisationen kan se forbrugsdata for dashboards og rapporter, som de opretter. [Få mere at vide](../collaborate-share/service-usage-metrics.md)

### <a name="per-user-data-in-usage-metrics-for-content-creators"></a>Brugerspecifikke data i forbrugsdata for indholdsforfattere

Forbrugsdata for indholdsforfattere viser viste navne og mailadresser for de brugere, der har adgang til indhold. [Få mere at vide](../collaborate-share/service-usage-metrics.md)

Brugerspecifikke data er som standard aktiveret for forbrugsdata, og kontooplysninger om indholdsforfattere indgår i rapporten med forbrugsdata. Hvis du ikke vil indsamle disse oplysninger for alle brugere, kan du deaktivere funktionen for nærmere angivne sikkerhedsgrupper eller for en hel organisation. Kontooplysningerne for de ekskluderede brugere vises derefter i rapporten som *Ikke-navngivet*.

## <a name="dashboard-settings"></a>Indstillinger for dashboard

### <a name="data-classification-for-dashboards"></a>Dataklassifikation for dashboards

Brugere i organisationen kan markere dashboards med klassificeringsangivelser, der angiver sikkerhedsniveauer for dashboards. [Få mere at vide](../create-reports/service-data-classification.md)

> [!NOTE]
> Denne indstilling gælder for hele organisationen og kan ikke begrænses til bestemte grupper.

## <a name="developer-settings"></a>Indstillinger for udviklere

### <a name="embed-content-in-apps"></a>Integrer indhold i apps

Brugere i virksomheden kan integrere Power BI-dashboards og rapporter i Software as a Service (SaaS)-programmer. Hvis denne indstilling deaktiveres, kan brugere ikke anvende REST API'er til at integrere Power BI-indhold i deres program. [Få mere at vide](../developer/embedded/embedding.md)

### <a name="allow-service-principals-to-use-power-bi-apis"></a>Tillad, at tjenesteprincipaler bruger Power BI-API'er

Webapps, der er registreret i Azure Active Directory (Azure AD), bruger en tildelt tjenesteprincipal til at få adgang til Power BI-API'erne, uden at en bruger er logget på. Hvis du vil tillade, at en app anvender den godkendte tjenesteprincipal, skal tjenesteprincipalen være inkluderet i den tilladte sikkerhedsgruppe. [Få mere at vide](../developer/embedded/embed-service-principal.md)

> [!NOTE]
> Tjenesteprincipaler nedarver tilladelserne til alle Power BI-lejerindstillinger fra deres sikkerhedsgruppe. Hvis du vil begrænse tilladelserne, skal du oprette en dedikeret sikkerhedsgruppe for tjenesteprincipaler og føje den til listen "Undtagen specifikke sikkerhedsgrupper" for de relevante aktiverede Power BI-indstillinger.

## <a name="dataflow-settings"></a>Indstillinger for dataflow

### <a name="create-and-use-dataflows"></a>Opret og brug dataflow

Brugere i organisationen kan oprette og bruge dataflow. Du kan se en oversigt over dataflow i [Selvbetjent dataforberedelse i Power BI](../transform-model/service-dataflows-overview.md). Hvis du vil aktivere dataflow i en Premium-kapacitet, skal du se under [Konfigurer arbejdsbelastninger](service-admin-premium-workloads.md).

> [!NOTE]
> Denne indstilling gælder for hele organisationen og kan ikke begrænses til bestemte grupper.

## <a name="template-apps-settings"></a>Indstillinger for skabelonapps

Tre indstillinger styrer, hvorvidt skabelonapps kan publicere eller installere skabelonapps.

![Indstillinger for skabelonprogrammer på Power BI-administrationsportal](media/service-admin-portal/power-bi-admin-portal-template-apps.png)

### <a name="publish-template-apps"></a>Publicer skabelonapps

Brugere i organisationen kan oprette arbejdsområder for skabelonapps. Styr, hvilke brugere der kan publicere skabelonapps eller distribuere dem til klienter uden for organisationen ved hjælp af [AppSource](https://appsource.microsoft.com) eller en anden distributionsmetode.

![Power BI-administrationsportal, indstillingen Opret skabelonprogrammer](media/service-admin-portal/power-bi-admin-portal-template-app-settings.png)

### <a name="install-template-apps-listed-on-appsource"></a>Installér skabelonapps, der er angivet på AppSource

Brugere i organisationen kan **kun** downloade og installere skabelonapps fra [AppSource](https://appsource.microsoft.com). Styr, hvilke specifikke brugere eller sikkerhedsgrupper der kan installere skabelonapps fra AppSource.

![Power BI-administrationsportal, indstillingen Installér skabelonapps](media/service-admin-portal/power-bi-admin-portal-template-app-settings-installer-appsource.png)

### <a name="install-template-apps-not-listed-on-appsource"></a>Installér skabelonapps, der ikke er angivet på AppSource

Styr, hvilke brugere i organisationen der kan downloade og installere skabelonapps, som **ikke er anført på [AppSource](https://appsource.microsoft.com)** .

![Power BI-administrationsportal, indstillingen Installér skabelonapps](media/service-admin-portal/power-bi-admin-portal-template-app-settings-installer-nonappsource.png)

## <a name="capacity-settings"></a>Kapacitetsindstillinger

### <a name="power-bi-premium"></a>Power BI Premium

Under fanen **Power BI Premium** kan du administrere en hvilken som helst Power BI Premium-kapacitet (EM eller P SKU), der er købt til din organisation. Alle brugere i organisationen får vist fanen **Power BI Premium**, men de kan kun se indholdet i den, hvis de enten er tildelt rollen som *Kapacitetsadministrator* eller er brugere med tildelingstilladelser. Hvis en bruger ikke har nogen tilladelser, vises følgende meddelelse.

![Ingen adgang til Premium-indstillinger](media/service-admin-portal/premium-settings-no-access.png)

### <a name="power-bi-embedded"></a>Power BI Embedded

Under fanen **Power BI Embedded** kan du se dine Power BI Embedded-kapaciteter (A SKU), som du har købt til din kunde. Da du kun kan købe A SKU'er fra Azure, kan du [administrere integrerede kapaciteter i Azure](../developer/embedded/azure-pbie-create-capacity.md) fra **Azure-portalen**.

Du kan finde flere oplysninger om, hvordan du administrerer indstillinger for Power BI Embedded (A SKU), under [Hvad er Power BI Embedded](../developer/embedded/azure-pbie-what-is-power-bi-embedded.md).

## <a name="embed-codes"></a>Integrer koder

Som administrator kan du få vist de integreringskoder, der er genereret for din lejer med henblik på offentlig deling af rapporter. Du kan også tilbagekalde eller slette koder. [Få mere at vide](../collaborate-share/service-publish-to-web.md)

![Integrer koder i Power BI-administrationsportalen](media/service-admin-portal/embed-codes.png)

 ## <a name=""></a><a name="organizational-visuals">Visualiseringer til virksomheder</a> 

Fanen **Organisationens visuals** giver dig mulighed for at installere og administrere Power BI-visuals i din organisation. Med visuals til organisationer kan du nemt installere privatejede visuals i din organisation, som forfattere af rapporter efterfølgende kan finde og importere i deres rapporter fra Power BI Desktop. [Få mere at vide](../developer/visuals/power-bi-custom-visuals-organization.md)

> [!WARNING]
> En brugerdefineret visual kan indeholde kode, der udgør en risiko for sikkerheden eller personlige oplysninger. Sørg for at have tillid til forfatteren af og kilden til den brugerdefinerede visual, før du installerer den i organisationens lager.

Følgende billede viser alle de Power BI-visuals, der i øjeblikket er installeret i en organisations lager.

![Organisationens administratorvisualisering](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>Tilføj en ny brugerdefineret visualisering

Hvis du vil føje en ny brugerdefineret visual til listen, skal du følge disse trin. 

1. Vælg **Tilføj en brugerdefineret visual** i ruden til højre.

    ![Power BI-visuals-formular](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

1. Udfyld formularen **Tilføj brugerdefineret visual**:

    * **Vælg en .pbiviz-fil** (påkrævet): Vælg den brugerdefinerede visualiseringsfil, som du vil uploade. Det er kun Power BI-visuals med versioneret API, der understøttes. Læs her, hvad det betyder.

    Før du uploader en brugerdefineret visualisering, bør du gennemgå den for at sikre, at sikkerhed og beskyttelse af personlige oplysninger stemmer overens med din virksomheds standarder.

    * **Navngiv din brugerdefinerede visual** (påkrævet): Angiv en kort titel på din visual, så brugerne af Power BI Desktop nemt kan forstå, hvad de kan bruge den til

    * **Ikon**: Den ikonfil, der vises på brugergrænsefladen i Power BI Desktop.

    * **Beskrivelse**: En kort beskrivelse af din visual, som giver brugeren mere kontekst og flere oplysninger

1. Vælg **Tilføj** for at starte anmodningen om upload. Hvis uploadet lykkes, kan du se det nye element på listen. Hvis uploadet mislykkes, får du vist en passende fejlmeddelelse

### <a name="delete-a-custom-visual-from-the-list"></a>Slet en brugerdefineret visualisering fra listen

Hvis du vil slette en visual permanent, skal du vælge ikonet Papirkurv for den pågældende visual i lageret.

> [!IMPORTANT]
> Du kan ikke fortryde en sletning. Når visualiseringen er slettet, holder den øjeblikkeligt op med at blive gengivet i eksisterende rapporter. Selv om du uploader den samme visual igen, erstatter den ikke den forrige, der blev slettet. Brugerne kan dog importere den nye visual igen og erstatte det eksemplar, de har i deres rapporter.

### <a name="disable-a-custom-visual-in-the-list"></a>Deaktiver en brugerdefineret visualisering på listen

Hvis du vil deaktivere visualiseringen fra organisationens lager, skal du vælge tandhjulsikonet. I sektionen **Adgang** skal du deaktivere den brugerdefinerede visualisering.

Når du har deaktiveret visualiseringen, gengives visualiseringen ikke i eksisterende rapporter, og fejlmeddelelsen nedenfor vises.

*Denne brugerdefinerede visualisering er ikke længere tilgængelig. Kontakt administratoren for at få flere oplysninger.*

Visualiseringer, der er angivet bogmærker for, virker dog stadig.

Efter en opdatering eller ændring af administrator skal brugerne af Power BI Desktop genstarte programmet eller opdatere browseren i Power BI-tjenesten for at se opdateringerne.

### <a name="update-a-visual"></a>Opdater en visual

Hvis du vil opdatere en visual fra organisationens lager, skal du vælge tandhjulsikonet. Gennemse og upload en ny version af den pågældende visual.

Sørg for, at id'et for visualiseringen ikke ændres. Den nye fil erstatter den forrige fil for alle rapporter i hele organisationen. Hvis der er risiko for, at den nye version af visualiseringen vil bryde brugen eller datastrukturen af den forrige version af visualiseringen, skal du ikke erstatte den forrige version. Du skal i stedet oprette en ny post for den nye version af visualiseringen. Føj f.eks. et nyt versionsnummer (version X.X) til titlen af den nye angivne visualisering. På den måde bliver det tydeligt, at det er den samme visualisering blot med et opdateret versionsnummer, så funktionaliteten i eksisterende rapporter ikke brydes. Sørg igen for, at id'et for visualiseringen ikke ændres. Næste gang brugerne derefter tilgår virksomhedens lager fra Power BI Desktop, kan de importere den nye version, og de bliver spurgt, om de vil erstatte den aktuelle version, de har i rapporten.

Du kan finde flere oplysninger under [Ofte stillede spørgsmål om Power BI-visuals til organisationer](../developer/visuals/power-bi-custom-visuals-faq.md#organizational-power-bi-visuals)

## <a name=""></a><a name="dataflowStorage">Dataflowlager (eksempelvisning)</a>

Som standard gemmes data, der bruges med Power BI, i et internt lager, der leveres af Power BI. Med integrationen af dataflow og Azure Data Lake Storage Gen2 (ADLS Gen2) kan du gemme dine dataflow på din organisations Azure Data Lake Storage Gen2-konto. Du kan finde flere oplysninger under [Integration af dataflow og Azure Data Lake (prøveversion)](../transform-model/service-dataflows-azure-data-lake-integration.md).

## <a name="workspaces"></a>Arbejdsområder

Som administrator kan du få vist de arbejdsområder, der findes i din lejer. Du kan sortere og filtrere listen over arbejdsområder og få vist detaljerne for hvert arbejdsområde. Kolonnerne i tabellen svarer til de egenskaber, der returneres af [REST API'erne til Power BI Administration](/rest/api/power-bi/admin) for arbejdsområder. Personlige arbejdsområder er af typen **Personlig gruppe**, klassiske arbejdsområder er af typen **Gruppe**, og arbejdsområder med den nye arbejdsområdeoplevelse er af typen **Arbejdsområde**. Du kan finde flere oplysninger under [Organiser arbejde i de nye arbejdsområder](../collaborate-share/service-new-workspaces.md).

Administratorer kan også administrere og genoprette arbejdsområder ved hjælp af enten Power BI Administration eller PowerShell-cmdlet'er. 

![Liste over arbejdsområder](media/service-admin-portal/workspaces-list.png)

På fanen **Arbejdsområder** kan du se *tilstanden* for hvert arbejdsområde. I tabellen nedenfor kan du se flere oplysninger om betydningen af disse tilstande.

|Stat  |Beskrivelse  |
|---------|---------|
| Aktiv | Et normalt arbejdsområde. Det angiver ikke noget om brug, eller hvad der er indeni, kun at selve arbejdsområdet er "normalt". |
| Uafhængig | Et arbejdsområde uden en administratorbruger. |
| Slettet | Et slettet arbejdsområde. Vi bevarer tilstrækkeligt mange metadata i op til 90 dage til at kunne gendanne arbejdsområdet, hvis det er nødvendigt. |
| Fjerner | Et arbejdsområde, der er ved at blive slettet, men endnu ikke forsvundet. Brugerne kan slette deres egne arbejdsområder og placere ting i Fjerner og til sidst Slettet. |

## <a name="custom-branding"></a>Brugerdefineret branding

Som administrator kan du tilpasse udseendet af Power BI for hele organisationen. Der er i øjeblikket tre primære muligheder:

![Brugerdefinerede brandingmuligheder](media/service-admin-portal/power-bi-custom-branding.png)

* **Upload logo**: Du opnår de bedste resultater ved at uploade et logo, der er gemt som en .png-fil på 10 KB eller mindre og mindst 200 x 30 pixel.

* **Upload forsidebillede**: Du opnår de bedste resultater ved at uploade et forsidebillede, der er gemt som en .jpg- eller .png-fil på 1 MB eller mindre og mindst 1920 x 160 pixel.

* **Vælg temafarve**: Du kan vælge dit tema på baggrund af en hex #, RGB, værdi eller fra den angivne palet.


Du kan finde flere oplysninger i [Brugerdefineret branding til din organisation](https://aka.ms/orgBranding).

![Liste over arbejdsområder](media/service-admin-portal/workspaces-list.png)

## <a name="manage-featured-content"></a>Administrer fremhævet indhold

Som lejeradministrator kan du administrere alle de rapporter, dashboards og apps, der er blevet opgraderet til afsnittet Udvalgte i Power BI Start i hele organisationen.

- Vælg **Fremhævet indhold** i administrationsportalen.

Her kan du se en oversigt over, hvem der har udvalgt indholdet, hvornår det blev udvalgt, og alle indholdets relevante metadata. Hvis noget ser mistænkeligt ud, eller hvis du vil rydde op i afsnittet Udvalgte, kan du slette det udvalgte indhold efter behov.

Se [Fremhævet indhold](#featured-content) i denne artikel for at få oplysninger om, hvordan du aktiverer udvalgt indhold.

## <a name="next-steps"></a>Næste trin

[Administrer Power BI i din organisation](service-admin-administering-power-bi-in-your-organization.md)  
[Beskrivelse af rollen som Power BI-administrator](service-admin-role.md)  
[Overvågning af Power BI i din virksomhed](service-admin-auditing.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
