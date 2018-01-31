---
title: "Distribuer Power BI-indhold til eksterne gæstebrugere med Azure AD B2B"
description: "Power BI kan integreres med Azure Active Directory Business-til-business (Azure AD B2B) for at tillade sikker distribution af Power BI-indhold til gæstebrugere uden for organisationen."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 12/07/2017
ms.author: maghan
ms.openlocfilehash: 36fb0838f9c712567d3fe14e7ba0c69d2da3adf4
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/30/2018
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Distribuer Power BI-indhold til eksterne gæstebrugere med Azure AD B2B

Power BI kan integreres med Azure Active Directory Business-til-business (Azure AD B2B) for at tillade sikker distribution af Power BI-indhold til gæstebrugere uden for organisationen, mens du stadig bevarer kontrollen over de interne data.

> [!VIDEO https://www.youtube.com/embed/xxQWEQ1NnlY]

> [!NOTE]
> Denne funktion er i øjeblikket ikke tilgængelig med Power BI-mobilapps. Du kan få vist Power BI-indhold, der deles med Azure AD B2B i en browser på en mobil enhed. 

## <a name="invite-guest-users"></a>Inviter gæstebrugere

Man kna invitere gæstebrugere til din Power BI-lejer på to måder: planlagte invitationer eller ad hoc-invitationer. Invitationer kræves kun første gang, en ekstern bruger inviteres til din organisation.

### <a name="planned-invites"></a>Planlagte invitationer

En planlagt invitation udføres i Microsoft Azure-portalen i Azure AD eller ved hjælp af PowerShell. Dette er den indstilling, du skal bruge, hvis du ved, hvilke brugere der skal inviteres. 

**Oprettelse af gæstebrugere i Azure AD-portalen kræver, at du er en lejeradministrator.**

1. Gå til [Azure-portalen](https://portal.azure.com), og vælg **Azure Active Directory**.

2. Gå til **Brugere og grupper** > **Alle brugere** > **Ny gæstebruger**.

    ![Azure AD-portalen – Ny gæstebruger](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

3. Angiv **mailadressen** og **den personlige meddelelse**.

    ![Azure AD-portalen – invitation til ny gæstebruger](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

4. Vælg **Inviter**.

Hvis du vil invitere mere end én gæstebruger, skal du bruge PowerShell. Du kan finde flere oplysninger i [Azure Active Directory B2B-samarbejdskode og PowerShell-eksempler](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-code-samples).

Gæstebrugeren skal vælge **Introduktion** i den invitation, de får på mail. Gæstebrugeren føjes derefter til lejeren.

![Mailinvitation til gæstebruger](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Ad hoc-invitationer

Du kan til enhver tid invitere en ekstern bruger ved at føje vedkommende til en apps adgangsliste, når du publicerer den.

![Ekstern bruger føjet til appens adgangsliste](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Gæstebrugeren modtager en mail, der angiver, at appen er blevet delt med vedkommende.

![Mail om, at appen er delt med gæstebrugeren](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

Gæstebrugeren skal logge på med sin mailadresse for organisationen. Han/hun vil blive bedt om at acceptere invitationen, når han/hun har logget på. Når gæstebrugeren er logget på, omdirigeres denne til appindholdet. Tilføj linket som bogmærke, eller gem mailen for at vende tilbage til appen.

## <a name="licensing"></a>Licensering

Gæstebrugeren skal have den korrekte licens for at få vist den delte app. Dette kan gøres på tre mulige måder.

### <a name="use-power-bi-premium"></a>Brug Power BI Premium

Tildeling af appens arbejdsområde til Power BI Premium-kapacitet gør det muligt for gæstebrugeren at bruge appen uden krav om en Power BI Pro-licens. Med Power BI Premium kan apps også drage fordel af andre funktioner, f.eks. øget opdateringshastighed, dedikeret kapacitet og store modelstørrelser.

![Brug Power BI Premium](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-power-bi-pro-license-to-guest-user"></a>Tildel Power BI Pro-licens til en gæstebruger

Tildeling af en Power BI Pro-licens til gæstebrugeren i din lejer gør det muligt for gæstebrugeren at se indholdet.

> [!NOTE]
> En Power BI Pro-licens fra din lejer gælder kun for gæstebrugere, når de får adgang til indhold i din lejer.

![Tildel Pro-licens fra din lejer](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Gæstebrugeren medtager sin egen Power BI Pro-licens

Gæstebrugeren har allerede en Power BI Pro-licens, der er tildelt i deres lejer.

![Gæstebrugeren medbringer sin egen licens](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="limitations"></a>Begrænsninger

* Eksterne B2B-gæster er udelukkende begrænset til forbrug af indhold. Eksterne B2B-gæster kan få vist apps, dashboards og rapporter samt eksportere data og oprette mailabonnementer på dashboards og rapporter. De kan ikke få adgang til arbejdsområder eller udgive deres eget indhold.
* Denne funktion er i øjeblikket ikke tilgængelig med Power BI-mobilapps. Du kan få vist Power BI-indhold, der deles med Azure AD B2B i en browser på en mobil enhed.
* Brug af gæstebrugere med Power BI understøttes ikke i suveræne clouds (offentlige myndigheder).

## <a name="next-steps"></a>Næste trin

Du kan få mere at vide, herunder hvordan sikkerhed på rækkeniveau fungerer, i [hvidbogen](https://aka.ms/powerbi-b2b-whitepaper).

Du kan finde oplysninger om Azure Active Directory B2B i [Hvad er Azure AD B2B-samarbejde?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)