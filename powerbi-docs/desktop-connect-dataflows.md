---
title: Opret forbindelse til data oprettet af Power BI-dataflow i Power BI Desktop (beta)
description: Opret nemt forbindelse til og brug data fra dataflows i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f1d782aa7409dce43d960956406e996cc7951a57
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/06/2020
ms.locfileid: "73876465"
---
# <a name="connect-to-data-created-by-power-bi-dataflows-in-power-bi-desktop-beta"></a>Opret forbindelse til data oprettet af Power BI-dataflow i Power BI Desktop (beta)
I **Power BI Desktop** kan du oprette forbindelse til data oprettet af **Power BI-dataflows** på samme måde som enhver anden datakilde i Power BI Desktop.

![Opret forbindelse til dataflows](media/desktop-connect-dataflows/connect-dataflows_01.png)

Med connectoren **Power BI-dataflow (beta)** kan du oprette forbindelse til enheder, der er oprettet af dataflow i Power BI-tjenesten. 

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Hvis du vil bruge denne betaversion af **connectoren Power BI-dataflow**, skal du køre den seneste version af **Power BI Desktop**. Du kan altid [hente Power BI Desktop](desktop-get-the-desktop.md) og installere det på din computer for at sikre dig, at du har den nyeste version.  

> [!NOTE]
> I den tidligere version af connectoren Power BI-dataflow krævedes det, at du downloadede en .MEZ-fil og anbragte den i en mappe. Aktuelle versioner af **Power BI Desktop** inkluderer connectoren Power BI-dataflow, så denne fil er ikke længere påkrævet og kan medføre konflikter med den inkluderede version af connectoren. Hvis du har placeret denne .MEZ-fil i mappen manuelt, *skal* du slette denne downloadede .MEZ-fil fra mappen **Dokumenter > Power BI Desktop > Brugerdefinerede connectors** for at undgå konflikter. 

## <a name="desktop-performance"></a>Stationær computers ydeevne
**Power BI Desktop** kører lokalt på den computer, hvor det er installeret. Ydeevnen for dataindtagelse for dataflow bestemmes af en lang række faktorer. Disse faktorer omfatter mængden af dataene, din computers CPU og RAM, netværkets båndbredde, afstanden til datacenteret og andre faktorer.

Du kan forbedre ydeevnen for dataindtagelse for dataflow. Hvis f.eks. mængden af de overførte data er for stor til, at **Power BI Desktop** kan administrere dem på din computer, kan du bruge sammenkædede og beregnede objekter i dataflow til at samle dataene (i dataflow) og kun overføre de samlede data, der er klargjort i forvejen. Dette medfører, at behandling af store datamængder udføres online i dataflow i stedet for at blive udført lokalt i din kørende forekomst af **Power BI Desktop**. Denne tilgang giver Power BI Desktop mulighed for at overføre mindre datamængder og sørger for, at oplevelsen med dataflow forbliver dynamisk og hurtig.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

De fleste dataflow er placeret i Power BI-tjenestelejeren. **Power BI Desktop**-brugerne kan dog ikke få adgang til dataflow, der er gemt under Azure Data Lake Storage Gen2-kontoen, medmindre de er ejer af dataflowet, eller de udtrykkeligt er godkendt til dataflowets CDM-mappe. Overvej følgende situation:

1.  Anna opretter et nyt arbejdsområde og konfigurerer det til at gemme dataflow i organisationens datasø.
2.  Ben, der også er medlem af det arbejdsområde, Anna har oprettet, vil gerne bruge Power BI Desktop og dataflowconnectoren til at hente data fra det dataflow, Anna har oprettet.
3.  Ben får vist en fejl, da han ikke er føjet til dataflowets CDM-mappe som en godkendt bruger i datasøen.

    ![Fejl under forsøg på at bruge dataflow](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_08.jpg)

Problemet kan løses ved, at Ben tildeles læsetilladelser til CDM-mappen og dens filer. Du kan få mere at vide om, hvordan du give adgang til CDM-mappen i [denne artikel](https://go.microsoft.com/fwlink/?linkid=2029121).




## <a name="next-steps"></a>Næste trin
Du kan gøre mange forskellige interessante ting med Power BI-dataflow. Du kan finde flere oplysninger i følgende ressourcer:

* [Selvbetjent dataforberedelse med dataflow](service-dataflows-overview.md)
* [Opret og brug dataflow i Power BI](service-dataflows-create-use.md)
* [Brug beregnede objekter i Power BI Premium (prøveversion)](service-dataflows-computed-entities-premium.md)
* [Brug dataflow med datakilder i det lokale miljø (prøveversion)](service-dataflows-on-premises-gateways.md)
* [Udviklerressourcer til Power BI-dataflow (prøveversion)](service-dataflows-developer-resources.md)

Du kan finde flere oplysninger om integration med Azure Data Lake Storage Gen2 i følgende artikler:

* [Integration af dataflow og Azure Data Lake (eksempelvisning)](service-dataflows-azure-data-lake-integration.md)
* [Konfigurer indstillinger for dataflow for et arbejdsområde (prøveversion)](service-dataflows-configure-workspace-storage-settings.md)
* [Føj en CDM-mappe til Power BI som et dataflow (prøveversion)](service-dataflows-add-cdm-folder.md)
* [Slut Azure Data Lake Storage Gen2 til et dataflowlager (prøveversion)](service-dataflows-connect-azure-data-lake-storage-gen2.md)

Der findes også artikler om **Power BI Desktop**, som du kan finde nyttige:

* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

