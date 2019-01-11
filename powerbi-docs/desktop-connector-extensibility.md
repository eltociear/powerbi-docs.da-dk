---
title: Forbindelsesudvidelse i Power BI
description: Forbindelsesudvidelse, funktioner, sikkerhedsindstillinger og certificerede forbindelser
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/25/2018
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: eaf76f2ba762a603bf37385ea00cd714499db4b5
ms.sourcegitcommit: 5206651c12f2b91a368f509470b46f3f4c5641e6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/02/2019
ms.locfileid: "53983410"
---
# <a name="connector-extensibility-in-power-bi"></a>Forbindelsesudvidelse i Power BI

I Power BI kan kunder og udviklere udvide de datakilder, som de kan oprette forbindelse til, på mange måder, f.eks. ved hjælp af eksisterende forbindelser og generiske datakilder (f.eks. ODBC, OData, Oledb, Web, CSV, XML, JSON). Ud over disse datakilder kan udviklere oprette dataudvidelser, som kaldes **brugerdefinerede forbindelser**, og de kan certificere en forbindelse for at gøre den til en **certificeret forbindelser**.

Aktuelt er funktionen **Brugerdefinerede forbindelser** aktiveret ved hjælp af en funktionsknap. Inden vi flytter funktionen fra beta til at være generelt tilgængelig, har vi tilføjet en menu, hvor du på en sikker måde kan styre det niveau af brugerdefineret kode, du vil tillade at køre på dit system: alle brugerdefinerede forbindelser eller kun de forbindelser, som er certificeret og distribueres af Microsoft i dialogboksen **Hent data**.

## <a name="custom-connectors"></a>Brugerdefinerede forbindelser

**Brugerdefinerede forbindelser** kan inkludere en bred vifte af muligheder lige fra små API'er, der er vigtige for din virksomhed, til store branchespecifikke tjenester, som Microsoft ikke har frigivet en forbindelse til. Mange forbindelser distribueres af leverandøren, og hvis du har brug for en bestemt dataforbindelse, skal du kontakte en leverandør.

Hvis du vil bruge en **brugerdefineret forbindelse**, skal du placere den i mappen *\[Dokumenter]\\Power BI Desktop\\Custom Connectors* og tilpasse sikkerhedsindstillingerne som beskrevet i følgende afsnit.

Du behøver ikke at justere sikkerhedsindstillingerne for at bruge **certificerede forbindelser**.

## <a name="data-extension-security"></a>Sikkerhed for dataudvidelse

Hvis du vil ændre sikkerhedsindstillingerne for en dataudvidelse i **Power BI Desktop**, skal du vælge **Fil > Indstillinger > Indstillinger > Sikkerhed**.

![Du kan styre, om du vil tillade indlæsning af brugerdefinerede forbindelser med indstillingerne under Sikkerhed for dataudvidelse](media/desktop-connector-extensibility/data-extension-security-1.png)

Under **Dataudvidelser** kan du vælge mellem to niveauer af sikkerhed:

* (Anbefalet) Tillad kun, at certificerede udvidelser indlæses
* (Ikke anbefalet) Tillad, at alle udvidelser indlæses uden advarsel

Hvis du planlægger at bruge **brugerdefinerede forbindelser** eller forbindelser, som du eller en tredjepart har udviklet og distribueret, skal du vælge **(Ikke anbefalet) Tillad, at alle udvidelser indlæses uden advarsel**. Vi anbefaler ikke denne sikkerhedsindstilling, medmindre du har fuld tillid til dine brugerdefinerede connectorer, eftersom kode i connectorerne kan håndtere legitimationsoplysninger (herunder at sende dem via HTTP) og ignorere niveauer for beskyttelse af personlige oplysninger.

Hvis du vælger sikkerhedsindstillingen **(Anbefalet)**, og der ikke er nogen brugerdefinerede forbindelser på dit system, vises der en fejl med en beskrivelse af de forbindelser, der ikke kan indlæses pga. sikkerhedsindstillingerne.

![Der åbnes en dialogboks med en beskrivelse af, hvilke brugerdefinerede forbindelser der ikke kan indlæses pga. sikkerhedsindstillingerne. I dette tilfælde er det forbindelsen TripPin.](media/desktop-connector-extensibility/data-extension-security-2.png)

Hvis du vil løse fejlen og bruge disse forbindelser, skal du ændre dine sikkerhedsindstillinger til indstillingen **(Ikke anbefalet)** som beskrevet tidligere og genstarte **Power BI Desktop**.

## <a name="certified-connectors"></a>Certificerede forbindelser

Et begrænset undersæt af dataforbindelser, der betragtes som **Certificeret**. De certificerede forbindelser er tilgængelige via dialogboksen **Hent data**, men det er stadig tredjepartsudvikleren, som er ansvarlig for vedligeholdelse og support. Selvom Microsoft distribuerer disse forbindelser, er vi ikke ansvarlige for deres ydeevne og fortsatte funktionalitet.

Hvis du vil certificere en brugerdefineret forbindelse, skal du få din leverandør til at kontakte dataconnectors@microsoft.com.
