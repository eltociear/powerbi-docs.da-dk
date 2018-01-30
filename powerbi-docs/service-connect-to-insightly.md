---
title: Opret forbindelse til Insightly med Power BI
description: Insightly til Power BI
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: d506b45cf2a5c41ab1a6d05edb233c214606a316
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-insightly-with-power-bi"></a>Opret forbindelse til Insightly med Power BI
Visualiser og del dine Insightly CRM-data i Power BI med Insightly-indholdspakken. Opret forbindelse til Power BI vha. din Insightly API-nøgle for at få vist og oprette rapporter og dashboards på baggrund af dine CRM-data. Med Power BI kan du analysere dine data på helt nye måder, oprette effektive grafer og diagrammer og få vist kontakter, kundeemner og organisationer på et kort.

Opret forbindelse til [Insightly-indholdspakken](https://app.powerbi.com/getdata/services/insightly) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-insightly/getdata.png)
2. I feltet **Tjenester** skal du vælge **Hent**.
   
   ![](media/service-connect-to-insightly/services.png)
3. Vælg **Insightly** \>  **Hent**.
   
   ![](media/service-connect-to-insightly/insightly.png)
4. Vælg **Nøgle** som godkendelsestype, og angiv din Insight-API-nøgle, og vælg derefter **Log på**. Se nedenstående oplysninger om, hvordan du [finder det](#FindingParams).
   
   ![](media/service-connect-to-insightly/creds.png)
5. Efter godkendelsen startes importprocessen automatisk. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
     ![](media/service-connect-to-insightly/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Indholdspakken indeholder følgende tabeller med felter fra de tilsvarende poster:

| Tabeller |  |  |  |
| --- | --- | --- | --- |
| Kontakter |Salgsmuligheder |Pipelinestadier |Fuldførelsesdato for opgave |
| Brugerdefinerede felter |Lukkedato for salgsmuligheder |Fuldførelsesdato for projekt |Opgaver |
| Hændelser |Prognosedato for salgsmuligheder |Projekter |Teams/medlemmer |
| Kundeemner |Organisationer |Mærker |Brugere |

Mange tabeller og rapporter inkluderer også entydige beregnede felter, f.eks.:  

* Tabeller med "grupperede" prognoselukkedatoer for salgsmuligheder, faktiske lukkedatoer for salgsmuligehder, fuldførelsesdatoer for projekter og fuldførelsesdatoer for opgaver, der kan analyseres efter måned, kvartal eller år.  
* Et vægtet værdifelt for salgsmuligheder (værdi for salgsmulighed * sandsynlighed for at vinde).  
* Felter med gennemsnit og samlet varighed for opgaver baseret på start- og fuldførelsesdatoer.  
* Rapporter med beregnede felter for vindingsfrekvens for salgsmuligheder (antal vundne/antal samlede salgsmuligheder) og værdi for vindingsfrekvens (værdien af vinding/værdien af samlede salgsmuligheder).  

## <a name="system-requirements"></a>Systemkrav
Der kræves en Insightly-konto med adgang til Insightly-API'en. Synlighedstilladelser baseres på den API-nøgle, der bruges til at oprette forbindelse til Power BI. Alle Insightly-poster, der er synlige for dig, vil også være synlige i Power BI-rapporter og på dashboards, som du deler med andre.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Søgning efter parametre
**API-nøgle**

Hvis du vil kopiere din API-nøgle fra Insightly, skal du vælge Brugerindstillinger i Insightly-profilmenuen og rulle ned. Denne tegnstreng bruges til at oprette forbindelse mellem dine data og Power BI.

![](media/service-connect-to-insightly/findapi.png)

## <a name="troubleshooting"></a>Fejlfinding
Dine data importeres via Insightly-API'en, som indeholder en daglig grænse, der er baseret på planniveauet for dit Insightly-abonnement. Grænserne er angivet i sektionen om frekvensgrænser/begrænsningsanmodninger i vores API-dokumentation: https://api.insight.ly/v2.2/Help#!/Overview/Introduction#ratelimit

De angivne rapporter bruger standardfelter fra Insightly og indeholder muligvis ikke din tilpasninger. Rediger rapporten for at få vist alle de tilgængelige felter.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)
