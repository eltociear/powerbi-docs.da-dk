Brug af **variabler** er en meget effektiv del af et DAX-udtryk.

![](media/7-4-dax-expressions/dax-variables_1.png)

Du kan definere en variabel et vilkårligt sted i et DAX-udtryk ved hjælp af følgende syntaks:

    VARNAME = RETURNEDVALUE

Variabler kan være alle slags datatyper, herunder hele tabeller.

Vær opmærksom på, at hver gang du refererer til en variabel i dit DAX-udtryk, skal Power BI genberegne dens værdi i henhold til din definition. Derfor er det en god idé at undgå gentagne variabler i funktionen.

> Videoindholdet er fra [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax)
> 
> 

