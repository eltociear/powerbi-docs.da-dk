---
title: Sådan får du dine Excel-data til at fungere godt med Spørgsmål og svar i Power BI
description: Sådan får du dine data til at fungere godt med Spørgsmål og svar i Power BI
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: b45c259cf90668fea878c220670f3efa76b482fd
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/09/2018
---
# <a name="how-to-make-your-excel-data-work-well-with-qa-in-power-bi"></a>Sådan får du dine Excel-data til at fungere godt med Spørgsmål og svar i Power BI
Hvis du opretter datamodeller eller opbygger Excel-projektmapper, der skal bruges med Power BI, skal du læse videre...

I Power BI kan Spørgsmål og svar søge i strukturerede data og vælge den rigtige visualisering til dit spørgsmål – præcis det, der gør det til et overbevisende værktøj at bruge.   

Spørgsmål og svar kan bruges på alle uploadede Excel-filer, der indeholder tabeller, områder eller indeholder en PowerPivot-model, men jo flere optimeringer og mere datarensning, du udfører, desto mere robust er funktionen Spørgsmål og svar.  Hvis du planlægger at dele rapporter og dashboards baseret på dit datasæt, så bør du sørge for, at dine kollegaer let kan stille spørgsmål og få kvalitetssvar.

### <a name="how-qa-works-with-excel"></a>Sådan fungerer Spørgsmål og svar med Excel
Spørgsmål og svar har en grundlæggende evne til at forstå naturligt sprog, der fungerer på tværs af dine data. Den har kontekstafhængig søgning med nøgleord efter navne på Excel-tabeller, kolonner og beregnede felter. Funktionen har også indbygget viden om, hvordan data filtreres, sorteres, aggregeres, grupperes og vises. 

I en Excel-tabel med navnet "Sales", der indeholder kolonnerne "Product", "Month", "Units Sold", "Gross Sales" og "Profit", kan du for eksempel stille spørgsmål om alle disse enheder.  Du kan bede om at få vist salg, samlet fortjeneste efter måned, sortere produkter efter solgte enheder og mange andet. Læs mere om, hvilke [slags spørgsmål, du kan stille](power-bi-q-and-a.md), og hvilke [typer visualiseringer, du kan angive i en forespørgsel med Spørgsmål og svar](power-bi-visualization-types-for-reports-and-q-and-a.md).

### <a name="prepare-an-excel-dataset-for-qa"></a>Udarbejd et Excel-datasæt til Spørgsmål og svar
Spørgsmål og svar er afhængig af navnene på tabeller, kolonner og beregnede felter for at besvare dataspecifikke spørgsmål, hvilket betyder, at det er vigtigt, hvad du kalder enheder i din projektmappe!

Her er nogle tip til at få mest ud af Spørgsmål og svar i din projektmappe.

* Kontrollér, at dine data er i en Excel-tabel. Her er oplysninger om, [hvordan du opretter en Excel-tabel](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US).
* Kontrollér, at navnene på tabellerne, kolonnerne og de beregnede felter giver mening i naturlig tale.
  
  Hvis du for eksempel har en tabel med salgsdata, skal du kalde tabellen "Sales". Kolonnenavne som eksempelvis "Year", "Product", "Sales Rep og "Amount" fungerer godt sammen med Spørgsmål og svar.

* Hvis din projektmappe har en Power Pivot-datamodel, kan du foretage endnu flere optimeringer. Læs mere om [Afmystificering af Spørgsmål og svar i Power BI del 2](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx) fra vores interne team af eksperter i naturligt sprog.

* Åbn datasættet i Power BI Desktop, og opret nye kolonner, opret beregnede målinger, sammenkæd felter for at oprette entydige værdier, klassificer data efter type (f.eks. datoer, strenge, geografi, billeder, URL-adresser) m.m.

## <a name="next-steps"></a>Næste trin
Tilbage til [Spørgsmål og svar i Power BI](power-bi-q-and-a.md)  
[Udarbejd datasæt i det lokale miljø til Spørgsmål og svar](service-q-and-a-direct-query.md)   
[Hurtig introduktion til Spørgsmål og svar](power-bi-visualization-introduction-to-q-and-a.md)  
[Hent data (til Power BI)](service-get-data.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

