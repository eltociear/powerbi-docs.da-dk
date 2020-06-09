---
title: Begrænsninger for tjenesteprincipal
description: Begrænsninger for tjenesteprincipal
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 06/06/2020
ms.custom: include file
ms.openlocfilehash: 8e50a529bfd398a4075ebf049ee4aec1bcf48b4d
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315761"
---
## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

* Tjenesteprincipalen fungerer kun med [nye arbejdsområder](../collaborate-share/service-create-the-new-workspaces.md).
* **Mit arbejdsområde** understøttes ikke til brug sammen med tjenesteprincipalen.
* Der kræves dedikeret kapacitet for at kunne begynde at producere.
* Du kan ikke logge på Power BI-portalen ved hjælp af en tjenesteprincipal.
* Der kræves rettigheder som Power BI-administrator for at kunne aktivere tjenesteprincipalen under Indstillinger for udvikler på Power BI-administrationsportalen.
* Programmer til [integration i din organisation](../developer/embedded/embed-sample-for-your-organization.md) kan ikke bruge en tjenesteprincipal.
* Administration af [dataflow](../transform-model/service-dataflows-overview.md) understøttes ikke.
* Tjenesteprincipaler understøtter i øjeblikket ingen administrator-API'er.
* Når du bruger en tjenesteprincipal med en [Azure Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-overview)-datakilde, skal selve tjenesteprincipalen have tilladelser til en forekomst af Azure Analysis Services. Brug af en sikkerhedsgruppe, der indeholder tjenesteprincipalen til dette formål, fungerer ikke.