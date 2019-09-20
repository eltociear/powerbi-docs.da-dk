---
title: Brug af den samme konto til Power BI og Azure
description: Sådan bruger du samme kontologon til Power BI og Azure
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: f9659ad657c4466ad58eb40d4a07916b46f9536a
ms.sourcegitcommit: 6a44cb5b0328b60ebe7710378287f1e20bc55a25
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/10/2019
ms.locfileid: "70877752"
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>Brug af den samme konto til Power BI og Azure

Hvis du både bruger Power BI og Azure, kan du med fordel bruge samme logon til begge tjenester, så du ikke er nødt til at indtaste din adgangskode to gange.

Power BI logger dig på med din organisationskonto, der er knyttet til din arbejds- eller skolemailadresse.  Azure logger dig på med enten en Microsoft-konto eller din organisationskonto.

Hvis du vil bruge samme logon til både Azure og Power BI, skal du logge på Azure med din organisationskonto.

**Hvad sker der, hvis jeg allerede logger på Azure med min Microsoft-konto?**

Du kan tilføje din organisationskonto som en medadministrator i Azure ved at benytte denne fremgangsmåde:

1. Log på [Azure Portal](http://portal.azure.com/). Hvis du bruger flere Azure-mapper, skal du vælge **Abonnementer** og derefter filtrere for kun at få vist den relevante mappe og de abonnementer, du vil redigere.

1. Vælg **Adgangskontrol (IAM)** i navigationsruden, og vælg derefter **Tilføj** \> **Tilføj medadministrator**.

    ![Tilføj en medadministrator i Azure Portal](media/service-admin-how-to-use-the-same-account-as-azure/add-co-administrator.png)

1. Angiv den mailadresse, der er tilknyttet din organisationskonto, og vælg **Tilføj**.

1. Næste gang du logger på Azure-administrationsportalen, skal du bruge din organisationsmailadresse.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
