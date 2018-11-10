---
title: Distribuer Power BI-indhold til eksterne gæstebrugere med Azure AD B2B
description: Power BI kan integreres med Azure Active Directory Business-til-business (Azure AD B2B) for at tillade sikker distribution af Power BI-indhold til gæstebrugere uden for organisationen.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: dded0f38ccc4c871bf402240aba25b11106bac09
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973206"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Distribuer Power BI-indhold til eksterne gæstebrugere med Azure AD B2B

Power BI kan integreres med Azure Active Directory Business-til-business (Azure AD B2B) for at tillade sikker distribution af Power BI-indhold til gæstebrugere uden for din organisation, mens du stadig bevarer kontrollen over de interne data.

## <a name="enable-access"></a>Aktivér adgang

Kontrollér, at funktionen [Eksport- og delingsindstillinger](service-admin-portal.md#export-and-sharing-settings) er aktiveret på Power BI-administratorportalen, før du inviterer gæstebrugere.

## <a name="who-can-you-invite"></a>Hvem kan du invitere?

Du kan invitere gæstebrugere med en hvilken som helst mailadresse, f.eks. gmail.com, outlook.com eller hotmail.com. I Azure AD B2B kaldes disse adresser for *sociale identiteter*.

## <a name="invite-guest-users"></a>Inviter gæstebrugere

Invitationer kræves kun første gang, en ekstern gæstebruger inviteres til din organisation. Der er to måder at invitere brugere på: planlagte invitationer og ad hoc-invitationer.

### <a name="planned-invites"></a>Planlagte invitationer

Brug en planlagt invitation, hvis du ved, hvilke brugere du vil invitere. Du kan sende invitationen ved hjælp af Azure Portal eller PowerShell. Du skal være en lejeradministrator for at invitere brugere.

Følg disse trin for at sende en invitation via Azure Portal.

1. På [Azure Portal](https://portal.azure.com) skal du vælge **Azure Active Directory**.

1. Under **Administrer** skal du gå til **Brugere** > **Alle brugere** > **Ny gæstebruger**.

    ![Azure AD-portalen – Ny gæstebruger](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

1. Angiv en **mailadresse** og **personlig meddelelse**.

    ![Azure AD-portalen – invitation til ny gæstebruger](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

1. Vælg **Inviter**.

Hvis du vil invitere mere end én gæstebruger, skal du bruge PowerShell. Du kan finde flere oplysninger i [Azure AD B2B-samarbejdskode og PowerShell-eksempler](/azure/active-directory/b2b/code-samples/).

Gæstebrugeren skal vælge **Introduktion** i den invitation, de får på mail. Gæstebrugeren føjes derefter til lejeren.

![Mailinvitation til gæstebruger](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Ad hoc-invitationer

Du kan når som helst invitere en ekstern bruger ved at føje personen til dit dashboard eller din rapport via delingsbrugergrænsefladen eller din app via adgangssiden. Her er et eksempel på, hvad du skal gøre, når du inviterer en ekstern bruger til at anvende en app.

![Ekstern bruger føjet til appens adgangsliste](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Gæstebrugeren modtager en mail, der angiver, at appen er blevet delt med vedkommende.

![Mail om, at appen er delt med gæstebrugeren](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

Gæstebrugeren skal logge på med sin mailadresse for organisationen. Han/hun vil blive bedt om at acceptere invitationen, når han/hun har logget på. Når gæstebrugeren er logget på, omdirigeres denne til appindholdet. For at vende tilbage til appen kan vedkommende tilføje linket som bogmærke eller gemme mailen.

## <a name="licensing"></a>Licensering

Gæstebrugeren skal have den korrekte licens for at få vist den delte app. Der er tre muligheder for at opnå dette: Brug Power BI Premium, tildel en Power BI Pro-licens, eller brug gæstens Power BI Pro-licens.

### <a name="use-power-bi-premium"></a>Brug Power BI Premium

Tildeling af apparbejdsområdet til [Power BI Premium-kapacitet](service-premium.md) gør det muligt for gæstebrugeren at bruge appen uden at have en Power BI Pro-licens. Med Power BI Premium kan apps også drage fordel af andre funktioner, f.eks. øget opdateringshastighed, dedikeret kapacitet og store modelstørrelser.

![Brug Power BI Premium](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-a-power-bi-pro-license-to-guest-user"></a>Tildel en Power BI Pro-licens til en gæstebruger

Tildeling af en Power BI Pro-licens til gæstebrugeren i din lejer gør det muligt for gæstebrugeren at få vist indholdet i lejeren.

![Tildel Pro-licens fra din lejer](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Gæstebrugeren medtager sin egen Power BI Pro-licens

Gæstebrugeren har allerede en Power BI Pro-licens, der er tildelt i deres lejer.

![Gæstebrugeren medbringer sin egen licens](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

* Eksterne B2B-gæster er udelukkende begrænset til forbrug af indhold. Eksterne B2B-gæster kan få vist apps, dashboards og rapporter samt eksportere data og oprette mailabonnementer på dashboards og rapporter. De kan ikke få adgang til arbejdsområder eller udgive deres eget indhold.

* Denne funktion er i øjeblikket ikke tilgængelig med Power BI-mobilapps. Du kan få vist Power BI-indhold, der deles med Azure AD B2B i en browser på en mobil enhed.

* Denne funktion er i øjeblikket ikke tilgængelig med rapportwebdelen til Power BI SharePoint Online.

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger, herunder hvordan sikkerhed på rækkeniveau fungerer, i dette whitepaper: [Distribuer Power BI-indhold til eksterne gæstebrugere ved hjælp af Azure AD B2B](https://aka.ms/powerbi-b2b-whitepaper).

Du kan finde oplysninger om Azure AD B2B i [Hvad er Azure AD B2B-samarbejde?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b/)
