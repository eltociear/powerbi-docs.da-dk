---
title: inkluderer fil
description: inkluderer fil
services: powerbi
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 05/31/2019
ms.author: mblythe
ms.openlocfilehash: 94b6959b6bcbf250e54a353e8b725b6c9e5a2e30
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448383"
---
## <a name="single-sign-on"></a>Enkeltlogon

Når du har publiceret et datasæt med Azure SQL DirectQuery til tjenesten, kan du aktivere enkeltlogon (SSO) via Azure Active Directory (Azure AD) OAuth2 for dine slutbrugere.

Du aktiverer SSO ved at gå til indstillinger for datasæt, åbne fanen **Datakilder** og markere feltet SSO.

![Dialogboksen Configure Azure SQL DQ (Konfigurer Azure SQL DQ)](media/direct-query-sso/sso-dialog.png)

Når indstillingen for enkeltlogon er aktiveret, og dine brugere får adgang til rapporter, som er baseret på datakilden, sender Power BI deres godkendte Azure AD-legitimationsoplysninger i forespørgslerne til Azure SQL-databasen eller data warehouse. På den måde kan Power BI overholde de sikkerhedsindstillinger, der er konfigureret på datakildeniveauet.

Indstillingen SSO gælder for alle datasæt, der bruger denne datakilde. Den påvirker ikke den godkendelsesmetode, der bruges til import af scenarier.

> [!Note]
> Azure MFA (Multi-Factor Authentication) understøttes ikke. Brugere, der gerne vil bruge SSO med Azure SQL DirectQuery, skal fritages fra MFA.