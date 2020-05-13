---
title: Vis en rapport
description: I dette emne beskrives, at Power BI-forbrugere og slutbrugere var nødt til at åbne og få vist en Power BI-rapport.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: mihart
ms.openlocfilehash: 661277337c00f160c010351ba5f827b6e0fc2f8f
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83277611"
---
# <a name="view-a-report-in-the-power-bi-service-for-consumers"></a>Få vist en rapport i Power BI-tjenesten for *forbrugere*

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

En rapport er en eller flere sider med visualiseringer. Rapporter oprettes af Power BI-*designere* og [deles med *forbrugere* direkte](end-user-shared-with-me.md) eller som en del af en [app](end-user-apps.md). 

Der er mange forskellige måder at åbne en rapport på. Her kan du se to af dem: Åbn fra startsiden, og åbn fra et dashboard. 

<!-- add art-->


## <a name="open-a-report-from-power-bi-home"></a>Åbn en rapport fra startsiden i Power BI
Lad os åbne en rapport, der er delt med dig direkte, og derefter åbne en rapport, der blev delt som en del af en app.

   ![Hjemmeside](./media/end-user-report-open/power-bi-home-canvas.png)

### <a name="open-a-report-that-has-been-shared-with-you"></a>Åbn en rapport, der er delt med dig
Power BI-*designere* kan dele en individuel rapport direkte med dig via et link i en mail eller ved at føje den til dit Power BI-indhold automatisk. Rapporter, der deles på denne måde, vises i objektbeholderen **Delt med mig** i navigationsruden og i afsnittet **Delt med mig** på lærredet Start.

1. Åbn Power BI-tjenesten (app.powerbi.com).

2. Vælg **Start** i navigationsruden for at få vist lærredet Start.  

   ![Lærred på startsiden](./media/end-user-report-open/power-bi-select-home-new.png)
   
3. Rul ned, indtil du ser **Delt med mig**. Kig efter rapportikonet ![rapportikon](./media/end-user-report-open/power-bi-report-icon.png). På dette skærmbillede er der ét dashboard og én rapport. Rapporten kaldes for *Eksempel på salg og marketing*. 
   
   ![afsnittet Delt med mig på startsiden](./media/end-user-report-open/power-bi-shared-new.png)

4. Du skal blot vælge *rapportkortet* for at åbne rapporten.

   ![rapportside](./media/end-user-report-open/power-bi-open.png)

5. Bemærk fanerne til venstre.  Hver fane repræsenterer en *side* i rapporten. Siden med *Growth Opportunity* er i øjeblikket åben. Vælg fanen *YTD Category* for at åbne denne rapportside i stedet for. 

   ![faner på rapportside](./media/end-user-report-open/power-bi-ytd.png)

6. Læg mærke til ruden **Filtre** langs højre side. De filtre, der er anvendt på denne rapportside eller i hele rapporten, vises her.

7. Når du holder over en rapportvisualisering, vises flere ikoner og **Flere indstillinger** (...). Hvis du vil se de filtre, der er anvendt på en bestemt visualisering, skal du vælge filterikonet. Her har vi valgt filterikonet for kurvediagrammet *Total units by rolling period and region*.

   ![faner på rapportside](./media/end-user-report-open/power-bi-visual-filters.png)

6. Lige nu får vi vist hele rapportsiden. Hvis du vil ændre visningen af siden (zoom), skal du vælge rullemenuen Vis i øverste højre hjørne og vælge **Faktisk størrelse**.

   ![skift zoom](./media/end-user-report-open/power-bi-fit-new.png)

   ![tilpas til siden](./media/end-user-report-open/power-bi-actual.png)

Der er mange måder, du kan interagere med en rapport på for at finde indsigt og træffe forretningsbeslutninger.  Brug indholdsfortegnelsen til venstre for at gennemse andre artikler om Power BI-rapporter. 

### <a name="open-a-report-that-is-part-of-an-app"></a>Åbn en rapport, der er en del af en app
Hvis du har modtaget apps fra kolleger eller fra AppSource, er disse apps tilgængelige via Start og via objektbeholderen **Apps** i navigationsruden. En [app](end-user-apps.md) er en samling af dashboards og rapporter, der er bundtet til dig af en Power BI-*designer*.

### <a name="prerequisites"></a>Forudsætninger
Hvis du vil følge med, skal du downloade appen Sales & Marketing.
1. Gå til appsource.microsoft.com i din browser.
1. Søg efter "Sales and marketing" og vælg **Microsoft Sample - Sales & Marketing**.
1. Vælg **Hent det nu** > **Fortsæt** > **Installér** for at installere appen i din objektbeholder til apps. 

Du kan åbne appen fra din objektbeholder til apps eller fra startsiden.
1. Gå tilbage til Start ved at vælge **Start** i navigationsruden.

7. Rul ned, indtil du ser **Mine apps**.

   ![Hjemmeside](./media/end-user-report-open/power-bi-app.png)

8. Vælg din nye *Salg og marketing*-app for at åbne den. Afhængigt af de indstillinger der er angivet af app*designeren*, åbner appen enten et dashboard eller en rapport. Denne app åbnes i et dashboard.  


## <a name="open-a-report-from-a-dashboard"></a>Åbn en rapport fra et dashboard
Rapporter kan åbnes fra et dashboard. De fleste [dashboardfelter](end-user-tiles.md) er *fastgjort* fra rapporter. Når du vælger et felt, åbnes den rapport, der blev brugt til at oprette feltet. 

1. Vælg et felt fra dashboardet. I dette eksempel har vi valgt feltet i søjlediagrammet *Enheder i alt ÅTD...* .

    ![dashboard med valgt felt](./media/end-user-report-open/power-bi-dashboard.png)

2.  Den tilknyttede rapport åbnes. Bemærk, at vi er på siden *ÅTD-kategori*. Dette er rapportsiden, der indeholder det søjlediagram, vi har valgt på dashboardet.

    ![rapport, der er åbnet i Læsevisning](./media/end-user-report-open/power-bi-report-tabs.png)

> [!NOTE]
> Det er ikke alle felter, der fører til en rapport. Hvis du vælger et felt, der er [oprettet med spørgsmål og svar](end-user-q-and-a.md), så åbnes skærmbilledet spørgsmål og svar. Hvis du vælger et felt, der er [oprettet ved hjælp af dashboardets widget **Tilføj felt**](../create-reports/service-dashboard-add-widget.md), kan der ske flere ting: En video kan blive afspillet, et websted åbnet m.m.  


##  <a name="still-more-ways-to-open-a-report"></a>Der er stadig flere måder at åbne en rapport
Når du bliver mere fortrolig med at navigere i Power BI-tjenesten, finder du ud af, hvilke arbejdsprocesser der fungerer bedst for dig. Der er et par enkelte andre måder at få adgang til rapporter på:
- Via navigationsruden ved hjælp af [Favoritter](end-user-favorite.md) og [Seneste](end-user-recent.md)    
- Brug [Få vist relaterede](end-user-related.md)    
- Via en mail, når nogen [deler med dig](../collaborate-share/service-share-reports.md), eller du [angiver en advarsel](end-user-alerts.md)    
- Fra dit [Meddelelsescenter](end-user-notification-center.md)    
- Fra et arbejdsområde
- og meget mere

## <a name="next-steps"></a>Næste trin
[Åbn og få vist et dashboard](end-user-dashboard-open.md)    
[Rapportfiltre](end-user-report-filter.md)

