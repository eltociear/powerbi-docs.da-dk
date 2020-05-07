---
title: Opret forbindelse til en Oracle-database
description: Trin og downloads, der er nødvendige for at oprette forbindelse mellem Oracle og Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a118cd0874410e538ca8329e0b8c0ed1bdb430b7
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "82149610"
---
# <a name="connect-to-an-oracle-database"></a>Opret forbindelse til en Oracle-database
Hvis du vil oprette forbindelse til en Oracle-database med Power BI Desktop, skal den korrekte Oracle-klientsoftware være installeret på den computer, der kører Power BI Desktop. Den Oracle-klientsoftware, du bruger, afhænger af, hvilken version af Power BI Desktop du har installeret: 32-bit eller 64-bit.

Understøttede Oracle-versioner: 
- Oracle 9 og nyere
- Oracle-klientsoftware 8.1.7 eller nyere

> [!NOTE]
> Hvis du konfigurerer en Oracle-database til Power BI-rapportserver, kan du se oplysningerne i artiklen [Oracle-forbindelsestype](https://docs.microsoft.com/sql/reporting-services/report-data/oracle-connection-type-ssrs?view=sql-server-ver15). 


## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Sådan finder du ud af, hvilken version af Power BI Desktop der er installeret
For at finde ud af, hvilken version af Power BI Desktop der er installeret, skal du vælge **Filer** > **Hjælp** > **Om** og derefter se linjen **Version**. På følgende billede er der installeret en 64-bit version af Power BI Desktop:

![Power BI Desktop-version](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Installér Oracle-klienten
- Til 32-bit versionen af Power BI Desktop skal du [downloade og installere 32-bit Oracle-klienten](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html).

- Til 64-bit versionen af Power BI Desktop skal du [downloade og installere 64-bit Oracle-klienten](https://www.oracle.com/technetwork/database/windows/downloads/index-090165.html).

## <a name="connect-to-an-oracle-database"></a>Opret forbindelse til en Oracle-database
Når den rette Oracle-klientdriver er installeret, kan du oprette forbindelse til en Oracle-database. Benyt følgende fremgangsmåde for at oprette forbindelse:

1. Vælg **Hent data** under fanen **Hjem**. 

2. I vinduet **Hent data**, der vises, skal du vælge **flere** (om nødvendigt), vælge **Database** > **Oracle database**og derefter vælge **Opret forbindelse**.
   
   ![Opret forbindelse til Oracle-databasen](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. I dialogboksen **Oracle-database**, der åbnes, skal du angive navnet på **serveren** og vælge **OK**. Hvis der kræves et SID, skal du angive det i formatet: *Servernavn/SID*, hvor *SID* er det entydige navn på databasen. Hvis formatet *Servernavn/SID* ikke virker, kan du prøve at bruge *Servernavn/Tjenestenavn*, hvor *Tjenestenavn* er det alias, du bruger, når du opretter forbindelse.


   ![Angiv Oracle-servernavnet](media/desktop-connect-oracle-database/connect-oracle-database_3.png)

   > [!TIP]
   > Hvis du har problemer med at oprette forbindelse i dette trin, kan du prøve at bruge følgende format i feltet **Server**: *(DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=host_name)(PORT=port_num))(CONNECT_DATA=(SERVICE_NAME=service_name)))*
   
3. Hvis du vil importere data ved hjælp af en oprindelig databaseforespørgsel, kan du placere din forespørgsel i feltet **SQL-sætning**, der vises, når du udvider afsnittet **Avancerede indstillinger** i dialogboksen **Oracle-database**.
   
   ![Udvid Avancerede indstillinger](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Når du har angivet dine oplysninger til Oracle-databasen i dialogboksen **Oracle-database** (herunder alle valgfrie oplysninger, f.eks. et SID eller en oprindelig databaseforespørgsel), skal du vælge **OK** for at oprette forbindelse.
5. Hvis Oracle-databasen kræver brugeroplysninger til databasen, skal du angive disse legitimationsoplysninger i dialogboksen, når du bliver bedt om det.


## <a name="troubleshooting"></a>Fejlfinding

Hvis du har downloadet Power BI Desktop via Microsoft Store, kan du muligvis ikke oprette forbindelse til Oracle-databaser på grund af et problem med en Oracle-driver. Hvis du oplever dette problem, returneres fejlmeddelelsen: *Objektreference er ikke angivet*. Du kan løse problemet ved at gøre et af følgende:

* Download Power BI Desktop fra [Download Center](https://www.microsoft.com/download/details.aspx?id=58494) i stedet for Microsoft Store.

* Hvis du vil bruge versionen fra Microsoft Store: Kopiér oraons.dll fra _12.X.X\client_X_ til _12.X.X\client_X\bin_ på din lokale computer, hvor _X_ repræsenterer versions- og mappenummeret.

Hvis du får vist fejlmeddelelsen *Objektreference er ikke angivet* i Power BI Gateway, når du opretter forbindelse til en Oracle-database, skal du følge vejledningen under [Administrer din datakilde – Oracle](service-gateway-onprem-manage-oracle.md).

Hvis du bruger Power BI-rapportserver, kan du se vejledningen i artiklen [Oracle-forbindelsestype](https://docs.microsoft.com/sql/reporting-services/report-data/oracle-connection-type-ssrs?view=sql-server-ver15).