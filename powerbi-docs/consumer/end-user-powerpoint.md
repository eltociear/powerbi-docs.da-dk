---
title: Eksportér rapporter fra Power BI til PowerPoint
description: Se, hvordan du kan eksportere en Power BI-rapport til PowerPoint.
author: mihart
manager: kvivek
ms.custom: seodec18
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 02/28/2019
ms.author: mihart
LocalizationGroup: Share your work
ms.openlocfilehash: f06b67dc0072c125d9430079fa756d963fd99f23
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/16/2019
ms.locfileid: "61063628"
---
# <a name="export-reports-from-power-bi-to-powerpoint"></a>Eksportér rapporter fra Power BI til PowerPoint
Med Power BI kan du publicere din rapport i **Microsoft PowerPoint** og nemt oprette et slidesæt ud fra din Power BI-rapport. Når du **eksporterer til PowerPoint**, sker der følgende:

* Hver side i Power BI-rapporten bliver til et enkeltslide i PowerPoint
* Hver side i Power BI-rapporten eksporteres som et enkelt billede med høj opløsning i PowerPoint
<!-- * The filters and slicers settings that you added to the report are preserved. -->
* Der oprettes et link i PowerPoint, som er en kæde til Power BI-rapporten 

Du kan hurtigt eksportere din **Power BI-rapport** til **PowerPoint**. Du skal blot følge de trin, der er beskrevet i det næste afsnit.

## <a name="how-to-export-your-power-bi-report-to-powerpoint"></a>Sådan eksporterer du en Power BI-rapport til PowerPoint
Vælg en rapport for at vise den på lærredet i Power BI-tjenesten. Du kan også vælge en rapport fra din **startside**, **Apps** eller en hvilken som helst anden sektion i navigationsruden til venstre.

![Vælg Filer på menulinjen – pil, der peger på Eksportér til PowerPoint](media/end-user-powerpoint/power-bi-publish.png)

Når den rapport, du vil eksportere til PowerPoint, vises på lærredet, skal du vælge **Filer > Eksportér til PowerPoint** på menulinjen i Power BI-tjenesten.

![Nærbillede af venstre navigationslinje med Mit arbejdsområde valgt – rullemenuen Filer valgt](media/end-user-powerpoint/powerbi_to_powerpoint_1.png)
   
Der vises et pop op-vindue, hvor du har mulighed for at vælge **Aktuel visning** eller **Standardvisning**.  Med **Aktuel visning** eksporteres rapporten i den aktuelle tilstand, hvilket omfatter de aktive ændringer, du har foretaget i udsnits- og filterværdier.  De fleste brugere vælger denne indstilling.  Alternativt kan du vælge **Standardvisning**, hvor rapporten eksporteres i sin oprindelige tilstand (som forfatteren har delt den), og hvor ændringer, du har foretaget af den oprindelige tilstand, ikke afspejles.
    
Derudover er der et afkrydsningsfelt, hvor du kan markere, om du vil eksportere skjulte faner i en rapport.  Du skal blot markere afkrydsningsfeltet, hvis du kun vil eksportere de rapportfaner, der er synlige for dig i browseren.  Hvis du foretrækker at inkludere alle skjulte faner i din eksport, skal du undlade at markere afkrydsningsfeltet.  Hvis afkrydsningsfeltet er nedtonet, er der ingen skjulte faner i rapporten.  Når du har foretaget dine valg, skal du klikke på **Eksportér** for at fortsætte.

Du får vist et meddelelsesbanner i øverste højre hjørne af Power BI-tjenestens browservindue, hvor der står, at rapporten eksporteres til PowerPoint. Dette kan tage nogle minutter, og du kan fortsætte med at arbejde i Power BI, mens rapporten eksporteres.

![meddelelse om, at eksport til PowerPoint er i gang](media/end-user-powerpoint/powerbi_to_powerpoint_2.png)

Når dette er fuldført, ændres meddelelsesbanneret for at give dig besked om, at Power BI-tjenesten er færdig med eksporten.

![Meddelelse om, at handlingen er fuldført, vises](media/end-user-powerpoint/powerbi_to_powerpoint_3.png)

Derefter finder du din fil der, hvor din browser viser downloadede filer. På det følgende billede vises det som et downloadbanner i bunden af browservinduet.

![pil, der peger på browsermeddelelsen nederst på skærmen](media/end-user-powerpoint/powerbi_to_powerpoint_4.png)

Så nemt er det. Du kan downloade filen, åbne den med PowerPoint og derefter ændre eller forbedre den yderligere, lige som du ville gøre med et hvilket som helst andet PowerPoint-slidesæt.

## <a name="checking-out-your-exported-powerpoint-file"></a>Udtjekning af din eksporterede PowerPoint-fil
Når du åbner den PowerPoint-fil, som Power BI har eksporteret, kan du finde nogle smarte og nyttige elementer. Se følgende billede, og se derefter de nummererede elementer nedenfor, som beskriver nogle af disse smarte funktioner.

![PowerPoint åbnes](media/end-user-powerpoint/powerbi_to_powerpoint_5.png)

1. Den første side i slidesættet indeholder navnet på din rapport og et link, så du kan få den rapport, som slidesættet er baseret på, **vist i Power BI**.
2. Du får også vist nogle nyttige oplysninger om rapporten, herunder den *seneste dataopdatering*, som rapporten er baseret på, og *dato og klokkeslæt for download*, som er det klokkeslæt og den dato, hvor Power BI-rapporten blev eksporteret til en PowerPoint-fil.
3. Hver rapportside er en separat slide, sådan som det er vist i venstre navigationsrude. 
4. Din publicerede rapport er gengivet på det sprog, der er angivet under dine Power BI-indstillinger, og ellers i henhold til indstillingen for landestandard i din browser. Hvis du vil se eller angive dine sprogindstillinger, skal du vælge tandhjulsikonet ![tandhjulsikon](media/end-user-powerpoint/power-bi-settings-icon.png) **> Indstillinger > Generelt > Sprog**. Du kan finde oplysninger om landestandard i [Understøttede sprog og lande/områder til Power BI](../supported-languages-countries-regions.md).
5. PowerPoint-præsentationen indeholder en forsideslide med tidspunktet for eksporten i den korrekte tidszone.

Når du skifter til en bestemt slide, kan du se, at hver rapportside er et uafhængigt billede.

>[!NOTE]
> Det er en ny funktionsmåde at have en visual for hver rapportside. Den tidligere funktionsmåde, som viste et uafhængigt billede for hver visual, implementeres ikke længere. 
 

![Billede, der viser hver enkelt visualisering som et separat billede](media/end-user-powerpoint/powerbi_to_powerpoint_6.png)

Hvad du herefter gør med dit PowerPoint-slidesæt eller nogen af billederne i høj opløsning, er op til dig!

## <a name="limitations"></a>Begrænsninger
Der er nogle få overvejelser og begrænsninger, du skal huske på, når du arbejder med funktionen **Eksportér til PowerPoint**.

* **R-visuals** understøttes ikke i øjeblikket. Sådanne visuals eksporteres som et tomt billede til PowerPoint med en fejlmeddelelse, hvor der står, at den pågældende visual ikke understøttes.
* **Brugerdefinerede visuals**, der er blevet **certificeret**, understøttes. Hvis du vil have flere oplysninger om certificerede brugerdefinerede visuals, herunder hvordan du får en brugerdefineret visual certificeret, skal du se [Sådan får du en brugerdefineret visual certificeret](../power-bi-custom-visuals-certified.md). Brugerdefinerede visuals, som ikke er certificeret, understøttes ikke og eksporteres som tomme billeder til PowerPoint med en fejlmeddelelse om, at den pågældende visual ikke understøttes.
* Rapporter med mere end 30 rapportsider kan ikke eksporteres i øjeblikket.
* Processen med at eksportere rapporten til PowerPoint kan tage nogle minutter at fuldføre, så vær tålmodig. Faktorer, som kan påvirke den tid, det kræver, omfatter rapportens struktur og den aktuelle belastning på Power BI-tjenesten.
* Hvis menuelementet **Eksportér til PowerPoint** ikke er tilgængeligt i Power BI-tjenesten, er det sandsynligvis fordi, din lejeradministrator har deaktiveret funktionen. Kontakt din lejeradministrator for at få flere oplysninger.
* Baggrundsbilleder beskæres med diagrammets omgivende område. Det anbefales, at du fjerner baggrundsbilleder, før du eksporterer til PowerPoint.
* Sider i PowerPoint oprettes altid i 9:16-standardstørrelsen, uanset de oprindelige sidestørrelser eller dimensioner i Power BI-rapporten.
* Rapporter, der ejes af en bruger uden for dit Power BI-lejerdomæne (f.eks. en rapport, der ejes af nogen uden for din organisation og er delt med dig), kan ikke publiceres til PowerPoint.
* Hvis du deler et dashboard med en person uden for din organisation (og dermed en bruger, der ikke er i din Power BI-lejer), kan denne bruger ikke eksportere det delte dashboards tilknyttede rapporter til PowerPoint. Hvis du f.eks. er aaron@contoso.com, kan du dele med david@cohowinery.com. Men david@cohowinery.com kan ikke eksportere de tilknyttede rapporter til PowerPoint.
* Eksport fungerer muligvis ikke med ældre versioner af PowerPoint.
* Hver rapportside eksporteres som tidligere nævnt som et enkelt billede i PowerPoint-filen.
* I Power BI-tjenesten anvendes din Power BI-sprogindstilling for PowerPoint-eksporten. Hvis du vil se eller angive dine sprogindstillinger, skal du vælge tandhjulsikonet ![tandhjulsikon](media/end-user-powerpoint/power-bi-settings-icon.png) **> Indstillinger > Generelt > Sprog**.
* **Downloadtidspunktet** på det forreste slide af den eksporterede PowerPoint-fil svarer til eksporttidspunktet iht. den tidszone, der er angivet på din computer.
* URL-filtre respekteres ikke i øjeblikket, når du vælger "Aktuelle værdier" til din eksport.

## <a name="next-steps"></a>Næste trin
[Udskriv en rapport](end-user-print.md)
