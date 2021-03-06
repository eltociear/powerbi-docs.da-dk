---
title: Indsendelsestest af en Power BI-visualisering
description: I denne artikel beskrives de testsager, som din visualisering skal bestå, før den publiceres i AppSource. Der er også valgfri testsager.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 04/15/2020
ms.openlocfilehash: 65e00fa5311ea12c9fe0011c6aa7c3e779f33dc5
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83131131"
---
# <a name="submission-testing-of-a-power-bi-visual"></a>Indsendelsestest af en Power BI-visualisering

Før du publicerer din visualisering i [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals), skal den bestå disse testsager. Test din visualisering, før du sender den. Hvis din visualisering ikke opfylder de påkrævede testsager, afvises den.

Du kan finde flere oplysninger om udgivelsesprocessen under [Publicer Power BI-visualiseringer til Partnercenter](./office-store.md).

## <a name="general-test-cases"></a>Generelle testsager

| Testsag | Forventet resultat
| --------- | ----------------
| Opret et **stablet søjlediagram** med **kategori** og **værdi**. Konvertér det til din visualisering, og vend tilbage til søjlediagrammet. | Der vises ingen fejl efter disse konverteringer. |
| Opret en **måler** med tre målinger. Konvertér den til din visualisering og derefter tilbage til **måler**. | Der vises ingen fejl efter disse konverteringer. |
| Foretag valg i din visualisering. | Andre visualiseringer afspejler valgene. |
| Vælg elementer i andre visualiseringer. | Din visualisering viser filtrerede data i henhold til det, der er valgt i andre visualiseringer. |
| Tjek minimum- og maksimumbetingelserne for **dataViewMapping**. | Feltbuckets kan acceptere flere felter, et enkelt felt eller bestemmes af andre buckets. Minimum-/maksimumbetingelserne for **dataViewMapping** skal være konfigureret korrekt i visualiseringens egenskaber. |
| Fjern alle felter i vilkårlig rækkefølge. | Der ryddes op i visualiseringen, efterhånden som felterne fjernes i vilkårlig rækkefølge. Der er ingen fejl i konsollen eller i browseren. |
| Åbn ruden **Formatér** med hver mulig bucketkonfiguration. | Denne test udløser ikke null-reference-undtagelser. |
| Filtrér data ved hjælp af ruden **Filter** på visualiserings-, side- og rapportniveau. | Værktøjstip er korrekte efter anvendelse af filtre. Værktøjstip viser den filtrerede værdi. |
| Filtrer data ved hjælp af et **udsnit**. | Værktøjstip er korrekte efter anvendelse af filtre. Værktøjstip viser den filtrerede værdi. |
| Filtrer data ved hjælp af en publiceret visualisering. Du kan f.eks. vælge et cirkeludsnit eller en kolonne. | Værktøjstip er korrekte efter anvendelse af filtre. Værktøjstip viser den filtrerede værdi. |
| Hvis krydsfiltrering understøttes, skal du kontrollere, at filtrene fungerer korrekt. | Det anvendte valg filtrerer andre visualiseringer på denne side i rapporten. |
| Vælg med tasterne Ctrl, Alt og Shift. | Der vises ikke nogen uventet funktionsmåde. |
| Rediger **visningstilstand** til **Faktisk størrelse**, **Tilpas til siden** og **Tilpas til bredde**. | Musekoordinaterne er nøjagtige. |
| Tilpas størrelsen på din visualisering. | Visualiseringen fungerer korrekt på tilpasningen af størrelsen. |
| Indstil rapportens størrelse til minimumværdien. | Der er ingen visningsfejl. |
| Sørg for, at rullepanelerne fungerer korrekt. | Der skal være rullepaneler, hvis det er nødvendigt. Kontrollér størrelsen på rullepanelet. Rullepanelerne må ikke være for brede eller høje. Placeringen og størrelsen af rullepanelerne skal være i overensstemmelse med andre elementer i visualiseringen. Kontrollér, at der er behov for rullepaneler til forskellige størrelser af visualiseringen. |
| Fastgør din visualisering til et **dashboard**. | Visualiseringen skal vises korrekt. |
| Føj flere versioner af din visualisering til en enkelt rapportside. | Alle versioner af visualiseringen vises og fungerer korrekt. |
| Føj flere versioner af din visualisering til flere rapportsider. | Alle versioner af visualiseringen vises og fungerer korrekt. |
| Skift mellem rapportsider. | Visualiseringen vises korrekt. |
| Test læsevisning og redigeringsvisning for visualiseringen. | Alle funktioner fungerer korrekt. |
| Hvis du bruger animationer i visualiseringen, kan du tilføje, ændre og slette elementer i visualiseringen. | Animationen af visuelle elementer fungerer korrekt. |
| Åbn ruden **Egenskab**. Slå egenskaber til og fra, angiv brugerdefineret tekst, fremhæv de tilgængelige indstillinger, og indtast forkerte data. | Visualiseringen reagerer korrekt. |
| Gem rapporten, og åbn den igen. | Alle indstillinger for egenskaber bevares. |
| Skift sider i rapporten, og skift tilbage igen. | Alle indstillinger for egenskaber bevares. |
| Test al funktionalitet for visualiseringen, herunder forskellige muligheder, som visualiseringen indeholder. | Alle visninger og funktioner fungerer korrekt. |
| Test alle numeriske datatyper, datoer og tegn som i følgende test. | Alle data er formateret korrekt. |
| Gennemse formateringen af værdier for værktøjstip, aksemærkater, datanavne og andre visuelle elementer med formatering. | Alle elementer er formateret korrekt. |
| Kontrollér, at datanavne bruger formatstrengen. | Alle datanavne er formateret korrekt. |
| Slå automatisk formatering til og fra for numeriske værdier i værktøjstip. | Værdierne i værktøjstippet vises korrekt. |
| Test dataposter med forskellige typer data, herunder numeriske, tekst, dato/klokkeslæt og forskellige formatstrenge fra modellen. Test forskellige datamængder, f.eks. tusindvis af rækker, én række og to rækker. | Alle vises, og funktionerne fungerer korrekt. |
| Angiv forkerte data i din visualisering, f.eks. null, uendelige værdier, negative værdier og forkerte værdityper. | Alle vises, og funktionerne fungerer korrekt. |

## <a name="optional-browser-testing"></a>Valgfri browsertest

AppSource-teamet validerer visualiseringer i de mest aktuelle Windows-versioner af Google Chrome-, Microsoft Edge- og Mozilla Firefox-browsere.
Du kan også teste din visualisering i følgende browsere.

| Testsag | Forventet resultat
| --------- | ----------------
| **Windows** |
| Google Chrome (tidligere version) | Alt vises, og funktionerne fungerer korrekt. |
| Mozilla Firefox (tidligere version) | Alt vises, og funktionerne fungerer korrekt. |
| Microsoft Edge (tidligere version) | Alt vises, og funktionerne fungerer korrekt. |
| Microsoft Internet Explorer 11 (valgfri) | Alt vises, og funktionerne fungerer korrekt. |
| **macOS** |
| Chrome (tidligere version) | Alt vises, og funktionerne fungerer korrekt. |
| Firefox (tidligere version) | Alt vises, og funktionerne fungerer korrekt. |
| Safari (tidligere version) | Alt vises, og funktionerne fungerer korrekt. |
| **Linux** |
| Firefox (nyeste og tidligere versioner) | Alt vises, og funktionerne fungerer korrekt. |
| **iOS til mobilenheder** |
| Apple Safari iPad (tidligere Safari-version) | Alt vises, og funktionerne fungerer korrekt. |
| Chrome iPad (nyeste Safari-version) | Alt vises, og funktionerne fungerer korrekt. |
| **Android til mobilenheder** |
| Chrome (nyeste og tidligere versioner) | Alt vises, og funktionerne fungerer korrekt. |

## <a name="desktop-testing"></a>Desktoptest

Test din visualisering i den aktuelle version af [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/).

| Testsag | Forventet resultat
| --------- | ----------------
| Test alle funktioner i visualiseringen. | Alt vises, og funktionerne fungerer korrekt. |
| Importér, gem, åbn en fil og publicer den i Power BI-webtjenesten ved hjælp af knappen **Publicer** i Power BI Desktop. | Alt vises, og funktionerne fungerer korrekt. |
| Skift den numeriske formatstreng, så den har nul decimaler eller tre decimaler ved at øge eller mindske præcisionen. | Visualiseringen vises korrekt. |

## <a name="performance-testing"></a>Test af ydeevne

Din visualisering skal have en ydeevne, der har et acceptabelt niveau. Brug udviklerværktøjer til at validere ydeevnen. Du bør ikke kun nøjes med at bruge visuelle tips og logtidspunkter i konsollen.

| Testsag | Forventet resultat
| --------- | ----------------
| Opret en visualisering med mange visuelle elementer. | Visualiseringen skal fungere godt, og programmet må ikke fryse. Der må ikke være problemer med ydeevnen i forhold til elementer, f.eks. animationshastighed, tilpasning af størrelse, filtrering og valg.

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger om udgivelsesprocessen under [Publicer Power BI-visualiseringer til Partnercenter](./office-store.md).

Har du flere spørgsmål? [Spørg Power BI-community'et](https://community.powerbi.com/).
