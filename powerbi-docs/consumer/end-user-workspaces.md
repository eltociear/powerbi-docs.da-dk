---
title: Sådan organiseres indhold i arbejdsområder
description: Få mere at vide om arbejdsområder og arbejdsområderoller
author: mihart
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/22/2020
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: 801b5cf5400bbe1cc0487eef596ea3d1cdc5fb1e
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "82120145"
---
# <a name="collaborate-in-workspaces"></a>Samarbejd i et arbejdsområde

 *Arbejdsområder* er steder, hvor du kan samarbejde med kolleger om bestemt indhold. Arbejdsområder oprettes af *Power BI-designere* til at opbevare samlinger af dashboards og rapporter. Designeren kan herefter gruppere disse samlinger i en *app*, som kan distribueres til hele organisationen eller til bestemte personer eller grupper. 

 Alle, der bruger Power BI-tjenesten, har også et **Mit arbejdsområde**.  Mit arbejdsområde er din personlige sandkasse, hvor du selv kan oprette indhold.

 Du kan se dine arbejdsområder på **startsiden** i Power BI eller ved at vælge **Arbejdsområde** eller **Mit arbejdsområde** fra navigationsruden til venstre.

 ![navigationsruden, der viser to typer arbejdsområder](media/end-user-workspaces/power-bi-home.png)

## <a name="types-of-workspaces"></a>Typer af arbejdsområder
I **Mit arbejdsområde** gemmes alt det indhold, du ejer og opretter. Tænk på det som din personlige sandkasse eller arbejdsområde til dit eget indhold. For mange Power BI-*forbrugere* vil **Mit arbejdsområde** vedblive med at være tomt, fordi deres job ikke involverer oprettelse af nyt indhold. *Forbrugere* er defineret som dem, der forbruger data, som er oprettet af andre, og bruger disse data til at træffe forretningsbeslutninger. Hvis du opretter indhold, kan du overveje at læse [Power BI-artiklerne til designere](../create-reports/index.yml) i stedet for.

**App-arbejdsområder** indeholder alt indhold til en specifik app. Når en *designer* opretter en app, samler vedkommende alt det indhold, der er nødvendigt for at bruge den pågældende app, og inkluderer det i appen. Indholdet kan omfatte: dashboards, rapporter, apps og datasæt. Det er ikke alle apps, der indeholder disse tre indholdselementer. En app kan indeholde blot ét dashboard eller tre af hver indholdstype eller endda 20 rapporter. Det afhænger af, hvad *designeren* inkluderer i appen. Det mest almindelige er, at app-arbejdsområder til *forbrugere* ikke indeholder datasæt.

App-arbejdsområdet med salg af figner nedenfor indeholder tre rapporter og ét dashboard. 

![navigationsruden, der viser to typer arbejdsområder](media/end-user-workspaces/power-bi-app-workspace.png)

## <a name="roles-in-the-workspaces"></a>Roller i arbejdsområderne

Roller bestemmer, hvem der kan gøre hvad i et arbejdsområde, så teams kan samarbejde.  Når du giver adgang til et nyt arbejdsområde, kan *designere* føje enkeltpersoner eller grupper til en af arbejdsområderollerne: **Fremviser**, **Medlem**, **Bidragyder** eller **Administrator**. 


Du kan som *forbruger* i Power BI interagere i arbejdsområder ved hjælp af rollen **Læser**. Men en *designer* kan også tildele dig rollen som **Medlem** eller **Bidragyder**. Når du har læserrollen kan du få vist og interagere med indhold (dashboards, rapporter og apps), der er oprettet af andre og delt med dig. Eftersom rollen som læser ikke kan få adgang til det underliggende datasæt, er det en sikker måde at interagere med indhold på, uden at du behøver at bekymre dig om, at du "skader" de underliggende data.


Du kan finde en detaljeret liste over, hvad du kan foretage dig som *forbruger* med læserrollen, i [Power BI-funktioner til forbrugere](end-user-features.md).


### <a name="workspace-roles"></a>Roller i arbejdsområdet
Her er egenskaberne for de fire roller: administratorer, medlemmer, bidragydere og fremvisere. Al denne funktionalitet, undtagen visning og interaktion, kræver en Power BI Pro-licens.

|Funktion   | Administrator  | Medlem  | Bidragsyder  | Fremviser |
|---|---|---|---|---|
| Opdatere og slette arbejdsområdet.  | X  |   |   |   | 
| Tilføje/fjerne personer, herunder andre administratorer.  | X  |   |   |   |
| Tilføje medlemmer eller andre med lavere tilladelser.  |  X | X  |   |   |
| Publicer og opdater en app. |  X | X  |   |   |
| Dele et element eller dele en app.<sup>1</sup> |  X | X  |   |   |
| Give andre tilladelse til at dele elementer igen.<sup>1</sup> |  X | X  |   |   |
| Fremhæve apps på kollegaers startside |  X | X  |   |   |
| Fremhæve dashboards og rapporter på kollegaers startside |  X | X  | X |   |
| Oprette, redigere og slette indhold i arbejdsområdet.  |  X | X  | X  |   |
| Publicere rapporter til arbejdsområdet, slette indhold.  |  X | X  | X  |   |
| Oprette en rapport i et andet arbejdsområde, der er baseret på et datasæt i dette arbejdsområde.<sup>1</sup> |  X | X  | X  |   |
| Kopiere en rapport. | X | X | X |  |
| Få vist og interagere med et element.<sup>2</sup> |  X | X  | X  | X  |
| Læs data, der er gemt i dataflow i arbejdsområdet | X | X | X | X |

1. Bidragydere og medlemmer kan dele elementer i et arbejdsområde, hvis de har tilladelsen Del igen.

2. Selvom du ikke har en Power BI Pro-licens, kan du få vist og interagere med elementer i Power BI-tjenesten, hvis elementerne findes i et arbejdsområde i en Premium-kapacitet.

## <a name="licensing-workspaces-and-capacity"></a>Licenser, arbejdsområder og kapacitet
Licensering spiller også en rolle, da licenseringen bestemmer, hvad du kan og ikke kan gøre i et arbejdsområde. Mange funktioner kræver, at brugeren har en Power BI *Pro*-licens. De fleste *brugere* arbejder med en *gratis* licens. 

Hvis du har en gratis licens, og arbejdsområdet er gemt i en *Premium-kapacitet*, kan du få vist og interagere med indholdet i det pågældende arbejdsområde. Et diamantikon angiver de arbejdsområder og apps, der er gemt i en Premium-kapacitet.

![Valgte arbejdsområder](media/end-user-workspaces/power-bi-diamond.png) Du kan få mere at vide under [Hvilken licens har jeg?](end-user-license.md).



## <a name="next-steps"></a>Næste trin
* [Apps i Power BI](end-user-apps.md)    

* Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

