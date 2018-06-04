---
title: Arkiveret arbejdsområde i Power BI
description: Arkiveret arbejdsområde i Power BI efter at have administreret din Office 365-lejer
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 8b9fcf1c6121c4aeecfdf948b77493f1f2a7f825
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/04/2018
ms.locfileid: "34293622"
---
# <a name="power-bi-archived-workspace"></a>Arkiveret arbejdsområde i Power BI
Med Power BI kan alle tilmelde sig og begynde at bruge tjenesten i løbet af et par minutter.  Senere kan det være, at din organisations it-afdeling måske vælger at overtage administrationen af Power BI for brugere i din organisation.  Hvis it-afdelingen tager over, vil du få fordel af central administration af brugere og tilladelser i din organisation, og du får måske også gavn af strømlinet logon ved brug af samme brugernavn og adgangskode, du bruger til andre tjenester i din organisation. 

Alt indhold, du har oprettet, inden it-afdelingen begyndte at administrere Power BI, placeres i et arkiveret arbejdsområde i Power BI, hvortil der er adgang fra venstre navigationsrude i [Power BI](https://app.powerbi.com).  Du skal starte med at oprette nyt Power BI-indhold i Mit arbejdsområde, som sikres og administreres af din organisations it-afdeling.  Dit Arkiverede arbejdsområde vil fortsat eksistere, men der er begrænsninger i de handlinger, du kan udføre vedrørende indholdet i dit Arkiverede arbejdsområde.  Hvis du vil fjerne disse begrænsninger, skal du overføre indholdet fra dit Arkiverede arbejdsområde til Mit arbejdsområde, som administreres af din it-afdeling.

## <a name="restrictions-in-your-archived-workspace"></a>Begrænsninger i dit Arkiverede arbejdsområde
Intet indhold slettes fra Arkiveret arbejdsområde.  Du kan fortsætte med at hente data, oprette rapporter og dashboards samt opdatere datasæt.  Eksisterende brugere, som du har delt indhold med, vil stadigvæk også kunne se indholdet af deres Arkiverede arbejdsområde.

Der er nogle begrænsninger på indhold i dit Arkiverede arbejdsområde:

* **OneDrive for Business.  ** Du vil ikke længere kunne hente data eller opdatere fra OneDrive for Business for datasæt i dit Arkiverede arbejdsområde.  Hvis du forsøger at oprette forbindelse til denne kilde, modtager du en advarsel.
* **Deling af dashboards.  ** Du kan ikke dele dashboards med andre brugere fra dit Arkiverede arbejdsområde.  Alle brugere, som allerede har adgang, vil fortsat kunne få vist delte dashboards ved at åbne deres Arkiverede arbejdsområde.
* **Oprettelse af grupper.  ** Du kan ikke oprette grupper i dit Arkiverede arbejdsområde.
* **Adgang til Power BI-mobilapps.  **Selvom du stadigvæk kan få vist indholdet på nettet i dit Arkiverede arbejdsområde, vil dette indhold ikke længere blive vist i Power BI-mobilappsene.

## <a name="migrating-content-in-your-archived-workspace"></a>Overførsel af indhold i dit Arkiverede arbejdsområde
Hvis du fortsat ønsker at bruge Power BI, skal du oprette nyt indhold i Mit arbejdsområde, som administreres af din it-afdeling.   Du skal også planlægge at overføre eventuelt indhold i dit Arkiverede arbejdsområde til Mit arbejdsområde.  Du overfører indhold afhængigt af type indhold således:

* **Excel- eller Power BI Desktop-datasæt.  ** Overfør disse datasæt ved at skifte fra dit Arkiverede arbejdsområde til Mit arbejdsområde og ved at uploade Excel- eller Power BI Desktop-filen igen ved at klikke på knappen "Mine Data".  Hvis du har angivet planlagt opdatering, skal du konfigurere disse indstillinger for det nye datasæt igen i Mit arbejdsområde.
* **Andre datasæt.  ** Skift til Mit arbejdsområde, og klik derefter på knappen Hent Data for at oprette forbindelse til andre datasæt, som du har oprettet i dit Arkiverede arbejdsområde.  Du skal muligvis angive sikkerheds- eller forbindelsesoplysningerne igen.
* **Rapporter.  ** Rapporter, der var indeholdt i Excel- eller Power BI Desktop-filer eller rapporter, der blev installeret som en del af indholdspakker bliver automatisk genoprettet, når du igen uploader den tilsvarende Excel- eller Power BI Desktop-fil eller opretter forbindelse til indholdspakken.  Hvis du har oprettet dine egne rapporter via Power BI-tjenesten, skal du genskabe disse rapporter i Mit arbejdsområde.
* **Dashboards.  ** Dashboards, der er installeret som en del af indholdspakker, bliver automatisk genoprettet, når du igen opretter forbindelse til indholdspakken i Mit arbejdsområde.  Hvis du har oprettet dine egne dashboards via Power BI-tjenesten, skal du genskabe disse dashboards i Mit arbejdsområde.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

