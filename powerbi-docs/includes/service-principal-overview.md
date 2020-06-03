---
title: Overblik over tjenesteprincipal
description: Overblik over tjenesteprincipal
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 04/05/2020
ms.custom: include file
ms.openlocfilehash: 8482278d9054228dedafb6bd1b37368f5a4b5dce
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315759"
---
Tjeneste principalen er en godkendelsesmetode, der kan bruges til at lade et Microsoft Azure AD-program få adgang indhold og API'er i Power BI-tjenesten.

Når du opretter en Azure Active Directory-app, oprettes der et [tjenesteprincipalobjekt](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object). Tjenesteprincipalobjektet, der også blot kaldes *tjenesteprincipal*, gør det muligt for Microsoft Azure AD at godkende din app. Når appen er godkendt, kan den få adgang til Microsoft Azure AD-lejerressourcer.

For at kunne godkende skal tjenesteprincipalen bruge Microsoft Azure AD-appens *program-id* og et af følgende:

* Programhemmelighed
* Certifikat