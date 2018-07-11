---
title: Flet og tilføj datakilder i det lokale miljø og i clouden
description: Brug datagatewayen i det lokale miljø til at flette eller tilføje datakilder i det lokale miljø eller clouden i samme forespørgsel.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 06/06/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 2547be7f7bdadb7f991db54230d4fd791941838d
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/03/2018
ms.locfileid: "37600059"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>Flet eller tilføj datakilder i det lokale miljø og i clouden

Med datagatewayen i det lokale miljø kan du flette eller tilføje datakilder i det lokale miljø eller clouden i samme forespørgsel. Dette er nyttigt, når du vil blande data fra flere kilder uden at bruge separate forespørgsler.

## <a name="prerequisites"></a>Forudsætninger

- En [gateway, der er installeret](service-gateway-install.md) på en lokal computer.
- En Power BI Desktop-fil med forespørgsler, der kombinerer datakilder i det lokale miljø og i clouden.

1. I øverste højre hjørne af Power BI-tjenesten skal du vælge tandhjulsikonet ![tandhjulsikonet for indstillinger](media/service-gateway-mashup-on-premises-cloud/icon-gear.png) > **Administrer gateways**.

    ![Administrer gateways](media/service-gateway-mashup-on-premises-cloud/manage-gateways.png)

2. Vælg den gateway, du vil konfigurere.

3. Under **Indstillinger for gatewayklynge** skal du vælge **Tillad, at brugerens datakilder fra skyen opdateres via denne gateway** > **Anvend**.

    ![Opdater via denne gatewayklynge](media/service-gateway-mashup-on-premises-cloud/refresh-gateway-cluster.png)

4. Under denne gatewayklynge kan du tilføje en [datakilde i det lokale miljø](service-gateway-enterprise-manage-scheduled-refresh.md#add-a-data-source), som skal bruges i dine forespørgsler. Du behøver ikke at tilføje datakilder i clouden her.

5. Upload Power BI Desktop-filen med de forespørgsler, der kombinerer datakilder i det lokale miljø og i clouden, til Power BI-tjenesten.

6. På siden **Datasætindstillinger** for det nye datasæt:

   - For kilden i det lokale miljø skal du vælge den gateway, der er knyttet til datakilden.

   - Under **Legitimationsoplysninger for datakilde** skal du redigere legitimationsoplysningerne for datakilden efter behov.

     ![Indstillinger for datasæt](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. Med cloudlegitimationsoplysningerne kan du nu opdatere datasættet ved hjælp af **Opdater nu**, eller du kan planlægge at opdatere med jævne mellemrum.


## <a name="next-steps"></a>Næste trin

Hvis du vil vide mere om dataopdateringer til gateways, skal du se [Brug af datakilde til planlagt opdatering](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh).