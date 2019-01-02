---
title: Oversigt over indholdspakkeprogrammet for Power BI-tjenesten
description: Program for indholdspakkecertificering
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/20/2018
ms.author: maggies
ms.openlocfilehash: f97393a8a7fe8dc9c413a0cb0cda8be0e965da5b
ms.sourcegitcommit: 6c6aa214dc36c26a01b29e823598d217a3e2b8a1
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/17/2018
ms.locfileid: "53451346"
---
# <a name="overview-of-the-power-bi-service-content-pack-program"></a>Oversigt over indholdspakkeprogrammet for Power BI-tjenesten
En indholdspakke er out-of-box-indhold, der gør det muligt for brugerne øjeblikkeligt at få indsigt i data fra en kilde. En indholdspakke fokuserer sædvanligvis på et bestemt forretningsscenario og giver indsigt i data for en rolle, et domæne eller en arbejdsproces.

ISV'er kan udvikle skabelonindholdspakker, som gør det muligt for kunderne at oprette forbindelse til og bruge deres egne konti. Som domæneeksperter kan de låse op for data på en måde, så erhvervsbrugere nemt kan bruge dem. Indholdspakkerne giver dine kunder ad hoc-overvågning og -analyse, uden at de behøver at investere i en stor rapportinfrastruktur.

Disse ISV-byggede skabelonindholdspakker kan sendes til Power BI-teamet, så de bliver tilgængelige for alle i galleriet med Power BI-indholdspakker (app.powerbi.com/getdata/services) og på Microsoft AppSource (appsource.microsoft.com). Du kan finde et eksempel på en indholdspakke [her](template-content-pack-experience.md).

## <a name="overview"></a>Oversigt
Der er mange trin i den generelle proces for udvikling og indsendelse af en skabelonindholdspakke.

 ![Proces](media/service-content-pack-overview/developer-content-pack-overview.png)

1. [Gennemse kravene](#requirements), og sørg for, at du overholder dem.
2. [Opret indhold](template-content-pack-authoring.md#queries) i Power BI Desktop.
3. [Opret et dashboard](template-content-pack-authoring.md#dashboard) på PowerBI.com.
4. [Test selv indholdspakken](template-content-pack-testing.md) i din organisation.
5. [Indsend](template-content-pack-testing.md#submission) indholdet til Power BI til publicering.

<a name="requirements"></a>

## <a name="requirements"></a>Krav
Hvis du vil oprette og indsende en indholdspakke, der skal publiceres i Power BI-tjenesten og på AppSource, skal du opfylde følgende krav:

* Du skal have et SaaS-program, der bruges af erhvervsbrugere.
* Dit SaaS-program skal indeholde brugerdata, der kan visualiseres i Power BI.
* Dit SaaS-program skal have en API, der er tilgængelig via offentligt internet. API'en skal helst være et REST-baseret API eller et OData-feed. Power BI-indholdspakker understøtter flere godkendelsestyper som Basisgodkendelse, OAuth 2.0 og API-nøgle. 
* Dit SaaS-program er godkendt til udgivelse af en indholdspakke. Send din anmodning til pbiservicesapps@microsoft.com. Vi vil vurdere hver indsendelse ud fra relevans og forventet brug. 
* Signeret partneraftale. Det gør du på [indsendelsestrinnet](template-content-pack-testing.md#submission).

Gennemse afsnittet om [oprettelse](template-content-pack-authoring.md) for at få flere oplysninger om de tekniske krav.

## <a name="business-scenario"></a>Forretningsscenario
Indholdspakker giver dig indsigt og metrikker, der fokuserer på et bestemt forretningsscenario. Viden om din målgruppen og de fordele, de får ud af indholdspakken, vil hjælpe med at sikre, at brugerne kan bruge det indhold, du leverer.

### <a name="tips"></a>Tip
* Identificer din målgruppe og de opgaver, de forsøger at løse.  
* Fokuser på en bestemt tidsperiode (de sidste 90 dage) eller de sidste N resultater.  
* Importér kun de tabeller/kolonner, der relaterer til dit scenario.  
* Overvej at tilbyde mere end kun én indholdspakke til de enkelte scenarier.  

## <a name="frequently-asked-questions"></a>Ofte stillede spørgsmål
**Kan jeg som tredjepart bygge en indholdspakke til Power BI-tjenesten for et SaaS-program, som jeg ikke ejer?**

Vi kræver en signeret partneraftale med ejeren af SaaS-programmet, før en indholdspakke publiceres i tjenesten. Som tredjepart skal du facilitere signeringen af partneraftalen med ejeren af SaaS-programmet.

**Jeg har ikke en offentlig udvikler-API til min tjeneste. Kan jeg stadig bygge en indholdspakke til Power BI-tjenesten, der henter data direkte fra datalageret?**

Nej, indholdspakker til Power BI-tjenesten kræver en udvikler-API, der er tilgængelig via offentligt internet.

**Hvilken type API'er understøttes af tjenesteindholdspakker, og hvilke godkendelsestyper kan de bruges sammen med?**

Indholdspakker til Power BI-tjenesten understøtter alle REST-API- eller OData-feeds. Power BI kan arbejde med flere godkendelsestyper, herunder Basisgodkendelse, OAuth2.0 og API-nøgle. Du kan finde flere oplysninger om de tekniske krav i artiklen om [oprettelse](template-content-pack-authoring.md#dashboard).

**Jeg har en indholdspakke, der er publiceret i Power BI. Hvordan kan jeg opdatere den?**

Publicerede indholdspakker kan opdateres én gang om måneden. Opdateringsanmodninger, der er sendt til [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com) før den sidste dag i den aktuelle måned, publiceres i den første uge i den følgende måned.

**Jeg har flere spørgsmål om tjenesteindholdspakker. Hvordan kan jeg kontakte dig?**

Du kan sende dine spørgsmål via mail til [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com)

## <a name="support"></a>Support
Hvis du vil have support under udvikling, skal du bruge [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support). Kundehændelser finder hurtigt vej til det relevante team.

## <a name="next-step"></a>Næste trin
[Oprettelse](template-content-pack-authoring.md)