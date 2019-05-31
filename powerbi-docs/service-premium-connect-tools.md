---
title: Opret forbindelse til datasæt i Power BI Premium med klientprogrammer og -værktøjer (prøveversion)
description: Beskriver, hvordan du opretter forbindelse til datasæt i Power BI Premium fra klientprogrammer og værktøjer.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 05/20/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 063f43cb2345ccb3d1fec5c414100beb8ccde451
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65941517"
---
# <a name="connect-to-datasets-with-client-applications-and-tools-preview"></a>Opret forbindelse til datasæt med klientprogrammer og -værktøjer (prøveversion)

Power BI Premium-arbejdsområder og datasæt, der understøtter *skrivebeskyttet* forbindelser fra Microsoft og tredjeparter klientprogrammer og værktøjer. 

> [!NOTE]
> I denne artikel er beregnet til kun at introducere skrivebeskyttet forbindelse til Power BI Premium-arbejdsområder og datasæt. Det *er ikke* beregnet til at give detaljerede oplysninger om programmering, bestemte værktøjer og programmer, arkitektur og administration af arbejdsområde og datasæt. Emner, der er beskrevet her, kræver en grundig forståelse af Analysis Services-tabelmodel database arkitektur og administration.

## <a name="protocol"></a>Protokol

Power BI Premium bruger den [XML for Analysis](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference) (XMLA)-protokollen til kommunikation mellem klientprogrammer og databaseprogrammet, der administrerer dine arbejdsområder og datasæt. Disse meddelelser er via det bliver ofte kaldt XMLA-slutpunkter. XMLA er den samme kommunikationsprotokol, der bruges af Microsoft Analysis Services-programmet, der under hjelmen?, kører Power bis semantisk modellering, styring, livscyklus og dataadministration. 

Langt størstedelen af klientprogrammer og værktøjer eksplicit kommunikerer ikke med programmet ved hjælp af XMLA-slutpunkter. I stedet bruge de klientbiblioteker som MSOLAP, ADOMD og AMO som mellemled mellem klientprogrammet og databaseprogrammet, som kommunikerer udelukkende ved hjælp af XMLA.


## <a name="supported-tools"></a>Understøttede funktioner

Disse værktøjer understøtter skrivebeskyttet adgang til Power BI Premium-arbejdsområder og datasæt:

**SQL Server Management Studio (SSMS)** -forespørgsler understøtter DAX, MDX, XMLA og TraceEvent. Kræver version 18.0. Download [her](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms). 

**SQL Server Profiler** -inkluderet i SSMS 18.0 (prøveversion), giver dette værktøj, sporing og fejlfinding af serverhændelser. Du kan hente og gemme data om hver hændelse til en fil eller en tabel til at analysere senere. Mens frarådes officielt til SQL Server, fortsætter med at blive inkluderet i SSMS Profiler, og understøttes stadig til Analysis Services og nu kan Power BI Premium. Hvis du vil vide mere, kan du se [SQL Server Profiler](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler).

**DAX-Studio** – åben kildekode, communityværktøj til udførelse og analyse af DAX-forespørgsler mod Analysis Services. Kræver version 2.8.2 eller nyere. Hvis du vil vide mere, kan du se [daxstudio.org](https://daxstudio.org/).

**Excel-pivottabeller** – Klik til at køre version af Office 16.0.11326.10000 eller nyere er påkrævet.

**Tredjepart** – omfatter visualisering klientprogrammer data og værktøjer, der kan oprette forbindelse til, forespørgsel og forbruge datasæt i Power BI Premium. De fleste funktioner kræver de nyeste versioner af MSOLAP-klientbiblioteker, men nogle må bruge ADOMD-forbindelser.

## <a name="client-libraries"></a>Klientbiblioteker

Klientbiblioteker er nødvendige for klientprogrammer og værktøjer til at oprette forbindelse til Power BI Premium-arbejdsområder. De samme klientbiblioteker, der bruges til at oprette forbindelse til Analysis Services understøttes også i Power BI Premium. Microsoft klientprogrammer som Excel, SQL Server Management Studio (SSMS) og SQL Server Data Tools (SSDT) installerer alle tre klientbiblioteker og opdatere dem sammen med regelmæssige programopdateringer. I nogle tilfælde kan især med tredjepartsprogrammer og -værktøjer, du muligvis installere nyere versioner af klientbibliotekerne. Klientbiblioteker opdateres hver måned. Hvis du vil vide mere, kan du se [-klientbiblioteker til at oprette forbindelse til Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-data-providers).

## <a name="connecting-to-a-premium-workspace"></a>Opretter forbindelse til en Premium-arbejdsområde

Du kan oprette forbindelse til arbejdsområder, der er tildelt til Premium dedikeret kapacitet. Arbejdsområder, der er knyttet til en dedikeret kapacitet har en forbindelsesstreng i URL-formatet. 

Hente forbindelsesstrengen arbejdsområde, i Power BI, i **indstillinger for arbejdsområde**under den **Premium** under fanen **arbejdsområde forbindelse**, skal du klikke på **Kopiér**.

![Forbindelsesstrengen for arbejdsområde](media/service-premium-connect-tools/connect-tools-workspace-connection.png)

Arbejdsområde forbindelser bruger følgende URL-format til at løse et arbejdsområde, som var den navnet på en Analysis Services-server:   
`powerbi://api.powerbi.com/v1.0/[tenant name]/[workspace name]` 

F.eks. `powerbi://api.powerbi.com/v1.0/contoso.com/Sales Workspace`
> [!NOTE]
> `[workspace name]` er tilfældet, der er følsomme og kan indeholde mellemrum. 

### <a name="to-connect-in-ssms"></a>Til at oprette forbindelse i SSMS

I **Opret forbindelse til serveren** > **servertype**, skal du vælge **Analysis Services**. I **servernavn**, Angiv URL-adressen. I **godkendelse**, skal du vælge **Active Directory - Universal med understøttelse af MFA**, og klik derefter på **brugernavn**, Angiv din organisations bruger-ID. 

Når forbindelsen er oprettet, vises arbejdsområdet som en Analysis Services-server, og datasæt i arbejdsområdet vises som databaser.  

![SSMS](media/service-premium-connect-tools/connect-tools-ssms.png)

### <a name="initial-catalog"></a>Oprindeligt katalog

Nogle funktioner, f.eks SQL Server Profiler, du skal muligvis angive en *Oprindeligt katalog*. Angiv et datasæt (database) i dit arbejdsområde. I **Opret forbindelse til serveren**, skal du klikke på **indstillinger**. I den **Opret forbindelse til serveren** dialogboksen under den **forbindelsesegenskaber** under fanen **Opret forbindelse til databasen**, Angiv datasættets navn.

### <a name="duplicate-workspace-name"></a>Duplikeret navn på arbejdsområde

Når du opretter forbindelse til et arbejdsområde med det samme navn som et andet arbejdsområde, kan du få følgende fejl: **Kan ikke oprettes forbindelse til powerbi://api.powerbi.com/v1.0/ [lejernavn] / [workspace name].**

Hvis du vil undgå denne fejl, ud over Arbejdsområdenavnet på, Angiv ObjectIDGuid, som kan kopieres fra det arbejdsområde objectID URL-adressen. Tilføj objekt-id'et til URL-adressen til forbindelsen. F.eks. 'powerbi://api.powerbi.com/v1.0/myorg/Contoso salg – 9d83d204-82a9-4b36-98f2-a40099093830'

### <a name="duplicate-dataset-name"></a>Duplikeret navn på datasæt

Når du opretter forbindelse til et datasæt med samme navn som et andet datasæt i det samme arbejdsområde, kan du føje datasæt guid til datasættets navn. Du kan få begge datasætnavn *og* guid, når du har forbindelse til arbejdsområdet i SSMS. 

### <a name="delay-in-datasets-shown"></a>Forsinkelse i datasæt, der vises

Når du opretter forbindelse til et arbejdsområde, kan ændringer fra nye, slettede og omdøbt datasæt tage op til fem minutter vises. 

### <a name="unsupported-datasets"></a>Ikke-understøttet datasæt

De følgende datasæt er ikke tilgængelige ved hjælp af XMLA-slutpunkter. Disse datasæt *vil ikke* vises under arbejdsområdet i SSMS eller i andre værktøjer: 

- Datasæt med en direkte forbindelse til en Analysis Services-modeller. 
- Datasæt Push data ved hjælp af REST-API'EN.
- Excel-projektmappe datasæt. 

De følgende datasæt understøttes ikke i Power BI-tjenesten:   

- Datasæt med en direkte forbindelse til et Power BI-datasæt.

## <a name="audit-logs"></a>Overvågningslogge 

Når klientprogrammer og værktøjer kan du oprette forbindelse til et arbejdsområde, adgang via XMLA-slutpunkter er logget på i Power BI overvågningslogfilerne under den **GetWorkspaces** handlingen. Hvis du vil vide mere, kan du se [overvågning af Power BI](service-admin-auditing.md).

## <a name="see-also"></a>Se også

[Analysis Services-referencer](https://docs.microsoft.com/bi-reference/#pivot=home&panel=home-all)   
[SQL Server Management Studio](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-ssms)   
[SQL Server Analysis Services-tds-protokol](https://docs.microsoft.com/openspecs/sql_server_protocols/ms-ssas-t/b98ed40e-c27a-4988-ab2d-c9c904fe13cf)   
[Dynamic Management-visninger (DMV)](https://docs.microsoft.com/sql/analysis-services/instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services)   


Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
