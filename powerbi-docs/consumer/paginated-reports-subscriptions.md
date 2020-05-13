---
title: Abonner på sideinddelte rapporter i Power BI-tjenesten
description: Denne artikel indeholder ting, du skal huske, når du abonnerer på sideinddelte rapporter i Power BI-tjenesten.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 12/03/2019
ms.openlocfilehash: c7f377c1295d4cd8f0d226331fcb6db697786e5a
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83141258"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Meld dig selv og andre til et abonnement på sideinddelte rapporter i Power BI-tjenesten 

Du kan nu oprette mailabonnementer på sideinddelte rapporter i Power BI-tjenesten for dig selv og andre. Generelt er processen den samme som [at abonnere på rapporter og dashboards i Power BI-tjenesten](end-user-subscribe.md). I denne artikel forklares forskelle og overvejelser. 

Når du konfigurerer abonnementer, vælger du ofte, hvordan du vil modtage mails: dagligt, ugentligt, månedligt eller hver time. Du kan også vælge det eller de tidspunkter, du vil have abonnementet til at køre på. Du kan i alt angive op til 24 forskellige abonnementer for hver rapport. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Overvejelser i forbindelse med abonnementer på sideinddelte rapporter 

- I modsætning til abonnementer på dashboards eller rapporter i Power BI indeholder dit abonnement en vedhæftet fil af hele outputtet for rapporten.  Følgende vedhæftede filtyper understøttes: PDF, PowerPoint-præsentation (PPTX), Excel-projektmappe (XLSX), Word-dokument (DOCX), CSV-fil og XML.

- Du kan inkludere et billede som forhåndsvisning af rapporten i mailens brødtekst.  Dette er valgfrit og kan variere en smule for den første side i din vedhæftede rapport, afhængigt af det valgte format for den vedhæftede fil. 

- Den maksimale størrelse af vedhæftede rapporter er 25 MB. 

- Du kan tilmelde andre brugere et abonnement på sideinddelte rapporter, der har forbindelse til en hvilken som helst understøttet datakilde, herunder Azure Analysis Services eller Power BI-datasæt. Husk på, at den vedhæftede rapport afspejler dataene baseret på dine tilladelser, ligesom SQL Server Reporting Services gør i dag. 

- Mailabonnementer kan sendes med enten de aktuelt valgte parametre eller standardparametrene for din rapport.  Du kan angive forskellige parameterværdier for hvert abonnement, du opretter for din rapport. 

- Hvis forfatteren af din rapport har angivet parametre baseret på et udtryk (f.eks. er standardværdien altid dags dato), bruger abonnementet det som standardværdi. Du kan ændre andre parameterværdier og vælge at bruge aktuelle værdier, men medmindre du også eksplicit ændrer denne værdi, bruger abonnementet parameteren, der er baseret på et udtryk.

- Der findes ingen indstilling til **Efter dataopdatering** for hyppigheden i forbindelse med sideinddelte rapporter. Du får altid de nyeste værdier fra den underliggende datakilde. 

## <a name="next-steps"></a>Næste trin

[Meld dig selv og andre til abonnementer på rapporter og dashboards i Power BI-tjenesten](../collaborate-share/service-report-subscribe.md)

[Sideinddelte rapporter i Power BI-tjenesten](end-user-paginated-report.md)
