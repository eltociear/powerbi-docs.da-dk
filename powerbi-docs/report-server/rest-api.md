---
title: Foretag udvikling med REST API'er til Power BI-rapportserver
description: REST API leverer programadgang til objekterne i et katalog til Power BI-rapportserver.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 08c8075fe275ff1472d3e9845f954ef4d029b373
ms.sourcegitcommit: 49570ab8f5b5cd5bab4cd388f4281b1372bcb80b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/09/2018
ms.locfileid: "35250424"
---
# <a name="develop-with-the-rest-apis-for-power-bi-report-server"></a>Foretag udvikling med REST API'er til Power BI-rapportserver

Power BI-rapportserver understøtter REST API'er (Representational State Transfer). REST API'er er tjenesteslutpunkter, der understøtter et sæt HTTP-handlinger (metoder), der leverer, opretter, henter, opdaterer eller sletter adgang for ressourcer i en rapportserver.

REST API leverer programadgang til objekterne i et katalog til Power BI-rapportserver. Mapper, rapporter, KPI'er, datakilder, datasæt, opdateringsplaner, abonnementer osv. er eksempler på objekter. Med brug af REST API kan du, f.eks. navigere i mappehierarkiet, finde indholdet af en mappe eller hente en rapportdefinition. Du kan desuden oprette, opdatere og slette objekter. Eksempler på arbejdet med objekter er upload af en rapport, afvikling af en opdateringsplan, sletning af en mappe osv.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-hybrid-note.md)]

## <a name="components-of-a-rest-api-requestresponse"></a>Komponenter i anmodning/svar for en REST API

Et anmodning/svar-par til en REST API kan opdeles i fem komponenter:

* **Anmodningens URI**, der består af: `{URI-scheme} :// {URI-host} / {resource-path} ? {query-string}`. Selvom anmodningens URI er medtaget i anmodningsmeddelelsens header, tager vi den her ud særskilt, fordi de fleste sprog eller frameworks kræver, at du overfører den særskilt fra anmodningsmeddelelsen.
  
  * URI-skema: Angiver den protokol, der bruges til at sende anmodningen. For eksempel `http` eller `https`.
  * URI-vært: Angiver domænenavnet eller IP-adressen for den server, hvor REST-tjenestens slutpunkt findes, f.eks. `myserver.contoso.com`.
  * Ressourcesti: Angiver den ressource eller samling af ressourcer, der kan indeholde flere segmenter, der bruges af tjenesten til at bestemme valget af disse ressourcer. Eksempel: `CatalogItems(01234567-89ab-cdef-0123-456789abcdef)/Properties` kan bruges til at hente de angivne egenskaber for CatalogItem.
  * Forespørgselsstreng (valgfrit): Stiller flere enkle parametre til rådighed, f.eks API'ens version eller kriterier for udvælgelse af ressourcer.
* Felter i HTTP-anmodningens meddelelsesheader:
  
  * En krævet [HTTP-metode](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) (også kaldet en handling eller et verbum), der informerer tjenesten om, hvilken type handling du anmoder om. REST API'er til rapporteringsservices understøtter metoderne DELETE, GET, HEAD, PUT, POST, og PATCH.
  * Valgfrie yderligere felter i headeren som krævet af den angivne URI og HTTP-metode.
* Valgfrie HTTP-felter til **brødteksten i anmodningsmeddelelsen** til understøttelse af URI og HTTP-handling. POST-handlinger indeholder f.eks. MIME-kodede objekter, der sendes som komplekse parametre. For POST- eller PUT-handlinger skal MIME-kodningstypen for brødteksten også angives i `Content-type`-anmodningens header. Nogle tjenester kræver, at du bruger en bestemt MIME-type, f.eks. `application/json`.
* HTTP-felter i **svarmeddelelsens header**:
  
  * En [HTTP-statuskode](http://www.w3.org/Protocols/HTTP/HTRESP.html), der kan være alt lige fra 2xx succeskoder til 4xx eller 5xx fejlkoder. Alternativt kan der også returneres en statuskode, der er defineret i tjenesten, som angivet i dokumentationen til API.
  * Valgfrie yderligere headerfelter, som kræves for at understøtte anmodningens svar, f.eks en `Content-type`-svarheader.
* Valgfrie HTTP-felter til **brødteksten i svarmeddelelsen**:
  
  * MIME-kodede svarobjekter returneres i brødteksten i HTTP-svaret, f.eks. et svar fra en GET-metode, der returnerer data. Disse objekter returneres typisk i et struktureret format, f.eks. JSON eller XML, som angivet i `Content-type`-svarheaderen.

## <a name="api-documentation"></a>API-dokumentation

Til en moderne REST API er der for brug for moderne API-dokumentation. REST API er bygget på OpenAPI-specifikationen (også kaldet swagger-specifikationen), og dokumentation er tilgængelig på [SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0). Ud over at dokumentere API'en hjælper SwaggerHub med at oprette et klientbibliotek i et sprog efter eget valg – JavaScript, TypeScript, C#, Java, Python, Ruby og meget mere.

## <a name="testing-api-calls"></a>Test af API-kald

[Fiddler](http://www.telerik.com/fiddler) er et værktøj til test af HTTP-anmodnings-/svarmeddelelser. Fiddler er en gratis webfejlfindingsproxy, der kan opfange dine REST-anmodninger, og som gør det lettere at diagnosticere HTTP-anmodnings-/svarmeddelelser.

## <a name="next-steps"></a>Næste trin

Se de tilgængelige API'er på [SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0).

Der findes eksempler på [GitHub](https://github.com/Microsoft/Reporting-Services). Eksemplet omfatter en HTML5-app, der er baseret på TypeScript, React og webpack sammen med et PowerShell-eksempel.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)