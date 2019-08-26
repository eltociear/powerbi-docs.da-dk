---
title: Konfigurer iOS-mobilapps, så du kan få fjernadgang til en rapportserver
description: Få mere at vide om, hvordan du kan konfigurere iOS-mobilapps eksternt for din rapportserver.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 08/08/2019
ms.author: maggies
ms.openlocfilehash: 7727157a9227a5340fccf0af129d87f69edd8c72
ms.sourcegitcommit: d12bc6df16be1f1993232898f52eb80d0c9fb04e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/13/2019
ms.locfileid: "68994803"
---
# <a name="configure-power-bi-ios-mobile-app-access-to-a-report-server-remotely"></a>Konfigurer Power BI iOS-mobilapps til at få ekstern adgang til en rapportserver

I denne artikel kan du se, hvordan du bruger din organisations MDM-værktøj til at konfigurere adgang til en rapportserver for Power BI iOS-mobilapps. Det kræver, at it-administratorer opretter en appkonfigurationspolitik, hvor de nødvendige oplysninger pushes til appen. 

 Når rapportserverforbindelsen allerede er oprettet, kan brugerne af Power BI iOS-mobilappen nemmere oprette forbindelse til organisationens rapportserver. 

## <a name="create-the-app-configuration-policy-in-mdm-tool"></a>Opret appkonfigurationspolitikken i MDM-værktøjet 

Som administrator skal du følge disse trin i Microsoft Intune for at oprette appkonfigurationspolitikken. Trinnene og oprettelsen af appkonfigurationspolitikken kan være anderledes i andre MDM-værktøjer. 

1. Opret forbindelse til dit MDM-værktøj. 
2. Opret og navngiv en ny appkonfigurationspolitik. 
3. Vælg, hvilke brugere appkonfigurationspolitikken skal distribueres til. 
4. Opret nøgle/værdi-par. 

I følgende tabel kan du se disse par.

|Nøgle  |Type  |Beskrivelse  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ServerURL-adresse | Streng | URL-adresse til rapportserver <br> Skal starte med http/https |
| com.microsoft.powerbi.mobile.ServerBrugernavn | Streng | [valgfri] <br> Det brugernavn, der skal bruges til at oprette forbindelse til serveren. <br> Hvis der ikke findes et brugernavn, vil appen bede brugeren skrive brugernavnet til forbindelsen.| 
| com.microsoft.powerbi.mobile.ServerVist navn | Streng | [valgfri] <br> Standardværdien er "Rapportserver" <br> Et navn, der bruges til at repræsentere serveren i appen | 
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boolesk | Standardværdien er True <br>Når værdien er angivet til "True", tilsidesætter den alle eksisterende rapportserverdefinitioner på mobilenheden. Eksisterende servere, der allerede er konfigureret, slettes. <br> Dette forhindrer også, at brugeren kan fjerne konfigurationen. <br> Hvis indstillingen er angivet til “False”, tilføjes de overførte værdier, og eksisterende indstillinger ændres ikke. <br> Hvis den samme URL-adresse allerede er konfigureret i mobilappen, forbliver konfigurationen, som den er. Appen beder ikke brugeren om at godkende igen for den samme server. |

Her er et eksempel på, hvordan du indstiller konfigurationspolitikken ved hjælp af Intune.

![Intune-konfiguratonsindstillinger](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configuration-settings.png)

## <a name="end-users-connecting-to-a-report-server"></a>Slutbrugere opretter forbindelse til en rapportserver

 Lad os sige, at du publicerer appkonfigurationspolitikken for en distributionsliste. Når brugerne og enhederne på den pågældende distributionsliste starter iOS-mobilappen, oplever de følgende: 

1. De får vist en meddelelse om, at mobilappen er konfigureret med en rapportserver og skal trykke på **Log på**.

    ![Log på rapportserveren](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-sign-in.png)

2.  Detaljerne om rapportserveren er allerede udfyldt på siden **Opret forbindelse til server**. De trykker på **Opret forbindelse**.

    ![Rapportserveroplysningerne er udfyldt](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configure-connect-server.png)

3. De indtaster en adgangskode som godkendelse og trykker derefter på **Log på**. 

    ![Rapportserveroplysningerne er udfyldt](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-address.png)

Nu kan de få vist og interagere med KPI'er og Power BI-rapporter på rapportserveren.

## <a name="next-steps"></a>Næste trin

- [Aktivér fjernadgang til Power BI - Mobil med Azure AD-programproxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-integrate-with-power-bi)
- [Administratoroversigt](admin-handbook-overview.md)  
- [Installer Power BI-rapportserver](install-report-server.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

