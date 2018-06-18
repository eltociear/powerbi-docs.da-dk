---
title: 'Selvstudium: Importér og analysér data fra en webside ved hjælp af Power BI Desktop'
description: 'Selvstudium: Importér og analysér data fra en webside ved hjælp af Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: tutorial
ms.date: 06/05/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 32de597b594fe8b148a2b0471352e4784d596cec
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/06/2018
ms.locfileid: "34813175"
---
# <a name="tutorial-analyze-web-page-data-using-power-bi-desktop"></a>Selvstudium: Analysér data på en webside ved hjælp af Power BI Desktop

Som inkarneret fodboldfan vil du oprette en rapport med vinderne af europamesterskaberne gennem årene. Med Power BI Desktop kan du importere disse data fra en webside til en rapport og oprette visualiseringer, der viser dataene. I dette selvstudium får du mere at vide om, hvordan du kan bruge Power BI Desktop til at:

- Oprette forbindelse til en webdatakilde og navigere på tværs af de tilgængelige tabeller,
- Forme og transformere data i **Power-forespørgselseditor**,
- Navngive en forespørgsel og importere den til en rapport i Power BI Desktop og 
- Oprette og tilpasse en visualisering på et kort og et cirkeldiagram.

## <a name="connect-to-a-web-data-source"></a>Opret forbindelse til en webdatakilde

Du kan få data om europamestrene fra resultattabellen på siden UEFA European Football Championship på Wikipedia på http://en.wikipedia.org/wiki/UEFA_European_Football_Championship. 

![Resultattabellen på Wikipedia](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

Bemærk, at webforbindelserne kun oprettes ved hjælp af grundlæggende godkendelse. De websteder, der kræver godkendelse, virker muligvis ikke korrekt med webconnectoren.

Sådan importerer du dataene:

1. I Power BI Desktop skal du gå til båndet **Hjem**, trykke på pil ned ud for **Hent data** og derefter vælge **Web**.
   
   ![Hent data fra båndet](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web3.png) 
   
   >[!NOTE]
   >Du kan også vælge selve menupunktet **Hent data** eller vælge **Hent data** fra Power BI-dialogboksen **Introduktion**, vælge **Web** fra sektionen **Alle** eller **Andre** i dialogboksen **Hent data** og derefter vælge **Opret forbindelse**.
   
2. I dialogboksen **Fra web** skal du indsætte URL-adressen `http://en.wikipedia.org/wiki/UEFA_European_Football_Championship` i tekstfeltet **URL-adresse** og derefter vælge **OK**.
   
    ![Hent data fra dialogboks](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web2.png)
   
   Når du har oprettet forbindelse til websiden Wikipedia, viser Power BI-dialogboksen **Navigator** en liste over tabeller, der er tilgængelige på siden. Du kan vælge et af tabelnavnene for at få vist dataene. Tabellen **Results[edit]** indeholder de ønskede data, men de har ikke helt det ønskede format. Du vil omforme og rydde op i dataene, før du indlæser dem i din rapport. 
   
   ![Dialogboksen Navigator](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)
   
   >[!NOTE]
   >I ruden **Eksempel** vises den seneste tabel, der er valgt, men alle de valgte tabeller indlæses i **Power-forespørgselseditor**, når du vælger **Rediger** eller **Indlæs**. 
   
3. Vælg tabellen **Results[edit]** på listen **Navigator**, og vælg derefter **Rediger**. 
   
   Der åbnes et eksempel på tabellen i **Power-forespørgselseditor**, hvor du kan anvende transformationer for at rydde op i dataene. 
   
   ![Power-forespørgselseditor](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)
   
## <a name="shape-data-in-power-query-editor"></a>Form data i Power-Forespørgselseditor

Du vil gøre det lettere at få et hurtigt overblik ved kun at vise år, og hvilke lande der har vundet. Du kan bruge **Power-forespørgselseditor** til at forme og rydde op i disse data.

Først skal du fjerne alle kolonner undtagen **Year** og **Final Winners**.

1. I gitteret **Power-forespørgselseditor** skal du vælge kolonnerne **Year** og **Final Winners** (hold nede på **Ctrl** for at markere flere elementer).
   
2. Højreklik på og vælg **Fjern andre kolonner** på rullelisten, eller vælg **Fjern kolonner** > **Fjern andre kolonner** i gruppen **Administrer kolonner** på båndet **Hjem** for at fjerne alle andre kolonner fra tabellen. 
   
   ![Rullelisten Fjern andre kolonner](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web6.png) eller ![Båndet Fjern andre kolonner](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

Derefter skal du fjerne det ekstra ord **Details** fra cellerne **Year** i kolonnen.

1. Vælg kolonnen **Year** (År).
   
2. Højreklik, og vælg **Erstat værdier** på rullelisten, eller vælg **Erstat værdier** i gruppen **Transformér** under fanen **Hjem** på båndet (findes også i gruppen **En hvilken som helst kolonne** under fanen **Transformér**). 
   
   ![Rullelisten Erstat værdier](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web7.png) eller ![Båndet Erstat værdier](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web8a.png)
   
3. I dialogboksen **Erstat værdier** skal du skrive **Details** i tekstfeltet **Værdi, der skal søges efter**, undlade at udfylde tekstfeltet **Erstat med** og derefter vælge **OK** for at slette ordet "Details" i posterne for **Year**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

Nogle af cellerne for **Year** indeholder kun ordet "Year" i stedet for værdier for år. Du kan filtrere kolonnen **Year** for kun at få vist rækker, der ikke indeholder ordet "Year". 

1. Vælg pil ned på rullelisten til filtrering i kolonnen **Year**.
   
2. Rul ned på rullelisten, og fjern markeringen i afkrydsningsfeltet ud for indstillingen **Year**, og vælg derefter **OK** for at fjerne de rækker, der kun indeholder ordet "Year" i kolonnen **Year**. 

   ![Filtrer data](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

Nu, hvor vi har ryddet dataene op i kolonnen **Year**, skal vi arbejde med kolonnen **Final Winner**. Da du kun ser på listen over finalevindere, kan du omdøbe denne kolonne til **Land**. Sådan omdøber du kolonnen:

1. Dobbeltklik på eller tryk og hold nede på kolonneoverskriften **Final Winner**, eller 
   - Højreklik på kolonneoverskriften **Final Winners**, og vælg **Omdøb** på rullelisten, eller 
   - Vælg kolonnen **Final Winners**, og vælg **Omdøb** i gruppen **En hvilken som helst kolonne** under **Transformér** på båndet. 
   
   ![Rullelisten Omdøb](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7a.png) eller ![Båndet Omdøb](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web8.png)
   
2. Skriv **Country** i overskriften, og tryk på **Enter** for at omdøbe kolonnen.

Du vil også filtrere rækker, f.eks. "2020", der indeholder null-værdier i kolonnen **Country**. Du kan bruge filtermenuen, som du gjorde med værdierne for **Year**, eller du kan:

1. Højreklikke på cellen **Country** på rækken **2020**, som indeholder værdien *null*. 
2. Vælge **Tekstfiltre** > **Forskellig fra** i genvejsmenuen for at fjerne rækker, der indeholder værdien i den pågældende celle.
   
   ![Tekstfilter](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web11.png)
   
## <a name="import-the-query-into-report-view"></a>Importér forespørgslen til rapportvisning

Nu, hvor du har formet dataene, som du ønsker det, er du klar til at navngive forespørgslen "Europamestre" og importere den til din rapport.

1. Skriv **Europamestre** i tekstfeltet **Navn** i ruden **Forespørgselsindstillinger**, og tryk derefter på **Enter**.
   
   ![Navngiv forespørgslen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

2. Vælg **Luk og anvend** > **Luk og anvend** under fanen **Hjem** på båndet.
   
   ![Luk og anvend](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)
   
Forespørgslen indlæses i **rapportvisningen** i Power BI Desktop, hvor du kan se den i ruden **Felter**. 
   
   ![Ruden Felter](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)
>[!TIP]
>Du kan altid vende tilbage til **Power-forespørgselseditor** for at redigere og tilpasse forespørgslen ved at:
>- Vælge ellipsen (**...**) for **flere indstillinger** ud for **Europamestre** i ruden **Felter** og vælge **Rediger forespørgsel** på rullelisten eller
>- Vælge **Rediger forespørgsler** > **Rediger forespørgsler** i gruppen **Eksterne data** under fanen **Hjem** på båndet i rapportvisning. 

## <a name="create-a-visualization"></a>Opret en visualisering

Sådan opretter du en visualisering ud fra dine data: 

1. Vælg feltet **Land** i ruden **Felter**, eller træk det til rapportlærredet. Power BI Desktop genkender dataene som landenavne og opretter automatisk en visualisering af typen **kort**. 
   
   ![Kortvisualisering](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web14.png)
   
2. Du kan udvide kortet ved at trække i håndtagene i hjørnerne, så navnene på alle vinderlandene bliver synlige.  

   ![Udvid kort](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)
   
3. Kortet viser identiske datapunkter for de lande, der har vundet europamesterskaberne. Du kan få størrelsen på de enkelte datapunkter til at afspejle, hvor mange gange landet har vundet, ved at trække feltet **Year** til **Træk datafelter hertil** under **Størrelse** i den nederste del af ruden **Visualiseringer**. Feltet ændres automatisk til en måling med **antal år**, og kortvisualiseringen viser nu større datapunkter for lande, der har vundet flere turneringer. 
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)
   

## <a name="customize-the-visualization"></a>Tilpas visualiseringen

Som du kan se, er det meget nemt at oprette visualiseringer baseret på dine data. Det er også nemt at tilpasse dine visualiseringer, så du bedre kan vise dataene på de måder, du ønsker det. 

### <a name="format-the-map"></a>Formatér kortet
Du kan ændre udseendet af en visualisering ved at markere den og derefter vælge ikonet **Format** (malerrulle) i ruden **Visualiseringer**. Datapunktet eller -punkterne for "Tyskland" i din visualisering kunne f.eks. være vildledende, fordi Vesttyskland har vundet to gange, og Tyskland har vundet én gang, og på kortet lægges to punkter oven på hinanden i stedet for at adskille eller lægge dem sammen. Du kan farvelægge disse to punkter forskelligt for at fremhæve dette. Du kan også give kortet en mere beskrivende og spændende titel. 

1. Mens visualiseringen er markeret, skal du vælge ikonet **Format** og derefter vælge **Datafarver** for at udvide indstillingerne for datafarver. 
   
   ![Formatér datafarver](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web15.png)
   
2. Slå **Vis alle** **til**, vælg rullelisten ud for **Vesttyskland**, og vælg derefter en gul farve. 
   
   ![Skift farve](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web16.png)
   
3. Vælg **Titel** for at udvide indstillingerne for titel, og skriv **Europamestre** i feltet **Titeltekst** i stedet for den aktuelle titel. 
4. Skift **Skriftfarve** til rød, **Tekststørrelse** til **12** og **Skrifttypefamilie** til **Segoe (Bold)**. 
   
   ![Formatér datafarver](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web17.png)
   

Din kortvisualisering ser nu ud som følger:

![Formateret kortvisualisering](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web18.png)
   
### <a name="change-the-visualization-type"></a>Ret visualiseringstypen
Du kan ændre typen af visualisering ved at markere den og derefter vælge et andet ikon øverst i ruden **Visualisering**. Din kortvisualisering mangler f.eks. data for Sovjetunionen og Tjekkoslovakiet, fordi disse lande ikke længere findes på verdenskortet. En anden type visualisering, f.eks. en træstruktur eller et cirkeldiagram, kan være mere nøjagtig, fordi den viser alle værdier. 

Hvis du vil ændre kortet til et cirkeldiagram, skal du markere kortet og derefter vælge ikonet **Cirkeldiagram** i ruden **Visualisering**. 
   
![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web19.png)

>[!TIP]
>- Du kan bruge formateringsindstillingerne for **Datafarver** til at give "Tyskland" og "Vesttyskland" samme farve. 
>- Hvis du vil gruppere lande, der har vundet flest gange, sammen i cirkeldiagrammet, skal du vælge ellipsen (**...**) øverst til højre i visualiseringen og derefter vælge **Sortér efter antal år** på rullelisten. 

Med Power BI Desktop er det nemt at hente data fra en lang række forskellige datakilder og forme dem til dine analysebehov for at kunne visualisere disse data på omfattende og interaktive måder. Når din rapport er færdig, kan du [uploade den til Power BI](desktop-upload-desktop-files.md) og oprette dashboards ud fra den, som du derefter kan dele med andre Power BI-brugere.

## <a name="see-also"></a>Se også
* [Læs andre selvstudier til Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Se videoer om Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Besøg Power BI-forummet](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Læs Power BI-bloggen](http://go.microsoft.com/fwlink/?LinkID=519327)

