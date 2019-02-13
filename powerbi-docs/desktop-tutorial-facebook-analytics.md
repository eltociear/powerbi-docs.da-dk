---
title: 'Selvstudium: Facebook-analyse ved hjælp af Power BI Desktop'
description: 'Selvstudium: Facebook-analyse ved hjælp af Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 8d80d0a2d976661f2b62476be7742b755d11f1c9
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/13/2019
ms.locfileid: "56216533"
---
# <a name="tutorial-facebook-analytics-using-power-bi-desktop"></a>Selvstudium: Facebook-analyse ved hjælp af Power BI Desktop

I dette selvstudium lærer du, hvordan du importerer data fra Facebook og bruger dem i Power BI Desktop. Du kommer til at oprette forbindelse til og importere data fra Power BI's Facebook-side, anvende transformationer på de importerede data og bruge dataene i rapportvisualiseringer.

## <a name="connect-to-a-facebook-page"></a>Opret forbindelse til en Facebook-side

I dette selvstudium bruges der data fra [Microsoft Power BI's Facebook-side](https://www.facebook.com/microsoftbi) (*https://www.facebook.com/microsoftbi*). Du behøver ikke nogen særlige legitimationsoplysninger for at oprette forbindelse og importere dataene fra denne side bortset fra en personlig Facebook-konto.

1. Åbn Power BI Desktop, og vælg **Hent data** i dialogboksen **Introduktion**. Du kan også vælge **Hent data** på fanen **Hjem** på båndet og derefter vælge **Mere...**.
   
2. I dialogboksen **Hent data** skal du vælge **Facebook** i gruppen **Onlinetjenester** og derefter vælge **Opret forbindelse**.
   
   ![Hent data](media/desktop-tutorial-facebook-analytics/t_fb_getdataother.png)
   
   Der vises en dialogboks med en advarsel om risikoen ved at bruge en tredjepartstjeneste.
   
   ![Advarsel om tredjepart](media/desktop-tutorial-facebook-analytics/t_fb_connectingtotps.png)
   
3. Vælg **Fortsæt**. Dialogboksen **Facebook** vises.
   
4. Skriv eller indsæt sidenavnet **microsoftbi** i tekstfeltet **Brugernavn**, vælg **Opslag** i rullemenuen **Forbindelse**, og vælg derefter **OK**.
   
   ![Opret forbindelse](media/desktop-tutorial-facebook-analytics/2.png)
   
5. Når du bliver bedt om dine legitimationsoplysninger, skal du logge på med din egen Facebook-konto og give Power BI adgang via din konto.
   
   ![Legitimationsoplysninger](media/desktop-tutorial-facebook-analytics/facebookcredentials.png)

   Når du har oprettet forbindelse til Power BI's Facebook-side, kan du se en eksempelvisning af sidens data med **Opslag**. 
   
   ![Eksempelvisning af data](media/desktop-tutorial-facebook-analytics/t_fb_1-loadpreview.png)
   
## <a name="shape-and-transform-the-imported-data"></a>Udform og transformér de importerede data

Du vil gerne se og vise, hvilke opslag der har fået flest kommentarer i tidens løb, men du har bemærket, at dataene i **created_time** i eksempelvisningen af data under **Opslag** er svære at læse og forstå, og at der slet ikke er nogen kommentarer. Du skal udføre og rense dataene for at få flest mulige oplysninger ud af dem. Du kan bruge **Power-forespørgselseditor** i Power BI Desktop til at redigere dataene, før eller efter du importerer dem i Power BI Desktop. 

### <a name="split-the-datetime-column"></a>Opdel kolonnen med dato/klokkeslæt

Adskil først værdierne dato og tid i kolonnen **created_time**, så den bliver mere læsevenlig. 

1. Vælg **Rediger** i eksempelvisningen af Facebook-dataene. 
   
   ![Redigering af data i eksempelvisning](media/desktop-tutorial-facebook-analytics/t_fb_1-editpreview.png)
   
   **Power-forespørgselseditor** i Power BI Desktop åbner i et nyt vindue, og eksempelvisningen af dataene fra Power BI's Facebook-side vises. 
   
   ![Power-forespørgselseditor](media/desktop-tutorial-facebook-analytics/t_fb_1-intoqueryeditor.png)
   
2. Vælg kolonnen **created_time**. Bemærk, at datatypen Tekst i øjeblikket anvendes, hvilket betegnes med et ikon af typen **ABC** i kolonneoverskriften. Højreklik på overskriften, og vælg **Opdel kolonne > Efter separator** i rullemenuen, eller vælg **Opdel kolonne > Efter separator** under **Transformér** på fanen Hjem på båndet.  
   
   ![Opdel kolonne efter separator](media/desktop-tutorial-facebook-analytics/delimiter1.png)
   
3. I dialogboksen **Opdel kolonne efter separator** skal du vælge **Brugerdefineret** i rullemenuen, angive **T** (det tegn, der starter tidsdelen i værdien created_time) i inputfeltet og vælge **OK**. 
   
   ![Dialogboksen Opdel kolonne efter separator](media/desktop-tutorial-facebook-analytics/delimiter2.png)
   
   Kolonnen opdeles i to kolonner, der indeholder strengene før og efter separatoren **T**, og kaldes henholdsvist **created_time.1** og **created_time.2**. Bemærk, at Power BI automatisk har registreret og ændret datatyperne til **Dato** for den første kolonne og **Tid** for den anden kolonne, og at dato- og tidsværdierne er blevet formateret, så de er mere læsevenlige.
   
4. Omdøb kolonnerne ved at dobbeltklikke på hver kolonneoverskrift eller ved at markere hver kolonne og derefter vælge **Omdøb** i gruppen **En hvilken som helst kolonne** under fanen **Transformér** på båndet. Skriv derefter nye kolonneoverskrifter **created_date** og **created_time**.
   
   ![Nye dato- og tidskolonner](media/desktop-tutorial-facebook-analytics/delimiter3.png)
   
### <a name="expand-the-nested-column"></a>Udvid den indlejrede kolonne

Nu hvor dataene for dato og tid er, som du ønsker, kan du få vist kommentarer ved at udvide en indlejret kolonne. 

1. Markér kolonnen **object_link**, og vælg derefter ikonet ![ikonet udvid](media/desktop-tutorial-facebook-analytics/14.png) for at åbne dialogboksen **Udvid/Sammenfat**. Vælg **forbindelser**, og vælg derefter **OK**. 
   
   ![Udvid object_link](media/desktop-tutorial-facebook-analytics/expand1.png)
   
   Kolonneoverskriften ændres til **object_link.connections**.
2. Vælg igen ikonet ![ikonet udvid](media/desktop-tutorial-facebook-analytics/14.png) øverst i kolonnen **object_link.connections**, vælg **kommentarer**, og vælg derefter **OK**. Kolonneoverskriften ændres til **object_link.connections.comments**.
   
3. Vælg ikonet ![ikonet udvid](media/desktop-tutorial-facebook-analytics/14.png) øverst i kolonnen **object_link.connections.comments**, og vælg denne gang **Sammenfat** i stedet for Udvid i dialogboksen. Vælg **# Antal id'er**, og vælg derefter **OK**. 
   
   ![Sammenfattede kommentarer](media/desktop-tutorial-facebook-analytics/expand2.png)
   
   Antallet af kommentarer for hver meddelelse vises nu i kolonnen. 
   
4. Omdøb kolonnen **Count of object_link.connections.comments.id** til **Number of comments**.
   
5. Vælg pilen i rullemenuen ved siden af overskriften **Number of comments**, og vælg **Sortér faldende** for at se opslag sorteret efter flest til færrest kommentarer. 
   
   ![Kommentarer pr. meddelelse](media/desktop-tutorial-facebook-analytics/data-fixed.png)
   
### <a name="review-query-steps"></a>Gennemse forespørgselstrin

Idet du udformede og transformerede data i **Power-forespørgselseditor**, blev hvert trin registreret i området **Anvendte trin** i ruden **Forespørgselsindstillinger** i højre side af vinduet Power-forespørgselseditor. Du kan gå tilbage igennem de Anvendte trin for at se nøjagtigt, hvilke ændringer du har lavet, og redigere, slette eller omarrangere dem, hvis det er nødvendigt. Dette kan dog være risikabelt, da ændring af foregående trin kan bryde senere trin. 

Efter du har anvendt datatransformationerne indtil nu, bør dine Anvendte trin ligne følgende:
   
   ![Anvendte trin](media/desktop-tutorial-facebook-analytics/applied-steps.png)
   
   >[!TIP]
   >De underliggende data for Anvendte trin er formler, som er skrevet på **Power-forespørgselssproget**, der også er kendt som **M**-sproget. Hvis du vil se og redigere formlerne, skal du vælge **Avanceret editor** i gruppen **Forespørgsel** under fanen Hjem på båndet. 

### <a name="import-the-transformed-data"></a>Importér de transformerede data

Når du er tilfreds med dataene, skal du vælge **Luk og anvend** > **Luk og anvend** under fanen Hjem på båndet for at importere dem i Power BI Desktop. 
   
   ![Luk og anvend](media/desktop-tutorial-facebook-analytics/t_fb_1-loadandclose.png)
   
   Der vises en dialogboks med statussen for indlæsningen af data i Power BI Desktop-datamodellen. 
   
   ![Indlæsning af data](media/desktop-tutorial-facebook-analytics/t_fb_1-loading.png)
   
   Når dataene er indlæst, vises de i Rapportvisningen som en ny forespørgsel på listen Felter.
   
   ![Ny forespørgsel](media/desktop-tutorial-facebook-analytics/fb-newquery.png)
   
## <a name="use-the-data-in-report-visualizations"></a>Brug dataene i rapportvisualiseringer 

Nu, hvor du har importeret dataene fra Facebook-siden, kan du hurtigt og nemt få indsigt i dataene ved hjælp af visualiseringer. Det er nemt at oprette en visualisering. Du skal blot markere et felt eller trække det fra listen **Felter** til rapportcanvasset.

### <a name="create-a-bar-chart"></a>Opret et liggende søjlediagram

1. I Rapportvisning i Power BI Desktop skal du vælge **message** på listen Felter eller trække den til canvasset. En tabel med alle opslagsmeddelelser vises på canvasset. 
   
   ![Ny forespørgsel](media/desktop-tutorial-facebook-analytics/table-viz.png)
   
2. Når du har markeret tabellen, skal du også markere **Number of comments** på listen Felter eller trække den ind i tabellen. 
   
3. Vælg ikonet **Stablet liggende søjlediagram** i ruden Visualiseringer. Tabellen ændres til et liggende søjlediagram med antallet af kommentarer pr. opslag. 
   
   ![Liggende søjlediagram](media/desktop-tutorial-facebook-analytics/barchart1.png)
   
4. Vælg ellipsen (...) i øverste højre hjørne af visualiseringen, og vælg derefter **Sortér efter antal kommentarer** for at sortere tabellen faldende efter antallet af kommentarer. 
   
   ![Sortér efter antallet af kommentarer](media/desktop-tutorial-facebook-analytics/barchart2.png)
   
5. Bemærk, at de fleste kommentarer er knyttet til **tomme** meddelelser. Disse opslag kan have været historier, links, videoer eller andet indhold, der ikke er tekst. Hvis du vil bortfiltrere tomme rækker, skal du vælge **message (alle)** under **Filtre** nederst i ruden Visualiseringer, vælge **Markér alle** og derefter vælge **Tomme** for at fjerne markeringen af den. Filterindtastningen ændres til **message er ikke (Tomme)**, så forsvinder rækken Tomme fra diagramvisualiseringen. 
   
   ![Bortfiltrer tomme](media/desktop-tutorial-facebook-analytics/barchart3.png)
   
### <a name="format-the-chart"></a>Formatér diagrammet

Visualiseringen bliver mere interessant, men du kan ikke se meget af teksten i opslagene i diagrammet. Gør følgende for at få vist mere af opslagene:

1. Ved hjælp af håndtagene i diagramvisualiseringen kan du tilpasse størrelsen af diagrammet, så det bliver så stort som muligt. 
   
2. Med diagrammet markeret skal du vælge **ikonet Formatér** (malerrullen) i ruden Visualiseringer.
   
3. Vælg pilen i rullemenuen ved siden af **Y-akse**, og træk skyderen ved siden af **Maksimumstørrelse** hele vejen til højre (50 %). 
4. Reducer også **Tekststørrelsen** til **10**, så der kan være mere tekst.
   
   ![Formatering af ændringer](media/desktop-tutorial-facebook-analytics/barchart4.png)
   
   Der vises nu mere af indholdet i opslagene i diagrammet. 
   
   ![Vis mere af opslagene](media/desktop-tutorial-facebook-analytics/barchart5.png)
   
Der vises ikke nøjagtige værdier på diagrammets X-akse (antal kommentarer), og det ser lidt malplaceret ud nederst i diagrammet. Du beslutter dig for at bruge datanavne i stedet. 

1. Vælg ikonet Formatér, og vælg derefter skyderen ved siden af **X-akse** for at slå den **Fra**. 
   
2. Vælg skyderen ved siden af **Datanavne** for at slå dem **Til**. Nu vises det nøjagtige antal kommentarer for hvert opslag i diagrammet.
   
   ![Anvend datanavne](media/desktop-tutorial-facebook-analytics/barchart6.png)
   
### <a name="edit-the-data-type"></a>Rediger datatypen

Det nærmer sig, men datanavnene har alle decimalen **,0**, hvilket er distraherende og misvisende, da **antallet af opslag** antal vil være et heltal. Du skal ændre datatypen for kolonnen **Number of posts** til heltal.

1. Du redigerer datatypen ved at højreklikke på **Query1** på listen Felter eller holde over den og vælge ellipsen **Flere indstillinger** (...) og derefter vælge **Rediger forespørgsel**. Du kan også vælge **Rediger forespørgsel** i området **Eksterne data** under fanen Hjem på båndet og derefter vælge **Rediger forespørgsler** i rullemenuen. **Power-forespørgselseditor** i Power BI Desktop åbnes i et separat vindue.
   
   ![Rediger forespørgsel via listen Felter](media/desktop-tutorial-facebook-analytics/editquery1.png)     ![Rediger forespørgsler via båndet](media/desktop-tutorial-facebook-analytics/t_fb_editquery.png)
   
2. I Power-forespørgselseditor skal du vælge kolonnen **Number of comments** og ændre datatypen til **Heltal** ved at gøre et af følgende: 
   - Vælg ikonet **1,2** ved siden af kolonneoverskriften **Number of comments**, og vælg **Heltal** i rullemenuen, eller
   - højreklik på kolonneoverskriften, og vælg **Skift type > Heltal**, eller
   - vælg **datatype: decimaltal** i gruppen **Transformér** under fanen Hjem, eller vælg **Heltal** i gruppen **En hvilken som helst kolonne** under fanen **Transformér**.
   
   Ikonet i kolonneoverskriften ændres til **123**, hvilket betegner datatypen Heltal.
   
   ![Skift datatype](media/desktop-tutorial-facebook-analytics/change-datatype.png)
   
3. Vælg **Luk og anvend**, eller blot **Anvend** for at anvende ændringerne, mens vinduet Power-forespørgselseditor fortsat er åbent. Når ændringerne er blevet indlæst, bliver datanavnene i diagrammet heltal. 
   
   ![Diagram med heltal](media/desktop-tutorial-facebook-analytics/vis-3.png)
   
### <a name="create-a-date-slicer"></a>Opret et dataudsnit

Du vil visualisere antallet af kommentarer i løbet af en tidsperiode. Du kan oprette en visualisering med udsnit for at filtrere diagramdataene efter forskellige tidsrammer. 

1. Klik på et tomt området på canvasset, og vælg derefter **ikonet Udsnit** i ruden Visualiseringer. En tom udsnitsvisualisering vises. 
   
   ![Vælg ikonet for udsnit](media/desktop-tutorial-facebook-analytics/slicer1.png)
   
2. Vælg feltet **created_date** på listen Felter, eller træk det til det nye udsnit. Udsnittet ændres til et udsnit med et datointerval baseret på feltets datatype for Dato.
   
   ![Udsnit med skyderen Datointerval](media/desktop-tutorial-facebook-analytics/slicer2.png)
   
3. Flyt skyderhåndtagene for at vælge forskellige datointervaller, og bemærk, hvordan diagramdataene filtreres tilsvarende. Du kan også vælge datofelterne i udsnittet, og angive specifikke datoer, eller vælge dem i et pop op-vindue med en kalender.
    
   ![Udsnit af data](media/desktop-tutorial-facebook-analytics/slicer3.png)
   
### <a name="format-the-visualizations"></a>Formatér visualiseringerne

Du beslutter dig for at give diagrammet en mere beskrivende og spændende titel. 

1. Med diagrammet markeret skal du vælge ikonet **Formatér** og derefter pilen i rullemenuen for at udvide **Titel**.
2. Ret **Titelteksten** til **Kommentar pr. opslag**. 
3. Vælg pilen i rullemenuen ved siden af **Skrifttypefarve**, og vælg derefter en grøn farve for at matche de grønne søjler i visualiseringerne.
4. Øg **Tekststørrelsen** til **10**, og ret **Skrifttypefamilien** til **Segoe (Bold)**.

![Formatér diagramtitel](media/desktop-tutorial-facebook-analytics/formatting1.png)

Eksperimentér med andre formateringsindstillinger for at ændre udseendet af visualiseringerne. 

![Visualiseringer](media/desktop-tutorial-facebook-analytics/vis-1.png)

## <a name="create-more-visualizations"></a>Opret flere visualiseringer

Som du kan se, er det nemt at tilpasse visualiseringer i din rapport, så dataene kan præsenteres på den måde, du vil. Prøv f.eks. at bruge de importerede Facebook-data til at oprette dette søjlediagram med antal kommentarer i løbet af en tidsperiode.

![Kurvediagram](media/desktop-tutorial-facebook-analytics/moreviz.png)

Med Power BI Desktop er det nemt at hente data fra en lang række forskellige datakilder og forme dem til dine analysebehov for at kunne visualisere disse data på omfattende og interaktive måder. Når din rapport er færdig, kan du [uploade den til Power BI-tjenesten](desktop-upload-desktop-files.md) og oprette dashboards ud fra den, som du derefter kan dele med andre Power BI-brugere.

## <a name="next-steps"></a>Næste trin
* [Læs andre selvstudier til Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Se videoer om Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Besøg Power BI-forummet](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Læs Power BI-bloggen](http://go.microsoft.com/fwlink/?LinkID=519327)

