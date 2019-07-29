---
title: Flet og tilføj datakilder i det lokale miljø og i clouden
description: Brug datagatewayen i det lokale miljø til at flette eller tilføje datakilder i det lokale miljø eller clouden i samme forespørgsel.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 39f5a01a396e45207777b1a5e58e73808ddf3f88
ms.sourcegitcommit: a58461fe7dfa65c751490b52de5fc73f8e69a17f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/19/2019
ms.locfileid: "68352186"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>Flet eller tilføj datakilder i det lokale miljø og i clouden

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Med datagatewayen i det lokale miljø kan du flette eller tilføje datakilder i det lokale miljø eller cloudmiljøet i samme forespørgsel. Dette er nyttigt, når du vil kombinere data fra flere kilder uden at bruge separate forespørgsler.

>[!NOTE]
>Denne artikel gælder kun for datasæt, der har datakilder i cloudmiljøet og det lokale miljø, som er flettet eller tilføjet i en enkelt forespørgsel. I forbindelse med datasæt, som indeholder separate forespørgsler – én, der opretter forbindelse til datakilder i det lokale miljø, og en anden, der opretter forbindelse til datakilder i cloudmiljøet – udføres forespørgslen, der bruger datakilden i cloudmiljøet, ikke ved hjælp af gatewayen.

## <a name="prerequisites"></a>Forudsætninger

- En [gateway, der er installeret](/data-integration/gateway/service-gateway-install) på en lokal computer.
- En Power BI Desktop-fil med forespørgsler, der kombinerer datakilder i det lokale miljø og i clouden.

>[!NOTE]
>Hvis du vil tilgå datakilder i cloudmiljøet, skal du sikre, at gatewayen har adgang til disse datakilder.

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

    Sørg for, at niveauet for beskyttelse af personlige oplysninger for datakilder både i cloudmiljøet og i det lokale miljø er angivet korrekt for at sikre, at joinforbindelserne håndteres sikkert.

     ![Indstillinger for datasæt](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. Med cloudlegitimationsoplysningerne kan du nu opdatere datasættet ved hjælp af **Opdater nu**, eller du kan planlægge at opdatere med jævne mellemrum.

## <a name="next-steps"></a>Næste trin

Hvis du vil vide mere om dataopdateringer til gateways, skal du se [Brug af datakilde til planlagt opdatering](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh).
