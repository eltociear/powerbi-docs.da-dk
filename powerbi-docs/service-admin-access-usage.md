---
title: Find Power BI-brugere, der er logget på
description: Hvis du er en lejeradministrator, og du vil se, hvem der er logget på Power BI, kan du bruge Azure Active Directory-adgang og anvendelsesrapporter til at skabe synlighed.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/31/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: dfd9aab419d0a097721c4f2b49e382c11be82541
ms.sourcegitcommit: 0611860a896e636ceeb6e30ce85243bfd8e7b61d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/01/2018
ms.locfileid: "50909496"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Find Power BI-brugere, der er logget på

Hvis du er lejeradministrator og gerne vil se, hvem der er logget på Power BI, skal du bruge [adgangs- og brugsrapporter i Azure Active Directory](/azure/active-directory/reports-monitoring/concept-sign-ins) til at få indsigt.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Aktivitetsrapporten indeholder nyttige oplysninger, men du kan ikke se, hvilken type licens hver bruger har. Brug Office 365 Administration til at få vist licenser.

## <a name="requirements"></a>Krav

Alle brugere (herunder personer, der ikke er administratorer) kan se en rapport over deres egne logon, men du skal opfylde følgende krav for at få vist en rapport for alle brugere.

* Din lejer skal have en Azure AD Premium-licens tilknyttet.

* Du skal have en af følgende roller: Global administrator, Sikkerhedsadministrator eller Sikkerhedslæser.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Brug Azure Portal til at få vist logon

Følg disse trin for at få vist logonaktivitet.

1. På **Azure Portal** skal du vælge **Azure Active Directory**.

1. Under **Overvågning** skal du vælge **Logon**.
   
    ![Azure AD-logon](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Filtrer programmet efter enten **Microsoft Power BI** eller **Power BI Gateway**, og vælg **Anvend**.

    **Microsoft Power BI** filtrerer efter logonaktivitet relateret til tjenesten, hvorimod **Power BI Gateway** filtrerer efter logonaktivitet, der er specifik for datagatewayen i det lokale miljø.
   
    ![Filtrering efter logon](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Eksportér dataene

Du har to muligheder for at eksportere logondataene: Download en csv-fil, eller brug PowerShell. Øverst i logonrapporten skal du vælge en af følgende muligheder:

* **Download** for at downloade en csv-fil for de data, der er filtreret i øjeblikket.

* **Script** for at downloade et PowerShell-script for de data, der er filtreret i øjeblikket. Du kan opdatere filteret i scriptet efter behov.

![Download csv-fil eller script](media/service-admin-access-usage/download-sign-in-data-csv.png)

## <a name="data-retention"></a>Dataopbevaring

Relaterede logondata er tilgængelige i op til 30 dage. Du kan finde flere oplysninger i [Politikker til opbevaring af Azure Active Directory-rapport](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Næste trin

[Brug af overvågning i din organisation](service-admin-auditing.md)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

