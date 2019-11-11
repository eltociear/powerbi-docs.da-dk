---
title: Publicer en sideinddelt rapport i Power BI-tjenesten
description: I dette selvstudium lærer du at publicere en sideinddelt rapport i Power BI-tjenesten ved at uploade den fra din lokale computer.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 11/05/2018
ms.openlocfilehash: 6cf3cd715915b5a6f3aa41e61c01c8b5b0a7d204
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874771"
---
# <a name="publish-a-paginated-report-to-the-power-bi-service"></a>Publicer en sideinddelt rapport i Power BI-tjenesten

I denne artikel lærer du om publicering af en sideinddelt rapport i Power BI-tjenesten ved at uploade den fra din lokale computer. Du kan uploade sideinddelte rapporter til Mit arbejdsområde eller andre arbejdsområder, så længe arbejdsområdet er i en Premium-kapacitet. Se efter rombeikonet ![Rombeikon for Power BI Premium-kapacitet](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) ud for navnet på arbejdsområdet. 

Hvis din datakilde til rapporten er i det lokale miljø, skal du [oprette en gateway](#create-a-gateway), når du har uploadet rapporten.

## <a name="add-a-workspace-to-a-premium-capacity"></a>Føj et arbejdsområde til en Premium-kapacitet

Hvis arbejdsområdet ikke har rombeikonet ![Rombeikon for Power BI Premium-kapacitet](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) ud for navnet, skal du føje arbejdsområdet til en Premium-kapacitet. 

1. Vælg **Arbejdsområder**, vælg ellipsen ( **...** ) ud for navnet på arbejdsområdet, og vælg derefter **Rediger arbejdsområde**.

    ![Vælg Rediger arbejdsområde](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace.png)

1. I dialogboksen **Rediger arbejdsområde** skal du udvide **Avanceret** og derefter sørge for, at indstillingen **Dedikeret kapacitet** er angivet til **Til**.

    ![Vælg Dedikeret kapacitet](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace-dialog.png)

   Du kan muligvis ikke kan ændre den. Hvis ikke, skal du kontakte administratoren af Power BI Premium-kapacitet for at får tildelt rettigheder, så du kan føje dit arbejdsområde til en Premium-kapacitet.


## <a name="upload-a-paginated-report"></a>Upload en sideinddelt rapport

1. Opret din sideinddelte rapport i Report Builder, og gem den på din lokale computer.

1. Åbn Power BI-tjenesten i en browser, og gå til arbejdsområdet Premium, hvor du vil publicere rapporten. Se efter rombeikonet ![Rombeikon for Power BI Premium-kapacitet](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) ud for navnet. 

1. Vælg **Hent data**.

    ![Power BI Hent data](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-get-data.png)

1. Vælg **Hent** i feltet **Filer**.

    ![Power BI Hent filer](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-files-get.png)

1. Vælg **Lokal fil** > gå til den sideinddelte rapport > **Åbn**.

    ![Vælg Lokal fil](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-local-file.png)

1. Vælg **Fortsæt** > **Rediger legitimationsoplysninger**.

    ![Vælg Rediger legitimationsoplysninger](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-edit-credentials.png)

1. Konfigurer dine legitimationsoplysninger > **Log på**.

    ![Rediger legitimationsoplysninger](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-credentials.png)

   Du kan se din rapport på listen over rapporter.

    ![Sideinddelt rapport på listen Rapporter](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

1. Vælg den for at åbne den i Power BI-tjenesten. Hvis den indeholder parametre, skal du vælge dem, før du kan få vist rapporten.
 
    ![Vælg parametre](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

## <a name="create-a-gateway"></a>Opret en gateway

Ligesom alle andre Power BI-rapporter skal du oprette eller oprette forbindelse til en gateway til at få adgang til dataene, hvis datakilden for rapporten er i det lokale miljø.

1. Ud for navnet på rapporten, skal du vælge **Administrer**.

   ![Administrer den sideinddelte rapport](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-manage.png)

1. Du kan se yderligere oplysninger og næste trin i artiklen [Hvad er en datagateway i det lokale miljø](service-gateway-onprem.md) til Power BI-tjenesten.

### <a name="gateway-limitations"></a>Gateway-begrænsninger

I øjeblikket understøtter gateways ikke parametre med flere værdier.


## <a name="next-steps"></a>Næste trin

- [Publicer en sideinddelt rapport i Power BI-tjenesten](paginated-reports-view-power-bi-service.md)
- [Hvad er sideinddelte rapporter i Power BI Premium?](paginated-reports-report-builder-power-bi.md)

