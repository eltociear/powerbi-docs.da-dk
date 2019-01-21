---
title: Opret forbindelse til en Oracle-database
description: Trin og downloads, der er nødvendige for at oprette forbindelse mellem Oracle og Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: dc26d6de5ca22fdabfd80bd7ba1d9830e274f808
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284489"
---
# <a name="connect-to-an-oracle-database"></a>Opret forbindelse til en Oracle-database
Hvis du vil oprette forbindelse til en Oracle-database med **Power BI Desktop**, skal den korrekte Oracle-klientsoftware være installeret på den computer, der kører Power BI Desktop. Hvilken Oracle-klientsoftware du bruger, afhænger af, hvilken version af Power BI Desktop du har installeret – **32-bit** versionen eller **64-bit** versionen.

**Understøttede versioner**: Oracle 9 og nyere, Oracle-klientsoftware 8.1.7 og nyere.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Sådan finder du ud af, hvilken version af Power BI Desktop der er installeret
For at finde ud af, hvilken version af Power BI Desktop der er installeret, skal du vælge **Filer > Hjælp > Om** og derefter kigge på linjen **Version:**. På følgende billede er der installeret en 64-bit version af Power BI Desktop:

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Installér Oracle-klienten
Til **32-bit** versioner af Power BI Desktop skal du bruge følgende link til at downloade og installere **32-bit** Oracle-klienten:

* [32-bit Oracle Data Access Components (ODAC) med Oracle Developer Tools til Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

Til **64-bit** versioner af Power BI Desktop skal du bruge følgende link til at downloade og installere **64-bit** Oracle-klienten:

* [64-bit ODAC 12c version 4 (12.1.0.2.4) til Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Opret forbindelse til en Oracle-database
Når den rette Oracle-klientdriver er installeret, kan du oprette forbindelse til en Oracle-database. Benyt følgende fremgangsmåde for at oprette forbindelse:

1. Åbn vinduet Hent data, og vælg **Database > Oracle-database**
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. I dialogboksen **Oracle-database**, der åbnes, skal du angive navnet på serveren og vælge **Opret forbindelse**. Hvis der kræves et SID, kan du angive det i formatet: *ServerName/SID*, hvor SID er det entydige navn på databasen. Hvis formatet *servernavn/SID* ikke virker, kan du prøve at bruge *servernavn/tjenestenavn*, hvor tjenestenavn er det alias, der bruges, når der oprettes forbindelse.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. Hvis du vil importere data ved hjælp af en oprindelig databaseforespørgsel, kan du anbringe din forespørgsel i feltet **SQL-sætning**, der bliver tilgængelig, når du udvider sektionen **Avancerede indstillinger** i dialogboksen **Oracle-database**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Når dine oplysninger til Oracle-databasen er angivet i dialogboksen Oracle-database (herunder alle valgfrie oplysninger som f.eks. et SID eller en oprindelig databaseforespørgsel), skal du vælge **OK** for at oprette forbindelse.
5. Hvis Oracle-databasen kræver brugeroplysninger til databasen, skal du angive disse legitimationsoplysninger i dialogboksen, når du bliver bedt om det.

