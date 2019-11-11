---
title: Opret forbindelse til en Oracle-database
description: Trin og downloads, der er nødvendige for at oprette forbindelse mellem Oracle og Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7c91095cf321fed56a0cb1c3c6bd1113f380a524
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73878501"
---
# <a name="connect-to-an-oracle-database"></a>Opret forbindelse til en Oracle-database
Hvis du vil oprette forbindelse til en Oracle-database med **Power BI Desktop**, skal den korrekte Oracle-klientsoftware være installeret på den computer, der kører Power BI Desktop. Hvilken Oracle-klientsoftware du bruger, afhænger af, hvilken version af Power BI Desktop du har installeret – **32-bit** versionen eller **64-bit** versionen.

**Understøttede versioner**: Oracle 9 og nyere, Oracle-klientsoftware 8.1.7 og nyere.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Sådan finder du ud af, hvilken version af Power BI Desktop der er installeret
For at finde ud af, hvilken version af Power BI Desktop der er installeret, skal du vælge **Filer > Hjælp > Om** og derefter kigge på linjen **Version:** . På følgende billede er der installeret en 64-bit version af Power BI Desktop:

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Installér Oracle-klienten
Til **32-bit** versioner af Power BI Desktop skal du bruge følgende link til at downloade og installere **32-bit** Oracle-klienten:

* [32-bit Oracle Data Access Components (ODAC) med Oracle Developer Tools til Visual Studio (12.1.0.2.4)](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

Til **64-bit** versioner af Power BI Desktop skal du bruge følgende link til at downloade og installere **64-bit** Oracle-klienten:

* [64-bit ODAC 12c version 4 (12.1.0.2.4) til Windows x64](https://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Opret forbindelse til en Oracle-database
Når den rette Oracle-klientdriver er installeret, kan du oprette forbindelse til en Oracle-database. Benyt følgende fremgangsmåde for at oprette forbindelse:

1. Åbn vinduet Hent data, og vælg **Database > Oracle-database**
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. I dialogboksen **Oracle-database**, der åbnes, skal du angive navnet på serveren og vælge **Opret forbindelse**. Hvis der kræves et SID, kan du angive det i formatet: *ServerName/SID*, hvor SID er det entydige navn på databasen. Hvis formatet *servernavn/SID* ikke virker, kan du prøve at bruge *servernavn/tjenestenavn*, hvor tjenestenavn er det alias, der bruges, når der oprettes forbindelse.


   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)

   > [!TIP]
   > Hvis du har problemer med at oprette forbindelse i dette trin, kan du prøve at bruge følgende format i feltet Servernavn: (DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=host_name)(PORT=port_num))(CONNECT_DATA=(SERVICE_NAME=service_name)))
   
3. Hvis du vil importere data ved hjælp af en oprindelig databaseforespørgsel, kan du anbringe din forespørgsel i feltet **SQL-sætning**, der bliver tilgængelig, når du udvider sektionen **Avancerede indstillinger** i dialogboksen **Oracle-database**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Når dine oplysninger til Oracle-databasen er angivet i dialogboksen Oracle-database (herunder alle valgfrie oplysninger som f.eks. et SID eller en oprindelig databaseforespørgsel), skal du vælge **OK** for at oprette forbindelse.
5. Hvis Oracle-databasen kræver brugeroplysninger til databasen, skal du angive disse legitimationsoplysninger i dialogboksen, når du bliver bedt om det.


## <a name="troubleshooting"></a>Fejlfinding

Hvis du har downloadet Power BI Desktop via Microsoft Store, kan du muligvis ikke oprette forbindelse til Oracle-databaser på grund af et problem med en Oracle-driver. Hvis du oplever dette problem, returneres fejlmeddelelsen "Objektreferencen er ikke angivet". Du kan løse problemet ved at gøre et af følgende:

* Download i stedet Power BI Desktop fra https://powerbi.microsoft.com/desktop.

* Hvis du vil bruge versionen fra Microsoft Store: Kopiér oraons.dll fra _12.X.X\client_X_ til _12.X.X\client_X\bin_ på din lokale computer. X repræsenterer versions- og mappetal.

Hvis du får vist fejlmeddelelsen *Objektreference er ikke angivet* i Power BI Gateway, når du opretter forbindelse til en Oracle-database, kan du muligvis løse problemet ved at følge instruktionerne i artiklen [Administrer din datakilde – Oracle](service-gateway-onprem-manage-oracle.md).
