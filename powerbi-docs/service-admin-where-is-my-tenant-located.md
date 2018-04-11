---
title: Hvor findes min Power BI-lejer?
description: Find ud af, hvor din Power BI-lejer er placeret, og hvordan denne placering markeres. Dette er vigtigt at forstå, da det kan påvirke de interaktioner, du har med tjenesten.
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 22b5319cf95beb3ea4a4a498c7174a701e56fb95
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/08/2018
---
# <a name="where-is-my-power-bi-tenant-located"></a>Hvor er min Power BI-lejer placeret?
<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Find ud af, hvor din Power BI-lejer er placeret, og hvordan denne placering markeres. Dette er vigtigt at forstå, da det kan påvirke de interaktioner, du har med tjenesten.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>Sådan afgør du, hvor din Power BI-lejer er placeret
For at finde det område, hvor din lejer befinder sig, kan du gøre følgende.

1. Vælg **?** i Power BI-tjenesten.
2. Vælg **Om Power BI**.
3. Søg efter værdien ud for **Dine data er lagret i**. Det er det område, du befinder dig i.

![](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>Sådan vælges dataområdet
Dataområdet er baseret på det land, der blev valgt, da lejeren blev oprettet første gang. Dette gælder for tilmelding til Office 365 og til Power BI, da disse oplysninger deles. Hvis dette er en ny lejer, får du vist en rulleliste med landenavne, når du tilmelder dig.

![](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Dette valg bestemmer placeringen af det sted, hvor dataene skal lagres. Power BI vælger et dataområde, der er tættest på dette valg.

> [!WARNING]
> Dette valg, kan ikke ændres!
> 
> 

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

