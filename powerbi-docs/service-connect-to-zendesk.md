---
title: Opret forbindelse til Zendesk med Power BI
description: Zendesk til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: afcaae9499aa1c7e1461030cfa6b5d7b35a47188
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2018
ms.locfileid: "37136013"
---
# <a name="connect-to-zendesk-with-power-bi"></a>Opret forbindelse til Zendesk med Power BI
Zendesk-indholdspakken indeholder et Power BI-dashboard og et sæt Power BI-rapporter, der giver indsigt i dine billetvolumener og agentydeevne. Du kan bruge dashboardet og rapporterne, som følger med, eller tilpasse dem for at fremhæve de oplysninger, som betyder mest for dig.  Dataene opdateres automatisk én gang dagligt. 

Opret forbindelse til [Zendesk-indholdspakken](https://app.powerbi.com/getdata/services/zendesk), eller læs mere om [Zendesk-integrationen](https://powerbi.microsoft.com/integrations/zendesk) med Power BI.

>[!NOTE]
>Der kræves en Zendesk-administratorkonto for at oprette forbindelse. Flere oplysninger om [kravene](#Requirements) nedenfor.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-zendesk/pbi_getdata.png)
2. I feltet **Tjenester** skal du vælge **Hent**.
   
   ![](media/service-connect-to-zendesk/pbi_getservices.png) 
3. Vælg **Zendesk** \> **Hent.**
   
   ![](media/service-connect-to-zendesk/zendesk.png)
4. Angiv den URL-adresse, som er knyttet til din konto. Den skal være i formatet **https://company.zendesk.com**. Du kan se oplysninger om, hvordan du [finder disse parametre](#FindingParams), nedenfor.
   
   ![](media/service-connect-to-zendesk/pbi_zendeskconnect.png)
5. Angiv dine Zendesk-legitimationsoplysninger, når du bliver bedt om dem.  Vælg **oAuth 2** som Godkendelsesmetode, og klik på **Log på**. Følg Zendesk-godkendelsesprocessen. (Hvis du er allerede er logget på Zendesk i din browser, bliver du muligvis ikke bedt om legitimationsoplysninger).
   
   > [!NOTE]
   > Denne indholdspakke kræver, at du opretter forbindelse med en Zendesk-administratorkonto. 
   > 
   > 
   
   ![](media/service-connect-to-zendesk/pbi_zendesksignin.png)
6. Klik på **Tillad** for at tillade, at Power BI får adgang til dine Zendesk-data.
   
   ![](media/service-connect-to-zendesk/zendesk2.jpg)
7. Klik på **Opret forbindelse** for at starte importprocessen. Når Power BI har importeret dataene, vises der et nyt dashboard, en ny rapport og et nyt datasæt i venstre navigationsrude. Nye elementer er markeret med en gul stjerne \*.
   
   ![](media/service-connect-to-zendesk/pbi_zendeskdash.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Følgende er inkluderet
Power BI-indholdspakken indeholder data om følgende:  

* Brugere (slutbrugere og agenter)  
* Organisationer  
* Grupper  
* Billetter  

Der er også et sæt af målinger, der er blevet beregnet, f.eks. gennemsnitlig ventetid og billetter løst inden for de seneste 7 dage. En komplet liste følger med indholdspakken.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Systemkrav
Der kræves en Zendesk-administratorkonto for at få adgang til Zendesk-indholdspakken. Hvis du er agent eller slutbruger og er interesseret i at få vist dine Zendesk-data, kan du tilføje et forslag og gennemgå Zendesk-connectoren i [Power BI Desktop](desktop-connect-to-data.md).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Søg efter parametre
URL-adressen til Zendesk skal være den samme som den URL-adresse, du bruger til at logge på din Zendesk-konto. Hvis du ikke er sikker på din Zendesk URL-adresse, kan du bruge [hjælp til logon](https://www.zendesk.com/login/) i Zendesk.

## <a name="troubleshooting"></a>Fejlfinding
Hvis du har problemer med at oprette forbindelse, skal du kontrollere din Zendesk URL-adresse og bekræfte, at du bruger en Zendesk-administratorkonto.

## <a name="next-steps"></a>Næste trin
* [Hvad er Power BI?](power-bi-overview.md)
* [Hent data](service-get-data.md)

