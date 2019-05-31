---
title: Opret forbindelse til Smartsheet med Power BI
description: Smartsheet til Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 841201aa87139b9630d6fc076d57109fb2b09804
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578971"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Opret forbindelse til Smartsheet med Power BI
Denne artikel fører dig gennem trække dine data fra din Smartsheet-konto med en app i Power BI-skabelon. Smartsheet byder på en nem platform til samarbejde og fildeling. Appen skabelon Smartsheet til Power BI indeholder et dashboard, rapporter og datasæt, der viser en oversigt over din Smartsheet-konto. Du kan også bruge [Power BI Desktop](desktop-connect-to-data.md) til at oprette forbindelse direkte til individuelle ark i din konto. 

Når du har installeret appen skabelon, kan du ændre dashboardet og rapporten. Derefter kan du distribuere den som en app til kollegaer i din organisation.

Opret forbindelse til den [Smartsheet skabelonapp](https://app.powerbi.com/groups/me/getdata/services/smartsheet) til Power BI.

>[!NOTE]
>Et Smartsheet-administratorkontoen er den foretrukne metode til at oprette forbindelse og indlæsning af skabelon Power BI-appen, da den har ekstra adgang.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. Vælg **Smartsheet** \> **Hent det nu**.
4. I **installere denne App i Power BI?** Vælg **installere**.
4. I den **Apps** skal du vælge den **Smartsheet** felt.

    ![Power BI Smartsheet appfeltet](media/service-connect-to-smartsheet/power-bi-smartsheet-tile.png)

6. I **Kom i gang med din nye app**, skal du vælge **forbinde data**.

    ![Kom i gang med din nye app](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

4. Til Godkendelsesmetode skal du vælge **oAuth2\> Log på**.
   
   Når du bliver spurgt, skal du angive dine legitimationsoplysninger til Smartsheet og følge godkendelsesprocessen.
   
   ![Legitimationsoplysninger til Smartsheet](media/service-connect-to-smartsheet/creds.png)
   
   ![Smartsheet logon](media/service-connect-to-smartsheet/creds2.png)

5. Når Power BI har importeret dataene, åbner dashboardet Smartsheet.
   
   ![Smartsheet-dashboard](media/service-connect-to-smartsheet/power-bi-smartsheet-dashboard.png)

## <a name="modify-and-distribute-your-app"></a>Rediger og Distribuer din app

Du har installeret appen Smartsheet-skabelon. Det betyder, at du har også oprettet Smartsheet app-arbejdsområdet. Du kan ændre rapporten og dashboardet i arbejdsområdet, og derefter distribuere den som en *app* til kollegaer i din organisation. 

1. For at få vist hele indholdet af det nye Smartsheet-arbejdsområde i venstre navigationslinje, skal du vælge **arbejdsområder** > **Smartsheet**. 

    ![Smartsheet-arbejdsområde i venstre navigationsrude](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace.png)

    Denne visning er listen over indhold til arbejdsområdet. I det øverste højre hjørne skal du se **Opdater app**. Når du er klar til at distribuere din app til dine kollegaer, er, hvor du vil starte. 

    ![Smartsheet indholdsliste](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace-content.png)

2. Vælg **rapporter** og **datasæt** at se de andre elementer i arbejdsområdet.

    Læs om [distribuere apps](service-create-distribute-apps.md) til dine kollegaer.

## <a name="whats-included"></a>Det følgende er inkluderet
Smartsheet skabelonapp til Power BI indeholder en oversigt over din Smartsheet-konto, f.eks antallet arbejdsområder, rapporter og ark, du har, når de er blevet redigeret osv. Brugere, administratorer kan du også se nogle oplysninger om brugerne i deres system, f.eks oprettere af øverste ark.  

Du kan også bruge Smartsheet-forbindelseskomponenten i [Power BI Desktop](desktop-connect-to-data.md) til at oprette direkte forbindelse til individuelle ark i din konto.  

## <a name="next-steps"></a>Næste trin

* [Opret nye arbejdsområder i Power BI](service-create-the-new-workspaces.md)
* [Installér og brug apps i Power BI](consumer/end-user-apps.md)
* [Opret forbindelse til Power BI-apps til eksterne tjenester](service-connect-to-services.md)
* Har du spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)