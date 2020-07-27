---
title: Begrænsninger for tjenesteprincipal
description: Begrænsninger for tjenesteprincipal
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 06/06/2020
ms.custom: include file
ms.openlocfilehash: 569d7dfe251183962a14de1c42d85ee2e58950af
ms.sourcegitcommit: d8acf2fb0318708a3e8e1e259cb3747b0312b312
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/15/2020
ms.locfileid: "86401673"
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
* Tjenesteprincipalen har i øjeblikket ikke adgang til datakilder i gatewayen. Du kan altså ikke tilføje en tjenesteprincipal som bruger af datakilder i gatewayen.
