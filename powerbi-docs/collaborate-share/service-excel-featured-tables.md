---
title: Få adgang til Power BI-tabeller i Excel (prøveversion)
description: I Excel kan du finde data fra udvalgte tabeller i Power BI-datasæt i datatypegalleriet.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d8ef72f25509fe41c983e7385095fdad5985f5de
ms.sourcegitcommit: 5e5a7e15cdd55f71b0806016ff91256a398704c1
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/22/2020
ms.locfileid: "83793543"
---
# <a name="access-power-bi-featured-tables-in-excel-preview"></a>Få adgang til Power BI-tabeller i Excel (prøveversion)

I Excel kan du finde data fra udvalgte tabeller i Power BI-datasæt i datatypegalleriet. De fremhævede tabeller gør det nemmere at føje virksomhedsdata til dine Excel-ark. Ved at bruge Power BI-certificerede og -promoverede datasæt kan organisationer gøre det muligt for flere brugere at finde og bruge relevante og opdaterbare data, så du kan træffe bedre beslutninger. Læs mere om, hvordan du bruger [Excel-datatyper fra Power BI](https://support.office.com/article/use-excel-data-types-from-power-bi-preview-cd8938ce-f963-444d-b82a-7140848241e9) i dokumentationen til Excel.

Datatypegalleriet viser kun de fremhævede tabeller, som en model har overvåget i Power BI-datasæt. Du kan også gennemse et vilkårligt datasæt i Excel, som du kan få adgang til i Power BI. Vælg indstillingen **Power BI-datasæt** i Excel under **Hent data** på båndet **Data**.

## <a name="access-power-bi-data-through-the-excel-data-types-gallery"></a>Få adgang til Power BI-data via Excel-datatypegalleriet
Udvalgte tabeller i Power BI-datasæt vises i Excel-datatypegalleriet på båndet Data.

:::image type="content" source="media/service-excel-featured-tables/excel-data-ribbon.png" alt-text="Excel-data-bånd":::

Når galleriet er udvidet, vises de mest tilgængelige datatyper.

:::image type="content" source="media/service-excel-featured-tables/excel-data-types-gallery.png" alt-text="Excel-datatypegalleri":::
 
Hvis du vil slå data op i en Power BI-tabel, skal du vælge en celle eller et område i Excel-arket.

:::image type="content" source="media/service-excel-featured-tables/excel-select-cell.png" alt-text="Vælg en celle":::
 
Vælg indstillingen **Organisationsdata** i galleriet for at søge efter data i udvalgte tabeller i certificerede datasæt, som du har adgang til.

:::image type="content" source="media/service-excel-featured-tables/excel-organizational-data.png" alt-text="Excel-organisationsdata":::
 
Vælg en bestemt datatype, hvis du ved, hvilken type data du søger efter, eller hvis du ikke kan finde tilsvarende rækker ved hjælp af indstillingen Organisationsdata.

:::image type="content" source="media/service-excel-featured-tables/excel-select-data-type.png" alt-text="Vælg en datatype":::
 
Hvis der findes en tilsvarende række med høj sikkerhed, når du søger, kædes cellen straks sammen med den pågældende række. Ikonet for det sammenkædede element angiver, at cellen er sammenkædet med rækken i Power BI.

:::image type="content" source="media/service-excel-featured-tables/excel-linked-item-icon.png" alt-text="Ikon for tilknyttet element":::

Hvis en celle har flere mulige tilsvarende rækker, vises ruden Datavælger. Cellen viser ikonet med spørgsmålstegnet, der åbner datavælgerruden for denne række. Her er et eksempel, hvor brugeren har valgt et område fra A2:A7 og søgt i en Power BI-funktionstabel.

:::image type="content" source="media/service-excel-featured-tables/excel-multiple-matches.png" alt-text="Flere mulige matchende rækker":::

De potentielt matchede rækker vises i ruden **Datavælger**.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-pane.png" alt-text="Ruden Excel-datavælger":::
 
Indstillingen Organisationsdata kan returnere rækker fra flere forskellige datatyper. Excel grupperer de potentielt matchende rækker efter den datatype, de kom fra. Excel sorter datatyperne baseret på deres mest tilsvarende række. Brug vinkelpilene til at skjule og udvide datatyperne, så de matcher rækkerne.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-multiple.png" alt-text="Ruden Excel-datavælger":::
 
For hver række skal du vælge rækkenavnet for at få vist flere detaljer i rækken, så du kan få hjælp til at vælge den rigtige række. Når du har fundet en række, skal du trykke på **Vælg** for at knytte rækken til cellen i Excel. 

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-select.png" alt-text="Oplysninger om datavælger":::
 
Når en række er markeret, knyttes cellen til rækken og dens værdi til værdien for feltet **Rækkeetiket** i Power BI-tabellen. 

:::image type="content" source="media/service-excel-featured-tables/excel-linked-item-icon.png" alt-text="Excel-tilknyttet element":::
 
Når du vælger ikonet **Sammenkædet celle** vises der et kort med data fra eventuelle felter og beregnede felter i den udvalgte tabel. Kortets titel viser værdien af feltet rækkeetiket i den valgte tabel.
 
:::image type="content" source="media/service-excel-featured-tables/excel-linked-item-details.png" alt-text="Oplysninger om tilknyttet element":::

Vælg ikonet **Indsæt data** for at føje feltværdier til gitteret.

:::image type="content" source="media/service-excel-featured-tables/excel-insert-data.png" alt-text="Indsæt data"::: 

Vælg et feltnavn på listen over felter for at føje værdien til gitteret.  

:::image type="content" source="media/service-excel-featured-tables/excel-select-field.png" alt-text="Vælg et feltnavn":::

Feltværdien placeres i den tilstødende celle. Celleformlen refererer til den sammenkædede celle og feltnavnet, så du kan bruge dataene i Excel-funktioner.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-formula.png" alt-text="Excel-celleformel":::
 
Når du formaterer dine data som en Excel-tabel, udvides tabellen når du tilføjer felter, og kolonneoverskriften indstilles til at matche feltnavnet. Rækker, der er knyttet til de samme datatyper, udfyldes også med deres respektive værdier.

:::image type="content" source="media/service-excel-featured-tables/excel-field-column-name.png" alt-text="Feltet er kolonnenavnet"::: 

## <a name="cell-formulas"></a>Celleformler

Når du bruger en Excel-tabel, kan du referere til kolonnen med sammenkædede tabeller og derefter tilføje datafelter ved hjælp af referencen `.` (periode).

:::image type="content" source="media/service-excel-featured-tables/excel-dot-reference.png" alt-text="Excel-periodereference":::

Når du bruger en celle, kan du også referere til cellen og bruge referencen `.` (periode) til at hente felter.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-dot-reference.png" alt-text="Celleperiodereference":::
 
## <a name="data-caching-and-refresh"></a>Data-cachelagring og -opdatering

Når Excel knytter en celle til en række i en Power BI-tabel, hentes og gemmes alle feltværdierne i Excel-filen. Alle, som du deler filen med, kan referere til et af felterne uden at anmode om data fra Power BI.  

Brug knappen **Opdater alle** på båndet **Data** for at opdatere data i sammenkædede celler. 

:::image type="content" source="media/service-excel-featured-tables/excel-refresh-all.png" alt-text="Opdater alt":::
 
Du kan også opdatere enkelte celler. Højreklik på cellen, og vælg **Datatyper** > **Opdater**.

## <a name="show-a-card-change-or-convert-to-text"></a>Vis et kort, skift eller konverter til tekst

Sammenkædede celler har tilføjede indstillinger til genvejsmenuen. Højreklik på en celle > Vælg **Datatype** >  

- **Vis kort**
- **Opdatering**
- **Skift** 
- **Konvertér til tekst**.

:::image type="content" source="media/service-excel-featured-tables/excel-right-click-data-type.png" alt-text="Højreklik, Konvertér til tekst":::
 
**Konvertér til tekst** fjerner linket til rækken i Power BI-tabellen. Det er vigtigt, at teksten i cellen er værdien for rækkeetiketten i den sammenkædede celle. Hvis du har knyttet en celle til en række, du ikke har tænkt dig at vælge, kan du vælge **Fortryd** i Excel for at gendanne de oprindelige celleværdier.

## <a name="licensing"></a>Licensering
Excel-datatypegalleriet og de forbundne oplevelser til Power BI-tabeller er kun tilgængelige for Excel E5- og G5-kunder. 

## <a name="security"></a>Sikkerhed

Du kan kun se udvalgte tabeller fra datasæt, som du har tilladelse til, i Power BI. Når du opdaterer data, skal du have adgangstilladelse til datasættet i Power BI for at hente rækkerne. Dette kræver tilladelsen Build eller Skriv på datasættet. Excel cachelagrer de data, der returneres for hele rækken. Alle, du deler Excel-filen med, kan se dataene for alle felterne i alle de sammenkædede celler.

Hvis et Power BI-datasæt har sikkerhed på rækkeniveau, eller hvis der er anvendt et navn på en Microsoft Information Protection-følsomhedsetiket, medtages de fremhævede tabeller fra det pågældende datasæt ikke i Excel-datatypegalleriet. Dette er en begrænsning af den oprindelige prøveversion.

## <a name="curate-a-featured-table-in-power-bi-desktop"></a>Organiser en udvalgt tabel i Power BI Desktop
Excel-datatypegalleriet viser udvalgte tabeller i datasæt, der er uploadet til Power BI-tjenesten. Brug Power BI Desktop til at overvåge udvalgte tabeller i datamodellen, og overfør dem derefter til Power BI-tjenesten.

### <a name="turn-on-the-featured-table-preview"></a>Slå eksempelvisning af udvalgte tabeller til

1. Vælg **Filer** > **Indstillinger** > **Indstillinger** > **Funktioner til eksempelvisning** i Power BI Desktop.
2. Markér afkrydsningsfeltet **Fremhævede tabeller**.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-preview-featured-tables.png" alt-text="Indstillingen Vis fremhævede tabeller":::

### <a name="select-a-table"></a>Vælg en tabel

1. Gå til Modelvisning i Power BI Desktop.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-model-view.png" alt-text="Modelvisning":::
 
2. Vælg en tabel, og sæt **Er en fremhævet tabel** til **Ja**.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-featured-table-yes.png" alt-text="Sæt Er en fremhævet tabel til Ja":::

4. I **Konfigurer denne tabel** skal du udfylde de påkrævede felter:

    - En **beskrivelse**.
    - Feltværdien **Rækkeetiket** bruges i Excel, så brugerne nemt kan identificere rækken. Den vises som celleværdien for en sammenkædet celle i ruden **Datavælger** og på kortet **Oplysninger**. 
    - Feltværdien **Nøglekolonne** indeholder det entydige id for rækken. Denne værdi gør det muligt for Excel at sammenkæde en celle med en bestemt række i tabellen.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-set-up-featured-table.png" alt-text="Opsæt fremhævet tabel":::

Når du udgiver eller importerer datasættet til Power BI-tjenesten, vises den fremhævede tabel i Excel-datatypegalleriet.

- Excel cachelagrer listen over datatyper, så du skal genstarte Excel for at se nyligt udgivede, fremhævede tabeller.
- Nogle datasæt understøttes ikke i prøveversionen. De fremhævede tabeller, der er defineret i disse datasæt, vises ikke i Excel. Se overvejelser og begrænsninger for at få flere oplysninger.

## <a name="administrative-control"></a>Administrativ kontrol

Power BI-administratorer kan styre, hvem i organisationen der kan bruge udvalgte tabeller i Excel-datatypegalleriet. Du kan finde flere oplysninger i [Udvalgte tabelindstillinger](../admin/service-admin-portal.md#featured-tables-settings) i artiklen på administrationsportalen. 
 
### <a name="auditing"></a>Overvågning

Overvågningslogge til administration viser disse hændelser for udvalgte tabeller:

- **AnalyzedByExternalApplication**: Giver administratorer overblik over, hvilke brugere der anvender hvilke udvalgte tabeller.
- **UpdateFeaturedTables**: Giver administratorer overblik over, hvilke brugere der udgiver og opdaterer udvalgte tabeller.

Du kan finde en komplet liste over hændelser i overvågningsloggen under [Sporing af brugeraktiviteter i Power BI](../admin/service-admin-auditing.md).

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Her er begrænsningerne for den oprindelige prøveversion:

- Integrationen er tilgængelig i Excel Insiders Builds.
- Excel-datatypegalleriet indeholder udvalgte tabeller til brugere med den relevante licens i Power BI Desktop og Power BI-tjenesten. Understøttelse af Power BI-tjenesten er muligvis ikke tilgængelig ved lanceringen af prøveversionen, men vil blive tilføjet.
- Udvalgte tabeller i Power BI-datasæt, der bruger følgende funktioner, vises ikke i Excel: 

    - Sikkerhedsdatasæt på rækkeniveau.
    - Microsoft Information Protection-aktiverede datasæt.
    - DirectQuery-datasæt.
    - Datasæt med en direkte forbindelse.

- Der vises kun data i kolonner og beregnede kolonner i den udvalgte tabel i Excel. Følgende er ikke angivet i den oprindelige prøveversion:

    - De målinger, der er defineret i funktionstabellen.
    - De målinger, der defineres for relaterede tabeller, og implicitte målinger beregnet ud fra relationer.

- Excel viser kun udvalgte tabeller, der er gemt i de nye Power BI-arbejdsområder. Udvalgte tabeller, der er gemt i de klassiske arbejdsområder eller Mit arbejdsområde, vises ikke som datatyper i Excel. Du kan [opgradere klassiske arbejdsområder til de nye arbejdsområder](service-upgrade-workspaces.md) i Power BI.

Datatyperne i Excel svarer til en opslagsfunktion. Det kræver en celleværdi, der er angivet i Excel-arket, og der søges efter tilsvarende rækker i udvalgte Power BI-tabeller. Søgeoplevelsen har følgende funktionsmåder:

- Når du bruger knappen **Organisationsdata** til at søge, søger Excel kun i udvalgte tabeller i certificerede datasæt.
- Rækkematchning er baseret på tekstkolonner i den udvalgte tabel. Den bruger den samme indeksering som Power BI Q&A-funktionen, som er optimeret til engelsksprogede søgninger. Søgning på andre sprog resulterer muligvis ikke i præcise matches. Der søges ikke efter matches i numeriske kolonner.
- Matchning er baseret på præcise og præfiksbaserede matches til individuelle søgeord. En celles værdi opdeles på baggrund af mellemrum eller andre mellemrumstegn, f.eks. faner. Derefter betragtes hvert ord som et søgeord. Værdier i en rækkes tekstfelt sammenlignes med hvert søgeord for at finde nøjagtige og præfiksbaserede forekomster. Der returneres en præfiksforekomst, hvis rækkens tekstfelt starter med søgeordet. Hvis en celle f.eks. indeholder "Orange County", så er "Orange" og "County" separate søgetermer. 

    - Rækker med tekstkolonner, hvis værdi svarer nøjagtigt til "Orange" eller "County", returneres. 
    - Rækker med tekstkolonner, hvis værdi starter med "Orange" eller "County", returneres. 
    - Det er vigtigt, at de rækker, der indeholder "Orange" eller "County", men ikke starter med dem, ikke returneres.

- Power BI returnerer maksimalt 100 rækkeforslag for hver celle.
- Indstilling eller opdatering af den udvalgte tabel understøttes ikke i XMLA-slutpunktet
- Excel-filer med en datamodel kan bruges til at publicere udvalgte tabeller. Indlæs dataene i Power BI Desktop, og udgiv derefter den udvalgte tabel.
- Ved ændring af tabelnavn, rækkeetiket eller nøglekolonne kan den udvalgte tabel påvirke Excel-brugere med sammenkædede celler til rækker i tabellen. 
- Excel viser, hvornår dataene blev hentet fra Power BI-datasættet. Det er ikke nødvendigvis det tidspunkt, hvor dataene blev opdateret i Power BI, eller tidspunktet for det seneste datapunkt i et datasæt. Antag f.eks., at et datasæt i Power BI blev opdateret for en uge siden, men de underliggende kildedata var en uge gammel, da opdateringen fandt sted. De faktiske data ville være to uger gamle, men Excel viser data, der hentes, som den dato og det klokkeslæt, hvor dataene blev indlæst i Excel.

## <a name="next-steps"></a>Næste trin

- Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

