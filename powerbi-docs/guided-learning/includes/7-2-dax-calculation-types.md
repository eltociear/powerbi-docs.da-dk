Der er to primære beregninger, som du kan oprette ved hjælp af DAX:

* **beregnede kolonner**
* **beregnede målinger**

Før du begynder at rode med at oprette en af dem, er det fornuftigt at have godt styr på DAX-syntaksen for tabeller og kolonner, som du skal bruge ved oprettelse af enten **beregnede kolonner** eller **beregnede målinger**.

## <a name="dax-table-and-column-name-syntax"></a>Navnesyntaks for DAX-tabeller og -kolonner
Uanset om du opretter en ny kolonne eller måling, er det vigtigt at kende standardformatet for tabelnavne i DAX:

    'Table Name'[ColumnName]

Hvis der mellemrum i tabelnavnet (som vist ovenfor), er de enkelte anførselstegn omkring tabelnavnet obligatoriske. Hvis tabelnavnet er uden mellemrum, kan de enkelte anførselstegn udelades, så syntaksen ser ud som følgende:

    TableName[ColumnName]

Det følgende billede viser en DAX-formel, som oprettes i Power BI:

![](media/7-2-dax-calculation-types/dax-calc-types_1.png)

Du kan også udelade tabelnavnet helt og blot bruge kolonnenavnet, men det er dårlig praksis for skrivning af tydelige funktioner (og dermed for tydelig DAX-kode). Kolonnenavne skal altid indeholde kantede parenteser.

Det er bedste praksis *altid* gøre følgende:

* Ingen mellemrum i tabelnavne
* Medtag altid tabelnavnet i formler (udelad det ikke, selvom DAX gør det muligt)

## <a name="creating-calculated-columns"></a>Opret beregnede kolonner
**Beregnede kolonner** er nyttige, når du ønsker at opdele eller filtrere på værdien, eller hvis du vil have beregninger for hver række i tabellen.

Du kan oprette beregnede kolonner i Power BI Desktop ved at vælge **Ny kolonne** under fanen **Modellering**. Det er bedst til at være i **datavisning** (i stedet for **rapport-** eller **relationsvisning**), da du kan se den nye kolonne, der er oprettet, og **formellinjen** er udfyldt og klar til din DAX-formel.

![](media/7-2-dax-calculation-types/dax-calc-types_2a.png)

Når du vælger knappen **Ny kolonne**, udfyldes **formellinjen** med et grundlæggende kolonnenavn (som du selvfølgelig ændrer, så det passer til formlen) og operatoren **=**, og den nye kolonne vises i datagitteret, som vist på følgende billede.

![](media/7-2-dax-calculation-types/dax-calc-types_3.png)

Der er følgende obligatoriske elementer til en beregnet kolonne:

* et nyt kolonnenavn
* mindst én funktion eller ét udtryk

Hvis du refererer til en tabel eller kolonne i den beregnede kolonneformel, behøver du ikke at angive en række i tabellen – Power BI beregner kolonnen for den aktuelle række for hver beregning.

## <a name="creating-calculated-measures"></a>Opret beregnede målinger
Brug en **beregnet måling**, når du beregner procenter eller forhold, eller du har brug for komplekse sammenlægninger. Vælg knappen **Ny måling** under fanen **Modellering** for at oprette en måling ved hjælp af en DAX-formel. Der er igen bedst at være i **datavisningen** i Power BI Desktop, da den indeholder **formellinjen** og gør det nemt at skrive DAX-formlen.

![](media/7-2-dax-calculation-types/dax-calc-types_4.png)

Med **målinger** kan du se et nyt ikon for måling, der vises i ruden **Felter** med navnet på målingen. **Formellinjen** udfyldes igen med navnet på din DAX-formel (denne gang med din måling).

![](media/7-2-dax-calculation-types/dax-calc-types_5.png)

De obligatoriske elementer til en beregnet måling er de samme som til en beregnet kolonne:

* et nyt målingsnavn
* mindst én funktion eller ét udtryk

> Videoindholdet er fra [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

