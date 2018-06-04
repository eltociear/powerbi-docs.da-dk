---
title: 'Fejl: Der blev ikke fundet nogen data i din Excel-projektmappe'
description: 'Fejl: Der blev ikke fundet nogen data i din Excel-projektmappe'
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 90fd71c59059f1b1b2c1b7d1d2da582d228c7a88
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34242358"
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>Fejl: Der blev ikke fundet nogen data i din Excel-projektmappe

>[!NOTE]
>Denne artikel gælder for Excel 2007 og nyere.

Når du importerer en Excel-projektmappe til Power BI, kan du se følgende fejl:

*Fejl: Der blev ikke fundet nogen data i din Excel-projektmappe. Dine data er muligvis ikke formateret korrekt. Du skal redigere projektmappen i Excel og importere den igen.*

![](media/service-admin-troubleshoot-excel-workbook-data/pbi_wecouldntfindanydata.png)

## <a name="quick-solution"></a>Hurtig løsning
1. Rediger din projektmappe i Excel.
2. Markér det celleområde, der indeholder dataene. Den første række skal indeholde kolonneoverskrifterne (kolonnenavnene).
3. Tryk på **Ctrl + T** for at oprette en tabel.
4. Gem projektmappen.
5. Vend tilbage til Power BI, og importér projektmappen igen, eller hvis du arbejder i Excel 2016, og du har gemt projektmappen på OneDrive for Business, skal du i Excel klikke på Filer > Udgiv.

## <a name="details"></a>Oplysninger
### <a name="cause"></a>Årsag
I Excel kan du oprette en **tabel** ud af et celleområde, som gør det nemmere at sortere, filtrere og formatere data.

Når du importerer en Excel-projektmappe, leder Power BI efter disse tabeller og importerer dem til et datasæt. Hvis der ikke findes nogen tabeller, vises denne fejlmeddelelse.

### <a name="solution"></a>Løsning
1. Åbn din projektmappe i Excel. 
    >[!NOTE]
    >Billederne her er til Excel 2013. Hvis du bruger en anden version, kan det se lidt anderledes ud, men trinnene er de samme.
    
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht1.png)
2. Markér det celleområde, der indeholder dataene. Den første række skal indeholde kolonneoverskrifterne (kolonnenavnene):
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht2.png)
3. Klik på **Tabel** på båndet under fanen **INDSÆT**. (Eller som en genvej kan du trykke på **Ctrl + T**).
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht3.png)
4. Du kan se følgende dialogboks. Sørg for, at **Tabellen indeholder overskrifter** er markeret, og vælg **OK**:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlcreatetbl.png)
5. Nu er dataene formateret som en tabel:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xltbl.png)
6. Gem projektmappen.
7. Vend tilbage til Power BI. Vælg Hent data nederst i venstre navigationsrude.
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_getdata.png)
8. Vælg **Hent** i feltet **Filer**.
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_getfiles.png)
9. Importér Excel-projektmappen igen. Denne gang bør importen finde tabellen.
   
    Hvis importen stadig mislykkes, kan du give os besked ved at klikke på **Community ** i menuen Hjælp:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_questionmenucommunity.png)
