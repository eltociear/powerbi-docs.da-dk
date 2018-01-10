---
title: "Fastgør et felt til et dashboard fra Spørgsmål og svar"
description: "Dokumentation i at fastgøre et felt til et Power BI-dashboard fra spørgsmålsfeltet Spørgsmål og svar"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 12/20/2017
ms.author: mihart
ms.openlocfilehash: 8a876c5a05fcdadff1a874148f5d56465bcc8c62
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/21/2017
---
# <a name="pin-a-tile-to-a-dashboard-from-qa"></a>Fastgør et felt til et dashboard fra Spørgsmål og svar
## <a name="how-to-pin-a-tile-from-qa"></a>Sådan fastgør du et felt fra Spørgsmål og svar
Spørgsmål og svar er Power BI's ad hoc-rapporteringsværktøj. Brug for at finde en bestemt indsigt? Stil et spørgsmål om dine data, og få svar i form af en visualisering.

Spørgsmål og svar er tilgængelig fra dashboards og rapporter. I denne artikel åbner vi Spørgsmål og svar fra et dashboard. Dashboards er tilgængelige i Power BI-tjenesten, men ikke i Power BI Desktop. Åbn [dashboardet Retail Analysis Sample](sample-retail-analysis.md) (Eksempel på detailhandelsanalyse) for at følge med.
> 
> 

1. Åbn et [dashboard](service-dashboards.md) med mindst ét felt fastgjort fra en rapport. Når du stiller et spørgsmål, leder Power BI efter svaret i de datasæt, hvor et felt er fastgjort til dette dashboard.  Du kan få flere oplysninger i [Hent data](service-get-data.md).
2. I spørgsmålsfeltet øverst i dit dashboard skal du begynde at indtaste, hvad du vil vide om dine data.  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-question-box.png)
3. Mens du f.eks. skriver "last year sales by month and territory"...  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-type-q-and-a.png)
   
   giver spørgsmålsfeltet dig forslag.
4. Hvis du vil føje diagrammet til dit dashboard som et felt, skal du vælge nålen ![](media/service-dashboard-pin-tile-from-q-and-a/pbi_pintile.png) øverst til højre på canvasset.
5. Fastgør feltet til et eksisterende dashboard eller til et nyt dashboard. 

   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin-to-dashboard.png)

   * Eksisterende dashboard: Vælg navnet på dashboardet på rullelisten. Du vil kun kunne vælge blandt de dashboards, der findes i det aktuelle arbejdsområde.
   * Nyt dashboard: Skriv navnet på det nye dashboard, og det vil blive føjet til dit aktuelle arbejdsområde.
6. Vælg **Fastgør**.
   
   En meddelelse om fuldførelse (næsten helt oppe i højre hjørne) giver dig besked om, at visualiseringen er blevet føjet til dit dashboard som et felt.  
   
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin.png)
7. Vælg **Gå til dashboard** for at se det nye felt. Der kan du [omdøbe, tilpasse størrelsen på, tilføje et hyperlink for og flytte feltet og meget mere](service-dashboard-edit-tile.md) på dit dashboard. 
   
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
* Når du begynder at indtaste et spørgsmål, begynder Spørgsmål og svar straks at søge efter det bedste svar fra alle de datasæt, der er knyttet til det aktuelle dashboard.  Det "aktuelle dashboard" er det dashboard, der er angivet på den øverste navigationslinje. For eksempel er dette spørgsmål blevet stillet i dashboardet **Retail Analysis Sample**, der er en del af **mihart**-apparbejdsområdet.
  
  ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-navbar.png)
* **Hvordan ved Spørgsmål og svar, hvilke datasæt der skal bruges**?  Spørgsmål og svar har adgang til alle datasæt, der har visualiseringer fastgjort til dette dashboard.

## <a name="next-steps"></a>Næste trin
[Omdøb, tilpas størrelse, tilføj et hyperlink, flyt feltet og meget mere](service-dashboard-edit-tile.md)    
[Få vist dit dashboardfelt i fokustilstand](service-focus-mode.md)     
[Tilbage til Spørgsmål og svar i Power BI](service-q-and-a.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

