---
title: Sådan kan administratorer administrere logon-formularen i Power BI Desktop
description: Find ud af, hvordan du kan administrere den første logon-formular, når Power BI Desktop åbnes.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
ms.openlocfilehash: a61075993afaa75aea420f55babc773dec075f73
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280879"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Sådan kan administratorer administrere logon-formularen i Power BI Desktop
Første gang Power BI Desktop startes, vises der en logon-formular. Du kan udfylde oplysninger, eller du kan logge på Power BI for at fortsætte. Administratorer kan administrere denne formular ved brug af en registreringsnøgle. 

![Formular til første logon til Power BI](media/desktop-admin-sign-in-form/sign-in-form.png)

Administratorer kan bruge følgende registreringsnøgle til at deaktivere logonformularen. Den kan også sendes til en hel organisation ved hjælp af globale politikker.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

En værdi på 0 deaktiverer dialogen.

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

