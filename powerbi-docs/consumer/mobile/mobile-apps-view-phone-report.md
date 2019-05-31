---
title: Få vist Power BI-rapporter, der er optimeret til din telefon
description: Læs om, hvordan du kan interagere med rapportsider, der er optimeret til visning i Power BI-telefonapps.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/22/2019
ms.author: mshenhav
ms.openlocfilehash: 79ca47f83bb39ab9d6df141b5a26dcb54e00c72c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100956"
---
# <a name="view-power-bi-reports-optimized-for-your-phone"></a>Få vist Power BI-rapporter, der er optimeret til din telefon

Gælder for:

| ![iPhone](./media/mobile-apps-view-phone-report/ios-logo-40-px.png) | ![Android-telefon](./media/mobile-apps-view-phone-report/android-logo-40-px.png) |
|:--- |:--- |
| iPhone-telefoner |Android-telefoner |

Når du får vist en rapport i Power BI på din telefon, kontrollerer Power BI for at se, hvis rapporten er blevet optimeret til telefoner. Hvis det er tilfældet, åbner Power BI automatisk den optimerede rapport i stående format.

![Rapport i stående format](./media/mobile-apps-view-phone-report/07-power-bi-phone-report-portrait.png)

Hvis der ikke findes en rapport, der er optimeret til telefoner, bliver rapporten stadig åbnet, men den åbnes i liggende format uden optimering til telefoner. Hvis du vender telefonen sidelæns, når du har åbnet en rapport, der er optimeret til telefoner, åbnes rapporten med det oprindelige rapportlayout uden optimering. Hvis det kun er nogle af siderne, der er optimeret, vises der en meddelelse i stående format om, at rapporten er tilgængelig i liggende format.

![Rapportside, der ikke er optimeret](./media/mobile-apps-view-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Alle andre funktioner i Power BI-rapporterne kan stadig bruges i de rapporter, der er optimeret til telefoner. Få mere at vide om, hvad du kan gøre i:

* [Rapporter på iPhone-telefoner](mobile-reports-in-the-mobile-apps.md). 
* [Rapporter på Android-telefoner](mobile-reports-in-the-mobile-apps.md).

## <a name="filter-the-report-page-on-a-phone"></a>Filtrer rapportsiden på en telefon
Hvis der er defineret filtre i en rapport, der er optimeret til telefoner, kan du bruge filtrene, når du får vist rapporten på en telefon. Rapporten åbnes på din telefon filtreret efter de værdier, der filtreres efter i rapporten på internettet. Du får vist en meddelelse om, at der er aktive filtre på siden. Du kan ændre filtrene på telefonen.

1. Tryk på filterikonet ![Telefonfilterikon](./media/mobile-apps-view-phone-report/power-bi-phone-filter-icon.png) nederst på siden. 
2. Brug grundlæggende eller avanceret filtrering for at få vist de resultater, du er interesseret i.
   
    ![Avanceret filter i Power BI-telefonrapport](./media/mobile-apps-view-phone-report/power-bi-iphone-advanced-filter-toronto.gif)

## <a name="cross-highlight-visuals"></a>Tværgående fremhævning i visualiseringer
Tværgående fremhævning af visuelle elementer i stående fungerer visning på samme måde det i Power BI-tjenesten og på telefoner i liggende format: Når du vælger data i en visualisering, fremhæves relaterede data i de andre visualiseringer på siden.

Læs mere om [filtre og fremhævning i Power BI](../../power-bi-reports-filters-and-highlighting.md).

## <a name="select-visuals"></a>Vælg visualiseringer
Når du vælger en visualisering i en rapport på en telefon, fremhæves visualiseringen, og der fokuseres på den, så du ikke kan bruge fingerbevægelser på dit canvas.

Når du har valgt en visualisering kan du bladre i visualiseringen. Hvis du vil fravælge en visualisering, skal du trykke et sted uden for visualiseringen.

## <a name="open-visuals-in-focus-mode"></a>Åbn visualisering i Fokustilstand
Telefonrapporter tilbyder også en fokustilstand: Du få en større visning af en enkelt visualisering og udforske det nemmere.

* Tryk på de tre prikker ( **...** ) i øverste højre hjørne af en visualisering i en rapport på telefonen, og vælg **Udvid til fokustilstand**.
  
    ![Udvid til fokustilstand](././media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)

Hvad du skal gøre i fokustilstand påvirker på dit rapportcanvas og omvendt. F.eks, hvis du fremhæver en værdi i et visuelt element og derefter vende tilbage til hele rapporten, er rapporten filtreret til den værdi, du fremhævede i Visualiseringen.

Nogle handlinger kan kun udføres i Fokustilstand på grund af den begrænsede skærmstørrelse:

* **Brug detailudledning** for at få vist flere oplysninger i en visualisering. Læs mere om [at få vist oplysninger på forskellige niveauer](mobile-apps-view-phone-report.md#drill-down-in-a-visual) i en rapport på en telefon herunder.
* **Sortér** værdierne i visualiseringen.
* **Tilbagefør**: Ryd de trin, du har udført i visualiseringen, og gå tilbage til den definition, der var angivet ved oprettelse af rapporten.
  
    Hvis du vil rydde alle ændringerne fra en visualisering, skal du trykke på de tre prikker ( **...** ) > **Tilbagefør**.
  
    ![Vend tilbage](././media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)
  
    Gendan er tilgængelige på rapportniveau, ryddes dine ændringer fra alle visualiseringer, eller på visualiseringsniveau, ryddes dine ændringer i den valgte visualisering.   

## <a name="drill-down-in-a-visual"></a>Detailudledning i en visualisering
Hvis der er defineret hierarkiniveauer i en visualisering, kan du dykke ned i de mere detaljerede oplysninger, som vises i en visualisering, og derefter gå opad i hierarkiet igen. Du kan [tilføje detailudledning i en visualisering](../end-user-drill.md) i enten Power BI-tjenesten eller i Power BI Desktop.

Der er nogle typer detailudledning:

### <a name="drill-down-on-a-value"></a>Analysér ned på en værdi
1. Tryk længe (Tryk på og hold) på et datapunkt i et visuelt element.
2. Værktøjstip vises, og hvis hierarki er defineret, derefter værktøjstip sidefoden vises analysér ned og pil op.
3. Tryk på pil ned for detailudledning

    ![Tryk på en detailudledning](././media/mobile-apps-view-phone-report/report-drill-down.png)
    
4. Tryk på pil op for færre detaljer.

### <a name="drill-to-next-level"></a>Analysér til næste niveau
1. Tryk på de tre prikker ( **...** ) i øverste højre hjørne i en rapport på telefonen, og vælg **Udvid til fokustilstand**.
   
    ![Udvid til fokustilstand](././media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)
   
    I dette eksempel viser søjlerne de aktuelle værdier for stater.
2. Tryk på udforskningsikonet ![Ikonet Udforsk](./media/mobile-apps-view-phone-report/power-bi-phone-report-explore-icon.png) nederst til venstre.
   
    ![Tilstanden Udforsk](./media/mobile-apps-view-phone-report/power-bi-phone-report-explore-mode.png)
3. Tryk på **Vis næste niveau** eller **Udvid til næste niveau**.
   
    ![Udvid til næste niveau](./media/mobile-apps-view-phone-report/power-bi-phone-report-expand-levels.png)
   
    Nu viser søjlerne værdierne for byer.
   
    ![Udvidede niveauer](./media/mobile-apps-view-phone-report/power-bi-phone-report-expanded-levels.png)
4. Hvis du trykker på pilen i øverste venstre hjørne, kommer du tilbage til telefonrapporten med værdierne udvidet til det nederste niveau.
   
    ![Stadig udvidet til nederste niveau](./media/mobile-apps-view-phone-report/power-bi-back-to-phone-report-expanded-levels.png)
5. Hvis du vil tilbage til det oprindelige niveau, skal du trykke på de tre prikker ( **...** ) igen og vælge **Tilbagefør**.
   
    ![Vend tilbage](././media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)

## <a name="drill-through-from-a-value"></a>Få detaljeadgang fra en værdi
Detaljeadgang forbinder værdier i én rapportside, med andre rapportsider. Når du analyserer via fra et datapunkt på en anden rapportside, datapunktværdier bruges til at filtrere den dykket via siden, eller den vil være inden for rammerne af de valgte data.
Forfattere kan [definere detaljeadgang](https://docs.microsoft.com/power-bi/desktop-drillthrough) når de opretter rapporten.

1. Tryk længe (Tryk på og hold) på et datapunkt i et visuelt element.
2. Værktøjstip vises, og hvis detaljeadgang er defineret, derefter værktøjstip sidefoden vises pil detaljeadgang.
3. Tryk på pilen for detaljeadgang

    ![Tryk på detaljeadgang](././media/mobile-apps-view-phone-report/report-drill-through1.png)

4. Vælg, hvilken rapportside til at gennemgå

    ![Vælg rapportside](././media/mobile-apps-view-phone-report/report-drill-through2.png)

5. Brug knappen Tilbage i headeren app for at gå tilbage til den side, du har startet fra.


## <a name="next-steps"></a>Næste trin
* [Opret rapporter, der er optimeret til Power BI-telefonapps](../../desktop-create-phone-report.md)
* [Opret en telefonvisning af et dashboard i Power BI](../../service-create-dashboard-mobile-phone-view.md)
* [Opret dynamiske visualiseringer, der er optimeret til alle størrelser](../../visuals/desktop-create-responsive-visuals.md)
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

