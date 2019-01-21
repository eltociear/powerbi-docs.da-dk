---
title: Tip og tricks til farveformatering i Power BI
description: Tip og tricks til farveformatering i Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/09/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 71ed70344281dec3353b73c8698594d62ef32eae
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54285593"
---
# <a name="tips-and-tricks-for-color-formatting-in-power-bi"></a>Tip og tricks til farveformatering i Power BI
Power BI indeholder mange forskellige måder at tilpasse dine dashboards og rapporter på. Denne artikel indeholder en samling af tip, som kan gøre dine Power BI-visualiseringer mere overbevisende, interessante og tilpasset efter dine behov.

Der findes følgende tip. Har du et andet fantastiske tip? Fantastisk! Send det til os, og vi finder ud af, om det skal føjes til listen.

* Skift farve på et enkelt datapunkt
* Basér farverne i et diagram på en numerisk værdi
* Basér farven på datapunkter på en feltværdi
* Tilpas farver, der bruges i farveskalaen
* Brug divergerende farveskalaer
* Sådan fortryder du i Power BI

Hvis du vil foretage ændringer, skal du redigere en rapport. Åbn rapporten, og vælg **Rediger rapport** i det øverste menuområde, som vist på følgende billede.

![](media/service-tips-and-tricks-for-color-formatting/power-bi-edit.png)

Når ruden **Visualiseringer** vises langs højre side af canvasset **Rapport**, er du klar til at starte tilpasning. Hvis ruden ikke vises, skal du vælge pilen i øverste højre hjørne for at åbne ruden.

![](media/service-tips-and-tricks-for-color-formatting/power-bi-formatting-pane.png)

## <a name="change-the-color-of-a-single-data-point"></a>Skift farve på et enkelt datapunkt
Nogle gange kan du få brug for at fremhæve ét bestemt datapunkt. Måske er det salgstal for lanceringen af et nyt produkt eller højere kvalitetsbedømmelser efter lancering af et nyt program. Med Power BI kan du fremhæve et bestemt datapunkt ved at ændre dets farve.

Følgende visualisering rangordner solgte enheder efter produktsegment. 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-grey.png)

Forestil dig nu, at du vil fremhæve segmentet **Convenience** for at vise, hvor godt dette nye segment præsterer, ved hjælp af farve. Her er trinnene:

Udvid afsnittet **Datafarver**, og slå skyderen til **Vis alle**. Farverne vises nu for hvert dataelement i visualiseringen. Når du peger på datapunkterne, aktiveres rulning, så du kan ændre datapunkterne.

![](media/service-tips-and-tricks-for-color-formatting/power-bi-show-all.png)

Angiv **Convenience** til orange. 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-orange.png)

Når du har foretaget et valg, får datapunktet **Convenience** en pæn orange nuance, der helt sikkert skiller sig ud.

Selvom du ændrer visualiseringstyper og derefter vender tilbage, kan Power BI huske valget, og **Convenience** er stadig orange.

Du kan ændre farven på et datapunkt for én, flere eller alle dataelementer i visualiseringen. Måske vil du gerne have, at din visual får virksomhedens farver. 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-corporate.png)

Der er forskellige ting, du kan gøre med farver. I det næste afsnit kigger vi på farveforløb.

## <a name="base-the-colors-of-a-chart-on-a-numeric-value"></a>Basér farverne i et diagram på en numerisk værdi
Diagrammer nyder ofte godt af dynamisk indstilling af farve baseret på den numeriske værdi i et felt. Ved at gøre dette kan du vise en anden værdi end normalt for størrelsen på en søjle og vise to værdier på en enkelt graf. Eller du kan bruge det til at fremhæve datapunkter over (eller under) en bestemt værdi – måske fremhæve områder med lav rentabilitet.

Følgende afsnit viser forskellige metoder til at basere farve på en numerisk værdi.

## <a name="base-the-color-of-data-points-on-a-value"></a>Basér farven på datapunkter på en værdi
Hvis du vil ændre farve baseret på en værdi, skal du trække det felt, du vil basere farven på, til området **Farvemætning** i ruden **Felter**. På det følgende billede er **%Market Share SPLY YTD** blevet trukket til **Farvemætning**. 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-color-saturation.png)

I ruden Formatering under **Datafarver** skal du bestemme, hvordan værdien **%Market Share SPLY YTD** får ændret farven og skyggen i dit søjlediagram. I dette eksempel bliver de lave værdier for %Market Share lyseblå og de høje værdier mørkeblå.


![](media/service-tips-and-tricks-for-color-formatting/power-bi-data-colors2.png)


Det fremgår, at selvom vi har solgt flere enheder af både **Productivity** og **Extreme** (deres kolonner er højere), har **Moderation** en større **%Market Share SPLY YTD** (kolonnen indeholder en mere mættet farve).

![](media/service-tips-and-tricks-for-color-formatting/power-bi-saturation.png)

## <a name="customize-the-colors-used-in-the-color-scale"></a>Tilpas de farver, der bruges i farveskalaen
Du kan også tilpasse farver, der bruges i farveskalaen. Som standard er den laveste værdi i dine data knyttet til den mindst mættede farve, og den højeste værdi til den mest mættede farve. Vi har brugt en blå graduering i billedet ovenfor. 

Udvid **Datafarver**, og du får vist et farveforløb, der bruges til at visualisere dine data. Farveområdet vises i en farveforløbslinje, der viser spektret mellem farveværdier for **Minimum** og **Maksimum**, med farven med **minimumværdien** til venstre, og farven med **maksimumværdien** til højre.

![](media/service-tips-and-tricks-for-color-formatting/power-bi-data-colors2.png)


Vælg farverullelisten ud for **Minimum** eller **Maksimum**, hvis du vil ændre skalaen til at bruge et andet farveområde, og vælg en farve. Følgende billede viser den **maksimale** farve, der er ændret til sort, og farveforløbslinjen viser det nye farvespektrum mellem **Minimum** og **Maksimum**.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_11.png)

Du kan også ændre den måde, som værdierne knyttes til disse farver på. På det følgende billede er farverne for **Minimum** og **Maksimum** indstillet til henholdsvis orange og grøn.

Læg mærke til på dette første billede, hvordan søjlerne i diagrammet afspejler det farveforløb, der vises i bjælken. Den højeste værdi er grøn, den laveste er orange, og hver søjle mellem er farvet med en nuance af spektret mellem grøn og orange.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_12.png)

Lad os se, hvad der sker, hvis vi angiver numeriske værdier i værdifelterne **Minimum** og **Maksimum**, som er under farvevælgerne **Minimum** og **Maksimum** (vises på følgende billede). Lad os angive 20.000.000 som **Minimum** og angive 20.000.001 som **Maksimum**.

Ved at angive disse værdier anvendes farveforløb ikke længere på værdierne i diagrammet, der er under **Minimum** eller over **Maksimum**. En søjle med en værdi over værdien **Maksimum** har farven grøn, og en søjle med en værdi under værdien **Minimum** har farven rød.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_13.png)

## <a name="use-diverging-color-scales"></a>Brug divergerende farveskalaer
Dine data kan nogle gange have en naturligt divergerende skala. Et tempereret område har for eksempel et naturligt centrum ved frysepunktet, og en rentabilitetsbedømmelse har et naturligt midtpunkt (nul).

Skub skyderen **Divergerende** til **Til**, hvis du vil bruge divergerende farveskalaer. Når **Divergerende** er slået til, vises en yderligere farvevælger og et værdifelt, der begge kaldes **Centrum**, som det vises på følgende billede.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_14.png)

Når skyderen **Divergerende** er slået til, kan du angive farverne for **Minimum**, **Maksimum** og **Centrum** separat. På det følgende billede er **Centrum** indstillet til en, så søjler med værdier over en er en farveforløbsnuance af grøn, og søjler under en er nuancer af rød.

## <a name="how-to-undo-in-power-bi"></a>Sådan fortryder du i Power BI
Som mange andre Microsoft-tjenester og -software giver Power BI en nem måde at fortryde den seneste kommando på. Lad os for eksempel antage, at du ændrer farven på et datapunkt eller en serie af datapunkter, og du ikke kan lide farven, når den vises i visualiseringen. Du kan ikke huske præcis, hvilken farve det havde før, men du ved, du vil farven tilbage!

Hvis du vil **fortryde** din sidste handling, eller de sidste par handlinger, skal du bare gøre følgende:

- Tryk på CTRL + Z

## <a name="feedback"></a>Feedback
Har du et tip, du vil dele? Send det til os, og vi finder ud af, om det skal medtages her.

>[!NOTE]
>Disse farve-, akse- og relaterede tilpasninger, der er tilgængelige, når ikonet **Formatér** er valgt, er også tilgængelige i Power BI Desktop.

## <a name="next-steps"></a>Næste trin
[Introduktion til farveformatering og akseegenskaber](service-getting-started-with-color-formatting-and-axis-properties.md)

