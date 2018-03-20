---
title: Brug en alternativ mailadresse
description: Brug en alternativ mailadresse
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 03/08/2018
ms.author: maghan
LocalizationGroup: Troubleshooting
ms.openlocfilehash: adc78cceb8a6b6edd06896e53a1a64cf0d28b2b8
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2018
---
# <a name="using-an-alternate-email-address"></a>Brug en alternativ mailadresse
Som standard bruges den mailadresse, du brugte ved tilmeldingen til Power BI, til at sende dig opdateringer omkring aktiviteter i Power BI.  Hvis nogen for eksempel sender en invitation til dig om deling af indhold, sendes den til denne mailadresse.

Nogle gange vil du have disse mails sendt til en alternativ mailadresse i stedet for til den mailadresse, du oprindeligt brugte ved tilmeldingen til Power BI.

## <a name="updating-through-office-365-personal-info-page"></a>Opdater via siden med personlige oplysninger i Office 365
1. Gå til din [side med personlige oplysninger i Office 365](https://portal.office.com/account/#personalinfo).  Hvis du bliver bedt om at logge på, skal du logge på med den mailadresse og adgangskode, du bruger til Power BI.
2. Klik på redigeringslinket i sektionen med kontaktoplysninger.  
   
   > [!NOTE]
   > Hvis der ikke vises et redigeringslink, administreres din mailadresse af din Office 365-administrator, og du skal kontakte vedkommende for at få opdateret din mailadresse.
   > 
   > 
   
   ![](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)
3. I feltet Alternativ mailadresse kan du angive den mailadresse, som opdateringer fra Power BI skal sendes til.

> [!NOTE]
> Når du ændrer denne indstilling, er det stadig den oprindelige mailadresse, der bruges til at sende oplysninger om opdateringer af tjenesten, nyhedsbreve og andre typer kampagneoplysninger.  Disse sendes altid til den mailadresse, du oprindeligt brugte ved tilmeldingen til Power BI.
> 
> 

## <a name="updating-through-azure-active-directory"></a>Opdatering via Azure Active Directory
Når du skal registrere et integreringstoken til AAD (Azure Active Directory) til Power BI, kan du bruge tre forskellige typer mails. De tre forskellige typer er:

* hovedmailadressen, der er knyttet til en brugers AAD-konto
* UPN-mailadressen (UserPrincipalName – brugerens hovednavn)
* matrixattributten for den "anden" mailadresse

Power BI vælger, hvilken mail der skal bruges, på baggrund af følgende kriterier:
1.  Hvis mailattributten i AAD-lejerens brugerobjekt er til stede, så bruger Power BI denne mailattribut til mailadressen
2.  Hvis UPN-mailen *ikke* er en mailadresse på domænet **\*.onmicrosoft.com** (oplysningerne efter "@"-symbolet), så bruger Power BI denne mailattribut til mailadressen
3.  Hvis matrixattributten for den anden "mail" i AAD-brugerobjektet til stede, så bruges den første mail på denne liste (da der kan være en liste over mails i denne attribut)
4. Hvis ingen af ovenstående betingelser er til stede, så bruges UPN-adressen

## <a name="updating-with-powershell"></a>Opdater via PowerShell
Du kan også opdatere den alternative mailadresse via PowerShell til Azure Active Directory. Det gør du med kommandoen [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser).

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

Du kan finde flere oplysninger under [Azure Active Directory PowerShell version 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

