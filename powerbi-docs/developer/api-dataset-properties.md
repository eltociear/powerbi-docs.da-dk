---
title: Egenskaber for Power BI-datasæt
description: Få mere at vide om Power BI-datasæt API'ers egenskaber
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 4654534d9643b9c5cf5911249a0eda33b5cc32af
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277888"
---
# <a name="dataset-properties"></a>Egenskaber for datasæt

Den aktuelle v1 for datasæts API giver kun mulighed for at oprette et datasæt med et navn og en samling af tabeller. Hver tabel kan have et navn og en samling af kolonner. Hver kolonne har et navn og en datatype. Vi udvider disse egenskaber, især med understøttelse af målinger og relationer mellem tabeller. Den komplette liste over understøttede egenskaber for denne version er som følger:

> [!IMPORTANT]
> Der kan tilgås på siden [Datasæts handlingsgrupper](https://docs.microsoft.com/rest/api/power-bi/datasets).

## <a name="dataset"></a>Datasæt

Navn  |Type  |Beskrivelse  |Skrivebeskyttet  |Påkrævet
---------|---------|---------|---------|---------
id     |  Guid       | Entydigt id for datasættet overalt i systemet.        | Sandt        | Falsk        
navn     | Streng        | Datasættets brugerdefinerede navn.        | Falsk        | Sandt        
tabeller     | Tabel[]        | Samling af tabeller.        |  Falsk       | Falsk        
relationer     | Relation[]        | Samling af relationer mellem tabeller.        | Falsk        |  Falsk  
standardtilstand     | Streng        | Bestemmer, om datasættet pushes, streames eller begge dele, med værdierne af "Push", "Streaming" og "PushStreaming".         | Falsk        |  Falsk

## <a name="table"></a>Tabel

Navn  |Type  |Beskrivelse  |Skrivebeskyttet  |Påkrævet
---------|---------|---------|---------|---------
navn     | Streng        |  Tabellens brugerdefinerede navn. Bruges også som id for tabellen.       | Falsk        |  Sandt       
kolonner     |  Kolonne[]       |  Samling af kolonner.       | Falsk        |  Sandt       
målinger     | måling[]        |  Samling af målinger.       | Falsk        |  Falsk       
isHidden     | Boolesk        | Hvis true, er tabellen skjult for klientværktøjer.        | Falsk        | Falsk        

## <a name="column"></a>Kolonne

Navn  |Type  |Beskrivelse  |Skrivebeskyttet  |Påkrævet
---------|---------|---------|---------|---------
navn     |  Streng        | Kolonnens brugerdefinerede navn.        |  Falsk       | Sandt       
dataType     |  Streng       |  Understøttede [EDM-datatyper](https://msdn.microsoft.com/library/ee382832.aspx) og begrænsninger. Se [Begrænsninger for datatypen](#DataTypeRestrictions).      |  Falsk       | Sandt        
formatString     | Streng        | En streng, der beskriver, hvordan værdien skal formateres, når den vises. Hvis du vil vide mere om strengformatering, se [FORMAT_STRING-indholdet](https://msdn.microsoft.com/library/ms146084.aspx).      | Falsk        | Falsk        
sortByColumn    | Streng        |   Strengnavnet på en kolonne i samme tabel, der bruges til at bestille den aktuelle kolonne.     | Falsk        | Falsk       
dataCategory     | Streng        |  Strengværdi, der bruges til datakategorien, som beskriver dataene i denne kolonne. Nogle almindelige værdier omfatter: Address, City, Continent, Country, Image, ImageUrl, Latitude, Longitude, Organization, Place, PostalCode, StateOrProvince, WebUrl       |  Falsk       | Falsk        
isHidden    |  Boolesk       |  Egenskaben, der angiver, om kolonnen er skjult i visningen. Standard er false.       | Falsk        | Falsk        
summarizeBy     | Streng        |  Standardmetode for sammenlægning til kolonnen. Værdier omfatter: standard, ingen, sum, min, maks, antal, gennemsnit, distinctCount     |  Falsk       | Falsk

## <a name="measure"></a>Måling

Navn  |Type  |Beskrivelse  |Skrivebeskyttet  |Påkrævet
---------|---------|---------|---------|---------
navn     | Streng        |  Målingens brugerdefinerede navn.       |  Falsk       | Sandt        
udtryk     | Streng        | Et gyldigt DAX-udtryk.        | Falsk        |  Sandt       
formatString     | Streng        |  En streng, der beskriver, hvordan værdien skal formateres, når den vises. Hvis du vil vide mere om strengformatering, se [FORMAT_STRING-indholdet](https://msdn.microsoft.com/library/ms146084.aspx).       | Falsk        | Falsk        
isHidden     | Streng        |  Hvis true, er tabellen skjult for klientværktøjer.       |  Falsk       | Falsk       

## <a name="relationship"></a>Relation

Navn  |Type  |Beskrivelse  |Skrivebeskyttet  |Påkrævet 
---------|---------|---------|---------|---------
navn     | Streng        | Relationens brugerdefinerede navn. Bruges også som id for relationen.        | Falsk       | Sandt        
crossFilteringBehavior     | Streng        |    Relationens retning for filtrering: OneDirection (standard), BothDirections, automatisk       | Falsk        | Falsk        
fromTable     | Streng        | Navnet på fremmed nøgle-tabellen.        | Falsk        | Sandt         
fromColumn    | Streng        | Navnet på fremmed nøgle-kolonnen.        | Falsk        | Sandt         
toTable    | Streng        | Navnet på tabellen med den primære nøgle.        | Falsk        | Sandt         
toColumn     | Streng        | Navnet på kolonnen med den primære nøgle.        | Falsk        | Sandt        

<a name="DataTypeRestrictions"/>

## <a name="data-type-restrictions-applies-to-datatype-property"></a>Begrænsninger for datatypen (gælder egenskaben dataType)

Datatype  |Begrænsninger  
---------|---------
Int64     |   Int64.MaxValue og Int64.MinValue er ikke tilladt.      
Double     |  Værdierne Double.MaxValue og Double.MinValue er ikke tilladt. NaN understøttes ikke. +Infinity og -Infinity understøttes ikke i visse funktioner (f.eks. Min, Max).       
Boolesk     |   Sand eller falsk.
Datetime    |   Under indlæsning af data beregnes værdier baseret på brøkdele af dagen i hele multipler af 1/300 sekunder (3,33 ms).      
Streng     |  Tillader i øjeblikket op til 4.000 tegn pr. strengværdi.
Decimal|præcision = 28, skala = 4

## <a name="example"></a>Eksempel
Følgende kodeeksempel omfatter en række disse egenskaber:

```
{

  "name": "PushAdvanced",

  "tables": [

    {

      "name": "Date",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        }

      ]

    },

    {

      "name": "sales",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "Sales",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ],

      "measures": [

        {

          "name": "percent to forecast",

          "expression": "SUM(sales[Sales])/SUM(forecast[forecast])",

          "formatString": "0.00 %;-0.00 %;0.00 %"

        }

      ]

    },

    {

      "name": "forecast",

      "columns": [

        {

          "name": "date",

          "dataType": "dateTime",

          "formatString": "m/d/yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "forecast",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ]

    }

  ],

  "relationships": [

    {

      "name": "2ea345ce-b147-436e-8ac2-9d3c4d82af8d",

      "fromTable": "sales",

      "fromColumn": "Date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    },

    {

      "name": "5d95f419-e589-4345-9581-6e70670b1bba",

      "fromTable": "forecast",

      "fromColumn": "date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    }

  ]

}
```