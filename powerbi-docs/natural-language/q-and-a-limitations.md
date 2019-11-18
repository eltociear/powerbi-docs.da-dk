---
title: Begrænsninger for Spørgsmål og svar i Power BI
description: Aktuelle begrænsninger for Spørgsmål og svar i Power BI
author: mohaali
manager: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/18/2019
ms.author: mohaali
ms.openlocfilehash: fc4a605f1258bcd93e0b49b596cc3a1691ce2edb
ms.sourcegitcommit: 26123c6bb24c8174beb390f4e06fb938d31238ea
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/22/2019
ms.locfileid: "72717738"
---
# <a name="limitations-of-power-bi-qa"></a>Begrænsninger for Spørgsmål og svar i Power BI

Der er i øjeblikket nogle begrænsninger for Spørgsmål og svar i Power BI.

## <a name="data-sources"></a>Datakilder

### <a name="supported-data-sources"></a>Understøttede datakilder

Spørgsmål og svar i Power BI understøtter følgende konfigurationer af datakilder i Power BI-tjenesten:

- Importtilstand
- Liveforbindelse til Azure Analysis Services
- Liveforbindelse til SQL Server Analysis Services (med en gateway)
- Power BI-datasæt. Der rapporteres en fejl med Spørgsmål og svar i Power BI Desktop, når der bruges et Power BI-datasæt. Fejlen forsvinder dog, når du publicerer rapporten i Power BI-tjenesten.

Sikkerhed på rækkeniveau understøttes i hver af disse konfigurationer.

### <a name="data-sources-not-supported"></a>Ikke-understøttede datakilder

Spørgsmål og svar i Power BI understøtter i øjeblikket ikke følgende konfigurationer:

- Sikkerhed på objektniveau med alle typer datakilder
- DirectQuery mod en hvilken som helst kilde. En løsning, der kan understøtte dette, er at bruge liveforbindelse med Azure Analysis Services, som bruger DirectQuery.
- Sammensatte modeller
- Reporting Services 

## <a name="tooling-limitations"></a>Begrænsninger for værktøjer

Den nye dialogboks for værktøjer giver brugerne mulighed for at tilpasse og forbedre det naturlige sprog i Spørgsmål og svar. Hvis du vil vide mere om værktøjer, kan du læse [Introduktion til værktøjer til Spørgsmål og svar](q-and-a-tooling-intro.md).

## <a name="review-question-limitations"></a>Begrænsninger for repetitionsspørgsmål

Spørgsmål, du har stillet til din datamodel, gemmes kun i 28 dage i repetitionsspørgsmålene. Når du bruger den nye egenskab for repetitionsspørgsmål, vil du måske opleve, at nogle spørgsmål ikke er registreret. Dette er tilsigtet, da programmet for naturligt sprog udfører en række trin til rensning af data for at sikre, at alle tastetryk fra en bruger ikke registreres eller vises.

Lejeradministratorer kan bruge indstillingerne for lejeradministrator til at administrere muligheden for at gemme spørgsmål. Tilladelserne er baseret på sikkerhedsgrupper. 

Brugerne kan også forhindre, at deres spørgsmål bliver registreret ved at vælge **Indstillinger** > **Generelt** og fjerne markeringen i **Giv Spørgsmål og svar tilladelse til at registrere min ytring**. 

## <a name="teach-qa-limitations"></a>Begrænsninger i Træn Spørgsmål og svar

Med Træn Spørgsmål og svar kan du rette to typer fejl:

- Tildel et ord til et felt.
- Tildel en filterbetingelse til et ord.

I øjeblikket understøtter vi ikke omdefinering af et genkendt begreb eller definering af andre typer betingelser eller sætninger. Når du definerer filtreringsbetingelser, kan du desuden kun bruge en begrænset delmængde af sprog, herunder:

- "Land" som er "USA"
- "Land" som ikke er "USA"
- "Vægt" > 2000
- "Vægt" = 2000
- "Vægt" < 2000

> [!NOTE]
> Værktøjer til Spørgsmål og svar understøtter kun importtilstand. De understøtter endnu ikke, at der oprettes forbindelse til en datakilde i det lokale miljø eller en Azure Analysis Services-datakilde. Denne aktuelle begrænsning vil blive fjernet i efterfølgende udgaver af Power BI.

### <a name="statements-not-supported"></a>Sætninger understøttes ikke

- Brug af målinger i betingelser understøttes ikke i øjeblikket. Konvertér i stedet målinger til beregnede kolonner for at få dem til at fungere.
- Flere betingelser understøttes ikke. Du kan løse problemet ved at oprette en DAX-beregnet kolonne, der evaluerer en boolesk sætning med flere betingelser og bruge dette felt i stedet.
- Hvis du ikke angiver en filterbetingelse, når Spørgsmål og svar beder om en delmængde af data, kan du ikke gemme definitionen, selvom der ikke er nogen rød understregning under hele sætningen.
