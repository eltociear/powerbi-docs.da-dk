---
title: Brug Spørgsmål og svar via direkte forbindelser i Power BI
description: Dokumentationen til brug for forespørgsler på naturlige sprog via Power BI-spørgsmål og svar med direkte forbindelser til Analysis Services-data og datagateway i lokalt miljø.
author: maggiesMSFT
manager: kfile
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 9836cd88bef5066f61a8ae44eabe7685196e2bed
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "65624934"
---
# <a name="enable-qa-for-live-connections-in-power-bi"></a>Aktivér Spørgsmål og svar via direkte forbindelser i Power BI
## <a name="what-is-the-on-premises-data-gateway--what-is-a-live-connection"></a>Hvad er datagatewayen i det lokale miljø?  Hvad er en direkte forbindelse?
Datasæt i Power BI kan importeres til Power BI, eller du kan oprette en direkte forbindelse til dem. Direkte forbindelse, der er datasæt, der ofte refereres til som "i det lokale miljø". De direkte forbindelser administreres ved hjælp af en [gateway](service-gateway-onprem.md), og data og forespørgsler sendes frem og tilbage ved hjælp af direkte forespørgsler.

## <a name="qa-for-on-premises-data-gateway-datasets"></a>Spørgsmål og svar til datasæt i datagateway i lokalt miljø
Hvis du vil bruge Spørgsmål og svar med datasæt, får du adgang via en gateway, men du skal aktivere dem først.

Når Power BI er aktiveret, opretter den et indeks for datakilden og uploader et undersæt af disse data til Power BI for at aktivere funktionen for at stille spørgsmål. Det kan tage flere minutter at oprette det første indeks, og Power BI vedligeholder og opdaterer indekset automatisk, når data ændres. Når du bruger Spørgsmål og svar med disse datasæt, fungerer det på samme måde som med data, der er publiceret til Power BI. Det fulde sæt af funktioner, der er tilgængelige i Spørgsmål og svar-oplevelsen, er understøttet i begge tilfælde, herunder brug af datakilden med Cortana.

Når du stiller spørgsmål i Power BI, afgør Spørgsmål og svar, hvad der er den bedste visuelle gengivelse for konstruktions- eller rapporteringsark, der skal bruges til at svare på dit spørgsmål ved hjælp af et indeks på datasættet. Når Spørgsmål og svar har fastlagt det bedst mulige svar, bruger Spørgsmål og svar DirectQuery til at hente data direkte fra datakilden via gateway'en for at udfylde diagrammer og grafer. Dette sikrer, at Power BI-spørgsmål og svar altid viser de seneste data direkte fra den underliggende datakilde.

Da Power BI-spørgsmål og svar bruger værdierne for tekst og skema fra din datakilde til at bestemme, hvordan der skal forespørges om den underliggende model for at få svar, afhænger søgninger efter specifikke nye eller slettede tekstværdier (f.eks anmode om en kundenavn, der er knyttet til en post med nytilføjet tekst), af, at indekset er opdateret med de nyeste værdier. Power BI opdaterer automatisk tekst- og skemaindekset i et 60-minuttersintervaller, hvor der kan ske ændringer.

Her finder du flere oplysninger:

* Hvad er [datagateway i lokalt miljø](service-gateway-onprem.md)?
* [Power BI Q & A til forbrugere](consumer/end-user-q-and-a.md)

## <a name="enable-qa"></a>Aktivering af Spørgsmål og svar
Når du har konfigureret datagateway'en, kan du oprette forbindelse til dine data fra Power BI.  Opret et dashboard ved hjælp af dataene i det lokale miljø, eller overfør en .pbix-fil, der bruger lokale data.  Du har måske også allerede data i lokalt miljø i dashboards, rapporter og datasæt, der er blevet delt med dig.

1. I øverste højre hjørne af Power BI skal du vælge tandhjulsikonet ![tandhjulsikon](media/service-q-and-a-direct-query/power-bi-cog.png) og vælge **Indstillinger**.
   
   ![Menuen Indstillinger](media/service-q-and-a-direct-query/powerbi-settings.png)
2. Vælg **Datasæt**, og vælg det datasæt, der aktiverer Spørgsmål og svar.
   
   ![Skærmbilledet Datasæt i menuen Indstillinger](media/service-q-and-a-direct-query/power-bi-q-and-a-settings.png)
3. Udvid **Spørgsmål og svar og Cortana**, vælg afkrydsningsfeltet for **Aktivér Spørgsmål og svar for dette datasæt**, og vælg **Anvend**.
   
    ![Udvidet område til spørgsmål og svar](media/service-q-and-a-direct-query/power-bi-q-and-a-directquery.png)

## <a name="what-data-is-cached-and-how-is-privacy-protected"></a>Hvilke data cachelagres, og hvordan beskyttes privatliv?
Når du aktiverer Spørgsmål og svar for dataene i det lokale miljø, cachelagres et undersæt af dine data i tjenesten. Det sker for at sikre, at Spørgsmål og svar fungerer sammen med en rimelig ydeevne. Power BI udelukker værdier med flere end 24 tegn fra cachelagring. Cachen slettes inden for et par timer, når du deaktiverer Spørgsmål og svar ved at fjerne markeringen **Aktivér Spørgsmål og svar for dette datasæt**, eller når du sletter dit datasæt.

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
Funktionen har nogle begrænsninger:

* Til at begynde med er funktionen kun tilgængelig for SQL Server 2016 Analysis Services Tabular-datakilder. Funktionen er optimeret til at arbejde med data i tabelformat. Spørgsmål og svar-oplevelsen endnu understøttes ikke for flerdimensionelle. Der udrulles løbende flere datakilder, som understøttes af den lokale datagateway.
* Fuld understøttelse af sikkerhed på rækkeniveau er defineret i SQL Server Analysis Services er ikke tilgængeligt først. Samtidig med at stille spørgsmål i spørgsmål og svar, har de "Autofuldførelse" af spørgsmål under skrivningen vise strengværdier en bruger ikke adgang til. Dog overholdes den RLS, der er defineret i modellen, for visning af rapporter og diagrammer, så ingen underliggende numeriske data kan fremvises. Indstillinger til at styre denne funktionsmåde vil blive udgivet i kommende opdateringer.
* Sikkerhed på objektniveau (OLS) understøttes ikke. Spørgsmål og svar respekterer ikke sikkerhed på objektniveau og tabel eller kolonne navne til brugere, der ikke har adgang til dem kan vise. Du skal aktivere RLS for at sikre, at også værdier er sikret korrekt. 
* Direkte forbindelser understøttes kun med datagateway i lokalt miljø. Dette kan derfor ikke bruges med den personlige gateway.

## <a name="next-steps"></a>Næste trin

- [Datagateway i lokalt miljø](service-gateway-onprem.md)  
- [Administrer din datakilde – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
- [Power BI: Grundlæggende begreber](consumer/end-user-basic-concepts.md)  
- [Spørgsmål og svar i Power BI – Oversigt](consumer/end-user-q-and-a.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

