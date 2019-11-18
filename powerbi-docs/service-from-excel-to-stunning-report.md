---
title: Fra Excel-projektmappe til fantastisk rapport i Power BI-tjenesten
description: I denne artikel kan du se, hvordan du hurtigt kan oprette en fantastisk rapport fra en Excel-projektmappe.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/12/2019
ms.author: maggies
LocalizationGroup: Data from files
ms.openlocfilehash: 6c393611851e05c7c76983674f2e1de7b5454898
ms.sourcegitcommit: 2aa83bd53faad6fb02eb059188ae623e26503b2a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/29/2019
ms.locfileid: "73020986"
---
# <a name="from-excel-workbook-to-stunning-report-in-the-power-bi-service"></a>Fra Excel-projektmappe til fantastisk rapport i Power BI-tjenesten
Din chef vil gerne se en rapport om dine seneste salgstal kombineret med dine seneste kampagneannoncer, inden dagen er omme. Men de nyeste data befinder sig i forskellige systemer hos tredjeparter og i filer på din bærbare computer. Tidligere har det taget timer at oprette visuelle elementer og formatere en rapport, og du er ved at være lidt nervøs.

Bare rolig. Med Power BI kan du oprette en imponerende rapport på ingen tid.

I dette eksempel uploader vi en Excel-fil fra et lokalt system, opretter en ny rapport og deler den med kolleger – alt sammen fra Power BI.

## <a name="prepare-your-data"></a>Forbered dine data
Lad os tage en simpel Excel-fil som eksempel. 

1. Før du kan indlæse din Excel-fil i Power BI, skal du organisere dine data i en flad tabel. I en flad tabel indeholder hver kolonne den samme datatype – f.eks. tekst, dato, tal eller valuta. Tabellen skal have en kolonneoverskrift, men ikke nogen kolonner eller rækker, der viser totaler.

   ![Data, der er organiseret i Excel](media/service-from-excel-to-stunning-report/pbi_excel_file.png)

2. Formatér derefter dataene som en tabel. I Excel skal du vælge **Formatér som tabel** på fanen **Hjem** i gruppen **Typografier**. 

3. Vælg en tabeltypografi, der skal anvendes på regnearket. 

   Dit Excel-regneark er nu klar til at blive indlæst i Power BI.

   ![Data, der er formateret som en tabel](media/service-from-excel-to-stunning-report/pbi_excel_table.png)

## <a name="upload-your-excel-file-to-the-power-bi-service"></a>Upload din Excel-fil til Power BI-tjenesten
Power BI-tjenesten opretter forbindelse til mange datakilder, herunder Excel-filer, der findes på din computer. 

 > [!NOTE] 
 > Brug [projektmappen Økonomieksempel](sample-financial-download.md) for at følge med i resten af dette selvstudium.

1. Log på Power BI-tjenesten for at komme i gang. Hvis du ikke har tilmeldt dig, [kan du gøre det gratis](https://powerbi.com).

2. Du vil oprette et nyt dashboard. Åbn **Mit arbejdsområde**, og vælg ikonet **Opret**.

   ![Ikonet Opret](media/service-from-excel-to-stunning-report/power-bi-new-dash.png)

3. Vælg **Dashboard**, angiv et navn, og vælg **Opret**. 

   Det nye dashboard vises – uden data.

   ![Rullelisten Opret](media/service-from-excel-to-stunning-report/power-bi-create-dash.png)

4. Vælg **Hent data** nederst i venstre navigationsrude. 

5. Vælg **Hent** under **Opret nyt indhold** i feltet **Filer** på siden **Hent data**.

   ![Hent data fra filer](media/service-from-excel-to-stunning-report/pbi_get_files.png)

6. Vælg **Lokal fil** på siden **Filer**. Gå til Excel-projektmappefilen på computeren, og vælg **Åbn** for at indlæse den i Power BI-tjenesten. 

   ![Hent data > Vinduet Filer](media/service-from-excel-to-stunning-report/pbi_local_file.png)

7. Vælg **Importér** på siden **Lokal fil**.


## <a name="build-your-report"></a>Opbyg din rapport
Når Power BI-tjenesten har importeret din Excel-fil, kan du begynde at opbygge din rapport. 

1. Når meddelelsen **Dit datasæt er parat** vises, skal du vælge **Vis datasæt**.  

   Power BI åbnes i redigeringsvisningen og viser rapportlærredet. Til højre finder du ruderne **Visualiseringer**, **Filtre** og **Felter**. Bemærk, at dataene fra tabellen i din Excel-projektmappe vises i ruden **Felter**. Under tabellens navn viser Power BI kolonneoverskrifterne som individuelle felter.

   ![Sådan ser Excel-data ud i ruden Felter](media/service-from-excel-to-stunning-report/pbi_report_fields.png)

2. Nu kan du begynde at oprette visualiseringer. Lad os sige, at din chef gerne vil have vist profit over tid. I ruden **Felter** skal du trække **Profit** til rapportlærredet. 

   Power BI viser et søjlediagram som standard. 

3. Derefter skal du trække **Dato** til rapportlærredet. 

   Power BI opdaterer søjlediagrammet for at vise profit efter dato.

   ![Søjlediagram i rapporteditor](media/service-from-excel-to-stunning-report/pbi_report_pin-new.png)

   > [!TIP]
   > Hvis diagrammet ikke ser ud som forventet, skal du kontrollere dine aggregeringer. For eksempel kan du under **Værdi** højreklikke på det felt, du lige har tilføjet, og kontrollere, at dataene lægges sammen på den måde, du ønsker. I dette eksempel bruger vi **Sum**.
   > 

Din chef vil gerne vide, hvilke lande/områder der er mest rentable. Imponer dem med en kortvisualisering. 

1. Vælg et tomt område på dit rapportlærred. 

2. I ruden **Felter** skal du trække felterne **Land** og **Profit** til rapportlærredet.

   Power BI opretter en kortvisual med bobler, der repræsenterer avancen for hver af de enkelte placeringer.

   ![Kortvisualisering i rapporteditor](media/service-from-excel-to-stunning-report/pbi_report_map-new.png)

Hvad med at vise en visual for salg efter produkt og markedssegment? Nemt nok. 

1. I ruden **Felter** skal du markere felterne **Salg**, **Produkt** og **Segment**. 
   
   Power BI opretter straks et liggende søjlediagram. 

2. Du kan ændre diagramtypen ved at vælge et af ikonerne i menuen **Visualiseringer**. Du kan f.eks. ændre det til et **stablet liggende søjlediagram**. 

3. Hvis du vil sortere diagrammet, skal du vælge **Flere indstillinger** (...) > **Sortér efter**.

   ![Stablet søjlediagram i rapporteditor](media/service-from-excel-to-stunning-report/pbi_barchart-new.png)

Fastgør alle dine visuelle elementer til dashboardet. Du er nu klar til at dele dem med dine kolleger.

   ![Dashboard, hvor de tre visuelle elementer er fastgjort](media/service-from-excel-to-stunning-report/pbi_report.png)

## <a name="share-your-dashboard"></a>Del dit dashboard
Lad os sige, at du gerne vil dele dashboardet med din chef. Du kan dele dit dashboard og den underliggende rapport med enhver kollega, der har en Power BI-konto. De kan interagere med rapporten, men ikke gemme ændringerne.

1. Hvis du vil dele din rapport, skal du vælge **Del** øverst på dashboardet.

   ![Delingsikon](media/service-from-excel-to-stunning-report/power-bi-share.png)

   Power BI viser siden **Del dashboard**. 

2. Angiv mailadresser på modtagerne i feltet **Angiv mailadresser**, og tilføj en meddelelse i feltet nedenfor. 

3. Hvis du vil tillade dine kollegaer at dele dit dashboard med andre, skal du markere **Tillad, at modtagerne må dele dette dashboard**. Vælg **Del**.

   ![Del dashboardvindue](media/service-from-excel-to-stunning-report/power-bi-share-dash-new.png)

## <a name="next-steps"></a>Næste trin

* [Kom i gang med Power BI-tjenesten](service-get-started.md)
* [Kom i gang med Power BI Desktop](desktop-getting-started.md)
* [Grundlæggende begreber for designere i Power BI-tjenesten](service-basic-concepts.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/).

