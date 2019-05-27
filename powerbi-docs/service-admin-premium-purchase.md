---
title: Sådan køber du Power BI Premium
description: Få mere at vide om, hvordan du køber Power BI Premium og aktiverer adgang til indhold for hele organisationen.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 03/12/2019
LocalizationGroup: Premium
ms.openlocfilehash: bc55d290e10832034ed96d7092c5baa4b7cc20d1
ms.sourcegitcommit: 317980e9f40fb3ed6eeb91b92056f242bd814a2c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/14/2019
ms.locfileid: "65565298"
---
# <a name="how-to-purchase-power-bi-premium"></a>Sådan køber du Power BI Premium

> [!NOTE]
> Denne artikel opdateres i øjeblikket for at beskrive nye funktioner, give flere detaljer og forbedre læsbarheden. 

I denne artikel beskrives, hvordan du køber Power BI Premium-kapacitet (P1-P3) til din organisation. Du kan købe Power BI Premium-kapacitet via Microsoft 365 Administration, og du administrerer dine kapaciteter på Power BI-administrationsportalen. Du kan finde aktuelle priser og oplysninger om planlægning på [siden Priser for Power BI](https://powerbi.microsoft.com/pricing/) og under [Power BI Premium-beregner](https://powerbi.microsoft.com/calculator/).

Forfattere af indhold skal stadig have en Power BI Pro-licens, også selvom organisationen bruger Power BI Premium. Sørg for at købe mindst én Power BI Pro-licens til din organisation.

Hvis et Premium-abonnement udløber, har du 30 dages fuld adgang til din kapacitet. Derefter vil dit indhold igen blive en delt kapacitet. Modeller, der er større 1 GB, understøttes ikke i delt kapacitet.

## <a name="create-a-new-tenant-with-power-bi-premium-p1"></a>Opret en ny lejer med Power BI Premium P1

Hvis du ikke har en eksisterende lejer og vil oprette en, kan du købe Power BI Premium samtidigt. Følgende link fører dig gennem processen med at oprette en ny lejer og giver dig mulighed for at købe Power BI Premium: [Tilbud på Power BI Premium P1](https://signup.microsoft.com/Signup?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1). Når du opretter din lejer, får du automatisk tildelt rollen Global administrator for Office 365 for den pågældende lejer.

## <a name="purchase-a-power-bi-premium-capacity-for-an-existing-organization"></a>Køb Power BI Premium-kapacitet til en eksisterende organisation

Hvis der allerede er registreret en organisation (lejer), skal du have rollen Global administrator eller Faktureringsadministrator for Office 365 for at købe abonnementer og licenser. Du kan finde flere oplysninger i [Om Office 365-administratorroller](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

Følg disse trin for at købe Premium-kapacitet.

1. Vælg Office 365-appvælgeren i Power BI-tjenesten, og vælg derefter **Administrator**.

    ![Office 365-appvælgeren](media/service-admin-premium-purchase/o365-app-picker.png)

    Du kan også navigere til Microsoft 365 Administration. Du kan komme dertil ved at gå til https://portal.office.com og vælge **Administrator**.

1. Vælg **Fakturering** > **Køb tjenester**.

1. Se efter Power BI Premium-tilbud under **Andre planer**. Det vises som P1 til P3, EM3 og P1 (for hver måned).

1. Hold over ellipsen (**...**), og vælg derefter **Køb nu**.

    ![Køb nu](media/service-admin-premium-purchase/premium-purchase.png)

1. Følg trinnene for at gennemføre købet.

Når du har gennemført købet, kan du på siden **Køb tjenester** se, at elementet er købt og aktivt.

![Har købt Power BI Premium](media/service-admin-premium-purchase/premium-purchased.png)

## <a name="purchase-additional-capacities"></a>Køb ekstra kapacitet

Nu, hvor du har en kapacitet, kan du tilføje mere, i takt med at dit behov vokser. Du kan også bruge en hvilken som helst kombination af SKU'er for Premium-kapacitet (P1 til P3) i din organisation. De forskellige SKU'er giver forskellige ressourcemuligheder.

1. I Microsoft 365 Administration skal du vælge **Fakturering** > **Køb tjenester**.

1. Find det Power BI Premium-element, du vil købe flere af, under **Andre planer**.

1. Peg på **ellipsen (...)** , og vælg derefter **Rediger licensantal**.

    ![Skift antal licenser](media/service-admin-premium-purchase/premium-purchase-more.png)

1. Ret det antal forekomster, du vil have til dette element. Vælg derefter **Send**, når du er færdig.

   > [!IMPORTANT]
   > Hvis du vælger **Send**, opkræves det registrerede kreditkort.

Siden **Køb tjenester** angiver derefter det antal forekomster, som du har. I Power BI-administrationsportalen under **Kapacitetsindstillinger**, afspejler de tilgængelige v-kerner den nye kapacitet, der er købt.

![Tilgængelige v-kerner til Power BI Premium-kapacitet](media/service-admin-premium-purchase/premium-capacities.png)

## <a name="cancel-your-subscription"></a>Opsig dit abonnement

Du kan opsige dit abonnementet via Microsoft 365 Administration. Gør følgende for at opsige dit Premium-abonnement.

1. Gå til Microsoft 365 Administration.

1. Vælg **Fakturering** > **Abonnementer**.

1. Vælg dit Power BI Premium-abonnement på listen.

1. Vælg **Flere handlinger** > **Annuller abonnement**.

1. Siden **Annuller abonnement** angiver, om du skal betale et [gebyr for tidlig opsigelse](https://support.office.com/article/early-termination-fees-6487d4de-401a-466f-8bc3-c0beb5cc40d3). På denne side får du også besked, når dataene slettes for abonnementet.

1. Læs oplysningerne igennem, og vælg **Annuller abonnement**, hvis du vil fortsætte.

### <a name="when-canceling-or-your-license-expires"></a>Når du annullerer din licens, eller når den udløber

Når du annullerer dit Premium-abonnement, eller når din kapacitetslicens udløber, kan du fortsætte med at få adgang til dine Premium-kapaciteter i en periode på 30 dage fra datoen for licensens annullering eller udløb. Efter 30 dage kan du ikke længere få adgang til dine Premium-kapaciteter eller arbejdsområderne i dem.

## <a name="next-steps"></a>Næste trin

[Side med Power BI-prisfastsættelse](https://powerbi.microsoft.com/pricing/)   
[Power BI Premium-beregner](https://powerbi.microsoft.com/calculator/)   
[Ofte stillede spørgsmål om Power BI Premium](service-premium-faq.md)   
[Hvidbog om planlægning af en Power BI Enterprise-installation](https://aka.ms/pbienterprisedeploy)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)