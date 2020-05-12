---
title: Brug af den samme konto til Power BI og Azure
description: Sådan bruger du samme kontologon til Power BI og Azure
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 4f1f8947827500ec89d189e17f8ab2189caaff93
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/05/2020
ms.locfileid: "74698572"
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>Brug af den samme konto til Power BI og Azure

Hvis du både bruger Power BI og Azure, kan du med fordel bruge samme logon til begge tjenester, så du ikke er nødt til at indtaste din adgangskode to gange.

Power BI logger dig på med din organisationskonto, der er knyttet til din arbejds- eller skolemailadresse.  Azure logger dig på med enten en Microsoft-konto eller din organisationskonto.

Hvis du vil bruge samme logon til både Azure og Power BI, skal du logge på Azure med din organisationskonto.

**Hvad sker der, hvis jeg allerede logger på Azure med min Microsoft-konto?**

Du kan tilføje din organisationskonto som en medadministrator i Azure ved at benytte denne fremgangsmåde:

1. Log på [Azure Portal](https://portal.azure.com/). Hvis du bruger flere Azure-mapper, skal du vælge **Abonnementer** og derefter filtrere for kun at få vist den relevante mappe og de abonnementer, du vil redigere.

1. Vælg **Adgangskontrol (IAM)** i navigationsruden, og vælg derefter **Tilføj** \> **Tilføj medadministrator**.

    ![Tilføj en medadministrator i Azure Portal](media/service-admin-how-to-use-the-same-account-as-azure/add-co-administrator.png)

1. Angiv den mailadresse, der er tilknyttet din organisationskonto, og vælg **Tilføj**.

1. Næste gang du logger på Azure-administrationsportalen, skal du bruge din organisationsmailadresse.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
