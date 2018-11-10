---
title: Ofte stillede spørgsmål om brugerdefinerede Power BI-visuals
description: Gennemse en liste med ofte stillede spørgsmål og svar om brugerdefinerede Power BI-visuals
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 10/29/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: 064d32944f52f6e391d4a7ec4df41ecbf09b7e3f
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223070"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Ofte stillede spørgsmål om brugerdefinerede Power BI-visuals

## <a name="organizational-custom-visuals"></a>Brugerdefinerede visuals til virksomheden

**Hvordan kan administratoren administrere de brugerdefinerede visuals til virksomheden?**

Under fanen "Brugerdefinerede visuals til virksomheder" på administrationsportalen kan administratoren se og [administrere alle de brugerdefinerede visuals til virksomheden](https://docs.microsoft.com/power-bi/service-admin-portal#organization-visuals): tilføje, deaktivere, aktivere og slette.
Der er ikke længere grund til at dele disse visuals via mail eller en delt mappe! Når visuals er udrullet i virksomhedens lager, kan brugerne nemt finde dem og importere de brugerdefinerede visuals til virksomheden i deres rapporter direkte fra Power BI Desktop eller tjenesten. Du kan finde de brugerdefinerede visuals til virksomheden i det indbyggede lager (på skrivebordet og tjenesten) under fanen "MIN ORGANIZATION". Når administratoren overfører en ny version af en brugerdefineret visual til virksomheden, får alle i organisationen den samme opdaterede version. Forfattere behøver ikke at slette denne visual i deres rapporter for at få den nye version af disse visuals, da alle rapporter, der bruger disse visuals, opdateres automatisk! Opdateringsmekanismen svarer til visuals på markedspladser.

**Hvis en administrator overfører en brugerdefineret visual fra den offentlige markedsplads til virksomhedslageret, opdateres den så automatisk, når en leverandør opdaterer denne visual på den offentlige markedsplads?**

Nej, der sker ingen automatisk opdatering fra den offentlige markedsplads.
Det er administratorens ansvar at opdatere versionen af de brugerdefinerede visuals til virksomheden, hvis det ønskes.

**Er det muligt at deaktivere virksomhedslageret?**

Nej, brugere får altid vist fanen "MIN ORGANIZATION" fra Power BI-skrivebordet og -tjenesten. Administratoren kan deaktivere eller slette alle brugerdefinerede visuals til virksomheden fra administrationsportalen, hvilket medfører, at virksomhedslageret bliver tomt.
  
**Hvis administratoren deaktiverer brugerdefinerede visuals fra administrationsportalen (lejerindstillinger), har brugere så stadig adgang til de brugerdefinerede visuals til virksomheden?**

Ja, hvis administratoren deaktiverer de brugerdefinerede visuals fra administrationsportalen, har det ingen indflydelse på virksomhedslageret. Nogle organisationer deaktiverer brugerdefinerede visuals og aktiverer kun håndplukkede visuals, der er importeret og overført af Power BI-administratoren til virksomhedslageret. Deaktivering af brugerdefinerede visuals fra administrationsportalen gennemtvinges ikke i Power BI Desktop. Desktop-brugere kan stadig tilføje og bruge brugerdefinerede visuals fra den offentlige markedsplads i deres rapporter. Men de offentlige brugerdefinerede visuals stopper med at gengive, når de publiceres på Power BI-tjenesten, og der udstedes en passende fejl. Når du bruger Power BI-tjenesten, kan du ikke importere brugerdefinerede visuals fra den offentlige markedsplads. Det er kun visuals fra virksomhedslageret, der kan importeres, fordi indstillingen for de brugerdefinerede visuals i administrationsportalen gennemtvinges i Power BI-tjenesten.

**Hvorfor udgør virksomhedslageret og brugerdefinerede visuals til virksomheden en fantastisk virksomhedsløsning?**

* Alle får den samme version af visuals, der styres af Power BI-administratoren. Når administratoren opdaterer versionen af visuals på administrationsportalen, får alle brugere i virksomheden automatisk den opdaterede version.

* Der er ikke længere grund til at dele visualfiler via mail eller delte mapper! Ét sted, som er synligt for alle medlemmer, der er logget på.

* Sikkerhed og understøttelse – nye versioner af brugerdefinerede visuals til virksomheden opdateres automatisk i alle rapporter på samme måde som visuals på markedspladsen.

* Brugere i organisationen, der anvender de brugerdefinerede visuals til virksomheden, skal være logget på for at se og bruge de brugerdefinerede visuals til virksomheden, hvilket er en sikkerhedsfaktor for organisationen.

* Administratorer kan styre, hvilke brugerdefinerede visuals der skal være tilgængelige i organisationen.

* Administratorer kan aktivere/deaktivere visuals til test fra administrationsportalen. Bedre håndhævelse af sikkerhed, da disse visuals kun bliver tilladt for medlemmer af organisationen.

## <a name="certified-custom-visuals"></a>Certificerede brugerdefinerede visuals

**Hvad er certificerede brugerdefinerede visuals?**

Certificerede brugerdefinerede visuals er visuals på [markedspladsen](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals), der opfylder visse [angivne](power-bi-custom-visuals-certified.md) kodekrav og test udført af Power BI-teamet.  De test, der udføres, er designet til at kontrollere, at visualen ikke har adgang til eksterne tjenester eller ressourcer. Men Microsoft er ikke forfatter af brugerdefinerede visuals fra tredjepart, og vi anbefaler, at kunder kontakter forfatteren direkte for at kontrollere funktionaliteten af en sådan visual.

## <a name="next-steps"></a>Næste trin

Du kan finde oplysninger om fejlfinding under [Fejlfinding af dine brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals-troubleshoot.md).
