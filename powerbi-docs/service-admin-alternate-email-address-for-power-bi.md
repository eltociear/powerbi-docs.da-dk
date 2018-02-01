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
ms.date: 08/09/2017
ms.author: maghan
ms.openlocfilehash: dd9e146b22c95d8c915ea653ee287bb7a51e6b06
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/30/2018
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

## <a name="updating-with-powershell"></a>Opdater via PowerShell
Du kan også opdatere den alternative mailadresse via PowerShell til Azure Active Directory. Det gør du med kommandoen [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser).

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

Du kan finde flere oplysninger under [Azure Active Directory PowerShell version 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

