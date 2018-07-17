---
title: Opret forbindelse til Office365Mon med Power BI
description: Office365Mon til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 16c8aba0d33fe9464aa55bfd55564babe282876c
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2018
ms.locfileid: "37135737"
---
# <a name="connect-to-office365mon-with-power-bi"></a>Opret forbindelse til Office365Mon med Power BI
Du kan nemt analysere nedetid i Office 365 og ydeevnedata med Power BI og Office365Mon-indholdspakken. Power BI henter dine data, herunder om nedetid og fra tilstandsundersøgelser, og opretter derefter et færdigt dashboard og rapporter ud fra de pågældende data.

Opret forbindelse til [Office365Mon-indholdspakken](https://app.powerbi.com/groups/me/getdata/services/office365mon) til Power BI.

>[!NOTE]
>Det er nødvendigt med en Office365Mon-administratorkonto for at oprette forbindelse til og indlæse Power BI-indholdspakken.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-office365mon/pbi_getdata.png)
2. I feltet **Tjenester** skal du vælge **Hent**.
   
   ![](media/service-connect-to-office365mon/pbi_getservices.png) 
3. Vælg **Office365Mon** \> **Hent**.
   
   ![](media/service-connect-to-office365mon/o365mon.png)
4. Som godkendelsesmetode skal du vælge **oAuth2** \> **Log på**.
   
   Når du bliver spurgt, skal du angive dine legitimationsoplysninger til din Office365Mon-administratorkonto og følge godkendelsesprocessen.
   
   ![](media/service-connect-to-office365mon/creds.png)
   
   ![](media/service-connect-to-office365mon/creds2.png)
5. Når du importerer data i Power BI, får du vist et nyt dashboard og datasæt samt en ny rapport i venstre navigationsrude. Nye elementer er markeret med en gul stjerne \*, vælg posten Office365Mon.
   
   ![](media/service-connect-to-office365mon/dashboard4.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved brug af **Opdater nu**

## <a name="troubleshooting"></a>Fejlfinding
Hvis du får fejlmeddelelsen **"Kunne ikke logge på"**, når du har brugt dine legitimationsoplysninger til Office365Mon-abonnementet for at logge på, skyldes det, at den konto, du bruger, ikke har tilladelse til at hente Office365Mon-data fra din konto. Kontrollér, at det er en administratorkonto, og prøv igen.

## <a name="next-steps"></a>Næste trin
[Hvad er Power BI?](power-bi-overview.md)

[Hent data til Power BI](service-get-data.md)

