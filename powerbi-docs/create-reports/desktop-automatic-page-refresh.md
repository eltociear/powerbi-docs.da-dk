---
title: Automatisk sideopdatering i Power BI Desktop (eksempelvisning)
description: Få mere at vide om, hvordan du automatisk opdaterer sider til DirectQuery-kilder i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/26/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7c9ba490a2cc30d42fee4f2317dbf5d4026ab59a
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "83299694"
---
# <a name="automatic-page-refresh-in-power-bi-desktop-preview"></a>Automatisk sideopdatering i Power BI Desktop (eksempelvisning)

Når du overvåger kritiske hændelser, er det vigtigt, at data opdateres, så snart kildedataene opdateres. I produktionsindustrien er det for eksempel vigtigt at få vide, når en maskine ikke fungerer korrekt eller er ved ikke at fungere korrekt.

Funktionen til automatisk sideopdatering i Power BI lader din aktive rapportside forespørge om nye data ved en foruddefineret hyppighed for [DirectQuery-kilder](https://docs.microsoft.com/power-bi/desktop-directquery-about).

## <a name="using-automatic-page-refresh"></a>Brug af automatisk sideopdatering

Hvis du vil have vist denne prøveversion, skal du aktivere funktionen til automatisk sideopdatering i Power BI Desktop. Gå til **Fil > Indstillinger**, vælg derefter **Indstillinger**, og vælg **Funktioner til eksempelvisning** i ruden til venstre. Aktivér funktionen ved at markere afkrydsningsfeltet ud for *Automatisk sideopdatering*. Automatisk sideopdatering er kun tilgængelig for DirectQuery-datakilder.

Hvis du vil bruge automatisk sideopdatering, skal du vælge den rapportside, du vil aktivere opdatering for. Vælg ikonet **Formatering** (en malerulle) i ruden **Visualiseringer**, og find **Sideopdatering** nederst i ruden. 

![Placering af Sideopdatering](media/desktop-automatic-page-refresh/automatic-page-refresh-01.png)

På følgende billede vises kortet **Sideopdatering**. De nummererede elementer forklares i de følgende afsnit:

![Kortet Sideopdatering](media/desktop-automatic-page-refresh/automatic-page-refresh-02.png)

1.    Skyderen Automatisk sideopdatering – slår sideopdatering til eller fra
2.    Intervalværdi for sideopdatering – talværdi for opdateringsinterval
3.    Intervalenhed for sideopdatering – intervalenhed for sideopdatering

Her kan du aktivere sideopdatering og vælge opdateringsvarighed. Standardværdien er 30 minutter, og det mindste opdateringsinterval er 1 sekund. Din rapport begynder at blive opdateret med det interval, du har angivet. 

## <a name="determining-the-page-refresh-interval"></a>Bestemmer intervallet for sideopdatering

Når automatisk sideopdatering er aktiveret, sender Power BI Desktop hele tiden forespørgsler til din DirectQuery-kilde. Der vil være en forsinkelse mellem den forespørgsel, der sendes, og de data, der returneres. I forbindelse med korte opdateringsintervaller skal du derfor bekræfte, at forespørgslerne returnerer de data, der forespørges efter, inden for det konfigurerede interval. Hvis dataene ikke returneres inden for intervallet, opretter du situationer, hvor visuelle elementer opdateres mindre hyppigt, end de konfigureres.

Som bedste fremgangsmåde skal opdateringsintervallet mindst svare til den forventede nye hastighed for datamodtagelse:

* Hvis der modtages nye data i kilden hvert 20. minut, kan opdateringsintervallet ikke være mindre end 20 minutter. 

* Hvis der modtages nye data hvert sekund, skal intervallet indstilles til ét sekund. 


I forbindelse med lave opdateringsintervaller som et sekund skal du også overveje typen af datakilden til den direkte forespørgsel, den belastning, dine forespørgsler forårsager for datakilden, afstanden mellem rapportlæserne og kapacitetens datacenter osv. 

Du kan beregne dette ved hjælp af funktionen Effektivitetsanalyse i Power BI Desktop, som gør det muligt for dig at bekræfte, om den enkelte forespørgsel efter visuelle elementer har nok tid til at returnere resultatet fra kilden, og hvor tiden bruges. På baggrund af resultaterne af effektivitetsanalysen kan du justere og foretage ændringer i datakilden, eller du kan eksperimentere med andre visuelle elementer og målinger i din rapport.

På følgende billede vises resultaterne af en DirectQuery i Effektivitetsanalyse:

![Resultater af effektivitetsanalysen](media/desktop-automatic-page-refresh/automatic-page-refresh-03.png)

Lad os overveje nogle andre egenskaber for denne datakilde. 

1.    Data ankommer hvert andet sekund. 
2.    Effektivitetsanalysen viser den maksimale forespørgselstid + visningstid på ca. 4,9 sekunder (4688 millisekunder). 
3.    Datakilden er konfigureret til at håndtere cirka 1000 samtidige forespørgsler pr. sekund. 
4.    Du forventer, at ca. 10 brugere skal have vist rapporten samtidig.

Resultatet er derfor som følger:

* **5 visuelle elementer x 10 brugere = cirka 50 forespørgsler**

Denne beregning resulterer i meget større belastning end den, datakilden kan understøtte. Dataene ankommer hvert andet sekund, så det skal være din opdateringshastighed. Eftersom forespørgslen tager ca. fem sekunder, skal vi dog angive opdateringshastigheden til mere end fem sekunder. 

Bemærk også, at dette resultat kan være anderledes, når du publicerer din rapport til tjenesten, da rapporten bruger den Analysis Services-forekomst, der hostes i cloudmiljøet. Det kan være en god idé at justere opdateringshastighederne i overensstemmelse hermed. 

Power BI tager højde for timing af forespørgsler og opdatering og kører kun den næste opdateringsforespørgsel, når alle de resterende opdateringsforespørgsler er fuldført. Så selvom dit opdateringsinterval er kortere end den tid, det tager at behandle dine forespørgsler, vil Power BI kun opdatere igen, når de resterende forespørgsler er fuldført. 

Lad os derefter se på, hvordan du potentielt kan registrere og diagnosticere ydelsesproblemer som en kapacitetsadministrator. Du kan også se afsnittet **Ofte stillede spørgsmål om automatisk sideopdatering** senere i denne artikel for at læse flere spørgsmål og svar om ydeevne og fejlfinding.

## <a name="automatic-page-refresh-in-the-power-bi-service"></a>Automatisk sideopdatering i Power BI-tjenesten

Du kan også angive intervaller for automatisk sideopdatering for rapporter, der er oprettet i Power BI Desktop, og som er publiceret til Power BI-tjenesten. 

Automatisk sideopdatering for rapporter i Power BI-tjenesten er konfigureret med en fremgangsmåde, der minder om konfigurationen i Power BI Desktop. Når den er konfigureret i Power BI-tjenesten, understøtter den automatiske opdatering af sider også [integreret Power BI](../developer/embedded/embedding.md)-indhold. På følgende billede vises konfigurationen **Sideopdatering** for Power BI-tjenesten:

![Automatisk sideopdatering i Power BI-tjenesten](media/desktop-automatic-page-refresh/automatic-page-refresh-04.png)

1.    Skyderen Automatisk sideopdatering – slår sideopdatering til eller fra
2.    Intervalværdi for sideopdatering – talværdi for opdateringsinterval, skal være et heltal
3.    Intervalenhed for sideopdatering – intervalenhed for sideopdatering

### <a name="page-refresh-intervals"></a>Sideopdateringsintervaller

De sideopdateringsintervaller, der er tilladt i Power BI-tjenesten, påvirkes af rapportens arbejdsområdetype. Dette gælder for alle følgende rapporter:

* Udgivelse af en rapport i et arbejdsområde, hvor automatisk sideopdatering er aktiveret.
* Redigering af et sideopdateringsinterval, der allerede findes i et arbejdsområde.
* Oprettelse af en rapport direkte i tjenesten.

Power BI Desktop har ingen begrænsninger for opdateringsinterval. Opdateringsintervallet kan finde sted hvert sekund. Når rapporter udgives i Power BI-tjenesten, kan der dog være visse begrænsninger, og de beskrives i følgende afsnit.

### <a name="restrictions-on-refresh-intervals"></a>Begrænsninger for opdateringsintervaller

I Power BI-tjenesten er der begrænsninger for automatisk sideopdatering, afhængigt af faktorer som f.eks. arbejdsområdet, og om der benyttes Premium-tjenester.

Vi vil tydeliggøre, hvordan dette fungerer, ved at begynde med nogle baggrundsoplysninger om kapaciteter og arbejdsområder:

**Kapaciteter** er et kernekoncept i Power BI og repræsenterer et sæt ressourcer (lager, processor og hukommelse), der bruges til at hoste og levere Power BI-indhold. Kapaciteter er enten delte eller dedikerede. En **delt kapacitet** er delt med andre Microsoft-kunder, mens en **dedikeret kapacitet** kun er beregnet til en enkelt kunde. Dedikerede kapaciteter introduceres i artiklen [Administration af Premium-kapaciteter](../admin/service-premium-capacity-manage.md).

I en delt kapacitet kører dine arbejdsbelastninger på databehandlingsressourcer, der deles med andre kunder. Eftersom kapaciteten skal dele ressourcerne, pålægges begrænsninger for at sikre *fair play*, f.eks. den maksimale modelstørrelse (1 GB) og den maksimale daglige opdateringshastighed (otte gange pr. dag).

**Arbejdsområder**  i Power BI er placeret i kapaciteter, og de repræsenterer sikkerheds-, samarbejds- og udrulningsobjektbeholdere. Hver bruger af Power BI har et personligt arbejdsområde, der er kendt som **Mit arbejdsområde**. Der kan oprettes flere arbejdsområder for at muliggøre samarbejde og udrulning, og disse kaldes **arbejdsområder**. Arbejdsområder, herunder personlige arbejdsområder, oprettes som standard i den **delte kapacitet**.

Her er nogle oplysninger om de to forskellige arbejdsområdescenarier:

**Delte arbejdsområder**  – for almindelige arbejdsområder (arbejdsområder, der ikke er en del af en Premium-kapacitet) har den automatiske sideopdatering et minimumsinterval på 30 minutter (det laveste tilladte interval).

**Premium-arbejdsområder**  – tilgængeligheden af automatisk sideopdatering i Premium-arbejdsområder afhænger af de arbejdsbelastningsindstillinger, som din Premium-administrator har konfigureret til Power BI Premium-kapaciteten. Der er to variabler, som kan påvirke din mulighed for at konfigurere automatisk sideopdatering:

 1. *Funktion til/fra*: Hvis din kapacitetsadministrator har besluttet at deaktivere funktionen, kan du ikke konfigurere nogen form for sideopdatering i din publicerede rapport.

 2. *Minimumsinterval for opdatering*: Når du aktiverer funktionen, skal din kapacitetsadministrator konfigurere et minimumsinterval for opdateringen. Hvis intervallet er lavere end minimumsintervallet, tilsidesætter Power BI-tjenesten intervallet for at overholde det minimumsinterval, der er angivet af kapacitetsadministratoren.

I nedenstående tabel beskrives flere detaljer, hvor denne funktion er tilgængelig, og grænserne for hver kapacitetstype og [lagertilstand](../connect-data/service-dataset-modes-understand.md)

| Lagertilstand | Dedikeret kapacitet | Delt kapacitet |
| --- | --- | --- |
| Direkte forespørgsel | **Understøttet** – ja. <br>**Minimumsinterval for opdatering** – 1 sekund <br>**Tilsidesættelse af kapacitetsadministrator**  – ja. | **Understøttet** – ja. <br>**Minimumsinterval for opdatering** – 30 minutter <br>**Tilsidesættelse af kapacitetsadministrator** – nej. |
| Importér | **Understøttet** – nej. <br>**Minimumsinterval for opdatering** – I/T. <br>**Tilsidesættelse af kapacitetsadministrator** – I/T. | **Understøttet** – nej. <br>**Minimumsinterval for opdatering** – I/T. <br>**Tilsidesættelse af kapacitetsadministrator** – I/T. |
| Blandet tilstand (DQ + andre) | **Understøttet** – ja. <br>**Minimumsinterval for opdatering** – 1 sekund <br>**Tilsidesættelse af kapacitetsadministrator**  – ja. | **Understøttet** – ja. <br>**Minimumsinterval for opdatering** – 30 minutter <br>**Tilsidesættelse af kapacitetsadministrator** – nej. |
| Live connect AS | **Understøttet** – nej. <br>**Minimumsinterval for opdatering** – I/T. <br>**Tilsidesættelse af kapacitetsadministrator** – I/T. | **Understøttet** – nej. <br>**Minimumsinterval for opdatering** – I/T. <br>**Tilsidesættelse af kapacitetsadministrator** – I/T. |
| Live connect PBI | **Understøttet** – nej. <br>**Minimumsinterval for opdatering** – I/T. <br>**Tilsidesættelse af kapacitetsadministrator** – I/T. | **Understøttet** – nej. <br>**Minimumsinterval for opdatering** – I/T. <br>**Tilsidesættelse af kapacitetsadministrator** – I/T. |

> [!NOTE]
> Når du publicerer din rapport med automatisk sideopdatering aktiveret fra Power BI Desktop til tjenesten, skal du angive legitimationsoplysningerne for DirectQuery-datakilden i menuen Indstillinger for datasæt.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Der er et par ting, du skal være opmærksom på, når du bruger automatisk sideopdatering i Power BI Desktop eller i Power BI-tjenesten.

* Tilstandene Import, LiveConnect og pushlagring understøttes ikke for automatisk sideopdatering.  
* Sammensatte modeller, der har mindst én DirectQuery-datakilde, understøttes.
* Power BI Desktop har ingen begrænsninger for opdateringsinterval, og opdateringen kan derfor finde sted så hyppigt som hvert sekund. Når rapporter publiceres i Power BI-tjenesten, kan der dog være visse begrænsninger, hvilket blev beskrevet tidligere i dette dokument.

### <a name="performance-diagnostics"></a>Ydeevnediagnosticering

Automatisk sideopdatering kan bruges til at overvåge scenarier og til at udforske hurtigt skiftende data. I nogle tilfælde kan dette dog belaste kapaciteten eller datakilden unødigt.

Power BI har følgende sikkerhedsforanstaltninger for at forhindre unødig belastning af datakilder:

1. Alle forespørgsler om automatisk sideopdatering kører ved en **lavere** prioritet for at sikre, at interaktive forespørgsler (f.eks. sideindlæsning og tværgående filtrering af visuelle elementer) har fortrinsret.
2. Hvis din forespørgsel ikke er færdig, før den næste opdateringscyklus er udført, udsteder Power BI ikke nye opdateringsforespørgsler, før den forrige forespørgsel er fuldført. Hvis du f.eks. har et opdateringsinterval på ét sekund, og dine forespørgsler i gennemsnit tager fire sekunder, udsteder Power BI kun en forespørgsel hvert 4. sekund.

Der er to områder, hvor du stadig kan opleve flaskehalse for ydeevnen:

1. **Kapaciteten:** Forespørgslen søger først i Premium-kapaciteten, der udvides og evaluerer den DAX-forespørgsel, der genereres fra rapportvisualiseringerne, i kildeforespørgslerne.
2. **Datakilde for DirectQuery:** De oversatte forespørgsler i det forrige trin køres derefter mod kilden. Dette er dine SQL-servere, SAP Hana-kilder osv.

Hvis du bruger [Premium Metrics-appen ](../admin/service-admin-premium-monitor-capacity.md), der er tilgængelig for administratorer, kan du få visualiseret, hvor meget af kapaciteten der bruges af forespørgsler med lav prioritet.

Forespørgsler med lav prioritet består af automatiske sideopdateringsforespørgsler og forespørgsler om modelopdatering. Der er i øjeblikket ingen måde at skelne mellem belastningen fra automatisk sideopdatering og fra forespørgsler om modelopdatering.

Hvis du bemærker, at din kapacitet er ved at blive overbelastet med forespørgsler med lav prioritet, er der nogle foranstaltninger, du kan træffe:

1. Anmod om en større Premium-SKU.
2. Kontakt rapportejeren, og bed om at sænke opdateringsintervallet.
3. I portalen til kapacitetsadministration kan du:
  1. Slå automatisk sideopdatering for den pågældende kapacitet fra.
  2. Øge minimumsintervallet for opdatering, som påvirker alle rapporter i kapaciteten.


### <a name="frequently-asked-questions"></a>Ofte stillede spørgsmål

Dette afsnit indeholder almindelige spørgsmål og svar 

1. Jeg er en rapportforfatter. Jeg har defineret opdateringsintervallet for min rapport til 1 sek. i Desktop, men efter at jeg har publiceret min rapport, opdateres den ikke i tjenesten.

    * Kontrollér, at automatisk sideopdatering er slået til for siden. Da denne indstilling gælder pr. side, skal du sikre dig, at den er aktiveret for hver side i rapporten, som du vil opdatere.
    * Kontrollér, at du har uploadet til et arbejdsområde med en tilknyttet Premium-kapacitet. Hvis det ikke er tilfældet, låses opdateringsintervallet ved 30 minutter.
    * Hvis din rapport er i et Premium-arbejdsområde, skal du spørge din administrator, om denne funktion er aktiveret for den vedhæftede kapacitet. Sørg desuden for, at minimumsintervallet for opdatering af kapaciteten er lavere eller det samme som din rapports.

2. Jeg er en kapacitetsadministrator. Jeg ændrede indstillinger for intervallet for den automatiske sideopdatering, men de slår ikke igennem. Med andre ord opdateres rapporter stadig ved en uønsket hastighed eller opdateres slet ikke, selvom jeg har aktiveret funktionen.

    * Det tager op til fem minutter, før ændringer af indstillinger for automatisk sideopdatering, der foretages i administratorgrænsefladen, træder i kraft.
    * Ud over at aktivere automatisk sideopdatering for kapaciteten skal du også aktivere funktionen for de sider i en rapport, du vil have opdateret.

3. Min rapport fungerer i blandet tilstand (DQ + import). Ikke alle visuelle elementer opdateres.

    * Hvis dine visuelle elementer refererer til importtabeller, er dette forventeligt. Funktionen Import understøtter ikke automatisk sideopdatering.
    * Se spørgsmål 1 i dette afsnit.

4. Min rapport er indtil nu blevet opdateret fint i tjenesten, men det er pludselig holdt op.

    * Prøv at opdatere siden for at se, om problemet løser sig selv.
    * Kontakt kapacitetsadministratoren, da vedkommende kan have slået funktionen fra eller forøget minimumsintervallet for opdateringen (se spørgsmål 2).

5. Jeg er en rapportforfatter. Mine visuelle elementer opdateres ikke ved den hastighed, jeg har angivet. De opdateres ved en lavere hastighed.

    * Hvis dine forespørgsler tager længere tid at udføre, vil opdateringsintervallet blive forsinket. Automatisk sideopdatering venter på, at alle forespørgsler er færdige med at køre, før der køres nye.
    * Kapacitetsadministratoren kan have angivet et minimumsinterval for opdateringen, der er højere end det, du angiver for din rapport. Kontakt kapacitetsadministratoren, og anmod om, at få intervallet reduceret.

6. Kommer automatiske sideopdateringer fra cachelageret?

    * Nej, cachelagrede data tilsidesættes af alle forespørgsler om automatisk sideopdatering.


## <a name="next-steps"></a>Næste trin

Du kan få flere oplysninger i følgende artikler:

* [Brug af DirectQuery in Power BI](../connect-data/desktop-directquery-about.md)
* [Brug Effektivitetsanalyse til at undersøge ydeevnen for rapportelementer](desktop-performance-analyzer.md)
* [Udrulning og administration af Power BI Premium-kapaciteter](../guidance/whitepaper-powerbi-premium-deployment.md)
* [Datakilder i Power BI Desktop](../connect-data/desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](../connect-data/desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](../connect-data/desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](../connect-data/desktop-enter-data-directly-into-desktop.md)   
