---
title: Ofte stillede spørgsmål vedrørende datagateway i lokalt miljø
description: Dette er ofte stillede spørgsmål vedrørende datagatewayen i det lokale miljø. Her samler vi ofte stillede spørgsmål vedrørende gateway'en på ét sted.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 01/24/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: b4ecec3b2e53c2fea0fcbb7d78d1114da1a105ed
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="on-premises-data-gateway-faq"></a>Ofte stillede spørgsmål vedrørende datagateway i lokalt miljø
<!-- Shared FAQ shared Include -->
[!INCLUDE [gateway-onprem-faq-shared-include](./includes/gateway-onprem-faq-shared-include.md)]

## <a name="analysis-services"></a>Analysis Services
**Spørgsmål:** Kan jeg bruge msdmpump.dll til at oprette brugerdefinerede effektive brugernavnstilknytninger til Analysis Services?  
**Svar:** Nej. Dette understøttes ikke på nuværende tidspunkt.

**Spørgsmål:** Kan jeg bruge gateway'en til at oprette forbindelse til en flerdimensionel (OLAP)-forekomst.  
**Svar:** Ja! Datagatewayen i det lokale miljø understøtter direkte forbindelser til såvel Analysis Services-tabelmodeller som flerdimensionelle modeller.

**Spørgsmål:** Hvad sker der, hvis jeg installerer gateway'en på en computer med et andet domæne end min lokale server, der bruger Windows-godkendelse?  
**Svar:** Vi garanterer ikke noget i dette tilfælde. Det afhænger alt sammen af tillidsforholdet mellem de to domæner. Hvis de to forskellige domæner er i en pålidelig domænemodel, er gateway'en muligvis i stand til at oprette forbindelse til Analysis Services-serveren, og det effektive brugernavn kan løses. Hvis det ikke er tilfældet, kan der opstå en loginfejl.

**Spørgsmål:** Hvordan kan jeg finde ud af, hvilket effektivt brugernavn der overføres til min lokale Analysis Services-server?  
**Svar:** Vi har svaret på dette spørgsmål i artiklen om [Fejlfinding](service-gateway-onprem-tshoot.md).

**Spørgsmål:** Jeg har 25 databaser i Analysis Services. Er det muligt at aktivere dem alle samtidigt for gateway'en?  
**Svar:** Nej. Det er på tegnebrættet, men vi har ikke en tidshorisont endnu.

## <a name="administration"></a>Administration
**Spørgsmål:** Kan jeg have mere end én administrator for en gateway?  
**Svar:** Ja! Når du administrerer en gateway, kan du gå til fanen Administrator for at tilføje flere administratorer.

**Spørgsmål:** Behøver gateway-administratoren at være administrator på den computer, hvor gateway'en er installeret?  
**Svar:** Nej. Gateway-administratoren bruges til at administrere gateway'en i tjenesten.

**Spørgsmål:** Kan jeg forhindre brugere i min organisation i at oprette en gateway?  
**Svar:** Nej. Det er på tegnebrættet, men vi har ikke en tidshorisont endnu.

**Spørgsmål:** Kan jeg få oplysninger om brug og statistik for alle gateways i min organisation?  
**Svar:** Nej. Det er på tegnebrættet, men vi har ikke en tidshorisont endnu.

## <a name="power-bi"></a>Power BI
**Spørgsmål:** Behøver jeg at opgradere den personlige gateway?
**Svar:** Nej, du kan blive ved med at bruge den personlige gateway til Power BI.

**Spørgsmål:** Hvor ofte bliver felter i et dashboard i Power BI opdateret, når forbindelsen er oprettet via datagatewayen i det lokale miljø?  
**Svar:** Hvert 10. minut. DirectQuery-forbindelser er bare sådan. Det betyder ikke, at et felt udsteder en forespørgsel til din lokale server og viser nye data hvert 10. minut.

**Spørgsmål:** Kan jeg uploade Excel-projektmapper med Power Pivot-datamodeller, opretter forbindelse til datakilder i det lokale miljø? Har jeg brug for en gateway til dette scenarie?  
**Svar:** Ja, du kan uploade projektmapper. Og nej, du behøver ikke en gateway. Men eftersom dataene vil være placeret i Excel-datamodellen, vil rapporter i Power BI, der er baseret på Excel-projektmappen, ikke være dynamiske. For at opdatere rapporter i Power BI ville du hver gang skulle uploade en opdateret projektmappe igen. Eller bruge gateway'en med planlagt opdatering.

**Spørgsmål:** Hvis brugerne deler dashboards, der har en DirectQuery-forbindelse, vil de andre brugere så kunne se dataene, også selvom de måske ikke har de samme tilladelser.  
**Svar:** For et dashboard forbundet til Analysis Services kan brugerne kun se de data, de har adgang til. Hvis brugerne ikke har de samme tilladelser, vil de ikke kunne se nogen data. Alle brugere vil dele de legitimationsoplysninger, der er angivet af administratoren for den pågældende datakilde, for andre datakilders vedkommende.

**Spørgsmål:** Hvorfor kan jeg ikke oprette forbindelse til Oracle-serveren?  
**Svar:** Du skal muligvis installere Oracle-klienten og konfigurere tnsnames.ora-filen med oplysninger om den korrekte server for at oprette forbindelse til Oracle-serveren. Dette er en separat installation uden for gateway'en. Du kan finde flere oplysninger under [Installation af Oracle-klienten](service-gateway-onprem-manage-oracle.md#installing-the-oracle-client).

**Spørgsmål:** Kan gateway'en fungere med ExpressRoute?  
**Svar:** Ja. Du kan finde flere oplysninger om ExpressRoute og Power BI under [Power BI og ExpressRoute](service-admin-power-bi-expressroute.md).

## <a name="next-steps"></a>Næste trin
[Datagateway i lokalt miljø](service-gateway-onprem.md)  
[Datagateway i det lokale miljø – detaljeret](service-gateway-onprem-indepth.md)  
[Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

