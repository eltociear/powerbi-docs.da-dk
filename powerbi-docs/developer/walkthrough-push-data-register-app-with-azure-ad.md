---
title: Registrer et program i Azure AD
description: Gennemgang – overfør data til et datasæt – registrer et program i Azure AD
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: a3154a7b74d196f3c0aa2969e7c25bf56000a662
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762024"
---
# <a name="step-1-register-an-app-with-azure-ad"></a>Trin 1: Registrer et program i Azure AD

Denne artikel er en del af en trinvis gennemgang af, hvordan du [sender data til et datasæt](walkthrough-push-data.md).

Det første, du skal gøre for at overføre data til et Power BI-datasæt, er at registrere dit program i Azure AD. Det skal du gøre for at få et **klient-id**, som identificerer dit program i Azure AD. Uden et **klient-id** kan dit program ikke godkendes i Azure AD.

> **BEMÆRK**! Inden du registrerer et program til Power BI, skal du [tilmelde dig Power BI](create-an-azure-active-directory-tenant.md).

Nedenfor kan du se, hvordan du registrerer et program i Azure AD.

## <a name="register-an-app-in-azure-ad"></a>Registrer et program i Azure AD

1. Gå til dev.powerbi.com/apps.
2. Klik på **Log på med din eksisterende konto**, og log på din Power BI-konto.
3. Angiv et **navn på programmet**, f.eks. "Prøveprogram til overførsel af data".
4. Under **Programtype** skal du vælge **Oprindeligt program**.
5. Angiv en **URL-adresse til omdirigering**, f.eks **https://login.live.com/oauth20_desktop.srf**. Når du har en **oprindelig klientapp**, giver en URI til omdirigering **Azure AD** flere oplysninger om det program, der skal godkendes. Den Uri, der er standard for et klient-program, er https://login.live.com/oauth20_desktop.srf.
6. I **Vælg de API'er, der skal opnås adgang til** skal du vælge **Læs og skriv alle datasæt**. Hvis du vil se en liste over alle tilladelser i Power BI-programmet, skal du gå til [Tilladelser i Power BI](power-bi-permissions.md).
7. Klik på **Registrer app**, og gem det **klient-id**, der oprettes. Et **klient-id** identificerer programmet i Azure AD.

Nedenfor kan du se, hvordan siden **Registrer et program til Power BI** bør se ud:

![Registrer program](media/walkthrough-push-data-register-app-with-azure-ad/powerbi-developer-sample-register-app.png)

På næste trin kan du se, hvordan du [får en adgangstoken til godkendelse](walkthrough-push-data-get-token.md).

[Næste trin >](walkthrough-push-data-get-token.md)

## <a name="next-steps"></a>Næste trin

[Tilmeld dig Power BI](create-an-azure-active-directory-tenant.md)  
[Hent et adgangstoken til godkendelse](walkthrough-push-data-get-token.md)  
[Gennemgang: Overfør data til et datasæt](walkthrough-push-data.md)  
[Registrer et program](register-app.md)  
[Oversigt over Power BI REST-API'en](overview-of-power-bi-rest-api.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)