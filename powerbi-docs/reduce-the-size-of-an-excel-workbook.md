---
title: Reducer størrelsen på en Excel-projektmappe for at få den vist i Power BI
description: Reducer størrelsen på en Excel-projektmappe for at få den vist i Power BI
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 12ff54b1aa44edaead98b1fab6942acbd76216c7
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2018
ms.locfileid: "39329425"
---
# <a name="reduce-the-size-of-an-excel-workbook-to-view-it-in-power-bi"></a>Reducer størrelsen på en Excel-projektmappe for at få den vist i Power BI
Du kan uploade en Excel-projektmappe, der er mindre end 1 GB, til Power BI. En Excel-projektmappe kan omfatte to dele: en datamodel og resten af rapporten, dvs. hovedindholdet i regnearket. Hvis rapporten ligger under følgende størrelsesgrænser, kan du gemme den til **OneDrive for Business**, oprette forbindelse til den fra Power BI og se den i Excel Online:

* Projektmappen må samlet set fylde op til 1 GB.
* Hovedindholdet i regnearket må fylde op til 10 MB.

## <a name="what-makes-core-worksheet-contents-larger-than-10-mb"></a>Det gør størrelsen på hovedindholdet i regnearket større end 10 MB
Her er nogle elementer, som kan gøre størrelsen på hovedindholdet i regnearket større end 10 MB:

* Billeder.
* Skraverede celler. [Fjern et celleskyggeformat](https://support.office.com/article/Add-or-change-the-background-color-of-cells-ac10f131-b847-428f-b656-d65375fb815e).
* Farvede regneark. [Fjern en arkbaggrund](https://support.office.com/en-US/article/add-or-remove-a-sheet-background-3577a762-8450-4556-96a2-cc265abc00a8).
* Tekstfelter.
* Clipart.

Overvej at fjerne disse elementer, hvis det er muligt. 

Hvis rapporten indeholder en datamodel, har du andre muligheder: 

* Fjern data fra Excel-regneark, og gem dem i stedet i datamodellen. Se Fjern data fra regneark nedenfor for at få flere oplysninger. 
* [Opret en hukommelseseffektiv datamodel](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70), og reducer rapportens samlede størrelse.

Hvis du vil foretage nogle af disse ændringer, skal du redigere projektmappen i Excel.

Læs mere om [begrænsninger for filstørrelsen for Excel-projektmapper i SharePoint Online](https://support.office.com/article/File-size-limits-for-workbooks-in-SharePoint-Online-9e5bc6f8-018f-415a-b890-5452687b325e).

## <a name="remove-data-from-worksheets"></a>Fjern data fra regneark
Hvis du importerer data i Excel fra fanen Power Query eller fanen Excel-data, indeholder projektmappen muligvis de samme data i en tabel i Excel som i datamodellen. Store tabeller i Excel-regneark kan gøre størrelsen på hovedindholdet i regnearket større end 10 MB. Hvis du fjerner tabellen i Excel og bevarer dataene i datamodellen, kan du reducere størrelsen på rapportens hovedindhold i regnearket. 

Når du importerer data i Excel, skal du følge disse tip:

* **I Power Query**: Ryd feltet **Indlæs i regneark**.
  
  Dataene er kun blevet importeret i datamodellen, uden data i Excel-regneark.
* **Fra fanen Excel-data**, hvis du tidligere har kontrolleret **Tabel** i Guiden Import: Gå til **Eksisterende forbindelser**, \> og klik på \> **Opret kun forbindelse**. Slet den oprindelige tabel eller den tabel, der blev oprettet under den indledende import.
* **Fra fanen Excel-data**: Markér ikke **Tabel** i feltet **Importér data**.

## <a name="workbook-size-optimizer"></a>Workbook Size Optimizer
Hvis din projektmappe indeholder en datamodel, kan du reducere størrelsen på projektmappen ved at køre Workbook Size Optimizer. [Download Workbook Size Optimizer](https://www.microsoft.com/en-us/download/details.aspx?id=38793).

## <a name="related-info"></a>Relaterede oplysninger
[Opret en hukommelseseffektiv datamodel](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)

[Brug OneDrive for Business-links i Power BI Desktop](desktop-use-onedrive-business-links.md)

