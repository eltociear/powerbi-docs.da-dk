---
title: URL-parametre i sideinddelte rapporter – Power BI Report Builder
description: I dette emne beskrives den almindelige brug af rapportparametre i Power BI Paginated Report Builder, hvilke egenskaber du kan angive og meget mere.
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.custom: ''
ms.date: 09/10/2019
ms.openlocfilehash: e39864081ce4dd1ad415224454b75404e882e9ce
ms.sourcegitcommit: 01de0b01f66f28ca45b8d309d7864f261d6c9a85
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/16/2019
ms.locfileid: "74128321"
---
# <a name="url-parameters-in-paginated-reports-in-power-bi"></a>URL-parametre i sideinddelte rapporter i Power BI

Du kan sende kommandoer til sideinddelte rapporter i Power BI ved at føje en parameter til en URL-adresse. For eksempel har du måske fået vist rapporten ved hjælp af et bestemt sæt rapportparameterværdier. Du kan indkapsle disse oplysninger i URL-adressen ved hjælp af foruddefinerede URL-adgangsparametre. Du kan desuden tilpasse, hvordan Power BI behandler rapporten, ved at integrere parametre for gengivelsesformater eller for udseendet og funktionaliteten af rapportværktøjslinjen. Du kan derefter indsætte denne URL-adresse direkte i en mail eller på en webside, så andre kan opleve din rapport på samme måde i browseren. 

Her er de handlinger, du kan udføre via URL-adgangsparametre: 

- Sende rapportparametre til en rapport. 
- Starte eksporten af rapportindholdet i et understøttet filformat. 
- Skjule eller vise ruden med parametre. 
- Angive indstillingen DeviceInfo. 

Du kan finde en komplet liste over de kommandoer og indstillinger, der er tilgængelige via URL-adgang, under  [Reference til URL-adgang](#url-access-parameter-reference) senere i denne artikel. 

## <a name="url-access-concepts"></a>Begreber til URL-adgang 

URL-anmodninger til Power BI indeholder parametre, der behandles af tjenesten. Den måde, tjenesten håndterer URL-anmodninger på, afhænger af parametre, parameterpræfikser og de typer elementer, der er inkluderet i URL-adressen. URL-funktionalitet i sideinddelte rapporter er kompatibel med de fleste browsere og programmer, der understøtter URL-standardadresser. 

## <a name="url-access-syntax"></a>URL-adgangssyntaks 

URL-anmodninger kan indeholde flere parametre, der er angivet i en vilkårlig rækkefølge. Parametre skal være adskilt af et &-tegn. Navn og værdipar adskilles med et lighedstegn (=). Eksempel:

```
powerbiserviceurl?rp:parametervalueh&rdl:parameter=value  
```

## <a name="syntax-description"></a>syntaksbeskrivelse 

### <a name="powerbiserviceurl"></a>powerbiserviceurl 

Webtjenestens URL-adresse for Power BI-lejeren. Eksempel: 

**&** Bruges til at adskille navne og værdipar for URL-adgangsparametre.

**præfiks** Et præfiks for URL-parameteren (f.eks. rp: elle rdl:), der angiver en handling i Power BI-tjenesten. 

> [!NOTE]
> Rapportparametre kræver et parameterpræfiks, og der skelnes mellem store og små bogstaver. 

**parameter** Navnet på parameteren. 

### <a name="value"></a>værdi 

URL-tekst, der svarer til værdien af den parameter, der bruges. 

Du kan finde eksempler på, hvordan du videregiver rapportparametre for URL-adressen i  [Videregiv en rapportparameter i en URL-adresse](report-builder-url-pass-parameters.md).

## <a name="url-access-parameter-reference"></a>Reference til URL-adgangsparameter

Du kan bruge følgende parametre som en del af en URL-adresse til at konfigurere udseendet og funktionaliteten af dine sideinddelte rapporter i Power BI. De mest almindelige parametre er angivet i dette afsnit. Der skelnes mellem store og små bogstaver i parametre, og de starter med parameterpræfikset `rdl:` , hvis de er relateret til outputformatet.  

### <a name="report-commands-rdl"></a>Rapportkommandoer (`rdl:`) 

**Eksportformat** Angiver det format, der skal gengives og eksporteres i en rapport. Tilgængelige værdier er:
 
- PPTX (PowerPoint)
- MHTML 
- BILLEDE 
- EXCELOPENXML (EXCEL) 
- WORDOPENXML (WORD) 
- CSV 
- PDF 
- XML 

**Enhedsoplysninger** Du kan angive yderligere outputparametre for følgende eksportformater. 

PDF:

- rdl:AccessiblePDF=true/false
- rdl:Columns=integer
- rdl:ColumnSpacing=decimal(in)
- rdl:DpiX=integer
- rdl:DpiY=integer
- rdl:EndPage=integer
- rdl:HumanReadablePDF=true/false
- rdl:MarginBottom=decimal(in)
- rdl:MarginBottom=decimal(in)
- rdl:MarginRight=decimal(in)
- rdl:MarginTop=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:PageHeight=decimal(in)
    - rdl:StartPage=integer
    
CSV:

- rdl:Encoding=string
- rdl:ExcelMode=true/false
- rdl:FieldDelimiter=string
- rdl:FileExtension=string
- rdl:NoHeader=true/false
- rdl:Qualifier=string
- rdl:RecordDelimiter=string
- rdl:SuppressLineBreaks=true/false
    - RDL: UseFormattedValues = true/false
    
WORDOPENXML (WORD):

- rdl:AutoFit=string -> True/False/Never/Default
- rdl:ExpandToggles=true/false
- rdl:FixedPageWidth=true/false
- rdl:OmitHyperlinks=true/false
- rdl:OmitDrillthroughs=true/false

EXCELOPENXML (EXCEL):

- rdl:OmitDocumentMap=true/false
- rdl:OmitFormulas=true/false
    - rdl:SimplePageHeaders=true/false
    
PPTX (PowerPoint):
 
- rdl:Columns=integer
- rdl:ColumnSpacing=decimal(in)
- rdl:DpiX=integer
- rdl:DpiY=integer
- rdl:EndPage=integer
- rdl:MarginBottom=decimal(in)
- rdl:MarginBottom=decimal(in)
- rdl:MarginRight=decimal(in)
- rdl:MarginTop=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:StartPage=integer
    - rdl:UseReportPageSize=true/false

XML:

- rdl:XSLT=string
- rdl:MIMEType=string
- RDL: UseFormattedValues = true/false
- rdl:Indented=true/false
- rdl:OmitNamespace=true/false
- rdl:OmitSchema=true/false
- rdl:Encoding=string
- rdl:FileExtension=string
- rdl:Schema=true/false

## <a name="next-steps"></a>Næste trin

- [Videregiv en rapportparameter i en URL-adresse til en sideinddelt rapport i Power BI](report-builder-url-pass-parameters.md)
- [Hvad er sideinddelte rapporter i Power BI Premium?](paginated-reports-report-builder-power-bi.md)
