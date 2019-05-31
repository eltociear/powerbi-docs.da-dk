---
title: Power BI Kom i gang med tredjeparts-apps
description: Power BI Kom i gang med tredjeparts-apps
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.cunstom: ''
ms.date: 08/10/2017
LocalizationGroup: Get started
ms.openlocfilehash: 11afe27ffbca295eec67fd07731cc646bcca56dc
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "64769688"
---
# <a name="get-started-with-third-party-apps"></a>Kom i gang med tredjepartsapps

Med Power BI kan du bruge en app, som er bygget af en virksomhed eller en enkeltperson, som ikke er Microsoft. Du kan f.eks, bruge en tredjeparts-app, som integreres i Power BI-felter i et webprogram med brugerdefinerede. Når du bruger en tredjepartsapp, du bliver bedt om at tildele det pågældende program visse tilladelser til din Power BI-konto og ressourcer. Det er vigtigt, at du kun giver tilladelser til programmer, du kender og har tillid til. Tilladelser til et program kan tilbagekaldes når som helst. Se [Tilbagekald tilladelser for tredjepartsapps](#revoke).

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

Du tilbagekalder tilladelser til en tredjeparts-app ved at gå til mine Apps i Office 365-webstedet.

På den **Office 365 mine apps** websted, sådan tilbagekalde tilladelser fra tredjepart:

1. Gå til [Office 365-webstedet Mine apps](https://portal.office.com/myapps).

2. På den **mine apps** , finde appen fra tredjepart.

3. Hold musemarkøren over appfeltet, klik på knappen **(...)** , og klik på **Fjern**.

   ![Fjern](media/service-power-bi-get-started-third-party-apps/remove.png)