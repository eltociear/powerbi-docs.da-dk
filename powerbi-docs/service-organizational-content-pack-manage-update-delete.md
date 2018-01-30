---
title: 'Organisationsindholdspakker: administrer og opdater'
description: "Læs om at administrere, opdatere og slette organisationsindholdspakker i Power BI."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: maggies
ms.openlocfilehash: 86d5ddd1643a713e3094ef39d9fbb46f9a1efc69
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/13/2017
---
# <a name="manage-update-and-delete-organizational-content-packs"></a>Administrer, opdater og slet organisationsindholdspakker
> [!NOTE]
> Har du hørt om de nye *apps*? Apps er ny måde at sende indhold til store målgrupper på i Power BI. Vi anbefaler at bruge apps i stedet for organisationsindholdspakker eller skrivebeskyttede arbejdsområder. Få [mere at vide om apps](service-install-use-apps.md).
> 
> 

Du kan pakke og dele dine dashboards, rapporter, Excel-projektmapper og datasæt med dine kollegaer som [organisationsindholdspakker](service-organizational-content-pack-introduction.md). Dine kollegaer kan bruge dem, som de er, eller de kan oprette deres egne kopier.

Oprettelse af indholdspakker adskiller sig fra deling af dashboards eller samarbejde om dem i en gruppe. Læs [Hvordan kan jeg samarbejde på og dele dashboards og rapporter?](service-how-to-collaborate-distribute-dashboards-reports.md) for at finde det bedste valg til din situation.

Du kan kun udføre visse organisationsindholdspakkeopgaver, hvis du har oprettet indholdspakken:

* Udgiv igen.
* Begræns eller udvid adgangen til indholdspakken.
* Angiv og rediger den planlagte opdatering.
* Slet indholdspakken.

## <a name="modify-and-re-publish-an-organizational-content-pack"></a>Opret og udgiv en organisationsindholdspakke igen
Hvis du foretager ændringer af indholdspakkens oprindelige dashboard, rapport eller Excel-projektmappe, beder Power BI dig om at publicere den igen. Derudover kan du som opretter af indholdspakken opdatere alle de indstillinger, du har valgt i vinduet Opret indholdspakke, når du opretter den oprindelige indholdspakke. 

## <a name="republish-with-new-content"></a>Publicer igen med nyt indhold
Når du foretager og gemmer en ændring af det dashboard, som du inkluderede i en indholdspakke, minder Power BI dig om at opdatere det, så andre kan se ændringerne. Dette er tilfældet, hvis du f.eks. fastgør et nyt felt eller blot ændrer navnet på dashboardet.

1. Vælg **Se indholdspakker** i meddelelsen.
   
   ![](media/service-organizational-content-pack-manage-update-delete/pbi_contpkchangesmessage.png)
2. Eller vælg tandhjulsikonet i øverste højre hjørne ![](media/service-organizational-content-pack-manage-update-delete/cog.png), og vælg **Se indholdspakke**.
   
   ![](media/service-organizational-content-pack-manage-update-delete/pbi_contpkview.png)
   
   Bemærk advarselsikonet ![](media/service-organizational-content-pack-manage-update-delete/pbi_contpkwarningicon.png).  Dette ikon fortæller dig, at du har ændret indholdspakken på en eller anden måde, og den svarer ikke længere til det, du har udgivet.
3. Vælg **Rediger**.  
4. Foretag de nødvendige ændringer i vinduet **Opdater indholdspakke**, og vælg **Opdater**. Meddelelsen **Udført** vises.
   
   * Opdateringen anvendes automatisk for gruppemedlemmer, som ikke har tilpasset indholdspakken.
   * Gruppemedlemmer, som har tilpasset indholdspakken, modtager en meddelelse om, at der er en ny version.  De kan gå til AppSource og hente den opdaterede indholdspakke uden at miste deres personligt tilpassede version.  De har nu to versioner: den personligt tilpassede version og den opdaterede indholdspakke.  I den personligt tilpassede version er alle fliser fra den oprindelige indholdspakke væk.  Men fliser, der er fastgjort fra andre rapporter, vises stadig.    

## <a name="update-the-audience-expand-or-restrict-access"></a>Opdater målgruppen: Udvid eller begræns adgangen
En anden ændring, der er tilgængelig for oprettere af indholdspakker, er at udvide og begrænse adgang til indholdspakken.  Du har måske publiceret en indholdspakke til en bred målgruppe, og du har besluttet dig for at begrænse adgangen til en mindre gruppe.  

1. Vælg tandhjulsikonet ![](media/service-organizational-content-pack-manage-update-delete/cog.png), og vælg **Se Indholdspakker**.
2. Vælg **Rediger**. 
3. Foretag de nødvendige ændringer i vinduet **Opdater indholdspakke**, og vælg **Opdater**. Du kan f.eks. slette den oprindelige distributionsgruppe i feltet **Bestemte grupper** og erstatte den med en anden distributionsgruppe (der har færre medlemmer).
   
   Meddelelsen Udført vises.
   
   Til alle medarbejdere, der ikke er en del af det nye alias:
   
   * For gruppemedlemmer, der ikke har tilpasset indholdspakken, er de dashboards og rapporter, der er tilknyttet den indholdspakke, ikke længere tilgængelige, og indholdspakken vises ikke i navigationsruden.
   * For gruppemedlemmer, som har tilpasset indholdspakken, er alle felter fra den oprindelige indholdspakke væk, næste gang de åbner det tilpassede dashboard.  Men fliser, der er fastgjort fra andre rapporter, vises stadig. De oprindelige indholdspakkerapporter og -datasæt er ikke længere tilgængelige, og indholdspakken vises ikke i navigationsruden.   

## <a name="refresh-an-organizational-content-pack"></a>Opdater en organisationsindholdspakke
Da du har oprettet indholdspakken, kan du [planlægge en opdatering af datasættene](refresh-data.md).  Når du opretter og uploader indholdspakken, uploades denne tidsplan for opdatering sammen med datasættet. Hvis du ændrer tidsplanen for opdatering, skal du publicere indholdspakken igen (se ovenfor).

## <a name="delete-an-organizational-content-pack-from-appsource"></a>Slet en organisationsindholdspakke fra AppSource
Du kan kun slette en indholdspakke fra AppSource, hvis du har oprettet den. 

> [!TIP]
> Du kan [slette din forbindelse til en indholdspakke](service-organizational-content-pack-disconnect.md), du ikke har oprettet. Det sletter ikke indholdspakken fra AppSource.
> 
> 

1. Hvis du vil slette en indholdspakke fra AppSource, skal du gå til apparbejdsområdet, hvor du oprettede indholdspakken, vælge tandhjulsikonet ![](media/service-organizational-content-pack-manage-update-delete/cog.png) og vælge **Se indholdspakker**.
2. Vælg **Slet \> Slet**. 
   
   * For gruppemedlemmer, som ikke har tilpasset indholdspakken, fjernes de dashboards og rapporter, der er knyttet til denne indholdspakke, automatisk. De er ikke længere tilgængelige, og indholdspakken vises ikke i navigationsruden.
   * For gruppemedlemmer, som har tilpasset indholdspakken, er alle felter fra den oprindelige indholdspakke væk, næste gang de åbner det tilpassede dashboard.  Men fliser, der er fastgjort fra andre rapporter, vises stadig. De oprindelige indholdspakkerapporter og -datasæt er ikke længere tilgængelige, og indholdspakken vises ikke i navigationsruden.   

## <a name="next-steps"></a>Næste trin
* [Introduktion til organisationsindholdspakker](service-organizational-content-pack-introduction.md)
* [Opret og distribuer en app i Power BI](service-create-distribute-apps.md) 
* Har du flere spørgsmål? [Prøv Power BI-community'et](http://community.powerbi.com/)
