---
title: Hent Power BI Desktop
description: Download og installér Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/05/2018
ms.author: davidi
LocalizationGroup: Get started
ms.openlocfilehash: 52ef1f6526b83a54ba26fdffaf8150049c55880d
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/26/2018
ms.locfileid: "34813313"
---
# <a name="get-power-bi-desktop"></a>Hent Power BI Desktop
Med **Power BI Desktop** kan du oprette avancerede forespørgsler, modeller og rapporter, som visualiserer data. Med **Power BI Desktop** kan du oprette datamodeller, oprette rapporter og dele dit arbejde ved at udgive det i Power BI-tjenesten.  **Power BI Desktop** kan downloades gratis.

Du kan hente **Power BI Desktop** på to måder, som beskrevet i følgende afsnit:

* **Download** det direkte (en MSI-pakke, du downloader og installerer på din computer)
* Installér som en app fra **Microsoft Store**

Begge fremgangsmåder henter den nyeste version af **Power BI Desktop** på computeren, men der er et par forskelle, du skal være opmærksom på, som beskrevet i følgende afsnit.

## <a name="download-power-bi-desktop"></a>Download Power BI Desktop
Hvis du vil downloade den nyeste version af **Power BI Desktop**, kan du vælge downloadikonet i øverste højre hjørne af Power BI-tjenesten og vælge **Power BI Desktop**.

![](media/desktop-get-the-desktop/getpbid_downloads.png)

Du kan også downloade den nyeste version af Power BI Desktop fra følgende downloadside:

* [**Download af Power BI Desktop**  (både 32- og 64-bit versionen)](https://powerbi.microsoft.com/desktop).
  
  [![](media/service-admin-power-bi-security/PBI_Security_01.png)](https://powerbi.microsoft.com/desktop)

Uanset hvordan du downloader **Power BI Desktop**, bliver du bedt om at køre installationsfilen, når den er hentet:

![](media/desktop-get-the-desktop/getpbid_3.png)

**Power BI Desktop** installeres som et program og kører på din computer.

![](media/desktop-get-the-desktop/designer_gsg_install.png)

> [!NOTE]
> Du kan ikke installere den downloadede version (MSI) og **Microsoft Store**-versionen af **Power BI Desktop** på samme computer (hvilket også kaldes for en *side om side*-installation).
> 
> 

## <a name="install-as-an-app-from-the-microsoft-store"></a>Installér som en app fra Microsoft Store
Du kan også hente **Power BI Desktop** via Microsoft Store ved hjælp af følgende link:

* [Installér **Power BI Desktop** via **Microsoft Store**](http://aka.ms/pbidesktopstore)

![](media/desktop-get-the-desktop/getpbid_04.png)

Der er nogle fordele ved at hente **Power BI Desktop** via Microsoft Store:

* **Automatiske opdateringer** – Windows downloader automatisk den nyeste version i baggrunden, så snart den bliver tilgængelig, så din version er altid opdateret.
* **Mindre downloads** – **Microsoft Store** sikrer, at det kun er komponenter, som er ændret i de enkelte opdateringer, der downloades til computeren, hvilket resulterer i mindre downloads for hver opdatering.
* **Der kræves ikke administratorrettigheder** – Når du downloader MSI direkte og installerer det, skal du være administrator, for at installationen kan fuldføres. Når du henter **Power BI Desktop** via Microsoft Store, kræves der *ikke* administratorrettigheder.
* **It-udrulning aktiveret** – **Microsoft Store**-versionen kan nemmere *udrulles* for alle i organisationen og gøre **Power BI Desktop** tilgængelig via **Microsoft Store til Virksomheder**.
* **Registrering af sprog** – **Microsoft Store**-versionen inkluderer alle understøttede sprog og kontrollerer, hvilke sprog der bruges på computeren, hver gang den startes. Dette påvirker også oversættelse af modeller, der oprettes i **Power BI Desktop**. Indbyggede datohierarkier vil f.eks. bruge det sprog, som **Power BI Desktop** brugte, da .pbix-filen blev oprettet.

Der er et par overvejelser og begrænsninger i forbindelse med at installere **Power BI Desktop** via Microsoft Store. De er som følger:

* Hvis du bruger SAP-connectoren, skal du muligvis flytte dine SAP-driverfiler til mappen *Windows\System32*.
* Brugerindstillingerne fra MSI-versionen kopieres ikke ved installation af **Power BI Desktop** via Microsoft Store. Du skal muligvis oprette forbindelse til dine seneste datakilder igen og angive dine legitimationsoplysninger til datakilden igen. 

> [!NOTE]
> Du kan ikke installere den downloadede version (MSI) og **Microsoft Store**-versionen af **Power BI Desktop** på samme computer (hvilket også kaldes for en *side om side*-installation). Du skal fjerne **Power BI Desktop** manuelt, før du downloader den fra **Microsoft Store**
> 
> [!NOTE]
> Power BI-rapportserverversionen af **Power BI Desktop** er en separat version og adskiller sig fra de versioner, der er beskrevet i denne artikel. Du kan finde oplysninger om rapportserverversionen af **Power BI Desktop** under [Opret en Power BI-rapport til Power BI-rapportserveren](report-server/quickstart-create-powerbi-report.md).
> 
> 

## <a name="using-power-bi-desktop"></a>Brug Power BI Desktop
Når du starter **Power BI Desktop**, vises der et *velkomstbillede*.

![](media/desktop-get-the-desktop/getpbid_05.png)

Hvis det er første gang, du bruger **Power BI Desktop** (og installationen ikke er en opgradering), bliver du bedt om at udfylde en formular og svare på et par spørgsmål eller logge på **Power BI-tjenesten**, før du kan fortsætte.

Herfra kan du gå i gang med at oprette datamodeller eller rapporter og dele dem med andre brugere af Power BI-tjenesten. Se linksene med **Flere oplysninger** sidst i denne artikel for at få links til vejledninger, der kan hjælpe dig med at komme i gang med at bruge **Power BI Desktop**.

## <a name="minimum-requirements"></a>Minimumkrav
Følgende liste indeholder minimumkravene til at køre **Power BI Desktop**:

* Windows 7/Windows Server 2008 R2 eller nyere
* .NET 4.5
* Internet Explorer 9 eller nyere
* **Hukommelse (RAM):** Mindst 1 GB ledig hukommelse, 1,5 GB eller mere anbefales.
* **Skærm:** Mindst 1440 x 900 eller 1600 x 900 (16:9) anbefales. En lavere opløsning, f.eks. 1024 x 768 eller 1280 x 800 anbefales ikke, da visse kontrolelementer (f.eks. lukning af startskærmen) vises ud over disse opløsninger.
* **Indstillinger for visning af vinduer:** Hvis dine visningsindstillinger er angivet til at ændre størrelsen på tekst, apps og andre elementer til mere end 100 %, kan du muligvis ikke se visse dialogbokse, der skal lukkes eller besvares for at fortsætte med at bruge **Power BI Desktop**. Hvis du oplever dette problem, skal du kontrollere dine **skærmindstillinger** ved at gå til **Indstillinger > System > Skærm** i Windows og bruge skyderen for at ændre skærmindstillinger tilbage til 100 %.
* **CPU:** x86- eller x64-bit processor med 1 gigahertz (GHz) eller hurtigere anbefales.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Nogle brugere støder på en fejl, der svarer til følgende, når du bruger en forældet version af **Power BI Desktop**: 

    "We weren't able to restore the saved database to the model" 

Du kan som regel løse problemet ved at opdatere til den aktuelle version af Power BI Desktop.

## <a name="next-steps"></a>Næste trin
Når du får **Power BI Desktop** installeret, kan følgende indhold hjælpe dig med at komme hurtigt i gang:

* [Introduktion til Power BI Desktop](desktop-getting-started.md)
* [Oversigt over forespørgsler i Power BI Desktop](desktop-query-overview.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Opret forbindelse til data i Power BI Desktop](desktop-connect-to-data.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Almindelige forespørgselsopgaver i Power BI Desktop](desktop-common-query-tasks.md)   

