---
title: Tip og tricks til farveformatering i Power BI
description: Tip og tricks til farveformatering i Power BI
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Visualizations
ms.openlocfilehash: 3c91a6a70899a4a59c3d98cd9ab948284df5b662
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34298383"
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

Hvis du vil foretage ændringer, skal du redigere en rapport: Vælg din **rapport** i ruden **Mit arbejdsområde**, vælg derefter **Rediger rapport** i det øverste menuområde, som det vises på det følgende billede.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_1.png)

Når ruden **Visualiseringer** vises langs højre side af canvasset **Rapport**, er du klar til at starte tilpasning.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_2.png)

## <a name="change-the-color-of-a-single-data-point"></a>Skift farve på et enkelt datapunkt
Nogle gange kan du få brug for at fremhæve ét bestemt datapunkt. Måske er det salgstal for lanceringen af et nyt produkt eller højere kvalitetsbedømmelser efter lancering af et nyt program. Med Power BI kan du fremhæve et bestemt datapunkt ved at ændre dets farve.

Følgende visualisering rangordner tilstande efter leveomkostninger. 

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_3.png)

Forestil dig nu, at du hurtigt vil vise, hvor Washington lander på denne rangordnede, ved hjælp af farve. Her er trinnene:

Udvid afsnittet **Datafarver**. Følgende vises.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_4.png)

Indstil **Vis alle** til **Til**. Farverne vises nu for hvert dataelement i visualiseringen. Når du peger på datapunkterne, aktiveres rulning, så du kan ændre datapunkterne.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_5.png)

Lad os i dette tilfælde ændre **Washington** til grøn. Vi ruller ned til **Washington** og vælger pil ned i farveboksen, og vinduet til valg af farve åbnes.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_6.png)

Når det er valgt, har datapunktet **Washington** en pæn grøn nuance og skiller sig klart ud.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_7.png)

Selvom du ændrer visualiseringstyper og derefter vender tilbage, kan Power BI huske valget, og **Washington** er stadig grøn.

Du kan også ændre farven på et datapunkt for mere end ét dataelementet. På det følgende billede er **Arizona** rød, og **Washington** er stadig grøn.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_8.png)

Der er forskellige ting, du kan gøre med farver. I det næste afsnit kigger vi på farveforløb.

## <a name="base-the-colors-of-a-chart-on-a-numeric-value"></a>Basér farverne i et diagram på en numerisk værdi
Diagrammer nyder ofte godt af dynamisk indstilling af farve baseret på den numeriske værdi i et felt. Ved at gøre dette kan du vise en anden værdi end normalt for størrelsen på en søjle og vise to værdier på en enkelt graf. Eller du kan bruge det til at fremhæve datapunkter over (eller under) en bestemt værdi – måske fremhæve områder med lav rentabilitet.

Følgende afsnit viser forskellige metoder til at basere farve på en numerisk værdi.

## <a name="base-the-color-of-data-points-on-a-value"></a>Basér farven på datapunkter på en værdi
Hvis du vil ændre farve baseret på en værdi, skal du trække det felt, du vil basere farve på, til området **Farvemætning** i ruden **Felt**. På det følgende billede er **Profit before tax** blevet trukket til **Farvemætning**. Som du kan se: Selvom **Velo** har højere **Gross Sales** (kolonnen er højere), har **Amarilla** en større **Profit before tax** (kolonnen indeholder mere farvemætning).

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_9.png)

## <a name="customize-the-colors-used-in-the-color-scale"></a>Tilpas de farver, der bruges i farveskalaen
Du kan også tilpasse farver, der bruges i farveskalaen. Udvid **Datafarver**, og du får vist et farveforløb, der bruges til at visualisere dine data. Som standard er den laveste værdi i dine data knyttet til den mindst mættede farve, og den højeste værdi til den mest mættede farve.

Farveområdet vises i en farveforløbslinje, der viser spektret mellem farveværdier for **Minimum** og **Maksimum**, med farven med **minimumværdien** til venstre, og farven med **maksimumværdien** til højre.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_10.png)

Vælg farverullelisten ud for **Minimum** eller **Maksimum**, hvis du vil ændre skalaen til at bruge et andet farveområde, og vælg en farve. Følgende billede viser den **maksimale** farve, der er ændret til sort, og farveforløbslinjen viser det nye farvespektrum mellem **Minimum** og **Maksimum**.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_11.png)

Du kan også ændre den måde, som værdierne knyttes til disse farver på. På det følgende billede er farverne for **Minimum** og **Maksimum** indstillet til henholdsvis orange og grøn.

Læg mærke til på dette første billede, hvordan søjlerne i diagrammet afspejler det farveforløb, der vises i bjælken. Den højeste værdi er grøn, den laveste er orange, og hver søjle mellem er farvet med en nuance af spektret mellem grøn og orange.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_12.png)

Lad os se, hvad der sker, hvis vi angiver numeriske værdier i værdifelterne **Minimum** og **Maksimum**, som er under farvevælgerne **Minimum** og **Maksimum** (vises på følgende billede). Lad os indstille **Minimum** til 20.000.000 og indstille **Maksimum** til 20.000.000.

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

