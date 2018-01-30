---
title: "Power BI til kunder i den amerikanske stat – oversigt"
description: "For kunder i den amerikanske stat: Få mere at vide om funktionerne og begrænsningerne for tjenesten Power BI US Government"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 9c8e2b44c128db283bef65198204e4aee1bfdd7a
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2017
---
# <a name="power-bi-for-us-government-customers"></a>Power BI til kunder i den amerikanske stat
**Power BI-tjenesten** har en tilgængelig version for kunder i den amerikanske stat som en del af abonnementer for **Office 365 US Government Community**. Versionen af **Power BI-tjenesten**, der er beskrevet i denne artikel, er udviklet specielt til kunder i den amerikanske stat og er separat og adskiller sig fra den kommercielle version af **Power BI-tjenesten**.

![](media/service-govus-overview/service_usgov_overview-1.png)

I afsnittene nedenfor beskrives de *funktioner*, der er tilgængelige for US Government-versionen af **Power BI-tjenesten**, der afdækkes nogle af *begrænsningerne*, vises **Ofte stillede spørgsmål** og svar (herunder hvordan du tilmelder dig), og der er links til flere oplysninger.

## <a name="features-of-power-bi-us-government"></a>Funktioner i Power BI US Government
Det er vigtigt at bemærke, at **Power BI US Government** kun er tilgængelig som en **Pro-licens** og ikke er tilgængelig som en gratis licens. Visse funktioner i Power BI-tjenesten er tilgængelige i **Power BI US Government**-versionen af tjenesten.

Følgende funktioner er tilgængelige for **Power BI US Government**-kunder, som de gælder for funktionalitet med **Pro**-licens:

* Opret og få vist dashboards og rapporter
* [Grænser for datakapacitet](service-admin-manage-your-data-storage-in-power-bi.md)
* [Planlagt dataopdatering](refresh-data.md)
* Teamdashboards, der kan opdateres
* Active Directory-grupper til deling og administration af adgangskontrol
* [Importér data](service-get-data.md) og rapporter fra Excel-, CSV- og Power BI Desktop-filer
* Datastyringsgateway
* Alle data er krypteret i både Azure SQL- og Blob-lager til Power BI
* Opret forbindelse til tjenester med [indholdspakker](service-connect-to-services.md)

## <a name="limitations-of-power-bi-us-government"></a>Begrænsninger for Power BI US Government
Nogle af de funktioner, der er tilgængelige i den kommercielle version af **Power BI-tjenesten**, er *ikke* tilgængelige i **Power BI-tjenesten** til kunder i den amerikanske stat. Power BI-teamet arbejder aktivt på at gøre disse funktioner tilgængelige for kunder i den amerikanske stat og vil opdatere denne artikel, når disse funktioner bliver tilgængelige.

* **Power BI US Government** er kun tilgængelig som en **Pro**-licens. Henvisninger til Power BI-licenser (gratis) på en administrationsportal (eller som brugere) kører i en kommerciel cloud til Power BI-tjenesten.
* **Overvågning** – overvågning er ikke tilgængelig via portalen Office 365 Security and Compliance.

Hvis du har gratis **Power BI**-licenser knyttet til din konto, kører disse konti i en kommerciel version af **Power BI**-tjenesten og er ikke en del af **Power BI US Government**-tilbuddet. For de gratis kontis vedkommende kan der opstå følgende problemer:

* Gateway, Mobil og Desktop ikke kan godkendes
* Du kan ikke få adgang til kommercielle Azure-datakilder
* PBIX-filer skal manuelt uploades fra kommerciel
* Power BI-mobilapps er ikke tilgængelige

Kontakt din kontorepræsentant for at afhjælpe problemer.

## <a name="frequently-asked-questions-faq-for-the-us-government-version-of-the-power-bi-service"></a>Ofte stillede spørgsmål til US Government-versionen af Power BI-tjenesten
Følgende spørgsmål (og svar) er angivet, så du hurtigt kan få oplysninger, du har brug for om tjenesten.

**Spørgsmål:** Hvordan overfører jeg mine kommercielle **Power BI**-data til **Power BI-tjenesten** for US Government-versionen?

**Svar:** Administratoren skal oprette en ny forekomst af **Power BI** under et separat abonnement, der er specifikt for den amerikanske stat. Du kan derefter replikere dine kommercielle data i **Power BI-tjenesten** for US Government-versionen, fjerne din kommercielle licens og knytte det eksisterende domæne til den nye tjeneste, der er specifik for den amerikanske stat.

**Spørgsmål:** Hvorfor kan jeg ikke oprette forbindelse til en bestemt indholdspakke?

**Svar:** Du skal sikre dig, at dit abonnement er aktiveret, før du opretter forbindelse til indholdspakken.

**Spørgsmål:** Jeg er interesseret i at få **Power BI** til min amerikanske statsorganisation. Hvordan kommer jeg i gang?

**Svar:** Tilmelding (kaldes ofte *onboarding*) kan være forskellig, afhængigt af din eksisterende licens og dit abonnement. Se artiklen [Tilmeld dig Power BI US Government](service-govus-signup.md) for at få flere oplysninger.

**Spørgsmål:** Er URL-adressen til at oprette forbindelse til **Power BI** for US Government-versionen anderledes end URL-adressen til den kommercielle **Power BI**?

**Svar:** Ja, URL-adresserne er forskellige. Følgende tabel indeholder hver URL-adresse:

| URL-adresse til kommerciel version | URL-adresse til US Government-version |
| --- | --- |
| https://app.powerbi.com/ |[https://app.powerbigov.us](https://app.powerbigov.us) |

## <a name="next-steps"></a>Næste trin
Du kan gøre mange forskellige ting med Power BI. Yderligere oplysninger og læring, herunder en artikel, der viser, hvordan du tilmelder dig tjenesten, findes i følgende ressourcer:

* [Tilmeld dig Power BI for US Government](service-govus-signup.md)
* <a href="https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government">Demo om Power BI US Government</a>
* [Automatiseret læring til Power BI](guided-learning/gettingstarted.yml#step-1)
* [Kom i gang med Power BI-tjenesten](service-get-started.md)
* [Kom i gang med Power BI Desktop](desktop-getting-started.md)
