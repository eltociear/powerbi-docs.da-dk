---
title: Administrer kapaciteter i Power BI Premium og Power BI Embedded
description: "Få mere at vide om, hvordan du kan administrere Power BI Premium og give adgang til indhold til hele organisationen."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 10/10/2017
ms.author: asaxton
ms.openlocfilehash: d78e5ee1648daaa5aeb9247483bf849cf07d2599
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="manage-capacities-within-power-bi-premium-and-power-bi-embedded"></a>Administrer kapaciteter i Power BI Premium og Power BI Embedded
Få mere at vide om, hvordan du kan administrere kapaciteter i Power BI Premium og Power BI Embedded, som indeholder dedikerede ressourcer til dit indhold.

![Indstillingsskærm for Power BI-kapacitet](media/service-admin-premium-manage/premium-capacity-management.png)

Kapacitet er en grundlægende funktion i Power BI Premium og Power BI Embedded.

## <a name="what-is-capacity"></a>Hvad er kapacitet?
Kapacitet er rækken af ressourcer, som er reserveret udelukkende til dit brug. Adgang til kapacitet giver dig mulighed for at publicere dashboards, rapporter og datasæt til brugere i hele organisationen uden at være nødt til at købe licenser til dem. Den garanterer også pålidelig, ensartet ydeevne for det indhold, der hostes i kapacitet.

Kapacitet er helt gennemskueligt for slutbrugere. De vil fortsat kunne bruge Power BI eller dit program på normal vis. De behøver ikke at være klar over, at noget (eller alt) indhold hostes af din dedikerede kapacitet. For brugerne fungerer alt helt som før.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

Du kan finde flere oplysninger i [Hvad er Power BI Premium?](service-premium.md).

## <a name="purchase-capacity"></a>Køb kapacitet
Hvis du vil drage fordel af dedikeret kapacitet, skal du købe et abonnement på Power BI Premium i Office 365 Administration eller oprette en Power BI Embedded-ressource på Microsoft Azure-portalen. Du kan få flere oplysninger i nedenstående ressourcer:

* **Power BI Premium:** [Sådan køber du Power BI Premium](service-admin-premium-purchase.md)
* **Power BI Embedded:** Kommer snart.

Når du køber Power BI Premium-varenumre, modtager din lejer det tilsvarende antal v-kerner til at køre kapaciteter. Køb af f.eks. Power BI Premium P3-varenumre giver lejeren adgang til 32 v-kerner.

## <a name="capacity-admins"></a>Kapacitetsadministratorer
> [!NOTE]
> Kapacitetsadministratorer (til Power BI Embedded-kapacitet) er defineret inden for Microsoft Azure-portalen.
> 
> 

Når du er tilknyttet en kapacitet som kapacitetsadministrator, så har du fuld kontrol over kapaciteten og dens administrative funktioner. Du kan tilføje flere kapacitetsadministratorer (kun Power BI Premium) eller give brugere rettigheder knyttet til kapacitetstildeling fra Power BI-administrationsportalen. Du kan massetildele arbejdsområder til en kapacitet og få vist forbrugsdata på en kapacitet.

Hver kapacitet har sine egne administratorer. Når en kapacitetsadministrator defineres til en kapacitet, så giver det ikke vedkommende adgang til alle kapaciteter i organisationen. Kapacitetsadministratorer har ikke adgang til alle områder af Power BI Administration som standard, som f.eks. forbrugsdata, overvågningslogger eller lejerindstillinger. Kapacitetsadministratorer har heller ikke tilladelse til at konfigurere nye kapaciteter eller ændre varenumrene for eksisterende kapaciteter. Kun globale administratorer eller Power BI-tjenesteadministratorer har adgang til disse elementer.

Alle Office 365 Globale administratorer og Power BI-administratorer er automatisk kapacitetsadministratorer af både Power BI Premium-kapacitet og Power BI Embedded-kapacitet.

## <a name="managing-capacity"></a>Administrering af kapacitet
Når du har købt kapacitetsnoder i Office 365, skal du derefter konfigurere en ny kapacitet. Dette gøres via [Power BI-administrationsportalen](service-admin-portal.md). I administrationsportalen kan du se afsnittet kaldet **Kapacitetsindstillinger**. Det er her, at du skal administrere Power BI Premium-kapaciteter for organisationen.

![Kapacitetsindstillinger i administrationsportalen](media/service-admin-premium-manage/admin-portal-premium.png)

Hvis du vælger **Kapacitetsindstillinger**, så bliver du ført over til skærmbilledet kapacitetsadministration og standardplaceringen Power BI Premium.

### <a name="setting-up-a-new-capacity-power-bi-premium"></a>Konfiguration af en ny kapacitet (Power BI Premium)
Antallet af v-kerner afspejler det brugte antal og tilgængelige antal, der kan bruges til at oprette kapaciteter med. Mængden af tilgængelige v-kerner for organisationen er baseret på de Premium-varenumre, du har købt. Køb af en P3 og en P2 resulterer f.eks. i 48 tilgængelige kerner – 32 fra P3 og 16 fra P2.

![Brugte og tilgængelige v-kerner for Power BI Premium](media/service-admin-premium-manage/admin-portal-v-cores.png)

Hvis du har tilgængelige v-kerner, skal du konfigurere en ny kapacitet på følgende måde.

1. Vælg **Konfigurer ny kapacitet**.
2. Giv din kapacitet et **navn**.
3. Definer, hvem kapacitetsadministratoren er for denne kapacitet.
   
    Kapacitetsadministratorer behøver ikke at være en Power BI-administrator eller en Office 365 Global administrator. Du kan finde flere oplysninger under [Power BI Premium-kapacitetsadministratorer](#capacity-admins)
4. Vælg kapacitetstørrelsen. Hvilke indstillinger, der er tilgængelige, afhænger af, hvor mange tilgængelige v-kerner du har. Du kan ikke vælge en indstilling, der er større end den, du har adgang til.
   
    ![Tilgængelige Premium-kapacitetsstørrelser](media/service-admin-premium-manage/premium-capacity-size.png)
5. Vælg **Konfigurer**.

![Konfigurer en ny kapacitet](media/service-admin-premium-manage/set-up-capacity.png)

Kapacitetsadministratorer såvel som Power BI-administratorer og Office 365 Globale administratorer får derefter vist kapaciteten på oversigten i administratorportalen.

### <a name="capacity-settings"></a>Kapacitetsindstillinger
Du kan vælge **tandhjulsikonet (indstillinger)** under handlinger i skærmbilledet administration af Premium-kapacitet. Dette gør det muligt at omdøbe eller slette en kapacitet. Det angiver også, hvem tjenestens administratorer er, kapacitetens varenummer/størrelse og hvilken region, kapaciteten er i.

![Kapacitetshandlinger i området for kapacitetsadministration](media/service-admin-premium-manage/capacity-actions.png)

![Kapacitetsindstillinger](media/service-admin-premium-manage/capacity-settings.png)

![Slet og anvend knapper til kapacitetsindstillinger i Power BI Premium](media/service-admin-premium-manage/capacity-settings-delete.png)

> [!NOTE]
> Power BI Embedded-kapacitetsindstillinger administreres i Microsoft Azure-portalen.
> 
> 

### <a name="change-capacity-size-power-bi-premium"></a>Tilpas kapacitetsstørrelse (Power BI Premium)
Power BI-administratorer og Office 365 Globale administratorer tilpasser størrelsen af Power BI Premium-kapaciteten ved at vælge **Tilpas kapacitetsstørrelse**. Kapacitetsadministratorer, der ikke er Power BI-administrator eller Office 365 Global administrator, har ikke adgang til denne indstilling.

![Tilpas Power BI Premium-kapacitetsstørrelse](media/service-admin-premium-manage/change-capacity-size.png)

Skærmbilledet **Tilpas kapacitetsstørrelse** giver dig adgang til at opgradere eller nedgradere kapacitetsstørrelsen, hvis du har tilgængelige ressourcer. Administratorer kan frit oprette, tilpasse størrelsen af og slette noder, så længe de har de fornødne antal v-kerner. 

P-varenumre kan ikke nedgraderes til EM-varenumre. Du kan placere markøren over deaktiverede indstillinger, som giver en forklaring.

![Rullemenu til tilpasning af Power BI Premium-kapacitetsstørrelse](media/service-admin-premium-manage/change-capacity-size2.png)

### <a name="capacity-assignment"></a>Kapacitetstildeling
Du kan administrere en kapacitet ved at vælge navnet på kapaciteten. Herfra bliver du ført hen til skærmbilledet med kapacitetsadministration.

![Vælg kapacitetsnavn for at åbne skærmbilledet med kapacitetstildeling](media/service-admin-premium-manage/capacity-assignment.png)

Hvis der ikke er blevet tildelt nogen arbejdsområder til kapaciteten, så får du vist meddelelsen **Tildel arbejdsområder**.

#### <a name="user-permissions"></a>Brugertilladelser
Du kan tildele yderligere **Kapacitetsadministratorer** til Power BI Premium-kapaciteter. Udover at tildele brugere med **kapacitetstildelingstilladelser**. Brugere, der har tildelingstilladelser, kan tildele et apparbejdsområde til kapaciteten, hvis de er administratorer af det pågældende arbejdsområde. De kan også tildele deres personlige *Mit arbejdsområde* til kapaciteten. Brugere med tildelingstilladelser har ikke adgang til administrationsportalen.

> [!NOTE]
> I forbindelse med Power BI Embedded-kapacitet tildeles kapacitetsadministratorer rettigheder inden for Microsoft Azure-portalen.
> 
> 

![](media/service-admin-premium-manage/capacity-user-permissions.png)

![](media/service-admin-premium-manage/capacity-user-permissions2.png)

## <a name="usage-measurements-power-bi-premium"></a>Målinger af forbrug (Power BI Premium)
For hver kapacitet har du mulighed for at bruge målinger af forbrug for CPU, hukommelse og Direkte forespørgsel. Hver KPI har tre angivelser **God (grøn)**, **Marginal (gul)** og **Kritisk (rød)**. Vi anbefaler, at man overvåger disse tal for at sørge for, at ens brugere oplever god ydeevne under brugen af Premium-indhold.

**Power BI Embedded-kapacitetsforbrug overvåges i Azure-portalen.**

![](media/service-admin-premium-manage/usage-metrics-critical.png "Kapacitetsforbrugsdata – kritisk")

| Data | Beskrivelse |
| --- | --- |
| CPU |CPU-forbrug af kerner. |
| Hukommelse |Repræsenterer hukommelsesforbrug af backend-kerner. Disse data angiver specifikt, hvor ofte modeller ryddes fra hukommelsen pga. hukommelsesforbrug grundet brugen af flere modeller. |
| DQ/s |* Vi begrænser det samlede antal forespørgsler i relation til DirectQuery og direkte forbindelse pr. sekund.<br/>* Grænserne er 30/s for P1, 60/s for P2 og 120/s for P3.<br/>* Forespørgsler i relation til DirectQuery og direkte forbindelse fordeles ligeligt i forhold til de ovenstående begrænsninger. Hvis du f.eks. har 15 DirectQueries og 15 direkte forbindelser på et sekund, er grænsen nået.<br/>* Dette gælder ligeligt for forbindelser i det lokale miljø og cloudbaserede forbindelser. |

Når disse data er marginale/kritiske, så oplever brugerne muligvis en forringelse af rapport- og opdateringsydeevnen, især på tidspunkter med spidsbelastning.

Dataene afspejler forbruget i den seneste uge og er designet til at tælle antallet af gange, hvor kapaciteten er overbelastet og derfor leverer en mindre end optimal ydeevne for brugerne.

Hver episode med *forbrug over 80 %* bør anses for at udgøre en potentiel ydeevneforringelse. Når der er mange forekomster, betyder det som regel for brugerne, at der er opstået et ydeevneproblem.

## <a name="assign-a-workspace-to-a-capacity"></a>Tildel et arbejdsområde til en kapacitet
Et arbejdsområde kan tildeles en kapacitet på nogle få måder.

### <a name="capacity-management-in-admin-portal"></a>Kapacitetsadministration i administrationsportalen
Udover Power BI-administratorer og Office 365 Globale administratorer kan kapacitetsadministratorer massetildele arbejdsområder inden for afsnittet med premium-kapacitetsadministration i administrationsportalen. Når du administrerer en kapacitet, får du vist et afsnit med **Arbejdsområder**, hvor du kan tildele arbejdsområder.

![Afsnit for tildeling af arbejdsområde i kapacitetsadministration](media/service-admin-premium-manage/capacity-manage-workspaces.png)

1. Vælg **Tildel arbejdsområder**. Dette er angivet flere steder, og udfører alle den samme opgave.
2. Vælg enten **Arbejdsområder til hele organisationen** eller **Specifikke arbejdsområder efter bruger**.
   
   | Markering | Beskrivelse |
   | --- | --- |
   | **Arbejdsområder til hele organisationen** |Hvis du tildeler Premium-kapacitet til arbejdsområder til hele organisationen, så tildeles alle apparbejdsområder og Mine arbejdsområder i organisationen den pågældende Premium-kapacitet. Desuden får alle aktuelle og fremtidige brugere tilladelse til at gentildele individuelle arbejdsområder til denne kapacitet. |
   | **Specifikke arbejdsområder efter bruger** |Når du tildeler arbejdsområder efter bruger eller gruppe, så tildeles alle arbejdsområder, der ejes af de pågældende brugere, Premium-kapacitet, herunder brugerens personlige arbejdsområde. Disse brugere får automatisk tilladelser til arbejdsområdetildeling.<br>Dette omfatter arbejdsområder, der allerede er tildelt en anden kapacitet. |
3. Vælg **Anvend**.

Denne indstilling tillader ikke, at du tildeler en kapacitet til specifikke arbejdsområder.

### <a name="app-workspace-settings"></a>Indstillinger for apparbejdsområde
Du kan også tildele en Premium-kapacitet til et apparbejdsområde fra det pågældende arbejdsområdes indstillinger. Benyt følgende fremgangsmåde for at tildele et apparbejdsområde en premiumkapacitet.

For at flytte en kapacitet til et arbejdsområde skal du have administratortilladelser til det pågældende arbejdsområde og desuden have tilladelser til kapacitetstildeling for den pågældende kapacitet. Bemærk, at arbejdsområdeadministratorer altid kan fjerne et arbejdsområde fra Premium-kapacitet.

1. Rediger et apparbejdsområde ved at vælge **ellipsen (...)**  og vælge **Rediger arbejdsområde**.
   
    ![Rediger arbejdsområde via ellipsegenvejsmenuen](media/service-admin-premium-manage/edit-app-workspace.png)
2. I **Rediger arbejdsområde** skal du udvide **Avanceret**.
3. Hvis du har fået tildelt tilladelser til tildeling af en given kapacitet, så har du mulighed for at aktivere **Premium** for dette arbejdsområde.
4. Vælg den pågældende kapacitet, du vil tildele dette apparbejdsområde.
   
    ![Rullemenu til valg af kapacitet](media/service-admin-premium-manage/app-workspace-advanced.png)
5. Vælg **Gem**.

Når du har gemt, flyttes arbejdsområdet og al dets indhold til Premium-kapacitet, uden at slutbrugerne oplever nogen tjenesteafbrydelser.

## <a name="what-premium-looks-like-for-users"></a>Premium-brugergrænsefladen
I de fleste tilfælde bemærker brugere slet ikke, at de er i en Premium-kapacitet. Deres dashboards og rapporter fungerer uden problemer. Arbejdsområder, der er i Premium-kapacitet, markeres visuelt med en diamantikon ud for de pågældende arbejdsområder. 

![Diamant angiver, at arbejdsområdet understøttes af Premium-kapacitet](media/service-admin-premium-manage/premium-workspace.png)

## <a name="power-bi-report-server-product-key"></a>Power BI Report Server-produktnøgle
På fanen **Kapacitetsindstillinger** i Power BI-administratorportalen kan du tilgå Power BI Report Server-produktnøglen. Den kan kun tilgås af globale administratorer eller brugere tildelt Power BI-tjenesteadministratorrollen, og hvis man har erhvervet et Power BI Premium-varenummer.

![Power BI Report Server-nøgle i kapacitetsindstillinger](media/service-admin-premium-manage/pbirs-product-key.png)

Når du vælger **Power BI Report Server-nøgle** vises en dialogboks med din produktnøgle. Du kan kopiere den og bruge den med installationen.

![Power BI Report Server-produktnøgle](media/service-admin-premium-manage/pbirs-product-key-dialog.png)

Du kan finde flere oplysninger under [Installér Power BI-rapportserveren](report-server/install-report-server.md).

## <a name="next-steps"></a>Næste trin
Del publicerede apps med gratisbrugere, når du tildeler en Premium-kapacitet til arbejdsområdet. Du kan finde flere oplysninger under [Opret og distribuer en app i Power BI](service-create-distribute-apps.md).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
