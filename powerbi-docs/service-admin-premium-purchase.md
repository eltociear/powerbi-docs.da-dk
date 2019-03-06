---
title: Sådan køber du Power BI Premium
description: Få mere at vide om, hvordan du køber Power BI Premium og aktiverer adgang til indhold for hele organisationen.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/26/2019
LocalizationGroup: Premium
ms.openlocfilehash: 8922bb329e4b598745fd259c67e74b063368b7be
ms.sourcegitcommit: 76772a361e6cd4dd88824b2e4b32af30656e69db
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/27/2019
ms.locfileid: "56892384"
---
# <a name="how-to-purchase-power-bi-premium"></a>Sådan køber du Power BI Premium

I denne artikel beskrives, hvordan du køber Power BI Premium-kapacitet (P1-P3) til din organisation. Du kan købe Power BI Premium-kapacitet via Office 365 Administration, og du [administrerer dine kapaciteter](service-admin-premium-manage.md) på Power BI-administrationsportalen. Du kan finde aktuelle priser og oplysninger om planlægning på [siden Priser for Power BI](https://powerbi.microsoft.com/pricing/) og under [Power BI Premium-beregner](https://powerbi.microsoft.com/calculator/).

Forfattere af indhold skal stadig have en Power BI Pro-licens, også selvom organisationen bruger Power BI Premium. Sørg for at købe mindst én Power BI Pro-licens til din organisation.

Hvis et Premium-abonnement udløber, har du 30 dages fuld adgang til din kapacitet. Derefter vil dit indhold igen blive en delt kapacitet. Modeller, der er større 1 GB, understøttes ikke i delt kapacitet.

## <a name="create-a-new-tenant-with-power-bi-premium-p1"></a>Opret en ny lejer med Power BI Premium P1

Hvis du ikke har en eksisterende lejer og vil oprette en, kan du købe Power BI Premium samtidigt. Følgende link fører dig gennem processen med at oprette en ny lejer og giver dig mulighed for at købe Power BI Premium: [Tilbud på Power BI Premium P1](https://signup.microsoft.com/Signup?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1). Når du opretter din lejer, får du automatisk tildelt rollen Global administrator for Office 365 for den pågældende lejer.

## <a name="purchase-a-power-bi-premium-capacity-for-an-existing-organization"></a>Køb Power BI Premium-kapacitet til en eksisterende organisation

Hvis der allerede er registreret en organisation (lejer), skal du have rollen Global administrator eller Faktureringsadministrator for Office 365 for at købe abonnementer og licenser. Du kan finde flere oplysninger i [Om Office 365-administratorroller](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

Følg disse trin for at købe Premium-kapacitet.

1. Vælg Office 365-appvælgeren i Power BI-tjenesten, og vælg derefter **Administrator**.

    ![Office 365-appvælgeren](media/service-admin-premium-purchase/o365-app-picker.png)

    Du kan også navigere til Office 365 Administration. Du kan komme dertil ved at gå til https://portal.office.com og vælge **Administrator**.

1. Vælg **Fakturering** > **Køb tjenester**.

1. Se efter Power BI Premium-tilbud under **Andre planer**. Det vises som P1 til P3, EM3 og P1 (for hver måned).

1. Hold over ellipsen (**...**), og vælg derefter **Køb nu**.

    ![Køb nu](media/service-admin-premium-purchase/premium-purchase.png)

1. Følg trinnene for at gennemføre købet.

Når du har gennemført købet, kan du på siden **Køb tjenester** se, at elementet er købt og aktivt.

![Har købt Power BI Premium](media/service-admin-premium-purchase/premium-purchased.png)

## <a name="purchase-additional-capacities"></a>Køb ekstra kapacitet

Nu, hvor du har en kapacitet, kan du tilføje mere, i takt med at dit behov vokser. Du kan også bruge en hvilken som helst kombination af SKU'er for Premium-kapacitet (P1 til P3) i din organisation. De forskellige SKU'er giver forskellige ressourcemuligheder.

1. I Office 365 Administration skal du vælge **Fakturering** > **Køb tjenester**.

1. Find det Power BI Premium-element, du vil købe flere af, under **Andre planer**.

1. Peg på **ellipsen (...)** , og vælg derefter **Rediger licensantal**.

    ![Skift antal licenser](media/service-admin-premium-purchase/premium-purchase-more.png)

1. Ret det antal forekomster, du vil have til dette element. Vælg derefter **Send**, når du er færdig.

   > [!IMPORTANT]
   > Hvis du vælger **Send**, opkræves det registrerede kreditkort.

Siden **Køb tjenester** angiver derefter det antal forekomster, som du har. I Power BI-administrationsportalen under **Kapacitetsindstillinger**, afspejler de tilgængelige v-kerner den nye kapacitet, der er købt.

![Tilgængelige v-kerner til Power BI Premium-kapacitet](media/service-admin-premium-purchase/premium-capacities.png)

## <a name="cancel-your-subscription"></a>Opsig dit abonnement

Du kan opsige dit abonnementet fra Office 365 Administration. Gør følgende for at opsige dit Premium-abonnement.

1. Naviger til Office 365 Administration.

1. Vælg **Fakturering** > **Abonnementer**.

1. Vælg dit Power BI Premium-abonnement på listen.

1. Vælg **Flere handlinger** > **Annuller abonnement**.

1. Siden **Annuller abonnement** angiver, om du skal betale et [gebyr for tidlig opsigelse](https://support.office.com/article/early-termination-fees-6487d4de-401a-466f-8bc3-c0beb5cc40d3). På denne side får du også besked, når dataene slettes for abonnementet.

1. Læs oplysningerne igennem, og vælg **Annuller abonnement**, hvis du vil fortsætte.

## <a name="next-steps"></a>Næste trin

[Siden Priser for Power BI](https://powerbi.microsoft.com/pricing/)
[Power BI Premium-beregner](https://powerbi.microsoft.com/calculator/)
[Hvad Power BI Premium?](service-premium.md)
[Ofte stillede spørgsmål om Power BI Premium](service-premium-faq.md)
[Hvidbog om Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)
[Hvidbog om planlægning af en udrulning af Power BI Enterprise](https://aka.ms/pbienterprisedeploy)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)