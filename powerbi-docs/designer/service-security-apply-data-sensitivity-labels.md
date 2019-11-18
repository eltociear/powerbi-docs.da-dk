---
title: Anvend følsomhedsmærkater i Power BI
description: Få mere at vide om, hvordan du anvender datafølsomhedsmærkater i Power BI
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/25/2019
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: 09f3a3e2dce7fd3462c5a21f014bf630bfc7c83e
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879030"
---
# <a name="apply-data-sensitivity-labels-in-power-bi-preview"></a>Anvend datafølsomhedsmærkater i Power BI (prøveversion)

Når følsomhedsmærkater er aktiveret i Power BI-tjenesten, kan du beskytte dine dashboards, rapporter, datasæt og dataflow mod uautoriseret adgang og lækage ved at anvende datafølsomhedsmærkater på dem. Hvis du forsyner dine data med datafølsomhedsmærkater korrekt, sikrer du, at det kun er godkendte personer, som kan få adgang til dine data.

Når databeskyttelse er aktiveret, vises følsomhedsmærkater i kolonnen med følsomhed i listevisningen af dashboards, rapporter, datasæt og dataflow.

![Aktivér datafølsomhedsmærkater](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-01.png)

> [!NOTE]
> Anvendelse af følsomhedsmærkater på dashboards, rapporter, datasæt og dataflow i Power BI kræver visse licenser og tilladelser. Du kan finde flere oplysninger under [Anvendelse af følsomhedsmærkater](#applying-sensitivity-labels).

## <a name="applying-sensitivity-labels"></a>Datafølsomhedsmærkater

For at kunne anvende følsomhedsmærkater i Power BI skal du og din organisation have følgende krav på plads:

* Organisationen skal have defineret følsomhedsmærkater enten i [Microsoft 365 Security Center](https://security.microsoft.com/) eller [Microsoft 365 Compliance Center](https://compliance.microsoft.com/).
* Du skal tilhøre en sikkerhedsgruppe, der har tilladelse til at anvende datafølsomhedsmærkater, som beskrevet i artiklen med titlen [Aktivér datafølsomhedsmærkater i Power BI (prøveversion)](../admin/service-security-enable-data-sensitivity-labels.md#enable-data-sensitivity-labels).
* Du skal have en Power BI Pro-licens og redigeringstilladelser til de ressourcer, du vil forsyne med en mærkat. 
* Du skal have en Premium P1- eller Premium P2-licens til Microsoft Azure Information Protection. Microsoft Azure Information Protection kan købes enten separat eller via en af Microsoft-licenspakkerne. Du kan finde flere oplysninger under [Priser på Microsoft Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection/).

Hvis du vil anvende eller ændre en følsomhedsmærkat for en rapport, skal du klikke på ikonet for rapportindstillinger på listen over arbejdsområder og derefter gå til afsnittet med datafølsomhed i sideruden Indstillinger. Vælg den relevante følsomhedsmærkat, og gem indstillingerne.

![Angiv datafølsomhedsmærkater](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-02.png)

Den opdaterede følsomhedsmærkat vises i kolonnen med følsomhed. 

![Visning af datafølsomhedsmærkater](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-03.png)

Anvendelse eller ændring af en følsomhedsmærkat for et dashboard følger samme proces, som beskrevet for rapporter. 

Du kan også angive følsomhedsmærkater på datasæt og dataflow. På følgende billede kan du se, hvordan du angiver en følsomhedsmærkat på et datasæt. Det er de samme trin for dataflow.

Du angiver en følsomhedsmærkat på et datasæt ved at vælge fanen Datasæt, klikke på de tre prikker for det datasæt, du vil anvende en mærkat på, og vælge **Indstillinger**.

![Åbn indstillinger for datasæt](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-05.png)

Åbn afsnittet med følsomhedsmærkater på siden Indstillinger, vælg den ønskede følsomhedsmærkat, og klik på **Anvend**.

![Vælg følsomhedsmærkat](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-06.png)

Anvendelse eller ændring af en følsomhedsmærkat for et dataflow følger samme proces, som beskrevet for datasæt.

## <a name="data-protection-in-exported-files"></a>Databeskyttelse i eksporterede filer

Når du [eksporterer data fra en rapport](https://docs.microsoft.com/power-bi/consumer/end-user-export), der har en følsomhedsmærkat, nedarves følsomhedsmærkaten af den genererede fil (Excel, PowerPoint og PDF – CSV understøttes ikke). Følsomhedsmærkaten er synlig i filen, og adgangen til filen begrænses til dem, der har tilstrækkelige tilladelser.

![Datafølsomhedsmærkater i brug](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-04b.png)

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Du skal gøre følgende overvejelser, når du anvender datafølsomhedsmærkater:

* Der kræves en Premium P1- eller Premium P2-licens til Microsoft Azure Information Protection for at anvende og få vist følsomhedsmærkater fra Microsoft Azure Information Protection i Power BI. Microsoft Azure Information Protection kan købes enten separat eller via en af Microsoft-licenspakkerne. Du kan finde flere oplysninger under [Priser på Microsoft Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection/).
* Følsomhedsmærkater kan kun anvendes på dashboards, rapporter, datasæt og dataflow.
* Gennemtvingelse af kontrolelementer til mærkater og beskyttelse af eksporterede filer understøttes kun for Excel-, PowerPoint- og PDF-filer. Mærkater og beskyttelse gennemtvinges ikke, når data eksporteres til. CSV-filer eller i forbindelse med Abonner på mail, Integrer visualiseringer og udskrivning.
* En bruger, der eksporterer en fil fra Power BI, har tilladelse til at tilgå og redigere filen i henhold til indstillingerne for følsomhedsmærkaten. Den bruger, der eksporterer dataene, får ikke ejerens tilladelser til filen. 
* Følsomhedsmærkater er i øjeblikket ikke tilgængelige til [sideinddelte rapporter]( https://docs.microsoft.com/power-bi/paginated-reports-report-builder-power-bi) og projektmapper. 
* Du kan i øjeblikket ikke slette en mærkat fra et Power BI-aktiv, når den først er blevet anvendt.
* Følsomhedsmærkater på Power BI-aktiver kan kun ses på listen over arbejdsområder og linjevisninger. Mærkater er i øjeblikket ikke synlige i Favoritter, Delt med mig, Seneste eller programvisninger. Bemærk dog, at en mærkat, som er anvendt på et Power BI-aktiv, altid bevares for data, der eksporteres til Excel-, PowerPoint- og PDF-filer, også selvom mærkaten ikke er synlig.
* *Indstillingen for filkryptering* i følsomhedsmærkaten konfigureres enten i [Microsoft 365 Security Center](https://security.microsoft.com/) eller [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) og gælder kun for filer, der *eksporteres fra* Power BI. Den gennemtvinges ikke *i* Power BI.
* [HYOK-beskyttelse](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) understøttes ikke for mærkater, der anvendes i Power BI.
* Der er [licenskrav](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-office-apps#subscription-and-licensing-requirements-for-sensitivity-labels) for visning og anvendelse af mærkater i Office-programmer.
* Følsomhedsmærkater understøttes kun for lejere i det globale cloudmiljø (offentligt). Følsomhedsmærkater understøttes ikke for lejere i andre cloudmiljøer.

## <a name="next-steps"></a>Næste trin

Denne artikel indeholdt en beskrivelse af, hvordan du anvender datafølsomhedsmærkater i Power BI. Følgende artikler indeholder flere oplysninger om databeskyttelse i Power BI. 

* [Oversigt over databeskyttelse i Power BI](../admin/service-security-data-protection-overview.md)
* [Aktivér datafølsomhedsmærkater i Power BI](../admin/service-security-enable-data-sensitivity-labels.md)
* [Brug af Microsoft Cloud App Security-kontrolelementer i Power BI](../admin/service-security-using-microsoft-cloud-app-security-controls.md)