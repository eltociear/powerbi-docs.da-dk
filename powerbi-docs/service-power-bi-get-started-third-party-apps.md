---
title: Introduktion til tredjepartsapps i Power BI
description: Introduktion til tredjepartsapps i Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
LocalizationGroup: Get started
ms.openlocfilehash: 7ac6cee3331333b40119d6f5ab014b2e39d2ef23
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="get-started-with-third-party-apps"></a>Introduktion til tredjepartsapps
Med Power BI kan du bruge en app, som er bygget af en virksomhed eller en enkeltperson, som ikke er Microsoft. Du kan f.eks. bruge en app fra en tredjepart, som integreres i Power BI-felter i et specialbygget webprogram. Når du bruger en tredjepartsapp, bliver du bedt om at tildele det pågældende program visse tilladelser til din Power BI-konto og dine Power BI-ressourcer. Det er vigtigt, at du kun giver tilladelser til programmer, du kender og har tillid til. Tilladelser til et program kan tilbagekaldes når som helst. Se [Tilbagekald tilladelser for tredjepartsapps](#revoke).

Her er de adgangstyper, et program kan anmode om.

## <a name="power-bi-app-permissions"></a>Power BI-apptilladelser
* **Vis alle dashboards**
  
  * Denne tilladelse giver et program mulighed for at få vist alle dashboards, du har adgang til. Det omfatter dashboards, som du ejer, som du har fået fra indholdspakker, og som er blevet delt med dig og findes i grupper, du er medlem af. Programmet kan ikke foretage nogen ændringer i dashboardet. Blandt andet kan denne tilladelse bruges af et program til at integrere indholdet af dit dashboard i dets grænseflader.
* **Vis alle rapporter**
  
  * Denne tilladelse giver et program mulighed for at få vist alle rapporter, du har adgang til. Det omfatter rapporter, som du ejer, som du har fået fra indholdspakker, og som findes i grupper, du er medlem af. En del af at få vist rapporten betyder, at programmet også kan få vist dataene i den. Programmet kan ikke foretage nogen ændringer i dashboardet. Blandt andet kan denne tilladelse bruges af et program til at integrere indholdet af din rapport i dets grænseflader.
* **Vis alle datasæt**
  
  * Denne tilladelse giver et program mulighed for at opstille alle datasæt, du har adgang til. Det omfatter datasæt, som du ejer, som du har fået fra indholdspakker, og som findes i grupper, du er medlem af. Et program kan se navnene på alle dine datasæt samt deres struktur, herunder tabel- og kolonnenavne. Denne tilladelse giver rettigheder til at læse dataene i et datasæt. Tilladelsen giver ikke programmet ret til at tilføje eller foretage ændringer i et datasæt.
* **Læs og skriv alle datasæt**
  
  * Denne tilladelse giver et program mulighed for at opstille alle datasæt, du har adgang til. Det omfatter datasæt, som du ejer, som du har fået fra indholdspakker, og som findes i grupper, du er medlem af. Et program kan se navnene på alle dine datasæt samt deres struktur, herunder tabel- og kolonnenavne. Denne tilladelse giver rettigheder til at læse og skrive dataene i et datasæt. Programmet kan også oprette nye datasæt eller foretage ændringer i eksisterende datasæt. Det bruges ofte af et program til at sende data direkte til Power BI.
* **Få vist brugerens grupper**
  
  * Denne tilladelse giver programmet mulighed for at opstille alle grupper, du er medlem af. Det kan bruge denne tilladelse sammen med nogle af de andre tilladelser, der er angivet, for at få vist eller opdatere indhold for den pågældende gruppe. Programmet kan ikke foretage ændringer i selve gruppen.

<a name="revoke"/>

## <a name="revoke-third-party-app-permissions"></a>Tilbagekald tilladelser for tredjepartsapps
Du tilbagekalder tilladelser fra en tredjepartsapp ved at gå til Office 365-webstedet Mine apps.

På webstedet **Mine apps i Office 365** kan du tilbagekalde tilladelser fra tredjepart på følgende måde:

1. Gå til [Office 365-webstedet Mine apps](https://portal.office.com/myapps).
2. Find tredjepartsappen på siden **Mine apps**.
3. Hold musemarkøren over appfeltet, klik på knappen **(...)**, og klik på **Fjern**.
   
   ![](media/service-power-bi-get-started-third-party-apps/remove.png)

