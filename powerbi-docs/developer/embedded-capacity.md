---
title: Kapacitet og SKU'er i integrerede Power BI-analyser
description: Om kapacitet og SKU'er i integrerede Power BI-analyser.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/11/2020
ms.openlocfilehash: f8c3bdf3e3f92d570205551a97389def2921fe98
ms.sourcegitcommit: 17aad73762579d6822383b27b96b1b63f87f2d6f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/14/2020
ms.locfileid: "77260451"
---
# <a name="capacity-and-skus-in-power-bi-embedded-analytics"></a>Kapacitet og SKU'er i integrerede Power BI-analyser

Når du går videre til produktion, kræver integreret analyse i Power BI en dedikeret kapacitet (*A*, *EM* eller *P* SKU) til udgivelse af integreret Power BI-indhold.

Kapacitet er et dedikeret sæt af ressourcer, som er reserveret til eksklusiv brug. Det gør det muligt for dig at publicere dashboards, rapporter og datasæt til brugere uden at være nødt til at købe licenser til hver enkelt bruger. Det garanterer også pålidelig, ensartet ydeevne for dit indhold.

>[!NOTE]
>Hvis du vil publicere, skal du bruge én Power BI Pro-konto.

## <a name="what-is-embedded-analytics"></a>Hvad er integreret analyse?

Integreret analyse i Power BI omfatter to løsninger:
* *Power BI Embedded* – Azure-tilbud
* Integration af Power BI som en del af *Power BI Premium* – Office-tilbud

### <a name="power-bi-embedded"></a>Power BI Embedded

Power BI Embedded er til ISV'er og udviklere, der vil integrere visualiseringer i deres programmer.

Programmer, der bruger Power BI Embedded, gør det muligt for brugerne at forbruge indhold, der er lagret på en Power BI Embedded-kapacitet.

### <a name="power-bi-premium"></a>Power BI Premium

[Power BI Premium](../service-premium-what-is.md) er kapacitetsmæssigt gearet mod virksomheder, som vil have en komplet BI-løsning, der giver adgang til en enkelt visning af virksomheden, kunderne og leverandørerne.

Power BI Premium er et SaaS-produkt, der giver mulighed for brugere at forbruge indhold gennem mobilapps, internt udviklede apps eller i Power BI-portalen (Power BI-tjeneste). Dette gør det muligt for Power BI Premium at levere en løsning til både interne og eksterne kundeorienterede programmer.

## <a name="capacity-and-skus"></a>Kapacitet og SKU'er

Hver enkelt kapacitet tilbyder en række SKU'er, og hver enkelt SKU indeholder forskellige ressourceniveauer til hukommelses- og computerkraft. Den type SKU, du har brug for, afhænger af den løsningstype, du vil udrulle.

Før du beslutter, hvilken SKU der skal købes, kan du gennemse oplysningerne i dette afsnit.
* Hvis du vil vide, hvilke arbejdsbelastninger der understøttes for hvert enkelt niveau, kan du se i artiklen [Konfigurer arbejdsbelastninger i en Premium-kapacitet](../service-admin-premium-workloads.md)
* Brug dette link til at [planlægge og teste din kapacitet](../service-premium-capacity-optimize.md#testing-approaches)

### <a name="power-bi-embedded-skus"></a>Power BI Embedded-SKU'er

Power BI Embedded leveres med en *A*-SKU.
* [Vær bevidst om, hvad din Power BI Embedded-kapacitet kan håndtere](https://powerbi.microsoft.com/blog/power-bi-developer-community-june-july-update/#Capacity-Plan)
* [Køb en *A*-SKU](../service-admin-premium-purchase.md#purchase-a-skus-for-testing-and-other-scenarios)

### <a name="power-bi-premium-skus"></a>Power BI Premium-SKU'er

Power BI Premium tilbyder to SKU'er, *P* og *EM*.
* [Forstå forskellene mellem *P*- og *EM*-SKU'er](../service-premium-what-is.md#subscriptions-and-licensing)
* [Køb en Premium-SKU](../service-admin-premium-purchase.md)

### <a name="which-sku-should-i-use"></a>Hvilken SKU skal jeg bruge?

I denne tabel finder du en oversigt over funktioner, den nødvendige kapacitet og den specifikke SKU, der kræves til hver enkelt. 

</br>
<table>
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<tbody>
<tr>
<td style="text-align: center"; colspan="2"><p><b>Funktion</b></p></td>
<td style="text-align: center">
<p><b>Power BI Embedded</b></p>
</td>
<td style="text-align: center"; colspan="2">
<p><b>Power BI Premium</b></p>
</td>
</tr>
<tr>
<td><p><em>Hvad forbruges?</em><p></td>
<td><p><em>Hvad forbruger?</em><p></td>
<td style="text-align: center"><p><em>A-SKU'er</br>(Azure)</em></p></td>
<td style="text-align: center"><p><em>EM-SKU'er</br>(Office)</em></p></td>
<td style="text-align: center"><p><em>P-SKU'er</br>(Office)</em></p></td>
</tr>
<tr>
<td>Integrer artefakter fra et Power BI-arbejdsområde</td>
<td>
</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="2">Power BI-rapporter</td>
<td>Et integreret program til din organisation</br>(brugeren ejer data)</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Et integreret program til dine kunder</br>(appen ejer data)</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="3">Power BI-indhold<br>(med en gratis Power BI-licens)</td>
<td>Power BI-tjeneste</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Power BI – Mobil</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>MS Office-apps</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
</tbody>
</table>

### <a name="capacity-considerations"></a>Kapacitetsovervejelser

I nedenstående tabel vises betalings- og forbrugsovervejelser pr. kapacitet.

</br>
<table>
<tbody>
<tr>
<td></td>
<td style="text-align: center;"><p><strong>Power BI Embedded</strong></p></td>
<td style="text-align: center;" colspan="2"><p><strong>Power BI Premium</strong></p></td>
</tr>
<tr>
<td><p><strong>Tilbud</strong></p></td>
<td style="text-align: center;"><p>Azure</p></td>
<td style="text-align: center;" colspan="2"><p>Office</p></td>
</tr>
<tr>
<td><p><strong>SKU</strong></p></td>
<td style="text-align: center;"><p>A</p></td>
<td style="text-align: center;"><p>EM</p></td>
<td style="text-align: center;"><p>P</p></td>
</tr>
<tr>
<td><p><strong>Fakturering</strong></td>
<td style="text-align: center;">Pr. time</td>
<td style="text-align: center;">Månedligt</td>
<td style="text-align: center;">Månedligt</td>
</tr>
<tr>
<td><p><strong>Forpligtelse</strong></td>
<td style="text-align: center;">Ingen</td>
<td style="text-align: center;">Månedligt eller årligt</td>
<td style="text-align: center;">Månedligt eller årligt</td>
</tr>
<tr>
<td valign="top"><p><strong>Forbrug</strong></td>
<td style="text-align: center;">Azure-ressourcer kan:</br>- <a href="azure-pbie-scale-capacity.md">skaleres op eller ned</a></br>- <a href="azure-pbie-pause-start.md">afbrydes midlertidigt og genoptages</a>
</td>
<td style="text-align: center;">Integrer i apps og i</br> Microsoft-programmer</td>
<td style="text-align: center;">Integrer i apps og</br> i Power BI-tjenesten</td>
</tr>
</tbody>
</table>

### <a name="sku-memory-and-computing-power"></a>SKU-hukommelses- og computerkraft

I nedenstående tabel beskrives ressourcerne og begrænsningerne for hver SKU.

| Kapacitetsnoder | V-kerner i alt | Backend-v-kerner | RAM (GB) | Frontend-v-kerner | DirectQuery/direkte forbindelser (pr. sek.) | Parallel opdatering af modeller |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0,5 | 2.5 | 0,5 | 3,75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7,5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| P4 | 64 | 32 | 200 | 32 | 240 | 48 |
| P5 | 128 | 64 | 400 | 64 | 480 | 96 |
| | | | | | | |

## <a name="next-steps"></a>De næste trin

> [!div class="nextstepaction"]
>[Integrer indhold for dine kunder](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Integrer til din organisation](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Integrer fra apps](embed-from-apps.md)