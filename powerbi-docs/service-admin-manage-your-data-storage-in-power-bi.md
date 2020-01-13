---
title: Administrer datalager i dine arbejdsområder
description: Få mere at vide om, hvordan du kan administrere dit datalager i dit individuelle område eller arbejdsområde for at sikre, at du kan fortsætte med at publicere rapporter og datasæt.
author: maggiesMSFT
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2018
ms.author: maggies
LocalizationGroup: Administration
ms.openlocfilehash: f8e7240b34e20a3d18443cadb5265c5d0d870790
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/06/2020
ms.locfileid: "73873645"
---
# <a name="manage-data-storage-in-power-bi-workspaces"></a>Administrer datalager i Power BI-arbejdsområder

Få mere at vide om, hvordan du kan administrere dit datalager i dit individuelle område eller arbejdsområde for at sikre, at du kan fortsætte med at publicere rapporter og datasæt.

Brugere og arbejdsområder har deres egne datakapaciteter:

* Alle brugere har maksimalt 10 GB datalager.
* Brugere med en Power BI Pro-licens kan oprette arbejdsområder med maksimalt 10 GB datalager hver.
* Et arbejdsområde i en Premium-kapacitet tæller ikke med i lageret for en Power BI Pro-bruger.

På lejerniveauet må det samlede forbrug ikke overstige 10 GB pr. Pro-bruger på tværs af alle Pro-brugere og arbejdsområder i lejeren.

Læs om andre funktioner i [prismodellen for Power BI](https://powerbi.microsoft.com/pricing).

Inkluderet i dit datalager er dine egne datasæt og Excel-rapporter samt de elementer, som nogen har delt med dig. Datasæt er de datakilder, du har uploadet eller oprettet forbindelse til. Disse datakilder omfatter de Power BI Desktop-filer og Excel-projektmapper, du bruger. Følgende er også medtaget i din datakapacitet.

* Excel-områder, der er fastgjort til dashboardet.
* Reporting Services-visualiseringer i det lokale miljø, der er fastgjort til et Power BI-dashboard.
* Uploadede billeder.

Størrelsen på et dashboard, som du deler, varierer, afhængigt af hvad der er fastgjort til det. Hvis du f.eks. fastgør elementer fra to rapporter, der er en del af to forskellige datasæt, omfatter størrelsen begge datasæt.

<a name="manage"/>

## <a name="manage-items-you-own"></a>Administrer de elementer, du ejer

Se, hvor meget datalager, du bruger på din Power BI-konto, og administrer din konto.

1. Hvis du vil administrere dit eget lager, skal du gå til **Mit arbejdsområde** i navigationsruden.
   
    ![Mit arbejdsområde](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)
2. Vælg tandhjulsikonet ![Tandhjulsikon](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) i øverste højre hjørne \> **Administrer personligt lager**.
   
    Den øverste bjælke viser, hvor meget af din maksimale lagerkapacitet du har brugt.
   
    ![Administrer lagergrænse](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    Datasæt og rapporter er opdelt på to faner:
   
    **Ejet af mig:** Du har uploadet disse rapporter og datasæt til din Power BI-konto, herunder tjenestedatasæt som f.eks. Salesforce og Dynamics CRM.  
    **Ejet af andre:** Andre har delt disse rapporter og datasæt med dig.
1. Hvis du vil slette et datasæt eller en rapport, skal du vælge ikonet for Papirkurv ![Papirkurv-ikon](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).

Vær opmærksom på, at du eller en anden muligvis har rapporter og dashboards, der er baseret på et datasæt. Hvis du sletter datasættet, fungerer disse rapporter og dashboards ikke længere.

## <a name="manage-your-workspace"></a>Administrer dit arbejdsområde
1. Vælg pilen ud for **Arbejdsområder** \> vælg navnet på arbejdsområdet.
   
    ![Vælg et arbejdsområde](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. Vælg tandhjulsikonet ![tandhjulsikon](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) i øverste højre hjørne \> **Administrer gruppelager**.
   
    Den øverste bjælke viser, hvor meget af gruppens maksimale lagerkapacitet der er brugt.
   
    ![Administrer lager for arbejdsområde](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    Datasæt og rapporter er opdelt på to faner:
   
    **Ejet af os:** Du eller en anden har uploadet disse rapporter og datasæt til gruppens Power BI-konto, herunder tjenestedatasæt som f.eks. Salesforce og Dynamics CRM.
    **Ejet af andre:** Andre har delt disse rapporter og datasæt med din gruppe.
3. Hvis du vil slette et datasæt eller en rapport, skal du vælge ikonet for Papirkurv ![Papirkurv-ikon](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).
   
   > [!NOTE]
   > Et hvilket som helst medlem af et arbejdsområde med redigeringstilladelser kan slette datasæt og rapporter fra arbejdsområdet.
   > 
   > 

Vær opmærksom på, at du eller en anden i gruppen muligvis har rapporter og dashboards, der er baseret på et datasæt. Hvis du sletter datasættet, fungerer disse rapporter og dashboards ikke længere.

## <a name="dataset-limits"></a>Begrænsninger for datasæt
Der er en grænse på 1 GB, pr. datasæt, der indlæses i Power BI. Hvis du har valgt at beholde Excel-oplevelsen i stedet for at importere dataene, er grænsen 250 MB for datasættet.

## <a name="what-happens-when-you-reach-a-limit"></a>Det sker der, når du når grænsen
Når du når din grænse for datakapacitet, får du vist meddelelser i tjenesten. 

Når du vælger tandhjulsikonet ![tandhjulsikon](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png), får du vist en rød linje, der angiver, at du har overskredet din datakapacitet.

![Lagergrænse er nået](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

Denne grænse angives også i **Administrer personligt lager**.

 ![Administrer personligt lager, lagergrænsen er nået](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 Når du forsøger at udføre en handling, som gør, at du når en af grænserne, får du vist en meddelelse, der angiver, at du har overskredet grænsen. Du kan [administrere](#manage) dit lager for at reducere mængden af lagret indhold og komme under grænsen.

 ![Du har overskredet din lagergrænse](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

