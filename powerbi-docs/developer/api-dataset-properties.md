---
title: Egenskaber for Power BI-datasæt
description: Få mere at vide om Power BI-datasæt API'ers egenskaber
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: cf489f842d114dbf0ac1add561a93c2ce5499971
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/03/2018
ms.locfileid: "37780559"
---
# <a name="dataset-properties"></a>Egenskaber for datasæt

Den aktuelle v1 for datasæts API giver kun mulighed for at oprette et datasæt med et navn og en samling af tabeller. Hver tabel kan have et navn og en samling af kolonner. Hver kolonne har et navn og en datatype. Vi udvider disse egenskaber, især med understøttelse af målinger og relationer mellem tabeller. Den komplette liste over understøttede egenskaber for denne version er som følger:

> [!IMPORTANT]
> Der kan tilgås på siden [Datasæts handlingsgrupper](https://docs.microsoft.com/rest/api/power-bi/datasets).

## <a name="dataset"></a>Datasæt

Navn  |Type  |Beskrivelse  |Skrivebeskyttet  |Påkrævet
---------|---------|---------|---------|---------
id     |  Guid       | Entydigt id for datasættet overalt i systemet.        | Sandt        | Falsk        
navn     | String        | Datasættets brugerdefinerede navn.        | Falsk        | Sandt        
tabeller     | Tabel[]        | Samling af tabeller.        |  Falsk       | Falsk        
relationer     | Relation[]        | Samling af relationer mellem tabeller.        | Falsk        |  Falsk  
standardtilstand     | String        | Bestemmer, om datasættet pushes, streames eller begge dele, med værdierne af "Push", "Streaming" og "PushStreaming".         | Falsk        |  Falsk

## <a name="table"></a>Tabel

Navn  |Type  |Beskrivelse  |Skrivebeskyttet  |Påkrævet
---------|---------|---------|---------|---------
navn     | String        |  Tabellens brugerdefinerede navn. Bruges også som id for tabellen.       | Falsk        |  Sandt       
kolonner     |  Kolonne[]       |  Samling af kolonner.       | Falsk        |  Sandt       
målinger     | måling[]        |  Samling af målinger.       | Falsk        |  Falsk       
isHidden     | Boolean        | Hvis true, er tabellen skjult for klientværktøjer.        | Falsk        | Falsk        

## <a name="column"></a>Kolonne

Navn  |Type  |Beskrivelse  |Skrivebeskyttet  |Påkrævet
---------|---------|---------|---------|---------
navn     |  String        | Kolonnens brugerdefinerede navn.        |  Falsk       | Sandt       
dataType     |  String       |  Understøttede [EDM-datatyper](https://msdn.microsoft.com/library/ee382832.aspx) og begrænsninger. Se [Begrænsninger for datatypen](#DataTypeRestrictions).      |  Falsk       | Sandt        
formatString     | String        | En streng, der beskriver, hvordan værdien skal formateres, når den vises. Hvis du vil vide mere om strengformatering, se [FORMAT_STRING-indholdet](https://msdn.microsoft.com/library/ms146084.aspx).      | Falsk        | Falsk        
sortByColumn    | String        |   Strengnavnet på en kolonne i samme tabel, der bruges til at bestille den aktuelle kolonne.     | Falsk        | Falsk       
dataCategory     | String        |  Strengværdi, der bruges til datakategorien, som beskriver dataene i denne kolonne. Almindelige værdier omfatter: adresse, by, kontinent, land, billede, BilledUrl, breddegrad, længdegrad, organisation, sted, postnummer, stat eller land, WebUrl       |  Falsk       | Falsk        
isHidden    |  Boolean       |  Egenskaben, der angiver, om kolonnen er skjult i visningen. Standard er false.       | Falsk        | Falsk        
summarizeBy     | String        |  Standardmetode for sammenlægning til kolonnen. Værdier omfatter: standard, ingen, sum, min, maks, antal, gennemsnit, distinctCount     |  Falsk       | Falsk

## <a name="measure"></a>Måling

Navn  |Type  |Beskrivelse  |Skrivebeskyttet  |Påkrævet
---------|---------|---------|---------|---------
navn     | String        |  Målingens brugerdefinerede navn.       |  Falsk       | Sandt        
udtryk     | String        | Et gyldigt DAX-udtryk.        | Falsk        |  Sandt       
formatString     | String        |  En streng, der beskriver, hvordan værdien skal formateres, når den vises. Hvis du vil vide mere om strengformatering, se [FORMAT_STRING-indholdet](https://msdn.microsoft.com/library/ms146084.aspx).       | Falsk        | Falsk        
isHidden     | String        |  Hvis true, er tabellen skjult for klientværktøjer.       |  Falsk       | Falsk       

## <a name="relationship"></a>Relation

Navn  |Type  |Beskrivelse  |Skrivebeskyttet  |Påkrævet 
---------|---------|---------|---------|---------
navn     | String        | Relationens brugerdefinerede navn. Bruges også som id for relationen.        | Falsk       | Sandt        
crossFilteringBehavior     | String        |    Relationens filterretning: OneDirection (standard), BothDirections, automatisk       | Falsk        | Falsk        
fromTable     | String        | Navnet på fremmed nøgle-tabellen.        | Falsk        | Sandt         
fromColumn    | String        | Navnet på fremmed nøgle-kolonnen.        | Falsk        | Sandt         
toTable    | String        | Navnet på tabellen med den primære nøgle.        | Falsk        | Sandt         
toColumn     | String        | Navnet på kolonnen med den primære nøgle.        | Falsk        | Sandt        

<a name="DataTypeRestrictions"/>

## <a name="data-type-restrictions-applies-to-datatype-property"></a>Begrænsninger for datatypen (gælder egenskaben dataType)

Datatype  |Begrænsninger  
---------|---------
Int64     |   Int64.MaxValue og Int64.MinValue er ikke tilladt.      
Double     |  Værdierne Double.MaxValue og Double.MinValue er ikke tilladt. NaN understøttes ikke. +Infinity og -Infinity understøttes ikke i visse funktioner (f.eks. Min, Max).       
Boolean     |   Sand eller falsk.
Datetime    |   Under indlæsning af data beregnes værdier baseret på brøkdele af dagen i hele multipler af 1/300 sekunder (3,33 ms).      
String     |  Tillader i øjeblikket op til 4.000 tegn pr. strengværdi.
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