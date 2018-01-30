---
title: "Overfør data til et datasæt"
description: "Overfør data til et Power BI-datasæt"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/05/2017
ms.author: asaxton
ms.openlocfilehash: aba135a0a790025f732379ecb07157f1150d999c
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/05/2018
---
# <a name="push-data-into-a-power-bi-dataset"></a>Overfør data til et Power BI-datasæt
Med Power BI-API'en kan du overføre data til et Power BI-datasæt. Et eksempel kunne f.eks. være, at du vil forlænge en eksisterende forretningsarbejdsproces for at overføre vigtige data til dit datasæt. I dette tilfælde vil du overføre et salg og marketing-datasæt, som indeholder en varetabel, til et andet datasæt.

Før du begynder at overføre data til et datasæt, skal du have en Azure AD- (Azure Active Directory) og [Power BI-konto](create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Sådan overfører du data til et datasæt
* Trin 1: [Registrer en app i Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* Trin 2: [Hent et adgangstoken til godkendelse](walkthrough-push-data-get-token.md)
* Trin 3: [Opret et datasæt i Power BI](walkthrough-push-data-create-dataset.md)
* Trin 4: [Hent et datasæt for at føje rækker til en Power BI-tabel](walkthrough-push-data-get-datasets.md)
* Trin 5: [Føj rækker til en Power BI-tabel](walkthrough-push-data-add-rows.md)

Det næste afsnit er en generel beskrivelse af de handlinger i Power BI-API'en, der overfører data.

## <a name="power-bi-api-operations-to-push-data"></a>Handlinger i Power BI-API'en til overførsel af data
Med Power BI REST API'en kan du overføre datakilder til Power BI. Når en app føjer rækker til et datasæt, opdateres felterne i dashboardet automatisk med de opdaterede data. Hvis du vil overføre data, skal du bruge handlingen [Create Dataset](https://msdn.microsoft.com/library/mt203562.aspx) sammen med handlingen [Add Rows](https://msdn.microsoft.com/library/mt203561.aspx). Hvis du vil finde et datasæt, skal du bruge handlingen [Get Datasets](https://msdn.microsoft.com/library/mt203567.aspx). Du kan overføre et gruppe-id for alle disse handlinger, hvis du vil arbejde med en gruppe. Brug handlingen [Get Groups](https://msdn.microsoft.com/library/mt243842.aspx) for at få vist en oversigt over alle gruppe-id'er.

Her er de handlinger, du skal bruge for at overføre data til et datasæt:

* [Create Dataset](https://msdn.microsoft.com/library/mt203562.aspx)
* [Hent datasæt](https://msdn.microsoft.com/library/mt203567.aspx)
* [Tilføj rækker](https://msdn.microsoft.com/library/mt203561.aspx)
* [Get Groups](https://msdn.microsoft.com/library/mt243842.aspx)

Du kan oprette et datasæt i Power BI ved at overføre en JSON-streng (JavaScript Object Notation) til Power BI-tjenesten. Hvis du vil have mere at vide om JSON, skal du se [Om JSON](http://json.org/).

JSON-strengen til et datasæt har følgende format:

**Power BI-datasæt JSON-objekt**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

Så for eksemplet med salg og marketing-datasættet ville du overføre en JSON-streng som vist i eksemplet nedenfor. I dette eksempel er **SalesMarketing** navnet på datasættet, og **Product** er navnet på tabellen. Når du har defineret tabellen, kan du definere tabelskemaet. Tabelskemaet indeholder kolonnerne ProductID, Manufacturer, Category, Segment, Product og IsComplete for datasættet **SalesMarketing**.

**Eksempeldatasæt JSON-objekt**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

Hvis du har et Power BI-tabelskema, kan du bruge følgende datatyper.

## <a name="power-bi-table-data-types"></a>Power BI-tabeldatatyper
| **Datatype** | **Begrænsninger** |
| --- | --- |
| Int64 |Int64.MaxValue og Int64.MinValue er ikke tilladt. |
| Double |Værdierne Double.MaxValue og Double.MinValue er ikke tilladt. NaN understøttes ikke. +Infinity og -Infinity understøttes ikke i visse funktioner (f.eks. Min, Max). |
| Boolean |None |
| Datetime |Under indlæsning af data beregnes værdier baseret på brøkdele af dagen i hele multipler af 1/300 sekunder (3,33 ms). |
| String |Tillader i øjeblikket op til 128.000 tegn. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Få mere at vide om at overføre data til Power BI
For at komme i gang med at overføre data til et datasæt skal du se [Trin 1: Registrer en app i Azure AD](walkthrough-push-data-register-app-with-azure-ad.md) i venstre navigationsrude.

[Næste trin >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Næste trin
[Tilmeld dig Power BI](create-an-azure-active-directory-tenant.md)  
[Opret datasæt](https://msdn.microsoft.com/library/mt203562.aspx)  
[Hent datasæt](https://msdn.microsoft.com/library/mt203567.aspx)  
[Tilføj rækker](https://msdn.microsoft.com/library/mt203561.aspx)  
[Hent grupper](https://msdn.microsoft.com/library/mt243842.aspx)  
[Introduktion til JSON](http://json.org/)  
[Oversigt over Power BI REST-API](overview-of-power-bi-rest-api.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
