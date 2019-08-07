---
title: Power BI-administrationsportal
description: Administrationsportalen giver adgang til lejeradministration af Power BI i virksomheden. Den indeholder elementer såsom metrikværdier, adgang til Microsoft 365 Administration og indstillinger.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 07/25/2019
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 6a1ce47d7af41df51b7c439240f3e9db0dd28397
ms.sourcegitcommit: d74aca333595beaede0d71ba13a88945ef540e44
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/03/2019
ms.locfileid: "68757728"
---
# <a name="administering-power-bi-in-the-admin-portal"></a>Administrer Power BI på administrationsportalen

På administrationsportalen kan du administrere en Power BI-*lejer* for din organisation. Portalen indeholder elementer såsom metrikværdier, adgang til Microsoft 365 Administration og indstillinger.

Hele administrationsportalen kan tilgås af alle brugere, som er globale administratorer i Office 365, eller som er blevet tildelt rollen Power BI-tjenesteadministrator. Hvis du ikke har en af disse roller, kan du kun se **Kapacitetsindstillinger** på portalen. Du kan finde flere oplysninger om Power BI-tjenesteadministratorrollen under [Beskrivelse af rollen som Power BI-administrator](service-admin-role.md).

## <a name="how-to-get-to-the-admin-portal"></a>Sådan finder du vej til administrationsportalen

Din konto skal være markeret som en **Global administrator** i Office 365 eller Azure Active Directory, eller skal være tildelt Power BI-tjenesteadministratorrollen for at få adgang til Power BI-administrationsportalen. Du kan finde flere oplysninger om Power BI-tjenesteadministratorrollen under [Beskrivelse af rollen som Power BI-administrator](service-admin-role.md). Benyt følgende fremgangsmåde for at tilgå Power BI-administrationsportalen.

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

## <a name="usage-metrics"></a>Forbrugsmålepunkter

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

Rapporter med forbrugsdata er en funktion, som Power BI- eller Office 365-administratoren kan slå til eller fra. Administratorer har detaljeret kontrol over, hvilke brugere der har adgang til forbrugsdata. Det er slået **Til** som standard for alle brugere i organisationen.

Administratorer kan også bestemme, om oprettere af indhold kan se brugerspecifikke data i forbrugsdata. 

Få mere at vide om selve rapporterne under [Overvåg forbrugsdata for dashboards og rapporter](service-usage-metrics.md).

### <a name="usage-metrics-for-content-creators"></a>Forbrugsdata for oprettere af indhold

1. På administrationsportalen skal du vælge **Lejerindstillinger** > **Forbrugsdata for oprettere af indhold**.

    ![Forbrugsdata i lejerindstillingerne på administrationsportalen](media/service-admin-portal/power-bi-admin-usage-metrics.png)

1. Aktivér (eller deaktiver) forbrugsdata > **Anvend**.

    ![Forbrugsdata er aktiveret](media/service-usage-metrics/power-bi-tenant-settings-updated.png)


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

Det er også muligt at angive en URL-adresse for at dirigere brugere til en brugerdefineret løsning for licensanmodninger. Denne parameter tilpasser destinations-URL-adressen for knappen Opgrader konto, som en bruger uden en Power BI Pro-licens kan finde i dialogboksen Opdater til Power BI Pro og på siden Administrer personligt lager.

### <a name="receive-email-notifications-for-service-outages-or-incidents"></a>Modtag mails ved tjenesteafbrydelser eller -hændelser

Mailaktiverede sikkerhedsgrupper modtager mails, hvis lejeren påvirkes af en tjenesteafbrydelse eller -hændelse. Få mere at vide om [Meddelelser om tjenesteafbrydelser](service-interruption-notifications.md).

## <a name="workspace-settings"></a>Indstillinger for arbejdsområde

### <a name="create-workspaces"></a>Opret arbejdsområder

Administratorer bruger indstillingen **Opret arbejdsområder** til at angive, hvilke brugere i organisationen der kan oprette apparbejdsområder til at samarbejde om dashboards, rapporter og andet indhold. Få mere at vide om [apparbejdsområder](service-create-the-new-workspaces.md).

Administrationsportalen indeholder en anden sektion med indstillinger for arbejdsområderne i din lejer. I denne sektion kan du sortere og filtrere listen over arbejdsområder og få vist detaljerne for hvert arbejdsområde. Se [Arbejdsområder](#workspaces) for at få flere oplysninger.

I administrationsportalen kan du også styre, hvilke brugere der har tilladelse til at distribuere apps til organisationen. Se [Publicer indholdspakker og apps til hele organisationen](#publish-content-packs-and-apps-to-the-entire-organization) i denne artikel for at få flere oplysninger.

## <a name="export-and-sharing-settings"></a>Eksport- og delingsindstillinger

### <a name="share-content-with-external-users"></a>Del indhold med eksterne brugere

Brugere i organisationen kan dele dashboards med brugere uden for organisationen. [Få mere at vide](service-share-dashboards.md#share-a-dashboard-or-report-with-people-outside-your-organization)

![Indstilling for eksterne brugere](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

På følgende billede ses den meddelelse, som vises, når du deler med en ekstern bruger.

![Deling med ekstern bruger](media/service-admin-portal/powerbi-admin-sharing-external.png)  

### <a name="publish-to-web"></a>Publicer på internettet

Brugere i virksomheden kan publicere rapporter på internettet. [Få mere at vide](service-publish-to-web.md)

På følgende billede ses menuen **Filer** for en rapport, når indstillingen **Publicer på internettet** er aktiveret.

![Indstillingen Publicer på internettet](media/service-admin-portal/powerbi-admin-publish-to-web.png)

Brugere kan se forskellige indstillinger på brugergrænsefladen afhængigt af indstillingen **Publicer på internettet**.

|Udvalgt |Aktiveret for hele organisationen |Deaktiveret for hele organisationen |Specifikke sikkerhedsgrupper   |
|---------|---------|---------|---------|
|**Publicer på internettet** under rapportens menu **Filer**.|Aktiveret for alle|Ikke synligt for alle|Kun synligt for godkendte brugere eller grupper.|
|**Håndter integreringskoder** under **Indstillinger**|Aktiveret for alle|Aktiveret for alle|Aktiveret for alle<br><br>Indstillingen * **Slet** er kun synlig for godkendte brugere eller grupper.<br>* **Hent koder** er aktiveret for alle.|
|**Integrer koder** i administrationsportalen|Status afspejler et af følgende:<br>* Aktiv<br>* Ikke understøttet<br>* Blokeret|Status viser **Deaktiveret**|Status afspejler et af følgende:<br>* Aktiv<br>* Ikke understøttet<br>* Blokeret<br><br>Hvis en bruger ikke er godkendt på grund af indstillingen af lejeren, vises status som **krænket**.|
|Eksisterende publicerede rapporter|Alle aktiveret|Alle deaktiveret|Rapporter fortsætter med at gengive for alle.|

### <a name="export-data"></a>Eksportér data

Brugere i virksomheden kan eksportere data fra et felt eller visualisering. [Få mere at vide](visuals/power-bi-visualization-export-data.md)

På følgende billede ses indstillingen for at eksportere data fra et felt.

![Eksportér data fra et felt](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> Hvis **Eksportér data** deaktiveres, kan brugere ikke anvende funktionen **Analysér i Excel** og heller ikke bruge Power BI-tjenestens direkte forbindelse.

### <a name="export-reports-as-powerpoint-presentations-or-pdf-documents"></a>Eksportér rapporter som PowerPoint-præsentationer eller PDF-dokumenter

Brugere i organisationen kan eksportere Power BI-rapporter som PowerPoint-filer eller PDF-dokumenter. [Få mere at vide](consumer/end-user-powerpoint.md)

På følgende billede ses menuen **Filer** for en rapport, når indstillingen **Eksportér rapporter som PowerPoint-præsentationer eller PDF-dokumenter** er aktiveret.

![Eksportér rapporter som PowerPoint-præsentationer](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Udskriv dashboards og rapporter

Brugere i virksomheden kan udskrive dashboards og rapporter. [Få mere at vide](consumer/end-user-print.md)

På følgende billede ses indstillingen for at udskrive et dashboard.

![Udskriv dashboard](media/service-admin-portal/powerbi-admin-print-dashboard.png)

På følgende billede ses menuen **Filer** for en rapport, når indstillingen **Udskriv dashboards og rapporter** er aktiveret.

![Udskriv rapport](media/service-admin-portal/powerbi-admin-print-report.png)

### <a name="allow-external-guest-users-to-edit-and-manage-content-in-the-organization"></a>Tillad, at eksterne brugere kan redigere og administrere indhold i organisationen
Azure B2B-brugere kan redigere og administrere indhold i organisationen [Få mere at vide](service-admin-azure-ad-b2b.md)

På følgende billede vises indstillingen Tillad, at eksterne brugere kan redigere og administrere indhold i organisationen.

![Tillad, at eksterne brugere kan redigere og administrere indhold i organisationen](media/service-admin-portal/powerbi-admin-tenant-settings-b2b-guest-edit-manage.png)

### <a name="email-subscriptions"></a>Mailabonnementer
Brugere i organisationen kan oprette mailabonnementer. Få mere at vide om [abonnementer](service-report-subscribe.md).

![Aktivér mailabonnementer](media/service-admin-portal/power-bi-manage-email-subscriptions.png)

## <a name="content-pack-and-app-settings"></a>Indholdspakke og appindstillinger

### <a name="publish-content-packs-and-apps-to-the-entire-organization"></a>Publicer indholdspakker og apps til hele organisationen

Administratorer bruger denne indstilling til at bestemme, hvilke brugere i organisationen der kan publicere indholdspakker og apps til hele organisationen frem for kun til specifikke grupper. Få mere at vide om [publicering af apps](service-create-distribute-apps.md).

På følgende billede vises indstillingen **Hele min organisation**, når du opretter en indholdspakke.

![Publicer indholdspakke til organisation](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-apps-and-organizational-content-packs"></a>Opret skabelonbaserede apps og indholdspakker for organisationen

Brugere i virksomheden kan oprette skabelonbaserede apps og indholdspakker for organisationen, der bruger datasæt baseret på én datakilde i Power BI Desktop. Få mere at vide om [skabelonapps](template-content-pack-authoring.md).

### <a name="push-apps-to-end-users"></a>Push apps til slutbrugere

Rapportoprettere kan dele apps direkte med slutbrugere uden at kræve installation fra [AppSource](https://appsource.microsoft.com). Få mere at vide om [automatisk installation af apps til slutbrugere](service-create-distribute-apps.md#automatically-install-apps-for-end-users).

## <a name="integration-settings"></a>Integrationsindstillinger

### <a name="ask-questions-about-data-using-cortana"></a>Stil spørgsmål til data ved hjælp af Cortana

Brugere i virksomheden kan stille spørgsmål til deres data ved hjælp af Cortana. [Få mere at vide](service-cortana-enable.md)

> [!NOTE]
> Denne indstilling gælder for hele organisationen og kan ikke begrænses til bestemte grupper.

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Brug Analysér i Excel med datasæt i det lokale miljø

Brugere i virksomheden kan bruge Excel til at se og interagere med Power BI-datasæt i det lokale miljø. [Få mere at vide](service-analyze-in-excel.md)

> [!NOTE]
> Hvis **Eksportér data** deaktiveres, kan brugere heller ikke anvende funktionen **Analysér i Excel**.

### <a name="use-arcgis-maps-for-power-bi"></a>Brug ArcGIS Maps til Power BI

Brugere i organisationen kan bruge ArcGIS Maps for Power BI-visualiseringen fra Esri. [Få mere at vide](visuals/power-bi-visualization-arcgis.md)

### <a name="use-global-search-for-power-bi-preview"></a>Brug global søgning til Power BI (prøveversion)

Brugere i organisationen kan bruge eksterne søgefunktioner, der bruger Azure Search. Brugere kan f.eks. bruge Cortana til at hente vigtige oplysninger direkte fra Power BI-dashboards og -rapporter. [Få mere at vide](service-cortana-intro.md)

## <a name="custom-visuals-settings"></a>Indstillinger for brugerdefinerede visualiseringer

### <a name="add-and-use-custom-visuals"></a>Tilføj og brug brugerdefinerede visualiseringer

Brugerne i organisationen kan interagere med og dele brugerdefinerede visualiseringer. [Få mere at vide](power-bi-custom-visuals.md)

> [!NOTE]
> Denne indstilling kan anvendes på hele organisationen, eller den kan begrænses til specifikke grupper.


Fra marts 2019 understøtter Power BI Desktop brugen af **Gruppepolitik** til at deaktivere brugen af brugerdefinerede visualiseringer på tværs af de computere, der er installeret i en organisation.

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

En værdi på 1 (decimal) aktiverer brugen af brugerdefinerede visualiseringer i Power BI (dette er standarden).

En værdi på 0 (decimal) deaktiverer brugen af brugerdefinerede visualiseringer i Power BI.

### <a name="allow-only-certified-visuals"></a>Tillad kun certificerede visualiseringer

Brugere i organisationen, som er tildelt tilladelser til at tilføje og bruge brugerdefinerede visualiseringer med indstillingen "Tilføj og brug brugerdefinerede visualiseringer", kan kun bruge [certificerede brugerdefinerede visualiseringer](https://go.microsoft.com/fwlink/?linkid=2002010) (de ikke-certificerede visualiseringer blokeres, og der vises en fejlmeddelelse, når de bruges). 


Fra marts 2019 understøtter Power BI Desktop brugen af **Gruppepolitik** til at deaktivere brugen af ikke-certificerede brugerdefinerede visualiseringer på tværs af de computere, der er installeret i en organisation.

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

En værdi på 1 (decimal) aktiverer brugen af ikke-certificerede brugerdefinerede visualiseringer i Power BI (dette er standarden).

En værdi på 0 (decimal) deaktiverer brugen af ikke-certificerede brugerdefinerede visualiseringer i Power BI (denne indstilling aktiverer kun brugen af [certificerede brugerdefinerede visualiseringer](https://go.microsoft.com/fwlink/?linkid=2002010)).

## <a name="r-visuals-settings"></a>R visuals – indstillinger

### <a name="interact-with-and-share-r-visuals"></a>Interager med og del R-visualiseringer

Brugere i virksomheden kan interagere med og dele visuelle elementer oprettet med R-scripts. [Få mere at vide](visuals/service-r-visuals.md)

> [!NOTE]
> Denne indstilling gælder for hele organisationen og kan ikke begrænses til bestemte grupper.

## <a name="audit-and-usage-settings"></a>Indstillinger for overvågning og brug

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>Opret overvågningslogge for intern aktivitetsovervågning og overholdelse

Brugere i virksomheden kan overvåge handlinger, der udføres i Power BI af andre brugere i virksomheden. [Få mere at vide](service-admin-auditing.md)

Denne indstilling skal være aktiveret, for at overvågningslogposter bliver registreret. Der kan være op til 48 timers forsinkelse, fra at du aktiverer overvågning, til at du får vist data i overvågningsloggen. Hvis du ikke får vist data med det samme, skal du tjekke overvågningsloggene senere. Der kan være en lignende forsinkelse mellem at få tilladelse til at få vist overvågningslogge og til at kunne åbne logfilerne.

> [!NOTE]
> Denne indstilling gælder for hele organisationen og kan ikke begrænses til bestemte grupper.

### <a name="usage-metrics-for-content-creators"></a>Forbrugsdata for oprettere af indhold

Brugere i organisationen kan se forbrugsdata for dashboards og rapporter, som de opretter. [Få mere at vide](service-usage-metrics.md)

### <a name="per-user-data-in-usage-metrics-for-content-creators"></a>Brugerspecifikke data i forbrugsdata for indholdsforfattere

Forbrugsdata for indholdsforfattere viser viste navne og mailadresser for de brugere, der har adgang til indhold. [Få mere at vide](service-usage-metrics.md)

Brugerspecifikke data er som standard aktiveret for forbrugsdata, og kontooplysninger om indholdsforfattere indgår i rapporten med forbrugsdata. Hvis du ikke vil indsamle disse oplysninger for alle brugere, kan du deaktivere funktionen for nærmere angivne sikkerhedsgrupper eller for en hel organisation. Kontooplysningerne for de ekskluderede brugere vises derefter i rapporten som *Ikke-navngivet*.

## <a name="dashboard-settings"></a>Indstillinger for dashboard

### <a name="data-classification-for-dashboards"></a>Dataklassificering til dashboards

Brugere i organisationen kan markere dashboards med klassificeringsangivelser, der angiver sikkerhedsniveauer for dashboards. [Få mere at vide](service-data-classification.md)

> [!NOTE]
> Denne indstilling gælder for hele organisationen og kan ikke begrænses til bestemte grupper.

## <a name="developer-settings"></a>Indstillinger for udviklere

### <a name="embed-content-in-apps"></a>Integrer indhold i apps

Brugere i virksomheden kan integrere Power BI-dashboards og rapporter i Software as a Service (SaaS)-programmer. Hvis denne indstilling deaktiveres, kan brugere ikke anvende REST API'er til at integrere Power BI-indhold i deres program. [Få mere at vide](developer/embedding.md)

### <a name="allow-service-principals-to-use-power-bi-apis"></a>Tillad, at tjenesteprincipaler bruger Power BI-API'er

Webapps, der er registreret i Azure Active Directory (Azure AD), bruger en tildelt tjenesteprincipal til at få adgang til Power BI-API'erne, uden at en bruger er logget på. Hvis du vil tillade, at en app anvender den godkendte tjenesteprincipal, skal tjenesteprincipalen være inkluderet i den tilladte sikkerhedsgruppe. [Få mere at vide](developer/embed-service-principal.md)

> [!NOTE]
> Tjenesteprincipaler nedarver tilladelserne til alle Power BI-lejerindstillinger fra deres sikkerhedsgruppe. Hvis du vil begrænse tilladelserne, skal du oprette en dedikeret sikkerhedsgruppe for tjenesteprincipaler og føje den til listen "Undtagen specifikke sikkerhedsgrupper" for de relevante aktiverede Power BI-indstillinger.

## <a name="dataflow-settings"></a>Indstillinger for dataflow

### <a name="create-and-use-dataflows"></a>Opret og brug dataflow

Brugere i organisationen kan oprette og bruge dataflow. Du kan se en oversigt over dataflow i [Selvbetjent dataforberedelse i Power BI](service-dataflows-overview.md). Hvis du vil aktivere dataflow i en Premium-kapacitet, skal du se under [Konfigurer arbejdsbelastninger](service-admin-premium-workloads.md).

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

Under fanen **Power BI Embedded** kan du se dine Power BI Embedded-kapaciteter (A SKU), som du har købt til din kunde. Da du kun kan købe A SKU'er fra Azure, kan du [administrere integrerede kapaciteter i Azure](developer/azure-pbie-create-capacity.md) fra **Azure-portalen**.

Du kan finde flere oplysninger om, hvordan du administrerer indstillinger for Power BI Embedded (A SKU), under [Hvad er Power BI Embedded](developer/azure-pbie-what-is-power-bi-embedded.md).

## <a name="embed-codes"></a>Integrer koder

Som administrator kan du få vist integreringskoder, der er genereret for din lejer. Du kan også tilbagekalde eller slette koder. [Få mere at vide](service-publish-to-web.md)

![Integrer koder i Power BI-administrationsportalen](media/service-admin-portal/embed-codes.png)

 ## <a name="organizational-visuals">Visualiseringer til virksomheder</a> 

Fanen **Organisationens visuals** giver dig mulighed for at installere og administrere brugerdefinerede visuals i din organisation. Med visuals til organisationer kan du nemt installere privatejede visuals i din organisation, som forfattere af rapporter efterfølgende kan finde og importere i deres rapporter fra Power BI Desktop. [Få mere at vide](power-bi-custom-visuals-organization.md)

> [!WARNING]
> En brugerdefineret visual kan indeholde kode, der udgør en risiko for sikkerheden eller personlige oplysninger. Sørg for at have tillid til forfatteren af og kilden til den brugerdefinerede visual, før du installerer den i organisationens lager.

Følgende billede viser alle de brugerdefinerede visuals, der i øjeblikket er installeret i en organisations lager.

![Organisationens administratorvisualisering](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>Tilføj en ny brugerdefineret visualisering

Hvis du vil føje en ny brugerdefineret visual til listen, skal du følge disse trin. 

1. Vælg **Tilføj en brugerdefineret visual** i ruden til højre.

    ![Formular til brugerdefinerede visuals](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

1. Udfyld formularen **Tilføj brugerdefineret visual**:

    * **Vælg en .pbiviz-fil** (påkrævet): Vælg den brugerdefinerede visualiseringsfil, som du vil uploade. Det er kun brugerdefinerede visualiseringer med versioneret API, der understøttes. Læs her, hvad det betyder.

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

Du kan finde flere oplysninger under [Ofte stillede spørgsmål om brugerdefinerede visualiseringer til virksomheder](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#organizational-custom-visuals)

## <a name="dataflowStorage">Dataflowlager (eksempelvisning)</a>

Som standard gemmes data, der bruges med Power BI, i et internt lager, der leveres af Power BI. Med integrationen af dataflow og Azure Data Lake Storage Gen2 (ADLS Gen2) kan du gemme dine dataflow på din organisations Azure Data Lake Storage Gen2-konto. Du kan finde flere oplysninger under [Integration af dataflow og Azure Data Lake (prøveversion)](service-dataflows-azure-data-lake-integration.md).

## <a name="workspaces"></a>Arbejdsområder

Som administrator kan du få vist de arbejdsområder, der findes i din lejer. Du kan sortere og filtrere listen over arbejdsområder og få vist detaljerne for hvert arbejdsområde. Kolonnerne i tabellen svarer til de egenskaber, der returneres af [REST API'erne til Power BI Administration](/rest/api/power-bi/admin) for arbejdsområder. Personlige arbejdsområder er af typen **Personlig gruppe**, klassiske arbejdsområder er af typen **Gruppe**, og arbejdsområder med den nye arbejdsområdeoplevelse er af typen **Arbejdsområde**. Du kan finde flere oplysninger under [Opret de nye arbejdsområder i Power BI](service-create-the-new-workspaces.md).

![Liste over arbejdsområder](media/service-admin-portal/workspaces-list.png)


## <a name="next-steps"></a>Næste trin

[Administrer Power BI i din organisation](service-admin-administering-power-bi-in-your-organization.md)  
[Beskrivelse af rollen som Power BI-administrator](service-admin-role.md)  
[Overvågning af Power BI i din virksomhed](service-admin-auditing.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
