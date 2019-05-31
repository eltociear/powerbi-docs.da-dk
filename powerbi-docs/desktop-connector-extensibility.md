---
title: Forbindelsesudvidelse i Power BI
description: Forbindelsesudvidelse, funktioner, sikkerhedsindstillinger og certificerede forbindelser
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 16b96d91a9dd37fa8a502bbcca772438c703cb63
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412993"
---
# <a name="connector-extensibility-in-power-bi"></a>Forbindelsesudvidelse i Power BI

I Power BI, kan kunder og -udviklere udvide de datakilder, som de opretter forbindelse på mange måder. De kan bruge eksisterende forbindelser og generiske datakilder (f.eks ODBC, OData, Oledb, Web-, CSV, XML, JSON). Eller, udviklere oprette dataudvidelser, der refereres til som **brugerdefinerede Connectors**, og gør dem **certificerede forbindelser**.

I øjeblikket kan du aktivere **brugerdefinerede Connectors** ved hjælp af en menu, der giver dig mulighed for sikkert styrer adgangsniveauet brugerdefineret kode, du ønsker, at køre på systemet. Du kan vælge alle brugerdefinerede connectors eller kun forbindelser certificeret og distribueres af Microsoft i den **Hent Data** dialog.

## <a name="custom-connectors"></a>Brugerdefinerede forbindelser

**Brugerdefinerede Connectors** kan indeholde en bred vifte af muligheder, lige fra små API'er, der er vigtige for din virksomhed, til store branchespecifikke tjenester, som Microsoft ikke har udgivet en forbindelse til. Mange connectorer distribueres af leverandøren. Hvis du har behov for en bestemt forbindelse, skal du kontakte en leverandør.

At bruge en **brugerdefineret forbindelseskomponent**, placeres i den  *\[dokumenter]\\Power BI Desktop\\brugerdefinerede Connectors* -mappe, og Juster sikkerhedsindstillingerne, som beskrevet i i følgende afsnit.

Du behøver ikke at justere sikkerhedsindstillingerne for at bruge **certificerede forbindelser**.

## <a name="data-extension-security"></a>Sikkerhed for dataudvidelse

Ændre data udvidelse sikkerhedsindstillinger, **Power BI Desktop** Vælg **fil > Indstillinger > Indstillinger > Sikkerhed**.

![Styre, om du vil indlæse brugerdefinerede forbindelser med indstillinger for udvidelse af datasikkerhed](media/desktop-connector-extensibility/data-extension-security-1.png)

Under **Dataudvidelser** kan du vælge mellem to niveauer af sikkerhed:

* (Anbefalet) Tillad kun, at certificerede udvidelser indlæses
* (Ikke anbefalet) Tillad, at alle udvidelser indlæses uden advarsel

Hvis du planlægger at bruge **brugerdefinerede Connectors** eller forbindelser, som du eller en tredjepart har udviklet, skal du vælge **"(Not Recommended) Tillad alle udvidelser til at indlæse uden advarsel"** . Vi anbefaler ikke denne sikkerhedsindstilling, medmindre du har fuld tillid til din brugerdefinerede Connectors. Da koden, der kan håndtere de legitimationsoplysninger, herunder at sende dem via HTTP, og Ignorer niveauerne for beskyttelse af personlige oplysninger.

På den **"(anbefales)"** sikkerhed indstilling, hvis der er brugerdefinerede connectorer på systemet, vises der en fejl, der beskriver de forbindelser, der ikke kan indlæses på grund af sikkerhed.

![En dialogboks, der beskriver brugerdefinerede Connectors, der ikke kan indlæses på grund af sikkerhedsindstillinger, i dette tilfælde TripPin](media/desktop-connector-extensibility/data-extension-security-2.png)

For at løse fejlen, og bruge disse forbindelser, skal du ændre dine indstillinger for at den **"(Not Recommended) Tillad alle udvidelser til at indlæse uden advarsel"** indstilling, som beskrevet tidligere. Genstart derefter **Power BI Desktop**.

## <a name="certified-connectors"></a>Certificerede forbindelser

Betragtes som en begrænset undersæt af dataudvidelser **Certified**. Få adgang til de certificerede forbindelser i den **Hent Data** dialog. Men, der oprettede connectoren tredjeparter udvikleren er ansvarlig for sin vedligeholdelse og support. Det er ikke ansvarlig for deres ydeevne eller fortsatte funktionen, mens Microsoft distribuerer forbindelserne.

Hvis du vil certificere en brugerdefineret forbindelse, skal du få din leverandør til at kontakte dataconnectors@microsoft.com.
