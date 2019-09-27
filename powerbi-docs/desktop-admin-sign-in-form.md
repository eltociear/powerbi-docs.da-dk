---
title: Sådan kan administratorer administrere logon-formularen i Power BI Desktop
description: Find ud af, hvordan du kan administrere den første logon-formular, når Power BI Desktop åbnes.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: 5c31277b640b16882bef5c5f2cd9c56b441ede82
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61329876"
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




Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

