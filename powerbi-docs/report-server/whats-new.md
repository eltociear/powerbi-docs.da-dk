---
title: Nyheder i Power BI-rapportserver
description: Læs om nyheder i Power BI-rapportserver. Dette dækker de primære funktionsområder og opdateres i takt med, at der frigives nye elementer.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/22/2019
ms.openlocfilehash: ad3025b9649529566972f75e9c447bb7558132b8
ms.sourcegitcommit: 91ac6185f7026ddbaa925dc54057bb742b4fa411
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2019
ms.locfileid: "56325191"
---
# <a name="whats-new-in-power-bi-report-server"></a>Nyheder i Power BI-rapportserver

Læs om nyheder i Power BI-rapportserver. I denne artikel beskrives de primære funktionsområder, og den opdateres, når der udgives nye elementer.

Du kan downloade de nyeste versioner af Power BI-rapportserver og Power BI Desktop, der er optimeret til Power BI-rapportserver, ved at gå til [Rapportering i det lokale miljø med Power BI-rapportserver](https://powerbi.microsoft.com/report-server/).

Du kan finde relaterede oplysninger om nyheder i Power BI under:

* [Nyheder i Power BI-tjenesten](../service-whats-new.md)
* [Nyheder i Power BI Desktop](../desktop-latest-update.md)
* [Nyheder i mobilappsene til Power BI](../consumer/mobile/mobile-whats-new-in-the-mobile-apps.md)

## <a name="january-2019"></a>Januar 2019

Understøttelse af disse funktioner i Power BI-rapporter:

[**Sikkerhed på rækkeniveau**](row-level-security-report-server.md) Konfiguration af sikkerhed på rækkeniveau med Power BI-rapportserver kan begrænse adgang til datakilder for bestemte brugere. Filtre begrænser adgangen til data på rækkeniveau, og du kan definere filtre inden for roller.

[**Udvid og skjul i matrixrækkeoverskrifter**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#expandCollapse) Vi har tilføjet muligheden for at udvide eller skjule enkelte rækkeoverskrifter, hvilket er en af de visuelle funktioner, der har været mest efterspurgt.

[**Kopiér og indsæt mellem .pbix-filer**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#copyPaste) Du kan kopiere visuelle elementer mellem .pbix-filer enten fra genvejsmenuen for det visuelle element eller med standardtastaturgenvejen Ctrl + C og indsætte dem i en anden rapport med Ctrl + V.

[**Smarte justeringshjælpelinjer**](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#smartGuides) De smarte justeringshjælpelinjer vises, når du flytter objekter på rapportsiden, f.eks. som i PowerPoint, så du kan justere alt på siden. Du kan se de smarte justeringshjælpelinjer, hver gang du trækker eller ændrer størrelsen på noget på siden. Når du flytter et objekt i nærheden af et andet, fastgøres det i en position, der er justeret i forhold til det andet objekt.

**Tilgængelighedsfunktioner** Der er for mange tilgængelighedsfunktioner til at vise dem allesammen: f.eks. [understøttelse af tilgængelighed til ruden med listen over felter](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#fieldList). Ruden med listen over felter er fuldt tilgængelig. Du kan navigere rundt i ruden ved blot at bruge tastaturet og en skærmlæser, og du kan bruge genvejsmenuen til at føje felter til din rapportside.

### <a name="administrator-settings"></a>Administratorindstillinger

Administratorer kan angive følgende egenskaber for serverfarmen under Avancerede egenskaber i SSMS:

**AllowedResourceExtensionsForUpload** Et sæt udvidelser til ressourcer, der kan uploades til rapportserveren. Udvidelser til indbyggede filtyper som &ast;.rdl og &ast;.pbix behøver ikke at være inkluderet. Standarden er "&ast;, &ast;.xml, &ast;.xsd, &ast;.xsl, &ast;.png, &ast;.gif, &ast;.jpg, &ast;.tif, &ast;.jpeg, &ast;.tiff, &ast;.bmp, &ast;.pdf, &ast;.svg, &ast;.rtf, &ast;.txt, &ast;.doc, &ast;.docx, &ast;.pps, &ast;.ppt, &ast;.pptx ". 

**SupportedHyperlinkSchemes** Angiver en kommasepareret liste over de URI-skemaer, der kan defineres i de linkhandlinger, der har tilladelse til at blive gengivet, eller "&ast;" for at aktivere alle linkskemaer. Indstillingen "http, https" tillader f.eks. link til "https://www. contoso.com", men ville fjerne link til "mailto:bill@contoso.com" eller "javascript:window.open(‘www.contoso.com’, ‘_blank’)". Standarden er "&ast;".

## <a name="august-2018"></a>August 2018

I august 2018 kommer der mange nye funktioner i Power BI Desktop, som er optimeret til Power BI-rapportserver. Her er de nye funktioner efter område:

- [Rapportering](#reporting)
- [Analyse](#analytics)
- [Modellering](#modeling)

### <a name="highlights-of-the-august-2018-release"></a>Højdepunkter i august 2018-versionen

Blandt de mange nye funktioner er følgende funktioner særligt interessante. Du kan finde flere oplysninger i dette [blogindlæg](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/).

#### <a name="report-theming"></a>Rapporttemaer

I august 2018-versionen af Power BI-rapportserver har vi tilføjet rapporttemaer, så du hurtigt kan anvende farver i hele din rapport, så den matcher et tema eller virksomhedens branding. Når du importerer et tema, bliver alle dine diagrammer automatisk opdateret til at bruge temafarverne, og du har adgang til temafarverne i farvepaletten. Du kan uploade en temafil ved hjælp af indstillingen **Importér tema** under knappen **Skift tema**.

En temafil er en JSON-fil, der indeholder alle de farver, du vil bruge i din rapport, sammen med en standardformatering, du vil anvende på visualiseringer.
Her er et eksempel på et JSON-tema, der kun opdaterer standardfarverne i rapporten:

```json
{
"name": "waveform",
"dataColors": [ "#31B6FD", "#4584D3", "#5BD078", "#A5D028", "#F5C040", "#05E0DB", "#3153FD", "#4C45D3", "#5BD0B0", "#54D028", "#D0F540", "#057BE0" ],
"background":"#FFFFFF",
"foreground": "#F2F2F2",
"tableAccent":"#5BD078"
}
```

#### <a name="conditional-formatting-by-a-different-field"></a>Betinget formatering af et andet felt

Muligheden for at formatere en kolonne efter et andet felt i modellen er en af de betydelige forbedringer af betinget formatering.

#### <a name="conditional-formatting-by-values"></a>Betinget formatering efter værdier

En anden ny type betinget formatering er **Formatér efter feltværdi**. Med Formatér efter feltværdi kan du bruge et mål eller en kolonne, der specificerer en farve, enten ved at angive en heksadecimal kode eller et navn for at anvende farven som baggrundsfarve eller skriftfarve.

#### <a name="report-page-tooltips"></a>Værktøjstip for rapportside

Funktionen med værktøjstip på rapportsiden er inkluderet i august 2018-opdateringen af Power BI-rapportserver. Med denne funktion kan du designe en rapportside, der skal bruges som et brugerdefineret værktøjstip til andre visualiseringer i din rapport.

#### <a name="log-axis-improvements"></a>Forbedringer af logaritmisk akse

Vi har forbedret den logaritmiske akse i dine kartesiske diagrammer væsentligt. Det er nu muligt at vælge en logaritmisk skala for den numeriske akse i et kartesisk diagram, herunder kombinationsdiagrammer, når du har data, som er udelukkende positive eller udelukkende negative.

#### <a name="sap-hana-sso-direct-query"></a>SAP HANA SSO Direct Query

SAP HANA SSO Direct Query understøttes nu med Kerberos for Power BI-rapporter.

>[!Note]
>Dette scenarie understøttes kun, når SAP HANA behandles som en relationel datakilde med rapporter, du har oprettet i Power BI Desktop.  Hvis du vil aktivere dette i Power BI Desktop, skal du gå til DirectQuery-menuen under Indstillinger, markere "Behandl SAP HANA som en relationel kilde" og klikke på OK.

#### <a name="custom-visuals"></a>Brugerdefinerede visuelle elementer

- Med denne version leveres API version 1.13.0.

- Nu kan brugerdefinerede visualiseringer falde tilbage på en tidligere version, der er kompatibel med den aktuelle version af server-API'et (hvis tilgængeligt).

### <a name="reporting"></a>Rapportering 

- [Rapporttemaer](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#theming)
- [Knapper til at udløse handlinger](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#buttons)
- [Stregtyper i kombinationsdiagram](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLines)
- [Forbedret standardsortering af visualiseringer](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sort)
- [Numerisk udsnit](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#numericSlicer)
- [Synkronisering af avancerede udsnit](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerSync)
- [Forbedringer af logaritmisk akse](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#logAxis)
- [Indstillinger for datanavne for tragtformet diagram](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#funnelChart)
- [Angiv stregbredden til nul](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#lineStroke)
- [Understøttelse af stor kontrast i rapporter](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#highContrast)
- [Kontrolelementet kranseradius](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#donutRadius)
- [Kontrolelement med navne på placering af cirkel- og kransediagram](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#detailLabels)
- [Formatér datanavne separat for hver måling i et kombinationsdiagram](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLabels)
- [Ny visuel overskrift med større fleksibilitet og flere formateringsmuligheder](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#visualHeader)
- [Formatering af baggrund](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#wallpaper)
- [Værktøjstip til tabel og matrix](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tableTooltips)
- [Slå værktøjstip fra for visualiseringer](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tooltips)
- [Tilgængelighed for udsnit](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerAccessibility)
- [Forbedringer til fanen Formatering](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#formattingPane)
- [Understøttelse af trinvise linjer i kurve- og kombinationsdiagrammer](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#steppedLine)
- [Bedre sorteringsfunktioner](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sorting)
- [Udskriv rapporter via Eksportér til PDF (i Power BI Desktop)](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#print)
- [Opret bogmærkegrupper](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#bookmarks)
- [Tilpasning af udsnit](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicer)
- [Værktøjstip for rapportside](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#reportPageTooltips)

### <a name="analytics"></a>Analyse

- [Ny DAX-funktion: COMBINEVALUES()](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#combineValues)
- [Mål detaljeadgang](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#measureDrillthrough)
- [Betinget formatering af et andet felt](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingField)
- [Betinget formatering efter værdier](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingValue)

### <a name="modeling"></a>Modellering

- [Filtrering og sortering i datavisning](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#filterAndSort)
- [Forbedret formatering af landestandarder](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#locale)
- [Datakategorier til målinger](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dataCategory)
- [Statistiske DAX-funktioner](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dax)

## <a name="may-2018"></a>Maj 2018

### <a name="configure-power-bi-ios-mobile-apps-for-report-servers-remotely"></a>Konfigurer Power BI iOS-mobilapps eksternt for rapportservere

Som it-administrator kan du bruge din organisations MDM-værktøj til eksternt at konfigurere adgang til en rapportserver for Power BI iOS-mobilapps. Se [Konfigurer Power BI iOS-mobilapps eksternt for rapportservere](configure-powerbi-mobile-apps-remote.md) for at få flere oplysninger.

## <a name="march-2018"></a>Marts 2018

Den nye version af Power BI Desktop optimeret til Power BI-rapportserver fra marts 2018 indeholder en lang række nye funktioner. Her er de nye funktioner efter område:

- [Visualisering](#visuals-updates)
- [Rapportering](#reporting)
- [Analyse](#analytics)
- [Ydeevne](#performance)
- [Rapportserver](#report-server)
- [Andet](#other-improvements)

### <a name="highlights-of-the-march-2018-release"></a>Højdepunkter i marts 2018-versionen

Blandt de mange nye funktioner er følgende funktioner særligt interessante.

#### <a name="rule-based-conditional-formatting-for-table-and-matrixhttpspowerbimicrosoftcomblogpower-bi-desktop-november-2017-feature-summaryconditionalformatting"></a>[Regelbaseret betinget formatering til tabel og matrix](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)

Opret regler baseret på betingelser. Du kan f.eks. farvelægge baggrunden eller vælge skrifttypefarven for en kolonne baseret på tabellens eller matrixens specifikke forretningslogik.

#### <a name="show-and-hide-pageshttpspowerbimicrosoftcomblogpower-bi-desktop-january-2018-feature-summaryhidepages"></a>[Vis og skjul sider](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

Du ønsker at give læserne adgang til din rapport, men nogle af siderne er ikke helt færdige. Nu kan du skjule dem, til de er færdige. Du kan også skjule sider i den normale navigation og give læsere adgang til en side ved hjælp af bogmærker eller detaljeadgang.

#### <a name="bookmarkinghttpspowerbimicrosoftcomblogpower-bi-desktop-march-2018-feature-summarybookmarking"></a>[Bogmærker](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

Opret bogmærker, som fortæller om dataene i din rapport.

- [Tværgående fremhævning til bogmærker](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): Bogmærker bevarer og viser rapportsidens tværgående fremhævninger på det tidspunkt, bogmærket blev oprettet.
- [Større fleksibilitet med bogmærker](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): Bogmærker afspejler de egenskaber, du angiver i din rapport, og påvirker udelukkende de visualiseringer, du vælger.

#### <a name="multi-select-data-points-across-multiple-chartshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarycrosshighlight"></a>[Markér flere datapunkter på tværs af diagrammer](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

Markér flere datapunkter i flere diagrammer, og anvend krydsfiltrering på hele siden.

#### <a name="sync-slicers-across-multiple-pages-of-your-reporthttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarysyncslicers"></a>[Synkroniser udsnitsværktøjer på tværs af flere sider i en rapport](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

Et udsnitsværktøj kan anvendes på én, to eller flere sider i en rapport.

#### <a name="quick-measureshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summaryquickmeasures"></a>[Hurtigmålinger](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

Opret nye målinger baseret på eksisterende målinger og numeriske kolonner i en tabel.

#### <a name="drilling-down-filters-other-visualshttpspowerbimicrosoftcomblogpower-bi-desktop-december-feature-summarydrillfiltersothervisuals"></a>[Detaljeudledning filtrerer andre visualiseringer](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

Når du foretager detaljeudledning i en bestemt kategori i en visualisering, kan du vælge at filtrere alle visualiseringerne på siden efter den pågældende kategori.

### <a name="visuals-updates"></a>Opdateringer til visualiseringer

- [Cellejustering for tabel og matrix](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [Vis enheder og præcisionskontrolelementer for kolonnerne Tabel og Matrix](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [Overløb af datanavne i søjlediagrammer i visualiseringer](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [Styre baggrundsfarve for datanavn i kartesiske og visuelle elementer med kort](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [Kontrolelement til udfyldning af værktøjslinje/kolonne](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [Forøge område, der bruges til akseetiketter i diagrammer](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [Punktvisualiseringer på baggrund af x- og y-aksegrupperinger](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [Stikprøvetagning med høj tæthed for kort, baseret på breddegrad og længdegrad](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [Dynamiske udsnitsværktøjer](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [Føj en ankerdato til et relativt datoudsnit](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>Rapportering

- [Slå overskriften i visualiseringer fra i Læsetilstand for en rapport](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [Rapportindstillinger til langsomme datakilder](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [Forbedret standardplacering af visualiseringer](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [Kontrollér arrangering af visualiseringer i valgruden](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [Lås objekter i din rapport](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [Søgning i ruderne Formatering og Analyse](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [Ruden Feltegenskaber og feltbeskrivelser](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>Analyse

- [UTCNOW() og UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [Markér brugerdefineret datotabel](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [Detaljeudledning filtrerer andre visualiseringer](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [Formatering på celleniveau for flerdimensionelle AS-modeller til kort med flere rækker](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)

### <a name="performance"></a>Ydeevne

- [Forbedring af ydeevnen ved filtrering](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [Forbedring af ydeevnen for DirectQuery](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [Forbedring af ydeevnen ved åbn og gem](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [Forbedring af "Vis elementer uden data"](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)

### <a name="report-server"></a>Rapportserver

#### <a name="export-to-accessible-pdf"></a>Eksport til tilgængelig PDF

Når du eksporterer en sideinddelt rapport (RDL) til PDF, kan du nu eksportere til en tilgængelig/tagget PDF-fil. Filen fylder mere, men skærmlæsere og andre hjælpemidler har nemmere ved at læse og navigere i den. Tilgængelig PDF aktiveres ved at angive indstillingen **AccessiblePDF** under enhedsoplysninger til **Sand**. Se [PDF-indstillinger for enhedsoplysninger](https://docs.microsoft.com/sql/reporting-services/pdf-device-information-settings) og [Ændring af indstillinger for enhedsoplysninger](https://docs.microsoft.com/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings).

### <a name="other-improvements"></a>Andre forbedringer

- [Forbedret Tilføj kolonne fra eksempler](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [Hurtiglink til rådgivningstjenester](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [Forbedret fejlrapportering](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [Visning af tidligere fejl, du har oplevet](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

## <a name="october-2017"></a>Oktober 2017

### <a name="power-bi-report-data-sources"></a>Power BI-rapportdatakilder

Power BI-rapporter i Power BI-rapportserver kan oprette forbindelse til en række forskellige datakilder. Du kan importere data og planlægge dataopdateringer, eller du kan forespørge på dem direkte ved hjælp af DirectQuery eller en liveforbindelse til SQL Server Analysis Services. Se listen over datakilder, der understøtter planlagt opdatering, og dem, der understøtter DirectQuery, i "Power BI-rapportdatakilder i Power BI-rapportserver".

### <a name="scheduled-data-refresh-for-imported-data"></a>Planlagt dataopdatering for importerede data

I Power BI-rapportserver kan du konfigurere planlagt opdatering af data for at sikre, at dataene er opdateret i Power BI-rapporter ved hjælp af en integreret model i stedet for en liveforbindelse eller DirectQuery. Med en integreret model importerer du dataene, så forbindelsen til den oprindelige datakilde afbrydes. Den skal opdateres for at holde dataene friske, og planlagt opdatering er måden at gøre det på. Læs mere om planlagt opdatering til Power BI-rapporter i Power BI-rapportserver.

### <a name="editing-power-bi-reports-from-the-server"></a>Redigering af Power BI-rapporter fra serveren

Du kan åbne og redigere Power BI-rapportfiler (.pbix) fra serveren, men du får den oprindelige fil tilbage, du har uploadet.  Det betyder, at **hvis dataene er blevet opdateret af serveren, opdateres dataene ikke, når du åbner filen første gang**. Du skal opdatere manuelt lokalt for at se ændringen.

### <a name="large-file-uploaddownload"></a>Upload/download af store filer

Du kan uploade filer på op til 2 GB, men som standard er denne grænse indstillet til 1 GB i indstillingerne for rapportserver i SQL Server Management Studio (SSMS).  Disse filer gemmes, som de er, i databasen til SharePoint, og der kræves ingen særlig konfiguration for SQL Server-kataloget.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Få adgang til delte datasæt såsom OData-feeds

Du kan få adgang til delte datasæt fra Power BI Desktop med et OData-feed. Du kan få mere at vide i [Få adgang til delte datasæt såsom OData-feeds på Power BI-rapportserver](access-dataset-odata.md).

### <a name="scale-out"></a>Scale-out

Denne udgave understøtter scale-out. Brug en belastningsjustering, og angiv servertilknytning for at få den bedste oplevelse. Bemærk, at scenariet endnu ikke er optimeret til scale-out, så du får vist modeller, som kan være replikeret på tværs af flere noder. Scenariet fungerer uden Network Load Balancer og sticky sessions. Du vil dog ikke kun se et overforbrug af hukommelse på tværs af noder, fordi modellen indlæses N gange, men ydeevnen sænkes mellem forbindelserne, da modellen streames, når den rammer en ny node mellem anmodningerne.  

### <a name="administrator-settings"></a>Administratorindstillinger

Administratorer kan angive følgende egenskaber for serverfarmen under Avancerede egenskaber i SSMS:

* EnableCustomVisuals: Sand/falsk
* EnablePowerBIReportEmbeddedModels: Sand/falsk
* EnablePowerBIReportExportData: Sand/falsk
* MaxFileSizeMb: Standarden er nu 1000
* ModelCleanupCycleMinutes: Hvor ofte der kontrolleres for at fjerne modeller fra hukommelsen
* ModelExpirationMinutes: Hvor lang tid, før en model er udløbet og fjernes, baseret på sidste gang den blev brugt
* ScheduleRefreshTimeoutMinutes: Hvor længe dataopdateringen kan vare for en tilstand. Som standard er dette to timer.  Der er ingen fastsat øvre grænse.

**Konfigurationsfil rsreportserver.config**

```xml
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>Udvikler-API

Udvikler-API'en (REST-API), der blev introduceret i SSRS 2017, er blevet udvidet til Power BI-rapportserver for at fungere sammen med både Excel-filer og .pbix-filer. En potentiel use case er programmeringsmæssigt at downloade filer fra serveren, opdatere dem og publicere dem igen. Dette er eksempelvis den eneste måde, hvorpå du kan opdatere Excel-projektmapper med PowerPivot-modeller.

Bemærk, at der er en ny separat API til store filer, som vil blive opdateret i Power BI-rapportserverversionen af Swagger. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>Hukommelsesfodaftryk for SQL Server Analysis Services (SSAS) og Power BI-rapportserver

Power BI-rapportserver hoster nu SQL Server Analysis Services (SSAS) internt. Dette er ikke specifikt for planlagt opdatering. At hoste SSAS kan markant udvide hukommelsesfodaftrykket for rapportserveren. AS.ini-konfigurationsfilen findes på servernoderne, så hvis du kender SSAS, kan du opdatere indstillingerne, herunder største hukommelsesgrænse og cachelagring på disk osv. Se [Serveregenskaber i Analysis Services](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services), for at få mere at vide.

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Få vist og interager med Excel-projektmapper

Excel og Power BI indeholder en portefølje af værktøjer, som er de eneste af deres slags i branchen. Tilsammen giver de forretningsanalytikere mulighed for nemmere at indsamle, forme, analysere og udforske deres data visuelt. Foruden at få vist Power BI-rapporter i webportalen kan virksomhedsbrugerne nu gøre det samme med Excel-projektmapper i Power BI-rapportserver, hvilket giver dem én samlet placering til at publicere og få vist deres Microsoft BI-indhold til selvbetjening.

Vi har udgivet en [gennemgang af, hvordan du tilføjer Office Online Server (OOS) i miljøet i din prøveversion af Power BI-rapportserver](excel-oos.md). Kunder, der har en volumenlicenskonto, kan downloade OOS fra Volume License Service Center uden omkostninger og få skrivebeskyttet funktionalitet. Efter konfigurationen kan brugerne få vist og interagere med Excel-projektmapper, der:

* ikke har nogen afhængigheder af eksterne data
* har en direkte forbindelse til en ekstern SQL Server Analysis Services-datakilde
* har en PowerPivot-datamodel.

### <a name="support-for-new-table-and-matrix-visuals"></a>Understøttelse af nye tabel- og matrixvisuals

Power BI-rapportserver understøtter nu de nye Power BI-tabel- og matrixvisuals. Hvis du vil oprette rapporter med disse visuals, skal du bruge en opdateret version af Power BI Desktop-udgave til versionen fra oktober 2017. Den kan ikke installeres side om side med versionen af Power BI Desktop fra juni 2017. Hvis du vil have den seneste version af Power BI Desktop, skal du vælge **Avancerede indstillinger for hentning af filer** på [siden til download af Power BI-rapportserver](https://powerbi.microsoft.com/report-server/).

## <a name="june-2017"></a>Juni 2017

* Power BI-rapportserver er blevet gjort offentligt tilgængeligt (GA).

## <a name="may-2017"></a>Maj 2017

* Prøveversion af Power BI-rapportserver gjort tilgængelig
* Mulighed for at publicere Power BI-rapporter i det lokale miljø
  * understøttelse af brugerdefinerede visualiseringer
  * Kun understøttelse af **Analysis Services-liveforbindelser**, men med flere datakilder på vej.
  * Appen Power BI - Mobil er blevet opdateret til at vise Power BI-rapporter, der hostes i Power BI-rapportserver
* Forbedret samarbejde i rapporter med kommentarer

## <a name="next-steps"></a>Næste trin

Kontrollér disse kilder for at holde dig ajour med nye funktioner i Power BI-rapportserver.

* [Microsoft Power BI-blog](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services-teamets blog](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [Guy in a Cube YouTube-kanal](https://aka.ms/guyinacube)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)