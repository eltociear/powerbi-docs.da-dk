---
title: "Find Power BI-brugere, der er logget på"
description: "Hvis du er en lejeradministrator, og du vil se, hvem der er logget på Power BI, kan du bruge Azure Active Directory-adgang og anvendelsesrapporter til at skabe synlighed."
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
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: 55caee3b289f187d6b955c216098313b483956f5
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/23/2017
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Find Power BI-brugere, der er logget på
Hvis du er en lejeradministrator, og du vil se, hvem der er logget på Power BI, kan du bruge Azure Active Directory-adgang og anvendelsesrapporter til at skabe synlighed.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

Du kan få adgang til aktivitetsrapporten i den [nye](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins) og den [klassiske](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) webportal i Azure Active Directory (Azure AD). Mens videoen ovenfor bruger den klassiske portal som et eksempel, fremhæves den nye portal i denne artikel.

> [!NOTE]
> Denne aktivitetsrapport indeholder både Power BI (gratis)- og Pro-brugere, men identificerer dem ikke efter hvilken licens, de har.
> 
> 

## <a name="requirements"></a>Krav
Følgende er kravene for at få vist logonaktivitetsrapporten.

* Brugere, der har rollen Global administrator, Sikkerhedsadministrator eller Sikkerhedslæser, kan få adgang til dataene.
* Alle brugere (ikke-administratorer) har adgang til deres egne logon.
* Din lejer skal have en Azure AD Premium-licens tilknyttet for at få vist alle logonaktivitetsrapporter.

## <a name="using-the-azure-portal-to-view-sign-ins"></a>Brug Azure-portalen til at få vist logonaktivitet
Du kan bruge Azure AD-portalen til at få vist logonaktivitet.

1. Gå til **Azure-portalen**, og vælg **Azure Active Directory**.
2. Under **Aktivitet** skal du vælge **Logonaktivitet**.
   
    ![](media/service-admin-access-usage/azure-portal-sign-ins.png)
3. Filtrer programmet efter enten **Microsoft Power BI** eller **Power BI Gateway**, og vælg **Anvend**.
   
    **Microsoft Power BI** er til logonaktivitet relateret til tjenesten, mens **Power BI Gateway** er specifik logonaktivitet for jeres datagateway i det lokale miljø.
   
    ![](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Eksportér dataene
Du har to indstillinger til eksport af logondataene. Du kan enten gøre dette ved at downloade en CSV-fil, eller du kan bruge PowerShell.

### <a name="download-csv"></a>Download csv
I skærmbilledet Aktivitet kan du vælge **Download** på værktøjslinjen. Dette vil download en csv-fil for de data, der i øjeblikket er filtreret.

![](media/service-admin-access-usage/download-sign-in-data-csv.png)

### <a name="powershell"></a>PowerShell
Du kan bruge PowerShell til at eksportere logondataene. Et [eksempel](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script) er tilgængeligt i Azure AD-dokumentationen.

> [!NOTE]
> Hvis PowerShell-eksemplet skal kunne fungere, skal du sørge for at følge [betingelserne for at få adgang til Azure AD-rapporterings-API'en](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-reporting-api-prerequisites).
> 
> 

## <a name="data-retention"></a>Dataopbevaring
Data, der er relateret til logonaktivitet, kan være tilgængelige i op til 30 dage. Du kan finde flere oplysninger i [Politikker til opbevaring af Azure Active Directory-rapport](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention).

## <a name="next-steps"></a>Næste trin
[Logonaktivitetsrapporter i Azure Active Directory-portalen (ny portal)](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins)  
[Få vist dine adgangs- og brugsrapporter (klassisk portal)](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports#view-or-download-a-report)  
[Logoneksempel i et PowerShell-script](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script)  
[Politikker til opbevaring af Azure Active Directory-rapport](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention)  
[Brug af overvågning i din organisation](service-admin-auditing.md)  
[Aktivering af den udvidede Pro-prøveversion](service-extended-pro-trial.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

