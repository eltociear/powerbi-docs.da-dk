---
title: Oversigt over Power BI-filterruden
description: Oversigt over filterruden for rapporter i Power BI-tjenesten og Power BI Dashboard
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/22/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 83aed39c8a652ed5b38c18b67f1cdccfc7884240
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Få en præsentation af ruden Rapportfiltre
Denne artikel ser nærmere på ruden Rapportfiltre. Du får vist ruden i [redigeringsvisning og læsevisning i Power BI-tjenesten](service-reading-view-and-editing-view.md) og i [rapportvisning i Power BI Desktop](desktop-report-view.md).

Der er mange forskellige måder at filtrere data på i Power BI, og vi anbefaler, at du først læser [Om filtre og fremhævning](power-bi-reports-filters-and-highlighting.md).

## <a name="working-with-filters"></a>Arbejde med filtre
Rapporter kan åbnes i [Redigeringsvisning eller Læsevisning](service-reading-view-and-editing-view.md). I Redigeringsvisning, kan rapportejere [føje filtre til en rapport](power-bi-report-add-filter.md), og disse filtre gemmes sammen med rapporten. Personer, der får vist rapporten i Læsevisning, kan arbejde med filtrene, men de kan ikke gemme filterændringer i rapporten.

## <a name="filters-in-reading-view"></a>Filtre i Læsevisning
Når en rapport er åbnet i læsevisning, vises filterruden i højre side af rapportcanvassen. Hvis du ikke kan se ruden, skal du vælge pilen i øverste højre hjørne for at udvide den.

I dette eksempel har vi valgt en visualisering, der indeholder seks filtre. Der er også filtre på rapportsiden. De er angivet under overskriften **Filtre på sideniveau**. Der er ét [detaljeadgangsfilter](power-bi-report-add-filter.md), og et filter for hele rapporten: **FiscalYear** is 2013 or 2014.

![](media/power-bi-how-to-report-filter/power-bi-filter-list.png)

Ordet **Alle** er vist ud for nogle af filtrene, og det betyder, at alle værdier er inkluderet i filteret.  **Chain(All)** på skærmbilledet nedenfor viser f.eks., at denne rapportside inkluderer data om alle store kæder.  På den anden side viser rapportfilteret **FiscalYear is 2013 or 2014**, at rapporten kun indeholder data for regnskabsårene 2013 og 2014.

Alle, der får vist denne rapport, kan arbejde med disse filtre.

* få vist oplysninger om filteret ved at holde musen henover og vælge pilen ud for filteret.
  
   ![](media/power-bi-how-to-report-filter/power-bi-expan-filter.png)
* skift filteret. Du kan f.eks. ændre **Lindseys** til **Fashions Direct**.
  
     ![](media/power-bi-how-to-report-filter/power-bi-filter-chain.png)
* slet filteret ved at markere **x** ud for filternavnet.
  
  Sletning af et filter, fjerner det fra listen, men det sletter ikke dataene i rapporten.  Hvis du f.eks. sletter filteret **FiscalYear is 2013 or 2014**, forekommer dataene for regnskabsårene stadig i rapporten, men de filtreres ikke længere til kun at vise 2013 og 2014. De viser alle de regnskabsår, som dataene indeholder.  Når du sletter filteret, kan du dog ikke redigere det igen, da det er fjernet fra listen. Det er bedre at rydde filteret ved at vælge viskelæderikonet ![](media/power-bi-how-to-report-filter/power-bi-eraser-icon.png).
  
  ![](media/power-bi-how-to-report-filter/power-bi-delete-filter.png)

## <a name="filters-in-editing-view"></a>Filtre i Redigeringsvisning
Når en rapport er åbnet i Læsevisning, vises ruden Filtre i højre side af rapportcanvassen i den nederste halvdel af **ruden Visualisering**. Hvis du ikke kan se ruden, skal du vælge pilen i øverste højre hjørne for at udvide den.

![](media/power-bi-how-to-report-filter/power-bi-all-filters.png).  

Hvis der ikke er valgt en visualisering i canvassen, er det kun de filtre, der gælder for hele rapportsiden, hele rapporten samt eventuelle detaljeadgangsfiltre (hvis der er angivet nogen), der vises i ruden Filtre. I nedenstående eksempel er der ikke valgt en visualisering, og der er ingen filtre på sideniveau eller detaljeadgangsniveau, men der er et filter på rapportniveau.  

![](media/power-bi-how-to-report-filter/power-bi-no-visual.png)  

Hvis der vælges en visualisering på canvassen, får du også vist de filtre, der kun gælder for denne visualisering:   

![](media/power-bi-how-to-report-filter/power-bi-visual-filters.png)

Hvis du vil have vist indstillingerne for et bestemt filter, skal du vælge pil ned ud for filternavnet.  I eksemplet nedenfor er filteret på rapportniveauet angivet til 2013 og 2014. Og dette er et eksempel på **grundlæggende filtrering**.  Hvis du vil have vist de avancerede indstillinger, skal du vælge **Avanceret filtrering**.

![](media/power-bi-how-to-report-filter/pbi_filterlistdropdown.jpg)

## <a name="clear-a-filter"></a>Ryd et filter
 Vælg viskelæderikonet ![](media/power-bi-how-to-report-filter/pbi_erasericon.jpg) i enten den avancerede eller grundlæggende filtreringstilstand for at nulstille filteret. 

## <a name="add-a-filter"></a>Tilføj et filter
* I redigeringsvisning skal du føje et filter til en visualisering, side, detaljeadgang eller rapport ved at vælge et felt på ruden Felter og trække det til den ønskede filterbrønd, hvor du kan se teksten **Træk felter hertil**. Når et felt er blevet tilføjet som et filter, kan du finjustere det vha. kontrolelementerne til grundlæggende og avanceret filtrering (beskrevet nedenfor).

- **Hvis du trækker et nyt felt til filtreringsområdet på visualiseringsniveau**, føjes feltet ikke til visualiseringen, men du kan filtrere visualiseringen med det nye felt. I nedenstående eksempel føjes **Kæde** til visualiseringen som et nyt filter. Bemærk, at hvis du bare tilføjer **Kæde** som et filter, ændres visualiseringen ikke, før du anvender kontrolelementerne til grundlæggende eller avanceret filtrering.

    ![](media/power-bi-how-to-report-filter/power-bi-visual-filter.gif)

* Alle de felter, der bruges til at oprette en visualisering, findes også som filtre. Du skal først vælge en visualisering for at aktivere den. De felter, der bruges i visualiseringen, angives i ruden Visualiseringer (hvis du er i Redigeringsvisning) og i ruden Filtre under overskriften **Filtre på visualiseringsniveau**.
  
   ![](media/power-bi-how-to-report-filter/power-bi-visual-filter.png)  
  
   Du kan finjustere et af disse felter vha. kontrolelementerne til grundlæggende og avanceret filtrering (beskrevet nedenfor).

## <a name="types-of-filters-text-field-filters"></a>Filtertyper: filtre for tekstfelter
### <a name="list-mode"></a>Listetilstand
Når du markerer et afkrydsningsfelt, vælger eller fravælger du værdien. Afkrydsningsfeltet **Alle** kan bruges til at slå tilstanden for alle afkrydsningsfelterne til eller fra. Afkrydsningsfelterne repræsenterer alle de værdier, der er tilgængelige for det pågældende felt.  Når du justerer filteret, opdateres afstemningen, så den afspejler dine valg. 

![](media/power-bi-how-to-report-filter/pbi_restatement.png)

Bemærk, hvordan der nu står "is Amarilla or Carretera" for afstemningen

### <a name="advanced-mode"></a>Avanceret tilstand
Vælg **Avanceret filtrering** for at skifte til avanceret tilstand. Brug kontrolelementerne på rullelisten og tekstfelterne til at identificere, hvilke felter der skal inkluderes. Ved at vælge mellem **Og** og **Eller** kan du udvikle komplekse filterudtryk. Vælg knappen **Anvend filter**, når du har angivet de ønskede værdier.  

![](media/power-bi-how-to-report-filter/aboutfilters.png)

## <a name="types-of-filters-numeric-field-filters"></a>Filtertyper: filtre for numeriske felter
### <a name="list-mode"></a>Listetilstand
Hvis værdierne er begrænsede, vises der en liste, når du vælger feltnavnet.  Se under **Filtre for tekstfelter** &gt; **Listevisning** ovenfor for at få hjælp til at bruge afkrydsningsfelterne.   

### <a name="advanced-mode"></a>Avanceret tilstand
Hvis værdierne er uafgrænsede eller repræsenterer et interval, åbnes den avancerede filtertilstand, når du vælger feltnavnet. Brug rullelisten og tekstfelterne til at angive et interval af værdier, du vil have vist. 

![](media/power-bi-how-to-report-filter/pbi_dropdown-and-text.png)

Ved at vælge mellem **Og** og **Eller** kan du udvikle komplekse filterudtryk. Vælg knappen **Anvend filter**, når du har angivet de ønskede værdier.

## <a name="types-of-filters-date-and-time"></a>Filtertyper: dato og klokkeslæt
### <a name="list-mode"></a>Listetilstand
Hvis værdierne er begrænsede, vises der en liste, når du vælger feltnavnet.  Se under **Filtre for tekstfelter** &gt; **Listevisning** ovenfor for at få hjælp til at bruge afkrydsningsfelterne.   

### <a name="advanced-mode"></a>Avanceret tilstand
Hvis feltværdierne repræsenterer en dato eller et klokkeslæt, kan du angive et start/sluttidspunkt, når du bruger filtrene Dato/Klokkeslæt.  

![](media/power-bi-how-to-report-filter/pbi_date-time-filters.png)

## <a name="next-steps"></a>Næste trin
[Filtre og fremhævning i rapporter](power-bi-reports-filters-and-highlighting.md)  
[Arbejde med filtre og fremhævning i Læsevisning for en rapport](service-reading-view-and-editing-view.md)  
[Opret filtre i Redigeringsvisning for en rapport](power-bi-report-add-filter.md)  
[Rediger, hvordan visualiseringer i rapporter krydsfiltrerer og krydsfremhæver hinanden](service-reports-visual-interactions.md)

Læs mere om [rapporter i Power BI](service-reports.md)  
[Power BI – Grundlæggende begreber](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

