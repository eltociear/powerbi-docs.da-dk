---
title: Power BI-administrationsportal
description: Administrationsportalen giver adgang til lejeradministration af Power BI i virksomheden. Den indeholder elementer som f.eks. forbrugsdata, adgang til Office 365 Administration og indstillinger.
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/27/2017
ms.author: asaxton
ms.openlocfilehash: d831363d6afa88aa94d78776f59f81ba8ba96299
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/06/2017
---
# <a name="power-bi-admin-portal"></a>Power BI-administrationsportal

Administrationsportalen giver adgang til lejeradministration af Power BI i virksomheden. Den indeholder elementer som f.eks. forbrugsdata, adgang til Office 365 Administration og indstillinger.

Lejeradministration af Power BI til din virksomhed foregår gennem Power BI-administrationsportalen. Administrationsportalen kan tilgås af alle brugere, som er globale administratorer i Office 365, eller som er blevet tildelt Power BI-tjenesteadministratorrollen. Du kan finde flere oplysninger om Power BI-tjenesteadministratorrollen under [Beskrivelse af rollen som Power BI-administrator](service-admin-role.md).

Alle brugere får vist **Administrationsportalen** under tandhjulsikonet. Brugere der ikke er administratorer, kan kun se afsnittet **Premium-indstillinger**, og de kan kun se de kapaciteter, som de har rettighederne til at administrere.

## <a name="how-to-get-to-the-admin-portal"></a>Sådan finder du vej til administrationsportalen

Din konto skal være markeret som en **Global administrator** i Office 365 eller Azure Active Directory, eller skal være tildelt Power BI-tjenesteadministratorrollen for at få adgang til Power BI-administrationsportalen. Du kan finde flere oplysninger om Power BI-tjenesteadministratorrollen under [Beskrivelse af rollen som Power BI-administrator](service-admin-role.md). Benyt følgende fremgangsmåde for at tilgå Power BI-administrationsportalen.

1. Vælg tandhjulet Indstillinger i øverste højre hjørne af Power BI-tjenesten.
2. Vælg **Administrationsportalen**.

![](media/service-admin-portal/powerbi-admin-settings.png)

I portalen er der fem faner. Disse er beskrevet nedenfor.

* [Forbrugsdata](#usage-metrics)
* [Brugere](#users)
* [Overvågningslogge](#audit-logs)
* [Lejerindstillinger](#tenant-settings)
* [Premium-indstillinger](#premium-settings)
* [Integrer koder](#embed-codes)

![](media/service-admin-portal/powerbi-admin-landing-page.png)

## <a name="usage-metrics"></a>Forbrugsdata
Den første fane i administrationsportalen er **Forbrugsdata**. Rapporten over forbrugsdataene giver dig mulighed for at overvåge forbruget i Power BI i virksomheden. Den giver dig også mulighed for at se, hvilke brugere og grupper, der er mest aktive i Power BI i virksomheden.

> [!NOTE]
> Første gang du tilgår dashboard'et, eller når du besøger det igen efter en lang periode uden at åbne dashboard'et, så får du sandsynligvis vist indlæsningsskærmen, mens vi indlæser dashboard'et.

Mens dashboard'et indlæses, så får du vist to afsnit med felter. Det første afsnit indeholder forbrugsdata for individuelle brugere, og det andet afsnit har lignende oplysninger for grupper i din virksomhed.

Nedenfor er en oversigt over indholdet i hvert felt:

* Specifik optælling af alle dashboards, rapporter og datasæt i brugerarbejdsområdet
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* Mest brugte dashboard efter antallet af brugere, der har adgang til det. Hvis du f.eks. har et dashboard, som du har delt med tre brugere, og du også har føjet det til en indholdspakke med to forskellige brugere tilsluttet, så er antallet 6 (1 + 3 + 2)
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* Det mest populære indhold, som brugere har oprettet forbindelse til. Dette vil være alt vilkårligt indhold, som brugere kan tilgå gennem Hent data-processen, dvs. Saas-indholdspakker, organisatoriske indholdspakker, filer eller databaser.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* En visning af dine vigtigste brugere baseret på, hvor mange dashboards de har, både dashboards de selv har oprettet, og dashboards der er delt med dem.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* En visning af dine vigtigste brugere baseret på, hvor mange rapporter de har
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

Det andet afsnit viser den samme type oplysninger, men baseret på grupper. Her kan du se, hvilke grupper i virksomheden, der er mest aktive og hvilke slags oplysninger, de bruger.

Med disse oplysninger kan du få reelt indsigt i, hvordan personer bruger Power BI på tværs af din virksomhed, og du kan holde styr på, hvilke af de pågældende brugere og grupper, der er meget aktive i din virksomhed.

## <a name="users"></a>Brugere

Den anden fane i administrationsportalen er **Administrer brugere**. Brugeradministrationen i Power BI håndteres i Office 365 Administration, så dette afsnit giver dig hurtig adgang til området for administration af brugere, administratorer og grupper i Office 365.

![](media/service-admin-portal/powerbi-admin-manage-users.png)

Når du klikker på **Gå til O365 Administration**, så føres du direkte til Office 365 Administration-landingssiden til administration af brugerne af din lejer.

![](media/service-admin-portal/powerbi-admin-o365-admin-center.png)

## <a name="audit-logs"></a>Overvågningslogge

Den tredje fane i administrationsportalen er **Overvågningslogge**. Loggene er placeret inden for Office 365 Security & Compliance Center. Dette afsnit giver dig hurtig adgang til dette område inden for Office 365. 

Du kan finde flere oplysninger om overvågningslogge under [Overvågning af Power BI i din virksomhed](service-admin-auditing.md)

## <a name="tenant-settings"></a>Lejerindstillinger

Den tredje fane i administrationsportalen er **Lejerindstillinger**. Lejerindstillingerne giver dig yderligere kontrol over, hvilke funktioner der gøres tilgængelige i din virksomhed. Hvis du har bekymringer omkring følsomme data, kan det være, at nogle af vores funktioner ikke er passende for din virksomhed, eller du vil måske kun have, at en given funktion er tilgængelig for en bestemt gruppe. Hvis det er tilfældet, kan du slå funktionen fra i din lejer.

![](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> Det kan tage op til ti minutter for indstillingen at træde i kraft for alle i din lejer.

Indstillinger kan have tre tilstande, som er baseret på de indstillinger, du har angivet.

### <a name="disabled-for-the-entire-organization"></a>Deaktiveret for hele virksomheden

Du kan deaktivere en funktion, så brugere ikke kan tilgå den.

![](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

### <a name="enabled-for-the-entire-organization"></a>Aktiveret for hele virksomheden

Du kan aktivere en funktion for hele virksomheden, hvorved alle brugere har adgang til den pågældende funktion.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

### <a name="enabled-for-a-subset-of-the-organization"></a>Aktiveret for et udsnit af virksomheden

Du kan også aktivere en funktion delvist for din virksomhed. Dette kan foregå på et par forskellige måder. Du kan aktivere den for hele din virksomhed med undtagelse af en bestemt gruppe brugere.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

Du kan også aktivere funktionen udelukkende for en bestemt gruppe af brugere og også deaktivere den for en gruppe af brugere. Dette vil sørge for, at visse brugere ikke har adgang til funktionen, selvom de er medlemmer af den tilladte gruppe.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

## <a name="export-and-sharing-settings"></a>Eksport- og delingsindstillinger

### <a name="share-content-to-external-users"></a>Deling af indhold med eksterne brugere

Brugere i virksomheden kan dele dashboards med brugere uden for virksomheden.

![](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Publicer på internettet

Brugere i virksomheden kan publicere rapporter på internettet. [Få mere at vide](service-publish-to-web.md)

![](media/service-admin-portal/powerbi-admin-publish-to-web.png)

Brugere får vist andre indstillinger i brugergrænsefladen, baseret på hvad indstillingen Publicer på internettet er.

|Udvalgt |Aktiveret for hele organisationen |Deaktiveret for hele organisationen |Specifikke sikkerhedsgrupper   |
|---------|---------|---------|---------|
|**Publicer på internettet** under rapportens menu **Filer**.|Aktiveret for alle|Ikke synligt for alle|Kun synligt for godkendte brugere eller grupper.|
|**Håndter integreringskoder** under **Indstillinger**|Aktiveret for alle|Aktiveret for alle|Aktiveret for alle<br><br>Indstillingen * **Slet** er kun synlig for godkendte brugere eller grupper.<br>* **Hent koder** er aktiveret for alle.|
|**Integrer koder** i administrationsportalen|Status afspejler et af følgende:<br>* Aktiv<br>* Ikke understøttet<br>* Blokeret|Status vises som **Deaktiveret**|Status afspejler et af følgende:<br>* Aktiv<br>* Ikke understøttet<br>* Blokeret<br><br>Hvis en bruger ikke er godkendt baseret på lejeren indstilling, vises status som **krænket**.|
|Eksisterende publicerede rapporter|Alle aktiveret|Alle deaktiveret|Rapporter fortsætter med at gengive for alle.|

### <a name="export-data"></a>Eksport af data

Brugere i virksomheden kan eksportere data fra et felt eller visualisering. [Få mere at vide](power-bi-visualization-export-data.md)

![](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> Deaktivering af **Eksport af data** forebygger også mod, at brugere kan bruge funktionen **Analysér i Excel** samt bruge Power BI-tjenestens direkte forbindelse.

### <a name="export-reports-as-powerpoint-presentations"></a>Eksport af rapporter som PowerPoint-præsentationer

Brugere i virksomheden kan eksportere Power BI-rapporter som PowerPoint-filer. [Få mere at vide](service-publish-to-powerpoint.md)

![](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Udskriv dashboards og rapporter

Brugere i virksomheden kan udskrive dashboards og rapporter. [Få mere at vide](service-print.md)

![](media/service-admin-portal/powerbi-admin-print-dashboard.png)

![](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-settings"></a>Indholdspakkeindstillinger

### <a name="publish-content-packs-to-the-entire-organization"></a>Udgiv indholdspakker til hele virksomheden

Brugere i virksomheden kan udgive indholdspakker til hele virksomheden.

![](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs"></a>Opret organisationpakker med skabelonindhold

Brugere i virksomheden kan oprette pakker med skabelonindhold, der bruger datasæt bygget på én datakilde i Power BI Desktop.

## <a name="integration-settings"></a>Integrationsindstillinger

### <a name="ask-questions-about-data-using-cortana"></a>Stil spørgsmål til data ved hjælp af Cortana
Brugere i virksomheden kan stille spørgsmål til deres data ved hjælp af Cortana.

> [!NOTE]
> Denne indstilling gælder for hele virksomheden og kan ikke begrænses til bestemte grupper.

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Brug Analysér i Excel med datasæt i det lokale miljø
Brugere i virksomheden kan bruge Excel til at se og interagere med Power BI-datasæt i det lokale miljø. [Få mere at vide](service-analyze-in-excel.md)

> [!NOTE]
> Hvis du deaktiverer **Eksportér data**, så vil det også forhindre brugerne i at bruge funktionen **Analysér i Excel**.

### <a name="user-arcgis-maps-for-power-bi-preview"></a>ArcGIS Maps for Power BI til brugere (eksempel)

Brugere i virksomheden kan bruge ArcGIS Maps for Power BI (prøveversion)-visualisering leveret af Esri. [Få mere at vide](power-bi-visualization-arcgis.md)

## <a name="r-visuals-settings"></a>R visuals – indstillinger

### <a name="interact-with-an-dshare-r-visuals"></a>Interager med en dshare R visuals

Brugere i virksomheden kan interagere med og dele visuelle elementer oprettet med R-scripts. [Få mere at vide](service-r-visuals.md)

> [!NOTE]
> Denne indstilling gælder for hele virksomheden og kan ikke begrænses til bestemte grupper.

## <a name="audit-settings"></a>Indstillinger for overvågning

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>Opret overvågningslogge for intern aktivitetsovervågning og overholdelse

Brugere i virksomheden kan overvåge handlinger, der udføres i Power BI af andre brugere i virksomheden. [Få mere at vide](service-admin-auditing.md)

Denne indstilling skal være aktiveret, for at overvågningslogposter bliver registreret.

> [!NOTE]
> Denne indstilling gælder for hele virksomheden og kan ikke begrænses til bestemte grupper.

## <a name="dashboard-settings"></a>Indstillinger for dashboard

### <a name="data-classification-for-dashboards"></a>Dataklassificering til dashboards

Brugere i virksomheden kan markere dashboards med klassificeringsangivelser, der angiver sikkerhedsniveauer for dashboards. [Få mere at vide](service-data-classification.md)

> [!NOTE]
> Denne indstilling gælder for hele virksomheden og kan ikke begrænses til bestemte grupper.

## <a name="developer-settings"></a>Indstillinger for udviklere

### <a name="embed-content-in-apps"></a>Integrer indhold i apps

Brugere i virksomheden kan integrere Power BI-dashboards og rapporter i Software as a Service (SaaS)-programmer. Hvis denne indstilling deaktiveres, kan brugere ikke bruge REST API'er til at integrere Power BI-indhold i deres program.

## <a name="premium-settings"></a>Premium-indstillinger

Fanen Premium-indstillinger giver dig mulighed for at administrere en given Power BI Premium-kapacitet, der er blevet købt til din virksomhed. Alle brugere i virksomheden får vist fanen Premium-indstillinger, men kan kun se indholdet i den, hvis de er tildelt rollen som enten **Kapacitetsadministrator** eller er bruger med tildelingstilladelser. Hvis en bruger ikke har nogen tilladelser, vil vedkommende se den følgende meddelelse.

![](media/service-admin-portal/premium-settings-no-access.png "Ingen adgang til Premium-indstillinger")

For at få flere oplysninger om, hvordan du administrerer Premium-indstillinger, skal du se [Administrer Power BI Premium](service-admin-premium-manage.md).

## <a name="embed-codes"></a>Integrer koder

![Integrer koder i Power BI-administrationsportalen](media/service-admin-portal/embed-codes.png)

Som administrator kan du få vist integreringskoder, der er genereret for din lejer. Du har handlingerne til visning af rapporten og sletning af integreringskoden for at tilbagekalde den.

## <a name="next-steps"></a>Næste trin

[Beskrivelse af rollen som Power BI-administrator](service-admin-role.md)  
[Overvågning af Power BI i din virksomhed](service-admin-auditing.md)  
[Administrer Power BI Premium](service-admin-premium-manage.md)  
[Administrering af Power BI i din virksomhed](service-admin-administering-power-bi-in-your-organization.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)