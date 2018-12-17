---
title: Løs problemer med import af Access- og .xls-filer i Power BI Desktop
description: Løs problemer med at importere Access-databaser og .xls-regneark til Power BI Desktop og Power Query
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: a1a350a8348dce5ba2553873077a0dfb102a187c
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/07/2018
ms.locfileid: "53024723"
---
# <a name="resolve-issues-importing-access-and-xls-files-in-power-bi-desktop"></a>Løs problemer med at importere Access- og .xls-filer i Power BI Desktop
I **Power BI Desktop** bruger både **Access-databaser** og tidligere versioner af **Excel-projektmapper** (.xls-filer af typen Excel 97-2003) *Access-databaseprogrammet*. Der er tre almindelige situationer, som kan forhindre Access-databaseprogrammet i at fungere korrekt:

## <a name="situation-1-no-access-database-engine-installed"></a>Situation 1: Access-databaseprogrammet er ikke installeret
Når fejlmeddelelsen i Power BI Desktop fortæller, at Access-databaseprogrammet ikke er installeret, skal du installere den version af Access-databaseprogrammet, enten 32-bit eller 64-bit, der svarer til din version af Power BI Desktop. Du kan installere Access-databaseprogrammet fra [downloadsiden](http://www.microsoft.com/download/details.aspx?id=13255).

>[!NOTE]
>Hvis den installerede version af Access-databaseprogrammet har en anden bit-version end din installation af Microsoft Office, kan Office-programmer ikke bruge Access-databaseprogrammet.

## <a name="situation-2-the-access-database-engine-bit-version-32-bit-or-64-bit-is-different-from-your-power-bi-desktop-bit-version"></a>Situation 2: Bit-versionen (32-bit eller 64-bit) af Access-databaseprogrammet er forskellig fra bit-versionen af Power BI Desktop
Denne situation opstår ofte, når den installerede version af Microsoft Office er 32-bit, og den installerede version af Power BI Desktop er 64-bit. Det modsatte kan også opstå, og bit-uoverensstemmelsen opstår i begge tilfælde (hvis du bruger et Office 365-abonnement, kan du se **Situation 3**, som beskriver et andet problem og en anden løsning). En af følgende løsninger kan løse problemet med uoverensstemmende bit-versioner:

1. Skift versionen af Power BI Desktop, så den svarer til bit-versionen af din Microsoft Office-installation. Du kan ændre bit-versionen af Power BI Desktop ved at fjerne Power BI Desktop og derefter installere den version af Power BI Desktop, der svarer til din installation af Office. Hvis du vil vælge en version af Power BI Desktop, skal du gå til downloadsiden for Desktop-versionen og vælge **Avancerede indstillinger for hentning af filer**.
   
   ![](media/desktop-access-database-errors/desktop-access-errors-1.png)
   
   Vælg dit sprog på den downloadside, der vises, og vælg derefter knappen **Download**. På den skærm, der vises, skal du markere afkrydsningsfeltet ud for PBIDesktop.msi for 32-bit versionen eller PBIDesktop_x64.msi for 64-bit versionen. 64-bit versionen er valgt på følgende skærm.
   
   ![](media/desktop-access-database-errors/desktop-access-errors-2.png)
   
   >[!NOTE]
   >Når du bruger 32-bit versionen af Power BI Desktop, og du opretter meget store datamodeller, kan du opleve problemer med manglende hukommelse.
2. Skift versionen af Microsoft Office, så den svarer til bit-versionen af din Power BI Desktop-installation. Du kan ændre bit-versionen af Microsoft Office ved at fjerne Office og derefter installere den version af Office, der svarer til installationen af Power BI Desktop.
3. Hvis fejlen opstod under forsøg på at åbne en .xls-fil (en Excel 97-2003-projektmappe), kan du undgå at bruge Access-databaseprogrammet ved at åbne .xls-filen i Excel og gemme den som en XLSX-fil.
4. Hvis de tre nævnte løsninger ikke kan gennemføres, er det muligt at installere begge versioner af Access-databaseprogrammet, men det er *ikke* en anbefalet løsning. Hvis du installerer begge versioner, kan det løse problemet for Power-forespørgsel til Excel og Power BI Desktop, men det medfører fejl og problemer for alle programmer, der automatisk (som standard) bruger den bit-version af Access-databaseprogrammet, som blev installeret først. Hvis du vil installere begge bit-versioner af Access-databaseprogrammet, skal du[downloade](http://www.microsoft.com/download/details.aspx?id=13255) begge versioner og derefter køre dem begge ved hjælp af parameteren */passive*. Eksempel:
   
       c:\users\joe\downloads\AccessDatabaseEngine.exe /passive
   
       c:\users\joe\downloads\AccessDatabaseEngine_x64.exe /passive

## <a name="situation-3-trouble-using-access-or-xls-files-with-an-office-365-subscription"></a>Situation 3: Problemer med at bruge Access- eller .xls-filer med et Office 365-abonnement
Hvis du bruger et Office 365-abonnement, uanset om det er **Office 2013** eller **Office 2016**, er udbyderen af Access-databaseprogrammet registreret i en virtuel placering i registreringsdatabasen, som *kun* Office-processer kan få adgang til. Miksprogrammet (der har ansvaret for at køre ikke-Office 365 Excel og Power BI Desktop), som ikke er en Office-proces, kan derfor ikke bruge udbyderen af Access-databaseprogrammet.

Du kan løse problemet ved at [downloade og installere den videredistribuerbare version af Access-databaseprogrammet](http://www.microsoft.com/download/details.aspx?id=13255), der stemmer overens med bit-versionen af din installation af Power BI Desktop (se tidligere afsnit for at få flere oplysninger om bit-versioner).

## <a name="other-situations-that-cause-import-issues"></a>Andre situationer, der kan medføre importproblemer
Vi bestræber os på at dække så mange af de problemer, der kan opstå i forbindelse med Access- og .xls-filer, som muligt. Hvis der opstår et problem, der ikke er beskrevet i denne artikel, kan du sende et spørgsmål om problemet til [Support til Power BI](https://powerbi.microsoft.com/support/). Vi kigger jævnligt på problemer, der kan påvirke mange kunder, og inkluderer dem i vores artikler.

