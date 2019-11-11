---
ms.openlocfilehash: 679c3e8c3d94c93899e9dcfae1e57f4b678fb218
ms.sourcegitcommit: a5853ef44ed52e80eabee3757bb6887fa400b75b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799768"
---
Med Power BI kan du oprette relationer mellem flere tabeller, herunder tabeller, der stammer fra helt forskellige datakilder. Du kan se disse relationer for en datamodel i visningen **Relationer** i Power BI Desktop.

![](media/7-5-table-relationships-and-dax/dax-relationships_1.png)

## <a name="dax-relational-functions"></a>DAX – relationelle funktioner
DAX har **relationelle funktioner**, der giver dig mulighed for at interagere med tabeller med fastlagte relationer.

Du kan returnere værdien af en kolonne, eller du kan returnere alle rækker i en relation, ved hjælp af DAX-funktioner.

Funktionen **RELATED** følger f.eks. relationer og returnerer værdien af en kolonne, mens **RELATEDTABLE** følger relationer og returnerer en hel tabel, der er filtreret, så den kun indeholder relaterede rækker.

![](media/7-5-table-relationships-and-dax/dax-relationships_2.png)

Funktionen **RELATED** fungerer på *mange til en*-relationer, mens **RELATEDTABLE** er til *en til mange*-relationer.

Du kan bruge relationelle funktioner til at oprette udtryk, der indeholder værdier på tværs af flere tabeller. DAX returnerer et resultat med disse funktioner, uanset hvor lang kæden af relationen er.

> Videoindholdet er fra [Alberto Ferrari, SQLBI](https://www.sqlbi.com/learning-dax)
> 
> 

