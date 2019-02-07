---
title: Power BI Premium understøtter store datasæt
description: Power BI Premium understøtter nu datasæt op til 10 GB.
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: 941d4bc3d66ce8e636f730d5757b7215c978d582
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794825"
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Power BI Premium understøtter store datasæt

Power BI Premium understøtter upload af Power BI Desktop-filer (.pbix), der er op til 10 GB i størrelse. Når de er uploadet, kan et datasæt med en størrelse på op til 12 GB opdateres. For at bruge et stort datasæt skal du udgive det på et arbejdsområde, som er tildelt Premium-kapacitet.
 
## <a name="best-practices"></a>Bedste praksis

Dette afsnit beskriver bedste praksis for arbejde med store datasæt.

**Store modeller kan være meget ressourcekrævende** for din kapacitet. Vi anbefaler mindst en P1-SKU for modeller, der er større end 1 GB. Selvom publicering af store modeller til arbejdsområder, som understøttes af A-SKU'er op til A3, kan fungere, vil en opdatering af dem ikke.

I nedenstående tabel beskrives de anbefalede SKU'er til forskellige .pbix-størrelser:

   |SKU  |.pbix-størrelse   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3, P4, P5    | op til 10 GB   |

Power BI Embedded A4-SKU'en er lig med P1-SKU'en, A5-SKU'en = P2 og A6-SKU'en = P3. Bemærk, at hvis du udgiver store modeller til A- og EM-SKU'er, kan det returnere fejl, der ikke er specifikke for størrelsesbegrænsningen af modellen i den delte kapacitet. Opdateringsfejl for store modeller i A- og EM-SKU'er skyldes sandsynligvis timeout. Vi arbejder på at forbedre fejlmeddelelserne i disse scenarier.

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
