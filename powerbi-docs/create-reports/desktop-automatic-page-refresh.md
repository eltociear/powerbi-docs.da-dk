---
title: Automatisk sideopdatering i Power BI Desktop
description: I denne artikel vises det, hvordan du automatisk opdaterer sider til DirectQuery-kilder i Power BI Desktop.
author: davidiseminger
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 06/10/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1febf93d35500d56f5b3b104487725f33d7b17ad
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85234173"
---
# <a name="automatic-page-refresh-in-power-bi-desktop"></a>Automatisk sideopdatering i Power BI Desktop 

Når du overvåger kritiske hændelser, er det vigtigt, at data opdateres, så snart kildedataene opdateres. I produktionsindustrien er det for eksempel vigtigt at få vide, når en maskine ikke fungerer korrekt, eller hvis der er tegn på, at der snart opstår fejlfunktion.

Funktionen til automatisk sideopdatering i Power BI gør det muligt for din aktive rapportside at forespørge om nye data med en foruddefineret hyppighed for [DirectQuery-kilder](https://docs.microsoft.com/power-bi/desktop-directquery-about).

## <a name="using-automatic-page-refresh"></a>Brug af automatisk sideopdatering

Automatisk sideopdatering er kun tilgængelig for DirectQuery-datakilder.

Hvis du vil bruge automatisk sideopdatering, skal du vælge den rapportside, du vil aktivere opdatering for. Vælg knappen **Formatering** (en malerulle) i ruden **Visualiseringer**, og find **Sideopdatering** nederst i ruden. 

![Placering af Sideopdatering](media/desktop-automatic-page-refresh/automatic-page-refresh-01.png)

På følgende billede vises kortet **Sideopdatering**. De nummererede elementer beskrives efter billedet.

![Kortet Sideopdatering](media/desktop-automatic-page-refresh/automatic-page-refresh-02.png)

1.    Slår sideopdatering til eller fra
2.    Talværdi for sideopdateringsintervallet
3.    Enhed for sideopdateringsintervallet

På dette kort kan du aktivere sideopdatering og vælge opdateringsvarigheden. Standardværdien er 30 minutter. Det mindste opdateringsinterval er ét sekund. Din rapport begynder at blive opdateret med det interval, du har angivet. 

## <a name="determining-the-page-refresh-interval"></a>Bestemmer intervallet for sideopdatering

Når automatisk sideopdatering er aktiveret, sender Power BI Desktop hele tiden forespørgsler til din DirectQuery-kilde. Når forespørgslen er sendt, går der et øjeblik, før der returneres data. I forbindelse med korte opdateringsintervaller skal du derfor bekræfte, at forespørgslerne returnerer de data, der forespørges efter, inden for det konfigurerede interval. Hvis dataene ikke returneres inden for intervallet, opdateres visuals sjældnere end konfigureret.

Som bedste fremgangsmåde skal opdateringsintervallet mindst svare til den forventede nye hastighed for datamodtagelse:

* Hvis der modtages nye data i kilden hvert 20. minut, kan opdateringsintervallet ikke være mindre end 20 minutter. 

* Hvis der modtages nye data hvert sekund, skal intervallet indstilles til ét sekund. 

Ved korte opdateringsintervaller som ét sekund skal du overveje følgende faktorer:
- Typen af DirectQuery-datakilde
- Den belastning, forespørgslerne opretter i den
- Rapportlæsernes afstand til kapacitetens datacenter 

Du kan beregne returtiderne ved hjælp af Effektivitetsanalyse i Power BI Desktop. Med Effektivitetsanalyse kan du kontrollere, om de enkelte visualforespørgsler har nok tid til at komme tilbage med resultaterne fra kilden. Du kan også se, hvor tiden bruges. På baggrund af resultaterne fra Effektivitetsanalyse kan du justere datakilden, eller du kan eksperimentere med andre visuelle elementer og målinger i din rapport.

På følgende billede vises resultaterne af en DirectQuery i Effektivitetsanalyse:

![Effektivitetsanalyse-resultater](media/desktop-automatic-page-refresh/automatic-page-refresh-03.png)

Lad os antage, at denne datakilde har nogle andre egenskaber: 

-    Data ankommer hvert andet sekund. 
-    Effektivitetsanalyse viser den maksimale forespørgselstid + visningstid på ca. 4,9 sekunder (4,688 millisekunder). 
-    Datakilden er konfigureret til at håndtere cirka 1.000 samtidige forespørgsler pr. sekund. 
-    Du forventer, at ca. 10 brugere skal have vist rapporten samtidig.

Dette resulterer derfor i følgende ligning:

**5 visuelle elementer x 10 brugere = cirka 50 forespørgsler**

Resultatet af denne beregning viser en meget større belastning, end datakilden kan understøtte. Dataene ankommer hvert andet sekund, så det skal være din opdateringshastighed. Men eftersom forespørgslen tager ca. fem sekunder, skal du angive opdateringshastigheden til mere end fem sekunder. 

Bemærk også, at dette resultat kan være anderledes, når du publicerer din rapport i tjenesten. Denne forskel opstår, fordi rapporten vil bruge den Azure Analysis Services-forekomst, der er hostet i cloudmiljøet. Det kan være en god idé at justere opdateringshastighederne i overensstemmelse hermed. 

Power BI tager højde for timing af forespørgsler og opdatering og kører kun den næste opdateringsforespørgsel, når alle de resterende opdateringsforespørgsler er fuldført. Så selvom dit opdateringsinterval er kortere end den tid, det tager at behandle dine forespørgsler, vil Power BI opdatere igen, når de resterende forespørgsler er fuldført. 

Lad os nu se på, hvordan du potentielt kan registrere og diagnosticere ydeevneproblemer som en kapacitetsadministrator. Du kan også se afsnittet [Ofte stillede spørgsmål](#frequently-asked-questions) senere i denne artikel, hvor du finder flere spørgsmål og svar om ydeevne og fejlfinding.

## <a name="automatic-page-refresh-in-the-power-bi-service"></a>Automatisk sideopdatering i Power BI-tjenesten

Du kan også angive intervaller for automatisk sideopdatering for rapporter, der er oprettet i Power BI Desktop, og som er publiceret til Power BI-tjenesten. 

Hvis du vil konfigurere automatisk sideopdatering for rapporter i Power BI-tjenesten, skal du bruge en fremgangsmåde, der minder om fremgangsmåden i Power BI Desktop. Når den er konfigureret i Power BI-tjenesten, understøtter den automatiske opdatering af sider også [integreret Power BI](../developer/embedded/embedding.md)-indhold. På dette billede vises konfigurationen **Sideopdatering** for Power BI-tjenesten:

![Automatisk sideopdatering i Power BI-tjenesten](media/desktop-automatic-page-refresh/automatic-page-refresh-04.png)

Disse beskrivelser svarer til de nummererede elementer: 

1.    Slår sideopdatering til eller fra.
2.    Talværdi for sideopdateringsintervallet. Skal være et helt tal.
3.    Enhed for sideopdateringsintervallet.

### <a name="page-refresh-intervals"></a>Sideopdateringsintervaller

De sideopdateringsintervaller, der er tilladt i Power BI-tjenesten, påvirkes af rapportens arbejdsområdetype. Dette gælder for disse rapporter:

* Udgivelse af en rapport i et arbejdsområde, hvor automatisk sideopdatering er aktiveret.
* Redigering af et sideopdateringsinterval, der allerede findes i et arbejdsområde
* Oprettelse af en rapport direkte i tjenesten.

Power BI Desktop har ingen begrænsninger for opdateringsintervaller. Opdateringsintervallet kan være så hyppigt som hvert sekund. Når rapporter publiceres i Power BI-tjenesten, kan der dog være visse begrænsninger. Disse begrænsninger er beskrevet i de følgende afsnit.

### <a name="restrictions-on-refresh-intervals"></a>Begrænsninger for opdateringsintervaller

I Power BI-tjenesten er der begrænsninger for automatisk sideopdatering, som er baseret på faktorer som f.eks. arbejdsområdet, og om der bruges Premium-tjenester.

Vi vil tydeliggøre, hvordan disse begrænsninger fungerer, ved at begynde med nogle baggrundsoplysninger om kapaciteter og arbejdsområder.

*Kapaciteter* er et vigtigt Power BI-koncept. De repræsenterer et sæt ressourcer (lager, processor og hukommelse), der bruges til at hoste og levere Power BI-indhold. Kapaciteter er enten delte eller dedikerede. En *delt kapacitet* deles med andre Microsoft-kunder. En *dedikeret kapacitet* er fuldt allokeret til en enkelt kunde. Du finder en introduktion til dedikerede kapaciteter i artiklen [Administration af Premium-kapaciteter](../admin/service-premium-capacity-manage.md).

I en delt kapacitet kører dine arbejdsbelastninger på databehandlingsressourcer, der deles med andre kunder. Eftersom kapaciteten skal dele ressourcerne, pålægges der begrænsninger for at sikre *fair play*, f.eks. den maksimale modelstørrelse (1 GB) og den maksimale daglige opdateringshastighed (otte gange pr. dag).

Kapaciteter omfatter Power BI-*arbejdsområder*. De repræsenterer objektbeholdere til sikkerheds, samarbejde og udrulning. Hver bruger af Power BI har et personligt arbejdsområde, der er kendt som **Mit arbejdsområde**. Der kan oprettes flere arbejdsområder for at muliggøre samarbejde og udrulning. De kaldes *arbejdsområder*. Arbejdsområder, herunder personlige arbejdsområder, oprettes som standard i den delte kapacitet.

Her er nogle oplysninger om de to forskellige arbejdsområdescenarier:

**Delte arbejdsområder**. For almindelige arbejdsområder (arbejdsområder, der ikke er en del af en Premium-kapacitet) har den automatiske sideopdatering et minimuminterval på 30 minutter (det laveste tilladte interval).

**Premium-arbejdsområder**. Tilgængeligheden af automatisk sideopdatering i Premium-arbejdsområder afhænger af de arbejdsbelastningsindstillinger, Premium-administratoren har konfigureret til Power BI Premium-kapaciteten. Der er to variabler, som kan påvirke din mulighed for at konfigurere automatisk sideopdatering:

 - **Funktion til/fra**. Hvis kapacitetsadministratoren har deaktiveret funktionen, kan du ikke konfigurere nogen form for sideopdatering i din publicerede rapport.

 - **Minimuminterval for opdatering**. Når du aktiverer funktionen, skal kapacitetsadministratoren konfigurere et minimuminterval for opdateringen. Hvis intervallet er lavere end minimumsintervallet, tilsidesætter Power BI-tjenesten intervallet for at overholde det minimumsinterval, der er angivet af kapacitetsadministratoren. Denne tilsidesættelse kaldes "tilsidesættelse af kapacitetsadministrator" i følgende tabel. 

I denne tabel beskrives flere detaljer, hvor denne funktion er tilgængelig, og grænserne for hver kapacitetstype og [lagertilstand](../connect-data/service-dataset-modes-understand.md):

| Lagertilstand | Dedikeret kapacitet | Delt kapacitet |
| --- | --- | --- |
| DirectQuery | **Understøttet**: Ja <br>**Minimuminterval for opdatering**: 1 sekund <br>**Tilsidesættelse af kapacitetsadministrator**: Ja | **Understøttet**: Ja <br>**Minimuminterval for opdatering**: 30 minutter <br>**Tilsidesættelse af kapacitetsadministrator**: Nej |
| Importér | **Understøttet**: Nej <br>**Minimuminterval for opdatering**: I/T <br>**Tilsidesættelse af kapacitetsadministrator**: I/T | **Understøttet**: Nej <br>**Minimuminterval for opdatering**: I/T <br>**Tilsidesættelse af kapacitetsadministrator**: I/T |
| Blandet tilstand (DirectQuery + andre datakilder) | **Understøttet**: Ja <br>**Minimuminterval for opdatering**: 1 sekund <br>**Tilsidesættelse af kapacitetsadministrator**: Ja | **Understøttet**: Ja <br>**Minimuminterval for opdatering**: 30 minutter <br>**Tilsidesættelse af kapacitetsadministrator**: Nej |
| Live connect AS | **Understøttet**: Nej <br>**Minimuminterval for opdatering**: I/T <br>**Tilsidesættelse af kapacitetsadministrator**: I/T | **Understøttet**: Nej <br>**Minimuminterval for opdatering**: I/T <br>**Tilsidesættelse af kapacitetsadministrator**: I/T |
| Live connect PBI | **Understøttet**: Nej <br>**Minimuminterval for opdatering**: I/T <br>**Tilsidesættelse af kapacitetsadministrator**: I/T | **Understøttet**: Nej <br>**Minimuminterval for opdatering**: I/T <br>**Tilsidesættelse af kapacitetsadministrator**: I/T |

> [!NOTE]
> Når du publicerer din rapport med automatisk sideopdatering aktiveret fra Power BI Desktop til tjenesten, skal du angive legitimationsoplysningerne for DirectQuery-datakilden i menuen Indstillinger for datasæt.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Der er et par ting, du skal være opmærksom på, når du bruger automatisk sideopdatering i Power BI Desktop eller Power BI-tjenesten:

* Tilstandene Import, LiveConnect og pushlagring understøttes ikke for automatisk sideopdatering.  
* Sammensatte modeller, der har mindst én DirectQuery-datakilde, understøttes.
* Power BI Desktop har ingen begrænsninger for opdateringsintervaller. Intervallet kan være så hyppigt som hvert sekund. Når rapporter publiceres i Power BI-tjenesten, kan der dog være visse begrænsninger, hvilket blev beskrevet [tidligere](#restrictions-on-refresh-intervals) i denne artikel.

### <a name="performance-diagnostics"></a>Ydeevnediagnosticering

Automatisk sideopdatering kan bruges til at overvåge scenarier og udforske hurtigt skiftende data. I nogle tilfælde kan det dog belaste kapaciteten eller datakilden unødigt.

Power BI har disse sikkerhedsforanstaltninger for at forhindre unødig belastning af datakilder:

- Alle forespørgsler om automatisk sideopdatering kører ved en lavere prioritet for at sikre, at interaktive forespørgsler (f.eks. sideindlæsning og tværgående filtrering af visuelle elementer) har fortrinsret.
- Hvis forespørgslen ikke er færdig, før den næste opdateringscyklus er udført, udsteder Power BI ikke nye opdateringsforespørgsler, før den forrige forespørgsel er fuldført. Hvis du f.eks. har et opdateringsinterval på ét sekund, og dine forespørgsler i gennemsnit tager fire sekunder, udsteder Power BI kun en forespørgsel hvert fjerde sekund.

Der er to områder, hvor du stadig kan opleve flaskehalse for ydeevnen:

1. **Kapaciteten**. Forespørgslen søger først i Premium-kapaciteten, der udvides og evaluerer den DAX-forespørgsel, der genereres fra rapportvisualiseringerne, i kildeforespørgslerne.
2. **Typen af DirectQuery-datakilde**. De oversatte forespørgsler i det forrige trin køres derefter mod kilden. Kilden er dine SQL Server-forekomster, SAP Hana-kilder osv.

Hvis du bruger [appen Premium Capacity Metrics-appen ](../admin/service-admin-premium-monitor-capacity.md), der er tilgængelig for administratorer, kan du få visualiseret, hvor meget af kapaciteten der bruges af forespørgsler med lav prioritet.

Forespørgsler med lav prioritet består af automatiske sideopdateringsforespørgsler og forespørgsler om modelopdatering. Der er i øjeblikket ingen måde at skelne mellem belastningen fra automatisk sideopdatering og forespørgsler om modelopdatering.

Hvis du bemærker, at din kapacitet er overbelastet med forespørgsler med lav prioritet, er der nogle foranstaltninger, du kan træffe:

- Anmod om en større Premium-SKU.
- Kontakt rapportejeren for at få reduceret opdateringsintervallet.
- I portalen til kapacitetsadministration kan du:
   - Slå automatisk sideopdatering for den pågældende kapacitet fra.
   - Øge minimumsintervallet for opdatering, som påvirker alle rapporter i kapaciteten.


### <a name="frequently-asked-questions"></a>Ofte stillede spørgsmål

**Jeg er rapportforfatter. Jeg har defineret opdateringsintervallet for min rapport til ét sek. i Power BI Desktop, men efter at jeg har publiceret min rapport, opdateres den ikke i tjenesten.**

* Kontrollér, at automatisk sideopdatering er slået til for siden. Da denne indstilling gælder pr. side, skal du sikre dig, at den er aktiveret for hver side i rapporten, som du vil opdatere.
* Kontrollér, om du har uploadet til et arbejdsområde med en tilknyttet Premium-kapacitet. Hvis du ikke har gjort det, er opdateringsintervallet låst fast på 30 minutter.
* Hvis din rapport er i et Premium-arbejdsområde, skal du spørge din administrator, om denne funktion er aktiveret for den vedhæftede kapacitet. Sørg desuden for, at minimumintervallet for opdatering af kapaciteten er lavere eller det samme som intervallet for din rapport.

**Jeg er kapacitetsadministrator. Jeg har ændret indstillingerne for automatisk sideopdateringsinterval, men ændringerne afspejles ikke. Med andre ord opdateres rapporter stadig ved en uønsket hastighed eller opdateres slet ikke, selvom jeg har aktiveret automatisk sideopdatering.**

* Det tager op til fem minutter, før ændringer af indstillingerne for automatisk sideopdatering, der er foretaget i administratorgrænsefladen, træder i kraft i rapporter.
* Ud over at aktivere automatisk sideopdatering for kapaciteten skal du også aktivere funktionen for de sider i en rapport, du vil have opdateret.

**Min rapport fungerer i blandet tilstand. (blandet tilstand betyder, at rapporten har en DirectQuery-forbindelse og en import datakilde). Nogle visuals opdateres ikke.**

- Hvis dine visuals refererer til importtabeller, er dette forventeligt. Automatisk sideopdatering understøttes ikke for import.
- Se det første spørgsmål i dette afsnit.

**Min rapport er indtil nu blevet opdateret fint i tjenesten, men det er pludselig holdt op.**

* Prøv at opdatere siden for at se, om problemet løser sig selv.
* Kontakt din kapacitetsadministrator. Administratoren har muligvis slået funktionen fra eller øget minimumintervallet for opdatering. Se det andet spørgsmål i dette afsnit.

**Jeg er rapportforfatter. Mine visuals opdateres ikke med den hastighed, jeg har angivet. De opdateres med en lavere hastighed.**

* Hvis dine forespørgsler tager længere tid at køre, forsinkes opdateringsintervallet. Automatisk sideopdatering venter på, at alle forespørgsler er færdige, før der køres nye.
* Kapacitetsadministratoren kan have angivet et minimumsinterval for opdateringen, der er højere end det, du har angivet for din rapport. Bed din kapacitets administrator om at reducere minimumintervallet for opdatering.

**Håndteres automatiske sideopdateringer fra cachelageret?**

* Nej. Alle cachelagrede data tilsidesættes af forespørgsler om automatisk sideopdatering.


## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger i disse artikler:

* [Brug af DirectQuery in Power BI](../connect-data/desktop-directquery-about.md)
* [Brug sammensatte modeller i Power BI Desktop](../transform-model/desktop-composite-models.md)
* [Brug Effektivitetsanalyse til at undersøge ydeevnen for rapportelementer](desktop-performance-analyzer.md)
* [Udrulning og administration af Power BI Premium-kapaciteter](../guidance/whitepaper-powerbi-premium-deployment.md)
* [Datakilder i Power BI Desktop](../connect-data/desktop-data-sources.md)
* [Udform og kombiner data i Power BI Desktop](../connect-data/desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](../connect-data/desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](../connect-data/desktop-enter-data-directly-into-desktop.md)   
