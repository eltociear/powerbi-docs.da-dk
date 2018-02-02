---
title: "Sådan eksporterer du en rapport fra Power BI-tjenesten til Desktop (eksempelvisning)"
description: Download en rapport fra Power BI-tjenesten til en Power BI Desktop-fil
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
ms.date: 01/24/2018
ms.author: mihart
ms.openlocfilehash: 7c0bd2f342385f71fd91bb81a284ef41deb46169
ms.sourcegitcommit: be5223b62e9a5d57c52f8588d4e539d814751dd6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2018
---
# <a name="export-a-report-from-power-bi-service-to-desktop-preview"></a>Eksportér en rapport fra Power BI-tjenesten til Desktop (eksempelvisning)
I Power BI Desktop kan du eksportere (også kaldet *downloade*) en rapport til Power BI-tjenesten ved at gemme rapporten og vælge **Publicer**. Du kan også eksportere i den anden retning og downloade en rapport fra Power BI-tjenesten til Desktop. Filtypenavnet for filer, der eksporteres, i begge retninger, er *.pbix*.

Der er et par begrænsninger og overvejelser, du skal være opmærksom på, som behandles senere i denne artikel.

![](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix"></a>Download rapporten som en .pbix
Følg disse trin for at downloade .pbix-filen:

1. Åbn den rapport, som du vil downloade, i [Redigeringsvisning](service-reading-view-and-editing-view.md) i **Power BI-tjenesten**.
2. Vælg **Filer > Download rapport** på menulinjen.
   
   > [!NOTE]
   > Rapporten skal være [oprettet ved hjælp af Power BI Desktop](guided-learning/publishingandsharing.yml#step-2) efter 23. november 2016 – og opdateret efterfølgende – for at den kan downloades. Hvis det ikke er tilfældet, er menupunktet *Download rapport* nedtonet i Power BI-tjenesten.
   > 
   > 
3. Under oprettelse af .pbix-filen vises fremskridt på et statusbanner. Når filen er klar, bliver du bedt om at åbne eller gemme .pbix-filen. Navnet på filen stemmer overens med titlen på rapporten.
   
    ![](media/service-export-to-pbix/power-bi-save-pbix.png)
   
    Du har nu mulighed for at åbne .pbix-filen i enten Power BI-tjenesten (app.powerbi.com) eller Power BI Desktop.     
4. Hvis du vil åbne rapporten i Desktop med det samme, skal du vælge **Åbn**. Vælg **Gem > Gem som** for at gemme filen på en bestemt placering. Hvis du ikke allerede har gjort det, skal du [installere Power BI Desktop](desktop-get-the-desktop.md).
   
    Når du åbner rapporten i Desktop, vises der muligvis en advarsel om, at visse funktioner, der er tilgængelige i Power BI-tjenestens rapport, muligvis ikke er tilgængelige i Desktop.
   
    ![](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. Rapporteditoren i Desktop og rapporteditoren i Power BI-tjenesten er næsten identiske.  
   
    ![](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
Der er nogle vigtige overvejelser og begrænsninger, som er knyttet til download (eksport) af en *.pbix*-fil fra Power BI-tjenesten.

* Hvis du vil hente filen, skal du have adgang til at redigere rapporten
* Rapporten skal være oprettet ved hjælp af **Power BI Desktop** og være blevet *publiceret* til **Power BI-tjenesten**, eller .pbix skal være *uploadet* til tjenesten.
* Rapporter skal være publiceret eller opdateret efter 23. november 2016. Rapporter publiceret før dette tidspunkt kan ikke downloades.
* Denne funktion vil ikke fungere sammen med rapporter, der oprindeligt er oprettet i **Power BI-tjenesten**, herunder indholdspakker.
* Du skal altid bruge den seneste version af **Power BI Desktop** ved åbning af downloadede filer. Downloadede *.pbix*-filer åbnes muligvis ikke i versioner af **Power BI Desktop**, der ikke er de nyeste.
* Hvis administratoren har deaktiveret muligheden for at eksportere data, kan denne funktion ikke ses i **Power BI-tjenesten**.

## <a name="next-steps"></a>Næste trin
Se videoen **Guy in a Cube** om denne funktion, den varer ét minut:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Desuden er her nogle flere artikler, der kan hjælpe dig med at lære at bruge **Power BI-tjenesten**:

* [Rapporter i Power BI](service-reports.md)
* [Power BI – Grundlæggende begreber](service-basic-concepts.md)

Når du får **Power BI Desktop** installeret, kan følgende indhold hjælpe dig med at komme i gang hurtigt:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)   

