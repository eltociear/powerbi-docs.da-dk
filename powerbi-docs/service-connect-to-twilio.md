---
title: Opret forbindelse til Twilio med Power BI
description: Twilio til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: f81330ec331ae42dea994982369428e9f7eb23aa
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249430"
---
# <a name="connect-to-twilio-with-power-bi"></a>Opret forbindelse til Twilio med Power BI
Med Microsoft Twilio-indholdspakken til Power BI kan du hente data ind i Power BI, og der oprettes et [Twilio-dashboard](https://powerbi.microsoft.com/integrations/twilio) og en rapport, der viser indsigt i dine data. Du kan også oprette brugerdefinerede rapporter og dashboard på det datasæt, Power BI opretter. Dataene opdateres en gang om dagen, så du altid ser på de seneste data.

Opret forbindelse til [Twilio-indholdspakken](https://app.powerbi.com/getdata/services/twilio) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-twilio/pbi_getdata.png) 
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-twilio/pbi_getservices.png) 
3. Vælg **Twilio** \> **Hent**.
   
   ![](media/service-connect-to-twilio/twilio.png)
4. Som **Godkendelsesmetode** skal du vælge **oAuth2** \> Log på. Når du bliver bedt om det, skal du angive dine legitimationsoplysninger til Twilio og tillade, at Power BI-programmet får adgang til dine data.
   
   ![](media/service-connect-to-twilio/pbi_twilio_login.png)
5. Dette starter importen af dine data fra din Twilio-konto, og dit dashboard vil blive udfyldt med dine opkald og meddelelser inden for de seneste 30 dage. 
   
   ![](media/service-connect-to-twilio/pbi_twilio_db.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Oplysninger om alle opkald og meddelelser inden for de seneste 30 dage. Du kan udføre alle mulige analyser og samling af disse data.

En række allerede samlede statistikker, som du kan holde øje med. Dette samling omfatter:

        All Time Calls Count  
        All Time Calls Duration  
        All Time Calls Price  
        All Time Messages Price  
        All Time Messages Count  
        All Time Count of Phone Numbers  
        All Time Price of Phone Numbers  
        All Time Twilio Client Calls Price  
        All Time Twilio Client Calls Duration  
        All Time Twilio Client Calls Count  
        All Time Total Price  
        All Time Inbound Calls Price  
        All Time Inbound Calls Duration  
        All Time Inbound Calls Count  
        All Time Outbound Calls Price  
        All Time Outbound Calls Duration  
        All Time Outbound Calls Count  
        This Month Calls Price  
        This Month Calls Duration  
        This Month Calls Count  
        This Month Messages Count  
        This Month Messages Price  
        This Month Count of Phone Numbers  
        This Month Price of Phone Numbers  
        This Month Twilio Client Calls Price  
        This Month Twilio Client Calls Duration  
        This Month Twilio Client Calls Count  
        This Month Total Price  
        This Month Inbound Calls Price  
        This Month Inbound Calls Duration  
        This Month Inbound Calls Count  
        This Month Outbound Calls Price  
        This Month Outbound Calls Duration  
        This Month Outbound Calls Count  
        This Month Inbound Messages Price  
        This Month Inbound Messages Count  
        This Month Outbound Messages Price  
        This Month Outbound Messages Count

## <a name="troubleshooting"></a>Fejlfinding
Hvis du har en meget stor mængde data inden for de sidste 30 dage (hundredtusindvis af transaktioner), kan trinnet til hentning af data mislykkes. Vi har kendskab til problemet og arbejder på at udbedre det. Hvis du er stødt på dette problem, kan du bruge supportlinket øverst på Power BI-siden til at fortælle os det. Så kontakter vi dig for yderligere undersøgelser.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

