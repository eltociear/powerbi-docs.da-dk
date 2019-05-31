---
title: Hvad er Power BI-skabelonprogrammer? (eksempelvisning)
description: Denne artikel indeholder en oversigt over Power BI-skabelonprogrammet. Få mere at vide om, hvordan du udarbejder Power BI-programmer med kun lidt eller ingen kode og udruller dem til dine Power BI-kunder.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
ms.openlocfilehash: 0ea8f19fa36bf1f9ceb5f8f0b92bd53ebdfa2a01
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578516"
---
# <a name="what-are-power-bi-template-apps-preview"></a>Hvad er Power BI-skabelonprogrammer? (eksempelvisning)

Med de nye Power BI-*skabelonprogrammer* kan Power BI-partnere udarbejde programmer i Power BI med kun lidt eller ingen kode og udrulle dem til Power BI-kunder.  Denne artikel indeholder en oversigt over Power BI-skabelonprogrammet.

Skabelonprogrammer er en erstatning for de aktuelle tjenesteindholdspakker. Som Power BI-partner kan du oprette indhold, der er klar til brug, for dine kunder og selv udgive det.  

Du kan udarbejde skabelonprogrammer, som gør det muligt for dine kunder at oprette forbindelse til og instantiere deres egne konti. Som domæneeksperter kan de låse op for data på en måde, så deres erhvervsbrugere nemt kan bruge dem.  

Du kan sende dine skabelon apps til Cloud Partner-portalen. Programmerne bliver derefter offentligt tilgængelige i Power BI-programgalleriet (app.powerbi.com/getdata/services) og på Microsoft AppSource (appsource.microsoft.com). Her er et overordnet Kig på oprettelse af den offentlige skabelon appoplevelsen.  

## <a name="process"></a>Proces
Den generelle proces for at udvikle og indsende en skabelonapp omfatter flere faser. Nogle faser kan indeholde mere end én aktivitet på samme tid.


| Fase | Power BI Desktop |  |Power BI-tjenesten  |  |Cloud Partner-portal  |
|---|--------|--|---------|---------|---------|
| **Et** | Udarbejd en datamodel og en rapport i en .pbix-fil |  | Opret et arbejdsområde. Importér en PBIX-fil. Opret et supplerende dashboard  |  | Registrer dig som partner |
| **To** |  |  | Opret en testpakke, og kør intern validering        |  | |
| **Tre** | |  | Hæv testpakken til præproduktion, så den kan valideres uden for din Power BI-lejer, og send den til AppSource  |  | Ved hjælp af din præproduktionspakke kan du oprette et tilbud på et Power BI-skabelonprogram og starte valideringsprocessen |
| **Fire** | |  | Hæv præprodukstionspakken til produktion |  | Gå live |

## <a name="requirements"></a>Krav

Du skal have tilladelse til at oprette et skabelonprogram. Du kan finde flere oplysninger på Power BI-administrationsportal, indstillingen Skabelonprogram. 

Hvis du vil udgive et skabelonprogram i Power BI-tjenesten og AppSource, skal du opfylde kravene til at [blive udgiver på Cloud Marketplace](https://docs.microsoft.com/azure/marketplace/become-publisher).
 
## <a name="high-level-steps"></a>Overordnede trin

Her er de overordnede trin. 

1. [Gennemse kravene](#requirements), så du er sikker på, at du opfylder dem. 

1. Udarbejd en rapport i Power BI Desktop. Brug parametre, så du kan gemme den som en fil, som andre kan bruge. 

1. Opret et arbejdsområde til dit skabelonprogram i din lejer i Power BI-tjenesten (app.powerbi.com). 

1. Importér din .pbix-fil, og føj indhold såsom et dashboard til dit program. 

1. Opret en testpakke for selv at teste skabelonprogrammet i din organisation. 

1. Hæv testprogrammet til præproduktion for at indsende programmet til validering i AppSource og teste det uden for din egen lejer. 

1. Send indholdet til Cloud Partner-platformen, så det kan blive udgivet. 

1. Gå "live" med dit tilbud i AppSource, og flyt programmet til produktion i Power BI.
2. Nu kan du begynde at udvikle den næste version i præproduktion i det samme arbejdsområde. 

## <a name="requirements"></a>Krav

Du skal have tilladelse til at oprette et skabelonprogram. Du kan finde flere oplysninger på Power BI[-administrationsportal, indstillingen Skabelonprogram](service-admin-portal.md#template-apps-settings-preview). 

Hvis du vil udgive et skabelonprogram i Power BI-tjenesten og AppSource, skal du opfylde kravene til at [blive udgiver på Cloud Marketplace](https://docs.microsoft.com/azure/marketplace/become-publisher).

## <a name="tips"></a>Tip 

- Sørg for, at dit program indeholder eksempeldata, så alle kan komme i gang med et enkelt klik. 
- Undersøg omhyggeligt dit program ved at installere det i din lejer og i en sekundær lejer. Sørg for, at kunderne kun ser det, du gerne vil have, at de skal se. 
- Brug AppSource som din onlinebutik til at hoste dit program. På denne måde kan alle, der bruger Power BI, finde dit program. 
- Overvej at tilbyde mere end ét skabelonprogram til de enkelte unikke scenarier. 
- Aktivér datatilpasning, f.eks. understøttelse af brugerdefineret forbindelse og konfiguration af parametre af installationsprogrammet.

Du kan finde flere forslag under [Tip til udarbejdelse af skabelonprogrammer i Power BI (prøveversion)](service-template-apps-tips.md).

## <a name="support"></a>Support
Hvis du vil have support under udvikling, skal du bruge [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support). Vi overvåger og administrerer aktivt dette websted. Kundehændelser finder hurtigt vej til det relevante team.

## <a name="next-steps"></a>Næste trin

[Opret et skabelonprogram](service-template-apps-create.md)