---
title: Detailudledning i en visualisering i Power BI
description: Dette dokument viser, hvordan man foretager detailudledning i en visualisering i Microsoft Power BI-tjenesten og Power BI Desktop.
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: MNAaHw4PxzE
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/26/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: fb834c92953c2cafcbca77bc1b3828b385755bca
ms.sourcegitcommit: 743e44fc8730fea0f7149916080b0c6d7eb6359d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/28/2018
---
# <a name="drill-down-in-a-visualization-in-power-bi"></a>Detailudledning i en visualisering i Power BI
## <a name="drill-down-requires-a-hierarchy"></a>Detailudledning kræver et hierarki
Når et visuelt element har et hierarki, kan du foretage detailudledning for at finde flere detaljer. Du har f.eks. en visualisering, der kigger på optælling af olympiske medaljer ud fra et hierarki udgjort af sport, disciplin og begivenhed. Som standard viser visualiseringen medaljeoptælling ud fra sportsgren – gymnastik, skiløb, vandsport osv. Men eftersom den har et hierarki, vises et stadigt mere detaljeret billede, når der vælges visuelle elementer (f.eks. søjle, linje eller boble). Vælg elementet **vandsport** for at få vist data for svømning, udspring og vandpolo.  Vælg elementet **udspring** for at få vist detaljer for vippe, platform og discipliner med synkronudspring.

Du kan føje hierarkier til rapporter, som du ejer, men ikke til rapporter, der deles med dig.
Hvilke Power BI-visualiseringer indeholder et hierarki?  Hold musen over en visualisering, og hvis du får vist disse kontrolknapper for detailudledning i de øverste hjørner, har din visualisering et hierarki.

![](media/power-bi-visualization-drill-down/power-bi-drill-icon4.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon3.png)
![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) ![](media/power-bi-visualization-drill-down/power-bi-drill-icon6.png)  

Datoer er en entydig type i hierarkiet. Når du føjer et datofelt til en visualisering, tilføjer Power BI automatisk et tidshierarki, der indholder år, kvartal, måned og dag. Du kan finde flere oplysninger under [Funktionsmåde for visuelle hierarkier og detailudledning](guided-learning/visualizations.yml#step-18) eller se videoen herunder.


  <iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Hvis du vil vide mere om at oprette hierarkier ved hjælp af Power BI Desktop, kan du se videoen [Sådan oprettes og tilføjes hierarkier](https://youtu.be/q8WDUAiTGeU)
> 
> 

## <a name="two-methods-to-drill-down"></a>To metoder til detailudledning
Du har to forskellige måder til at analysere ned (og op) i din visualisering.  Begge er beskrevet i denne artikel. Begge metoder resulterer det samme, så brug den metode, du bedst kan lide.

> [!NOTE]
> For at komme videre skal du [åbne eksemplet med detailanalyse](sample-datasets.md) i Power BI-tjenesten og oprette en træstruktur, der kigger på **Samlet antal enheder dette år** (værdier) efter **Område**, **By**, **Postnummer** og **Navn** (gruppe).  
> 
> 

## <a name="method-one-for-drill-down"></a>Metode 1 til analysering
Denne metode bruger ikonerne for detailudledning, der vises i de øverste hjørner af selve visualiseringen.

1. I Power BI skal du åbne en rapport i [Læsevisning eller Redigeringsvisning](service-reading-view-and-editing-view.md). Detailudledning kræver en visualisering med et hierarki. 
   
   I animationen herunder er vist et hierarki.  Visualiseringen har et hierarki bestående af område, by, postnummer og bynavn. Hvert område har en eller flere byer, hver by har et eller flere postnumre osv. Som standard viser visualiseringen kun områdedata, fordi *Område* vises først på listen.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. For at aktivere detailudledning skal du vælge pilikonet i øverste højre hjørne af visualiseringen. Når ikonet er mørkt, er detailudledning aktiveret. Hvis du ikke aktiverer detailudledning, sker der krydsfiltrering af de andre diagrammer på rapportsiden, når der vælges et visuelt element (f.eks en søjle eller boble).    
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon.png)
3. Hvis du vil analysere **ét felt ad gangen**, skal du vælge et af elementerne i din visualisering. I et liggende søjlediagram betyder det, at du skal klikke på en af søjlerne. I en træstruktur betyder det, at du skal klikke på et af **bladene**. Bemærk, at titlen ændres, når du foretager detailudledning eller fjerner detaljerne igen. I denne animation ændres navnet fra "Samlet antal enheder dette år efter område" til "Samlet antal enheder dette år efter område og by" og derefter fra "Samlet antal enheder dette år efter område, by og postnummer" til "Samlet antal enheder dette år efter område, by, postnummer og navn". Og for at fjerne detaljerne igen skal du vælge ikonet for **Fjern detaljer**![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) i øverste venstre hjørne af visualiseringen som vist nedenfor.
   
   ![](media/power-bi-visualization-drill-down/drill.gif)
4. For at analysere ***alle felterne ned på én gang*** skal du vælge dobbeltpilen i øverste venstre hjørne af visualiseringen.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillall.png)
5. For at fjerne detaljerne igen skal du vælge pil op i øverste venstre hjørne af visualiseringen.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillup2.png)

## <a name="method-two-for-drill-down"></a>Metode 2 til analysering
Denne metode bruger **Explore**-rullelisten fra den øverste menulinje i Power BI.

1. I Power BI skal du åbne en rapport i [Læsevisning eller Redigeringsvisning](service-reading-view-and-editing-view.md). Detailudledning kræver en visualisering med et hierarki. 
   
   I billedet herunder er vist et hierarki.  Visualiseringen har et hierarki bestående af område, by, postnummer og bynavn. Hvert område har en eller flere byer, hver by har et eller flere postnumre osv. Som standard viser visualiseringen kun områdedata, fordi *Område* vises først på listen.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. For at aktivere detailudledning skal du vælge en visualisering og fra den øverste menulinje i Power BI vælge **Udforsk** > **Detailudledning**. Ikonet for detailudledning i øverste højre hjørne af visualiseringen ændres til sort baggrund. ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  
   
   ![](media/power-bi-visualization-drill-down/power-bi-explore2.png)
3. Når indstillingen er aktiveret, skal du analysere ét felt ned ad gangen ved at vælge et af bladene i træstrukturen. I dette eksempel er området med navnet **NC** valgt for at få vist det samlede antal enheder, der er solgt i år i North Carolina ud fra by.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drilldown-1.png)
4. For at analysere alle felterne ned på én gang skal du vælge **Udforsk** > **Vis næste niveau**.
   
   ![](media/power-bi-visualization-drill-down/power-bi-show-next-level.png)
5. For at fjerne detaljerne igen skal du vælge **Udforsk** > **Fjern dig fra detaljerne**.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-up2.png)

6. Hvis du vil se de data, der bruges til at oprette visualiseringen, skal du vælge **Se data**. Dataene vises i en rude under visualiseringen. Denne rude vises fortsat, efterhånden som du fortsætter med at foretage detailudledning via det visuelle element. Du kan finde flere oplysninger under [Vis data, der bruges til at oprette det visuelle element](service-reports-show-data.md).

## <a name="understanding-the-hierarchy-axis-and-hierarchy-group"></a>Om hierarkiaksen og hierarkigruppen
Du kan tænke på hierarkiaksen og hierarkigruppen som de mekanismer, du kan bruge til at øge og reducere detaljeringsgraden af de data, du vil have vist. Alle data, der kan organiseres i kategorier og underkategorier, er kvalificeret til at have et hierarki. Det inkluderer, selvfølgelig, datoer og klokkeslæt.

Du kan oprette en visualisering i Power BI for at få et hierarki ved at vælge et eller flere datafelter, der skal føjes til enten brønden **Akse** eller brønden **Gruppe** sammen med de data, du vil undersøge som datafelter i brønden **Værdier**. Du ved, om dine data er hierarkiske, hvis ikonerne Analysetilstand vises i øverste venstre og højre hjørne af visualiseringen. 

I bund og grund er det praktisk at tænke på to typer hierarkiske data:
- Dato- og klokkeslætsdata – Hvis du har et datafelt med en DateTime-datatype, har du allerede hierarkiske data. I Power BI oprettes automatisk et hierarki ti eventuelle datafelter, hvis værdier kan fortolkes i en [DateTime](https://msdn.microsoft.com/library/system.datetime.aspx)-struktur. Du skal kun bruge ét DateTime-felt til brønden **Akse** eller **Gruppe**.
- Kategoridata – Hvis dine data er afledt af samlinger, der indeholder undersamlinger, eller de på anden vis har rækker af data, der deler fælles værdier, har du hierarkiske data.

Power BI gør det muligt for dig at udvide med et eller alle undersæt. Du kan analysere dine data for at se et enkelt undersæt på hvert niveau eller for at se alle undersæt samtidigt på hvert enkelt niveau. Du kan f.eks. analysere et bestemt år eller få vist alle resultater for hvert enkelt år, når du arbejder dig ned igennem hierarkiet. Du kan også gøre det omvendt.

I følgende sektioner beskrives, hvordan du analyserer fra hhv. den højeste, midterste og laveste visning.

### <a name="hierarchical-data-and-time-data"></a>Hierarkiske data og klokkeslætsdata
I dette eksempel skal du følge med vha. [eksemplet på detailhandelsanalyse](sample-datasets.md) og oprette en visualisering med et stablet søjlediagram, der ser på **Måned** (akse) efter **SamletSalg** (værdier).  

Selvom datafeltet Akse er **Måned**, opretter det stadigt en kategori af typen **År** i brønden **Akse**. Det er fordi, Power BI giver den komplette DateTime-struktur for alle de værdier, der læses. Øverst i hierarkiet vises årets data.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-1.png)

Når tilstanden Analysér ned er slået til, skal du klikke på søjlen i diagrammet for at gå ét niveau ned i hierarkiet. Du får vist tre søjler med dataene for de tilgængelige kvartaler. Derefter skal du vælge **Udvid alle ét niveau ned i hierarkiet** i ikonerne øverst til venstre. Derefter skal du gøre det samme igen for at få vist hierarkiets nederste niveau, der viser resultater for hver enkelt måned.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-2.png)

Bortset fra visualiseringen kan vi se hierarkiet afspejlet i de data, der gengives for hver enkelt rapport. I følgende tabel vises resultaterne for **Vis data** i en rapportanalyse for en enkelt måned eller for alle måneder. 

Bemærk, at dataene er de samme for kvartals- og årsrapporter, men når du analyserer ned til detaljeniveauet for **Værdier**, kan du se, hvordan den enkelte rapport bliver mere specifik, og rapporten for "alle måneder" indeholder flere data.


|Udvidelsestilstand|År|Kvartal|Måned|Dag|
| ---|:---:|:---:|:---:|---|
|Enkelt|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-day.png)|
|Alle|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-day.png)|


### <a name="hierarchical-category-data"></a>Hierarkiske kategoridata
Data, der er modelleret fra samlinger og undersamlinger, er hierarkiske. Det er placeringsdata et godt eksempel på. Overvej en tabel i en datakilde, hvor kolonnerne er Land, Stat, By og Postnummer. Data, der deler samme Land, Stat og By, er hierarkiske.

I dette eksempel skal du følge med vha. [eksemplet på detailhandelsanalyse](sample-datasets.md). Opret en visualisering med et stablet søjlediagram, der viser **Samlede enheder dette år** (værdier) efter **Territorium**, **By**, **Postnummer** og **Navn** (gruppe).  

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-1.png)

Når tilstanden Analysér ned er slået til, skal du vælge **Udvid alle ét niveau ned i hierarkiet** tre gange via ikonerne øverst til venstre.
Du skal være på det nederste niveau i hierarkiet, hvor du kan se resultaterne for Territorium, By og Postnummer.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-2.png)

Bortset fra visualiseringen kan vi se hierarkiet afspejlet i de data, der gengives for hver enkelt rapport. I følgende tabel vises resultaterne for **Vis data** i en rapportanalyse for et enkelt territorium eller for alle territorier. Efterhånden som du analyserer, kan du se, hvordan den enkelte rapport bliver mere specifik, og rapporten for "alle territorier" indeholder flere data.


| Udvidelsestilstand|Distrikt|By|Postnummer|Navn|
| ---|:---:|:---:|:---:|---|
|Enkelt|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal-name.png)|
|Alle|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal-name.png)|


## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger
* Hvis du ikke kan oprette et hierarki ved at føje et datofelt til en visualisering, kan det skyldes, at "datofeltet" slet ikke er gemt som en dato. Hvis du ejer datasættet, kan du åbne det i *Data*-visningen i Power BI Desktop, vælge den kolonne, der indeholder datoen og under fanen Modellering ændre **Datatypen** til **Dato** eller  **Dato/klokkeslæt**. Hvis rapporten er blevet delt med dig, kan du kontakte ejeren for at anmode om ændringen.  
  
  ![](media/power-bi-visualization-drill-down/power-bi-change-data-type2.png)

## <a name="next-steps"></a>Næste trin
[Visualiseringer i Power BI-rapporter](power-bi-report-visualizations.md)

[Power BI-rapporter](service-reports.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

