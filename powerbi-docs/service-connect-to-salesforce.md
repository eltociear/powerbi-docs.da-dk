---
title: Opret forbindelse til Salesforce med Power BI
description: Salesforce til Power BI
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
ms.openlocfilehash: 6998f273a7e40cae2c7a50f043f79eec540b4789
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-salesforce-with-power-bi"></a>Opret forbindelse til Salesforce med Power BI
Med Power BI kan du kan nemt oprette forbindelse til din konto på Salesforce.com. Når du opretter denne forbindelse, hentes dine data, du får automatisk et dashboard og rapporter baseret på dine data.

Opret forbindelse til [Salesforce-indholdspakken](https://app.powerbi.com/getdata/services/salesforce) til Power BI, eller læs mere om [Salesforce-integration](https://powerbi.microsoft.com/integrations/salesforce) med Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. Klik på **Salesforce**, og vælg **Hent**.  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. Vælg **Log på** for at starte logonflowet.
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. Angiv dine Salesforce-legitimationsoplysninger, når du bliver bedt om det. Klik på **Tillad**, så Power BI kan få adgang til dine grundlæggende Salesforce-oplysninger og -data.
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. Konfigurer, hvad du vil importere til Power BI, ved hjælp af rullelisteindstillingen:
   
   * **Dashboard**
     
     Vælg et foruddefineret dashboard, der er baseret på en karakter (f.eks. **Salgschef**). Disse dashboards henter bestemte sæt af standarddata fra Salesforce og medtager ikke brugerdefinerede felter.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **Rapporter**
     
     Vælg en eller flere brugerdefinerede rapporter fra din Salesforce-konto. Disse rapporter stemmer overens med dine visninger i Salesforce og kan indeholde data fra brugerdefinerede felter eller objekter.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     Hvis du ikke kan se nogen rapporter, kan du tilføje eller oprette dem i din Salesforce-konto og prøve at oprette forbindelse igen.
7. Klik på **Tilslut** for at starte importprocessen. Under importen får du vist en meddelelse om, at importen er i gang. Når importen er fuldført, får du vist et dashboard, en rapport og et datasæt for dine Salesforce-data, som er angivet i navigationsruden til venstre.
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

Du kan ændre dette dashboard for at få vist dine data, som du ønsker. Du kan stille spørgsmål i sektionen med spørgsmål og svar – eller klikke på et felt for at [åbne den underliggende rapport](service-dashboard-tiles.md) og [ændre felterne](service-dashboard-edit-tile.md) i dashboardet.

**Hvad nu?**

* Prøv at [stille et spørgsmål i feltet Spørgsmål og svar](service-q-and-a.md) øverst i dashboardet
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboardet
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport
* Dit datasæt vil være programsat til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="system-requirements"></a>Systemkrav
* Forbindelse til en Salesforce-produktionskonto, der har adgang til API aktiveret
* Tilladelse tildelt til Power BI-appen under logon
* Kontoen har tilstrækkelige API-kald til at trække og opdatere dataene
* Der kræves et gyldigt godkendelsestoken for at opdatere. Sørg for, at du har importeret fem eller færre Salesforce-datasæt, da Salesforce har en begrænsning på fem godkendelsestokens pr. program

## <a name="troubleshooting"></a>Fejlfinding
Hvis der opstår fejl, skal du gennemse ovenstående krav. Bemærk også, at muligheden for at logge på et brugerdefineret domæne eller et sandkassedomæne ikke understøttes i øjeblikket.

## <a name="next-steps"></a>Næste trin
[Introduktion til Power BI](service-get-started.md)

[Hent data](service-get-data.md)
