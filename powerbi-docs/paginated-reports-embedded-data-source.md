---
title: Integrerede datakilder for sideinddelte rapporter i Power BI-tjenesten (eksempelvisning)
description: I denne artikel kan du læse om, hvordan du opretter og redigerer en integreret datakilde i en sideinddelt rapport i Power BI-tjenesten.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/16/2019
ms.openlocfilehash: 4dd9ad935a9f7b286aa64d977a78364f2aed0e0f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65853390"
---
# <a name="create-an-embedded-data-source-for-paginated-reports-in-the-power-bi-service-preview"></a>Opret en integreret datakilde for sideinddelte rapporter i Power BI-tjenesten (eksempelvisning)

I denne artikel kan du læse om, hvordan du opretter og redigerer en integreret datakilde for en sideinddelt rapport i Power BI-tjenesten. Du definerer en integreret datakilde i en enkelt rapport og bruger den kun i denne rapport. I øjeblikket skal sideinddelte rapporter, der er publiceret i Power BI-tjenesten, bruge integrerede datasæt og datakilder, og de kan oprette forbindelse til følgende datakilder:

- Azure SQL Database og Data Warehouse
- SQL Server
- SQL Server Analysis Services
- Oracle 
- Teradata 

For disse datakilder, kan du bruge den [forbindelse til SQL Server Analysis Services](service-premium-connect-tools.md) indstilling:

- Azure Analysis Services
- Power BI Premium-datasæt

Sideinddelte rapporter opretter forbindelse til lokale datakilder via en gateway. Du kan konfigurere gatewayen, når du har publiceret rapporten til Power BI-tjenesten. Få mere at vide om [Power BI-gateways](service-gateway-getting-started.md). 

## <a name="create-an-embedded-data-source"></a>Opret en integreret datakilde
  
1. Åbn Power BI Report Builder.

1. På værktøjslinjen i ruden Rapportdata skal du vælge **Ny** > **Datakilde**. Dialogboksen **Egenskaber for datakilde** åbnes.

    ![Ny datakilde](media/paginated-reports-embedded-data-source/power-bi-paginated-new-data-source.png)
  
2.  I tekstfeltet **Navn** skal du skrive et navn til datakilden eller acceptere standardværdien.  
  
3.  Vælg **Brug en forbindelse, som er integreret i min rapport**.  
  
1.  På listen **Vælg forbindelsestype** skal du vælge en datakildetype. 

1.  Angiv en forbindelsesstreng ved hjælp af en af disse metoder:  
  
    -   Skriv forbindelsesstrengen direkte i tekstfeltet **Forbindelsesstreng**. 
  
    -   Vælg udtryksknappen (**fx)** for at oprette et udtryk, der evalueres som en forbindelsesstreng. I dialogboksen **Udtryk** skal du skrive udtrykket i ruden Udtryk. Vælg **OK**. 
  
    -   Vælg **Byg** for at åbne dialogboksen **Forbindelsesegenskaber** for den datakilde, du har valgt i trin 2.  
  
        Udfyld felterne i dialogboksen **Forbindelsesegenskaber**, så de passer til datakilden. Forbindelsesegenskaber omfatter typen af datakilde, navnet på datakilden og de legitimationsoplysninger, du bruger. Når du har angivet værdier i denne dialogboks, skal du vælge **Test forbindelse** for at bekræfte, at datakilden er tilgængelig, og at de legitimationsoplysninger, du har angivet, er korrekte.  
  
4.  Vælg **Legitimationsoplysninger**.  
  
     Angiv de legitimationsoplysninger, der skal bruges til denne datakilde. Ejeren af datakilden vælger typen af legitimationsoplysninger, der understøttes. Du kan finde flere oplysninger i [Angiv legitimationsoplysninger og forbindelsesoplysninger til rapportdatakilder](https://docs.microsoft.com/sql/reporting-services/report-data/specify-credential-and-connection-information-for-report-data-sources).
  
5.  Vælg **OK**.  
  
     Datakilden vises i ruden Rapportdata.  

## <a name="next-steps"></a>Næste trin

- [Opret et integreret datasæt til en sideinddelt rapport i Power BI-tjenesten](paginated-reports-create-embedded-dataset.md)
- [Hvad er sideinddelte rapporter i Power BI Premium? (prøveversion)](paginated-reports-report-builder-power-bi.md)
