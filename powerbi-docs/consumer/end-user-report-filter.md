---
title: Oversigt over Power BI-ruden Filtre for forbrugere
description: Oversigt over ruden Filtre i rapporter i Power BI-tjenesten
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 09/25/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: c49e075bd7fbe2debb0b577a1ce2771491d5fac4
ms.sourcegitcommit: 52ac456bf2ac025b22ea634c28482f22e1cc19ac
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/10/2018
ms.locfileid: "48908273"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Få en præsentation af ruden Rapportfiltre
I denne artikel ser vi nærmere på ruden Filtre i rapporter i Power BI-tjenesten.

Der er mange forskellige måder at filtrere data på i Power BI, og vi anbefaler, at du først læser [Om filtre og fremhævning](../power-bi-reports-filters-and-highlighting.md).

![rapport i browser](media/end-user-report-filter/power-bi-browser.png)

## <a name="working-with-the-report-filters-pane"></a>Arbejde med ruden Filtre i rapporter
Når en kollega deler en rapport med dig, skal du søge efter ruden **Filtre**. Nogle gange er den skjult langs højre kant af rapporten. Vælg den for at udvide den.   

![rapport i browser](media/end-user-report-filter/power-bi-expanded.png)

Ruden Filtre indeholder filtre, der er føjet til rapporten af rapport*designeren*. *Forbrugere* som dig selv, kan arbejde med filtrene og gemme deres ændringer, men de kan ikke føje nye filtre til rapporten.

I Power BI-tjenesten gemmes de ændringer, du foretager i ruden Filtre, sammen med rapporten og overføres til mobilversionen af rapporten. Du kan nulstille ruden Filtre til designerens standardindstilling ved at vælge **Nulstil til standard** på den øverste menulinje.     

## <a name="open-the-filters-pane"></a>Åbning af ruden Filtre
Når en rapport er åbnet, vises ruden Filtre i højre side af rapportcanvasset. Hvis du ikke kan se ruden, skal du vælge pilen i øverste højre hjørne for at udvide den.  

I dette eksempel har vi valgt en visualisering, der indeholder seks filtre. Der er også filtre på rapportsiden. De er angivet under overskriften **Filtre på sideniveau**. Der er ét [detaljeadgangsfilter](../power-bi-report-add-filter.md), og et filter for hele rapporten: **FiscalYear** is 2013 or 2014.

![liste over filtre](media/end-user-report-filter/power-bi-filter-list.png)

Ordet **Alle** er vist ud for nogle af filtrene, og det betyder, at alle værdier er inkluderet i filteret.  **Chain(All)** på skærmbilledet nedenfor viser f.eks., at denne rapportside inkluderer data om alle store kæder.  På den anden side viser rapportfilteret **FiscalYear is 2013 or 2014**, at rapporten kun indeholder data for regnskabsårene 2013 og 2014.

Alle, der får vist denne rapport, kan arbejde med disse filtre.

* Få vist oplysninger om filtret ved at pege på det med musen, og vælg pilen ud for filteret.
  
   ![viser Lindseys som valgt](media/end-user-report-filter/power-bi-expan-filter.png)
* Skift filtret. Du kan f.eks. ændre **Lindseys** til **Fashions Direct**.
  
     ![viser Fashions Direct som valgt](media/end-user-report-filter/power-bi-filter-chain.png)

* Nulstil filtrene til den oprindelige tilstand ved at vælge **Nulstil til standard** på den øverste menulinje.    
    ![nulstil til standard](media/end-user-report-filter/power-bi-reset-to-default.png)
    
* Slet filtret ved at vælge **x** ud for filternavnet.
  
  Sletning af et filter, fjerner det fra listen, men det sletter ikke dataene i rapporten.  Hvis du f.eks. sletter filtret **FiscalYear is 2013 or 2014**, bevares dataene for de to regnskabsår i rapporten, men rapporten filtreres ikke længere til kun at vise 2013 og 2014. Den viser alle de regnskabsår, som dataene indeholder.  Når du sletter filteret, kan du dog ikke redigere det igen, da det er fjernet fra listen. Det er bedre at fjerne filteret ved at vælge viskelæderikonet ![viskelæderikon](media/end-user-report-filter/power-bi-eraser-icon.png).
  
  ![x fremhævet](media/end-user-report-filter/power-bi-delete-filter.png)



## <a name="clear-a-filter"></a>Ryd et filter
 Vælg viskelæderikonet i den avancerede eller grundlæggende filtreringstilstand  ![viskelæderikon](media/end-user-report-filter/pbi_erasericon.jpg) for at fjerne filteret. 


## <a name="types-of-filters-text-field-filters"></a>Filtertyper: filtre for tekstfelter
### <a name="list-mode"></a>Listetilstand
Når du markerer et afkrydsningsfelt, vælger eller fravælger du værdien. Afkrydsningsfeltet **Alle** kan bruges til at slå tilstanden for alle afkrydsningsfelterne til eller fra. Afkrydsningsfelterne repræsenterer alle de værdier, der er tilgængelige for det pågældende felt.  Når du justerer filteret, opdateres afstemningen, så den afspejler dine valg. 

![filter for listetilstand](media/end-user-report-filter/pbi_restatement.png)

Bemærk, hvordan der nu står "is Amarilla or Carretera" for afstemningen

### <a name="advanced-mode"></a>Avanceret tilstand
Vælg **Avanceret filtrering** for at skifte til avanceret tilstand. Brug kontrolelementerne på rullelisten og tekstfelterne til at identificere, hvilke felter der skal inkluderes. Ved at vælge mellem **Og** og **Eller** kan du udvikle komplekse filterudtryk. Vælg knappen **Anvend filter**, når du har angivet de ønskede værdier.  

![avanceret tilstand](media/end-user-report-filter/aboutfilters.png)

## <a name="types-of-filters-numeric-field-filters"></a>Filtertyper: filtre for numeriske felter
### <a name="list-mode"></a>Listetilstand
Hvis værdierne er begrænsede, vises der en liste, når du vælger feltnavnet.  Se under **Filtre for tekstfelter** &gt; **Listevisning** ovenfor for at få hjælp til at bruge afkrydsningsfelterne.   

### <a name="advanced-mode"></a>Avanceret tilstand
Hvis værdierne er uafgrænsede eller repræsenterer et interval, åbnes den avancerede filtertilstand, når du vælger feltnavnet. Brug rullelisten og tekstfelterne til at angive et interval af værdier, du vil have vist. 

![filter for avanceret](media/end-user-report-filter/pbi_dropdown-and-text.png)

Ved at vælge mellem **Og** og **Eller** kan du udvikle komplekse filterudtryk. Vælg knappen **Anvend filter**, når du har angivet de ønskede værdier.

## <a name="types-of-filters-date-and-time"></a>Filtertyper: dato og klokkeslæt
### <a name="list-mode"></a>Listetilstand
Hvis værdierne er begrænsede, vises der en liste, når du vælger feltnavnet.  Se under **Filtre for tekstfelter** &gt; **Listevisning** ovenfor for at få hjælp til at bruge afkrydsningsfelterne.   

### <a name="advanced-mode"></a>Avanceret tilstand
Hvis feltværdierne repræsenterer en dato eller et klokkeslæt, kan du angive et start/sluttidspunkt, når du bruger filtrene Dato/Klokkeslæt.  

![dato/klokkeslæt-filter](media/end-user-report-filter/pbi_date-time-filters.png)


## <a name="next-steps"></a>Næste trin
[Få mere at vide om, hvordan og hvorfor visuals krydsfiltrerer og krydsfremhæver hinanden på en rapportside](end-user-interactions.md)