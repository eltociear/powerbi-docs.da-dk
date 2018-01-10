---
title: Kortvisualiseringer (dvs. felter med store tal)
description: Opret en kortvisualisering i Power BI
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 12/24/2017
ms.author: mihart
ms.openlocfilehash: 1136aae9af4481a1d55ca3d11ed300242aab187b
ms.sourcegitcommit: 74fbbca81a056dda19b3647ae058005aba5296f5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/03/2018
---
# <a name="card-visualizations"></a>Kortvisualiseringer
Nogle gange er et enkelt tal det vigtigste, du vil finde frem til på dit Power BI-dashboard eller i din Power BI-rapport som f.eks. salg i alt, markedsandel fra år til år eller salgsmuligheder i alt. Denne type visualisering kaldes et *kort*. Som med næsten alle de oprindelige Power BI-visualiseringer kan kort oprettes ved hjælp af rapporteditoren eller Spørgsmål og svar.

![kortvisualisering](media/power-bi-visualization-card/pbi_opptuntiescard.png)

## <a name="create-a-card-using-the-report-editor"></a>Opret et kort ved hjælp af rapporteditoren
I denne vejledning bruges Retail Analysis Sample (Eksempel på detailhandelsanalyse). Du skal [downloade eksemplet](sample-datasets.md) til Power BI-tjenesten (app.powerbi.com) eller Power BI Desktop, så du kan følge med.   

1. Start på en [tom rapportside](power-bi-report-add-page.md), og vælg feltet **Store** \> **Open store count**. Hvis du bruger Power BI-tjenesten, skal du åbne rapporten i [Redigeringsvisning](service-interact-with-a-report-in-editing-view.md).

    Power BI opretter et søjlediagram med det ene tal.

   ![](media/power-bi-visualization-card/pbi_rptnumbertilechart.png)
2. Vælg kortikonet i ruden Visualiseringer.

   ![](media/power-bi-visualization-card/pbi_changechartcard.png)
6. Hold markøren over et kort, og vælg ikonet med tegnestiften ![](media/power-bi-visualization-card/pbi_pintile.png) for at føje visualiseringen til dashboardet.

   ![](media/power-bi-visualization-card/power-bi-pin-icon.png)
7. Fastgør feltet til et eksisterende dashboard eller et nyt dashboard.

   * Eksisterende dashboard: Vælg navnet på dashboardet på rullelisten.
   * Nyt dashboard: Skriv navnet på det nye dashboard.
8. Vælg **Fastgør**.

   En meddelelse om fuldførelse (næsten helt oppe i højre hjørne) giver dig besked om, at visualiseringen er blevet føjet til dit dashboard som et felt.

   ![](media/power-bi-visualization-card/power-bi-pin-success-message.png)
9. Vælg **Gå til dashboard**. Der kan du [redigere og flytte](service-dashboard-edit-tile.md) den fastgjorte visualisering.


## <a name="create-a-card-from-the-qa-question-box"></a>Opret et kort fra feltet til spørgsmål i Spørgsmål og svar
Feltet til spørgsmål er den nemmeste måde at oprette et kort på. Feltet til spørgsmål i Spørgsmål og svar er tilgængelig i Power BI-tjenesten (app.powerbi.com) fra et dashboard eller en rapport. Nedenstående trin beskriver oprettelsen af et kort fra et dashboard i Power BI-tjenesten. Hvis du gerne vil oprette et kort ved hjælp af Spørgsmål og svar i Power BI Desktop, [skal du følge denne vejledning](https://powerbi.microsoft.com/en-us/blog/power-bi-desktop-december-feature-summary/#QandA) for at få prøveversionen af Spørgsmål og svar til Desktop-rapporter.

1. Opret et [dashboard](service-dashboards.md), og [hent data](service-get-data.md). I dette eksempel bruges [eksemplet Opportunity Analysis](sample-opportunity-analysis.md).

1. Begynd at skrive dit spørgsmål i feltet til spørgsmål øverst i dashboardet. 

   ![](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

>**TIP**! Fra en rapport i Power BI-tjenesten skal du vælge [Stil et spørgsmål](service-reading-view-and-editing-view.md) på den øverste menulinje i **Redigeringsvisning**. I en rapport i Power BI Desktop skal du finde en tom plads i en rapport og dobbeltklikke for at åbne et felt til spørgsmål.

3. Skriv f.eks. "number of opportunities" i feltet til spørgsmål.

   ![](media/power-bi-visualization-card/power-bi-q-and-a.png)

   Feltet til spørgsmål kommer med forslag og tilpasninger og viser til sidst det samlede antal.  
4. Vælg ikonet med tegnestiften ![](media/power-bi-visualization-card/pbi_pintile.png) i øverste højre hjørne for at føje kortet til dashboardet.

   ![](media/power-bi-visualization-card/power-bi-pin.png)
5. Fastgør kortet som et felt til et eksisterende dashboard eller et nyt dashboard.

   * Eksisterende dashboard: Vælg navnet på dashboardet på rullelisten. Du vil kun kunne vælge blandt de dashboards, der findes i det aktuelle arbejdsområde.
   * Nyt dashboard: Skriv navnet på det nye dashboard, og det vil blive føjet til dit aktuelle arbejdsområde.
6. Vælg **Fastgør**.

   En meddelelse om fuldførelse (næsten helt oppe i højre hjørne) giver dig besked om, at visualiseringen er blevet føjet til dit dashboard som et felt.  

   ![](media/power-bi-visualization-card/power-bi-success.png)
7. Vælg **Gå til dashboard** for at se det nye felt. Der kan du [omdøbe, tilpasse størrelsen på, tilføje et hyperlink for og flytte feltet og meget mere](service-dashboard-edit-tile.md) på dit dashboard.

   ![](media/power-bi-visualization-card/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
- Hvis du ikke kan se feltet til spørgsmål, skal du kontakte system- eller lejeradministratoren.    
- Hvis du bruger Desktop og dobbeltklikker på et tomt sted i en rapport, og Spørgsmål og svar ikke åbnes, kan det være nødvendigt at aktivere funktionen.  Vælg **Fil > Indstillinger > Indstillinger > Funktioner til eksempelvisning > Q&A**, og genstart Desktop.


## <a name="next-steps"></a>Næste trin
[Dashboardfelter i Power BI](service-dashboard-tiles.md)

[Dashboards i Power BI](service-dashboards.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
