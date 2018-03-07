---
title: "Brug Figurkort i Power BI Desktop (prøveversion)"
description: "Opret relative sammenligninger mellem områder ved hjælp af figurkort i Power BI Desktop"
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
ms.date: 01/16/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 335e9800be3d2a2cd30cc84835ab7b0173922c46
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2018
---
# <a name="shape-maps-in-power-bi-desktop-preview"></a>Figurkort i Power BI Desktop (prøveversion)
I Power BI Desktop kan du oprette visualiseringen **Figurkort** for at vise relative sammenligninger mellem områder på et kort ved at anvende forskellige farver for forskellige områder. I modsætning til visualiseringen **Kort** kan **Figurkort** ikke vise nøjagtige geografiske lokationer med datapunkter på et kort. I stedet er det primære formål at vise relative sammenligninger af områder på et kort ved at farvelægge dem forskelligt.

Visualiseringen **Figurkort** er baseret på ESRI/TopoJSON-kort, der kan anvendes med brugerdefinerede kort, som du opretter, for eksempel geografiske kort, arrangement af siddepladser og andet. Muligheden for at bruge brugerdefinerede kort er ikke tilgængelig i denne evalueringsversion af **Figurkort**.

## <a name="creating-shape-maps"></a>Opret figurkort
Du kan afprøve kontrolelementet **Figurkort** med de kort, som medfølger i denne prøveversion, eller du kan bruge dine egne brugerdefinerede kort, så længe de opfylder de krav, der er angivet i afsnittet **Brug brugerdefinerede kort** nedenfor.

Visualiseringen **Figurkort** er en prøveversion og skal aktiveres i Power BI Desktop. Du kan aktivere **Figurkort** ved at vælge **Fil > Indstillinger > Indstillinger > Funktioner til eksempelvisning** og derefter markere afkrydsningsfeltet **Figurkort**. Du skal genstarte Power BI Desktop, når du har markeret indstillingen.

![](media/desktop-shape-map/shape-map_1a.png)

Når du har aktiveret **Figurkort**, skal du klikke på kontrolelementet **Figurkort** i ruden **Visualiseringer**.

![](media/desktop-shape-map/shape-map_2.png)

Power BI Desktop opretter et tomt designlærred for **figurkortet**.

![](media/desktop-shape-map/shape-map_3.png)

Gør følgende for at oprette et **figurkort**:

1. I ruden **Felter** skal du trække et datafelt med navne på områder (eller forkortelser) til feltet **Placering** og et datamålingsfelt til feltet **Værdier** (der vises ikke et kort endnu).
   
   > [!NOTE]
> Se afsnittet **Hent kortdata** herunder for at få oplysninger om, hvordan du hurtigt kan hente kortdata til test af **Figurkort**.
   > 
   > 
   
   ![](media/desktop-shape-map/shape-map_3a.png)
2. I ruden **Format** skal du udvide **Figur** og vælge på rullemenuen **Standardkort** for at få vist dine data. På nuværende tidspunkt vises gengivelsen af kortet som vist i følgende billede.
   
   ![](media/desktop-shape-map/shape-map_3b.png)
   
   > [!NOTE]
> I afsnittet **Områdenøgler** sidst i denne artikel kan du se en samling af tabeller, som indeholder kortområdenøgler, du kan bruge til at teste visualiseringen **Figurkort**.
   > 
   > 
3. Derefter kan du ændre kortprojiceringen og zoomindstillinger samt farverne på datapunkterne under indstillingerne i ruden **Format**. Du kan også ændre zoomindstillingerne. Du kan for eksempel ændre farver, angive maksimum- og minimumværdier med mere.
   
   ![](media/desktop-shape-map/shape-map_3d.png)
4. Du kan også tilføje en kolonne med kategoridata i feltet **Forklaring** og klassificere kortområderne baseret på kategorier.

## <a name="use-custom-maps"></a>Brug brugerdefinerede kort
Du kan bruge brugerdefinerede kort med **Figurkort**, hvis de er i formatet **TopoJSON**. Hvis dit kort er i et andet format, kan du bruge onlineværktøjer som [**Map Shaper**](http://mapshaper.org/) til at konvertere dine *figurfiler* eller dine *GeoJSON*-kort til **TopoJSON**-format.

Hvis du vil bruge en **TopoJSON**-kortfil, skal du tilføje visualiseringen Figurkort i din rapport og tilføje nogle data i felterne *Placering* og *Værdier*. Derefter skal du vælge sektionen **Format** (malerrullen, der vises som (1) i det følgende billede) i ruden **Visualiseringer**, udvide sektionen **Figur** og vælge **+ Tilføj kort**.

![](media/desktop-shape-map/shape-map_6.png)

## <a name="getting-map-data"></a>Hent kortdata
Hvis du hurtigt vil hente data ind i en model, så du kan teste **Figurkort**, kan du kopiere en af tabellerne sidst i denne artikel og derefter vælge **Angiv data** under fanen **Hjem**.

![](media/desktop-shape-map/shape-map_4.png)

Du kan derefter indsætte tabellen i Power BI Desktop. Den øverste række bliver automatisk identificeret som overskrift.

![](media/desktop-shape-map/shape-map_5.png)

Du kan angive en ny kolonne ved at skrive et nyt kolonnenavn (i den tomme kolonne til højre) og derefter angive værdier i hver celle på samme måde som i Excel. Når du er færdig, skal du vælge **Indlæs**, hvorefter tabellen tilføjes i datamodellen for Power BI Desktop.

> [!NOTE]
> Når du arbejder med lande eller områder, kan du bruge forkortelsen på tre bogstaver til at sikre, at geokodning fungerer korrekt i kortvisualiseringer. Benyt *ikke* forkortelser på to bogstaver, da nogle lande eller områder muligvis ikke genkendes korrekt.
> 
> Hvis du kun har forkortelser på to bogstaver, kan du tjekke [dette eksterne blogindlæg](https://blog.ailon.org/how-to-display-2-letter-country-data-on-a-power-bi-map-85fc738497d6#.yudauacxp) for at få fremgangsmåden til, hvordan forkortelser på to bogstaver for land/område knyttes til forkortelser på tre bogstaver for land/område.
> 
> 

## <a name="preview-behavior-and-requirements"></a>Funktionsmåder og krav i prøveversionen
Du skal være opmærksom på nogle få ting i forbindelse med denne prøveversion af **Figurkort**:

* Visualiseringen **Figurkort** er en prøveversion og skal aktiveres i Power BI Desktop. Du kan aktivere **Figurkort** ved at vælge **Fil > Indstillinger > Indstillinger > Funktioner til eksempelvisning** og derefter markere afkrydsningsfeltet **Figurkort**.
* Du skal også angive værdier i feltet **Værdier** for at klassificeringen **Forklaring** virker korrekt
* I den endelige udgave af **Figurkort**, vil brugergrænsefladen vise kortnøglerne for det aktuelt valgte kort (der er ikke angivet nogen dato for den endelige udgave, og **Figurkort** er stadig en prøveversion). I denne prøveversion kan du referere til kortområdenøglerne i tabellerne i afsnittet **Områdenøgler** i denne artikel.
* Den visuelle fremstilling i **Figurkort** kan maksimal vise op til 1.000 datapunkter.

## <a name="region-keys"></a>Områdenøgler
Brug følgende **Områdenøgler** i denne prøveversion for at afprøve **Figurkort**.

### <a name="australia-states"></a>Australien: delstater
| id | forkortelse | iso | navn | postal |
| --- | --- | --- | --- | --- |
| au-wa |WA |AU-WA |Western Australia |WA |
| au-vic |Vic |AU-VIC |Victoria |VIC |
| au-tas |Tas |AU-TAS |Tasmania |TAS |
| au-sa |SA |AU-SA |South Australia |SA |
| au-qld |Qld |AU-QLD |Queensland |QLD |
| au-nt |NT |AU-NT |Northern Territory |NT |
| au-nsw |NSW |AU-NSW |New South Wales |NSW |
| au-act |ACT |AU-ACT |Australian Capital Territory |ACT |

### <a name="austria-states"></a>Østrig: delstater
| id | iso | navn | navn-en | postnummer |
| --- | --- | --- | --- | --- |
| at-wi |AT-9 |Wien |Vienna |WI |
| at-vo |AT-8 |Vorarlberg |Vorarlberg |VO |
| at-tr |AT-7 |Tirol |Tyrol |TR |
| at-st |AT-6 |Steiermark |Styria |ST |
| at-sz |AT-5 |Salzburg |Salzburg |SZ |
| at-oo |AT-4 |Oberösterreich |Upper Austria |OO |
| at-no |AT-3 |Niederösterreich |Lower Austria |NO |
| at-ka |AT-2 |Kärnten |Carinthia |KA |
| at-bu |AT-1 |Burgenland |Burgenland |BU |

### <a name="brazil-states"></a>Brasilien: delstater
| id |
| --- |
| Tocantins |
| Pernambuco |
| Goias |
| Sergipe |
| Sao Paulo |
| Santa Catarina |
| Roraima |
| Rondonia |
| Rio Grande do Sul |
| Rio Grande do Norte |
| Rio de Janeiro |
| Piaui |
| Parana |
| Paraiba |
| Para |
| Minas Gerais |
| Mato Grosso |
| Maranhao |
| Mato Grosso do Sul |
| Distrito Federal |
| Ceara |
| Espirito Santo |
| Bahia |
| Amazonas |
| Amapa |
| Alagoas |
| Acre |
| Litigated Zone 1 |
| Litigated Zone 2 |
| Litigated Zone 3 |
| Litigated Zone 4 |

### <a name="canada-provinces"></a>Canada: provinser
| id | iso | navn | postnummer |
| --- | --- | --- | --- |
| ca-nu |CA-NU |Nunavut |NU |
| ca-nt |CA-NT |Northwest Territories |NT |
| ca-yt |CA-YT |Yukon |YT |
| ca-sk |CA-SK |Saskatchewan |SK |
| ca-qc |CA-QC |Quebec |QC |
| ca-pe |CA-PE |Prince Edward Island |PE |
| ca-on |CA-ON |Ontario |ON |
| ca-ns |CA-NS |Nova Scotia |NS |
| ca-nl |CA-NL |Newfoundland and Labrador |NL |
| ca-nb |CA-NB |New Brunswick |NB |
| ca-mb |CA-MB |Manitoba |MB |
| ca-bc |CA-BC |British Columbia |BC |
| ca-ab |CA-AB |Alberta |AB |

### <a name="france-regions"></a>Frankrig: regioner
| id | navn | navn-en |
| --- | --- | --- |
| Alsace |Alsace |Alsace |
| Rhone-Alpes |Rhône-Alpes |Rhone-Alpes |
| Provence-Alpes-Cote d'Azur |Provence-Alpes-Côte d'Azur |Provence-Alpes-Cote d'Azur |
| Poitou-Charentes |Poitou-Charentes |Poitou-Charentes |
| Picardie |Picardie |Picardy |
| Pays de la Loire |Pays de la Loire |Pays de la Loire |
| Nord-Pas-de-Calais |Nord-Pas-de-Calais |Nord-Pas-de-Calais |
| Midi-Pyrenees |Midi-Pyrénées |Midi-Pyrenees |
| Lorraine |Lorraine |Lorraine |
| Limousin |Limousin |Limousin |
| Languedoc-Roussillon |Languedoc-Roussillon |Languedoc-Roussillon |
| Ile-del-France |Île-de-France |Ile-de-France |
| Haute-Normandie |Haute-Normandie |Upper Normandy |
| Franche-Comte |Franche-Comté |Franche-Comte |
| Corse |Corse |Corsica |
| Champagne-Ardenne |Champagne-Ardenne |Champagne-Ardenne |
| Centre-Val de Loire |Centre-Val de Loire |Centre-Val de Loire |
| Bretagne |Bretagne |Brittany |
| Bourgogne |Bourgogne |Burgundy |
| Basse-Normandie |Basse-Normandie |Lower Normandy |
| Auvergne |Auvergne |Auvergne |
| Aquitaine |Aquitaine |Aquitaine |

### <a name="germany-states"></a>Tyskland: delstater
| id | iso | navn | navn-en | postnummer |
| --- | --- | --- | --- | --- |
| de-be |DE-BE |Berlin |Berlin |BE |
| de-th |DE-TH |Thüringen |Thuringia |TH |
| de-st |DE-ST |Sachsen-Anhalt |Saxony-Anhalt |ST |
| de-sn |DE-SN |Sachsen |Saxony |SN |
| de-mv |DE-MV |Mecklenburg-Vorpommern |Mecklenburg-Vorpommern |MV |
| de-bb |DE-BB |Brandenburg |Brandenburg |BB |
| de-sh |DE-SH |Schleswig-Holstein |Schleswig-Holstein |SH |
| de-sl |DE-SL |Saarland |Saarland |SL |
| de-rp |DE-RP |Rheinland-Pfalz |Rhineland-Palatinate |RP |
| de-nw |DE-NW |Nordrhein-Westfalen |North Rhine-Westphalia |NW |
| de-ni |DE-NI |Niedersachsen |Lower Saxony |NI |
| de-he |DE-HE |Hessen |Hesse |HE |
| de-hh |DE-HH |Hamborg |Hamburg |HH |
| de-hb |DE-HB |Bremen |Bremen |HB |
| de-by |DE-BY |Bayern |Bavaria |BY |
| de-bw |DE-BW |Baden-Württemberg |Baden-Wurttemberg |BW |

### <a name="ireland-counties"></a>Irland: amter
| id |
| --- |
| Wicklow |
| Wexford |
| Westmeath |
| Waterford |
| Sligo |
| Tipperary |
| Roscommon |
| Offaly |
| Monaghan |
| Meath |
| Mayo |
| Louth |
| Longford |
| Limerick |
| Leitrim |
| Laoighis |
| Kilkenny |
| Kildare |
| Kerry |
| Galway |
| Dublin |
| Donegal |
| Cork |
| Clare |
| Cavan |
| Carlow |

### <a name="italy-regions"></a>Italien: regioner
| id | iso | navn | navn-en | postnummer |
| --- | --- | --- | --- | --- |
| it-vn |IT-34 |Veneto |Veneto |VN |
| it-vd |IT-23 |Valle d'Aosta |Aosta Valley |VD |
| it-um |IT-55 |Umbrien |Umbria |UM |
| it-tt |IT-32 |Trentino-Alto Adige |Trentino-South Tyrol |TT |
| it-tc |IT-52 |Toscana |Tuscany |TC |
| it-sc |IT-82 |Sicilien |Sicily |SC |
| it-sd |IT-88 |Sardinien |Sardinia |SD |
| it-pm |IT-21 |Piemonte |Piedmont |PM |
| it-ml |IT-67 |Molise |Molise |ML |
| it-mh |IT-57 |Marche |Marche |MH |
| it-lm |IT-25 |Lombardiet |Lombardy |LM |
| it-lg |IT-42 |Ligurien |Liguria |LG |
| it-lz |IT-62 |Lazio |Lazio |LZ |
| it-fv |IT-36 |Friuli-Venezia Giulia |Friuli-Venezia Giulia |FV |
| it-er |IT-45 |Emilia-Romagna |Emilia-Romagna |ER |
| it-cm |IT-72 |Campania |Campania |CM |
| it-lb |IT-78 |Calabrien |Calabria |LB |
| it-bc |IT-77 |Basilicata |Basilicata |BC |
| it-pu |IT-75 |Apulien |Puglia |PU |
| it-ab |IT-65 |Abruzzo |Abruzzo |AB |

### <a name="mexico-states"></a>Mexico: delstater
| id | abreviatura | iso | navn | navn-en | postnummer |
| --- | --- | --- | --- | --- | --- |
| mx-zac |Zac. |MX-ZAC |Zacatecas |Zacatecas |ZA |
| mx-yuc |Yuc. |MX-YUC |Yucatán |Yucatan |YU |
| mx-ver |Ver. |MX-VER |Veracruz |Veracruz |VE |
| mx-tla |Tlax. |MX-TLA |Tlaxcala |Tlaxcala |TL |
| mx-tam |Tamps. |MX-TAM |Tamaulipas |Tamaulipas |TM |
| mx-tab |Tab. |MX-TAB |Tabasco |Tabasco |TB |
| mx-son |Son. |MX-SON |Sonora |Sonora |SO |
| mx-sin |Sin. |MX-SIN |Sinaloa |Sinaloa |SI |
| mx-slp |S.L.P. |MX-SLP |San Luis Potosí |San Luis Potosi |SL |
| mx-roo |Q.R. |MX-ROO |Quintana Roo |Quintana Roo |QR |
| mx-que |Qro. |MX-QUE |Querétaro |Queretaro |QE |
| mx-pue |Pue. |MX-PUE |Puebla |Puebla |PU |
| mx-oax |Oax. |MX-OAX |Oaxaca |Oaxaca |OA |
| mx-nle |N.L. |MX-NLE |Nuevo León |Nuevo Leon |NL |
| mx-nay |Nay. |MX-NAY |Nayarit |Nayarit |NA |
| mx-mor |Mor. |MX-MOR |Morelos |Morelos |MR |
| mx-mic |Mich. |MX-MIC |Michoacán |Michoacan |MC |
| mx-mex |Méx. |MX-MEX |Mexico |Mexico State |MX |
| mx-jal |Jal. |MX-JAL |Jalisco |Jalisco |JA |
| mx-hid |Hgo. |MX-HID |Hidalgo |Hidalgo |HI |
| mx-gro |Gro. |MX-GRO |Guerrero |Guerrero |GR |
| mx-gua |Gto. |MX-GUA |Guanajuato |Guanajuato |GT |
| mx-dur |Dgo. |MX-DUR |Durango |Durango |DU |
| mx-dif |Col. |MX-DIF |Mexico City |Mexico City |DF |
| mx-col |Coah. |MX-COL |Colima |Colima |CL |
| mx-coa |Chis. |MX-COA |Coahuila |Coahuila |CA |
| mx-chh |Chih. |MX-CHH |Chihuahua |Chihuahua |CH |
| mx-chp |CDMX. |MX-CHP |Chiapas |Chiapas |CP |
| mx-cam |Camp. |MX-CAM |Campeche |Campeche |CM |
| mx-bcs |B.C.S. |MX-BCS |Baja California Sur |Baja California Sur |BS |
| mx-bcn |B.C. |MX-BCN |Baja California |Baja California |BN |
| mx-agu |Ags. |MX-AGU |Aguascalientes |Aguascalientes |AG |

### <a name="netherlands-provinces"></a>Nederlandene: provinser
| id | iso | navn | navn-en |
| --- | --- | --- | --- |
| nl-zh |NL-ZH |Zuid-Holland |South Holland |
| nl-ze |NL-ZE |Zeeland |Zeeland |
| nl-ut |NL-UT |Utrecht |Utrecht |
| nl-ov |NL-OV |Overijssel |Overijssel |
| nl-nh |NL-NH |Noord-Holland |North Holland |
| nl-nb |NL-NB |Noord-Brabant |North Brabant |
| nl-li |NL-LI |Limburg |Limburg |
| nl-gr |NL-GR |Groningen |Groningen |
| nl-ge |NL-GE |Gelderland |Gelderland |
| nl-fr |NL-FR |Fryslân |Friesland |
| nl-fl |NL-FL |Flevoland |Flevoland |
| nl-dr |NL-DR |Drenthe |Drenthe |

### <a name="uk-countries"></a>Storbritannien: lande/områder
| id | iso | navn |
| --- | --- | --- |
| gb-wls |GB-WLS |Wales |
| gb-sct |GB-SCT |Skotland |
| gb-nir |GB-NIR |Nordirland |
| gb-eng |GB-ENG |England |

### <a name="usa-states"></a>USA: stater
| id | navn | postnummer |
| --- | --- | --- |
| us-mi |Michigan |MI |
| us-ak |Alaska |AK |
| us-hi |Hawaii |HI |
| us-fl |Florida |FL |
| us-la |Louisiana |LA |
| us-ar |Arkansas |AR |
| us-sc |South Carolina |SC |
| us-ga |Georgia |GA |
| us-ms |Mississippi |MS |
| us-al |Alabama |AL |
| us-nm |New Mexico |NM |
| us-tx |Texas |TX |
| us-tn |Tennessee |TN |
| us-nc |North Carolina |NC |
| us-ok |Oklahoma |OK |
| us-az |Arizona |AZ |
| us-mo |Missouri |MO |
| us-va |Virginia |VA |
| us-ks |Kansas |KS |
| us-ky |Kentucky |KY |
| us-co |Colorado |CO |
| us-md |Maryland |MD |
| us-wv |West Virginia |WV |
| us-de |Delaware |DE |
| us-dc |District of Columbia |DC |
| us-il |Illinois |IL |
| us-oh |Ohio |OH |
| us-ca |Californien |CA |
| us-ut |Utah |UT |
| us-nv |Nevada |NV |
| us-in |Indiana |IN |
| us-nj |New Jersey |NJ |
| us-ri |Rhode Island |RI |
| us-ct |Connecticut |CT |
| us-pa |Pennsylvania |PA |
| us-ny |New York |NY |
| us-ne |Nebraska |NE |
| us-ma |Massachusetts |MA |
| us-ia |Iowa |IA |
| us-nh |New Hampshire |NH |
| us-or |Oregon |OR |
| us-mn |Minnesota |MN |
| us-vt |Vermont |VT |
| us-id |Idaho |ID |
| us-wi |Wisconsin |WI |
| us-wy |Wyoming |WY |
| us-sd |South Dakota |SD |
| us-nd |North Dakota |ND |
| us-me |Maine |ME |
| us-mt |Montana |MT |
| us-wa |Washington |WA |

