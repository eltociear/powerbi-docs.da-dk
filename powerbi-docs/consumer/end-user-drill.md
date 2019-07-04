---
title: Visning af flere eller færre detaljer i en visualisering
description: I denne artikel gennemgår vi, hvordan man foretager detailudledning i en visualisering i Microsoft Power BI-tjenesten og Power BI Desktop.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: MNAaHw4PxzE
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 6/17/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 29823a2f1ca7f1448df54282e0ce081310974eb3
ms.sourcegitcommit: 8c52b3256f9c1b8e344f22c1867e56e078c6a87c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/19/2019
ms.locfileid: "67265662"
---
# <a name="drill-mode-in-a-visualization-in-power-bi"></a>Analysetilstand i en visualisering i Power BI

I denne artikel gennemgår vi, hvordan man foretager detailudledning i en visualisering i Microsoft Power BI-tjenesten og Power BI Desktop. Power BI-rapporter muliggør flere hierarkier af data for at give dig maksimal indsigt i dine data. Når du får vist flere eller færre detaljer for dine datapunkter, kan du udforske detaljerede oplysninger om dine data. Du kan også drage nytte af funktionerne på dine mobilenheders lille formfaktor.

## <a name="drill-requires-a-hierarchy"></a>Analysetilstand kræver et hierarki

Når en visualisering har et hierarki, kan du foretage detailudledning for at finde flere detaljer. Du har f.eks. en visualisering, der kigger på optælling af olympiske medaljer ud fra et hierarki udgjort af sport, disciplin og begivenhed. Som standard viser visualiseringen medaljeoptælling ud fra sportsgren – gymnastik, skiløb, vandsport osv. Men eftersom den har et hierarki, vises et stadigt mere detaljeret billede, når der vælges visualiseringer (f.eks. søjlediagram, kurvediagram eller boble). Vælg elementet **vandsport** for at få vist data for svømning, udspring og vandpolo.  Vælg elementet **udspring** for at få vist detaljer for vippe, platform og discipliner med synkronudspring.

Du kan føje hierarkier til rapporter, du ejer, men ikke til rapporter, der deles med dig.
Ved du, hvilke Power BI-visualiseringer der indeholder et hierarki? Peg på en visualisering. Hvis du får vist disse kontrolknapper i de øverste højre hjørner, har visualiseringen et hierarki.

![Skærmbillede af ikonet for detailudledning i ét niveau.](./media/end-user-drill/power-bi-drill-icon4.png)  ![Skærmbillede af ikonet til at slå detailudledning til og fra.](./media/end-user-drill/power-bi-drill-icon2.png)  ![Skærmbillede af ikonet for detailudledning af alle felter på én gang.](./media/end-user-drill/power-bi-drill-icon3.png)
![ikonet for visning af færre detaljer](./media/end-user-drill/power-bi-drill-icon5.png) ![skærmbillede af ikonet for udvid.](./media/end-user-drill/power-bi-drill-icon6.png)  

Datoer er en unik type i hierarkiet. Når du føjer et datofelt til en visualisering, tilføjer Power BI automatisk et tidshierarki, der indholder år, kvartal, måned og dag. Du kan finde flere oplysninger under [Funktionsmåde for visualiseringshierarkier og detailudledning](../guided-learning/visualizations.yml?tutorial-step=18), eller se videoen herunder.

<iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Hvis du vil vide mere om at oprette hierarkier ved hjælp af Power BI Desktop, kan du se videoen [Sådan oprettes og tilføjes hierarkier](https://youtu.be/q8WDUAiTGeU).

## <a name="prerequisites"></a>Forudsætninger

1. I Power BI-tjenesten eller Power BI Desktop kræver analysetilstand en visualisering med et hierarki.

1. Åbn [eksemplet på detailhandelsanalyse](../sample-datasets.md) for at følge med. Opret en **træstrukturvisualisering**, der ser på:

    | Brønd | Felt |
    | ---- | ----- |
    | Værdi |Salg<br>\|\_ Enheder i alt i år |
    | Gruppe | Butik<br>\|\_ Område<br>\|\_ By<br>\|\_ Postnummer<br>\|\_ Navn

    Træstrukturen har et hierarki bestående af område, by, postnummer og bynavn. Hvert område har en eller flere byer, hver by har et eller flere postnumre osv. Visualiseringen viser som standard kun områdedata, fordi *Område* vises først på listen.

    ![Skærmbillede af ruden Visualiseringer med feltet Område, der er fremhævet.](media/end-user-drill/power-bi-hierarcy-list.png)

1. Det kan være et smule forvirrende at lære, hvordan de forskellige analyseikoner fungerer sammen. Lad os filtrere træstrukturen for kun at få vist to af de mindre områder: **KY** og **TN**. Vælg træstrukturen, og under **Filtre på visualiseringsniveau** skal du udvide **Område** og vælge **KY** og **TN**.

    ![Skærmbillede af ruden Visualiseringer med filter for KY og TN.](./media/end-user-drill/power-bi-filter.png)

    Nu vises der kun to områder i træstrukturen.

    ![Skærmbillede af det visuelle element, hvor KY og TN er fremhævet.](./media/end-user-drill/power-bi-territories.png)

## <a name="three-ways-to-use-the-drill-features"></a>Tre måder at benytte funktionerne til analyse på

Du har flere muligheder for at få adgang til detailudledning, få vist flere detaljer og udvide de funktioner til visualisering, som har hierarkier. I denne artikel kan du se, hvordan du bruger den første mulighed nedenfor. Når du lærer de grundlæggende funktioner bag detailudledning og udvid, ved du også, hvordan du kan bruge alle tre. De har alle tre samme formål. Prøv dem, og vælg den, du synes bedst om.

- Peg på en visualisering for at få vist og bruge ikonerne.  

    ![Skærmbillede af eksemplet med musen.](./media/end-user-drill/power-bi-hover.png)

- Højreklik på en visualisering for at få vist og bruge menuen.

    ![Skærmbillede af eksemplet med højreklik.](./media/end-user-drill/power-bi-drill-menu.png)

- På menulinjen i Power BI skal du vælge knappen **Udforsk**.

   ![Skærmbillede af valg af Gennemse, der viser detailudledningsikoner og indstillinger.](media/end-user-drill/power-bi-explore.png)

## <a name="drill-pathways"></a>Stier for analyse

### <a name="drill-down"></a>Detailudledning

Der er flere måder, hvorpå du kan få vist flere detaljer i din visualisering. Via **Detailudledning** føres du til næste niveau i hierarkiet. Hvis du kigger på niveauet **Område**, kan du gå ned til niveauet By, derefter Postnummer og til sidst Navn. Hvert trin på stien viser nye oplysninger.

![Diagram, der viser sti til detailudledning](./media/end-user-drill/power-bi-drill-path.png)

### <a name="expand"></a>Udvid

**Udvid** føjer et ekstra hierarkiniveau til den aktuelle visning. Hvis du kigger på niveauet **Område**, kan du udvide og føje oplysninger om by, postnummer og navn til din træstruktur. Hvert trin på stien viser de samme oplysninger og tilføjer et niveau med nye oplysninger.

![Diagram, der viser sti til at udvide](./media/end-user-drill/power-bi-expand-path.png)

Du kan også vælge at bruge detailudledning eller at udvide for ét felt ad gangen eller alle felter på en gang.

## <a name="drill-down-all-fields-at-once"></a>Brug detailudledning på alle felter på en gang

1. Start på det øverste niveau i træstrukturen for at få vist data for KY og TN. Udvid træstrukturen ved at vælge et af håndtagene og trække mod højre.

    ![Skærmbillede af træstrukturvisualiseringen, der viser KY og TN](./media/end-user-drill/power-bi-drill-down.png)

1. Hvis du vil bruge detailudledning på *alle felter på en gang*, skal du vælge dobbeltpilen i øverste venstre hjørne af visualiseringen ![ikon for dobbelt detailudledning](./media/end-user-drill/power-bi-drill-icon3.png). Din træstruktur viser nu bydata for Kentucky og Tennessee.

    ![Skærmbillede af træstrukturvisualiseringen, der viser detailudledning til byerne.](./media/end-user-drill/power-bi-drill-down1.png)

1. Analysér ned én gang mere til niveauet Postnummer i hierarkiet.

    ![Skærmbillede af træstrukturvisualiseringen, der viser detailudledning til postnummeret.](./media/end-user-drill/power-bi-drill-down2.png)

1. Hvis du vil fjerne dig fra detaljerne igen, skal du vælge pil op i øverste venstre hjørne af visualiseringen ![Skærmbillede af ikonet for visning af færre detaljer i ét niveau.](./media/end-user-drill/power-bi-drill-icon5.png).

## <a name="drill-down-one-field-at-a-time"></a>Detailudledning på ét felt ad gangen

Til denne metode bruges ikonet for detailudledning, som vises i øverste højre hjørne af selve visualiseringen.

1. Vælg ikonet for detailudledning for at aktivere funktionen ![Skærmbillede af ikonet for detailudledning til/fra, der er aktiveret.](./media/end-user-drill/power-bi-drill-icon2.png).

    Nu kan du bruge detailudledning for **ét felt ad gangen**.

    ![Skærmbillede af visualisering med en pil, der peger på ikonet for detailudledning til/fra, der er aktiveret.](media/end-user-drill/power-bi-drill-icon-new.png)

    Hvis du ikke aktiverer detailudledning, finder der ingen detailudledning sted, når du vælger et visualiseringselement (f.eks. en søjle, boble eller blad). I stedet for krydsfiltreres de andre diagrammer på rapportsiden.

1. Vælg bladet for **TN**. Din træstruktur viser nu alle de byer i Tennessee, hvor der er en butik.

    ![Skærmbillede af træstrukturen, der kun viser data for TN.](media/end-user-drill/power-bi-drill-down-one1.png)

1. På nuværende tidspunkt kan du:

    1. Fortsætte med at detailudlede for Tennessee.

    1. Detailudlede for en bestemt by i Tennessee.

    1. Udvide i stedet (se **Udvid alle felter på én gang** nedenfor).

    Lad os fortsætte med detailudledning på ét felt ad gangen.  Vælg **Knoxville, TN**. Din træstruktur viser postnummeret for din butik i Knoxville.

    ![Skærmbillede af træstrukturen, der viser postnummeret 37919.](media/end-user-drill/power-bi-drill-down-one2.png)

    Bemærk, at titlen ændres, når du foretager detailudledning eller fjerner detaljerne igen.

## <a name="expand-all-and-expand-one-field-at-a-time"></a>Udvid alle, og udvid ét felt ad gangen

Det er ikke så informativt at have en træstruktur, der kun viser et postnummer.  Så lad os udvide ét niveau ned i hierarkiet.  

1. Med træstrukturen aktiveret kan du vælge ikonet *udvid ned* ![skærmbillede af ikonet udvid ned](./media/end-user-drill/power-bi-drill-icon6.png). Nu vises to niveauer af hierarkiet i træstrukturen: postnummer og butiksnavn.

    ![Skærmbillede af træstrukturen, der viser postnummer og butiksnavn](./media/end-user-drill/power-bi-expand1.png)

1. Hvis du vil have vist alle fire hierarkiniveauer for Tennessee, skal du vælge pilen for at gå et niveau op, indtil du kommer til det andet niveau, **Samlet antal enheder i år efter område og by**, i træstrukturen.

    ![Skærmbillede af træstrukturen, der viser alle data for TN.](media/end-user-drill/power-bi-drill-down-one1.png)

1. Sørg for, at detailudledning stadig er slået til, ![skærmbillede af detailudledning til/fra-ikonet, der er aktiveret.](./media/end-user-drill/power-bi-drill-icon2.png) og vælg ikonet *udvid ned* ![skærmbillede af ikonet for udvid ned.](./media/end-user-drill/power-bi-drill-icon6.png). Nu vises der nogle flere detaljer i træstrukturen. I stedet for kun at vise by og stat vises postnummer også.

    ![Skærmbillede af visualiseringen, der viser by, stat og postnummer.](./media/end-user-drill/power-bi-expand-one3.png)

1. Vælg ikonet *udvid ned* en gang til for at få vist alle fire hierarkiniveauer med detaljer for Tennessee i træstrukturen. Peg på et blad for at få vist flere detaljer.

    ![Skærmbillede af træstrukturen, der viser et værktøjstip med bladspecifikke data.](./media/end-user-drill/power-bi-expand-all.png)

## <a name="drilling-filters-other-visuals"></a>Analyse filtrerer andre visualiseringer

Når du arbejder med analysetilstand, skal du beslutte, hvordan detailudledning og udvidelse påvirker andre visualiseringer på siden.

Detailudledning filtrerer ikke andre visualiseringer i en rapport som standard. Du kan aktivere denne funktion i Power BI Desktop og Power BI-tjenesten.

1. I Desktop skal du vælge fanen **Format** og derefter markere afkrydsningsfeltet **Detailudledning filtrerer andre visualiseringer**.

    ![Skærmbillede, der viser Boring filtrerer andre visuelle elementer i Power BI Desktop](./media/end-user-drill/power-bi-drill-filters-desktop.png)

1. Når du nu udfører detailudledning eller får vist flere detaljer eller udvider i en visualisering med et hierarki, filtrerer handlingen de øvrige visualiseringer på siden.

    ![Skærmbillede af resultatet i Desktop.](./media/end-user-drill/power-bi-drill-filters.png)

    ![Skærmbillede af det andet resultat i Desktop.](./media/end-user-drill/power-bi-drill-filters2.png)

> [!NOTE]
> Hvis du vil aktivere dette i Power BI-tjenesten, skal du vælge **Interaktioner mellem visualiseringer** > **Boring filtrerer andre visuelle elementer**.
>
> ![Skærmbillede, der viser Boring filtrerer andre visuelle elementer i Power BI-tjenesten](./media/end-user-drill/power-bi-drill-filters-service.png)

## <a name="learn-about-the-hierarchy-axis-and-hierarchy-group"></a>Få mere at vide om hierarkiaksen og hierarkigruppen

Du kan tænke på hierarkiaksen og hierarkigruppen som de mekanismer, du kan bruge til at øge og reducere detaljeringsgraden af de data, du vil have vist. Alle data, der kan organiseres i kategorier og underkategorier, er kvalificeret til at have et hierarki, der inkluderer datoer og klokkeslæt.

Du kan oprette en visualisering i Power BI med et hierarki ved at vælge et eller flere datafelter, der skal føjes til enten brønden **Akse** eller brønden **Gruppe**. Tilføj derefter de data, du vil undersøge, som datafelter i brønden **Værdier**. Du ved, om dine data er hierarkiske, hvis ikonerne for *Analysetilstand* vises i øverste venstre og højre hjørne af visualiseringen.

I bund og grund er det praktisk at tænke på to typer hierarkiske data:

- Dato- og klokkeslætsdata – Hvis du har et datafelt med en DateTime-datatype, har du allerede hierarkiske data. Power BI opretter automatisk et hierarki til eventuelle datafelter. Du kan fortolke værdierne i en [DateTime](https://msdn.microsoft.com/library/system.datetime.aspx)-struktur. Du skal kun bruge ét DateTime-felt til brønden **Akse** eller **Gruppe**.

- Kategoridata – hvis Power BI afleder dine data af samlinger, der indeholder undersamlinger, eller de på anden vis har rækker af data, der deler fælles værdier, har du hierarkiske data.

Power BI gør det muligt for dig at udvide med et eller alle undersæt. Du kan analysere dine data for at få vist et enkelt undersæt på hvert niveau eller for at få vist alle undersæt samtidigt på hvert enkelt niveau. Du kan f.eks. analysere et bestemt år eller få vist alle resultater for hvert enkelt år, når du arbejder dig ned igennem hierarkiet.

Du kan også gøre det omvendt.

I følgende sektioner beskrives, hvordan du analyserer fra hhv. den højeste, midterste og laveste visning.

### <a name="hierarchical-data-and-time-data"></a>Hierarkiske data og klokkeslætsdata

I dette eksempel:

1. Følg med vha. [eksemplet på detailhandelsanalyse](../sample-datasets.md), og opret en visualisering med et stablet søjlediagram, der ser på:

    | Brønd | Felt |
    | ---- | ----- |
    | Akse | Tidspunkt<br>\|\_ Måned |
    | Værdier | Salg<br>\|\_ Salg i alt |

    Selvom datafeltet Akse er **Måned**, opretter det stadigt en kategori af typen **År** i brønden **Akse**. Det er fordi, Power BI giver den komplette DateTime-struktur for alle de værdier, der læses. Øverst i hierarkiet vises årets data.

    ![Skærmbillede af den enkelte søjle med data grupperet efter år](media/end-user-drill/power-bi-hierarchical-axis-datetime-1.png)

1. Når detailudledning er slået til, skal du vælge søjlen i diagrammet for at gå ét niveau ned i hierarkiet. Du får vist tre søjler med dataene for de tilgængelige kvartaler.

1. Derefter skal du vælge **Udvid alle ét niveau ned i hierarkiet** fra ikonerne øverst til venstre.

1. Derefter skal du gøre det samme igen for at få vist hierarkiets nederste niveau, der viser resultater for hver enkelt måned.

    ![Skærmbillede af søjlediagrammet med søjle pr. måned](media/end-user-drill/power-bi-hierarchical-axis-datetime-2.png)

Bortset fra visualiseringen kan vi se hierarkiet afspejlet i de data, der gengives for hver enkelt rapport. Vælg ellipsen i øverste højre hjørne, og vælg derefter **Vis data**. I følgende tabel vises resultaterne for detailudledning for en enkelt måned eller for alle måneder:

|Udvidelsestilstand|År|Kvartal|Måned|Dag|
| --- |:---:|:---:|:---:|---|
|Enkelt|![ét år](./media/end-user-drill/power-bi-hierarchical-year.png)|![ét kvartal](media/end-user-drill/power-bi-hierarchical-quarter.png)|![én måned](./media/end-user-drill/power-bi-hierarchical-one-month.png)|![én dag](media/end-user-drill/power-bi-hierarchical-one-day.png)|
|Alle|![alle år](./media/end-user-drill/power-bi-hierarchical-year.png)|![alle kvartaler](media/end-user-drill/power-bi-hierarchical-quarter.png)|![alle måneder](./media/end-user-drill/power-bi-hierarchical-all-month.png)|![alle dage](media/end-user-drill/power-bi-hierarchical-all-day.png)|

Bemærk, at dataene er de samme for rapporterne **Kvartal** og **År**. Når du analyserer ned til detaljeniveauet for **Værdier**, kan du se, hvordan den enkelte rapport bliver mere specifik, og rapporten for "alle måneder" indeholder flere data.

### <a name="hierarchical-category-data"></a>Hierarkiske kategoridata

Data, der er udformet på baggrund af samlinger og undersamlinger, er hierarkiske.

Det er placeringsdata et godt eksempel på. Overvej en tabel i en datakilde, hvor kolonnerne er Land, Stat, By og Postnummer. Data, der deler samme Land, Stat og By, er hierarkiske.

I dette eksempel:

1. I dette eksempel skal du følge med vha. [eksemplet på detailhandelsanalyse](../sample-datasets.md). Opret en visualisering med et stablet søjlediagram, der ser på:

    | Brønd | Felt |
    | ---- | ----- |
    | Værdi |Salg<br>\|\_ Enheder i alt i år |
    | Akse | Butik<br>\|\_ Område<br>\|\_ By – du skal muligvis trække By fra brønden **Forklaring** til brønden **Akse**.<br>\|\_ Postnummer<br>\|\_ Navn |

    ![Skærmbillede af søjlediagrammet, der viser det samlede antal enheder dette år efter område.](media/end-user-drill/power-bi-hierarchical-axis-category-1.png)

1. Når detailudledning er slået til, skal du vælge **Udvid alle ét niveau ned i hierarkiet** tre gange via ikonerne øverst til venstre.

    Du skal være på det nederste niveau i hierarkiet, hvor du kan se resultaterne for Område, By og Postnummer.

    ![Skærmbillede af søjlediagrammet, der viser det laveste niveau i hierarkiet, det mest detaljerede.](media/end-user-drill/power-bi-hierarchical-axis-category-2.png)

Bortset fra visualiseringen kan vi se hierarkiet afspejlet i de data, der gengives for hver enkelt rapport. Vælg ellipsen i øverste højre hjørne, og vælg derefter **Vis data**. I følgende tabel vises resultaterne af detailudledning for et enkelt område eller alle områder.

| Udvidelsestilstand|Område|By|Postnummer|Navn|
| ---|:---:|:---:|:---:|---|
|Enkelt|![ét område](./media/end-user-drill/power-bi-hierarchical-territory.png)|![én by](media/end-user-drill/power-bi-hierarchical-one-territory-city.png)|![ét postnummer](./media/end-user-drill/power-bi-hierarchical-one-territory-city-postal.png)|![ét navn](media/end-user-drill/power-bi-hierarchical-one-territory-city-postal-name.png)|
|Alle|![alle områder](./media/end-user-drill/power-bi-hierarchical-territory.png)|![alle byer](media/end-user-drill/power-bi-hierarchical-all-territory-city.png)|![alle postnumre](./media/end-user-drill/power-bi-hierarchical-all-territory-city-postal.png)|![alle navne](media/end-user-drill/power-bi-hierarchical-all-territory-city-postal-name.png)|

 Efterhånden som du foretager detailudledning, kan du se, hvordan den **enkelte** rapport bliver mere specifik, og rapporten for **alle** områder indeholder flere data.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Hvis du ikke kan oprette et hierarki ved at føje et datofelt til en visualisering, kan det skyldes, at datofeltet slet ikke er gemt som en dato. Hvis du ejer datasættet:

1. Åbn det i visningen *Data* i Power BI Desktop.

1. Vælg den kolonne, der indeholder datoen.

1. På fanen **Udformning** skal du ændre **Datatype** til **Dato** eller **Dato/klokkeslæt**.

![Skærmbillede af visningen Vælg data og i det øverste højre hjørne kan du se Datotype.](media/end-user-drill/power-bi-change-data-type2.png)

Hvis rapporten er blevet delt med dig, kan du kontakte ejeren for at anmode om ændringen.

## <a name="next-steps"></a>Næste trin

[Visualiseringer i Power BI-rapporter](../visuals/power-bi-report-visualizations.md)

[Power BI-rapporter](end-user-reports.md)

[Power BI – Grundlæggende begreber](end-user-basic-concepts.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
