---
title: Arkiveret arbejdsområde i Power BI
description: Arkiveret arbejdsområde i Power BI efter at have administreret din Office 365-lejer
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 8636ec85cb56e87f28a93f9f1f89989ffcc097bb
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973137"
---
# <a name="power-bi-archived-workspace"></a>Arkiveret arbejdsområde i Power BI

Med Power BI kan alle tilmelde sig og begynde at bruge tjenesten i løbet af et par minutter.  Det kan være, at din organisations it-afdeling senere måske vælger at overtage administrationen af Power BI for brugere i organisationen.  Hvis dette sker, kan du nyde godt af central administration af brugere og tilladelser i organisationen. Du kan muligvis også drage fordel af strømlinet logon ved hjælp af det samme brugernavn og den samme adgangskode, som du bruger til andre tjenester i organisationen.

Alt indhold, du har oprettet, inden it-afdelingen begyndte at administrere Power BI, placeres i Arkiveret arbejdsområde i Power BI, som du har adgang til via venstre navigationsrude i [Power BI](https://app.powerbi.com). Du skal starte med at oprette nyt Power BI-indhold i Mit arbejdsområde, som sikres og administreres af din organisations it-afdeling.  Dit Arkiveret arbejdsområde vil fortsat eksistere, men der er begrænsninger i de handlinger, du kan udføre vedrørende indholdet i dit Arkiveret arbejdsområde.  Hvis du vil fjerne disse begrænsninger, skal du overføre indholdet fra dit Arkiveret arbejdsområde til Mit arbejdsområde, som administreres af din it-afdeling.

## <a name="restrictions-in-your-archived-workspace"></a>Begrænsninger i dit Arkiveret arbejdsområde

Power BI sletter ikke indhold fra dit Arkiveret arbejdsområde. Du kan fortsætte med at hente data, oprette rapporter og dashboards samt opdatere datasæt. Eksisterende brugere, som du har delt indhold med, kan også stadig få vist indholdet i deres Arkiveret arbejdsområde. Der er nogle begrænsninger på indhold i dit Arkiveret arbejdsområde:

* **OneDrive for Business**: Du kan ikke længere hente eller opdatere data fra OneDrive for Business i forbindelse med datasæt i dit Arkiveret arbejdsområde.  Hvis du forsøger at oprette forbindelse til denne kilde, får du vist en advarsel.

* **Deling af dashboards**: Du kan ikke dele dashboards med andre brugere fra dit Arkiveret arbejdsområde.  Alle brugere, som allerede har adgang, vil fortsat kunne få vist delte dashboards ved at åbne deres Arkiveret arbejdsområde.

* **Oprettelse af grupper**: Du kan ikke oprette grupper i dit Arkiveret arbejdsområde.

* **Adgang på Power BI-mobilapps**: Selvom du stadig kan få vist indholdet på internettet i dit Arkiveret arbejdsområde, vises dette indhold ikke længere i Power BI-mobilappsene.

## <a name="migrating-content-in-your-archived-workspace"></a>Overførsel af indhold i dit Arkiveret arbejdsområde

Hvis du fortsat vil bruge Power BI, skal du oprette nyt indhold i Mit arbejdsområde. Du skal også planlægge at overføre eventuelt indhold i dit Arkiveret arbejdsområde til Mit arbejdsområde.  Du overfører indhold afhængigt af type indhold således:

* **Datasæt fra Excel eller Power BI Desktop**: Overfør disse datasæt ved at skifte fra dit Arkiveret arbejdsområde til Mit arbejdsområde og uploade Excel- eller Power BI Desktop-filen igen ved at klikke på knappen **Mine data**.  Hvis du konfigurerer planlagt opdatering, skal du konfigurere disse indstillinger igen for det nye datasæt i Mit arbejdsområde.

* **Andre datasæt**: Skift til Mit arbejdsområde, og klik derefter på knappen **Hent data** for at genoprette forbindelsen til andre datasæt, som du oprettede i dit Arkiveret arbejdsområde.  Du skal muligvis angive sikkerheds- eller forbindelsesoplysningerne igen.

* **Rapporter**: Rapporter, der er indeholdt i Excel- eller Power BI Desktop-filer, genskabes automatisk, når du uploader den tilsvarende Excel eller Power BI Desktop-fil igen. Rapporter, der er installeret som en del af en indholdspakke, genskabes også, når du genopretter forbindelsen til indholdspakken. Hvis du oprettede dine egne rapporter via Power BI-tjenesten, skal du genskabe disse rapporter i Mit arbejdsområde.

* **Dashboards**: Dashboards, der er installeret som en del af indholdspakker, genskabes automatisk, når du genopretter forbindelsen til indholdspakken i Mit arbejdsområde. Hvis du oprettede dine egne dashboards via Power BI-tjenesten, skal du genskabe disse dashboards i Mit arbejdsområde.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

