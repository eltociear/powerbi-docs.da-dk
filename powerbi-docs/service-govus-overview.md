---
title: Power BI til kunder i den amerikanske stat – oversigt
description: 'For kunder i den amerikanske stat: Få mere at vide om funktionerne og begrænsningerne for tjenesten Power BI US Government'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Get started
ms.openlocfilehash: f2e3ad8528108e63a5573a3df502f90fee6d4c55
ms.sourcegitcommit: 2ae660a7b70fce23eb58b159d049eca44a664f2c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/30/2018
ms.locfileid: "52670158"
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
* Opret forbindelse til tjenester med [indholdspakker](consumer/end-user-connect-to-services.md)

## <a name="connectivity-between-government-and-public-azure-cloud-services"></a>Forbindelse mellem Government- og Public Azure Cloud-tjenester 

Azure er fordelt blandt adskillige cloud-tjenester. Som standard har lejere tilladelse til at åbne firewall-regler til en cloud-specifik forekomst, men tvær-cloudnetværk er anderledes og kræver åbning af specifikke firewall-regler for at kommunikere mellem tjenester. Hvis du er en Power BI-kunde, og du har eksisterende SQL-forekomster i den offentlige cloud, som du har brug for at få adgang til, skal du åbne specifikke firewallregler i SQL til Azure Government Cloud IP-plads, for de følgende datacentre:

* USGov Iowa
* USGov Virginia
* USGov Texas
* USGov Arizona

IP-pladser er tilgængelige i den offentlige cloud, men for government cloud-tjenesten, skal du oprette en anmodning om support i Azure for at bede om IP-områderne for ovenstående datacentre. 


## <a name="limitations-of-power-bi-us-government"></a>Begrænsninger for Power BI US Government
Nogle af de funktioner, der er tilgængelige i den kommercielle version af **Power BI-tjenesten**, er *ikke* tilgængelige i **Power BI-tjenesten** til kunder i den amerikanske stat. Power BI-teamet arbejder aktivt på at gøre disse funktioner tilgængelige for kunder i den amerikanske stat og vil opdatere denne artikel, når disse funktioner bliver tilgængelige.

* **Integrer i SharePoint Online** – Det er ikke muligt at integrere indhold i SharePoint Online ved hjælp af Power BI-webdelen.
* **Power BI US Government** er kun tilgængelig som en **Pro**-licens. Henvisninger til Power BI-licenser (gratis) på en administrationsportal (eller som brugere) kører i en kommerciel cloud til Power BI-tjenesten.
* **Overvågning** – overvågning er nu tilgængeligt via portalen Office 365 Security and Compliance fra juni 2018.
* **Power BI-indhold i Cortana** - Power BI-resultater vises ikke i søgeresultater i Cortana, der omfatter resultaterne for dit Power BI-indhold (dashboards, rapporter og apps) samt resultater, der viser Cortana-optimerede rapportsider for bestemte nøgleord.
* **Deling med eksterne brugere** – deling er tilladt inden for en Power BI-lejer. Fra juni 2018 kan du også dele med brugere uden for din Power BI-lejer. Se [Distribuer Power BI-indhold til eksterne gæstebrugere med Azure AD B2B](service-admin-azure-ad-b2b.md).
* **Forbrugsmålinger for dashboards og rapporter** – forbrugsmålinger er ikke tilgængelige for rapporter og dashboards. Kunder kan bruge data i overvågningsloggen til at få forbrugsoplysninger om indhold i deres organisation.

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

**Spørgsmål:** Min konto er klargjort i mere end én national cloud. Når jeg bruger **Power BI Desktop**, hvordan kan jeg så vælge, hvilken cloud jeg opretter forbindelse til?

**Svar:** Fra og med juli 2018-udgaven af **Power BI Desktop** kan du vælge, hvilken cloud du vil bruge, når du logger på **Power BI Desktop**.


## <a name="next-steps"></a>Næste trin
Du kan gøre mange forskellige ting med Power BI. Yderligere oplysninger og læring, herunder en artikel, der viser, hvordan du tilmelder dig tjenesten, findes i følgende ressourcer:

* [Tilmeld dig Power BI for US Government](service-govus-signup.md)
* <a href="https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government">Demo om Power BI US Government</a>
* [Automatiseret læring til Power BI](guided-learning/gettingstarted.yml?tutorial-step=1)
* [Kom i gang med Power BI-tjenesten](service-get-started.md)
* [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)

