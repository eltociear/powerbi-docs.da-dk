---
title: Brug sikkerhed på rækkeniveau med integreret Power BI-indhold
description: Få mere at vide om, hvordan du integrerer Power BI-indhold i dit program.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/22/2018
ms.author: maghan
ms.openlocfilehash: 218f4cd0aaaa5ffc8cab3a06b06af9544b02143d
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
---
# <a name="use-row-level-security-with-power-bi-embedded-content"></a>Brug sikkerhed på rækkeniveau med integreret Power BI-indhold
Sikkerhed på rækkeniveau (Row Level Security eller RLS) kan bruges til at begrænse brugeradgang til data i dashboards, felter, rapporter og datasæt. Flere forskellige brugere kan arbejde med de samme artefakter og stadig få vist forskellige data. Integrering understøtter RLS.

Du bør læse denne artikel, hvis du integrerer for brugere, der ikke anvender Power Bi (appen ejer dataene), hvilket er typisk ved et Independent Software Vendor-scenarie (ISV). Du skal konfigurere integreringstokenet for at tage højde for brugeren og rollen. Læs nedenfor, hvordan du gør.

Hvis du integrerer til Power BI-brugere (brugeren ejer dataene) i din organisation, fungerer sikkerhed på rækkeniveau på samme måde, som det gør direkte i Power BI-tjenesten. Der er ikke mere, du skal gøre i dit program. Du kan finde flere oplysninger i [Sikkerhed på rækkeniveau med Power BI](../service-admin-rls.md).

![Vigtige elementer i forbindelse med sikkerhed på rækkeniveau.](media/embedded-row-level-security/powerbi-embedded-rls-components.png)

Hvis du vil benytte sikkerhed på rækkeniveau, er der tre vigtige begreber, du skal kende: brugere, roller og regler. Lad os se nærmere på dem:

**Brugere** – slutbrugere, der får vist artefakten (dashboardet, feltet, rapporten eller datasættet). I Power BI Embedded identificeres brugerne ved hjælp af egenskaben username i et integreringstoken.

**Roller** – brugerne tilhører roller. En rolle er en objektbeholder til regler og kan have navne i stil med *Sales Manager* eller *Sales Rep*. Du opretter roller i Power BI Desktop. Du kan finde flere oplysninger i [Sikkerhed på rækkeniveau med Power BI Desktop](../desktop-rls.md).

**Regler** – rollerne har regler, og reglerne er de faktiske filtre, der anvendes på dataene. Det kunne f.eks. være noget så simpelt som “Country = USA” eller noget, der er meget mere dynamisk.
I resten af denne artikel giver vi et eksempel på, hvordan du opretter sikkerhed på rækkeniveau og derefter bruger det i et integreret program. Vi bruger PBIX-filen [Retail Analysis Sample](http://go.microsoft.com/fwlink/?LinkID=780547) i eksemplet.

![Eksempel på rapport](media/embedded-row-level-security/powerbi-embedded-report-example.png)

## <a name="adding-roles-with-power-bi-desktop"></a>Tilføj roller med Power BI Desktop
I eksemplet Retail Analysis vises salgstallene for alle butikkerne i en detailkæde. Uden sikkerhed på rækkeniveau får områdecheferne vist de samme data, når de logger på og åbner rapporten. Den øverste ledelse har besluttet, at de enkelte områdechefer kun skal kunne se salgstallene for de butikker, som de styrer. Det kan sikkerhed på rækkeniveau bruges til.

Sikkerhed på rækkeniveau oprettes i Power BI Desktop. Når datasættet og rapporten åbnes, kan vi skifte til diagramvisning for at se skemaet:

![Diagramvisning i Power BI Desktop](media/embedded-row-level-security/powerbi-embedded-schema.png)

Her er nogle ting, du bør bemærke i dette skema:

* Alle mål, f.eks. **Total Sales**, gemmes i faktatabellen **Sales**.
* Der er fire andre relaterede tabeller med mål: **Item**, **Time**, **Store** og **District**.
* Pilene på relationslinjerne angiver, hvilken vej filtrene kan gå fra en tabel til en anden. Hvis der f.eks. filtreres på **Time[Date]**, vil det kun være værdierne fra tabellen **Sales**, der medtages i det aktuelle skema. Ingen andre tabeller vil blive påvirket af dette filter, da alle pilene på relationslinjerne peger mod tabellen Sales og ikke væk fra den.
* Tabellen **District** angiver, hvem der er chef for hvert område:
  
    ![Rækker i tabellen Disctrict](media/embedded-row-level-security/powerbi-embedded-district-table.png)

Hvis vi ud fra dette skema anvender et filter på kolonnen **District Manager** i tabellen **District**, og hvis filteret stemmer overens med den bruger, der får vist rapporten, vil filteret også vise værdierne fra tabellerne **Store** og **Sales**, så det kun er data for den områdechef, der vises.

Sådan gør du:

1. Vælg **Administrer roller** under fanen **Udformning**.
   
    ![Fanen Udformning i Power BI Desktop](media/embedded-row-level-security/powerbi-embedded-manage-roles.png)
2. Opret en ny rolle, der kaldes **Manager**.
   
    ![Opret en ny rolle](media/embedded-row-level-security/powerbi-embedded-new-role.png)
3. Angiv DAX-udtrykket **[District Manager] = USERNAME()** i tabellen **District**.
   
    ![DAX-udtryk til regel for sikkerhed på rækkeniveau](media/embedded-row-level-security/powerbi-embedded-new-role-dax.png)
4. Du kan kontrollere, at reglen virker, ved at vælge **Vis som roller** under fanen **Udformning** og derefter vælge både rollen **Chef**, som du lige har oprettet, og rollen **Anden bruger**. Angiv **Andrew Ma** som bruger.
   
    ![Dialogboksen Vis som roller](media/embedded-row-level-security/powerbi-embedded-new-role-view.png)
   
    De data, der nu bliver vist i rapporten, er dem, som bliver vist, når du logger på som **Andrew Ma**.

Når du anvender filteret på den måde, som vi gjorde her, vil det vise alle de relevante værdier fra tabellerne **District**, **Store** og **Sales**. Men på grund af filtreringsretningen for relationen mellem tabellerne **Sales** og **Time**, vil værdierne fra tabellerne **Sales** og **Item** og **Item** og **Time** ikke blive vist. Du kan få mere at vide om tovejskrydsfiltrering ved at downloade hvidbogen [Bidirectional cross-filtering in SQL Server Analysis Services 2016 and Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx).

## <a name="applying-user-and-role-to-an-embed-token"></a>Anvend bruger og rolle for at integrere et token
Nu hvor du har konfigureret roller i Power BI Desktop, er der nogle opgaver, du skal udføre i dit program, så du kan udnytte rollerne.

Brugerne godkendes af dit program, og integreringstokens bruges til at give en bruger adgang til en bestemt rapport i Power BI Embedded. Der findes ingen specifikke oplysninger om, hvem brugeren er, i Power BI Embedded. Hvis sikkerhed på rækkeniveau skal fungere, skal du overføre ekstra kontekst som en del af dit integreringstoken i form af identiteter. Det gør du ved hjælp af [GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx)-API'en.

[GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx)-API'en accepterer en liste over identiteter med angivelse af de relevante datasæt. Hvis sikkerhed på rækkeniveau skal fungere, skal du overføre følgende som en del af identiteten.

* **username (obligatorisk)** – dette er en streng, der kan bruges til at identificere brugeren, når reglerne for sikkerhed på rækkeniveau anvendes. Du kan kun angive én enkelt bruger.
* **roles (obligatorisk)** – en streng med de roller, der skal vælges, når reglerne for sikkerhed på rækkeniveau anvendes. Hvis du overfører mere end én rolle, skal de overføres som en strengmatrix.
* **dataset (obligatorisk)** – det datasæt, der gælder for det artefakt, du integrerer. 

Du kan oprette integreringstokenet ved hjælp af metoden **GenerateTokenInGroup** på **PowerBIClient.Reports**. 

Du kan f.eks. ændre eksemplet [PowerBIEmbedded_AppOwnsData](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data). *Home\HomeController.cs line 76 and 77* kunne opdateres fra:

```
// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync(GroupId, report.Id, generateTokenRequestParameters);
```

til

```
var generateTokenRequestParameters = new GenerateTokenRequest("View", null, identities: new List<EffectiveIdentity> { new EffectiveIdentity(username: "username", roles: new List<string> { "roleA", "roleB" }, datasets: new List<string> { "datasetId" }) });

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync("groupId", "reportId", generateTokenRequestParameters);
```

Hvis du kalder REST-API'en, accepterer den opdaterede API nu en ekstra JSON-matrix med navnet **identities**, der indeholder et brugernavn, en liste over strengroller og en liste over strengdatasæt, f.eks.:

```
{
    "accessLevel": "View",
    "identities": [
        {
            "username": "EffectiveIdentity",
            "roles": [ "Role1", "Role2" ],
            "datasets": [ "fe0a1aeb-f6a4-4b27-a2d3-b5df3bb28bdc" ]
        }
    ]
}
```

Nu hvor alle delene er samlet, vil brugerne kun få vist de data, de har tilladelse til at få vist ifølge sikkerheden på rækkeniveau, når de logger på programmet for at få vist dette artefakt.

## <a name="working-with-analysis-services-live-connections"></a>Arbejde med Analysis Services-liveforbindelser
Sikkerhed på rækkeniveau kan bruges med Analysis Services-liveforbindelser for lokale servere. Der er nogle specifikke begreber, du bør kende, når du bruger denne type forbindelse.

Den faktiske identitet, der leveres for egenskaben brugernavn, skal være en Windows-bruger med tilladelser til Analysis Services-serveren.

**Konfigurer en datagateway i det lokale miljø**

En [datagateway i det lokale miljø](../service-gateway-onprem.md) bruges, når du arbejder med Analysis Services-liveforbindelser. Når du genererer et integreringstoken med et id angivet, skal den overordnede konto være angivet som en administrator af gatewayen. Hvis den overordnede konto ikke er angivet, vil sikkerhed på rækkeniveau ikke blive anvendt på egenskaben for dataene. En bruger uden administrative rettigheder kan levere roller, men skal angive sit eget brugernavn til den eksisterende identitet.

**Brug af roller**

Roller kan angives med identiteten i et integreringstoken. Hvis der ikke angives nogen rolle, vil det brugernavn, der blev angivet, blive brugt til at løse de tilknyttede roller.

**Brug af funktionen CustomData**

Funktionen CustomData gør det muligt at fortolke fritekst (streng) vha. egenskaben CustomData for forbindelsesstrengen, en værdi, der skal bruges af AS (via funktionen CUSTOMDATA()).
Du kan bruge denne som en alternativ måde at tilpasse dataforbrug på.
Du kan bruge den i rollen DAX-forespørgsel, og du kan bruge den uden en rolle i en DAX-målingsforespørgsel.
Funktionen CustomData er en del af vores tokengenerations funktionalitet for følgende artefakter: dashboard, rapport og felt. Dashboards kan have flere CustomData-identiteter (én pr. felt/model).

> [!NOTE]
> Funktionen CustomData fungerer kun for modeller, der findes i Azure Analysis Services, og den fungerer kun i livetilstand. Til forskel fra brugere og roller, kan datafunktionen ikke angives i en .pbix-fil. Når et token genereres med den brugerdefinerede datafunktion, skal du have et brugernavn.
>
>

**CustomData SDK-tilføjelser**

Strengegenskaben CustomData blev føjet til vores effektive identitet i tokengenerationsscenariet.
        
        [JsonProperty(PropertyName = "customData")]
        public string CustomData { get; set; }

Identiteten kan oprettes med brugerdefinerede data vha. følgende kald:

        public EffectiveIdentity(string username, IList<string> datasets, IList<string> roles = null, string customData = null);

**CustomData SDK-forbrug**

Hvis du kalder REST-API'en, kan du tilføje brugerdefinerede data i hver enkelt identitet, f.eks.:

```
{
    "accessLevel": "View",
    "identities": [
        {
            "username": "EffectiveIdentity",
            "roles": [ "Role1", "Role2" ],
            "customData": "MyCustomData",
            "datasets": [ "fe0a1aeb-f6a4-4b27-a2d3-b5df3bb28bdc" ]
        }
    ]
}
```

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger
* Tildeling af brugere til roller i Power BI-tjenesten påvirker ikke sikkerheden på rækkeniveau, når du bruger et integreringstoken.
* Selvom Power BI-tjenesten ikke anvender indstillingen for sikkerhed på rækkeniveau på administratorer eller medlemmer med redigeringsrettigheder, vil den blive anvendt på dataene, når du angiver en identitet med et integreringstoken.
* Analysis Services-liveforbindelser understøttes på lokale servere.
* Liveforbindelser i Azure Analysis Services understøtter filtrering efter roller, men er ikke dynamisk efter brugernavn.
* Hvis der ikke skal bruges sikkerhed på rækkeniveau på det underliggende datasæt, må GenerateToken-anmodningen **ikke** indeholde en eksisterende identitet.
* Hvis det underliggende datasæt er en cloudmodel (cachelagret model eller DirectQuery), skal den eksisterende identitet indeholde mindst én rolle, eller vil der ikke blive tildelt en rolle.
* En liste over identiteter gør det muligt at have flere identitetstokens ved integrering i dashboardet. For alle andre artefakter vil listen indeholde en enkelt identitet.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)