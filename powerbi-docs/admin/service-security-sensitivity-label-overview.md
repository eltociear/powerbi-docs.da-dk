---
title: Følsomhedsmærkater fra Microsoft Information Protection i Power BI
description: Få mere at vide om, hvordan følsomhedsmærkater fra Microsoft Information Protection fungerer i Power BI
author: paulinbar
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 08/10/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: 4d719d7df5b982341b6377c41e448267197e769b
ms.sourcegitcommit: 9e39232cbc28d8b39dfec5496db7ece9837b5e53
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2020
ms.locfileid: "88049228"
---
# <a name="sensitivity-labels-in-power-bi"></a>Følsomhedsmærkater i Power BI

I denne artikel beskrives funktionaliteten af [Microsoft Information Protection-følsomhedsmærkater](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels?view=o365-worldwide) i Power BI. Du kan finde oplysninger om, hvordan du anvender følsomhedsmærkater til Power BI-rapporter, -dashboards, -datasæt og -dataflows, i [Sådan anvendes følsomhedsmærkater i Power BI](./service-security-apply-data-sensitivity-labels.md). Du kan finde oplysninger om aktivering af følsomhedsmærkater i din lejer under [Aktivér følsomhedsmærkater i Power BI](service-security-enable-data-sensitivity-labels.md).

Microsoft Information Protections følsomhedsmærkater giver brugerne en nem måde at klassificere kritisk indhold i Power BI på uden at gå på kompromis med produktiviteten eller muligheden for at samarbejde.

Følsomhedsmærkater kan kun anvendes på datasæt, rapporter, dashboards og dataflows. Når data eksporteres fra Power BI til Excel-, PowerPoint- eller PDF-filer, anvender Power BI automatisk en følsomhedsmærkat på den eksporterede fil og beskytter den i henhold til indstillingerne for mærkatens filkryptering. På den måde forbliver dine følsomme data beskyttede, uanset hvor de er.

Følsomhedsmærkater, der anvendes på Power BI-rapporter, -dashboards, -datasæt og -dataflows, er synlige fra mange forskellige steder i Power BI-tjenesten. Følsomhedsmærkater på rapporter og dashboards er også synlige i Power BI iOS- og Android-mobilapps og i integrerede visualiseringer.

Der er en [målepunktsrapport for beskyttelse](service-security-data-protection-metrics-report.md) i Power BI-administrationsportalen, der giver Power BI-administratorer fuld synlighed over de følsomme data i Power BI-lejeren. Derudover omfatter Power BI-overvågningsloggene oplysninger om følsomhedsmærkater for aktiviteter som f.eks. anvendelse, fjernelse og ændring af mærkater samt om aktiviteter som f.eks. visning af rapporter, dashboards, osv., der giver Power BI og sikkerhedsadministratorer synlighed over forbruget af følsomme data med det formål at overvåge og undersøge samt i forbindelse med sikkerhedsadvarsler.

## <a name="important-considerations"></a>Vigtige overvejelser

Følsomhedsmærkater påvirker **ikke** adgangen til indhold i Power BI – adgangen til indhold i Power BI styres udelukkende af Power BI-tilladelser. Selvom mærkaterne er synlige, anvendes eventuelle tilknyttede krypteringsindstillinger (konfigureret enten i [Microsoft 365 Security Center](https://security.microsoft.com/) eller [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)) ikke. De anvendes kun på de data, der eksporteres til Excel-, PowerPoint- og PDF-filer.

Følsomhedsmærkater og filkryptering anvendes **ikke** i andre eksportstier end eksport til Excel, PowerPoint og PDF. Power BI-lejeradministratoren kan deaktivere enhver eller alle eksportstier, der ikke understøtter anvendelsen af følsomhedsmærkater og de tilknyttede indstillinger for filkryptering.

>[!NOTE]
> Brugere, der har fået adgang til en rapport, bliver tildelt adgang til hele det underliggende datasæt, medmindre [sikkerhed på rækkeniveau](./service-admin-rls.md) begrænser deres adgang. Rapportforfattere kan klassificere og navngive rapporter ved hjælp af følsomhedsmærkater. Hvis følsomhedsmærkaten har beskyttelsesindstillinger, anvender Power BI disse beskyttelsesindstillinger, når rapportdataene eksporteres til Excel-, PowerPoint-eller PDF-filer. Kun autoriserede brugere kan åbne beskyttede filer.

## <a name="how-sensitivity-labels-work-in-power-bi"></a>Sådan fungerer følsomhedsmærkater i Power BI

Når du anvender en følsomhedsmærkat på et dashboard, en rapport, et datasæt eller et dataflow i Power BI, svarer det til at anvende et mærke for den pågældende ressource, hvilket har følgende fordele:
* **Kan tilpasses** – Du kan oprette kategorier for forskellige niveauer af følsomt indhold i din organisation, f.eks. Personlig, Offentlig, Generelt, Fortrolig og Meget fortroligt.
* **Klartekst** – Da mærkater er i klartekst, er det nemt for brugerne at forstå, hvordan de skal behandle indholdet i henhold til retningslinjerne for følsomhedsmærkater.
* **Fast** – når en følsomhedsmærkat er blevet anvendt på indhold, følger den dette indhold, når den eksporteres til Excel-, PowerPoint- og PDF-filer, og den bliver grundlaget for anvendelse og håndhævelse af politikker.

Her er et hurtigt eksempel på, hvordan en følsomhedsmærkat i Power BI kan fungere. På billedet nedenfor kan du se, hvordan der anvendes en følsomhedsmærkat i en rapport i Power BI-tjenesten, derefter hvordan dataene fra rapporten eksporteres til en Excel-fil, og til sidst hvordan følsomhedsmærkaten og dens beskyttelse forbliver i den eksporterede fil.

![Animeret GIF, der viser følsomhedsmærkaternes anvendelse og fastholdelse](media/service-security-sensitivity-label-overview/ApplyLabelandProtection.gif)

I Microsoft Office-programmer vises en følsomhedsmærkat som et mærke for mailen eller dokumentet ligesom det, der er vist på billedet ovenfor.

Du kan også tildele en klassificering til indhold (f.eks. et klistermærke), der bevares og følger med indholdet, i takt med at det bruges og deles i Power BI. Du kan bruge denne klassificering til at generere forbrugsrapporter og se aktivitetsdata for dit følsomme indhold. På baggrund af disse oplysninger kan du altid senere vælge at anvende beskyttelsesindstillinger.

## <a name="sensitivity-label-inheritance-upon-creation-of-new-content"></a>Nedarvning af følsomhedsmærkater ved oprettelse af nyt indhold

Når der oprettes nye rapporter og dashboards i Power BI-tjenesten, arver de automatisk den følsomhedsmærkat, der tidligere er anvendt på et overordnet datasæt eller en rapport. En ny rapport, der er oprettet oven på et datasæt, som har følsomhedsmærkaten "stærkt fortroligt" får f.eks. automatisk også mærkaten "stærkt fortroligt".

På følgende billede kan du se, hvordan et datasæts følsomhedsmærkat anvendes automatisk på en ny rapport, der er bygget oven på datasættet.

![Animeret GIF, der viser nedarvning af følsomhedsmærkater](media/service-security-sensitivity-label-overview/InheritanceUponCreation.gif)

>[!NOTE]
>Hvis følsomhedsmærkaten af en eller anden grund ikke kan anvendes på den nye rapport eller det nye dashboard, blokerer Power BI **ikke** oprettelsen af det nye element.

## <a name="sensitivity-labels-and-protection-on-exported-data"></a>Følsomhedsmærkater og beskyttelse af eksporterede data

Når data eksporteres fra Power BI til Excel-, PowerPoint- eller PDF-filer, anvender Power BI automatisk en følsomhedsmærkat på den eksporterede fil og beskytter den i henhold til indstillingerne for mærkatens filkryptering. På den måde forbliver dine følsomme data beskyttede, uanset hvor de er.

En bruger, der eksporterer en fil fra Power BI, har tilladelse til at tilgå og redigere filen i henhold til indstillingerne for følsomhedsmærkaten. De får ikke ejertilladelser til filen.

Følsomhedsmærkater og beskyttelse anvendes ikke, når data eksporteres til .csv- eller .pbix-filer eller andre typer eksportstier.

Anvendelse af en følsomhedsmærkat og beskyttelse af en eksporteret fil føjer ikke indholdsmarkeringer til filen. Men hvis mærkaten er konfigureret til at anvende indholdsmarkeringer, anvendes markeringerne automatisk af Azure Information Protection Unified-navngivningsklienten, når filen åbnes i Office Desktop-apps. Indholdsmærkaterne anvendes ikke automatisk, når du bruger indbygget navngivning til skrivebords-, mobil- eller webapps. Se [Når Office-apps anvender indholdsmarkering og kryptering](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-office-apps?view=o365-worldwide#when-office-apps-apply-content-marking-and-encryption) for at få flere oplysninger.

Eksporten mislykkes, hvis en mærkat ikke kan anvendes, når der eksporteres data til en fil. Hvis du vil kontrollere, om eksporten mislykkedes, fordi mærkaten ikke kunne anvendes, skal du klikke på navnet på rapporten eller dashboardet i midten af titellinjen og se, om der står "Følsomhedsmærkat kan ikke indlæses" på den rulleliste, der åbnes. Dette kan ske som følge af et midlertidigt systemproblem, eller hvis den anvendte mærkat er blevet fjernet eller slettet af sikkerhedsadministratoren.

## <a name="sensitivity-label-inheritance-in-analyze-in-excel"></a>Nedarvning af følsomhedsmærkater i Analysér i Excel

Når du opretter en pivottabel i Excel med en direkte forbindelse til et Power BI-datasæt (du kan enten gøre det fra Power BI via [Analysér i Excel](../collaborate-share/service-analyze-in-excel.md) eller fra [Excel](https://support.microsoft.com/office/create-a-pivottable-from-power-bi-datasets-31444a04-9c38-4dd7-9a45-22848c666884?ui=en-US&rs=en-US&ad=US)), nedarves datasættets følsomhedsmærkat og anvendes på din Excel-fil sammen med eventuelle tilknyttede beskyttelsesforanstaltninger. Hvis mærkaten på datasættet senere ændres til et mere restriktivt, opdateres den mærkat, der anvendes på den sammenkædede Excel-fil, automatisk efter dataopdatering.

![Skærmbillede af Excel, hvor følsomhedsmærkaten er nedarvet fra datasæt via direkte forbindelse.](media/service-security-sensitivity-label-overview/live-connection-inheritance.png)
 
Følsomhedsmærkater i Excel, der blev angivet manuelt, tilsidesættes ikke automatisk af datasættets følsomhedsmærkat. I stedet vises der et banner med en besked om, at datasættet har en følsomhedsmærkat, og det anbefales, at du anvender den.

>[!NOTE]
>Hvis datasættets følsomhedsmærkat er mindre restriktiv end Excel-filens følsomhedsmærkat, sker der ingen nedarvning eller opdatering af mærkater. En Excel-fil arver aldrig en mindre restriktiv følsomhedsmærkat.


## <a name="sensitivity-label-persistence-in-embedded-reports-and-dashboards"></a>Fastholdelse af følsomhedsmærkater i integrerede rapporter og dashboards

Du kan integrere Power BI-rapporter, -dashboards og -visualiseringer i virksomhedsprogrammer som f.eks. Microsoft Teams og SharePoint eller på en organisations websted. Når du integrerer en visualisering, en rapport eller et dashboard, der har en følsomhedsmærkat, er følsomhedsmærkaten synlig i den integrerede visning, og mærkaten og beskyttelsen af den bevares, når der eksporteres data til Excel.

![Skærmbillede af rapport, der er integreret i SharePoint Online](media/service-security-sensitivity-label-overview/embedded-report-sensitivity-label.png)

Følgende integreringsscenarier understøttes:
* [Integrer til din organisation](../developer/embedded/embed-sample-for-your-organization.md)
* Microsoft 365-apps (f.eks. [Teams](../collaborate-share/service-embed-report-microsoft-teams.md) og [SharePoint](../collaborate-share/service-embed-report-spo.md))
* [Integrering af sikre URL-adresser](../collaborate-share/service-embed-secure.md) (integration fra Power BI-tjenesten) 

## <a name="sensitivity-labels-in-the-power-bi-mobile-apps"></a>Følsomhedsmærkater i Power BI-mobilapps

Følsomhedsmærkater kan vises på rapporter og dashboards i Power BI-mobilapps. Et ikon i nærheden af navnet på rapporten eller dashboardet angiver, at der er et følsomhedsmærkat, og typen af mærkat og en tilhørende beskrivelse fremgår af rapportens eller dashboardets oplysningsfelt.

![Skærmbillede af følsomhedsmærkat i mobilapp](media/service-security-sensitivity-label-overview/mobile-app-sensitivity-label2.png)

## <a name="supported-clouds"></a>Understøttede cloudmiljøer
Følsomhedsmærkater understøttes kun for lejere i globale (offentlige) cloudmiljøer, og de understøttes ikke for lejere i cloudmiljøer, f.eks. nationale cloudmiljøer.

## <a name="licensing-and-requirements"></a>Licenser og krav

Se [Licenser og krav](service-security-enable-data-sensitivity-labels.md#licensing-and-requirements).

## <a name="sensitivity-label-creation-and-management"></a>Oprettelse og administration af følsomhedsmærkater

Følsomhedsmærkater oprettes og administreres enten i [Microsoft 365 Security Center](https://security.microsoft.com/) eller [Microsoft 365 Compliance Center](https://compliance.microsoft.com/).

Hvis du vil have adgang til følsomhedsmærkater i et af disse centre, skal du navigere til **Klassificering > Følsomhedsmærkater**. Disse følsomhedsmærkater kan bruges af flere Microsoft-tjenester, f.eks. Microsoft Azure Information Protection, Office-programmer og Office 365-tjenester.

>[!Important]
> Hvis din organisation bruger følsomhedsmærkater fra Azure Information Protection, skal du [overføre](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) dem til en af de tidligere angivne tjenester, før følsomhedsmærkaterne kan bruges i Power BI.

## <a name="limitations"></a>Begrænsninger

Følgende liste indeholder nogle begrænsninger for følsomhedsmærkater i Power BI:

* Følsomhedsmærkater kan kun anvendes på dashboards, rapporter, datasæt og dataflows. De er i øjeblikket ikke tilgængelige til [sideinddelte rapporter](../paginated-reports/report-builder-power-bi.md) og projektmapper.
* Følsomhedsmærkater på Power BI-aktiver kan kun ses på listen over arbejdsområder og linjevisninger, Favoritter, Seneste og programvisninger. Mærkater er i øjeblikket ikke synlige i visningen Delt med mig. Bemærk dog, at en mærkat, som er anvendt på et Power BI-aktiv, altid bevares for data, der eksporteres til Excel-, PowerPoint- og PDF-filer, også selvom mærkaten ikke er synlig.
* Følsomhedsmærkater for data understøttes ikke for skabelonapps. Følsomhedsmærkater, der er angivet af opretteren af skabelonprogrammet, fjernes, når programmet udtrækkes og installeres. Følsomhedsmærkater, der føjes til artefakter i et installeret skabelonprogram af programbrugeren, mistes (nulstilles til ingenting), når programmet opdateres.
* Power BI understøtter ikke følsomhedsmærkater for beskyttelsestyperne [Videresend ikke](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions) og [brugerdefineret](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions) og [HYOK](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions). Beskyttelsestyperne Videresend ikke og brugerdefineret henviser til de mærkater, der er defineret i [Microsoft 365 Security Center](https://security.microsoft.com/) eller [Microsoft 365 Compliance Center](https://compliance.microsoft.com/).
* Det anbefales ikke at gøre det muligt for brugerne at anvende overordnede mærkater i Power BI. Hvis der anvendes en overordnet mærkat til indhold, kan eksport af data fra dette indhold til en fil (Excel, PowerPoint og PDF) mislykkes. Se [Undermærkater (grupperingsmærkater)](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels?view=o365-worldwide#sublabels-grouping-labels).

## <a name="next-steps"></a>Næste trin

Denne artikel indeholdt en oversigt over databeskyttelse i Power BI. Følgende artikler indeholder flere oplysninger om databeskyttelse i Power BI. 

* [Aktivér følsomhedsmærkater i Power BI](service-security-enable-data-sensitivity-labels.md)
* [Sådan anvendes følsomhedsmærkater i Power BI](service-security-apply-data-sensitivity-labels.md)
* [Brug af Microsoft Cloud App Security-kontrolelementer i Power BI](service-security-using-microsoft-cloud-app-security-controls.md)
* [Rapport over beskyttelsesmålepunkter](service-security-data-protection-metrics-report.md)