---
title: Tilføj Power BI-rapportparametre ved hjælp af URL-adressen
description: Filtrer en rapport ved hjælp af parametre for forespørgselsstrengen til URL-adressen, du kan endda filtrere på mere end ét felt.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: aeaea6d14cf8f4fd62fbbf5098e68429fe40b96a
ms.sourcegitcommit: 2b9ef93bbff5c741ba55ea0502f642632683d593
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/24/2018
---
# <a name="filter-a-report-using-query-string-parameters-in-the-url"></a>Filtrer en rapport ved hjælp af parametre for forespørgselsstrengen i URL-adressen
Når du åbner en rapport i Power BI-tjenesten, har hver side i rapporten sin egen entydige URL-adresse. Hvis du vil filtrere denne rapportside, kan du bruge ruden Filtre på rapportcanvasset.  Eller du kan føje parametre for forespørgselsstrengen til URL-adressen for at filtrere rapporten. Du har måske en rapport, du vil vise til kollegaer, og du vil filtrere den på forhånd for dem. Det kan du f.eks. gøre ved at starte med URL-standardadressen til rapporten, føje filterparametrene til URL-adressen og derefter sende dem hele URL-adressen via mail.

![Power BI-rapport i tjenesten](media/service-url-filters/power-bi-report2.png)

<iframe width="640" height="360" src="https://www.youtube.com/embed/WQFtN8nvM4A?list=PLv2BtOtLblH3YE_Ycas5B1GtcoFfJXavO&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="query-string-parameter-syntax-for-filtering"></a>Syntaks til parametre for forespørgselsstreng til filtrering
Syntaksen er forholdsvis enkel. Start med URL-adressen til rapporten, tilføj et spørgsmålstegn, og tilføj derefter din filtersyntaks.

URL?filter=***Tabel***/***Felt*** eq '***værdi***'

![URL-adresse med filter](media/service-url-filters/power-bi-filter-urls7b.png)

* I navnene for **Tabel** og **Felt** skelnes der mellem store og små bogstaver, men ikke i **værdi**.
* Felter, der er skjult i rapportvisningen, kan stadig filtreres.
* **Værdi** skal omgives af enkelte anførselstegn.
* Felttypen skal være et tal eller en streng
* Tabel- og feltnavne må ikke indeholde mellemrum.

Hvis det stadig er forvirrende, kan du fortsætte med at læse og vi undersøger det nærmere.  

## <a name="filter-on-a-field"></a>Filtrer på et felt
Lad os antage, at URL-adressen til rapporten er følgende.

![Starter URL-adresse](media/service-url-filters/power-bi-filter-urls6.png)

Og vi kan se i vores kortvisualisering (ovenfor), at vi har butikker i North Carolina.

>[!NOTE]
>Dette eksempel er baseret på [eksemplet på detailhandelsanalyse](sample-datasets.md).
> 

Hvis du vil filtrere rapporten, så der kun vises data for butikker i "NC" (North Carolina), skal du tilføje følgende i URL-adressen:

?filter=Store/Territory eq 'NC'

![URL-adresse med filter](media/service-url-filters/power-bi-filter-urls7.png)

>[!NOTE]
>*NC* er en værdi, som er lagret i feltet **Territory** i tabellen **Store**.
> 
> 

Nu er rapporten filtreret for North Carolina, så alle visualiseringer på rapportsiden viser kun data for North Carolina.

![](media/service-url-filters/power-bi-report4.png)

## <a name="filter-on-multiple-fields"></a>Filtrer på flere felter
Du kan også filtrere på flere felter ved at føje yderligere parametre til din URL-adresse. Lad os gå tilbage til vores oprindelige filterparameter.

```
?filter=Store/Territory eq 'NC'
```

Hvis du vil filtrere på flere felter, skal du tilføje en `and` og et andet felt i samme format som ovenfor. Her er et eksempel.

```
?filter=Store/Territory eq 'NC' and Store/Chain eq 'Fashions Direct'
```

<iframe width="640" height="360" src="https://www.youtube.com/embed/0sDGKxOaC8w?showinfo=0" frameborder="0" allowfullscreen></iframe>


### <a name="using-dax-to-filter-on-multiple-values"></a>Brug DAX til at filtrere på flere værdier
En anden metode til at filtrere på flere felter er at oprette en beregnet kolonne, som sammenkæder to felter til en enkelt værdi. Derefter kan du filtrere på denne værdi.

Vi har f.eks. to felter: Territory og Chain. [Opret en ny beregnet kolonne](desktop-tutorial-create-calculated-columns.md) (felt) med navnet TerritoryChain i Power BI Desktop. Husk, at navnet på **Felt** ikke må indeholde mellemrum. Her er DAX-formlen for den pågældende kolonne.

TerritoryChain = [Territory] & " - " & [Chain]

Publicer rapporten på Power BI-tjenesten, og brug derefter URL-forespørgselsstrengen til at filtrere og kun vise data for Lindseys-butikker i NC.

    https://app.powerbi.com/groups/me/reports/8d6e300b-696f-498e-b611-41ae03366851/ReportSection3?filter=Store/TerritoryChain eq 'NC–Lindseys'

## <a name="pin-a-tile-from-a-filtered-report"></a>Fastgør et felt fra en filtreret rapport
Når du har filtreret rapporten ved hjælp af parametre for forespørgselsstrengen, kan du kan fastgøre visualiseringer fra denne rapport til dit dashboard. Feltet på dashboardet viser de filtrerede data, og når dette dashboardfelt vælges, åbnes den rapport, der blev brugt til at oprette det.  Men filtreringen, du foretog ved hjælp af URL-adressen, gemmes ikke med rapporten, og når dashboardfeltet vælges, åbnes rapporten i ufiltreret tilstand.  Det betyder, at de data, der vises i dashboardfeltet, ikke svarer til de data, der vises i rapportvisualiseringen.

Der kan være nogle tilfælde, hvor dette er nyttigt, når du vil se forskellige resultater: filtreret på dashboardet og ufiltreret i rapporten.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
Der er et par ting, du skal være opmærksom på, når du bruger parametre for forespørgselsstrengen.

* På Power BI-rapportserveren kan du [sende rapportparametre](https://docs.microsoft.com/sql/reporting-services/pass-a-report-parameter-within-a-url?view=sql-server-2017.md) ved at inkludere dem i en URL-adresse til rapporten. Disse parametre i URL-adressen har ikke noget præfiks, da de sendes direkte til det program, der behandler rapporten. 
* Filtrering af forespørgselsstrengen fungerer ikke sammen med [Publicer på internettet](service-publish-to-web.md) eller Power BI Embedded.   
* Felttypen skal være et tal eller en streng.
* Tabel- og feltnavne må ikke indeholde mellemrum.

## <a name="next-steps"></a>Næste trin
[Fastgør en visualisering til et dashboard](service-dashboard-pin-tile-from-report.md)  
[Prøv det – det er gratis!](https://powerbi.com/)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

