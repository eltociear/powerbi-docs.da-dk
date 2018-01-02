---
title: "Indlejring af rapport ved hjælp af en iFrame"
description: "Installationen af selve Power BI-rapportserver er meget hurtig. Download, installation og konfiguration er hurtigt overstået, og du kan få det hele op at køre på få minutter."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/09/2017
ms.author: asaxton
ms.openlocfilehash: df22a7ed0772979d164a9afae18f4931310ec4a1
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>Hurtigstart: Integrer en Power BI-rapport ved hjælp af en iFrame og URL-parametre

Du kan integrere en hvilken som helst rapport ved hjælp af en iFrame i dit program. 

## <a name="url-parameter"></a>URL-parameter

For en hvilken som helst URL-adresse til en rapport kan du tilføje forespørgselsstrengparameteren `?rs:Embed=true`.

Eksempel:

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

Dette fungerer på alle rapporttyper i Power BI-rapportserver.

## <a name="iframe"></a>iFrame

Når du har din URL-adresse, kan du oprette en iFrame inden for en webside som vært for rapporten.

Eksempel:

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>URL-filter

Du kan føje en forespørgselsstrengparameter til URL-adressen for at filtrere de data, der returneres i Power BI-rapporten.

Syntaksen er enkel. Start med URL-adressen til rapporten, tilføj et spørgsmålstegn og derefter denne filtersyntaks.

URL?filter=***Tabel***/***Felt*** eq '***værdi***'

Vær opmærksom på følgende:

- I navnene for **Tabel** og **Felt** skelnes der mellem store og små bogstaver, men ikke i **værdi**.
- Du kan filtrere en rapport med felter, der er skjult fra rapportvisningen.
- **Værdi** skal omgives af enkelte anførselstegn.
- Felttypen skal være en streng.
- Tabel- og feltnavne må ikke indeholde mellemrum.

###  <a name="example-filter-on-a-field"></a>Eksempel: Filtrer på et felt

Tag f.eks. [Retail Analysis Sample](../sample-datasets.md) (Eksempel på detailhandelsanalyse). Lad os antage, at dette er URL-adressen til rapporten på rapportserveren i en mappe med navnet "power-bi":

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

Du kan se, at kortvisualiseringen i Retail Analysis Sample viser butikker i North Carolina og andre stater.

![Kortvisualisering af Retail Analysis Sample](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

*NC* er værdien for North Carolina, som er lagret i feltet **Territory** (Område) i tabellen **Store** (Butik). Så hvis du vil filtrere rapporten for kun at få vist data for butikker i North Carolina, skal du tilføje følgende i URL-adressen:

?filter=Store/Territory eq 'NC'

Nu er rapporten filtreret for North Carolina, så alle visualiseringer på rapportsiden viser kun data for North Carolina.

![Filtreret visualisering for Retail Analysis Sample](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>Opret en DAX-formel for at filtrere på flere værdier

En anden metode til at filtrere på flere felter er at oprette en beregnet kolonne i Power BI Desktop, som sammenkæder to felter med en enkelt værdi. Derefter kan du filtrere på denne værdi.

For eksempel har Retail Analysis Sample to felter: Territory (Område) og Chain (Kæde). I Power BI Desktop kan du [oprette en beregnet kolonne](../desktop-tutorial-create-calculated-columns.md) (felt) med navnet TerritoryChain. Husk, at navnet på **Felt** ikke må indeholde mellemrum. Her er DAX-formlen for den pågældende kolonne.

TerritoryChain = [Territory] & "-" & [Chain]

Publicer rapporten på Power BI-rapportserver, og brug derefter URL-forespørgselsstrengen til at filtrere for kun at vise data for Lindseys-butikker i NC.

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>Næste trin

[Hurtigstart: Opret en Power BI-rapport til Power BI-rapportserver](quickstart-create-powerbi-report.md)  
[Hurtigstart: Opret en sideinddelt rapport for Power BI-rapportserver](quickstart-create-paginated-report.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)