---
title: Power BI-tilladelser
description: Power BI-tilladelser
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 10/01/2018
ms.openlocfilehash: 51c43a19613381d39e0397864e55baed2022663c
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "79491358"
---
# <a name="power-bi-permissions"></a>Power BI-tilladelser

## <a name="permission-scopes"></a>Omfang af tilladelse

Med Power BI-tilladelser får et program mulighed for at foretage visse handlinger på en brugers vegne. Alle tilladelser skal være godkendt af en bruger for at være gyldige.

| Vist navn | Beskrivelse | Værdi for omfang |
| --- | --- | --- |
| Få vist alle datasæt |Appen kan få vist alle datasæt for den bruger, der er logget på, samt datasæt, som brugeren har adgang til. |Dataset.Read.All |
| Læs og skriv alle datasæt |Appen kan få vist og skrive til alle datasæt for den bruger, der er logget på, samt datasæt, som brugeren har adgang til. |Dataset.ReadWrite.All |
| Føj data til en brugers datasæt |Giver en app adgang til at tilføje eller slette rækker i en brugers datasæt. Denne tilladelse giver ikke appen adgangen til brugerens data. |Data.Alter_Any |
| Opret indhold |Appen kan automatisk oprette indhold og datasæt for en bruger. |Content.Create |
| Få vist brugergrupper |Appen kan få vist alle grupper, som den bruger, der er logget på, tilhører. |Group.Read |
| Se alle grupper |Appen kan få vist alle grupper, som den bruger, der er logget på, tilhører. |Group.Read |
| Læs og skriv alle grupper |Appen kan få vist og skrive til alle grupper for den bruger, der er logget på, samt grupper, som brugeren har adgang til. |Group.ReadWrite.All |
| Vis alle dashboards |Appen kan få vist alle dashboards for den bruger, der er logget på, samt dashboards, som brugeren har adgang til. |Dashboard.Read.All |
| Vis alle rapporter |Appen kan få vist alle rapporter for den bruger, der er logget på, samt rapporter, som brugeren har adgang til. Appen kan også se dataene i rapporter samt strukturen. |Report.Read.All |
| Læs og skriv alle rapporter |Appen kan få vist og skrive til alle rapporter for den bruger, der er logget på, samt rapporter, som brugeren har adgang til. Det giver ikke ret til at oprette en ny rapport. |Report.ReadWrite.All |
| Læs og skriv alle kapaciteter |Appen kan få vist og skrive til alle kapaciteter for den bruger, der er logget på, samt kapaciteter, som brugeren har adgang til. Det giver ikke ret til at oprette en ny kapacitet. |Capacities.ReadWrite.All |
| Læs alle kapaciteter |Appen kan få vist og skrive til alle kapaciteter for den bruger, der er logget på, samt kapaciteter, som brugeren har adgang til. Det giver ikke ret til at oprette en ny kapacitet. |Capacities.Read.All |
| Læs og skriv alt indhold i lejeren |Appen kan få vist og skrive til alle artefakter, f.eks. grupper, rapporter, dashboards og datasæt i Power BI. Forudsat at den bruger, der er logget på, er Power BI-tjenesteadministrator. |Tenant.ReadWrite.All |
| Vis alt indhold i lejeren |Appen kan få vist til alle artefakter, f.eks. grupper, rapporter, dashboards og datasæt i Power BI. Forudsat at den bruger, der er logget på, er Power BI-tjenesteadministrator. |Tenant.Read.All |

Et program kan anmode om tilladelser, når det forsøger at logge på en brugers side for første gang, ved at sende de ønskede tilladelser i parameteren for omfanget i forbindelse med kaldet. Hvis tilladelserne gives, returneres der et adgangstoken til appen, som kan bruges ved fremtidige API-kald. Adgangen kan kun bruges af et bestemt program.

> [!NOTE]
> Power BI-API'erne refererer stadig til arbejdsområder som grupper. Referencer til grupper betyder, at du arbejder med arbejdsområder.

## <a name="requesting-permissions"></a>Anmodning om tilladelser

Du kan kalde API'en for at godkende vha. et brugernavn og en adgangskode. Hvis du vil kunne handle på vegne af en anden bruger, skal vedkommende anmode om tilladelser, som denne bruger derefter godkender. Herefter sendes det genererede adgangstoken ved alle kommende kald. Vi følger standardprotokollen [OAuth 2.0](https://oauth.net/2/) i forbindelse med denne proces. Selvom den faktiske implementering kan variere, er der følgende elementer i OAuth-flowet for Power BI:

* **Logonbrugergrænsefladen** – Dette er en brugergrænseflade, som udvikleren kan benytte til at anmode om tilladelser. Det kræver, at brugeren logger på, hvis vedkommende ikke allerede er logget på. Brugeren skal også godkende de tilladelser, programmet anmoder om. I logonvinduet vises enten en adgangskode eller en fejlmeddelelse for en angivet URL-adresse til omdirigering.
  * Der skal angives en standard-URL-adresse til omdirigering i Power BI, som kan bruges af oprindelige programmer.
* **Godkendelseskode** – Godkendelseskoder returneres til webprogrammer efter logon via URL-adresseparametre i URL-adressen til omdirigering. Da de findes i parametre, er der en vis sikkerhedsrisiko. Webprogrammer skal ombytte godkendelseskoden med et Autorisationstoken
* **Autorisationstoken** – Autorisationstoken bruges til at godkende API-kald på vegne af en anden bruger. De vil være begrænset til et bestemt program. Tokens har en bestemt levetid, og når de udløber, skal de opdateres.
* **Opdateringstoken** – Når tokens udløber, er der en proces til opdatering af dem.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)