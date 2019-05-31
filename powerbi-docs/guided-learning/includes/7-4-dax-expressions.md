---
ms.openlocfilehash: 5c2b254f20bd1eba97840a464a1b554cc4fe1238
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61273228"
---
Brug af **variabler** er en meget effektiv del af et DAX-udtryk.

![](media/7-4-dax-expressions/dax-variables_1.png)

Du kan definere en variabel et vilkårligt sted i et DAX-udtryk ved hjælp af følgende syntaks:

    VARNAME = RETURNEDVALUE

Variabler kan være alle slags datatyper, herunder hele tabeller.

Vær opmærksom på, at hver gang du refererer til en variabel i dit DAX-udtryk, skal Power BI genberegne dens værdi i henhold til din definition. Derfor er det en god idé at undgå gentagne variabler i funktionen.

> Videoindholdet er fra [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax)
> 
> 

