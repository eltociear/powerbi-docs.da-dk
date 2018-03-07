---
title: "Opdater et datasæt, der er oprettet ud fra en Power BI Desktop-fil på OneDrive eller SharePoint Online"
description: "Opdater et datasæt, der er oprettet ud fra en Power BI Desktop-fil på OneDrive eller SharePoint Online"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: 851b8bc2c05aad87749c0fd6af14ba4f810ecbe2
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="refresh-a-dataset-stored-on-onedrive-or-sharepoint-online"></a>Opdater et datasæt, der er gemt på OneDrive eller SharePoint Online
Hvis du importerer filer fra OneDrive eller SharePoint Online til Power BI-tjenesten, kan du nemt sikre, at det arbejde, du udfører i **Power BI Desktop**, altid er synkroniseret med Power BI-tjenesten.

## <a name="advantages-of-storing-a-power-bi-desktop-file-on-onedrive-or-sharepoint-online"></a>Fordele ved at gemme en Power BI Desktop-fil på OneDrive eller SharePoint Online
Når du gemmer en **Power BI Desktop**-fil på OneDrive eller SharePoint Online, bliver de data, du har indlæst i filens model, importeret til datasættet, og de rapporter, du har oprettet i filen, indlæses i **Rapporter** i Power BI-tjenesten. Hvis du ændrer i din fil på OneDrive eller SharePoint Online, for eksempel tilføjer nye målinger, omdøber kolonnenavne eller redigerer visualiseringer, bliver ændringerne opdateret i Power BI-tjenesten, når du gemmer filen. Det sker som regel inden for en time.

Du kan udføre en manuel engangsopdatering direkte i Power BI Desktop ved at vælge Opdater under Hjem på båndet. Når du vælger Opdater her, opdateres dataene i *filens* model med de opdaterede data fra den oprindelige datakilde. Denne type opdatering, som foretages i selve Power BI Desktop, er forskellig fra den manuelle eller planlagte opdatering i Power BI, og det er vigtigt at forstå forskellen.

![](media/refresh-desktop-file-onedrive/pbix-refresh.png)

Når du importerer din Power BI Desktop-fil fra OneDrive eller SharePoint Online, indlæses data og andre oplysninger om modellen i et datasæt i Power BI. Du skal opdatere dataene i datasættet i Power BI-tjenesten, ikke i Power BI Desktop, da dine rapporter i Power BI-tjenesten er baseret på disse data. Da datakilderne er eksterne, kan du manuelt opdatere datasættet vha. **Opdater nu**, eller du kan oprette en tidsplan for opdatering vha. **Planlæg opdatering**.

Når du opdaterer datasættet, oprettes der ikke forbindelse til filen på OneDrive eller SharePoint Online for at forespørge om opdaterede data. Oplysningerne i datasættet bruges til at oprette forbindelse direkte til datakilderne for at hente opdaterede data, som derefter indlæses i datasættet. De opdaterede data i datasættet synkroniseres ikke tilbage til filen på OneDrive eller SharePoint Online.

## <a name="whats-supported"></a>Hvad understøttes?
I Power BI understøttes "Opdater nu" og "Planlæg opdatering" for de datasæt, der er oprettet via Power BI Desktop-filer, som er importeret fra et lokalt drev, hvor Hent data/Forespørgselseditor bruges til at oprette forbindelse til og indlæse data fra en af følgende datakilder:

### <a name="power-bi-gateway---personal"></a>Power BI Gateway – Personlig
* Alle onlinedatakilder, der vises i Hent data og Query Editor i Power BI Desktop.
* Alle datakilder i det lokale miljø, der vises i Hent data og Forespørgselseditor i Power BI Desktop, undtagen Hadoop-fil (HDFS) og Microsoft Exchange.

<!-- Refresh Data sources-->
[!INCLUDE [refresh-datasources](./includes/refresh-datasources.md)]

> [!NOTE]
> Der skal være installeret og køre en gateway, for at Power BI kan oprette forbindelse til datakilder i det lokale miljø og opdatere datasættet.
> 
> 

## <a name="onedrive-or-onedrive-for-business-whats-the-difference"></a>OneDrive eller OneDrive for Business. Hvad er forskellen?
Hvis du har både et personligt OneDrive og OneDrive for Business, anbefales det, at du opbevarer alle filer, som du vil importere til Power BI, i OneDrive for Business. Årsag: Du bruger sandsynligvis to forskellige konti til at logge på dem.

Når du opretter forbindelse til OneDrive for Business i Power BI, sker det normalt automatisk, fordi den konto, du bruger til at logge på Power BI med, ofte er den samme konto, der bruges til at logge på OneDrive for Business. Men med et personligt OneDrive kan du logge på med en anden [Microsoft-konto](http://www.microsoft.com/account/default.aspx).

Når du logger på med din Microsoft-konto, skal du vælge Forbliv logget på. Power BI kan derefter synkronisere eventuelle opdateringer, som du foretager i filen i Power BI Desktop, med datasæt i Power BI  
    ![](media/refresh-desktop-file-onedrive/refresh_signin_keepmesignedin.png)

Hvis du foretager ændringer i din fil på OneDrive, som ikke kan synkroniseres med datasættet eller rapporterne i Power BI, fordi dine legitimationsoplysninger til Microsoft muligvis er blevet ændret, skal du oprette forbindelse til og importere filen igen fra dit personlige OneDrive.

## <a name="how-do-i-schedule-refresh"></a>Hvordan kan jeg planlægge en opdatering?
Når du konfigurerer en tidsplan for opdatering, oprettes der direkte forbindelse til datakilderne i Power BI vha. forbindelsesoplysningerne og legitimationsoplysningerne i datasættet for at hente opdaterede data. Derefter indlæses de opdaterede data i datasættet. Alle visuelle elementer i rapporter og dashboards, der er baseret på dette datasæt i Power BI-tjenesten, opdateres også.

Du kan finde oplysninger om, hvordan du konfigurerer en tidsplan for opdatering, under [Konfigurer tidsplan for opdatering](refresh-scheduled-refresh.md).

## <a name="when-things-go-wrong"></a>Når det går galt
Når tingene går galt, skyldes det som regel, at Power BI ikke kan logge på datakilder, at gatewayen er offline, eller hvis datasættet opretter forbindelse til en datakilde i det lokale miljø. Kontrollér, at Power BI kan logge på datakilderne. Hvis du har ændret den adgangskode, du bruger til at logge på en datakilde med, eller hvis Power BI logges af datakilden, skal du prøve at logge på datakilderne igen vha. legitimationsoplysningerne for datakilden.

Hvis du ændrer i Power BI Desktop-filen på OneDrive og gemmer, og hvis ændringerne ikke afspejles i Power BI inden for ca. en time, kan det skyldes, at Power BI ikke kan oprette forbindelse til OneDrive. Prøv at oprette forbindelse til filen på OneDrive igen. Hvis du bliver bedt om at logge på, skal du vælge Forbliv logget på. Da Power BI ikke kunne oprette forbindelse til OneDrive for at synkronisere med filen, skal du importere filen igen.

Sørg for, at indstillingen **Send mig en mail med meddelelse om opdateringsfejl** er markeret. Du vil have det at vide med det samme, hvis en planlagt opdatering mislykkes.

## <a name="troubleshooting"></a>Fejlfinding
Nogle gange går opdateringen af data muligvis ikke som forventet. Dette skyldes som regel et problem i forbindelse med en gateway. Se artiklerne om fejlfinding af gatewayen for at få oplysninger om værktøjer og kendte problemer.

[Fejlfinding af datagateway i det lokale miljø](service-gateway-onprem-tshoot.md)

[Fejlfinding af Power BI Gateway – Personlig](service-admin-troubleshooting-power-bi-personal-gateway.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

