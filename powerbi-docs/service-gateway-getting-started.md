---
title: Introduktion til Power BI-gateways
description: "Lær det grundlæggende om datagateways til Power BI."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 14c96dbc88784cd76099c25508409bcc24064e35
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/25/2018
---
# <a name="getting-started-with-power-bi-gateways"></a>Introduktion til Power BI-gateways
Velkommen til vejledningen **Introduktion til Power BI-gateways**. Denne korte gennemgang gør dig bekendt med, hvad en gateway gør, hvordan den fungerer, og hvordan du får din egen gateway installeret, konfigureret og op at køre.  

![](media/service-gateway-getting-started/gw_gettingstarted_0a.png)

Gateways kan være et teknisk emne, og fordi hvert netværk og hver virksomhed er forskellige, kan kompleksiteten af gateways være betydelig. Lad os starte med det grundlæggende for at holde denne kompleksitet lidt på afstand.

## <a name="how-power-bi-gateways-work"></a>Sådan fungerer Power BI-gateways
En **gateway** er software, der gør det nemmere at få adgang til data, der er placeret på et privat netværk i det lokale miljø, til efterfølgende brug i en cloudtjeneste som Power BI. Den er som en dørvogter, der lytter efter anmodninger om forbindelse, og kun tildeler dem, når en brugeres anmodninger opfylder visse kriterier (f.eks. om de har tilladelse til at bruge gatewayen). Det gør det muligt for organisationer at lade databaser og lagre blive på deres lokale netværk, og alligevel på sikker vis bruge undersæt af disse data til at oprette overbevisende rapporter og dashboards i Power BI.

En gateway sikrer også adgang og data ved at kryptere og komprimere alle data, der sendes gennem den, samt alle adgangskoder, der bruges til at oprette forbindelse til datakilder. Alt dette lyder umiddelbart ganske enkelt, men der er mange detaljer at tage højde for.

Nogle gange har du brug for en gateway kun til dig selv – du har måske en stor Excel-projektmappe plus tre SQL-databaser med flere års løbende salgs- og markedsføringsdata, og du vil oprette et Power BI-dashboard, der viser disse salgstal fra enhver vinkel. Du er den eneste, der opretter rapporter, det er din Excel-projektmappe, og kun du bruger disse databaser til at oprette Power BI-rapporter. Du skal blot bruge en gateway til personlig brug og ikke dele disse datakilder med alle andre.

På andre tidspunkter er du muligvis i en organisation med alle mulige databaser fra forskellige leverandører, herunder Analysis Services, SAP, Oracle, IBM og forskellige andre datakilder, og du har brug for, at mange personer får adgang til dem, så de kan oprette masser af rapporter. I dette tilfælde skal du bruge en gateway, der gør det muligt at konfigurere adgangen til alle disse datakilder, og derefter skal du dele den med mange personer i din organisation. Det er en helt anden type gateway.

Heldigvis tilbyder Power BI to gateways, der passer glimrende til hvert af disse scenarier. Disse to gatewaytilbud fra Power BI-tilbud er følgende:

* **Datagateway i det lokale miljø (personlig tilstand)** – gør det muligt for én bruger at oprette forbindelse til datakilder og kan ikke deles med andre. Kan kun bruges med Power BI.
* **Datagateway i det lokale miljø** – gør det muligt for flere brugere at oprette forbindelse til flere datakilder i det lokale miljø og kan bruges af Power BI, PowerApps, Flow og Azure Logics-apps, det hele med en enkelt gatewayinstallation.

Begge gateways udfører en tilsvarende funktion – de gør det nemmere at få adgang til data, der er placeret på et privat netværk i det lokale miljø, så disse data kan bruges i cloudbaserede tjenester som Power BI. Den personlige gateway kan bruges af én person og kun af Power BI, **datagatewayen i det lokale miljø** kan benyttes af mange brugere og mange tjenester.

Der er tre dele eller stadier i at gøre en gateway funktionel:

* Installer gatewayen
* Føj brugere til gatewayen (lad dem bruge gatewayen)
* Opret forbindelse til datakilder

Med brug af en gateway kan du derudover gøre noget andet, som kan være vigtigt:

* Opdater data i det lokale miljø, så Power BI-rapporter kan opdateres med nye data

Opdatering af data betyder, at dine Power BI-dashboards og -rapporter ser friske ud og afspejler de nyeste data. Så når en person får vist en rapport, du har oprettet med data i det lokale miljø, kan denne rapport vise de seneste oplysninger, selvom du har oprettet rapporten for et stykke tid siden.

Den første del, at installere en gateway, er nem. Det er også nemt at tillade brugerne at få adgang til gatewayen – du skal blot tilføje dem i en dialogboks i Power BI, og de er klar. Det kan blive komplekst at oprette forbindelse til datakilder, fordi der er så mange datakilder, og de har hver især deres egne forbindelseskrav og små forskelle. Og vi behandler opdatering i en anden vejledning, for at bevare fokus på gatewayen i denne artikel.

Så lad os tage det nemme først og gennemgå installation af en gateway.

## <a name="install-the-gateway"></a>Installer gatewayen
Hvis du vil installere en gateway, skal du åbne Power BI-tjenesten (du kan bruge dette link til at starte Power BI-tjenesten i din browser og logge på) og logge på med din Power BI-konto. Vælg **downloadikonet** i øverste højre hjørne i Power BI-tjenesten, som vist på følgende billede, og vælg **Data Gateway**.

![](media/service-gateway-getting-started/gw_gettingstarted_01.png)

Så kommer du til en downloadside, hvor du klikker på knappen **Download gateway** for at starte download.

![](media/service-gateway-getting-started/gw_gettingstarted_02.png)

Dette skærmbillede giver dig den meget korte forklaring på, hvad en gateway gør. Det indeholder også et par vigtige **advarsler** – når du installerer en gateway, kører den rent faktisk på den computer, hvor du udfører installationen. Og hvis computeren slukkes, så slukkes gatewayen også (den vil altså ikke fungere, når den ikke kører). Det er heller ikke bedst at installere på en computer, der bruger et trådløst netværk, så du skal bruge en computer, der er forbundet med et kabeltilsluttet netværk.

Når du er klar, skal du vælge **Næste** for at fortsætte med installationen.

![](media/service-gateway-getting-started/gw_gettingstarted_03.png)

Det er her, du beslutter, hvilken gateway der skal installeres – gateway i det lokale miljø eller en personlig gateway. I denne vejledning skal vi installere **datagatewayen i det lokale miljø**.

Der er et par ting at være opmærksom på i forbindelse med denne beslutning:

* Begge gateways kræver 64-bit Windows-operativsystemer.
* Gateways kan ikke installeres på en domænecontroller.
* Du kan installere op til to datagateways i det lokale miljø på den samme computer, en i hver tilstand (personlig og standard). 
* Du kan ikke have mere end én gateway, der kører i den samme tilstand på samme computer.
* Du kan installere flere datagateways i det lokale miljø på forskellige computere og administrere dem alle fra den samme grænseflade i Power BI til administration af gateways (undtagen personlige, se følgende punkttegn).
* Du kan kun have én gateway i personlig tilstand, der kører for hver bruger af Power BI. Hvis du installerer endnu en gateway i personlig tilstand for den samme bruger, selv på en anden computer, erstatter den nyeste installation den tidligere eksisterende installation.

Når vi vælger **Næste**, starter installationen af gatewayen. Du skal angive, hvor den vil blive installeret, og standardplaceringen er normalt bedst.

![](media/service-gateway-getting-started/gw_gettingstarted_06.png)

Installationsprocessen er hurtig, og du får vist en statuslinje.

![](media/service-gateway-getting-started/gw_gettingstarted_06a.png)

Når du næsten er færdig, skal du identificere kontoen, der skal bruges med gatewayen. Det bør være den konto (brugernavn og adgangskode), du bruger til at logge på Power BI. Gatewayen er knyttet til din Power BI-konto, og du kan konfigurere gateways i Power BI-tjenesten.

![](media/service-gateway-getting-started/gw_gettingstarted_07.png)

Du bliver logget på, som det vises på følgende billede.

![](media/service-gateway-getting-started/gw_gettingstarted_08.png)

Når du er logget på, skal du oprette en **genoprettelsesnøgle**. De beskrives mere detaljeret i en anden artikel, men lige nu er det nok at vide, at du skal bruge den til at genoprette eller flytte din gateway.

![](media/service-gateway-getting-started/gw_gettingstarted_09.png)

Når alt går, som det skal, får du vist et vindue med oplysninger om, at din gateway er klar.

![](media/service-gateway-getting-started/gw_gettingstarted_10.png)

Det var det hele til installation af en gateway i det lokale miljø. Som lovet var det en ganske nem proces. Det næste trin er enten at **tilføje brugere** eller **tilføje datakilder** – du kan tilføje en af dem først og derefter tilføje den anden efter din indledende konfiguration.

I det næste afsnit beskrives det, hvordan du føjer brugere til gatewayen, og derefter behandler vi, hvor du så går hen for at føje datakilder til gatewayen.

## <a name="add-users-to-a-gateway"></a>Føj brugere til en gateway
Nu hvor vi har installeret en gateway, skal vi administrere gatewayen fra **Power BI-tjenesten**. Vælg tandhjulsikonet i øverste højre hjørne i Power BI-tjenesten for at komme til skærmbilledet til administration af gateways, og vælg derefter **Administrer gateways**.

![](media/service-gateway-getting-started/gw_gettingstarted_15.png)

Der vises en side i Power BI-tjenestens canvas, hvor du kan administrere dine gateways. Siden **Indstillinger for gateway** ligner følgende.

![](media/service-gateway-getting-started/gw_gettingstarted_12.png)

Hvis du trykker eller klikker på **Administratorer**, kan du se følgende administrationsside for administratorer. Bemærk, at det kun er, hvilke brugere der kan *administrere* gatewayen, og at brugere af gatewayen tilføjes (eller fjernes) fra hver enkelt datakilde ved hjælp af en anden side – som vi gennemgår i de næste par afsnit.

![](media/service-gateway-getting-started/gw_gettingstarted_13.png)

Når du har installeret og valideret (oprettet forbindelse til) en datakilde, vises den under dens tilknyttede gateway i venstre side af skærmbilledet **Administrer gateways**, som det vises på følgende billede. Bemærk, at der i den højre rude er to afsnit, du kan skifte mellem: **Indstillinger for datakilde** og **Brugere**. Skærmbilledet lige efter er afsnittet **Indstillinger for datakilde**.

![](media/service-gateway-getting-started/gw_gettingstarted_16.png)

Når du vælger **Brugere**, får du vist et tekstfelt, hvor du kan indtaste brugere fra din organisation, som du vil give adgang til den valgte datakilde. På følgende skærmbillede kan du se, at jeg har tilføjet Maggie og Adam.

Når du begynder at indtaste en mailadresse i tekstfeltet, viser Power BI en liste over de brugere, hvis mail matcher det, som du skriver, så du kan klikke på navnet og føje dem til listen.

Du kan også tilføje mailgrupper (aliasser) for at give grupper af personer adgang, samt enkeltpersoner.

![](media/service-gateway-getting-started/gw_gettingstarted_17.png)

Når du har valgt **Tilføj**, vises de tilføjede medlemmer i feltet, og du kan tilføje flere, hvis du vil. Det er lige så let at fjerne brugere. Du skal blot markere afkrydsningsfeltet ud for brugerens navn og derefter vælge knappen **Fjern** under feltet.

![](media/service-gateway-getting-started/gw_gettingstarted_18.png)

Så nemt er det. Vær opmærksom på, at du skal føje brugere til hver enkelt datakilde, du vil give adgang til. Hver enkelt datakilde har en separat liste over brugere, og du skal føje brugere til hver enkelt datakilde særskilt.

## <a name="adding-data-sources"></a>Tilføj datakilder
For at gøre din gateway brugbar skal du selvfølgelig tilføje datakilder. Dette er her, hvor noget af kompleksiteten i Power BI-gateways kommer ind i billedet – der er mange forskellige tilgængelige datakilder, og de har hver især deres egne krav (og ofte deres egen påkrævede driver).

Men før vi sender dig videre til en anden artikel, kan du her se, hvordan du får tilføjet en datakilde. Mens du er på siden **Administrer gateways** i **Power BI-tjenesten**, skal du vælge gatewayen, som du vil føje en datakilde til, og vælge **Tilføj datakilde** i det øverste venstre hjørne af siden lige over listen med dine gateways.

Når du gør det, vises panelet **Indstillinger for datakilde** i den højre rude, som det vises på følgende billede. Der kan du navngive datakilden (angivet i tekstfelt **Navn på datakilde**) og vælge typen på rullelisten **Datakildetype**.

![](media/service-gateway-getting-started/gw_gettingstarted_14.png)

Vi har nu en gateway installeret, og du er klar til at tilføje datakilder. Fantastisk! Se ressourcerne i følgende afsnit for at få oplysninger om datakilder, flere oplysninger om brug af gateways og andre nyttige oplysninger.

## <a name="next-steps"></a>Næste trin
[Brug datagatewayen i det lokale miljø](service-gateway-onprem.md)  
[Datagateway i det lokale miljø – detaljeret](service-gateway-onprem-indepth.md)  
[Datagateway i det lokale miljø (personlig tilstand)](service-gateway-personal-mode.md)
[Fejlfinding af datagatewayen i det lokale miljø](service-gateway-onprem-tshoot.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)

