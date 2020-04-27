---
title: Power BI-licenser i din organisation
description: Oversigt over de forskellige licenstyper, der er tilgængelige i Power BI, og hvordan administratorer køber og administrerer licenser for deres organisation.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/08/2020
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: a41e9453158c38a208fe7f4ac937b4e86a515f4b
ms.sourcegitcommit: b2cb0b02bdc451bf11a92a68f2c4d560a811f563
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/16/2020
ms.locfileid: "81436316"
---
# <a name="power-bi-licensing-in-your-organization"></a>Power BI-licenser i din organisation

Det, en bruger kan udføre i Power BI-tjenesten, afhænger af den typer licens pr. bruger, som vedkommende har, og om det indhold, vedkommende arbejder med, befinder sig i et arbejdsområde, som er tildelt en Power BI Premium-kapacitet. Alle brugere af Power BI-tjenesten skal have en licens.

Brugerne kan få en licens på to måder. Brugerne kan få deres egen gratis licens eller en Pro-licens ved hjælp af funktionaliteten til tilmelding via selvbetjening og deres arbejds- eller skolekonto. Eller administratorer kan få et Power BI-abonnement og tildele licenser til brugere.

I denne artikel fokuseres der på køb af tjenester og licenser pr. bruger set fra en administrators perspektiv. Du kan finde flere oplysninger om, hvordan brugerne kan få deres egne licenser, under [Tilmelding til Power BI som enkeltperson](service-self-service-signup-for-power-bi.md).

## <a name="who-can-purchase-and-assign-licenses"></a>Hvem kan købe og tildele licenser?

Du skal have tildelt en administratorrolle for at kunne købe eller tildele licenser for din organisation. Administratorroller tildeles ved hjælp af Azure Active Directory Administration eller Microsoft 365 Administration. I følgende tabel kan du se, hvilken rolle der kræves for at udføre opgaver relateret til køb og licenser. Du kan finde flere oplysninger om administratorroller i Azure Active Directory under [Få vist og tildel administratorroller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal). Hvis du vil have mere at vide om administratorroller i Microsoft 365, herunder bedste praksis, skal du se [Om administratorroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).

| Hvem kan købe tjenester og licenser? | Hvem kan administrere brugerlicenser? |
| --------------- | --------------- |
| Faktureringsadministrator | Licensadministrator |
| Global administrator | Brugeradministrator |
|  | Global administrator |

Disse roller administrerer organisationen. Du kan finde flere oplysninger om administratorroller i Power BI-tjenesten under [Beskrivelse af administratorroller i Power BI](service-admin-role.md).

## <a name="get-power-bi-for-your-organization"></a>Få Power BI til din organisation

En global administrator eller en faktureringsadministrator kan tilmelde sig Power BI-tjenesten og købe licenser til brugerne i organisationen. Hvis du ikke er helt klar til at købe, skal du vælge Power BI Pro (prøveversion). Du får 25 licenser, som du kan bruge i én måned. Du kan se en trinvis vejledning til, hvordan du tilmelder dig, under [Få et Power BI-abonnement til din organisation](admin/service-admin-org-subscription.md).

## <a name="about-self-service-sign-up"></a>Om tilmelding via selvbetjening

De enkelte brugere kan få deres egen Power BI-licens ved at tilmelde sig med deres arbejds- eller skolekonto. Med en gratis licens kan brugerne udforske Power BI til personlig dataanalyse og visualiseringer ved hjælp af Mit arbejdsområde, men de kan ikke indlede et samarbejde med andre brugere. Der kræves en Power BI Pro-licens for at dele indhold. Brugerne kan opgradere deres licenstype til Pro eller tilmelde sig Pro direkte, hvis organisationen bruger det kommercielle cloudmiljø. Direkte køb af eller opgradering til Pro er ikke tilgængelig til uddannelsesinstitutioner eller organisationer, der er udrullet til instanser af cloudmiljøet til offentlige myndigheder eller nationale cloudmiljøer.

Hvis du ikke ønsker, at tilmelding via selvbetjening skal være tilgængelig til brugerne i din organisation, skal du se [Aktivér eller deaktiver tilmelding via selvbetjening](admin/service-admin-disable-self-service.md) for at få mere at vide om, hvordan du slår det fra.

Hvis du vil se, hvilke brugere i din organisation der måske allerede har en licens, skal du se [Få vist og administrer brugerlicenser](admin/service-admin-manage-licenses.md).

## <a name="license-types-and-capabilities"></a>Licenstyper og funktionalitet

Der er to slags licenser pr. bruger i Power BI: gratis og Pro. Den type licens, som en bruger har brug for, bestemmes af, hvor indholdet gemmes, og hvordan brugeren vil interagere med dette indhold. Din organisations [abonnementstype](#subscription-types) afgør, hvor indholdet kan gemmes.

[Power BI Premium](service-admin-premium-purchase.md) er én abonnementstype, som giver brugerne en gratis licens til at arbejde med indhold i arbejdsområder, der er tildelt en Premium-kapacitet. Uden for en Premium-kapacitet kan en bruger med en gratis licens kun bruge Power BI-tjenesten til at oprette forbindelse til data og oprette rapporter og dashboards i et personligt arbejdsområde. De kan ikke dele indhold med andre eller publicere indhold til apparbejdsområder.

Der bruges en delt kapacitet til et Power BI-standardabonnement. Når indhold gemmes i en delt kapacitet, kan brugere, der har fået tildelt en Power BI Pro-licens, kun samarbejde med andre Power BI Pro-brugere. De kan forbruge indhold, der er delt med andre brugere, publicere indhold til apparbejdsområder, dele dashboards og abonnere på dashboards og rapporter.  Når arbejdsområder befinder sig i en Premium-kapacitet, kan Pro-brugere distribuere indhold til brugere, der ikke har en Power BI Pro-licens.

I nedenstående tabel opsummeres den grundlæggende funktionalitet for hver licenstype. Hvis du vil have en detaljeret oversigt over tilgængelige funktioner i hver licenstype, skal du se [Funktioner efter licenstype](service-features-license-type.md).

| Licenstype | Funktionalitet, når arbejdsområdet befinder sig i en delt kapacitet | Yderligere funktionalitet, når arbejdsområdet befinder sig i en Premium-kapacitet |
| --------- | ----------- | ----------- |
| Power BI (gratis) | Adgang til indhold i Mit arbejdsområde | Forbruge indhold, der deles med dem |
| Power BI Pro | Publicere indhold til apparbejdsområder, dele dashboards, abonnere på dashboards og rapporter, dele med brugere, der har en Pro-licens | Distribuere indhold til brugere, der har gratis licenser |

## <a name="subscription-types"></a>Abonnementstyper

Alle brugerbaserede, kommercielle licensabonnementer fra Microsoft er baseret på Azure Active Directory-identiteter. Det betyder, at du skal logge på med en identitet, som understøttes af Azure Active Directory til kommercielle licenser. Du kan føje et Power BI-abonnement til et hvilket som helst Microsoft-abonnement, der bruger Azure Active Directory til identitetstjenester. Nogle abonnementer, f.eks. Office 365 E5, indeholder en Power BI Pro-licens, så det er ikke nødvendigt at tilmelde sig Power BI separat.

Der er to slags Power BI-abonnementer til organisationer: BI via selvbetjening med Power BI Pro og avanceret analyse med Power BI Premium.

Med et selvbetjent Power BI Pro-standardabonnement kan administratorer tildele licenser pr. bruger. Der er et månedligt gebyr pr. bruger for Power BI Pro-licenser, som muliggør samarbejde, publicering, deling og ad hoc-analyse. Indhold gemmes i en delt kapacitet, som administreres fuldt ud af Microsoft.

Med et Power BI Premium-abonnement tildeles en dedikeret kapacitet til en organisation. Premium er velegnet til BI i virksomheder, big data-analyse samt rapportering i cloudmiljøet og det lokale miljø. Det muliggør avanceret administration og styring af udrulning. Dedikerede beregnings- og lagerressourcer administreres af kapacitetsadministratorer i organisationen. Der er en månedlig omkostning for dette dedikerede miljø. Foruden andre Premium-fordele kan indhold, der gemmes i en Premium-kapacitet, tilgås af og distribueres til brugere, der ikke har Power BI Pro-licenser. Mindst én bruger skal være tildelt en Power BI Pro-licens for at bruge Premium, og indholdsskabere og udviklere skal stadig have en Power BI Pro-licens.

De to abonnementstyper er ikke indbyrdes uforenelige. Du kan have både Power BI Premium og Power BI Pro. I denne konfiguration kan indhold, der er gemt i en Premium-kapacitet, deles med alle brugere, og delt indhold er også tilgængeligt. Du kan finde oplysninger om kapacitetsgrænser under [Administrer datalager i Power BI-arbejdsområder](service-admin-manage-your-data-storage-in-power-bi.md).

Du kan se en sammenligning af funktioner og priser i [Power BI-priser](https://powerbi.microsoft.com/pricing).

## <a name="guest-user-access"></a>Adgang for gæstebruger

Du har måske brug for at distribuere indhold til brugere uden for din organisation. Du kan dele indhold med eksterne brugere ved at invitere dem til at få vist indhold som en gæst. Med Azure Active Directory Business-to-business (Azure AD B2B) er det muligt at dele indehold med eksterne gæstebrugere. Følgende forudsætninger skal være opfyldt, før du kan dele med eksterne brugere:

- Muligheden for at dele indhold med eksterne brugere skal være aktiveret

- Gæstebrugeren skal have den korrekte licens for at få vist det delte indhold

Se flere oplysninger om adgang for gæstebrugere under [Distribuer Power BI-indhold til eksterne gæstebrugere med Azure AD B2B](service-admin-azure-ad-b2b.md).

## <a name="purchase-power-bi-pro-licenses"></a>Køb Power BI Pro-licenser

Som administrator kan du købe Power BI Pro-licenser via Microsoft 365 eller via en Microsoft-partner. Når du har købt licenserne, kan du tildele dem til individuelle brugere. Du kan finde flere oplysninger i [Køb og tildel Power BI Pro-licenser](service-admin-purchasing-power-bi-pro.md).

### <a name="power-bi-pro-license-expiration"></a>Udløb af Power BI Pro-licens

Der er en respitperiode, efter en Power BI Pro-licens er udløbet. For licenser, der er en del af et volumenlicenskøb, er respitperioden 90 dage. Hvis du har købt licensen direkte, er respitperioden 30 dage.

Power BI Pro har den samme abonnementslivscyklus som Office 365. Du kan finde flere oplysninger under [Hvad sker der med mine data og adgang, når mit abonnement på Office 365 til virksomheder slutter?](https://support.office.com/article/What-happens-to-my-data-and-access-when-my-Office-365-for-business-subscription-ends-4436582f-211a-45ec-b72e-33647f97d8a3)


## <a name="next-steps"></a>Næste trin

- [Køb og tildel Power BI Pro-licenser](service-admin-purchasing-power-bi-pro.md)
- [Dokumentation til Microsoft 365 Business-abonnementer og -fakturering](https://docs.microsoft.com/microsoft-365/commerce/?view=o365-worldwide)
- [Find Power BI-brugere, der er logget på](service-admin-access-usage.md)
- Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
