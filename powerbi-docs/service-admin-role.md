---
title: Beskrivelse af rollen som Power BI-administrator
description: I denne artikel beskrives rollen som Power BI-tjenesteadministrator, og hvordan den kan bruges i din organisation.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: a6121ca16250de9765557b9c9acbf73b513723ee
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/02/2019
ms.locfileid: "74699906"
---
# <a name="understanding-the-power-bi-service-administrator-role"></a>Om rollen Power BI-tjenesteadministrator

Få mere at vide om, hvordan du kan bruge rollen Power BI-tjenesteadministrator i organisationen. Brugere med denne rolle har fuld kontrol over en Power BI-lejer og de tilhørende administrative funktioner (undtagen licensering).

Rollen Power BI-tjenesteadministrator kan tildeles brugere, som skal have adgang til Power BI-administrationsportalen uden også at tildele dem nogen anden administrativ adgang i Office 365.

Administratorer af Office 365-brugeradministration tildeler brugere rollen Power BI-tjenesteadministrator i Microsoft 365 Administration eller ved hjælp af et PowerShell-script. Når en bruger er tildelt, har vedkommende adgang til [Power BI-administrationsportalen](service-admin-portal.md). Her har vedkommende adgang til lejerbaserede forbrugsdata og kan kontrollere lejerbaseret forbrug af Power BI-funktioner.

## <a name="limitations-and-considerations"></a>Begrænsninger og overvejelser

Rollen Power BI-tjenesteadministrator giver ikke adgang til følgende funktioner:

* Mulighed for at redigere brugere og licenser via Microsoft 365 Administration,

* Adgang til overvågningslogge. Du kan finde flere oplysninger under [Brug af overvågning i din organisation](service-admin-auditing.md).

## <a name="assign-users-to-the-admin-role-in-office-365"></a>Tildel brugere administratorrollen via Office 365

Følg disse trin for at tildele brugere rollen Power BI-administrator via Microsoft 365 Administration.

1. I [Microsoft 365 Administration](https://portal.office.com/adminportal/home#/homepage) skal du vælge **Brugere** > **Aktive brugere**.

    ![Microsoft 365 Administration](media/service-admin-role/powerbi-admin-users.png)

1. Vælg den bruger, du vil tildele rollen.

1. Under **Roller** skal du vælge **Rediger**.

    ![Rediger roller](media/service-admin-role/powerbi-admin-edit-roles.png)

1. Vælg **Brugerdefineret administrator** > **Power BI-tjenesteadministrator**.

    ![Power BI Service Administrator](media/service-admin-role/powerbi-admin-role.png)

1. Vælg **Gem**, og derefter **Luk**.

Du bør se, at den pågældende bruger er tildelt rollen **Power BI-tjenesteadministrator** på oversigten.

![Roller](media/service-admin-role/powerbi-admin-role-set.png)

## <a name="assign-users-to-the-admin-role-with-powershell"></a>Tildel brugere administratorrollen via PowerShell

Du kan også tildele brugere roller ved hjælp af PowerShell. Brugere administreres i Azure Active Directory (Azure AD). Hvis du ikke allerede har Azure AD PowerShell-modulet, skal du [downloade og installere den nyeste version](https://www.powershellgallery.com/packages/AzureAD/).

1. Først skal du oprette forbindelse til Azure AD:
   ```
   PS C:\Windows\system32> Connect-AzureAD
   ```

1. Derefter skal du hente **ObjectId** for rollen **Power BI-tjenesteadministrator**. Du kan køre [Get-AzureADDirectoryRole](/powershell/module/azuread/get-azureaddirectoryrole) for at hente **ObjectId**

    ```
    PS C:\Windows\system32> Get-AzureADDirectoryRole

    ObjectId                             DisplayName                        Description
    --------                             -----------                        -----------
    00f79122-c45d-436d-8d4a-2c0c6ca246bf Power BI Service Administrator     Full access in the Power BI Service.
    250d1222-4bc0-4b4b-8466-5d5765d14af9 Helpdesk Administrator             Helpdesk Administrator has access to perform..
    3ddec257-efdc-423d-9d24-b7cf29e0c86b Directory Synchronization Accounts Directory Synchronization Accounts
    50daa576-896c-4bf3-a84e-1d9d1875c7a7 Company Administrator              Company Administrator role has full access t..
    6a452384-6eb9-4793-8782-f4e7313b4dfd Device Administrators              Device Administrators
    9900b7db-35d9-4e56-a8e3-c5026cac3a11 AdHoc License Administrator        Allows access manage AdHoc license.
    a3631cce-16ce-47a3-bbe1-79b9774a0570 Directory Readers                  Allows access to various read only tasks in ..
    f727e2f3-0829-41a7-8c5c-5af83c37f57b Email Verified User Creator        Allows creation of new email verified users.
    ```

    I dette tilfælde er rollen **ObjectId** 00f79122-c45d-436d-8d4a-2c0c6ca246bf.

1. Hent derefter brugerens **ObjectId**. Det finder du ved at køre [Get-AzureADUser](/powershell/module/azuread/get-azureaduser).

    ```
    PS C:\Windows\system32> Get-AzureADUser -ObjectId 'tim@contoso.com'

    ObjectId                             DisplayName UserPrincipalName      UserType
    --------                             ----------- -----------------      --------
    6a2bfca2-98ba-413a-be61-6e4bbb8b8a4c Tim         tim@contoso.com        Member
    ```

1. For at føje medlemmet til rollen skal du køre [Add-AzureADDirectoryRoleMember](/powershell/module/azuread/add-azureaddirectoryrolemember).

    | Parameter | Beskrivelse |
    | --- | --- |
    | ObjectId |Rollen ObjectId. |
    | RefObjectId |Medlemmernes ObjectId. |

    ```powershell
    Add-AzureADDirectoryRoleMember -ObjectId 00f79122-c45d-436d-8d4a-2c0c6ca246bf -RefObjectId 6a2bfca2-98ba-413a-be61-6e4bbb8b8a4c
    ```

## <a name="next-steps"></a>Næste trin

[Administrer Power BI i din organisation](service-admin-administering-power-bi-in-your-organization.md)  
[Power BI-administrationsportal](service-admin-portal.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)