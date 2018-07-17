---
title: Opret forbindelse til QuickBooks Online med Power BI
description: QuickBooks Online til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b4cd8974316119978749db4f3996db76d907ab38
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2018
ms.locfileid: "37136059"
---
# <a name="connect-to-quickbooks-online-with-power-bi"></a>Opret forbindelse til QuickBooks Online med Power BI
Når du opretter forbindelse til dine QuickBooks Online-data fra Power BI, får du straks et Power BI-dashboard og Power BI-rapporter, der giver indsigt i antallet af din virksomheds likviditet, lønsomhed, kunder m.m. Brug dashboardet og rapporterne, som de er, eller tilpas dem for at fremhæve de oplysninger, som betyder mest for dig. Dataene opdateres automatisk én gang dagligt.

Opret forbindelse til [QuickBooks Online-indholdspakken](https://dxt.powerbi.com/getdata/services/quickbooks-online) til Power BI.

>[!NOTE]
>Hvis du vil importere dine QuickBooks Online-data i Power BI, skal du være administrator på din QuickBooks Online-konto og logge på med din administratorkonto. Du kan ikke bruge denne connector til QuickBooks Desktop-softwaren. 

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-quickbooks-online/pbi_getdata.png) 
2. I feltet **Tjenester** skal du vælge **Hent**.
   
   ![](media/service-connect-to-quickbooks-online/pbi_getservices.png) 
3. Vælg **QuickBooks Online**, og vælg derefter **Hent**.
   
   ![](media/service-connect-to-quickbooks-online/qbo.png)
4. Vælg **oAuth2** som Godkendelsesmetode, og vælg derefter **Log på**. 
5. Når du bliver spurgt, skal du angive dine legitimationsoplysninger til QuickBooks Online og følge QuickBooks Online-godkendelsesprocessen. Hvis du er allerede er logget på QuickBooks Online i din browser, bliver du muligvis ikke spurgt om legitimationsoplysninger.
   >[!NOTE]
   >Du skal bruge administratorlegitimationsoplysninger til din QuickBooks Online-konto.
6. Vælg det firma, du vil forbinde til Power BI, på det næste skærmbillede.
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_almost.png)
7. Vælg **Godkend** i det næste skærmbillede for at starte importprocessen. Det kan tage et par minutter, afhængigt af størrelsen på virksomhedens data. 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_authorizesm.png)
   
   Når Power BI har importeret dataene, vises der et nyt dashboard, en ny rapport og et nyt datasæt i venstre navigationsrude. Nye elementer er markeret med en gul stjerne \*.
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_leftnavnew.png)
8. Vælg QuickBooks Online-dashboardet. Dette er dashboardet, som Power BI oprettede automatisk for at vise dine importerede data. Du kan ændre dette dashboard, så det viser data på din foretrukne måde. 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_dash.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved brug af **Opdater nu**

## <a name="troubleshooting"></a>Fejlfinding
**"Ups! Der er opstået en fejl"**

Hvis du får vist denne meddelelse, når du har valgt **Godkend**:

"Ups! Der opstod en fejl." Luk dette vindue, og prøv igen.

En anden bruger abonnerer allerede på dette program til denne virksomhed. Kontakt [administratormail] for at foretage ændringer på abonnementet."

![](media/service-connect-to-quickbooks-online/pbi_qbo_oopssm.png)

... dette betyder, at en anden administrator i din virksomhed allerede har forbindelse til dine firmadata med Power BI. Bed denne administrator om at dele dashboardet med dig. I øjeblikket kan kun én administrator oprette forbindelse et bestemt QuickBooks Online-firmadatasæt til Power BI. Når Power BI har oprettet dashboardet, kan administratoren dele det med flere kolleger på de samme Power BI-lejere.

**"Denne app er ikke konfigureret til at tillade forbindelser fra dit land"**

Power BI understøtter i øjeblikket kun amerikanske versioner af QuickBooks Online. 

![](media/service-connect-to-quickbooks-online/pbi_qbo_countrynotsupported.png)

## <a name="next-steps"></a>Næste trin
[Hvad er Power BI?](power-bi-overview.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

