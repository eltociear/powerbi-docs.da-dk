---
title: Kørsel af R-scripts i Power BI Desktop
description: Kørsel af R-scripts i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 188669525a210afc516cc9740d5d7e7c5682ea93
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514725"
---
# <a name="run-r-scripts-in-power-bi-desktop"></a>Kør R-scripts i Power BI Desktop
Du kan køre R-scripts direkte i **Power BI Desktop** og importere de resulterende datasæt i en datamodel i Power BI Desktop.

## <a name="install-r"></a>Installér R
Hvis du vil køre R-scripts i Power BI Desktop, skal du installere **R** på din lokale maskine. Du kan downloade og installere **R** gratis fra mange forskellige steder, herunder [downloadsiden for Revolution Open](https://mran.revolutionanalytics.com/download/) og [CRAN Repository](https://cran.r-project.org/bin/windows/base/). Den aktuelle version af R-script i Power BI Desktop understøtter Unicode-tegn og mellemrum (tomme tegn) i installationsstien.

## <a name="run-r-scripts"></a>Kør R-scripts
Med blot nogle få trin i Power BI Desktop kan du køre R-scripts og oprette en datamodel, hvorfra du kan oprette rapporter og dele dem i Power BI tjenesten. R-script i Power BI Desktop understøtter nu talformater, der indeholder decimaler (.) og kommaer (,).

### <a name="prepare-an-r-script"></a>Klargør et R-script
Hvis du vil køre et R-script i Power BI Desktop, skal du oprette scriptet i dit lokale R-udviklingsmiljø og sørge for, at det kører korrekt.

Hvis du vil køre scriptet i Power BI Desktop, skal du kontrollere, at scriptet kører korrekt i et nyt og uændret arbejdsområde. Det betyder, at alle pakker og afhængigheder udtrykkeligt skal være indlæst og køre. Du kan bruge *source()* til at køre afhængige scripts.

Når du forbereder og kører et R-script i Power BI Desktop, er der et par begrænsninger:

* Det er kun datarammer, der importeres, derfor skal du sørge for, at de data, du vil importere til Power BI, er repræsenteret i en dataramme
* Kolonner, der skrives som Kompleks og Vektor importeres ikke, og de erstattes af fejlværdier i den oprettede tabel
* Værdier, der ikke er tilgængelige oversættes til NULL-værdier i Power BI Desktop
* Der opstår timeout for R-scripts, som har kørt i mere end 30 minutter
* Interaktive kald i R-scriptet, f.eks. afventer brugerinput, stopper kørslen af scriptet
* Når arbejdsmappen angives i R-scriptet, *skal* du definere en fuld sti til arbejdsmappen i stedet for en relativ sti

### <a name="run-your-r-script-and-import-data"></a>Kør R-scriptet, og importér data
1. I Power BI Desktop findes dataconnectoren for R-scriptet under **Hent data**. Hvis du vil køre R-scriptet, skal du vælge **Hent data &gt; Mere...**  og derefter vælge **Andet &gt; R-script** som vist på følgende billede:
   
   ![](media/desktop-r-scripts/r-scripts-1.png)
2. Hvis R er installeret på din lokale maskine, vælges den senest installerede version som R-programmet. Du skal blot kopiere scriptet ind i scriptvinduet og vælge **OK**.
   
   ![](media/desktop-r-scripts/r-scripts-2.png)
3. Hvis R ikke er installeret, ikke kan identificeres, eller hvis der er flere installationer på din lokale maskine, skal du udvide **Indstillinger for R-installation** for at få vist installationsindstillingerne eller for at vælge, hvilken installation du vil bruge til kørsel af R-scriptet.
   
   ![](media/desktop-r-scripts/r-scripts-3.png)
   
   Hvis R er installeret, men ikke er identificeret, kan du udtrykkeligt angive dets placering i tekstfeltet, som vises, når du udvider **Indstillinger for R-installation**. På billedet ovenfor er stien *C:\Program Files\R\R-3.2.0* udtrykkeligt angivet i tekstfeltet.
   
   Indstillingerne for R-installation findes centralt i sektionen om R-scripts i dialogboksen Indstillinger. Du angiver indstillingerne for din R-installation ved at vælge **Filer > Indstillinger**  og derefter **Indstillinger > R-script**. Hvis der er flere R-installationer tilgængelige, vises der en rullemenu, hvor du kan vælge, hvilken installation der skal bruges.
   
   ![](media/desktop-r-scripts/r-scripts-4.png)
4. Vælg **OK** for at køre R-scriptet. Når scriptet køres, kan du vælge de resulterende datarammer, der skal føjes til Power BI-modellen.

### <a name="refresh"></a>Opdater
Du kan opdatere et R-script i Power BI Desktop. Når du opdaterer et R-script, køres R-scriptet i Power BI Desktop igen i Power BI Desktop-miljøet.

## <a name="next-steps"></a>Næste trin
Du kan finde flere oplysninger om R i Power BI i følgende artikler.

* [Opret R-visualiseringer i Power BI Desktop](desktop-r-visuals.md)
* [Brug en ekstern R IDE med Power BI](desktop-r-ide.md)

