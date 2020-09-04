---
title: Skift forbindelsesstrenge til datakilden med PowerShell
description: Skift forbindelsesstrenge til datakilden ved hjælp af API'er i PowerShell – Power BI-rapportserver.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.date: 09/01/2020
ms.author: maggies
ms.openlocfilehash: 69aa11216624416f005dcb2e47d1b818204ae7ec
ms.sourcegitcommit: 89ce1777a85b9fc476f077cbe22978c6cf923603
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/02/2020
ms.locfileid: "89286722"
---
# <a name="change-data-source-connection-strings-in-power-bi-reports-with-powershell---power-bi-report-server"></a>Skift forbindelsesstrenge til datakilden i Power BI-rapporter ved hjælp PowerShell – Power BI-rapportserver


Du kan ændre datakildeforbindelsesstrenge for Power BI-rapporter, der hostes i Power BI-rapportserver, ved at bruge PowerShell til at kommunikere med de nødvendige API'er. 

> [!NOTE]
> Denne funktionalitet fungerer i øjeblikket kun for DirectQuery. Understøttelse af import og dataopdatering er på vej.

1. Installér PowerShell-commandlets for Power BI-rapportserver. Find commandlets og installationsvejledningen på [https://github.com/Microsoft/ReportingServicesTools](https://github.com/Microsoft/ReportingServicesTools). 

    Installer `ReportingServicesTools` modulet direkte fra [PowerShell Gallery](https://www.powershellgallery.com/packages/ReportingServicesTools/) ved hjælp af følgende kommando.

    ```powershell
    Install-Module ReportingServicesTools
    ```

2. Hent oplysningerne om den eksisterende datakilde for Power BI-filen via PowerShell-commandlets:

    ```powershell
    Get-RsRestItemDataSource -RsItem '/MyPbixReport'
    ```

    Hvis du vil have vist oplysninger om den første datakilde, der findes i Power BI rapporten: 

    ```powershell
    $dataSources[0]
    ```

3. Opdater oplysningerne om forbindelse og legitimationsoplysninger efter behov. Hvis du opdaterer forbindelsesstrengen, og datakilden anvender gemte legitimationsoplysninger, skal du angive adgangskoden til kontoen. 

    Sådan opdaterer du en forbindelsesstreng til datakilden:

    ```powershell
    $dataSources[0].ConnectionString = 'data source=myCatalogServer;initial catalog=ReportServer;persist security info=False' 
    ```

    Sådan ændrer du typen af legitimationsoplysninger for datakilden:

    ```powershell
    $dataSources[0].DataModelDataSource.AuthType = 'Integrated'
    ```

    Sådan ændrer du brugernavn/adgangskode for datakilden:

    ```powershell
    $dataSources[0].DataModelDataSource.Username = 'domain\user'
    ```
    ```powershell
    $dataSources[0].DataModelDataSource.Secret = 'password'
    ```

4. Gem de opdaterede legitimationsoplysninger på serveren igen.

    ```powershell
    Set-RsRestItemDataSource -RsItem '/MyPbixReport' -RsItemType 'PowerBIReport' -DataSources $dataSources
    ```

## <a name="next-steps"></a>Næste trin

[Sideinddelte rapportdatakilder på Power BI-rapportserver](connect-data-sources.md) 

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
