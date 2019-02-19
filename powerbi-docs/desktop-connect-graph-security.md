---
title: Opret forbindelse til Microsoft Graph Security i Power BI Desktop
description: Opret nemt forbindelse til Microsoft Graph Security API i Power BI Desktop
author: preetikr
manager: kfile
ms.reviewer: ''
ms.custom: seojan19
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/29/2019
ms.author: preetikr
LocalizationGroup: Connect to data
ms.openlocfilehash: 2187a24820ef8ea3db9fdd1b7a881dc9cfb6393f
ms.sourcegitcommit: f07520591db6c3f27ab6490612cc56384abc6633
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2019
ms.locfileid: "56298885"
---
# <a name="connect-to-microsoft-graph-security-in-power-bi-desktop"></a>Opret forbindelse til Microsoft Graph Security i Power BI Desktop

Du kan bruge Power BI Desktop til at oprette forbindelse til Microsoft Graph Security API ved hjælp af Microsoft Graph Security Power BI-connectoren. Det giver dig mulighed for at bygge dashboards og rapporter, så du kan få viden om sikkerhedsrelaterede [beskeder](https://docs.microsoft.com/graph/api/resources/alert?view=graph-rest-1.0) og din [Secure Score](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta). [Microsoft Graph Security API](https://aka.ms/graphsecuritydocs) kan oprette forbindelse til [flere sikkerhedsløsninger](https://aka.ms/graphsecurityalerts) fra Microsoft og økosystempartnere for at give bedre korrelation af beskeder, give adgang til detaljeret kontekstafhængige oplysninger og forenkle automatisering. Dette gør det muligt for organisationer at få hurtig viden og tage handling på tværs af deres sikkerhedsprodukter og samtidig reducere omkostningerne og kompleksiteten ved at bygge og vedligeholde flere integrationer.

## <a name="prerequisites-to-connect-with-the-microsoft-graph-security-connector"></a>Forudsætningerne for at oprette forbindelse til Microsoft Graph Security-connectoren

* Hvis du vil bruge Microsoft Graph Security-connectoren, skal du *give eksplicit* samtykke til Azure Active Directory-lejeradministratoren, da det er en del af [Microsoft Graph Security Authentication-kravene](https://aka.ms/graphsecurityauth). Dette samtykke kræver program-id og navn for Microsoft Graph Security Power BI-connectoren, som du også finder på [Azure-portalen](https://portal.azure.com):

   | Egenskab | Værdi |
   |----------|-------|
   | **Programnavn** | `MicrosoftGraphSecurityPowerBIConnector` |
   | **Program-id** | `cab163b7-247d-4cb9-be32-39b6056d4189` |
   |||

   For at give samtykke til connectoren skal din Azure AD-lejeradministrator følge et af disse trin:

   * [Giv lejeradministratoren samtykke til Azure AD-programmer](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).

   * Når din logikapp køres første gang, kan din app anmode om samtykke fra din Azure AD-lejeradministrator via [funktionen til programsamtykke](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).
   
* Den brugerkonto, der bruges til at logge på for at oprette forbindelse til Microsoft Graph Security Power BI-connectoren, skal være medlem af rollen Security Reader Limited i Azure AD (enten Security Reader eller Security Administrator). Følg trinnene i afsnittet [Tildel Azure AD-roller til brugere](https://docs.microsoft.com/graph/security-authorization#assign-azure-ad-roles-to-users). 

## <a name="using-the-microsoft-graph-security-connector"></a>Brug af Microsoft Graph Security-connectoren

Følg disse trin for at bruge **Microsoft Graph Security**-connectoren:

1. Vælg **Hent data -> Flere…** på båndet **Hjem** i Power BI Desktop.
2. Vælg **Onlinetjenester** fra kategorierne i venstre side.
3. Klik på **Microsoft Graph Security (Beta)**.

    ![Hent data](media/desktop-connect-graph-security/GetData.PNG)
    
4. Vælg den version af Microsoft Graph API, du vil sende forespørgsler til, i vinduet **Microsoft Graph Security**. Du kan vælge mellem v1.0 og beta.

    ![Vælg en version](media/desktop-connect-graph-security/selectVersion.PNG)
    
5. Log på din Azure Active Directory-konto, når du bliver bedt om det. Denne konto skal have rollen **Security Reader**, som det blev nævnt i forudsætningerne herover.

    ![Log på](media/desktop-connect-graph-security/SignIn.PNG)
    
6. Hvis du er lejeradministrator, **og** hvis du endnu ikke har givet samtykke til Microsoft Graph Security Power BI-connectoren (program) ifølge forudsætningerne, får du vist følgende dialogboks. Husk at vælge "**Samtykke på vegne af din organisation**".

    ![Administratorsamtykke](media/desktop-connect-graph-security/AdminConsent.PNG)
    
7. Når du er logget på, kan du se følgende vindue, der angiver, om du er blevet godkendt. Vælg **Opret forbindelse**.

    ![Logget på](media/desktop-connect-graph-security/SignedIn.PNG)
    
8. Når du har oprettet forbindelse, vises vinduet **Navigator** på følgende måde, og objekterne vises som beskeder osv. De er tilgængelige i [Microsoft Graph Security API](https://aka.ms/graphsecuritydocs) for den version, du valgte i det foregående trin. Vælg et eller flere objekter, du kan importere og bruge i **Power BI Desktop**. Klik på **Indlæs** for at komme til resultatet, som er beskrevet på trin 10.

   ![Navigationstabel](media/desktop-connect-graph-security/NavTable.PNG)
    
9. Hvis du vil foretage en avanceret forespørgsel i Microsoft Graph Security API, skal du vælge funktionen **Angiv brugerdefineret URL-adresse til Microsoft Graph Security for at filtrere resultaterne**. Det giver dig mulighed for at foretage en [OData.Feed](https://docs.microsoft.com/power-bi/desktop-connect-odata)-forespørgsel til Microsoft Graph Security API med de tilladelser, der kræves for at få adgang til API'en.

   > [!NOTE]
   > Den serviceUri, der bruges som eksempel herunder, er `https://graph.microsoft.com/v1.0/security/alerts?$filter=Severity eq 'High'`. Se [Graph-understøttede ODATA-forespørgselsparametre](https://docs.microsoft.com/graph/query-parameters) for at bygge forespørgsler, der kan filtrere, sortere eller hente de seneste resultater.

   ![OData-feed](media/desktop-connect-graph-security/ODataFeed.PNG)
    
   Når du vælger **Invoke**, vil OData.Feed-funktionen foretage et kald til API'en, der åbner Forespørgselseditor, så du kan filtrere og finindstille det datasæt, du vil bruge, og derefter indlæse dette finindstillede datasæt i Power BI Desktop.

10. I følgende billede kan du se resultatvinduet for de Microsoft Graph Security-objekter, du oprettede forespørgslen for.

   ![Resultat](media/desktop-connect-graph-security/Result.PNG)
    

Du er nu klar til at bruge de data, der er importeret fra Microsoft Graph Security-connectoren, i Power BI Desktop til at oprette visualiseringer og rapporter eller interagere med andre data, som du måske vil oprette forbindelse til og importere, f.eks. andre Excel-projektmapper, databaser eller en hvilken som helst anden datakilde.

## <a name="next-steps"></a>Næste trin
* Se Power BI-eksempler og -skabeloner ved hjælp af denne connector under [Microsoft Graph Security GitHub Power BI-eksemplerne](https://aka.ms/graphsecuritypowerbiconnectorsamples).

* Se nogle brugerscenarier og yderligere oplysninger i [dette blogindlæg om Microsoft Graph Security Power BI-connector](https://aka.ms/graphsecuritypowerbiconnectorblogpost).

* Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder i følgende ressourcer:

    * [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)
    * [Datakilder i Power BI Desktop](desktop-data-sources.md)
    * [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
    * [Opret forbindelse til Excel-projektmapper i Power BI Desktop](desktop-connect-excel.md)
    * [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)
