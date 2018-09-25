---
title: Åbn en rapport i Læsevisning eller Redigeringsvisning i Power Bi-tjenesten
description: Åbn en Power BI-rapport i Læsevisning eller Redigeringsvisning
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mihart
ms.openlocfilehash: fe1916b2b287dffd59bf4535cc07e13d10d01321
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565791"
---
# <a name="open-a-report-in-power-bi-service-apppowerbicom"></a>Åbn en rapport i Power BI-tjenesten (app.powerbi.com)
Rapporter er tilgængelige i Power BI-tjenesten, Power BI Desktop, Power BI - Mobil og endda Power BI Embedded. Denne artikel gælder for åbning af rapporter i ***Power BI-tjenesten***.

Der er to forskellige tilstande til at få vist og interagere med rapporter i Power BI-tjenesten: [Læsevisning og Redigeringsvisning](end-user-reading-view.md). Læsevisning er tilgængelig for alle brugere og er især udviklet til *forbrugere* af rapporter, mens Redigeringsvisning kun er tilgængelig for *oprettere* og ejere af rapporter. 

## <a name="open-a-report-from-a-workspace-via-the-reports-content-view-list"></a>Åbn en rapport fra et arbejdsområde (via indholdsvisningslisten **Rapporter**)

1. Start i et arbejdsområde, og vælg fanen **Rapporter** for at få vist alle rapporter i dette arbejdsområde.  
   
   ![Fanen Rapporter i et arbejdsområde](./media/end-user-report-open/power-bi-open-report.png)
2. Vælg rapportens navn for at åbne rapporten i Læsevisning.  
   
    ![rapport i Læsevisning](./media/end-user-report-open/power-bi-reading-view.png)
3. Der er [så meget, du kan gøre i Læsevisning](end-user-reading-view.md).  Denne eksempelrapport indeholder flere sider, så du kan starte med at udforske hver fane nederst på rapportlærredet. 

## <a name="open-a-report-from-a-dashboard"></a>Åbn en rapport fra et dashboard
Der er mange andre måder at åbne en rapport. Du kan f.eks. starte på et dashboard og vælge et felt, der er oprettet ud fra en rapport.  Når flisen vælges, åbnes rapporten i Læsevisning. [Åbn eksempeldashboardet Salg og marketing](../sample-datasets.md) for at følge med.

1. Åbn et dashboard, og vælg et felt.

   Hvis du vælger et felt, der er [oprettet med spørgsmål og svar](../service-dashboard-pin-tile-from-q-and-a.md), så åbnes skærmbilledet spørgsmål og svar. Hvis du vælger et felt, der er [oprettet ved hjælp af dashboardet **Tilføj felt**-widget'en](../service-dashboard-add-widget.md), skal du åbne guiden, hvis du vil redigere denne widget.  

2.  I dette eksempel har vi valgt søjlediagramfeltet "Enheder i alt ÅTD...".

    ![dashboard med valgt felt](./media/end-user-report-open/power-bi-dashboard.png)

3.  Den tilknyttede rapport åbner i Læsevisning. Bemærk, at vi er på siden "ÅTD-kategori". Dette er rapportsiden, der indeholder det søjlediagram, vi har valgt på dashboardet.

    ![rapport, der er åbnet i Læsevisning](./media/end-user-report-open/power-bi-report.png)

4. Bliv i Læsevisning eller vælg **Rediger rapport** for at åbne rapporten i Redigeringsvisning. Vær opmærksom på, at kun brugere med redigeringsrettigheder for denne rapport kan åbne den i redigeringstilstand.

    ![Rapporteditor, der viser ikonet Rediger rapport](./media/end-user-report-open/power-bi-edit-report.png)

## <a name="create-a-brand-new-report-from-a-dataset"></a>Opret en ny rapport ud fra et datasæt
Og én metode mere til at åbne en rapport er fra et datasæt. Når du starter fra et datasæt, vil rapportcanvasset være tomt, så denne metode anbefales til *oprettere* af rapporter, som er interesserede i at oprette en ny rapport, der er baseret på et datasæt, som vedkommende ejer. Som eksemplet ovenfor, skal du downloade [Eksempelprogrammet salg og marketing](../sample-datasets.md) for at følge med.

1. Start i arbejdsområdet, der indeholder det datasæt, du vil bruge som udgangspunkt for en rapport.

   ![venstre navigationsrude, der viser apparbejdsområder](./media/end-user-report-open/power-bi-workspace.png)

2. Vælg fanen **Datasæt** for at få vist listen over alle datasæt i dette arbejdsområde. Dette kaldes listen over **Datasætindhold**.
   
   ![liste over datasæt](./media/end-user-report-open/power-bi-dataset.png)

1. Find datasættet og vælg ikonet **Opret rapport** for at åbne datasættet i redigeringsvisning. Hvis du ikke har redigeringsrettigheder til et datasæt, kan du ikke åbne det. 
   
    ![datasæt med ikonet Opret rapport](./media/end-user-report-open/power-bi-create-report.png)

3. Datasættet åbnes i rapporteditoren. Du får vist de datafelter, der vises til højre, som kun venter på, at du begynder at udforske og oprette visualiseringer. 

   ![rapportcanvas](./media/end-user-report-open/power-bi-blank-canvas.png)

##  <a name="still-more-ways-to-open-a-report"></a>Der er stadig flere måder at åbne en rapport
Når du bliver mere fortrolig med at navigere i Power BI-tjenesten, finder du ud af hvilke arbejdsprocesser, der fungerer bedst for dig. Der er et par enkelte andre måder at få adgang til rapporter på:
- Fra den venstre navigationsrude ved hjælp af **Favoritter**, **Seneste**, **Apps** og **Delt med mig**. 
- Brug [Få vist relaterede](end-user-related.md)
- I en mail, når nogen [deler med dig](../service-share-reports.md), eller du [angiver en advarsel](../service-set-data-alerts.md).    
- Fra dit [Meddelelsescenter](end-user-notification-center.md)    
- og meget mere

## <a name="next-steps"></a>Næste trin
Få mere at vide om [rapporter i Power BI](end-user-reports.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)  

