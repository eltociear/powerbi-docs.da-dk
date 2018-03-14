---
title: "Sådan kan administratorer administrere logon-formularen i Power BI Desktop"
description: "Find ud af, hvordan du kan administrere den første logon-formular, når Power BI Desktop åbnes."
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 519f8b56b5086292addf577d969a707a6d6efcc8
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/09/2018
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Sådan kan administratorer administrere logon-formularen i Power BI Desktop
Første gang Power BI Desktop startes, vises der en logon-formular. Du kan udfylde oplysninger, eller du kan logge på Power BI for at fortsætte. Administratorer kan administrere denne formular ved brug af en registreringsnøgle. 

![Formular til første logon til Power BI](media/desktop-admin-sign-in-form/sign-in-form.png)

Administratorer kan bruge følgende registreringsnøgle til at deaktivere logon-formularen. Den kan også skubbes ud ved brug af globale politikker for hele organisationen.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

En værdi på 0 deaktiverer dialogen.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

