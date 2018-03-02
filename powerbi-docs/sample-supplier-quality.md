---
title: "Eksempel på analyse af leveringskvalitet til Power BI: Få en introduktion"
description: "Eksempel på analyse af leveringskvalitet til Power BI: Få en introduktion"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 01/19/2018
ms.author: mihart
LocalizationGroup: Samples
ms.openlocfilehash: 5636ccd4685205b2b01dd4c591942d7d2670bc48
ms.sourcegitcommit: 743e44fc8730fea0f7149916080b0c6d7eb6359d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/28/2018
---
# <a name="supplier-quality-analysis-sample-for-power-bi-take-a-tour"></a>Eksempel på analyse af leveringskvalitet til Power BI: Få en introduktion

## <a name="a-brief-overview-of-the-supplier-quality-analysis-sample"></a>En kort oversigt over eksemplet på analyse af leverandørkvalitet
Dette eksempel på et dashboard og den underliggende rapport for en bestemt branche fokuserer på en af de typiske udfordringer ved forsyningskæden – analyse af leveringskvalitet.
To primære målepunkter er i spil i denne analyse: det samlede antal defekter og den samlede nedetid, som disse defekter har været årsag til. Dette eksempel har to overordnede formål:

* At finde ud af hvem de bedste og de værste leverandører er med hensyn til kvalitet
* At identificer de anlæg, der er bedst til at finde og kassere defekter og dermed reducere nedetiden

![](media/sample-supplier-quality/supplier1.png)

Dette eksempel er en del af en række, der illustrerer, hvordan du kan bruge Power BI med forretningsrelaterede data, rapporter og dashboards.
Der er anvendt rigtige data fra obviEnce ([www.obvience.com](http://www.obvience.com/)), der er blevet anonymiseret.

## <a name="prerequisites"></a>Forudsætninger

 Før du kan bruge eksemplet, skal du først hente det som en [indholdspakke](https://docs.microsoft.com/en-us/power-bi/sample-supplier-quality#get-the-content-pack-for-this-sample), [.pbix-fil](http://download.microsoft.com/download/8/C/6/8C661638-C102-4C04-992E-9EA56A5D319B/Supplier-Quality-Analysis-Sample-PBIX.pbix) eller [Excel-projektmappe](http://go.microsoft.com/fwlink/?LinkId=529779).

### <a name="get-the-content-pack-for-this-sample"></a>Hent indholdspakken for dette eksempel

1. Åbn Power BI-tjenesten (app.powerbi.com), og log på.
2. Vælg **Hent data** i nederste venstre hjørne.
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. Vælg ikonet **Eksempler** på siden Hent data, der vises.
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. Vælg **Supplier Quality Analysis Sample**, og vælg **Opret forbindelse**.  
  
   ![Supplier Quality Analysis Sample](media/sample-supplier-quality/supplier16.png)
   
5. Power BI importerer indholdspakken og føjer et nyt dashboard, en rapport og et datasæt til dit aktuelle arbejdsområde. Det nye indhold er markeret med en gul stjerne. 
   
   ![Stjerne](media/sample-supplier-quality/supplier17.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Hent .pbix-filen knyttet til dette eksempel

Du kan også hente eksemplet som en pbix-fil, som er beregnet til brug med Power BI Desktop. 

 * [Supplier Quality Analysis Sample](http://download.microsoft.com/download/8/C/6/8C661638-C102-4C04-992E-9EA56A5D319B/Supplier-Quality-Analysis-Sample-PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Hent Excel-projektmappen for dette eksempel
Du kan også [kun downloade datasættet (Excel-projektmappe)](http://go.microsoft.com/fwlink/?LinkId=529779) for dette eksempel. Projektmappen indeholder Power View-ark, som du kan få vist og redigere. Du kan se de rå data ved at vælge **Power Pivot > Administrer**.


## <a name="downtime-caused-by-defective-materials"></a>Nedetid på grund af defekte materialer
Lad os analysere den nedetid, der skyldes defekte materialer, og se, hvilke forhandlere der er ansvarlige.  

1. På dashboardet skal du vælge talfeltet **Defekt antal i alt** eller talfeltet **Nedetid i minutter i alt**.  

   ![](media/sample-supplier-quality/supplier2.png)  

   "Eksempel på analyse af leveringskvalitet"-rapporten åbner siden "Analyse af nedetid". Bemærk, at vi har 33 millioner defekte enheder i alt, og den samlede nedetid, som disse enheder er skyld i, er på 77.000 minutter. Nogle materialer har færre defekte enheder, men de kan forårsage store forsinkelser, der medfører længere nedetid. Lad os se nærmere på dem på siden med rapporter.  
2. På linjen **Nedetid i minutter i alt** i kombinationsdiagrammet **Defekter og nedetid (min.) efter materialetype** kan vi se, at korrugerede materialer forårsager mest nedetid.  
3. Vælg kolonnen **Korrugeret** i det samme kombinationsdiagram for at se, hvilke anlæg, der påvirkes mest af denne defekt, og hvilken forhandler der er ansvarlig.  

   ![](media/sample-supplier-quality/supplier3.png)  
4. Vælg individuelle anlæg på kortet for at se, hvilken forhandler eller hvilket materiale der er ansvarligt for nedetid på det pågældende anlæg.

### <a name="which-are-the-worst-suppliers"></a>Hvem er de værste forhandlere?
 Vi ønsker at finde de værste otte forhandlere og at finde ud af, hvilken procentdel af nedetiden, de er ansvarlige for. Det kan vi gøre ved at ændre områdediagrammet **Nedetid (min.) efter forhandler** til en træstruktur.  

1. På side 3 af rapporten "Analyse af nedetid" skal du vælge **Rediger rapport** i det øverste venstre hjørne.  
2. Vælg områdediagrammet **Nedetid (min.) efter leverandør**, og vælg Træstruktur i ruden Visuelle elementer.  

   ![](media/sample-supplier-quality/supplier4.png)  

    Træstrukturen indstiller automatisk feltet **Leverandør** til **Gruppe**.  

    ![](media/sample-supplier-quality/supplier5.png)  

   I træstrukturen kan vi se de otte største leverandører som otte blokke til venstre. Vi kan også se, at de står for 50 % af alle minutterne i nedetiden.  
3. Vælg **Eksempel på analyse af leveringskvalitet** på den øverste navigationslinje for at vende tilbage til dashboardet.

### <a name="comparing-plants"></a>Sammenligning af anlæg
Nu vil vi se nærmere på, hvilke anlæg der er bedst til administration af defekte materialer, hvilket resulterer i mindre nedetid.  

1. Vælg kortfeltet **Defektrapporter i alt efter anlæg, defekttype**.  

    Rapporten åbner siden "Leveringskvalitet".  

   ![](media/sample-supplier-quality/supplier6.png)  
2. I kortforklaringen skal du vælge cirklen **Indvirkning**.  

    ![](media/sample-supplier-quality/supplier7.png)  

    Bemærk i boblediagrammet, at **Logistik** er den mest problematiske kategori – den er størst i forhold til antallet af defekter i alt, defektrapporter i alt og nedetid i minutter alt. Lad os se nærmere på denne kategori.  
3. Vælg Logistik-boblen i boblediagrammet, og se på anlæggene i Springfield, IL og Naperville, IL. Naperville ser ud til at klare sig meget bedre inden for administration af defekte leveringer, fordi den har et højt antal kasseringer og få indvirkninger, sammenlignet med Springfield’s høje antal indvirkninger.  

   ![](media/sample-supplier-quality/supplier8.png)  
4. Vælg **Eksempel på analyse af leveringskvalitet** på den øverste navigationslinje for at vende tilbage til dit aktive arbejdsområde.

## <a name="which-material-type-is-best-managed"></a>Hvilken materialetype er bedst administreret?
Den bedst administrerede materialetype er den med den korteste nedetid eller ingen indvirkning, uanset antallet af defekter.

* Se på feltet **Antal defekter i alt efter materialetype, defekttype** på dashboardet.

  ![](media/sample-supplier-quality/supplier9.png)

Bemærk, at **Råmaterialer** har et højt antal defekter i alt, men at de fleste af defekterne enten kasseres eller ingen indvirkning har.

Lad os bekræfte, at råmaterialer ikke medfører en masse nedetid trods det høje antal defekter.

* Se på feltet **Antal defekter i alt , samlet nedetid i minutter efter materialetype** på dashboardet.

  ![](media/sample-supplier-quality/supplier10.png)

Tilsyneladende administreres råmaterialer godt: De har flere defekter, men en kortere nedetid i minutter.

### <a name="compare-defects-to-downtime-by-year"></a>Sammenlign defekter i forhold til nedetid efter år
1. Vælg kortfeltet **Samlet antal defektrapporter efter anlæg, defekttype** for at åbne rapporten til den første rapportside, Leveringskvalitet.
2. Bemærk, at **Antal defekter** er højere i 2014 end i 2013.  

    ![](media/sample-supplier-quality/supplier11.png)  
3. Betyder flere defekter mere nedetid? Vi kan stille spørgsmål i Spørgsmål og svar for at finde ud af.  
4. Vælg **Eksempel på analyse af leveringskvalitet** på den øverste navigationslinje for at vende tilbage til dashboardet.  
5. Da vi ved, at råmaterialer har det højeste antal defekter, kan du skrive "Vis materialetyper, år og samlet antal defekter" i spørgsmålsfeltet.  

    Der var mange flere defekte råmaterialer i 2014 end i 2013.  

    ![](media/sample-supplier-quality/supplier12.png)  
6. Nu skal du ændre spørgsmålet til "Vis materialetyper, år og samlet nedetid i minutter".  

   ![](media/sample-supplier-quality/supplier13.png)

Nedetiden pga. råmaterialer var cirka den samme i 2013 og 2014, selvom der var mange flere defekte råmaterialer i 2014.

Det viser sig, at flere defekte råmaterialer i 2014 ikke førte til meget højere nedetid pga. råmaterialer i 2014.

### <a name="compare-defects-to-downtime-month-to-month"></a>Sammenlign defekter i forhold til nedetid måned efter måned
Lad os se på et andet dashboardfelt, der har relation til det samlede antal defekte materialer.  

1. Vælg tilbage-pilen ![](media/sample-supplier-quality/backarrow.png) i det øverste venstre hjørne over feltet til spørgsmål for at komme tilbage til dashboardet.  

    Når vi ser nærmere på feltet **Defekter i alt efter måned, år**, viser det, at det første halvår af 2014 havde et antal defekter, der ligner antallet i 2013, men i andet halvår af 2014 steg antallet af defekter væsentligt.  

    ![](media/sample-supplier-quality/supplier14.png)  

    Lad os se, om denne forøgelse i antallet af defekter førte til en lignende forøgelse af nedetiden i minutter.  
2. Skriv "samlet nedetid i minutter efter måned og år som et kurvediagram" i feltet til spørgsmål.  

   ![](media/sample-supplier-quality/supplier15.png)

   Vi kan se et spring i nedetiden i minutter i juni og oktober, men derudover resulterede springet i det samlede antal defekter ikke i væsentligt længere nedetid. Det viser, at vi administrerer defekter korrekt.  
3. Du kan fastgøre dette diagram på dit dashboard ved at vælge tegnestiftikonet ![](media/sample-supplier-quality/pin.png) til højre for feltet til spørgsmål.  
4. For at se nærmere på de afvigende måneder kan du f.eks. se på nedetiden i minutter i oktober efter materialetype, anlæggets placering, kategori osv. og stille spørgsmål som f.eks. "samlet nedetid i minutter i oktober efter anlæg".    
5. Vælg tilbage-pilen ![](media/sample-supplier-quality/backarrow.png) i det øverste venstre hjørne over feltet til spørgsmål for at komme tilbage til dashboardet.

Dette er et sikkert miljø at lege i. Du kan altid vælge ikke at gemme dine ændringer. Hvis du gemmer dem, kan du altid gå til **Hent data** for at få en ny kopi af dette eksempel.

## <a name="next-steps-connect-to-your-data"></a>Næste trin: Opret forbindelse til dine data
Vi håber, at denne rundtur viser, hvordan Power BI-dashboards, spørgsmål og svar og rapporter kan give indsigt i data om leveringskvalitet. Nu er det din tur – opret forbindelse til dine egne data. Med Power BI kan du oprette forbindelse til en lang række datakilder. Få mere at vide om, hvordan du [kommer i gang med Power BI](service-get-started.md).
