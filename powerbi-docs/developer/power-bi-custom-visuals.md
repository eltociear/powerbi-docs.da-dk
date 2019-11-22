---
title: Visualiseringer i Power BI
description: Brugerdefinerede visualiseringer i Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: a45566d6fe9f4833ebed91e7c10656a8ca1c6961
ms.sourcegitcommit: 08b73af260ded51daaa6749338cb85db2eab587f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/15/2019
ms.locfileid: "74102059"
---
# <a name="visuals-in-power-bi"></a>Visualiseringer i Power BI

Når du opretter eller redigerer en Power BI-rapport, kan du bruge mange forskellige typer visualiseringer. Ikonerne for disse visualiseringer vises i ruden **Visualiseringer**. Disse visualiseringer er pakke på forhånd, når du downloader [Power BI Desktop](https://powerbi.microsoft.com/desktop/) eller åbner [Power BI-tjenesten](https://app.powerbi.com).

![visualiseringer](media/power-bi-custom-visuals/power-bi-visualizations.png)

Du er dog ikke begrænset til dette sæt visualiseringer. Hvis du vælger **Flere indstillinger** (...) nederst, bliver en anden kilde til rapportvisualiseringer tilgængelig – *Power BI-visuals*.

Udviklere opretter Power BI-visualiseringer ved hjælp af SDK'er til Power BI-visualiseringer. Disse visualiseringer giver virksomhedsbrugere mulighed for at se deres data på en måde, som passer bedst til deres virksomhed. Forfattere af rapporter kan derefter importere de brugerdefinerede visualiseringsfiler til deres rapporter og bruge dem som en hvilken som helst anden Power BI-visualisering. Power BI-visualiseringer er førsteklasses komponenter i Power BI, og de kan filtreres, fremhæves, redigeres, deles osv.

Power BI-visualiseringer udrulles på tre måder:

* Brugerdefinerede visualiseringsfiler
* Visualiseringer til organisationen
* Visualiseringer på markedspladser

## <a name="custom-visual-files"></a>Brugerdefinerede visualiseringsfiler

Power BI-visualiseringer er pakker, der indeholder kode til gengivelse af de data, de fodres med. Alle kan oprette en brugerdefineret visualisering og pakke den som en enkelt `.pbiviz`-fil, som derefter kan importeres i en Power BI-rapport.

> [!WARNING]
> En brugerdefineret visualisering kan indeholde kode, der kan udgøre en risiko for sikkerheden eller beskyttelsen af personlige oplysninger. Vær sikker på, at du har tillid til forfatteren og kilden til den brugerdefinerede visualisering, før du importerer den i din rapport.

## <a name="organizational-visuals"></a>Visualiseringer til organisationen

Power BI-administratorer godkender og udruller Power BI-visualiseringer i deres organisation, som forfattere af rapporter nemt kan finde, opdatere og bruge. Administratorer kan nemt administrere (f.eks. opdatere version, deaktivere/aktivere) disse visualiseringer.

 [Læs mere om visualiseringer til organisationer](power-bi-custom-visuals-organization.md).

## <a name="marketplace-visuals"></a>Visualiseringer på markedspladser

Det er både medlemmer af community'et og Microsoft, der har bidraget med deres Power BI-visualiseringer til offentlig brug og publiceret dem på [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals)-markedspladsen. Du kan downloade disse visualiseringer og føje dem til dine Power BI-rapporter. Microsoft har testet og godkendt disse Power BI-visualiseringer i forhold til funktionalitet og kvalitet.

Hvad er [AppSource](office-store.md)? Det er det sted, du finder apps, tilføjelsesprogrammer og udvidelser til din Microsoft-software. AppSource forbinder millioner af brugere af produkter som Office 365, Azure, Dynamics 365, Cortana og Power BI med løsninger, der kan hjælpe dem med at arbejde mere effektivt, med større indsigt og smukkere end før.

### <a name="certified-visuals"></a>Certificerede visualiseringer

Certificerede Power BI-visualiseringer er visualiseringer på markedspladser, der har bestået yderligere strenge kvalitetstest, og understøttes i yderligere scenarier, f.eks. [mailabonnementer](../service-report-subscribe.md) og [eksport til PowerPoint](../consumer/end-user-powerpoint.md).
Hvis du vil se en liste over certificerede Power BI-visualiseringer eller indsende dine egne, skal du se [Certificerede Power BI-visualiseringer](power-bi-custom-visuals-certified.md).

Er du webudvikler og interesseret i at oprette dine egne visualiseringer og føje dem til AppSource? Se under [Udvikling af en brugerdefineret visualisering i Power BI](visuals/custom-visual-develop-tutorial.md), og få mere at vide om, hvordan du [publicerer brugerdefinerede visualiseringer i AppSource](office-store.md).

### <a name="import-a-custom-visual-from-a-file"></a>Importér en brugerdefineret visualisering fra en fil

1. Vælg ellipsen på knappen i ruden **Visualiseringer**.

    ![visualiseringer2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Vælg **Importér fra fil** på rullelisten.

    ![importér fra fil](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. I filmenuen **Åbn** skal du vælge den `.pbiviz`-fil, du vil importere, og derefter vælge **Åbn**. Ikonet for den brugerdefinerede visualisering tilføjes nederst i ruden **Visualiseringer** og kan nu bruges i din rapport.

    ![Importeret fra cv](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organizational-visuals"></a>Importér visualiseringer til organisationen

1. Vælg ellipsen på knappen i ruden **Visualiseringer**.

    ![Visualisering org 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. Vælg **Importér fra markedsplads** på rullelisten.

    ![Visualisering org 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Vælg **MIN ORGANISATION** i øverste fanemenu.

    ![Visualisering org 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. Rul gennem listen for at finde den visualisering, du vil importere.

    ![Visualisering org 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. Vælg **Tilføj** for at importere den brugerdefinerede visualisering. Ikonet for den brugerdefinerede visualisering tilføjes nederst i ruden **Visualiseringer** og kan nu bruges i din rapport.

    ![Visualisering org 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-power-bi-visuals-from-microsoft-appsource"></a>Download eller importér Power BI-visualiseringer fra Microsoft AppSource

Du har to muligheder for at downloade og importere Power BI-visualiseringer: fra Power BI og fra [AppSource-webstedet](https://appsource.microsoft.com/).

### <a name="import-power-bi-visuals-from-within-power-bi"></a>Importér Power BI-visualiseringer fra Power BI

1. Vælg ellipsen på knappen i ruden **Visualiseringer**.

    ![visualiseringer 2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Vælg **Importér fra markedsplads** på rullelisten.

    ![Visualisering org 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Rul gennem listen for at finde den visualisering, du vil importere.

    ![importér visualisering](media/power-bi-custom-visuals/power-bi-import-visual.png)

4. Du kan få mere at vide om en af visualiseringerne, hvis du fremhæver og vælger den.

    ![Markér](media/power-bi-custom-visuals/power-bi-select.png)

5. På siden med oplysninger kan du se skærmbilleder, videoer, en detaljeret beskrivelse med mere.

    ![Synoptic](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. Rul ned til bunden for at se anmeldelser.

    ![Anmeldelser](media/power-bi-custom-visuals/power-bi-reviews.png)

7. Vælg **Tilføj** for at importere den brugerdefinerede visualisering. Ikonet for den brugerdefinerede visualisering tilføjes nederst i ruden **Visualiseringer** og kan nu bruges i din rapport.

    ![visualisering er importeret](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-power-bi-visuals-from-microsoft-appsource"></a>Download og importér Power BI-visualiseringer fra Microsoft AppSource

1. Start med [Microsoft AppSource](https://appsource.microsoft.com), og vælg fanen for **Apps**.

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. Gå til [siden med appresultater](https://appsource.microsoft.com/marketplace/apps), hvor du kan få vist de mest populære apps i hver kategori, herunder *Power BI-apps*. Vi leder efter Power BI-visuals, så lad os vælge **Power BI-visualiseringer** på listen i navigationsruden for at indsnævre resultaterne.

    ![AppSource-visualiseringer](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource viser et felt for hver brugerdefinerede visualisering.  Hvert felt har et snapshot af den brugerdefinerede visualisering med en kort beskrivelse og et downloadlink. Vælg feltet for at få vist flere detaljer.

    ![Valgt brugerdefineret visualisering](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. På siden med oplysninger kan du se skærmbilleder, videoer, en detaljeret beskrivelse med mere. Vælg **Hent det nu** for at downloade den brugerdefinerede visualisering, og acceptér derefter Vilkår for anvendelse.

    ![Hent AppSource](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. Vælg linket for at downloade den brugerdefinerede visualisering.

    ![Download](media/power-bi-custom-visuals/powerbi-custom-download.png)

    Downloadsiden indeholder også instruktioner til, hvordan du importerer den brugerdefinerede visualisering i Power BI Desktop og Power BI-tjenesten.

    Du kan også downloade et eksempel på en rapport, der indeholder den brugerdefinerede visual og viser dets egenskaber.

    ![Eksempel](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. Gem `.pbiviz`-filen, og åbn derefter Power BI.

7. Importér `.pbiviz`-filen i din rapport. Se afsnittet [Importér en brugerdefineret visualisering fra en fil](#import-a-custom-visual-from-a-file) ovenfor.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

* En brugerdefineret visualisering føjes til en bestemt rapport, når den importeres. Hvis du vil bruge visualiseringen i en anden rapport, skal du også importere den i denne rapport. Når du gemmer en rapport med en brugerdefineret visualisering vha. indstillingen **Gem som**, gemmes der en kopi af den brugerdefinerede visualisering sammen med den nye rapport.

* Hvis du ikke kan se ruden **Visualiseringer**, betyder det, at du ikke har redigeringstilladelser til rapporten.  Du kan kun føje Power BI-visualiseringer til rapporter, som du kan redigere, og ikke til rapporter, der kun er blevet delt med dig.

## <a name="troubleshoot"></a>Fejlfind

Hvis du skal foretage fejlfinding, skal du se [Fejlfinding af dine Power BI-visualiseringer](power-bi-custom-visuals-troubleshoot.md).

## <a name="faq"></a>Ofte stillede spørgsmål

Du kan finde flere oplysninger og få svar på spørgsmål under [Ofte stillede spørgsmål om Power BI-visualiseringer](power-bi-custom-visuals-faq.md#organizational-visuals).

## <a name="next-steps"></a>Næste trin

* [Visualiseringer i Power BI-rapporter](../visuals/power-bi-report-visualizations.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/).
