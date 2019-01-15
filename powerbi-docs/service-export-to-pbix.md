---
title: Sådan eksporterer du en rapport fra Power BI-tjenesten til Desktop (eksempelvisning)
description: Download en rapport fra Power BI-tjenesten til en Power BI Desktop-fil
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 5c42b633b3c8746d2e26656eb5310b1f74cb2500
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282005"
---
# <a name="export-a-report-from-power-bi-service-to-desktop-preview"></a>Eksportér en rapport fra Power BI-tjenesten til Desktop (eksempelvisning)
I Power BI Desktop kan du eksportere (også kaldet *downloade*) en rapport til Power BI-tjenesten ved at gemme rapporten og vælge **Publicer**. Du kan også eksportere i den anden retning og downloade en rapport fra Power BI-tjenesten til Desktop. Filtypenavnet for filer, der eksporteres, i begge retninger, er *.pbix*.

Der er et par begrænsninger og overvejelser, du skal være opmærksom på, som behandles senere i denne artikel.

![Rullelisten Filer](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix"></a>Download rapporten som en .pbix
Følg disse trin for at downloade .pbix-filen:

1. Åbn den rapport, som du vil downloade, i [Redigeringsvisning](consumer/end-user-reading-view.md) i **Power BI-tjenesten**.
2. Vælg **Filer > Download rapport** på menulinjen.
   
   > [!NOTE]
   > Rapporten skal være [oprettet ved hjælp af Power BI Desktop](guided-learning/publishingandsharing.yml?tutorial-step=2) efter 23. november 2016 – og opdateret efterfølgende – for at den kan downloades. Hvis det ikke er tilfældet, er menupunktet *Download rapport* nedtonet i Power BI-tjenesten.
   > 
   > 
3. Under oprettelse af .pbix-filen vises fremskridt på et statusbanner. Når filen er klar, bliver du bedt om at åbne eller gemme .pbix-filen. Navnet på filen stemmer overens med titlen på rapporten.
   
    ![åbn, gem eller annuller](media/service-export-to-pbix/power-bi-save-pbix.png)
   
    Du har nu mulighed for at åbne .pbix-filen i enten Power BI-tjenesten (app.powerbi.com) eller Power BI Desktop.     
4. Hvis du vil åbne rapporten i Desktop med det samme, skal du vælge **Åbn**. Vælg **Gem > Gem som** for at gemme filen på en bestemt placering. Hvis du ikke allerede har gjort det, skal du [installere Power BI Desktop](desktop-get-the-desktop.md).
   
    Når du åbner rapporten i Desktop, vises der muligvis en advarsel om, at visse funktioner, der er tilgængelige i Power BI-tjenestens rapport, muligvis ikke er tilgængelige i Desktop.
   
    ![advarselsdialogboks](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. Rapporteditoren i Desktop og rapporteditoren i Power BI-tjenesten er næsten identiske.  
   
    ![Rapporteditor i Desktop](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
Der er nogle vigtige overvejelser og begrænsninger, som er knyttet til download (eksport) af en *.pbix*-fil fra Power BI-tjenesten.

* Hvis du vil hente filen, skal du have adgang til at redigere rapporten
* Rapporten skal være oprettet ved hjælp af **Power BI Desktop** og være blevet *publiceret* til **Power BI-tjenesten**, eller .pbix skal være *uploadet* til tjenesten.
* Rapporter skal være publiceret eller opdateret efter 23. november 2016. Rapporter publiceret før dette tidspunkt kan ikke downloades.
* Denne funktion vil ikke fungere sammen med rapporter, der oprindeligt er oprettet i **Power BI-tjenesten**, herunder indholdspakker.
* Du skal altid bruge den seneste version af **Power BI Desktop** ved åbning af downloadede filer. Downloadede *.pbix*-filer åbnes muligvis ikke i versioner af **Power BI Desktop**, der ikke er de nyeste.
* Hvis administratoren har deaktiveret muligheden for at eksportere data, kan denne funktion ikke ses i **Power BI-tjenesten**.
* Datasæt med trinvis opdatering kan ikke downloades til en *.pbix*-fil.

## <a name="next-steps"></a>Næste trin
Se videoen **Guy in a Cube** om denne funktion, den varer ét minut:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Desuden er her nogle flere artikler, der kan hjælpe dig med at lære at bruge **Power BI-tjenesten**:

* [Rapporter i Power BI](consumer/end-user-reports.md)
* [Power BI – Grundlæggende begreber](consumer/end-user-basic-concepts.md)

Når du får **Power BI Desktop** installeret, kan følgende indhold hjælpe dig med at komme i gang hurtigt:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)   

