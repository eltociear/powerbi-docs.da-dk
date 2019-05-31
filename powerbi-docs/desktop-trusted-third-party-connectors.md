---
title: Der er tillid til tredjeparts-forbindelser i Powerbi
description: Hvordan kan have tillid til en signeret tredjeparts-connector i Power BI
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 30b7457c6149320c43f24b967a842382821b01b1
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607789"
---
# <a name="trusting-third-party-connectors"></a>Tillid tredjeparts-forbindelser

## <a name="why-do-you-need-trusted-third-party-connectors"></a>Hvorfor skal du har tillid til tredjeparts-connectors?

I Power BI, Generelt anbefales det at holde din 'udvidelse datasikkerhed' niveau på højere niveau, hvilket forhindrer indlæsning af kode, der ikke er certificeret af Microsoft. Der kan dog være mange tilfælde, hvor du vil indlæse specifikke forbindelser – dem, du har skrevet, eller dem, der er leveret til dig af en konsulent eller leverandør uden for Microsoft-certificering stien.

Udvikleren af en bestemt connector kan logge på med et certifikat og giver dig de oplysninger, skal du indlæse dem på en sikker måde uden at sænke sikkerhedsindstillingerne.

Hvis du vil vide mere om sikkerhedsindstillingerne, kan du læse om dem [her](https://docs.microsoft.com/power-bi/desktop-connector-extensibility).

## <a name="using-the-registry-to-trust-third-party-connectors"></a>Ved hjælp af registreringsdatabasen kan have tillid til tredjeparts-forbindelser

Tillid tredjeparts-forbindelser i Power BI gøres ved at få vist aftrykket af det certifikat, du har tillid til en værdi i den angivne registreringsnøgle. Hvis dette aftryk stemmer overens med aftrykket af det certifikat på forbindelsen, du vil indlæse, vil du kunne indlæse dem i 'Anbefalet' sikkerhedsniveauet for Power BI. 

Registreringsdatabasestien til er HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI Desktop. Sørg for, at stien findes, eller Opret den. Vi har valgt denne placering på grund af det er primært styres af IT-politik, samt der skal have adgang til administration af lokale computer til at redigere. 

![Angiv Power BI Desktop registreringsdatabasen med nogen der er tillid til tredjeparts-nøgler](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

Tilføj en ny værdi under den sti, der er angivet ovenfor. Typen skal være "Flere strengværdi" (REG_MULTI_SZ), og det skal kaldes "TrustedCertificateThumbprints" 

![Power BI Desktop registreringsdatabasen med en post for der er tillid til tredjeparts-forbindelser, men ingen nøgler](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

Tilføj thumbprints af de certifikater, som du har tillid til. Du kan tilføje flere certifikater ved hjælp af "\0" som en afgrænser eller i registreringsdatabasen editor, højre -> skal du klikke på Rediger og placerer hver aftryk på en ny linje. Eksempel aftryk er taget fra et selvsigneret certifikat. 

 ![Power BI Desktop registreringsdatabasen med tillid til tredjeparts-nøgler](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

Hvis du har fulgt instruktionerne korrekt, og du har fået tildelt de korrekte aftryk af dine udvikler, bør du nu kunne sikkert trust forbindelser signeret med det tilknyttede certifikat.

## <a name="how-to-sign-connectors"></a>Sådan logger du forbindelser

Hvis du har en connector, du eller en udvikler, skal du logge, kan du læse om det i Power-forespørgsel dokumenter [her](https://docs.microsoft.com/power-query/handlingconnectorsigning).
