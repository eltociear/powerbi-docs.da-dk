---
title: Brug af DirectQuery i Power BI
description: Om brugen af DirectQuery med Power BI
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/05/2018
ms.author: davidi
ms.openlocfilehash: ceccf00879d3ac17f907f5dce296bb03bb0227d2
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/09/2018
---
# <a name="using-directquery-in-power-bi"></a>Brug af DirectQuery i Power BI
Du kan oprette forbindelse til alle mulige forskellige datakilder, når du bruger **Power BI Desktop** eller **Power BI-tjenesten**, og du kan oprette disse dataforbindelser på forskellige måder. Du kan enten *importere* data i Power BI, hvilket er den mest almindelige måde at hente data på, eller du kan oprette forbindelse direkte til dataene i det oprindelige kildelager, der også er kendt som **DirectQuery**. I denne artikel beskrives **DirectQuery** og dens egenskaber, herunder følgende emner:

* Forskellige forbindelsesmuligheder for DirectQuery
* Vejledning, når du overvejer at bruge DirectQuery i stedet for at importere
* Ulemper i forbindelse med brugen af DirectQuery
* Bedste praksis i forbindelse med brugen af DirectQuery

Kort sagt er bedste praksis i forbindelse med brugen af import i forhold til DirectQuery som følger:

* Du skal **importere** data i Power BI, når det er muligt. Dermed udnyttes fordelen ved forespørgselsprogrammets høje ydeevne i Power BI, og du får en yderst interaktiv oplevelse med fuld funktionalitet i forbindelse med dine data.
* Hvis du ikke kan få opfyldt dine mål vha. import af data, kan du overveje at bruge **DirectQuery**. Hvis dataene f.eks. ændres ofte, og rapporter skal afspejle de seneste data, kan DirectQuery være bedst. Brugen af DirectQuery er generelt kun praktisk, når den underliggende datakilde kan levere interaktive forespørgsler (mindre end 5 sekunder) for en typisk samlet forespørgsel og kan håndtere den forespørgselsbelastning, der genereres. Desuden skal den liste over begrænsninger, der følger med brugen af DirectQuery overvejes nøje, så du sikrer dig, at dine mål stadig kan opfyldes.

Det sæt af egenskaber, Power BI kan tilbyde i forbindelse med begge forbindelsesformer – import og DirectQuery – udvikles med tiden. Det vil indebære en øget fleksibilitet ved brug af importerede data, så importen kan bruges i flere tilfælde, samt eliminering af nogle af de ulemper, der er forbundet med at bruge DirectQuery. Uanset disse forbedringer, så vil ydeevnen for den underliggende datakilde altid være den største overvejelse ved brugen af DirectQuery. Hvis den underliggende datakilde er langsom, vil det ikke være praktisk at anvende DirectQuery for den pågældende kilde.

Dette emne dækker DirectQuery med Power BI og ikke SQL Server Analysis Services. DirectQuery er også en funktion i **SQL Server Analysis Services**, og mange af de oplysninger, der er angivet nedenfor gælder også for brugen af den. Der er dog også væsentlige forskelle. Du kan finde flere oplysninger om brugen af DirectQuery med SQL Server Analysis Services under [det whitepaper, der indeholder detaljer om DirectQuery i SQL Server Analysis Services 2016](http://download.microsoft.com/download/F/6/F/F6FBC1FC-F956-49A1-80CD-2941C3B6E417/DirectQuery%20in%20Analysis%20Services%20-%20Whitepaper.pdf).  

I denne artikel fokuseres der på det anbefalede workflow for DirectQuery, hvor rapporten oprettes i **Power BI Desktop**, men oprettelse af forbindelse direkte i **Power BI-tjenesten** dækkes også.

## <a name="power-bi-connectivity-modes"></a>Power BI-forbindelsestilstande
Power BI opretter forbindelse til et meget stort antal forskellige datakilder, der omfatter:

* Online-tjenester (Salesforce, Dynamics 365 med flere)
* Databaser (SQL Server, Access, Amazon Redshift med flere)
* Enkle filer (Excel, JSON med flere)
* Andre datakilder (Spark, websteder, Microsoft Exchange med flere)

For disse datakilder er det normalt muligt at importere data i Power BI. For nogle er det også muligt at oprette forbindelse vha. DirectQuery. Det præcise sæt kilder, der understøtter DirectQuery, er beskrevet i artiklen [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md). Der aktiveres flere kilder for DirectQuery fremover, primært med fokus på kilder, der kan forventes at levere en god interaktiv ydeevne i forbindelse med forespørgsler.

**SQL Server Analysis Services** er et særligt tilfælde. Når du opretter forbindelse til SQL Server Analysis Services, kan du vælge at importere dataene eller bruge en *liveforbindelse*.  Brugen af en liveforbindelse ligner brugen af DirectQuery, da der ikke importeres data, og den underliggende datakilde altid forespørges i forbindelse med opdateringen af en visualisering. En *liveforbindelse* er dog forskellig på mange andre punkter, og derfor bruges der et andet ord for den (*live* i forhold til *DirectQuery*).

Disse tre muligheder for oprettelse af forbindelse til data – **import**, **DirectQuery** og **liveforbindelse** – forklares mere detaljeret i de følgende sektioner.

### <a name="import-connections"></a>Importforbindelser
Når du bruger **Get Data** i **Power BI Desktop** til at oprette forbindelse til en datakilde som f.eks. SQL Server, og du vælger **Import**, er funktionsmåden for forbindelsen som følger:

* Under den indledende **Get Data**-oplevelse, definerer det valgte tabelsæt en forespørgsel, der returnerer et datasæt (disse forespørgsler kan redigeres før indlæsning af dataene, f.eks. for at anvende filtre, samle dataene eller forbinde forskellige tabeller).
* Ved indlæsning importeres alle de data, der er defineret af disse forespørgsler, i Power BI-cachen.
* Ved bygning af en visualisering i **Power BI Desktop**, sendes en forespørgsel til de importerede data. Power BI-lageret sikrer, at forespørgslen er meget hurtig, og derfor afspejles alle ændringer i visualiseringen med det samme.
* Eventuelle ændringer i de underliggende data afspejles ikke i visualiseringerne. Det er nødvendigt at *opdatere*, hvorefter dataene importeres igen.
* Ved publicering af rapporten (.pbix-filen) i **Power BI-tjenesten**, oprettes der et datasæt, som uploades til Power BI-tjenesten.  De importerede data inkluderes i det pågældende datasæt. Det er derefter muligt at konfigurere en planlagt opdatering af de pågældende data, f.eks. for at importere dataene igen hver dag. Afhængigt af placeringen af den oprindelige datakilde kan det være nødvendigt at konfigurere en datagateway i det lokale miljø.
* Når du åbner en eksisterende rapport i **Power BI-tjenesten** eller forfatter en ny rapport, sendes en ny forespørgsel til de importerede data, hvilket sikrer interaktivitet.
* Visualiseringer eller hele rapportsider kan fastgøres som dashboardfelter. Felterne opdateres automatisk, når det underliggende datasæt opdateres.  

### <a name="directquery-connections"></a>DirectQuery-forbindelser
Når du bruger **Get Data** i **Power BI Desktop** til at oprette forbindelse til en datakilde, og du vælger **DirectQuery**, er funktionsmåden for forbindelsen som følger:

* Under den indledende **Get Data**-oplevelse, vælges kilden. I forbindelse med relationskilder betyder det, at sæt af tabeller vælges, som hver især definerer en forespørgsel, der logisk returnerer et datasæt. Ved flerdimensionelle kilder som SAP BW er det kun kilden, der vælges.
* Ved indlæsning importeres der dog ingen data i Power BI-lageret. Når du bygger en visualisering i **Power BI Desktop**, sendes forespørgsler i stedet til den underliggende datakilde for at hente de nødvendige data. Den tid, det derefter tager at opdatere visualiseringen, afhænger af den underliggende datakildes ydeevne.
* Eventuelle ændringer i de underliggende data afspejles ikke i eksisterende visualiseringer med det samme. Det er stadig nødvendigt at opdatere, hvorefter de nødvendige forespørgsler sendes igen for hver enkelt visualisering, og derefter opdateres visualiseringen efter behov.
* Ved publicering af rapporten i **Power BI-tjenesten**, oprettes der igen et datasæt i Power BI-tjenesten, som det var tilfældet i forbindelse med import. Der inkluderes dog *ingen data* i det pågældende datasæt.
* Når du åbner en eksisterende rapport i **Power BI-tjenesten**, eller du opretter en ny, sendes der igen en forespørgsel til den underliggende datakilde for at hente de nødvendige data. Afhængigt af placeringen af den oprindelige datakilde kan det være nødvendigt at konfigurere en datagateway i det lokale miljø, lige som den er påkrævet i importtilstanden, hvis dataene opdateres.
* Visualiseringer eller hele rapportsider kan fastgøres som dashboardfelter. Hvis du vil sikre dig, at åbningen af et dashboard sker hurtigt, skal felterne automatisk opdateres i henhold til en tidsplan (f.eks. hver time). Opdateringsfrekvensen kan styres, så den afspejler, hvor ofte dataene ændres, og hvor vigtigt det er at få vist de allernyeste data. Derfor afspejler felterne dataene ved den seneste opdatering, når du åbner et dashboard, og ikke nødvendigvis de allernyeste ændringer, der er foretaget af den underliggende kilde. Et åbent dashboard kan altid opdateres, så du sikrer dig, at det er ajour.    

### <a name="live-connections"></a>Liveforbindelser
Når du opretter forbindelse til SSAS (**SQL Server Analysis Services**),er det muligt enten at importere data fra eller oprette liveforbindelse til den valgte datamodel. Hvis du vælger **import**, definerer du en forespørgsel i forhold til den eksterne SSAS-kilde, og dataene importeres som normalt. Hvis du vælger **connect live**, er der ikke defineret en forespørgsel, og hele den eksterne model vises på feltlisten. Hvis du vælger **DirectQuery**, sendes forespørgsler til den eksterne SSAS-kilde, efterhånden som visualiseringerne bygges. I modsætning til DirectQuery, er der dog ingen overordnet mening med, hvordan en ny *model* oprettes. Med andre ord, er det ikke muligt at definere nye beregnede kolonner, hierarkier, relationer osv. I stedet opretter du blot direkte forbindelse til den eksterne SSAS-model.

Den situation, der er beskrevet i den foregående sektion gælder også i forbindelse med oprettelse af forbindelse til følgende kilder, bortset fra at det er ikke muligt at importere dataene:

* Power BI-datasæt (når der f.eks. oprettes forbindelse til et Power BI-datasæt, der tidligere er blevet oprettet og publiceret til tjenesten, for at oprette en ny rapport for det)
* Common Data Services

Funktionsmåden for rapporter i forbindelse med SSAS ved publicering til **Power BI-tjenesten** svarer til DirectQuery-rapporter på følgende måde:

* Når du åbner en eksisterende rapport i **Power BI-tjenesten** eller opretter en ny rapport, sendes der en forespørgsel til den underliggende SSAS-kilde (som muligvis kræver en datagateway i det lokale miljø)
* Dashboardfelterne opdateres automatisk efter en tidsplan (f.eks hver time, eller hvilken frekvens, der nu er defineret)

Der er dog også vigtige forskelle, bl.a. at identiteten af den bruger, der åbner rapporten, altid sendes til den underliggende SSAS-datakilde for dynamiske forbindelser.

Nu, hvor vi har lavet disse sammenligninger, kan vi nøjes med at fokusere på **DirectQuery** i resten af denne artikel.

## <a name="when-is-directquery-useful"></a>Hvornår er DirectQuery nyttig?
I følgende tabel beskrives scenarier, hvor oprettelse af forbindelse til DirectQuery kan være særlig nyttig, herunder tilfælde, hvor det anses for at være en fordel at bevare dataene i den oprindelige kilde. I beskrivelsen diskuteres det, om det angivne scenarie er tilgængeligt i Power BI.

| Begrænsning | Beskrivelse |
| --- | --- |
| Data ændres ofte, og derfor er der behov for rapportering næsten i realtid |Modeller med importerede data kan højst opdateres én gang i timen. Hvis dataene ændres hele tiden, og det er nødvendigt for rapporter at få vist de nyeste data, kan det derfor være, at brugen af Import med planlagt opdatering ganske enkelt ikke opfylder disse behov. Bemærk, at det også er muligt at streame data direkte til Power BI, selvom der i disse tilfælde er en begrænsning på de understøttede datamængder. <br/> <br/> I modsætning hertil vil brugen af DirectQuery betyde, at der ved åbning eller opdatering af en rapport eller et dashboard altid vises de seneste data i kilden. Derudover kan dashboardfelterne opdateres oftere (helt op til hvert kvarter). |
| Datamængden er meget stor |Hvis datamængden er meget stort, vil det bestemt ikke være praktisk at importere den overhovedet. I modsætning hertil kræver DirectQuery ingen stor dataoverførsel, da der sendes en forespørgsel til dem der, hvor de ligger. <br/> <br/> Dog kan store datamængder også medføre, at ydeevnen af forespørgsler i forhold til den underliggende datakilde er for langsom (som beskrevet i sektionen *Konsekvenser ved brugen af DirectQuery* senere i denne artikel). Det er heller ikke altid nødvendigt at importere de fuldt detaljerede data. I stedet kan dataene samles på forhånd under import (og det er meget nemt vha. **Forespørgselseditor**). I helt særlige tilfælde vil det være muligt at importere præcis de samlede data, der er brug for, for hver enkelt visualisering. Så mens DirectQuery er den nemmeste måde få adgang til store datamængder på, skal du være opmærksom på, at import af samlede data ofte kan være en løsning, hvis den underliggende kilde er for langsom. |
| Sikkerhedsregler defineres i den underliggende kilde |Når dataene er importeret, opretter Power BI forbindelse til datakilden vha. legitimationsoplysningerne for de aktuelle brugere (fra Power BI Desktop) eller vha. de legitimationsoplysninger, der er defineret som en del af konfiguration af den planlagte opdatering (fra Power BI-tjenesten). Det vil sige, at det er vigtigt kun at dele en rapport med brugere, der har tilladelse til at se de samme data, når sådan en rapport publiceres og deles. Ellers skal der defineres sikkerhed på rækkeniveau som en del af datasættet. <br/> <br/> Da DirectQuery altid sender forespørgsler til den underliggende datakilde, vil dette ideelt set tillade, at den underliggende kilde anvendes. I dag vil Power BI dog altid oprette forbindelse til den underliggende kilde vha. de samme legitimationsoplysninger, som bruges til import. <br/> <br/> Indtil Power BI gør det muligt at sende identiteten af brugeren af rapporten til den underliggende kilde, er der ingen fordele i forhold til datakildens sikkerhed med DirectQuery. |
| Der kan være begrænsninger for datasuverænitet |Nogle organisationer har politikker omkring datasuverænitet, hvilket betyder, at data ikke kan forlade det lokale miljø i en organisation. En løsning, der er baseret på import, vil tydeligvis medføre problemer. I modsætning hertil, forbliver dataene i den underliggende kilde med DirectQuery. <br/> <br/> Det skal dog bemærkes, at selv med DirectQuery bevares nogle cashelagrede data på visualiseringsniveau i Power BI-tjenesten (på grund af planlagt opdatering af felter). |
| Underliggende datakilder er en OLAP-datakilde, der indeholder målinger |Hvis den underliggende datakilde indeholder *målinger* (f.eks. SAP HANA eller SAP Business Warehouse), medfører importen af dataene andre problemer. Det betyder, at de importerede data befinder sig på et bestemt niveau i samlingen som defineret af forespørgslen. Det kan f.eks. være TotalSales efter Class, Year og City. Så hvis en visualisering bygges og efterspørger data på et højere niveau i samlingen (f.eks TotalSales efter år), samles den samlede værdi yderligere. Dette fungerer fint for additive målinger (f.eks. Sum, Min.), men det er et problem for ikke-additive målinger (f.eks. Average, DistinctCount). <br/> <br/> Hvis du vil gøre det nemt at hente de korrekte samlede data (som relevant for en bestemt visualisering) direkte fra kilden, vil det være nødvendigt at sende forespørgsler pr. visualisering som i DirectQuery. <br/> <br/> Når du opretter forbindelse til SAP Business Warehouse (BW) og vælger DirectQuery, er denne behandling af målingerne mulig. Understøttelse af SAP BW behandles yderligere i [DirectQuery og SAP BW](desktop-directquery-sap-bw.md). <br/> <br/> I øjeblikket behandler DirectQuery i forhold til SAP HANA dataene på samme måde som en relationskilde, og derfor er importfunktionsmåden den samme. Dette behandles yderligere under [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md). |

Det vil altså sige, at med de aktuelle egenskaber i DirectQuery i Power BI, er der fordele med følgende scenarier:

* Data ændres ofte, og derfor er der behov for rapportering næsten i realtid
* Håndtering af meget store datamængder, uden at der er behov for at samle på forhånd
* Der kan være begrænsninger for datasuverænitet
* Kilden er en multidimensionel kilde, der indeholder målinger (f.eks. SAP BW)

Bemærk, at oplysningerne på den forrige liste kun er relateret til brugen af Power BI. Det er altid muligt at bruge en ekstern model for SQL Server Analysis Services (eller Azure Analysis Services) til at importere data og derefter bruge Power BI til at oprette forbindelse til den pågældende model. Selvom denne fremgangsmåde kræver flere kompetencer, er den mere fleksibel. Der kan f.eks. importeres meget større datamængder, og der er ingen begrænsninger for, hvor ofte dataene kan opdateres.

## <a name="implications-of-using-directquery"></a>Konsekvenser ved brugen af DirectQuery
Brug af **DirectQuery** har muligvis negative konsekvenser, som beskrevet i dette afsnit. Nogle af disse begrænsninger er lidt anderledes, afhængigt af den nøjagtige kilde der bruges. Dette påpeges, hvor det er relevant, og der vil være separate emner, der behandler de kilder, der er markant anderledes.  

### <a name="performance-and-load-on-the-underlying-source"></a>Ydeevne og arbejdsbelastning i den underliggende kilde
Når du bruger **DirectQuery**, afhænger den generelle oplevelse i høj grad af den underliggende datakildes ydeevne. Hvis det tager nogle få sekunder (<5 sek.) at opdatere hver enkelt visualisering (når du f.eks. har ændret en udsnitsværdi), vil oplevelsen være rimeligt, men den kan stadig føles langsom sammenlignet med det øjeblikkelig svar, du er vant til at få, når du importerer data i Power BI. Hvis den langsomme kilde betyder, at det tager længere tid at opdatere enkelte visualiseringer (mere end ti sekunder), bliver oplevelsen derfor meget ringe, og måske opstår der endda timeout for forespørgslerne.

Sammen med den underliggende kildes ydeevne, skal du være opmærksom på den arbejdsbelastning, den påføres (der naturligvis ofte påvirker ydeevnen). Som behandles yderligere nedenfor, sendes der mindst én forespørgsel pr. visualisering til den underliggende kilde i forbindelse med hver enkelt bruger, der åbner en delt rapport, og hvert dashboardfelt, der opdateres jævnligt. Det kræver, at kilden er i stand til at håndtere sådan en forespørgselsbelastning, samtidig med at der bevares en rimelig ydeevne.

### <a name="limited-to-a-single-source"></a>Begrænset til en enkelt kilde
Når du importerer data, er det muligt at kombinere data fra flere kilder i en enkelt model. Hvis du f.eks. nemt vil joinforbinde data fra en virksomheds SQL Server-database med lokale data, der ligger i en Excel-fil. Det er ikke muligt, når du bruger DirectQuery. Når du vælger DirectQuery for en kilde, vil det derefter kun være muligt at bruge data fra denne enkelte kilde (f.eks en enkelt SQL Server-database).

### <a name="limited-data-transformations"></a>Begrænsede datatransformationer
På samme måde er der begrænsninger i datatransformationer, der kan anvendes i **Forespørgselseditor**. Med importerede data kan der let anvendes et avanceret sæt transformationer til at rydde op i og forme dataene igen, før du bruger dem til at oprette visualiseringer (f.eks fortolkning af JSON-dokumenter eller pivotere data fra en kolonne- til en rækkeorienteret form). Disse transformationer er mere begrænset i DirectQuery. Når du opretter forbindelse til en OLAP-kilde, f.eks. SAP Business Warehouse, kan der ikke defineres transformeringer overhovedet, og hele den eksterne 'model' hentes fra kilden. For relationskilder som SQL Server er det stadig muligt at definere et sæt transformationer pr. forespørgsel, men disse transformationer er begrænset af hensyn til ydeevnen. Alle disse transformationer skal anvendes på hver enkelt forespørgsel til den underliggende kilde i stedet for én gang i forbindelse med dataopdatering. Derfor er de begrænset til de transformationer, der med rimelighed kan fortolkes til en enkelt oprindelig forespørgsel. Hvis du bruger en transformation, der er for kompleks, vil du får vist en fejl om, at den enten skal slettes, eller at modellen skal ændres til importtilstand.

Desuden anvendes den forespørgsel, der kommer fra dialogboksen **Get Data** eller **Forespørgselseditor**, i en undermarkering i de genererede forespørgsler og sendes for at hente de nødvendige data til en visualisering. Derfor skal den forespørgsel, der er defineret i Forespørgselseditor, være gyldig i denne kontekst. Det betyder, at det ikke er muligt at bruge en forespørgsel med fælles tabeludtryk, eller som starter lagrede procedurer.

### <a name="modelling-limitations"></a>Modelleringsbegrænsninger
Udtrykket *modellering* betyder i denne kontekst den måde, du kan finjustere og forbedre rådata på som en del af oprettelsen af en rapport, der anvender disse data. Det kan f.eks. være:

* Definition af relationer mellem tabeller
* Tilføjelse af nye beregninger (beregnede kolonner og målinger)
* Omdøbning og skjul af kolonner og mål
* Definition af hierarkier
* Definition af formatering, standardopsummering og sorteringsrækkefølge for en kolonne
* Gruppering eller klyngeoprettelse af værdier

Når du bruger **DirectQuery**, kan mange af disse modelforbedringer stadig foretages, og der er stadig et princip om, at rådataene kan forbedres, hvilket også forbedrer den senere brug. Der er dog nogle af modelleringsegenskaberne, der ikke er tilgængelige, eller som er begrænset, når du bruger DirectQuery. Begrænsningerne anvendes generelt for at undgå problemer med ydeevnen. Sættet af begrænsninger, der er fælles for alle DirectQuery-kilder, er angivet i følgende punktopstilling. Der kan gælde yderligere begrænsninger for enkelte kilder, som beskrevet i *Oplysninger for specifikke datakilder* i slutningen af denne artikel.

* **Intet indbygget datohierarki:** Når du importerer data, vil der som standard være et indbygget datahierarki tilgængeligt for hver enkelt dato/dato-klokkeslætskolonne. Hvis import af en tabel med salgsordrer f.eks. inkluderer en kolonne af typen OrderDate, vil det være muligt at vælge det relevante anvendelsesniveau (Year, Month, Day), når du bruger OrderDate i en visualisering. Dette indbyggede datohierarki er ikke tilgængeligt, når du bruger tilstanden DirectQuery. Bemærk dog, at hvis Datotabel er tilgængelig i den underliggende kilde (det er almindeligt i mange data warehouses), kan DAX Time Intelligence-funktionerne bruges som normalt.
* **Begrænsninger i beregnede kolonner:** Beregnede kolonner er begrænset til samme række, dvs. de kan kun referere til andre kolonner i samme tabel uden at bruge af samlingsfunktioner. Derudover er de tilladte DAX-skaleringsfunktioner (f.eks. LEFT()) desuden begrænset til dem, som ganske enkelt kan sendes til den underliggende kilde. Dermed vil de variere afhængigt af kildens specifikke egenskaber. Funktioner, der ikke understøttes, vises ikke under autofuldførelse, når DAX godkendes for en beregnet kolonne, og det vil medføre en fejl, hvis de bruges.
* **Ingen understøttelse af overordnede/underordnede DAX-funktioner:** I DirectQuery-modellen er det ikke muligt at bruge serien af DAX PATH()-funktioner, som normalt håndterer overordnet/underordnet-strukturer (f.eks. diagram over konti eller medarbejderhierarkier).
* **Begrænsninger (standard) for målinger:** Som standard er de DAX-funktioner og -udtryk, der kan bruges i målinger, begrænset. Autofuldførelse vil endnu engang begrænse de angivne funktioner, og der vil opstå en fejl, hvis der anvendes en ugyldig funktion eller et udgyldigt udtryk. Det er ganske enkelt en foranstaltning, som sikrer, at målinger som standard er begrænset til enkle målinger, hvor det er usandsynligt, at de selv forårsager problemer med ydeevnen. Erfarne brugere kan vælge at omgå denne begrænsning ved at vælge **Filer > Indstillinger**, vælge **Indstillinger > Indstillinger > DirectQuery** og derefter vælge indstillingen *Tillad ubegrænsede målinger i DirectQuery-tilstand*. Når denne indstilling er valgt, kan ethvert DAX-udtryk, der er gyldigt for en måling, anvendes. Brugerne skal dog være opmærksomme på, at nogle udtryk, der udføres korrekt, når data importeres, kan resultere i meget langsomme forespørgsler til backendkilden i DirectQuery-tilstand.
  
  * Det vil f.eks. som standard:
    
    * være muligt at oprette en måling, der ganske enkelt lægger salgsbeløbet sammen:
      
          SalesAmount = SUMX(Web_Sales, [ws_sales_price]* [ws_quantity])
    * *ikke* være muligt at oprette en måling, der derefter udregner gennemsnittet af Salgsbeløbet for alle varerne:
      
          AverageItemSalesAmount = AVERAGEX('Item', [SalesAmount])
    
    Det skyldes, at en sådan måling kan medføre en dårlig ydeevne, hvis der er et meget stort antal varer.
* **Beregnede tabeller understøttes ikke:** Mulighed for at definere en beregnet tabel vha. et DAX-udtryk understøttes ikke i DirectQuery-tilstand.
* **Relationsfiltrering er begrænset til en enkelt retning:** Når du bruger DirectQuery, er det ikke muligt at angive retningen På tværs af filtre for en relation til "Begge". I nedenstående tre tabeller vil det f.eks. ikke være muligt at oprette en visualisering, der viser hver enkelt Customer[Gender] og antallet af Product[Category], der er købt af hver enkelt. Brugen af denne type tovejsfiltrering er beskrevet [i dette detaljerede whitepaper](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional cross-filtering in Analysis Services 2016 and Power BI.docx) (rapporten præsenterer eksempler i forbindelse med SQL Server Analysis Services, men de grundlæggende pointer gælder også for Power BI).
  
  ![](media/desktop-directquery-about/directquery-about_01.png)
  
  Endnu engang er grænsen angivet på grund af konsekvenserne for ydeevnen. En særlig vigtig anvendelse af denne er, at når sikkerhed på rækkeniveau skal defineres som en del af rapporten, skal et fælles mønster have mange-til-mange-relationer mellem brugerne og de enheder, de har adgang til. Brugen af tovejsfiltrering er nødvendig for at håndhæve dette. Brugen af tovejsfiltrering for DirectQuery-modeller skal dog bruges med omtanke, og det er vigtigt at være opmærksom på eventuelle skadelige konsekvenser for ydeevnen.  
* **Ingen klyngeoprettelse:** Når du bruger DirectQuery, er det ikke muligt at bruge klyngeoprettelsesegenskaben til automatisk at finde grupper

### <a name="reporting-limitations"></a>Rapporteringsbegrænsninger
Næsten alle rapporteringsegenskaber understøttes for DirectQuery-modeller. Så længe den underliggende kilde tilbyder en passende ydeevne, kan det samme sæt visualiseringer bruges. Der er dog nogle vigtige begrænsninger i nogle af de andre egenskaber, der findes i **Power BI-tjenesten**, når en rapport publiceres, som beskrevet under følgende punkter:

* **Quick Insights understøttes ikke:** Power BI Quick Insights søger i forskellige undersæt i datasættet og anvender samtidig et sæt avancerede algoritmer for at finde indsigt, der kan være interessant. På grund af behovet for forespørgsler med meget høj ydeevne er denne funktion ikke tilgængelig for datasæt, der bruger DirectQuery.
* **Q&A understøttes ikke:** Power BI Q&A gør det muligt for dig at udforske dine data vha. intuitive egenskaber for naturligt sprog og modtage svar i form af diagrammer og grafer. Det understøttes dog ikke i øjeblikket for datasæt, der bruger DirectQuery.
* **Brug af Udforsk i Excel vil sandsynligvis resultere i dårligere ydeevne:** Det er muligt at udforske dine data vha. egenskaben "Udforsk i Excel" i forbindelse med et datasæt. Dette vil gøre det muligt at oprette pivottabeller og pivotdiagrammer i Excel. Selvom denne egenskab understøttes i forbindelse med datasæt, der bruger DirectQuery, vil ydeevnen normalt være langsommere end oprettelsen af visualiseringer i Power BI. Hvis brugen af Excel er vigtige for din scenarier, skal der derfor tages højde for det, når du beslutter dig for at bruge DirectQuery.

### <a name="security"></a>Sikkerhed
Som beskrevet tidligere i denne artikel vil en rapport, der bruger **DirectQuery**, altid anvende de samme faste legitimationsoplysninger til at oprette forbindelse til den underliggende datakilde, efter at dem er publiceret i **Power BI-tjenesten**. Bemærk, at dette gælder specifikt for DirectQuery og ikke for liveforbindelser til SQL Server Analysis Services, som er anderledes i denne forbindelse. Derfor er det nødvendigt at konfigurere legitimationsoplysningerne for den bruger, der skal arbejde med en DirectQuery-rapport, umiddelbart efter publiceringen af den. Indtil det er gjort, får du vist en fejl, når du åbner rapporten i Power BI-tjenesten.

Når legitimationsoplysningerne for brugeren er angivet, anvendes disse oplysninger, *uanset hvilken bruger, der åbner rapporten*. På denne måde er det præcis som i tilfældet med importerede data, at alle brugere vil se samme data, medmindre sikkerhed på rækkeniveau er defineret som en del af rapporten. Hvis der er defineret sikkerhedsregler i den underliggende datakilde, er det derfor vigtigt at være opmærksom i forbindelse med deling af rapporten.

### <a name="behavior-in-the-power-bi-service"></a>Funktionsmåde i Power BI-tjenesten
I dette afsnit beskrives funktionsmåden for en **DirectQuery**-rapport i **Power BI-tjenesten**. Det primære formål er, at du kan forstå den belastningsgrad, som placeres på backendkilden under hensyntagen til det antal brugere, rapporten og dashboardet deles, samt rapportens kompleksitet og, om der er defineret sikkerhed på rækkeniveau i rapporten.

#### <a name="reports--opening-interacting-with-editing"></a>Rapporter – åbning, interaktion og redigering
Når en rapport åbnes, opdateres alle visualiseringer på siden med visualiseringer, der er synlige i øjeblikket. Hver enkelt visualisering kræver normalt mindst én forespørgsel til den underliggende datakilde. Nogle visualiseringer kan kræve mere end én forespørgsel (hvis f.eks. den viste samlede værdier fra to forskellige faktatabeller eller indeholdt en mere kompleks måling eller indeholdt totaler for en ikke-additiv måling, som f.eks. Count Distinct). Hvis du flytter til en ny side, opdateres disse visualiseringer, hvilket medfører en ny række forespørgsler til den underliggende kilde.

Enhver interaktion i rapporten kan medføre, at visualiseringer opdateres. Hvis du f.eks. vælger en anden værdi i et udsnitsværktøj, kræver det, at der sendes et nyt sæt forespørgsler for at opdatere alle de berørte visualiseringer. Det samme gør sig gældende, hvis du klikker på en visualisering for at krydsfremhæve andre visualiseringer eller ændre et filter.  

På samme måde vil redigering af en ny rapport kræve, at der sendes forespørgsler for hvert enkelt trin i forbindelse med produktionen af den endelige visualisering.

Nogle af resultaterne cachelagres, og derfor vil opdateringen af en visualisering afspejles øjeblikkeligt, hvis de præcis samme resultater er blevet hentet for nylig. Disse cachelagre deles ikke med alle brugere, hvis der er defineret sikkerhed på rækkeniveau som en del af rapporten.

#### <a name="dashboard-refresh"></a>Dashboardopdatering
Individuelle visualiseringer eller hele sider kan fastgøres til dashboardet som felter. Felter, der er baseret på **DirectQuery**-datasæt, opdateres derefter automatisk i overensstemmelse med en tidsplan. Det medfører, at forespørgsler sendes til backenddatakilden. Som standard sker dette hver time, men det kan konfigureres som en del af datasætindstillingerne til at forekomme med intervaller på mellem 15. minutter og ugentligt.

Hvis der ikke er defineret sikkerhed på rækkeniveau, betyder det, at hvert enkelt felt opdateres én gang, og resultaterne deles med alle brugere. Hvis sikkerhed på rækkeniveau er defineret, kan der være en stor multiplikatoreffekt – hvert enkelt felt kræver, at der sendes separate forespørgsler pr. bruger til den underliggende kilde.  

Et dashboard med ti felter, der deles med 100 brugere, og som er oprettet på en datasæt vha. **DirectQuery** med sikkerhed på rækkeniveau, og som er konfigureret til at blive opdateret hvert 15. minut, vil medføre, at der sendes mindst 1.000 forespørgsler til backendkilden hvert 15. minut.

Derfor er det vigtigt at være opmærksom på brugen af sikkerhed på rækkeniveau og konfigurationen af tidsplanen for opdatering.

#### <a name="timeouts"></a>Timeouts
Der anvendes en timeout på fire minutter på de enkelte forespørgsler i **Power BI-tjenesten**, og forespørgsler, der tager længere tid, vil ganske enkelt mislykkes. Som det tidligere blev understreget, anbefales det, at DirectQuery bruges til kilder, der giver en nærmest interaktiv forespørgselsydeevne. Derfor er denne grænse beregnet til at forhindre problemer med alt for lange kørselstider.

### <a name="other-implications"></a>Andre konsekvenser
Nogle af de øvrige generelle konsekvenser af brugen af **DirectQuery** er som følger:

* **Hvis dataene ændres, er det nødvendigt at opdatere for at sikre, at de nyeste data vises:** På grund af brugen af cachelagrene, er der ingen garanti for, at visualiseringen altid viser de nyeste data. En visualisering kan f.eks. vise transaktionerne for den seneste dag. Hvis et udsnitsværktøj ændres, kan visualiseringen blive opdateret, så den viser transaktionerne for de seneste to dage, herunder nogle nye transaktioner, der lige er modtaget. Hvis udsnitsværktøjet returneres til den oprindelige værdi, vil visualiseringen igen vise den cachelagrede værdi, der tidligere blev hentet, og som ikke inkluderer den nye transaktion, der lige er blevet modtaget.
  
  Hvis du vælger at opdatere, ryddes alle cachelagre, og alle de visualiseringerne på siden viser de nyeste data.
* **Hvis dataene ændres, er der ingen garanti for konsekvens mellem visualiseringerne:** Forskellige visualiseringer, uanset om de er på samme eller forskellige sider, kan opdateres på forskellige tidspunkter. Hvis dataene i den underliggende kilde ændres, er der derfor ingen garanti for, at hver enkelt visualisering viser dataene på præcist samme tidspunkt. Selvom der nogle gange kræves mere end én forespørgsel for en enkelt visualisering (for f.eks. at få vist både detaljer og totaler), kan konsekvensen inden for en enkelt visualisering ikke altid garanteres. Hvis det skal kunne garanteres, kræver det, at alle visualiseringer opdateres, uanset hvornår en vilkårlig visualisering opdateres, samtidigt med, at der anvendes dyre funktioner, såsom Snapshot Isolation, på den underliggende datakilde.
  
  Dette problem kan i høj udstrækning afhjælpes ved, at du vælger at opdatere igen, da alle visualiseringer på en side dermed opdateres. Og det skal bemærkes, at selvom du er i importtilstand, er der et lignende problem med sikring af konsekvens, hvis der importeres data fra mere end én tabel.
* **Opdatering i Power BI Desktop er nødvendig for at afspejle ændringer i metadata:** Når en rapport er publiceret, vil en opdatering ganske enkelt opdatere visualiseringerne i rapporten. Hvis skemaet for den underliggende datakilde er ændret, er disse ændringer ikke automatisk anvendt for at ændre de tilgængelige felter på feltlisten. Hvis tabeller eller kolonner er blevet fjernet fra den underliggende kilde, kan det derfor medføre, at der opstår fejl i forbindelse med forespørgslen ved opdatering. Hvis du åbner rapporten i Power BI Desktop og vælger Opdater, opdateres felterne i modellen, så de afspejler ændringerne.
* **Grænsen på en million rækker blev returneret for alle forespørgsler:** Der er en fast grænse på 1 mio. rækker for det antal rækker, der kan returneres i en enkelt forespørgsel til den underliggende kilde. Dette har normalt ingen konsekvenser i praksis, og visualiseringerne viser ikke så mange punkter. Dog kan grænsen opstå i tilfælde, hvor Power BI ikke er fuldt optimeret til de sendte forespørgsler, og der er nogle mellemliggende forespørgselsresultater, som overskrider denne grænse. Det kan også forekomme, når du opretter en visualisering, inden den bliver endelig. Hvis Kunde og SamletSalgsmængde inkluderes, rammes grænsen f.eks., hvis der er mere end 1 mio. kunder, indtil der anvendes et filter.
  
  Den fejl, der returneres, vil være "Resultatsættet for en forespørgsel til en ekstern datakilde overskrider den maksimalt tilladte størrelse på '1.000.000' rækker."
* **Der kan ikke ændres fra tilstanden Import til DirectQuery:** Bemærk, at selvom det generelt er muligt at skifte tilstand for en model fra DirectQuery til Import, betyder det, at alle nødvendige data skal importeres. Det er heller ikke muligt at skifte tilbage (primært fordi sættet af funktioner ikke understøttes i tilstanden DirectQuery). DirectQuery-modeller i forhold til flerdimensionelle kilder kan, som det er tilfældet med SAP BW, heller ikke ændres fra DirectQuery til Import på grund af den helt anderledes behandling af eksterne målinger.

## <a name="directquery-in-the-power-bi-service"></a>DirectQuery i Power BI-tjenesten
Alle datakilder understøttes via **Power BI Desktop**. Nogle kilder er også tilgængelige direkte fra **Power BI-tjenesten**. Det er f.eks. muligt for erhvervsbrugere at anvende Power BI til at oprette forbindelse til deres Salesforce-data og straks få et dashboard – uden brug af **Power BI Desktop**.

Det er kun to af de kilder, der er aktiveret via DirectQuery, der er tilgængelige direkte i tjenesten:

* Spark
* Azure SQL Data Warehouse

Det anbefales på det kraftigste, at enhver brug af **DirectQuery** i forhold til disse to datakilder startes i **Power BI Desktop**. Årsagen er, at når forbindelsen oprettes for første gang i **Power BI-tjenesten**, vil der være mange nøglebegrænsninger. Det beryder, at mens det er let at starte op (start i Power BI-tjenesten), er der begrænsninger i forbindelse med yderligere forbedring af resultatrapporten. Det er f.eks. ikke muligt derefter at oprette beregninger, anvende mange analysefunktioner eller endda opdatere metadataene, så de afspejler eventuelle ændringer i det underliggende skema.   

## <a name="guidance-for-using-directquery-successfully"></a>Vejledning i korrekt brug af DirectQuery
Hvis du vil bruge **DirectQuery**, kan du i denne sektion finde råd til, hvordan du sikrer succes på højt niveau. Vejledningen i denne sektion er baseret på konsekvenserne af brugen af DirectQuery, som beskrevet i denne artikel.

### <a name="backend-data-source-performance"></a>Ydeevne for backenddatakilde
Det anbefales på det kraftigste at validere, at simple visualiseringer kan opdateres inden for et rimeligt tidsrum. Det skal være inden for 5 sekunder for at sikre en rimelig interaktiv oplevelse. Hvis det tager mere end 30 sekunder at opdatere visualiseringer, er det meget sandsynligt, at der vil opstå flere problemer i forbindelse med publiceringen af rapporten, hvilket gør, at løsningen ikke fungerer.

Hvis forespørgslerne er langsomme, skal du først undersøge de forespørgsler, der sendes til den underliggende kilde, og kontrollere årsagen til deres ydeevne. Dette emne dækker ikke de mange forskellige gode fremgangsmåder til databaseoptimering på tværs af det fulde sæt af potentielle underliggende datakilder. Det dækker dog de standardfremgangsmåder, der gælder i de fleste situationer i forbindelse med databaser:

* Relationer, der er baseret på heltalskolonner, har normalt en bedre ydeevne end joinforbindelser til kolonner med andre datatyper
* Der skal oprettes de relevante indekser, hvilket normalt betyder brugen af kolonnelagerindekser i de understøttende datakilder (f.eks. SQL Server).
* Alle nødvendige statistikker i kilden skal opdateres

### <a name="model-design-guidance"></a>Vejledning i modeldesign
Når du definerer modellen, skal du overveje at gøre følgende:

* **Undgå komplekse forespørgsler i Forespørgselseditor.** Den forespørgsel, der er defineret i Forespørgselseditor, skal oversættes til en enkelt SQL-forespørgsel, som derefter inkluderes i undermarkeringen af hver enkelt forespørgsel, der sendes til den pågældende tabel. Hvis denne forespørgsel er kompleks, kan det medføre problemer med ydeevnen for hver enkelt forespørgsel, der sendes. Du kan få den faktiske SQL-forespørgsel for et sæt trin ved at vælge det sidste trin i Forespørgselseditor og vælge *Vis oprindelig forespørgsel* i genvejsmenuen.
* **Sørg for, at målinger er enkle.** Det anbefales at begrænse målinger til enkle samlinger, i det mindste til at begynde. Hvis de viser sig at være tilfredsstillende, kan der derefter defineres mere komplekse målinger. Det er dog vigtigt at være opmærksom på ydeevnen for hver enkelt.
* **Undgå relationer for beregnede kolonner.** Det er især relevant for databaser, hvor det er nødvendigt at udføre joinforbindelser med flere kolonner. På nuværende tidspunkt tillades relationer, der er baseret på flere kolonner, ikke i Power BI som FK/PK. Den almindelige midlertidige løsning er at sammenkæde kolonnerne vha. en beregnet kolonne og basere joinforbindelsen på den. Selvom denne midlertidige løsning er rimelig i forbindelse med importerede data, vil den i forbindelse med **DirectQuery** resultere i en joinforbindelse for et udtryk, der almindeligvis forhindrer brugen af indekser og dermed føre til en dårlig ydeevne. Den eneste midlertidige løsning er faktisk at materialisere flere kolonner til én enkelt kolonne i den underliggende database.
* **Undgå relationer for kolonner med datatypen uniqueidentifier.** Power BI understøtter ikke datatypen uniqueidentifier oprindeligt. Derfor vil definitionen af en relation mellem kolonner af datatypen uniqueidentifier resultere i en forespørgsel med en joinforbindelse, der omfatter en Cast. Det medfører sædvanligvis også en dårlig ydeevne. Indtil denne fremgangsmåde optimeres specifikt, er den eneste midlertidige løsning at materialisere kolonner af en anden type i den underliggende database.
* **Skjul kolonnen *til* i forbindelse med i relationer.** Kolonnen *til* i forbindelse med relationer (ofte den primære nøgle for tabellen *til*) skal være skjult, så den ikke vises på feltlisten, og derfor ikke kan bruges i visualiseringer. De kolonner, som relationer er baseret på, er faktisk ofte *systemkolonner* (f.eks. erstatningsnøgler i et datawarehouse), og det er i forvejen en god idé at skjule denne type kolonner. Hvis kolonnen har betydning, kan du introducere en beregnet kolonne, der er synlig, og som har et enkelt udtryk, der svarer til den primære nøgle. Eksempel:
  
      ProductKey_PK   (Destination of a relationship, hidden)
      ProductKey (= [ProductKey_PK],   visible)
      ProductName
      ...
  
  Årsagen til dette er ganske enkelt at undgå problemer med ydeevnen, der kan opstå, hvis en visualisering indeholder kolonnen med den primære nøgle.
* **Undersøg al brug af beregnede kolonner og ændringer af datatyper.** Brugen af disse egenskaber er ikke nødvendigvis skadelig. De medfører, at forespørgsler, der sendes til den underliggende datakilde, indeholder udtryk i stedet for enkle referencer til kolonner, hvilket igen kan resultere i, at indekser ikke bruges.  
* **Undgå brug af (eksempelvisning) tovejstværfiltrering af relationer.**
* **Eksperimentér med indstillingen *Antag referentiel integritet*.** Indstillingen *Antag referentiel integritet* på relationer aktiverer forespørgsler til at anvende INNER JOIN-sætninger i stedet for OUTER JOIN. Dette forbedrer ydeevnen for forespørgsler generelt, selvom det er afhængigt af specifikationerne for datakilden.
* **Brug ikke relativ datofiltrering i Forespørgselseditor.** Det er muligt at angive relativ datofiltrering i Forespørgselseditor. Du kan f.eks. filtrere på de rækker, hvor datoen er inden for de seneste 14 dage.
  
  ![](media/desktop-directquery-about/directquery-about_02.png)
  
  Dette oversættes dog til et filter, der er baseret på den faste dato, som er det tidspunkt, hvor forespørgslen blev skrevet. Dette kan ses i den oprindelige forespørgsel.
  
  ![](media/desktop-directquery-about/directquery-about_03.png)
  
  Det er højst sandsynligvis ikke, det der var ønsket. Hvis du vil sikre dig, at filteret anvendes på baggrund af datoen, når rapporten køres, skal du i stedet anvende filteret i rapporten som et Rapportfilter. I øjeblikket gør du det ved at oprette en beregnet kolonne, der beregner antallet af dage, der er gået siden (ved hjælp af funktionen DAX DATE()), og derefter bruger denne beregnede kolonne i et filter.

### <a name="report-design-guidance"></a>Vejledning i rapportdesign
Når du opretter en rapport vha. en DirectQuery-forbindelse, skal den være i overensstemmelse med følgende retningslinjer:

* **Overvej at bruge indstillinger til Reduktion af forespørgsel:** Med Power BI får du indstillinger i rapporten til at sende færre forespørgsler og til at deaktivere visse interaktioner, der ellers ville resultere i en dårlig oplevelse, hvis de deraf følgende forespørgsler tager lang tid at udføre. Du får adgang til disse indstillinger i **Power BI Desktop** ved at gå til **Fil > Indstillinger > Indstillinger** og vælge **Reduktion af forespørgsel**. 

   ![](media/desktop-directquery-about/directquery-about_03b.png)

    Ved at markere afkrydsningsfelter under **Reduktion af forespørgsel** kan du deaktivere krydsfremhævning på tværs af hele rapporten. Du kan også få vist en knap af typen *Anvend* for udsnitsværktøjer og/eller filtermarkeringer, hvilket giver dig mulighed for at foretage mange valg med udsnitsværktøjer og filtre. Det resulterer i, at der ikke sendes nogen forespørgsler, før du klikker på knappen **Anvend** på udsnitsværktøjet. Dine valg bruges derefter til at filtrere dataene.

    Disse indstillinger anvendes på din rapport, mens du interagerer med den i **Power BI Desktop**, og når brugerne gør brug af rapporten i **Power BI-tjenesten**.

* **Anvend filtre først:** Du skal altid anvende de relevante filtre når du begynder at oprette en visualisering. I stedet for f.eks. at trække TotalSalgsmængde Produktnavn ind skal du filtrere efter et bestemt år og anvende filteret på År helt fra starten af. Dette skyldes, at hvert enkelt trin i oprettelsen af en visualisering sender en forespørgsel, og selvom det er muligt derefter at foretage en anden ændring, før den første forespørgsel er fuldført, så giver det stadig en unødvendig belastning på den underliggende kilde. Når du anvender filtre tidligt, reducerer det generelt omkostningerne ved disse mellemliggende forespørgsler. Hvis du ikke anvender filtre tidligt, kan det også resultere i, at du rammer grænsen på 1 mio. rækker, som angivet ovenfor.
* **Begræns antallet af visualiseringer på en side:** Når en side er åbnet (eller et udsnitsværktøj på sideniveau eller et filter er ændret), opdateres alle visualiseringerne på en side. Der er også en grænse for antallet af forespørgsler, der sendes parallelt. Derfor opdateres nogle visualiseringer i rækkefølge, når antallet af visualiseringer øges, hvilket medfører, at den tid, det tager at opdatere hele siden, øges tilsvarende. Derfor anbefales det at begrænse antallet af visualiseringer på en enkelt side og i stedet have flere enkle sider.
* **Overvej at slå interaktion mellem visualiseringer fra:** Som standard kan visualiseringer på en rapportside bruges til tværgående filtrering og tværgående fremhævning af de andre visualiseringer på siden. Hvis "1999" f.eks. er valgt i cirkeldiagrammet, er søjlediagrammet fremhævet på tværs for at vise salget efter kategori for "1999".                                                                  
  
  ![](media/desktop-directquery-about/directquery-about_04.png)
  
  I DirectQuery kræver en sådan krydsfiltrering og -fremhævning, at der sendes forespørgsler til den underliggende kilde. Derfor bør interaktionen være slået fra, hvis det vil tage urimeligt lang tid at svare på brugernes valg. Denne interaktion kan dog slås fra enten for hele rapporten (som beskrevet ovenfor ifm. *indstillinger for Reduktion af forespørgsel*) eller på ad hoc-basis (som beskrevet [i denne artikel](service-reports-visual-interactions.md)).

Ud over ovenstående liste over forslag skal du bemærke, at hver af følgende rapporteringsegenskaber kan medføre problemer med ydeevnen:

* **Målingsfiltre:** Visualiseringer, der indeholder målinger (eller samlinger af kolonner), kan indeholde filtre i disse målinger. Nedenstående visualisering viser f.eks. Salgsmængde efter kategori, men inkluderer kun kategorier med et salg på mere end 20 mio.
  
  ![](media/desktop-directquery-about/directquery-about_05.png)
  
  Dette medfører, at der sendes to forespørgsler til den underliggende kilde:
  
  * Den første forespørgsel henter kategorier, der opfylder betingelsen (salg > 20 mio.)
  * Den anden forespørgsel henter derefter de nødvendige data til visualiseringen, herunder de kategorier, der opfylder betingelsen i WHJERE-delsætningen.  
  
  Denne proces fungerer som regel fint, hvis der er hundreder eller tusinder af kategorier som i dette eksempel. Ydeevnen kan forringes, hvis antallet af kategorier er meget større (og pga. den tidligere beskrevne grænse på 1 mio. rækker, vil processen helt sikkert mislykkes, hvis der er mere end en million kategorier, der opfylder betingelsen).
* **TopN-filtre:** Avancerede filtre kan defineres, så de kun filtrerer de øverste (eller nederste) N-værdier, der er placeret efter en given måling, så de f.eks. kun inkluderer de øverste 10 kategorier som i ovenstående visualisering. Dette medfører igen, at der sendes to forespørgsler til den underliggende kilde. Dog returnerer den første forespørgsel alle kategorier fra den underliggende kilde, og derefter bestemmes TopN på baggrund af de returnerede resultater. Afhængigt af kardinaliteten for den involverede kolonne kan det medføre problemer med ydeevnen (eller forespørgselsfejl pga. grænsen på 1 mio. rækker).
* **Median:** Normalt sendes evt. samlinger (Sum, Count Distinct osv.) til den underliggende kilde. Det gælder dog ikke for medianen, da denne samling generelt ikke understøttes af den underliggende kilde. I så fald hentes detaljerede data fra den underliggende kilde, og medianen beregnes ud fra de returnerede resultater. Dette er rimeligt, når medianen skal beregnes i forhold til et lille antal resultater, men der vil opstå problemer med ydeevnen (eller forespørgselsfejl på grund af grænsen på 1 mio. rækker), hvis kardinaliteten er stor.  Medianen Landebefolkning er muligvis rimelig, men medianen Salgspris er muligvis ikke.
* **Avancerede tekstfiltre ("indeholder"' og lignende):** Når du filterer på en tekstkolonne, tillades filtre som "indeholder" og "begynder med" osv. i forbindelse med avanceret filtrering. Disse filtre kan medføre forringet ydeevne for nogle datakilder. Standardfilteret "indeholder" skal især ikke bruges, hvis det, der reelt ønskes er et præcist match ("er" eller "er ikke"). Selvom resultaterne kan være de samme, afhængigt af de faktiske data, kan ydeevnen være markant anderledes på grund af brugen af indekser.
* **Udsnitsværktøjer til flere markeringer:** Som standard tillader udsnitsværktøjer kun, at der foretages én enkelt markering. Tilladelse af flere markeringer i filtre kan medføre problemer med ydeevnen, da brugeren vælger et sæt elementer i udsnitsværktøjet (f.eks. de ti produkter, vedkommende er interesseret i). Derefter vil hver enkelt ny markering medføre, at der sendes forespørgsler til backendkilden. Selvom brugeren kan markere det næste element, før forespørgslen er udført, resulterer det i en ekstra belastning af den underliggende kilde.

* **Overvej at slå totaler fra i visualiseringer:** Som standard vises totaler og subtotaler i tabeller og matrixer. I mange tilfælde skal der sendes separate forespørgsler til den underliggende kilde for at hente værdierne for sådanne totaler. Dette gælder, når *DistinctCount*-samling bruges eller i alle tilfælde, når DirectQuery via SAP BW eller SAP HANA bruges. Sådanne totaler bør slås fra (ved hjælp af ruden **Format**), hvis de ikke er påkrævet. 

### <a name="diagnosing-performance-issues"></a>Diagnosticering af problemer med ydeevnen
I denne sektion beskrives det, hvordan problemer med ydeevnen diagnosticeres, og hvordan du kan få mere detaljerede oplysninger om, hvordan rapporterne kan optimeres.

Det anbefales på det kraftigste, at enhver diagnosticering af problemerne med ydeevnen starter i **Power BI Desktop** og ikke i **Power BI-tjenesten**. Ofte er problemer med ydeevnen ganske enkelt baseret på niveauet for ydeevnen i den underliggende kilde, og de er nemmere at identificere og diagnosticere i det meget mere isolerede miljø i **Power BI Desktop**. Dermed udelukkes visse komponenter fra starten af (f.eks. Power BI-gatewayen). Det er kun, hvis problemerne med ydeevnen ikke er relateret til Power BI Desktop, at undersøgelsen skal fokusere på de specifikke data i rapporten i Power BI-tjenesten.

På samme måde anbefales det, at du først forsøger at isolere eventuelle problemer til en enkelt visualisering i stedet for mange visualiseringer på en side.

Lad os sige, at disse trin (fra forrige afsnit i denne sektion) er gennemgået – vi har nu en enkelt visualisering på en side i **Power BI Desktop**, der stadig er langsom. Hvis du vil se de forespørgsler, der sendes til den underliggende datakilde fra Power BI Desktop, kan du få vist oplysninger om sporing/diagnosticering, som kan udledes af den pågældende kilde. Sådanne sporinger kan også indeholde nyttige oplysninger om, hvordan forespørgslen blev udført, og hvordan den kan forbedres.

Selv om sådanne sporinger fra kilden ikke bliver fundet, er det dog muligt at få vist de forespørgsler, der er sendt af Power BI, sammen med deres kørselstider, som beskrevet nedenfor.

#### <a name="determining-the-queries-sent-by-power-bi-desktop"></a>Fastlæggelse af forespørgsler, der er sendt af Power BI Desktop
Som standard logger **Power BI Desktop** hændelser i løbet af en given session til en sporingsfil kaldet FlightRecorderCurrent.trc.

For nogle **DirectQuery**-kilder inkluderer denne log alle forespørgsler, der er sendt til den underliggende datakilde (de resterende DirectQuery-kilder inkluderes i fremtiden). Følgende kilder sender forespørgsler til loggen:

* SQL Server
* Azure SQL Database
* Azure SQL Data Warehouse
* Oracle
* Teradata
* SAP HANA

Sporingsfilen findes i mappen **AppData** for den aktuelle bruger:

    \<User>\AppData\Local\Microsoft\Power BI Desktop\AnalysisServicesWorkspaces

Her er en nem måde at finde denne mappe på: I **Power BI Desktop** skal du vælge **Filer > Indstillinger > Indstillinger** og derefter vælge **Diagnosticering**. Følgende vindue vises:

![](media/desktop-directquery-about/directquery-about_06.png)

Når du vælger linket *Åbn sporingsmappe* under **Diagnosticeringsindstillinger**, åbnes følgende mappe:

    \<User>\AppData\Local\Microsoft\Power BI Desktop\Traces

Når du går til den overordnede mappe for denne mappe, vises mappen, der indeholder *AnalysisServicesWorkspaces*, som indeholder én arbejdsområdeundermappe for hver åben instans af **Power BI Desktop**. Disse undermapper er navngivet med et heltalssuffiks, f.eks. *AnalysisServicesWorkspace2058279583*.

I mappen er der en undermappe af typen *\Data*, som indeholder sporingsfilen FlightRecorderCurrent.trc for den aktuelle Power BI-session. Den tilsvarende arbejdsområdemappe slettes, når den tilknyttede Power BI Desktop-session afsluttes.

Sporingsfilerne kan læses ved hjælp af værktøjet **SQL Server Profiler**, der kan downloades gratis som en del af **SQL Server Management Studio**. Du kan hente det på [denne placering](https://msdn.microsoft.com/library/mt238290.aspx).

Når du downloader og installerer **SQL Server Management Studio**, skal du køre **SQL Server Profiler**.

![](media/desktop-directquery-about/directquery-about_07.png)

Hvis du vil åbne sporingsfilen, skal du benytte følgende fremgangsmåde:

1. I **SQL Server Profiler** skal du vælge **Filer > Åbn > Sporingsfil**
2. Angiv stien til sporingsfilen for den åbne Power BI-session, f.eks.:
   
         C:\Users\<user>\AppData\Local\Microsoft\Power BI Desktop\AnalysisServicesWorkspaces\AnalysisServicesWorkspace2058279583\Data
3. Åbn FilghtRecorderCurrent.trc

Alle hændelser fra den aktuelle session vises. Der vises et anmærket eksempel nedenfor, hvor grupper af hændelser er fremhævet. Hver enkelt gruppe har følgende:

* En hændelse af typen *Query Begin* og *Query End*, der repræsenterer start og slutning af en DAX-forespørgsel, som genereres af brugergrænsefladen (f.eks. fra en visualisering eller fra udfyldningen af en liste over værdier i brugergrænsefladen for filteret)
* Et eller flere par af hændelserne *DirectQuery Begin* og *DirectQuery End*, der repræsenterer en forespørgsel, som er sendt til den underliggende datakilde som en del af evalueringen af DAX-forespørgslen.

Bemærk, at flere DAX-forespørgsler kan udføres parallelt, så hændelser fra forskellige grupper kan indskydes. Værdien af aktivitets-id'et kan bruges til at afgøre, hvilke hændelser der tilhører samme gruppe.

![](media/desktop-directquery-about/directquery-about_08.png)

Følgende kolonner er også interessante:

* **TextData:** Tekstdetaljerne for hændelsen. For hændelser af typen "Query Begin/End" vil det være DAX-forespørgslen. For hændelser af typen "DirectQuery Begin/End" vil det være den SQL-forespørgsel, der er sendt til den underliggende kilde. TextData for den hændelse, der er valgt i øjeblikket, vises også i området nederst.
* **EndTime:** Når hændelsen er fuldført.
* **Duration:** Varigheden i millisekunder for det tidsrum, det har taget at udføre DAX- eller SQL-forespørgslen.
* **Error:** Angiver, om der opstod en fejl (i så fald vises hændelsen også med rødt).

Bemærk, at i billedet ovenfor er nogle af de mindre interessante kolonner smallere, hvilket gør de muligt at se de interessante kolonner mere tydeligt.

Vi anbefaler følgende metode til registrering af en sporing for at hjælpe med at diagnosticere et muligt problem med ydeevnen:

* Åbn en enkelt **Power BI Desktop**-session (for at undgå forvirring med flere arbejdsområdemapper)
* Udfør et sæt interessante handlinger i **Power BI Desktop**. Inkluder derudover nogle få ekstra handlinger for at sikre dig, at de interessante hændelser inkluderes i sporingsfilen.
* Åbn **SQL Server Profiler**, og undersøg sporingen, som beskrevet tidligere. Husk, at sporingsfilen slettes ved lukning af **Power BI Desktop**. Desuden vises yderligere handlinger i Power BI Desktop ikke med det samme – sporingsfilen skal lukkes og åbnes igen, for at du kan se de nye hændelser.
* Bevar individuelle sessioner, der er rimeligt små (ti-sekunders handlinger – ikke hundredvis), for at gøre det nemmere at fortolke sporingsfilen (da der er en grænse for størrelsen på sporingsfilen, er der en risiko for at tidlige hændelser fjernes for meget lange sessioner).

#### <a name="understanding-the-form-of-query-sent-by-power-bi-desktop"></a>Om formen af forespørgsler, der sendes af Power BI Desktop
Det generelle format for forespørgsler, der oprettes og sendes af **Power BI Desktop** bruger undermarkeringer for hver af de tabeller, der henvises til. Undermarkeringen er defineret af den forespørgsel, der er defineret i **Forespørgselseditor**. Antag f.eks. følgende TPC DS-tabeller i SQL Server:

![](media/desktop-directquery-about/directquery-about_09.png)

Overvej følgende forespørgsel:

![](media/desktop-directquery-about/directquery-about_10.png)

Denne forespørgsel resulterer i følgende visualisering:

![](media/desktop-directquery-about/directquery-about_11.png)

Opdatering af denne visualisering vil resultere i den SQL-forespørgsel, der er vist under næste afsnit. Som du kan se, er der tre undermarkeringer for Web Sales, Item og Date_dim, som hver især returnerer alle kolonnerne i tabellen, selvom der faktisk kun henvises til fire kolonner i visualiseringen. Disse forespørgsler i undermarkeringen (de er nedtonet) er lige præcis resultatet af de forespørgsler, der er defineret i **Forespørgselseditor**. Brug af undermarkeringer på denne måde ser ikke ud til at have en konsekvens for ydeevnen i forbindelse med de datakilder, der indtil videre understøttes for DirectQuery. Datakilder i stil med SQL Server fjerner ganske enkelt henvisningerne til de øvrige kolonner.

En af grundene til, at Power BI anvender dette mønster, er, at den anvendte SQL-forespørgsel kan angives direkte af analytikeren og bruges "som den er", uden at den behøver at blive omskrevet.

![](media/desktop-directquery-about/directquery-about_12.png)

## <a name="next-steps"></a>Næste trin
I denne artikel beskrives aspekter af **DirectQuery**, der er fælles på tværs af alle datakilder. Der er visse oplysninger, der er specifikke for enkelte kilder. Se under følgende emner for at få hjælp til specifikke kilder:

* [DirectQuery og SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery og SAP BW](desktop-directquery-sap-bw.md)

Du kan finde flere oplysninger om **DirectQuery** i følgende ressourcer:

* [Datakilder, der understøttes af DirectQuery](desktop-directquery-data-sources.md)

