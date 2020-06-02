---
title: Databeskyttelse i Power BI
description: Få mere at vide om, hvordan databeskyttelse fungerer i Power BI
author: paulinbar
manager: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/22/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: d70262908df5568066533d1b638c7a1495a3f30b
ms.sourcegitcommit: c1f05254eaf5adb563f8d4f33c299119134c7d1f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/21/2020
ms.locfileid: "83733226"
---
# <a name="data-protection-in-power-bi-preview"></a>Databeskyttelse i Power BI (prøveversion)

Moderne virksomheder har strenge forretningsregler og krav til, hvordan de håndterer og beskytter deres følsomme data. Power BI kan integreres med Microsoft Azure Information Protection og Microsoft Cloud App Security for at give større kontrol med og synlighed over følsomme data i Power BI. 

Med databeskyttelse i Power BI kan du gøre følgende:

* Brug følsomhedsmærkater fra Microsoft til at klassificere indhold i Power BI-tjenesten (dashboards, rapporter, datasæt og dataflow) og forsyne det med mærkater ved hjælp af den samme taksonomi, der bruges til at klassificere og beskytte filer i Microsoft 365.

* Gennemtving beskyttelsesindstillinger, f.eks. kryptering eller vandmærker, når du eksporterer data fra Power BI-tjenesten til filer ved at anvende indholdets følsomhedsmærkat og beskyttelse (Excel, PowerPoint og PDF). 

  Brugerne kan f.eks. anvende en fortrolighedsmærkat på en rapport i Power BI. Når dataene derefter eksporteres til en Excel-fil, vil Power BI anvende fortrolighedsmærkaten på filen. Mærkaten kan kryptere indholdet og anvende et fortrolighedsvandmærke.

* Brug Microsoft Cloud App Security til at overvåge aktiviteter i Power BI, undersøge sikkerhedsproblemer og beskytte indhold i Power BI med Appobjekt til betinget adgang i Microsoft Cloud App Security. 

## <a name="sensitivity-labels-in-power-bi"></a>Følsomhedsmærkater i Power BI

Følsomhedsmærkater oprettes og administreres enten i [Microsoft 365 Security Center](https://security.microsoft.com/) eller [Microsoft 365 Compliance Center](https://compliance.microsoft.com/).

Hvis du vil have adgang til følsomhedsmærkater i et af disse centre, skal du navigere til **Klassificering** > **Følsomhedsmærkater**. Disse følsomhedsmærkater kan bruges af flere Microsoft-tjenester, f.eks. Microsoft Azure Information Protection, Office-programmer og Microsoft 365-tjenester.

> [!IMPORTANT]
> Kunder, der bruger Microsoft Azure Information Protection, skal overføre mærkaterne til en af de tidligere angivne tjenester, før følsomhedsmærkaterne kan bruges i Power BI. Derudover understøttes følsomhedsmærkater kun i offentlige cloudmiljøer, og de understøttes ikke for lejere i cloudmiljøer, f.eks. nationale cloudmiljøer.
>
> Få mere at vide om [overførsel af følsomhedsmærkater til Microsoft Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels).

## <a name="how-sensitivity-labels-work"></a>Sådan fungerer følsomhedsmærkater

Når du anvender en følsomhedsmærkat på et dashboard, en rapport, et datasæt eller et dataflow i Power BI, svarer det til at anvende et *mærke* for den pågældende ressource, hvilket resulterer i følgende fordele:
* **Kan tilpasses** – Du kan oprette kategorier for forskellige niveauer af følsomt indhold i din organisation, f.eks. Personlig, Offentlig, Generelt, Fortrolig og Meget fortroligt.
* **Klartekst** – Da mærkater er i klartekst, er det nemt for brugerne at forstå, hvordan de skal behandle indholdet i henhold til retningslinjerne for følsomhedsmærkater.
* **Bevares** – Når en følsomhedsmærkat er blevet anvendt for indhold, følger den med dette indhold, når det eksporteres til følgende understøttede filtyper: Excel, PowerPoint og PDF. 

  Det betyder, at følsomhedsmærkaterne følger indholdet, herunder dens beskyttelsesindstillinger, og bliver grundlaget for anvendelse og gennemtvingelse af politikker. 

## <a name="sensitivity-label-example"></a>Eksempel på følsomhedsmærkat 

Her er et hurtigt eksempel på, hvordan en følsomhedsmærkat i Power BI kan fungere.

1. I Power BI-tjenesten er følsomhedsmærkaten **Meget fortroligt – Kun internt** anvendt på en rapport.

   ![Følsomhedsmærkater i listevisning](media/service-security-data-protection-overview/sensitivity-labels-overview-01.png)

2. Når data eksporteres til en Excel-fil fra denne rapport, anvendes følsomhedsmærkaten og beskyttelsen for den eksporterede Excel-fil.

   ![Følsomhedsmærkaten følger indholdet](media/service-security-data-protection-overview/sensitivity-labels-overview-02.png)

I Microsoft Office-programmer vises en følsomhedsmærkat som et mærke for mailen eller dokumentet ligesom på billedet ovenfor.

Du kan også tildele en klassificering til indhold (f.eks. et klistermærke), der bevares og følger med indholdet, i takt med at det bruges og deles. Du kan bruge denne klassificering til at generere forbrugsrapporter og se aktivitetsdata for dit følsomme indhold. På baggrund af disse oplysninger kan du altid senere vælge at anvende beskyttelsesindstillinger.


## <a name="using-sensitivity-labels-in-power-bi"></a>Brug af følsomhedsmærkater i Power BI

Før dine følsomhedsmærkater kan aktiveres i Power BI, skal du først fuldføre følgende forudsætninger: 

* Sørg for, at der er defineret følsomhedsmærkater enten i [Microsoft 365 Security Center](https://security.microsoft.com/) eller [Microsoft 365 Compliance Center](https://compliance.microsoft.com/). 
* [Aktivér følsomhedsmærkater](service-security-enable-data-sensitivity-labels.md) (prøveversion) i Power BI.
* Sørg for, at brugerne har den rette licens.
  * Brugerne skal have en Premium P1- eller Premium P2-licens til Microsoft Azure Information Protection for at få vist eller anvende mærkater i Power BI. Microsoft Azure Information Protection kan købes enten separat eller via en af Microsoft-licenspakkerne. Du kan finde flere oplysninger under [Priser på Microsoft Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection/).
  * Brugeren skal have en Power BI Pro-licens foruden en af de ovenfor nævnte licenser til Microsoft Azure Information Protection, før vedkommende kan anvende mærkater på Power BI-ressourcer. 

## <a name="protect-content-using-microsoft-cloud-app-security"></a>Beskyt indhold ved hjælp af Microsoft Cloud App Security

Du kan beskytte indhold i Power BI mod utilsigtede lækager eller brud ved hjælp af Microsoft Cloud App Security. Når Microsoft Cloud App Security er angivet og konfigureret, kan administratorer af sikkerhed overvåge brugeradgang og -aktivitet, udføre risikoanalyse i realtid og angive mærkatspecifikke kontrolelementer.

Organisationer kan f.eks. bruge Microsoft Cloud App Security til at konfigurere en politik, der forhindrer brugere i at downloade følsomme data fra Power BI til enheder, der ikke administreres. En sådan konfiguration gør det muligt for brugerne at forblive produktive og oprette forbindelse til Power BI overalt, samtidig med at de bruger Microsoft Cloud App Security til at forhindre, at brugerhandlinger bliver kompromitteret – alt sammen i realtid. 

### <a name="requirements"></a>Krav

Før Microsoft Cloud App Security kan bruges til dine følsomhedsmærkater, skal følgende forudsætninger være opfyldt: 

* Cloud App Security og Microsoft Azure Information Protection [skal være aktiveret for din lejer](https://docs.microsoft.com/cloud-app-security/azip-integration).
* Programmet [skal have forbindelse til Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Følgende liste indeholder nogle begrænsninger for følsomhedsmærkater i Power BI:

* Der kræves en Premium P1- eller Premium P2-licens til Microsoft Azure Information Protection for at anvende og få vist følsomhedsmærkater fra Microsoft Azure Information Protection i Power BI. Microsoft Azure Information Protection kan købes enten separat eller via en af Microsoft-licenspakkerne. Du kan finde flere oplysninger under [Priser på Microsoft Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection/).
* Følsomhedsmærkater kan kun anvendes på dashboards, rapporter, datasæt og dataflow.
* Gennemtvingelse af kontrolelementer til mærkater og beskyttelse af eksporterede filer understøttes kun for Excel-, PowerPoint- og PDF-filer. Mærkater og beskyttelse gennemtvinges ikke, når data eksporteres til. CSV-filer eller i forbindelse med Abonner på mail, Integrer visualiseringer og udskrivning.
* En bruger, der eksporterer en fil fra Power BI, har tilladelse til at tilgå og redigere filen i henhold til indstillingerne for følsomhedsmærkaten. Den bruger, der eksporterer dataene, får ikke ejerens tilladelser til filen. 
* Følsomhedsmærkater er i øjeblikket ikke tilgængelige til [sideinddelte rapporter]( https://docs.microsoft.com/power-bi/paginated-reports-report-builder-power-bi) og projektmapper.
* Følsomhedsmærkater på Power BI-aktiver kan kun ses på listen over arbejdsområder og linjevisninger. Mærkater er i øjeblikket ikke synlige i Favoritter, Delt med mig, Seneste eller programvisninger. Bemærk dog, at en mærkat, som er anvendt på et Power BI-aktiv, altid bevares for data, der eksporteres til Excel-, PowerPoint- og PDF-filer, også selvom mærkaten ikke er synlig.
* *Indstillingen for filkryptering* i følsomhedsmærkaten konfigureres enten i [Microsoft 365 Security Center](https://security.microsoft.com/) eller [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) og gælder kun for filer, der *eksporteres fra* Power BI. Den gennemtvinges ikke *i* Power BI.
* [HYOK-beskyttelse](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) understøttes ikke for mærkater, der anvendes i Power BI.
* Der er [licenskrav](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels#subscription-and-licensing-requirements-for-sensitivity-labels) for visning og anvendelse af mærkater i Office-programmer.
* Følsomhedsmærkater understøttes kun for lejere i det globale cloudmiljø (offentligt). Følsomhedsmærkater understøttes ikke for lejere i andre cloudmiljøer.
* Følsomhedsmærkater for data understøttes ikke for skabelonapps. Følsomhedsmærkater, der er angivet af opretteren af skabelonprogrammet, fjernes, når programmet udtrækkes og installeres. Følsomhedsmærkater, der føjes til artefakter i et installeret skabelonprogram af programbrugeren, mistes (nulstilles til ingenting), når programmet opdateres.
* Power BI understøtter ikke følsomhedsmærkater for beskyttelsestyperne **Videresend ikke** og **Ad hoc**.

## <a name="next-steps"></a>Næste trin

Denne artikel indeholdt en oversigt over databeskyttelse i Power BI. Følgende artikler indeholder flere oplysninger om databeskyttelse i Power BI. 

* [Aktivér datafølsomhedsmærkater i Power BI](service-security-enable-data-sensitivity-labels.md)
* [Anvend datafølsomhedsmærkater i Power BI](../collaborate-share/service-security-apply-data-sensitivity-labels.md)
* [Brug af Microsoft Cloud App Security-kontrolelementer i Power BI](service-security-using-microsoft-cloud-app-security-controls.md)
* [Rapport over databeskyttelsesmålepunkter](service-security-data-protection-metrics-report.md)