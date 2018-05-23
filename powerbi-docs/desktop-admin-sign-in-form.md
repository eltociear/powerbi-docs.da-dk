---
title: Sådan kan administratorer administrere logon-formularen i Power BI Desktop
description: Find ud af, hvordan du kan administrere den første logon-formular, når Power BI Desktop åbnes.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
ms.openlocfilehash: 98bf9579ae7ee551634eed765138c0e78156464c
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2018
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

