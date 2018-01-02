---
title: "Power BI Premium understøtter store datasæt"
description: "Power BI Premium understøtter nu datasæt op til 10 GB."
services: powerbi
documentationcenter: 
author: MarkMcGeeAtAquent
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/11/2017
ms.author: v-mamcge
ms.openlocfilehash: 82ac4382fe80d83b60705f135b50738718f28876
ms.sourcegitcommit: 7eb15c813a0d14322cb1316bb7aab23cbc13aae6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/11/2017
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Power BI Premium understøtter store datasæt

Power BI Premium understøtter upload af Power BI Desktop-filer (.pbix), der er op til 10 GB i størrelse. For at bruge et stort datasæt skal du udgive det på et arbejdsområde, som er tildelt Premium-kapacitet.
 
## <a name="best-practices"></a>Bedste praksis

Dette afsnit beskriver bedste praksis for arbejde med store datasæt.

**Store modeller kan virke meget belastende** på din kapacitet. Vi anbefaler, at du har mindst en P1 SKU for alle modeller, der er større end 1 GB. I nedenstående tabel beskrives de anbefalede SKU'er til forskellige .pbix-størrelser:


   |SKU  |.pbix-størrelse   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3    | op til 10 GB   |



**Dine .pbix-filer repræsenterer data i en stærkt komprimeret tilstand**. Data udvides sandsynligvis flere gange, når de indlæses i hukommelsen, og herfra vil de sikkert blive udvidet gentagne gange under dataopdatering.

**Planlagt opdatering af store datasæt kan tage lang tid** og være meget ressourcekrævende. Derfor bør du ikke planlægge for mange overlappende opdateringer. Bemærk desuden, at timeouten for planlagte opdateringsjob er blevet fordoblet til fire timer for alle datasæt i denne kapacitet.

**Den første rapportindlæsning af store datasæt kan tage lang tid**, hvis det er et stykke tid siden, det sidste datasæt blev brugt, fordi modellen indlæses i Premium-kapacitetens hukommelse. En linje for længere rapportindlæsninger viser indlæsningens status.

**Hvis du fjerner arbejdsområdet fra Premium-kapacitet**, så vil modellen og alle tilknyttede rapporter og dashboards ikke virke.

**Selvom hukommelses- og tidsbegrænsninger pr. forespørgsel er meget større i Premium-kapacitet**, så anbefales det kraftigt, at du bruger filtre og udsnitsværktøj til at begrænse visuelle elementer til kun at vise det mest nødvendige.

## <a name="next-steps"></a>Næste trin
[Power BI Premium – hvad er det?](service-premium.md)  
[Produktbemærkninger til Power BI Premium](service-premium-release-notes.md)  
[Hvidbog om Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[Hvidbog om planlægning af en Power BI Enterprise-installation](https://aka.ms/pbienterprisedeploy)  
[Aktivering af den udvidede Pro-prøveversion](service-extended-pro-trial.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
