---
title: Tredjeparts-connectors, der er tillid til, i Power BI
description: Sådan opnår du er tillid til en signeret tredjeparts-connector i Power BI
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 05db20b2f83f10409339fad949874fc1076a6b98
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83285963"
---
# <a name="trusted-third-party-connectors"></a>Tredjepartsconnectors, der er tillid til

## <a name="why-do-you-need-trusted-third-party-connectors"></a>Hvorfor har du brug for tredjeparts-connectors, der er tillid til?

I Power BI anbefaler vi generelt at bevare niveauet for "sikkerhed for dataudvidelse" på det høje niveau, hvilket forhindrer indlæsning af kode, der ikke er certificeret af Microsoft. Der kan dog være mange tilfælde, hvor du vil indlæse bestemte connectors – dem, du har skrevet, eller dem, du har fået af en konsulent eller leverandør uden for Microsoft-certificeringsstien.

Udvikleren af en given Connector kan signere den med et certifikat og give dig de oplysninger, du har brug for, til at indlæse den sikkert uden at sænke dine sikkerhedsindstillinger.

Hvis du vil vide mere om sikkerhedsindstillingerne, kan du læse om dem [her](https://docs.microsoft.com/power-bi/desktop-connector-extensibility).

## <a name="using-the-registry-to-trust-third-party-connectors"></a>Brug af registreringsdatabasen til at opnå tillid til tredjeparts-connectors

Du opnår tillid til tredjeparts-connectors i Power BI ved at vise aftrykket af det certifikat, du vil have tillid til, i en bestemt registreringsdatabaseværdi. Hvis denne miniature matcher certifikatets aftryk på den connector, du vil indlæse, kan du indlæse den på sikkerhedsniveauet 'Anbefalet' i Power BI. 

Stien til registreringsdatabasen er HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI Desktop. Kontrollér, at stien findes, eller opret den. Vi har valgt denne placering, da den primært styres af it-politikken og kræver, at du har administrationsadgang til den lokale maskine for at redigere den. 

![Power BI Desktop-registreringsdatabasen uden angivelse af tredjepartsnøgler, der er tillid til](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

Tilføj en ny værdi under den sti, der er angivet ovenfor. Typen skal være "multi-String Value" (REG_MULTI_SZ), og den skal have navnet "TrustedCertificateThumbprints" 

![Power BI Desktop-registreringsdatabase med en post for tredjeparts-connectors, der er tillid til, men ingen nøgler](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

Tilføj aftryk for de certifikater, du vil have tillid til. Du kan tilføje flere certifikater ved at bruge "\0" som en afgrænser eller ved at højreklikke > rediger i registreringseditoren og placere hvert aftryk på en ny linje. Eksempelaftryk hentes fra et selvsigneret certifikat. 

 ![Power BI Desktop-registreringsdatabasen med angivelse af tredjepartsnøgler, der er tillid til](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

Hvis du har fulgt vejledningen korrekt og har fået det rette aftryk af udvikleren, skulle du nu kunne stole på, at der er tillid til connectors, der er signeret med det tilknyttede certifikat.

## <a name="how-to-sign-connectors"></a>Sådan signeres connectors

Hvis du har en connector, som du eller en udvikler skal bruge til at signere, kan du læse om det i Power Query-dokumentationen [her](https://docs.microsoft.com/power-query/handlingconnectorsigning).
