---
title: Opret forbindelse til filer i OneDrive til et Power BI-apparbejdsområde
description: Læs om at lagre og oprette forbindelse til dine Excel-, CSV- og Power BI Desktop-filer på OneDrive til dit Power BI-apparbejdsområde.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukasz
ms.service: powerbi
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 52b7748b6b634caf87de01ddc965576339a04b8b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61174928"
---
# <a name="connect-to-files-stored-in-onedrive-for-your-power-bi-app-workspace"></a>Opret forbindelse til filer, der lagres i OneDrive til dit Power BI-apparbejdsområde
Når du har [oprettet et apparbejdsområde i Power BI](service-create-distribute-apps.md), kan du gemme dine Excel-, CSV- og Power BI Desktop-filer på OneDrive for Business til dit Power BI-apparbejdsområde. Du kan fortsætte med at opdatere de filer, du lagrer i OneDrive. Disse opdateringer afspejles automatisk i Power BI-rapporter og dashboards baseret på filerne. 

> [!NOTE]
> Den nye oplevelse arbejdsområde ændringer relationen mellem Power BI-arbejdsområder og Office 365-grupper. Du opretter ikke automatisk en Office 365-gruppe, hver gang du opretter en af de nye arbejdsområder. Læs om [oprettelse af nye arbejdsområder](service-create-the-new-workspaces.md)

Tilføjelse af filer i dit apparbejdsområde er en proces med to trin: 

1. Først skal du [uploade filer til OneDrive for Business](service-connect-to-files-in-app-workspace-onedrive-for-business.md#1-upload-files-to-the-onedrive-for-business-for-your-app-workspace) til dit apparbejdsområde.
2. Derefter skal du [oprette forbindelse til disse filer fra Power BI](service-connect-to-files-in-app-workspace-onedrive-for-business.md#2-import-excel-files-as-datasets-or-as-excel-online-workbooks).

> [!NOTE]
> Apparbejdsområder er kun tilgængelige med [Power BI Pro](service-features-license-type.md).
> 

## <a name="1-upload-files-to-the-onedrive-for-business-for-your-app-workspace"></a>1 Upload filer til OneDrive for Business til dit apparbejdsområde
1. I Power BI-tjenesten skal du vælge pilen ud for Arbejdsområder > vælge ellipsen ( **…** ) ud for navnet på dit arbejdsområde. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-ellipsis.png)
2. Vælg **Filer** for at åbne OneDrive for Business til dit apparbejdsområde i Office 365.
   
   > [!NOTE]
   > Hvis du ikke ser **Filer** i menuen til apparbejdsområdet, skal du vælge **Medlemmer** for at åbne OneDrive for Business til dit apparbejdsområde. Her skal du vælge **Filer**. Office 365 konfigurerer en OneDrive-lagerplacering til din apps gruppearbejdsområdefiler. Denne proces kan tage noget tid. 
   > 
   > 
3. Her kan du uploade dine filer til OneDrive for Business til dit apparbejdsområde. Vælg **Upload**, og gå til dine filer.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grpfilesonedrive.png)

## <a name="2-import-excel-files-as-datasets-or-as-excel-online-workbooks"></a>2 Importér Excel-filer som datasæt eller Excel Online-projektmapper
Nu hvor dine filer er i OneDrive for Business til dit apparbejdsområde, står du over for et valg. Du kan: 

* [Importér data fra Excel-projektmappen som et datasæt](service-get-data-from-files.md). Brug derefter dataene til at oprette rapporter og dashboards, du kan få vist i en webbrowser og på mobilenheder.
* Eller [oprette forbindelse til en hel Excel-projektmappe i Power BI](service-excel-workbook-files.md) og vise den præcis, som den vises i Excel Online.

### <a name="import-or-connect-to-the-files-in-your-app-workspace"></a>Importér eller opret forbindelse til filer i dit apparbejdsområde
1. Skift til apparbejdsområdet i Power BI, så navnet på apparbejdsområdet er i det øverste venstre hjørne. 
2. Vælg **Hent data** nederst i venstre navigationsrude. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-get-data-button.png)
3. Vælg **Hent** i feltet **Filer**.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_getfiles.png)
4. Vælg **OneDrive** - *navnet på dit apparbejdsområde*.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grp_one_drive_shrpt.png)
5. Markér den ønskede fil > **Opret forbindelse**.
   
    Herefter kan du beslutte, om du vil [importere dataene fra Excel-projektmappen](service-get-data-from-files.md), eller [oprette forbindelse til hele Excel-projektmappen](service-excel-workbook-files.md).
6. Vælg **Importér** eller **Opret forbindelse**.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_importexceldataorwholecrop.png)
7. Hvis du vælger **Importér**, så vises projektmappen på fanen **Datasæt**. 
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-import.png)
   
    Hvis du vælger **Opret forbindelse**, så er projektmappen på fanen **Projektmapper**.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-connect.png)

## <a name="next-steps"></a>Næste trin
* [Opret apps og apparbejdsområder i Power BI](service-create-distribute-apps.md)
* [Importér data fra Excel-projektmapper](service-get-data-from-files.md)
* [Opret forbindelse til hele Excel-projektmapper](service-excel-workbook-files.md)
* Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)
* Har du feedback? Besøg [Power BI Ideas](https://ideas.powerbi.com/forums/265200-power-bi)

