---
title: Power BI Premium understøtter store datasæt
description: Power BI Premium understøtter nu datasæt op til 10 GB.
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: 416f022ee3c413c69650e6f1736cc94edcd58f13
ms.sourcegitcommit: a764e4b9d06b50d9b6173d0fbb7555e3babe6351
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/22/2018
ms.locfileid: "49641246"
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Power BI Premium understøtter store datasæt

Power BI Premium understøtter upload af Power BI Desktop-filer (.pbix), der er op til 10 GB i størrelse. Når de er uploadet, kan et datasæt med en størrelse på op til 12 GB opdateres. For at bruge et stort datasæt skal du udgive det på et arbejdsområde, som er tildelt Premium-kapacitet. I denne artikel beskrives overvejelser og bedste fremgangsmåder, når du arbejder med store datasæt.

**Store modeller kan være meget ressourcekrævende** for din kapacitet. Vi anbefaler mindst en P1-SKU for modeller, der er større end 1 GB. I nedenstående tabel beskrives de anbefalede SKU'er til forskellige .pbix-størrelser:

   |SKU  |.pbix-størrelse   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3, P4, P5    | op til 10 GB |

**Dine .pbix-filer repræsenterer data i en stærkt komprimeret tilstand**. Data udvides sandsynligvis flere gange, når de indlæses i hukommelsen, og herfra vil de sikkert blive udvidet gentagne gange under dataopdatering.

**Planlagt opdatering af store datasæt kan tage lang tid** og være meget ressourcekrævende. Derfor bør du ikke planlægge for mange overlappende opdateringer. Bemærk desuden, at timeouten for planlagte opdateringsjob er blevet fordoblet til fire timer for alle datasæt i denne kapacitet. Vi anbefaler [trinvis opdatering](service-premium-incremental-refresh.md), fordi det er hurtigere og mere pålideligt og forbruger færre ressourcer.

**Den første rapportindlæsning af store datasæt kan tage lang tid**, hvis det er et stykke tid siden, det sidste datasæt blev brugt, fordi modellen indlæses i Premium-kapacitetens hukommelse. En linje for længere rapportindlæsninger viser indlæsningens status.

**Hvis du fjerner arbejdsområdet fra Premium-kapacitet**, så vil modellen og alle tilknyttede rapporter og dashboards ikke virke.

**Selvom hukommelses- og tidsbegrænsninger pr. forespørgsel er meget større i Premium-kapacitet**, så anbefales det kraftigt, at du bruger filtre og udsnitsværktøj til at begrænse visuelle elementer til kun at vise det mest nødvendige.

**De næste trin**

[Hvad er Power BI Premium?](service-premium.md)
[Produktbemærkninger til Power BI Premium](service-premium-release-notes.md)
[Whitepaper til Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)
[Planlægning af et whitepaper til Power BI Enterprise Deployment](https://aka.ms/pbienterprisedeploy)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
