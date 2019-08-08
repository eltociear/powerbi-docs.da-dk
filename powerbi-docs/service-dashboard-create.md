---
title: Opret et Power BI-dashboard fra en rapport
description: Opret et Power BI-dashboard fra en rapport
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/17/2019
ms.author: maggies
ms.openlocfilehash: b50d247f54cfe2af4cefbd14b9528b1dfa263acf
ms.sourcegitcommit: bc688fab9288ab68eaa9f54b9b59cacfdf47aa2e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/30/2019
ms.locfileid: "68624315"
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Opret et Power BI-dashboard fra en rapport
Du har læst [Introduktion til dashboards i Power BI](service-dashboards.md), og nu vil du oprette dit eget. Der er mange forskellige måder at oprette et dashboard på. Du kan f.eks. oprette et dashboard fra en rapport, fra bunden, fra et datasæt, ved at kopiere et eksisterende dashboard og meget mere.  

Da det kan virke overvældende, når du starter for første gang, begynder vi med hurtigt og nemt at oprette et dashboard, som fastgør visualiseringer fra en rapport, der allerede er oprettet. 

Når du har gennemført denne hurtige start, har du en god forståelse af:
- Forholdet mellem dashboards og rapporter
- Hvordan du åbner redigeringsvisningen i rapporteditoren
- Sådan fastgøres felter 
- Sådan navigerer du mellem et dashboard og en rapport 

## <a name="who-can-create-a-dashboard"></a>Hvem kan oprette et dashboard?
Muligheden for at oprette et dashboard anses som en *opretterfunktion*  og kræver redigeringsrettigheder til rapporten. Redigeringstilladelser er tilgængelige for rapportoprettere og de kolleger, opretteren giver adgang til. Hvis David f.eks. opretter en rapport i workspaceABC og derefter tilføjer dig som medlem af dette arbejdsområde, har både du og David redigeringsrettigheder. På anden side, hvis en rapport er blevet delt med dig direkte eller som en del af en [Power BI-app](service-create-distribute-apps.md) (du *bruger* rapporten), kan du ikke fastgøre felter til et dashboard.
 
![Dashboard](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

> [!NOTE] 
> Dashboards er en funktion i Power BI-tjenesten ikke Power BI Desktop. Selvom der kan ikke oprettes dashboards på Power BI-mobilenheder, kan du [få dem vist og dele dem](consumer/mobile/mobile-apps-view-dashboard.md) der.
>
> 

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Video: Opret et dashboard ved at fastgøre visualiseringer og billeder fra en rapport
Se Amanda oprette et nyt dashboard ved at fastgøre visualiseringer fra en rapport. Følg derefter fremgangsmåden i [Importér et datasæt med en rapport](#import-a-dataset-with-a-report) på egen hånd ved hjælp af Indkøbsanalyse-eksemplet.
    

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>Importér et datasæt med en rapport
Vi importerer et af eksempeldatasættene i Power BI og bruger det til at oprette vores nye dashboard. Det eksempel, vi bruger, er en Excel-projektmappe med to PowerView-ark. Når du importerer projektmappen til Power BI, føjes der et datasæt og en rapport til dit arbejdsområde. Rapporten oprettes automatisk ud fra PowerView-arkene.

1. Download [Excel-filen](http://go.microsoft.com/fwlink/?LinkId=529784) med Indkøbsanalyse-eksemplet. Det anbefales, at du gemme den i din OneDrive for Business.
2. Åbn Power BI-tjenesten i din browser (app.powerbi.com).
3. Vælg **Mit arbejdsområde** fra venstre navigationsrude, og vælg derefter **Hent Data**.

    ![Venstre navigationsrude](media/service-dashboard-create/power-bi-get-data3.png)
5. Vælg **Filer**.

   ![Hent filer](media/service-dashboard-create/power-bi-select-files.png)
6. Naviger til den placering, hvor du har gemt Excel-filen med eksempel på indkøbsanalyse. Markér den, og vælg **Opret forbindelse**.

   ![Opret forbindelse til filer](media/service-dashboard-create/power-bi-connectnew.png)
7. Til denne øvelse skal du vælge **Importér**.

    ![Vinduet OneDrive for Business](media/service-dashboard-create/power-bi-import.png)
8. Når du får vist meddelelsen om, at processen lykkedes, skal du klikke på **x** for at afvise den.

   ![Meddelelse om fuldførelse](media/service-dashboard-create/power-bi-view-datasetnew.png)

### <a name="open-the-report-and-pin-tiles-to-your-dashboard"></a>Åbn rapporten, og fastgør felter på dit dashboard
1. I det samme arbejdsområde skal du vælge fanen **Rapporter** og derefter vælge **Indkøbsanalyseeksempel** for at åbne rapporten.

    ![Fanen Rapporter](media/service-dashboard-create/power-bi-reports.png) Rapporten åbnes som standard i Læsevisning. Bemærk, at den har to faner nederst: **Rabatanalyse** og **Oversigt over forbrug**. Hver fane repræsenterer en side i rapporten.

2. Vælg **Rediger rapport** for at åbne rapporten i Redigeringsvisning.

    ![Rapport i Læsevisning](media/service-dashboard-create/power-bi-reading-view.png)
3. Peg på en visualisering for at få vist de tilgængelige indstillinger. Hvis du vil føje en visualisering til et dashboard, skal du vælge ikonet til fastgørelse ![Tegnestiftikon](media/service-dashboard-create/power-bi-pin-icon.png).

    ![Peg på et felt](media/service-dashboard-create/power-bi-hover.png)
4. Da vi opretter et nyt dashboard, skal du markere indstillingen for **nyt dashboard** og give den et navn.

    ![Dialogboksen Fastgør til dashboard](media/service-dashboard-create/power-bi-pin-tile.png)
5. Når du vælger **Fastgør**, opretter Power BI det nye dashboard i det aktuelle arbejdsområde. Efter at meddelelsen **Fastgjort til dashboard** vises, skal du vælge **Gå til dashboard**. Hvis du bliver bedt om at gemme rapporten, skal du vælge **Gem**.

    ![Meddelelse om fuldførelse](media/service-dashboard-create/power-bi-pin-success.png)

    Power BI åbner det nye dashboard. Det har ét felt: den visualisering, du lige har fastgjort.

   ![dashboard med et felt](media/service-dashboard-create/power-bi-pinned.png)
7. Markér feltet for at vende tilbage til rapporten. Fastgør nogle flere felter til det nye dashboard. Når vinduet **Fastgør til dashboard** vises, skal du vælge **Eksisterende dashboard**.  

   ![Dialogboksen Fastgør til dashboard](media/service-dashboard-create/power-bi-existing-dashboard.png)

## <a name="pin-an-entire-report-page-to-the-dashboard"></a>Fastgør en hel rapportside til dashboardet
I stedet for at fastgøre én visualisering ad gangen, kan du [fastgøre en hel rapportside som et *dynamisk felt*](service-dashboard-pin-live-tile-from-report.md). Lad os gøre det.

1. I rapporteditoren skal du vælge fanen **Udgiftsoversigt** for at åbne den anden side i rapporten.

   ![Fanen Rapport](media/service-dashboard-create/power-bi-page-tab.png)

2. Vi vil gerne have alle de visuals i rapporten på dit dashboard. I øverste højre hjørne af menulinjen skal du vælge **Fastgør en dynamisk side**. På et dashboard opdateres felter for dynamiske sider hver gang, siden opdateres.

   ![Øverst til højre i rapporteditoren](media/service-dashboard-create/power-bi-pin-live.png)

3. Når vinduet **Fastgør til dashboard** vises, skal du vælge **Eksisterende dashboard**.

   ![Dialogboksen Fastgør til dashboard](media/service-dashboard-create/power-bi-pin-live2.png)

4. Efter du får vist en meddelelse om, at handlingen er udført, skal du vælge **Gå til dashboard**. Der kan du se de felter, du har fastgjort fra rapporten. I nedenstående eksempel har vi fastgjort to felter fra side 1 i rapporten, og ét dynamisk felt, som udgør side 2 i rapporten.

   ![Dashboard](media/service-dashboard-create/power-bi-dashboard.png)

## <a name="next-steps"></a>Næste trin
Tillykke med oprettelsen af dit første dashboard! Nu, hvor du har et dashboard, er der utroligt meget, du kan bruge det til. Følg en af de foreslåede artikler nedenfor, eller kom i gang med at udforske det: 

* [Tilpas størrelsen af felter, og flyt dem](service-dashboard-edit-tile.md)
* [Alt om dashboardfelter](service-dashboard-tiles.md)
* [Del dit dashboard ved at oprette en app](service-create-workspaces.md)
* [Power BI – Grundlæggende begreber](service-basic-concepts.md)
* [Tip til udformning af et fantastisk dashboard](service-dashboards-design-tips.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/).
