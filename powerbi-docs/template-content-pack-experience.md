---
title: Skabelon til oplevelse af indholdspakke i Power BI
description: Skabelon til oplevelse af indholdspakke
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maggies
ms.openlocfilehash: 23a8875479197f1d200a9f086fcfd27d483faf40
ms.sourcegitcommit: 3a287ae4ab16d1e76caed651bd8ae1a1738831cd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/19/2018
ms.locfileid: "39157341"
---
# <a name="template-content-pack-experiences-in-power-bi"></a>Skabelon til oplevelse af indholdspakke i Power BI
I dette afsnit fremhæves en oplevelse, der er typisk for en bruger, der opretter forbindelse til en ISV[-indholdspakke](service-connect-to-services.md).

Prøv selv at udføre forbindelsesoplevelsen ved at oprette forbindelse til en udgivet indholdspakke på https://app.powerbi.com/getdata/services (f.eks. [GitHub-indholdspakken](https://app.powerbi.com/getdata/services/github), der er beskrevet nedenfor).

## <a name="connect"></a>Opret forbindelse
For at komme i gang skal en bruger gennemse galleriet med indholdspakker og vælge en indholdspakke, der skal oprettes forbindelse til. Posten i indholdspakken viser et navn, et ikon og en beskrivende tekst, som giver brugeren flere oplysninger.

![opret forbindelse](media/template-content-pack-experience/github_data.png)

![opret forbindelse](media/template-content-pack-experience/github_connect.png)

## <a name="parameters"></a>Parametre
Når den er valgt, bliver brugeren bliver bedt om at angive parametre (hvis det er påkrævet). Dialogboksen med parametre vises med en erklæring, som forfatteren skrev under oprettelse af indholdspakken.

I øjeblikket er brugergrænsefladen for parametre meget grundlæggende – det er ikke muligt at optælle rullelisterne og validering af datainput er begrænset til regex.

![parametre](media/template-content-pack-experience/github_params.png)

## <a name="credentials"></a>Legitimationsoplysninger
Efter at have angivet parametre bliver brugeren bedt om at logge på.  Hvis kilden understøtter flere typer godkendelse, skal brugeren vælge den relevante indstilling. Hvis kilden kræver OAuth, vises brugergrænsefladen for logon til tjenesten, når brugeren trykker på Log på.  Ellers kan brugeren angive legitimationsoplysningerne i den dialogboks, der åbnes.

![Legitimationsoplysninger](media/template-content-pack-experience/github_login.png)

![opret forbindelse](media/template-content-pack-experience/github_creds2.png)

## <a name="instantiation"></a>Instantiering
Når der er logget på, vises de artefakter, der er inkluderet i indholdspakken – model, rapporter og dashboard – på navigationslinjen.  Disse artefakter føjes til de enkelte brugeres konto.  Dataene indlæses asynkront for at udfylde datasættet (modellen).  Brugeren kan derefter bruge dashboardet, rapporterne og modellen.

Der konfigureres som standard en tidsplan for daglig opdatering for brugeren, som evaluerer forespørgslerne i modellen igen.  De legitimationsoplysninger, der er sendt til brugerne, skal give dem tilladelse til at opdatere dataene, uden at de er til stede.

![Instantiering](media/template-content-pack-experience/github_dashboard.png)

## <a name="exploration-and-monitoring"></a>Udforskning og overvågning
Når indholdspakken er integreret i brugernes konto, kan de undersøge og overvåge dataene/indsigterne.

Dette omfatter typisk:

* Visning og tilpasning af dashboardet.
* Visning og tilpasning af rapporten.
* Brug af et naturligt sprog til at stille spørgsmål om dataene
* Brug af udforskningslærredet til at udforske dataene i datamodellen

Det skal overvejes, om det skal være muligt at udføre modellering (synonymer) på et naturligt sprog, og om der skal leveres et forståeligt modelskema for at give bedre udforskningsoplevelser.

