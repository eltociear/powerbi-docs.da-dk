---
title: 'Eksempel på indkøbsanalyse: Få en introduktion'
description: 'Eksempel på indkøbsanalyse for Power BI: Få en introduktion'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/23/2018
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 18b99bf86f49f1355d4ab9f20ff6e8a83c89731d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61233617"
---
# <a name="procurement-analysis-sample-for-power-bi-take-a-tour"></a>Eksempel på indkøbsanalyse for Power BI: Få en introduktion

## <a name="overview-of-the-procurement-analysis-sample"></a>Oversigt over eksemplet på indkøbsanalyse
Dette brancheeksempel på et dashboard og den underliggende rapport tager udgangspunkt i en produktionsvirksomheds udgifter til leverandører efter kategori og placering. I eksemplet udforsker vi følgende områder:

* Hvem er topleverandørerne
* Hvilke kategorier vi har flest udgifter til
* Hvilke leverandører giver os de største rabatter og hvornår

Dette eksempel er en del af en række, der illustrerer, hvordan du kan bruge Power BI med forretningsrelaterede data, rapporter og dashboards. Der er anvendt rigtige data fra obviEnce ([www.obvience.com)](http://www.obvience.com/), som er blevet anonymiseret.

![](media/sample-procurement/procurement1.png)

## <a name="prerequisites"></a>Forudsætninger

 Før du kan bruge eksemplet, skal du først downloade det som en [indholdspakke](https://docs.microsoft.com/power-bi/sample-procurement#get-the-content-pack-for-this-sample), [.pbix-fil](http://download.microsoft.com/download/D/5/3/D5390069-F723-413B-8D27-5888500516EB/Procurement%20Analysis%20Sample%20PBIX.pbix) eller [Excel-projektmappe](http://go.microsoft.com/fwlink/?LinkId=529784).

### <a name="get-the-content-pack-for-this-sample"></a>Hent indholdspakken for dette eksempel

1. Åbn Power BI-tjenesten (app.powerbi.com), og log på.
2. Vælg **Hent data** i nederste venstre hjørne.
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. Vælg ikonet **Eksempler** på siden Hent data, der vises.
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. Vælg **Eksempel på indkøbsanalyse**, og vælg **Opret forbindelse**.  
  
   ![Hent data](media/sample-procurement/procurement1a.png)
   
5. Power BI importerer indholdspakken og føjer et nyt dashboard, en rapport og et datasæt til dit aktuelle arbejdsområde. Det nye indhold er markeret med en gul stjerne. 
   
   ![Stjerne](media/sample-procurement/procurement1b.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Hent .pbix-filen knyttet til dette eksempel

Du kan også hente eksemplet som en pbix-fil, som er beregnet til brug med Power BI Desktop. 

 * [Procurement Analysis Sample](http://download.microsoft.com/download/D/5/3/D5390069-F723-413B-8D27-5888500516EB/Procurement%20Analysis%20Sample%20PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Hent Excel-projektmappen for dette eksempel
Du kan også [kun downloade datasættet (Excel-projektmappe)](http://go.microsoft.com/fwlink/?LinkId=529784) for dette eksempel. Projektmappen indeholder Power View-ark, som du kan få vist og redigere. Du kan se de rå data ved at vælge **Power Pivot > Administrer**.


## <a name="spending-trends"></a>Udgiftstendenser
Lad os først se på udgiftstendenser efter kategori og placering.  

1. Åbn fanen **Dashboards** fra arbejdsområdet, og vælg dashboardet Procurement Analysis.
2. Vælg dashboardfeltet **Total Invoice by Country/Region**. Det åbner siden "Spend Overview" i rapporten "Procurement Analysis Sample".

    ![](media/sample-procurement/procurement2.png)

Vær opmærksom på et par ting:

* I kurvediagrammet **Total Invoice by Month and Category**: Kategorien **Direct** har ret konsistente udgifter, **Logistics** er højest i december, og **Other** er højest i februar.
* På kortet **Total Invoice by Country/Region**: De fleste af vores udgifter er i USA.
* I søjlediagrammet **Total Invoice by Sub Category**: **Hardware** og **Indirect Goods & Services** er de største udgiftskategorier.
* I det liggende søjlediagram Total Invoice by Tier: De fleste af vores forretninger finder sted med vores leverandører på niveau 1 (de 10 øverste). Dette hjælper os med at bedre administrere leverandørrelationer.

## <a name="spending-in-mexico"></a>Udgifter i Mexico
Lad os udforske udgiftsområder i Mexico.

1. I cirkeldiagrammet skal du vælge boblen **Mexico** på kortet. Læg mærke til, at i søjlediagrammet "Total Invoice by Sub Category"er det meste i underkategorien **Indirect Goods & Services**.

   ![](media/sample-procurement/pbi_procsample_spendmexico.png)
2. Foretag detaljeudledning i kolonnen **Indirect Goods & Services**:

   * Vælg pilen til detaljeudledning ![](media/sample-procurement/pbi_drilldown_icon.png) i øverste højre hjørne af diagrammet.
   * Markér kolonnen **Indirect Goods & Services**.

      Salg og marketing er langt den største udgift samlet set i denne kategori.
   * Vælg **Mexico** på kortet igen.

      Den største udgift i denne kategori i Mexico er Maintenance & Repair.

      ![](media/sample-procurement/pbi_procsample_drill_mexico.png)
3. Vælg pil op i det øverste venstre hjørne af diagrammet for at få vist en detaljeudledning.
4. Vælg pilen igen for at deaktivere detaljeudledning.  
5. Vælg **Power BI** i navigationslinjen øverst for at vende tilbage til dit arbejdsområde.

## <a name="evaluate-different-cities"></a>Evaluer forskellige byer
Vi kan bruge markering til at evaluere forskellige byer.

1. Vælg dashboardfeltet **Total Invoice, Discount % By Month**. Rapporten åbner på siden "Discount Analysis".
2. Vælg de forskellige byer i træstrukturen **Total Invoice by City** for at se, hvordan de sammenlignes. Næsten alle Miamis fakturaer er fra leverandører på niveau 1.

   ![](media/sample-procurement/pbi_procsample_miamitreemap2.png)

## <a name="vendor-discounts"></a>Leverandørrabatter
Lad os også udforske rabatter, der er tilgængelige fra leverandører, og de tidsperioder, hvor vi får flest rabatter.

![](media/sample-procurement/procurement4.png)

Specifikt disse spørgsmål:

* Er rabatter forskellige fra måned til måned, eller er rabatter de samme hver måned?
* Får nogle byer flere rabatter end andre?

### <a name="discount-by-month"></a>Rabat pr. måned
På kombinationsdiagrammet **Total Invoice and Discount % by Month** kan vi se, at **February** er den travleste måned, og **September** er den mindst travle måned. Se nu på rabatprocenten i løbet af disse måneder.
Bemærk, at når mængden går op, falder rabatten, og når mængden er lav, går rabatten op. Jo større brug vi har for rabatten, desto dårligere handel får vi.

![](media/sample-procurement/procurement5.png)

### <a name="discount-by-city"></a>Rabat efter by
Et andet område at udforske er rabat efter by. Vælg alle byerne i træstrukturen, og se, hvordan de andre diagrammer ændrer sig.

* St. Louis, MO havde en stor stigning i samlet faktura i februar og et stort fald i rabatbesparelser i april.
* Mexico City, Mexico har den højeste rabatprocent (11,05 %), og Atlanta, GA har den mindste (0,08 %).

![](media/sample-procurement/procurement6.png)

### <a name="edit-the-report"></a>Rediger rapporten
Vælg **Rediger rapport** i det øverste venstre hjørne, og udforsk Redigeringsvisning.

* Se, hvordan siderne laves
* Tilføj sider og diagrammer baseret på de samme data
* Skift visualiseringstypen for et diagram – skift f.eks. træstrukturen til et kransediagram
* Fastgør dem til dit dashboard

Dette er et sikkert miljø at lege i. Du kan altid vælge ikke at gemme dine ændringer. Hvis du gemme dem, kan du altid gå til **Hent data** for at få en ny kopi af dette eksempel.

## <a name="next-steps-connect-to-your-data"></a>Næste trin: Opret forbindelse til dine data
Vi håber, at denne rundtur viser, hvordan Power BI-dashboards og -rapporter kan give indsigt i indkøbsdata. Nu er det din tur &#151; opret forbindelse til dine egne data. Med Power BI kan du oprette forbindelse til en lang række datakilder. Få mere at vide om, hvordan du [kommer i gang med Power BI](service-get-started.md).
