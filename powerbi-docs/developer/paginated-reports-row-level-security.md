---
title: Brug sikkerhed på rækkeniveau med integreret Power BI-indhold
description: Få mere at vide om, hvordan du integrerer Power BI-indhold i din app.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: nishalit
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 11/04/2019
ms.openlocfilehash: f28ffa89647272306dc9cecb5c93928d36805d2a
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880462"
---
# <a name="implementing-row-level-security-in-embedded-paginated-reports-preview"></a>Implementering af sikkerhed på rækkeniveau i integrerede sideinddelte rapporter (prøveversion)

Når du integrerer en sideinddelt rapport, kan du styre, hvilke data der skal vises. Det gør det muligt at skræddersy de viste oplysninger pr. bruger. Hvis du f. eks. har en sideinddelt Power BI-rapport, der omfatter globale salgsresultater, kan du integrere den, så kun salgsresultater fra en bestemt region er tilgængelige.

Denne funktion er en sikker måde at få vist et undersæt af dataene på, så det ikke kompromitterer de øvrige data. Den ligner funktionen [Sikkerhed på rækkeniveau](embedded-row-level-security.md), som er en sikker måde at få vist data på i Power BI-rapporter (der ikke er sideinddelt), dashboards, felter og datasæt.  

> [!Note]
> Denne funktion kan bruges sammen med integration af sideinddelte rapporter for kunder.

## <a name="configuring-a-parameter-to-filter-the-dataset"></a>Konfiguration af en parameter til filtrering af datasættet

Når du anvender sikkerhed på rækkeniveau på en sideinddelt Power BI-rapport, skal du tildele en [parameter](../report-builder-parameters.md) til attributten **UserID**. Denne parameter begrænser de data, der trækkes fra datasættet, før rapporten integreres.

Når du har tildelt parameteren til **UserID**, skal du bruge [Reports GenerateTokenForCreateInGroup](https://docs.microsoft.com/rest/api/power-bi/embedtoken/reports_generatetokenforcreateingroup)-API'en til at hente integreringstokenet.

## <a name="use-uderid-as-a-filter-at-report-or-query-level"></a>Brug UserID som et filter på rapport-eller forespørgselsniveau

Du kan bruge **UserId** som et *filter* eller i en *forespørgsel* til datakilden i [Sideinddelt Report Builder i Power BI](../report-builder-power-bi.md).

### <a name="using-the-filter"></a>Brug af filteret

1. I vinduet **Egenskaber for datasæt** skal du vælge **Filter** i ruden til venstre.

    ![Power BI Report Builder-filter](media/embedded-paginated-reports-secure-data/filter.png)

2. Vælg den parameter, du vil bruge til filtrering af dataene, i rullemenuen **Udtryk**.

     ![Power BI Report Builder-udtryk](media/embedded-paginated-reports-secure-data/expression.png)

3. Klik på funktionsknappen **Værdi**. 

    ![Power BI Report Builder-værdi](media/embedded-paginated-reports-secure-data/function.png)

4. I vinduet **Udtryk** skal du vælge **Indbyggede felter** på listen **Kategori**.

    ![Power BI Report Builder-udtryk](media/embedded-paginated-reports-secure-data/built-in-fields.png)

5. På listen **Element** skal du vælge **UserID** og klikke på **OK**.

    ![Power BI Report Builder-UserID](media/embedded-paginated-reports-secure-data/userid.png)

6. I vinduet **Egenskaber for datasæt** skal du kontrollere, at udtrykket er *din valgte parameter = UserID*, og klikke på **OK**.

    ![Egenskaber for Power BI Report Builder-datasæt](media/embedded-paginated-reports-secure-data/verify.png)

### <a name="using-a-query"></a>Brug af en forespørgsel

1. I vinduet **Egenskaber for datasæt** skal du vælge **Parametre** i ruden til venstre og klikke på **Tilføj**.

    ![Power BI Report Builder-parametre](media/embedded-paginated-reports-secure-data/parameters.png)

2. I **Parameternavn** skal du angive **@UserID** , og i **Parameterværdi** skal du tilføje **[&UserID]** .

    ![Navn på Power BI Report Builder-parameter](media/embedded-paginated-reports-secure-data/parameter-name.png) 

3. I ruden til venstre skal du vælge **Forespørgsel** tilføje parameteren **UserID** i Forespørgsel som en del af din forespørgsel og klikke på **OK**.
    > [!NOTE]
    > I skærmbilledet nedenfor bruges farveparameteren som et eksempel (whereFinalTable. Color = @UserID). Hvis det er nødvendigt, er det muligt at oprette en mere kompleks forespørgsel.

    ![Redigering af Power BI Report Builder-forespørgsler](media/embedded-paginated-reports-secure-data/query-edit.png)

## <a name="passing-the-configured-parameter-using-the-embed-token"></a>Overførsel af den konfigurerede parameter ved hjælp af integreringtokenet

Når du integrerer en sideinddelt rapport til dine kunder, bruges [Reports GenerateTokenForCreateInGroup](https://docs.microsoft.com/rest/api/power-bi/embedtoken/reports_generatetokenforcreateingroup)-API'en til at hente integreringtokenet. Dette token kan også bruges til at filtrere nogle af de data, der trækkes ud af de sideinddelte rapporter.

Hvis du kun vil vise nogle af dataene, skal du tildele feltet `username` med de oplysninger, du vil have vist. Hvis du f. eks. angiver *grøn* i feltet `username` i en sideinddelt rapport, der har en farveparameter, begrænser det integrerede token for eksempel de integrerede data til kun at vise de data, der har værdien *grøn* i farvekolonnen.

```JSON
{
    "accessLevel": "View",
    "reportId": "cfafbeb1-8037-4d0c-896e-a46fb27ff229",
    "identities": [
            {
                    // Replace the 'username' with a paginated report parameter
                    "username":     "...",
                    "reports: [
                        "cfafbeb1-8037-4d0c-896e-a46fb27ff229"
                    ]
            }
    ]
}
```
