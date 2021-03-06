---
title: Power BI til US Government-kunder – oversigt
description: US Government-kunder kan føje et Power BI Pro-abonnement til deres Microsoft 365 Government-abonnement. Få mere at vide om, hvordan du tilmelder dig og gennemser tilgængelige funktioner i denne tjenestebeskrivelse.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/02/2020
ms.author: kfollis
ms.custom: licensing support
LocalizationGroup: Get started
ms.openlocfilehash: 2b5481e3d0b84f81a9cdee827df27c90e32a7e84
ms.sourcegitcommit: ae9e698b082598f37242080a3ad3dd0b3be08478
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/04/2020
ms.locfileid: "89474792"
---
# <a name="power-bi-for-us-government-customers"></a>Power BI til US Government-kunder

Denne artikel er for kunder inden for de amerikanske offentlige myndigheder, der udruller Power BI som en del af en Microsoft 365-plan til offentlige myndigheder. Planer til offentlige myndigheder er designet til at opfylde de særlige behov hos organisationer, der overholder amerikanske standarder og sikkerhedsstandarder. Power BI-tjenesten, der er udviklet til US Government-kunder, adskiller sig fra den kommercielle version af Power BI-tjenesten. Disse funktionsforskelle og egenskaber er beskrevet i følgende afsnit.

## <a name="add-power-bi-to-your-microsoft-365-government-plan"></a>Føj Power BI til din Microsoft 365-plan til offentlige myndigheder

Før du kan få et Power BI US Government-abonnement og tildele licenser til brugere, skal du tilmelde dig et Microsoft 365-abonnement til offentlige myndigheder. Hvis din organisation allerede har en Microsoft 365-plan for offentlige myndigheder, skal du gå videre til [Køb et Power BI Pro-abonnement til offentlige myndigheder](#buy-a-power-bi-pro-subscription-for-government-customers).

### <a name="enroll-in-a-microsoft-365-government-plan"></a>Tilmeld dig en Microsoft 365-plan til offentlige myndigheder

Hvis du er ny kunde, skal du validere din organisations berettigelse, før du kan tilmelde dig en Microsoft 365-plan til offentlige myndigheder.  Kom i gang ved at udfylde [formularen til bekræftelse af berettigelsen til Microsoft 365 til offentlige myndigheder](https://www.microsoft.com/microsoft-365/government/eligibility-validation). Du kan sikre dig, at du vælger den rette plan til din organisation ved at gennemse [tjenestebeskrivelserne for Microsoft 365 til de amerikanske offentlige myndigheder](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government).

> [!NOTE]
> Hvis du allerede har udrullet Power BI i et kommercielt miljø og gerne vil migrere til US Government-cloudmiljøet, skal du føje et nyt Power BI Pro-abonnement til dit Microsoft 365-abonnement til offentlige myndigheder. Derefter skal du replikere de kommercielle data til Power BI-tjenesten til US Government, fjerne kommercielle licenstildelinger fra brugerkonti og derefter tildele en Power BI Pro Government-licens til brugerkontiene.
>
>
### <a name="buy-a-power-bi-pro-subscription-for-government-customers"></a>Køb et Power BI Pro-abonnement til offentlige kunder

Når du har udrullet Microsoft 365, kan du tilføje et Power BI Pro-abonnement. Følg den trinvise vejledning i, hvordan du [tilmelder din US Government-organisation](service-govus-signup.md), for at købe Power BI Pro Government-tjenesten. Køb tilstrækkeligt mange licenser til alle de brugere, der skal bruge Power BI, og tildel derefter disse licenser til individuelle brugerkonti.

> [!IMPORTANT]
> Power BI US Government er ikke tilgængelig som en *gratis* licens. Hver enkelt bruger skal tildeles en *Pro-licens* for at få adgang til Government Community Cloud. Hvis en brugerkonto har fået tildelt en gratis licens, er brugeren kun autoriseret til at få adgang til den kommercielle cloud og vil opleve problemer med godkendelse og adgang. Hvis du har købt Power BI Premium, behøver du ikke at tildele Pro-licenser for at aktivere brugeradgang.  Alle brugere i organisationen har adgang til rapporter, der er delt med dem, så længe rapporterne er udgivet til en Premium-kapacitet. Hvis du vil gennemgå forskellene mellem licenstyper, skal du se [Funktioner i Power BI-tjenesten efter licenstype](../fundamentals/service-features-license-type.md).
>

## <a name="government-cloud-instances"></a>Instanser i det offentlige cloud

Microsoft 365 indeholder forskellige miljøer, så de offentlige myndigheder kan opfylde de forskellige overensstemmelseskrav. Du kan finde flere oplysninger om hvert miljø under:

* [Microsoft 365 GCC (Government Community Cloud)](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc) er udviklet til forbundsmyndigheder samt statslige og lokale myndigheder.

* [Microsoft 365 GCC High (Government Community Cloud High)](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc-high-and-dod) er udviklet til forbundsmyndigheder, forsvarsindustrien, rumfartsindustrien og andre organisationer, der opbevarer kontrollerede ikke-klassificerede oplysninger. Dette miljø egner sig til nationale sikkerhedsorganisationer og virksomheder med ITAR-data (International Traffic in Arms Regulations) eller DFARS-krav (Defense Federal Acquisition Regulations Supplement).

* [Microsoft 365 DoD-miljøet](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc-high-and-dod) er udviklet udelukkende til det amerikanske forsvarsministerium.

## <a name="connect-to-power-bi-for-us-government"></a>Oversigt over Power BI til US Government

URL-adressen til oprettelse af forbindelse til Power BI er forskellig for offentlige brugere og kommercielle brugere. Hvis du vil logge på Power BI, skal du bruge følgende URL-adresser:

| Kommerciel version  | GCC  | GCC High | DoD |
| --- | --- | --- | --- |
| [https://app.powerbi.com/](https://app.powerbi.com) |[https://app.powerbigov.us](https://app.powerbigov.us) | [https://app.high.powerbigov.us](https://app.high.powerbigov.us) | [https://app.mil.powerbigov.us](https://app.mil.powerbigov.us) |

Din konto kan være konfigureret i mere end ét cloudmiljø. Hvis din konto er konfigureret på denne måde, kan du vælge, hvilken cloud der skal oprettes forbindelse til, når du logger på Power BI Desktop.

## <a name="connect-government-and-global-azure-cloud-services"></a>Opret forbindelse mellem Government-tjenester og globale Azure Cloud-tjenester

Azure er fordelt på flere cloudmiljøer. Du kan som standard aktivere firewallregler for at åbne en forbindelse til en cloudspecifik forekomst, men netværket på tværs af skyen er anderledes.  Hvis du vil kommunikere mellem tjenester i den offentlige cloud og tjenesterne i Government Community Cloud, skal du konfigurere særlige firewallregler. Hvis du f.eks. vil have adgang til offentlige cloudforekomster af en SQL-database fra din offentlige cloududrulning af Power BI, skal du have en firewallregel i SQL-databasen. Konfigurer særlige firewallregler for SQL-databaser, så der tillades forbindelser til Azure Government Cloud for følgende datacentre:

* USGov Iowa
* USGov Virginia
* USGov Texas
* USGov Arizona

Pladserne for IP-adresse er tilgængelige i det offentlige cloudmiljø. Hvis du vil have adgang til cloud-IP-intervallerne for US Government, skal du downloade filen [Azure IP Ranges and Service Tags – US Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063).

Hvis du vil konfigurere firewalls for SQL-databaser, skal du følge fremgangsmåden for at [oprette og administrere IP-firewallregler](https://docs.microsoft.com/azure/sql-database/sql-database-firewall-configure#create-and-manage-ip-firewall-rules).

## <a name="power-bi-feature-availability"></a>Tilgængelighed af funktioner i Power BI

Der er visse forskelle mellem offentlige planer og kommercielle planer for at imødekomme kravene til offentlige cloudkunder. Vores mål er at gøre alle funktioner tilgængelige i cloudmiljøer for de offentlige myndigheder inden for 30 dage fra, de bliver generelt tilgængelige. I nogle tilfælde forhindrer underliggende afhængigheder os i at gøre en funktion tilgængelig.

Følgende tabel indeholder en liste over de funktioner, der ikke er tilgængelige i et bestemt miljø for de offentlige myndigheder, samt den estimerede tilgængelighed, hvis en udgivelse er planlagt:

|Funktion |GCC |GCC High |DoD|
|------|------|------|------|
|[Azure B2B-samarbejde mellem cloudmiljøet for de offentlige myndigheder og det kommercielle cloudmiljø](service-admin-azure-ad-b2b.md)<sup>1</sup>|![tilgængelig](../media/yes.png)|![ikke tilgængelig](../media/no.png)|![ikke tilgængelig](../media/no.png)|
|[Integrer i SharePoint Online ved hjælp af Power BI-webdelen](https://docs.microsoft.com/esharepoint/dev/spfx/web-parts/overview-client-side-web-parts)|![tilgængelig](../media/yes.png)|![Tilgængelig](../media/yes.png)|![ikke tilgængelig](../media/no.png)|
|[Power Automate-forbindelse til datadrevne underretninger](../connect-data/power-bi-data-sources.md)|![tilgængelig](../media/yes.png)|![tilgængelig](../media/yes.png)|![ikke tilgængelig](../media/no.png)|
|[Fanen Power BI i Teams](../collaborate-share/service-collaborate-microsoft-teams.md)<sup>2</sup>|![tilgængelig](../media/yes.png)|![ikke tilgængelig](../media/no.png)|![ikke tilgængelig](../media/no.png)|
|[Målepunkter for kapacitet](../admin/service-admin-premium-monitor-portal.md)|3\. kvartal 2020 |3\. kvartal 2020|3\. kvartal 2020|
|[Store modeller](service-premium-large-models.md) | 4\. kvartal 2020 |4\. kvartal 2020| ![ikke tilgængelig](../media/no.png) |
|[Dataflow – SQL Compute-programoptimering](../transform-model/service-dataflows-enhanced-compute-engine.md) | 4\. kvartal 2020 |4\. kvartal 2020| ![ikke tilgængelig](../media/no.png) |
|[Dataflow – -direkte forespørgsel](../transform-model/service-dataflows-directquery.md) | 4\. kvartal 2020 |4\. kvartal 2020|![ikke tilgængelig](../media/no.png)|
|[Meddelelser om tjenesteafbrydelser](service-premium-large-models.md)|4\. kvartal 2020 |4\. kvartal 2020|4\. kvartal 2020|
|[Data beskyttelse (MIP-mærkater)](service-security-sensitivity-label-overview.md)|4\. kvartal 2020|4\. kvartal 2020 |4\. kvartal 2020|
|[Skabelonapps](../connect-data/service-template-apps-overview.md)<sup>3</sup>|4\. kvartal 2020 |4\. kvartal 2020| 4\. kvartal 2020|
|[Brugerdefinerede visualiseringer](../developer/visuals/power-bi-custom-visuals.md)<sup>3</sup>|4\. kvartal 2020 |4\. kvartal 2020| 4\. kvartal 2020|
|[QR-kodeoprettelse](../create-reports/service-create-qr-code-for-tile.md)|![ikke tilgængelig](../media/no.png)|![ikke tilgængelig](../media/no.png)|![ikke tilgængelig](../media/no.png)|

<sup>1</sup> Selvom B2B Collaboration er tilgængelig til GCC, skal der udstedes en licens til eksterne brugere i dette miljø. Kommercielle cloudlicenser er ikke gyldige i GCC. Du kan finde flere oplysninger om kendte begrænsninger med B2B Collaboration til US Government ved at [sammenligne Azure Government og global Azure](https://docs.microsoft.com/azure/azure-government/compare-azure-government-global-azure#azure-active-directory-premium-p1-and-p2)

<sup>2</sup> Power BI-oplevelsen i Teams til GCC er begrænset, fungerer kun for klassiske arbejdsområder og indeholder ikke de forbedrede funktioner, der er beskrevet i [Integrerer Power BI-indhold i Microsoft Teams](../collaborate-share/service-embed-report-microsoft-teams.md).

<sup>3</sup> Funktionaliteten af udgivne skabelonapps og brugerdefinerede visualiseringer begrænses for cloudmiljøer for offentlige myndigheder. Der publiceres flere oplysninger om specifikke begrænsninger ved udgivelsen.

## <a name="next-steps"></a>Næste trin

* [Tilmeld dig Power BI til US Government](service-govus-signup.md)
* [Microsoft Power Apps US Government](https://docs.microsoft.com/power-platform/admin/powerapps-us-government)
* [Power Automate US Government](https://docs.microsoft.com/power-automate/us-govt)
* [Demo om Power BI US Government](https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government)
