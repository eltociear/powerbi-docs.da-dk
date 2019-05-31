---
title: Overfør data til et datasæt
description: Overfør data til et Power BI-datasæt
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 9eb81610044f795b6f9dc5c58aeefad13de06542
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222150"
---
# <a name="push-data-into-a-power-bi-dataset"></a>Overfør data til et Power BI-datasæt

Power BI-API'EN gør det muligt at overføre data til et Power BI-datasæt. I denne artikel bruger viser vi, hvordan du overføre et salg og Marketing-datasæt, der indeholder en varetabel, til en eksisterende datasæt.

Før du går i gang, du har brug for en Azure Active Directory (Azure AD) og en [Power BI-konto](create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Sådan overfører du data til et datasæt

* Trin 1: [Registrer en app med Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* Trin 2: [Hent et adgangstoken til godkendelse](walkthrough-push-data-get-token.md)
* Trin 3: [Opret et datasæt i Power BI](walkthrough-push-data-create-dataset.md)
* Trin 4: [Hent et datasæt for at føje rækker til en Power BI-tabel](walkthrough-push-data-get-datasets.md)
* Trin 5: [Indsæt rækker i en Power BI-tabel](walkthrough-push-data-add-rows.md)

Det næste afsnit er en generel beskrivelse af de handlinger i Power BI-API'en, der overfører data.

## <a name="power-bi-api-operations-to-push-data"></a>Handlinger i Power BI-API'en til overførsel af data

Med Power BI REST API'en kan du overføre datakilder til Power BI. Når en app føjer rækker til et datasæt, dashboard-felter opdatering automatisk med de nye data. Hvis du vil overføre data, du bruger den [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset) og [PostRows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows) handlinger. Du kan finde et datasæt ved brug af [Get Datasets](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets) handling. Du kan overføre et gruppe-ID til at arbejde med en gruppe for alle disse handlinger. For at få en liste med gruppe-ID, du bruger den [Get Groups](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups) handling.

Her er de handlinger, du skal bruge for at overføre data til et datasæt:

* [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)
* [Hent datasæt](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)
* [Post Rows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows)
* [Hent grupper](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups)

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

For eksemplet med salg og Marketing datasættet ville du overføre en JSON-streng som vist nedenfor. I dette eksempel **SalesMarketing** er navnet på datasættet, og **produkt** tabelnavnet. Når du definerer tabellen, skal definere du tabelskemaet. For datasættet **SalesMarketing** indeholder tabelskemaet disse kolonner: ProductID, Manufacturer, Category, Segment, Product og IsCompete.

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
| Double |Værdierne Double.MaxValue og Double.MinValue er ikke tilladt. NaN understøttes ikke. + Infinity og -Infinity understøttes ikke i visse funktioner (f.eks, Min, Max). |
| Boolesk |None |
| Datetime |Under indlæsning af data, beregnes værdier baseret på brøkdele af dagen af hele intervaller på 1/300 sekunder (3,33 ms). |
| Streng |I øjeblikket tillader op til 128 tegn. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Få mere at vide om at overføre data til Power BI

Du kan få hjælp til at komme i gang med at overføre data til et datasæt i [Trin 1: Registrer en app med Azure AD](walkthrough-push-data-register-app-with-azure-ad.md) i venstre navigationsrude.

[Næste trin >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Næste trin

[Tilmeld dig Power BI](create-an-azure-active-directory-tenant.md)  
[Introduktion til JSON](http://json.org/)  
[Oversigt over Power BI REST-API](overview-of-power-bi-rest-api.md)  
Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)