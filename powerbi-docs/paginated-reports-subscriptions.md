---
title: Abonner på sideinddelte rapporter i Power BI-tjenesten
description: I denne artikel kan lære du ting, du skal være opmærksom på angående abonnerer på sideinddelte rapporter i Power BI-tjenesten.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/24/2019
ms.openlocfilehash: ccec6658808d94728f2a4f14de67c36da0f51def
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222188"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Selv og andre Abonner sideinddelte rapporter i Power BI-tjenesten 

Du kan nu oprette mailabonnementer til dig selv og andre for sideinddelte rapporter i Power BI-tjenesten. Generelt processen er den samme som [at abonnere på rapporter og dashboards i Power BI-tjenesten](service-report-subscribe.md). I denne artikel forklares forskelle og overvejelser. 

At konfigurere abonnementer, du vælger, hvor ofte du gerne vil modtage mails: dagligt, ugentligt eller pr. time. Hvis du vælger dagligt eller ugentligt, kan du vælge tidspunktet gerne du abonnementet til at køre. I alle, kan du angive op til 24 forskellige abonnementer pr. dag for hver rapport. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Overvejelser i forbindelse med abonnementer sideinddelt rapport 

- I modsætning til abonnementer for dashboards eller rapporter i Power BI indeholder abonnementet en vedhæftet fil til hele rapporten outputtet.  Følgende filtyper vedhæftet, der understøttes: PDF-, PowerPoint-præsentation (PPTX), Excel-projektmappe (XLSX), Word-dokument (DOCX), CSV-fil og XML.

- Der er ingen eksempelbilledet af rapporten i mailens brødtekst.  Vi planlægger at have billedet af den første side i rapporten som et valgfrit element. 

- Den maksimale rapport vedhæftet fil er 25 MB. 

- Du kan abonnere på andre brugere for sideinddelte rapporter, der opretter forbindelse til en hvilken som helst understøttede datakilder, herunder Azure Analysis Services eller Power BI-datasæt. Vær opmærksom på den vedhæftede fil rapport afspejler de data, der er baseret på dine tilladelser, ligesom SQL Server Reporting Services har i dag. 

- Rapportsideabonnementer er bundet til navnet på rapporten.  

- Mailabonnementer sendes med rapportens Standardparameterværdier. 

- Der er ingen **efter dataopdatering** mulighed for hyppighed sammen med sideinddelte rapporter. Du kan altid få de nyeste værdier fra den underliggende datakilde. 

## <a name="next-steps"></a>Næste trin

[Selv og andre Abonner rapporter og dashboards i Power BI-tjenesten](service-report-subscribe.md)

[Hvad er sideinddelte rapporter i Power BI Premium? (prøveversion)](paginated-reports-report-builder-power-bi.md)
