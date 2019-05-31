---
title: Brug en alternativ mailadresse
description: Brug en alternativ mailadresse
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 88432f55fc8cfeefa07b66ea68437bbb23f12531
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906634"
---
# <a name="use-an-alternate-email-address"></a>Brug en alternativ mailadresse

Når du tilmelder dig Power BI, angiver du en mailadresse. Power BI bruger som standard denne adresse til at sende dig opdateringer om aktiviteter i tjenesten. Hvis nogen for eksempel sender en invitation til deling til dig, sendes den til denne adresse.

I nogle tilfælde vil du måske have disse mails sendt til en alternativ mailadresse i stedet for den, du har tilmeldt dig med. I denne artikel forklares det, hvordan du angiver en alternativ adresse i Office 365 og PowerShell. I artiklen forklares også, hvordan Azure Active Directory (Azure AD) løser en mailadresse.

> [!NOTE]
> Angivelse af en alternativ mailadresse påvirker ikke den mailadresse, som Power BI bruger til tjenesteopdateringer, nyhedsbreve og anden kommunikation. Disse meddelelser sendes altid til mailadressen, du brugte, da du tilmeldte dig Power BI.

## <a name="use-office-365"></a>Brug Office 365

Følg disse trin for at angive en alternativ adresse i Office 365.

1. Åbn [siden med personlige oplysninger i Office 365](https://portal.office.com/account/#personalinfo). Hvis appen beder dig om, kan du logge på med den mailadresse og adgangskode, du bruger til Power BI.

1. Vælg **Personlige oplysninger** i menuen til venstre.

1. I afsnittet **Kontaktoplysninger** skal du vælge **Rediger**.

    Hvis du ikke kan redigere dine oplysninger, det betyder, at din Office 365-administratoren administrerer din mailadresse. Kontakt din administrator for at opdatere din e-mail-adresse.

    ![Kontaktoplysninger](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)

1. I den **alternativ mail** skal du angive den mailadresse, du gerne vil have en Office 365, der skal bruges til Power BI-opdateringer.

## <a name="use-powershell"></a>Brug PowerShell

Hvis du vil angive en alternativ adresse i PowerShell, skal du bruge kommandoen [Set-AzureADUser](/powershell/module/azuread/set-azureaduser/).

```powershell
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

## <a name="email-address-resolution-in-azure-ad"></a>Løsning af mailadresse i Azure AD

Til at hente en Azure AD integreringstoken til Power BI, kan du bruge én af tre forskellige typer mailadresser:

* Den primære mailadresse, der er knyttet til en brugers Azure AD-konto

* UPN-mailadressen (UserPrincipalName – brugerens hovednavn)

* Matrixattributten for *anden mailadresse*

Power BI vælger, hvilken mail der bruges, på baggrund af følgende sekvens:

1. Hvis mailattributten i Azure AD-lejerens brugerobjekt er til stede, så bruger Power BI denne mailattribut til mailadressen.

1. Hvis UPN-mailen *ikke* er en mailadresse på domænet **\*.onmicrosoft.com** (oplysningerne efter "\@"-symbolet), bruger Power BI denne mailattribut til mailadressen.

1. Hvis den *andre mailadresse* matrixattributten i Azure AD-brugerobjektet er til stede, Power BI bruger derefter den første mail på denne liste (da der kan være en liste over mails i denne attribut).

1. Hvis ingen af ovenstående betingelser er til stede, så bruger Power BI UPN-adressen.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)