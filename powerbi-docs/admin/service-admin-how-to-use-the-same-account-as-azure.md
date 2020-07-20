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
ms.openlocfilehash: fe93fa3f41cf1c340b31ce3c6f817f842f3039ff
ms.sourcegitcommit: c18130ea61e67ba111be870ddb971c6413a4b632
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/09/2020
ms.locfileid: "86161646"
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>Brug af den samme konto til Power BI og Azure

Hvis du både bruger Power BI og Azure, kan du med fordel bruge samme logon til begge tjenester, så du ikke er nødt til at indtaste din adgangskode to gange.

Power BI logger dig på med din organisationskonto, der er knyttet til din arbejds- eller skolemailadresse.  Azure logger dig på med enten en Microsoft-konto eller din organisationskonto.

Hvis du vil bruge samme logon til både Azure og Power BI, skal du logge på Azure med din organisationskonto.

**Hvad sker der, hvis jeg allerede logger på Azure med min Microsoft-konto?**

Du kan tilføje din organisationskonto som en medadministrator i Azure ved at benytte denne fremgangsmåde:

1. Log på [Azure Portal](https://portal.azure.com/). Hvis du bruger flere Azure-mapper, skal du vælge **Abonnementer** og derefter filtrere for kun at få vist den relevante mappe og de abonnementer, du vil redigere.

1. Vælg **Adgangskontrol (IAM)** i navigationsruden, og vælg derefter **Tilføj** \> **Tilføj medadministrator**.

    ![Skærmbillede af Adgangskontrol, hvor Tilføj en medadministrator er fremhævet.](media/service-admin-how-to-use-the-same-account-as-azure/add-co-administrator.png)

1. Angiv den mailadresse, der er tilknyttet din organisationskonto, og vælg **Tilføj**.

1. Næste gang du logger på Azure-administrationsportalen, skal du bruge din organisationsmailadresse.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
