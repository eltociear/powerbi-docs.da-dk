---
title: Sådan kan administratorer administrere logon-formularen i Power BI Desktop
description: Find ud af, hvordan du kan administrere den første logon-formular, når Power BI Desktop åbnes.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: b1ab5188ba8f5ccf54589d359f6f8ced1ada3060
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/06/2020
ms.locfileid: "73878851"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Sådan kan administratorer administrere logon-formularen i Power BI Desktop
Første gang Power BI Desktop startes, vises der en logon-formular. Du kan udfylde oplysninger, eller du kan logge på Power BI for at fortsætte. Administratorer kan administrere denne formular ved brug af en registreringsnøgle. 

![Formular til første logon til Power BI](media/desktop-admin-sign-in-form/sign-in-form.png)

Administratorer kan bruge følgende registreringsnøgle til at deaktivere logonformularen. Den kan også sendes til en hel organisation ved hjælp af globale politikker.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```
Du kan også prøve følgende nøgle, som har været nyttig for nogle kunder baseret på deres konfigurationer:

```
Key: HKEY_CURRENT_USER\SOFTWARE\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

En værdi på 0 deaktiverer dialogen.




Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

