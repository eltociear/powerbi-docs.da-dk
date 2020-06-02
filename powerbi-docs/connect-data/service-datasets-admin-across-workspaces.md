---
title: Styr brugen af datasæt på tværs af arbejdsområder – Power BI
description: Lær, hvordan du begrænser flowet af oplysninger i Power BI-lejeren.
author: maggiesMSFT
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/30/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 4599b5aa8961c5a6526f5de6a07815355e6e41db
ms.sourcegitcommit: 5e5a7e15cdd55f71b0806016ff91256a398704c1
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/22/2020
ms.locfileid: "83793566"
---
# <a name="control-the-use-of-datasets-across-workspaces"></a>Styr brugen af datasæt på tværs af arbejdsområder

Brug af datasæt på tværs af arbejdsområder er en effektiv måde at drive datakultur og datademokratisering i en organisation på. Hvis du er Power BI-administrator vil du måske nogle gange begrænse flowet af oplysninger i Power BI-lejeren. Ved hjælp af lejerindstillingen **Brug datasæt på tværs af arbejdsområder** kan du begrænse genbrug af datasæt enten helt eller delvist for hver sikkerhedsgruppe.

![Indstillinger for arbejdsområde for Power BI-administrator](media/service-datasets-admin-across-workspaces/power-bi-admin-workspace-settings.png)

Hvis du slår denne indstilling fra, kan du her se effekten på forfattere af rapporter:

- Knappen til at kopiere rapporter på tværs af arbejdsområder er ikke tilgængelig. 
- I en rapport, der er baseret på et delt datasæt, er knappen **Rediger rapport** ikke tilgængelig.
- I Power BI-tjenesten vises der kun datasæt for det aktuelle arbejdsområde i forbindelse med søgningsoplevelsen.
- I Power BI Desktop vises der kun datasæt fra arbejdsområder, hvor du er medlem, i forbindelse med søgningsoplevelsen.
- I Power BI Desktop får brugerne vist en fejlmeddelelse, hvor de bliver bedt om at oprette forbindelse til et andet datasæt, hvis de åbner en .pbix-fil med en direkte forbindelse til et datasæt uden for et hvilket som helst arbejdsområde.

## <a name="provide-a-link-for-the-certification-process"></a>Angiv et link til certificeringsprocessen

Som lejeradministrator kan du angive en URL-adresse for linket **Få mere at vide** på siden med indstillingen **Godkendelse**.  Dette link kan føre til dokumentation om certificeringsprocessen. Hvis du ikke angiver en destination for linket **Få mere at vide**, peger det som standard på artiklen om [certificering af datasæt](service-datasets-certify.md).

![Få mere at vide om certificering af datasæt](media/service-datasets-certify-promote/power-bi-dataset-learn-more-certification.png)

## <a name="next-steps"></a>Næste trin

- [Brug datasæt på tværs af arbejdsområder](service-datasets-across-workspaces.md)
- Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
