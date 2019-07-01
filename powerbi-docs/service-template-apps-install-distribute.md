---
title: Distribuer skabelonprogrammer i din organisation – Power BI
description: Få mere at vide om installation, tilpasning og distribution af skabelonprogrammer i din organisation i Power BI.
author: teddybercovitz
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/10/2019
ms.author: tebercov
ms.openlocfilehash: 158345c44f8801a98e19dcd9b4c7dde14aa6126b
ms.sourcegitcommit: 8c52b3256f9c1b8e344f22c1867e56e078c6a87c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/19/2019
ms.locfileid: "67264524"
---
# <a name="install-and-distribute-template-apps-in-your-organization---power-bi"></a>Installér og distribuer skabelonprogrammer i din organisation – Power BI

Er du Power BI-analytiker? Hvis du er det, så kan du i denne artikel se en forklaring på, hvordan du installerer *skabelonprogrammer* for at oprette forbindelse til mange af de tjenester, du bruger til at drive din forretning, f.eks. Salesforce, Microsoft Dynamics og Google Analytics. Du kan redigere dashboardet og rapporterne, så de opfylder din organisations behov, og derefter distribuere dem til dine kolleger som et *program*. 

![Installerede Power BI-programmer](media/service-template-apps-install-distribute/power-bi-get-apps.png)

Hvis du er interesseret i at oprette skabelonprogrammer, som du selv distribuerer, skal du se [Opret et skabelonprogram i Power BI](service-template-apps-create.md). Power BI-partnere kan udarbejde Power BI-programmer med kun lidt eller ingen kode og udrulle dem til Power BI-kunder. 

## <a name="prerequisites"></a>Forudsætninger  

Her er kravene til installation, tilpasning og distribution af et skabelonprogram: 

- En [Power BI Pro-licens](service-self-service-signup-for-power-bi.md)
- Kendskab til de [grundlæggende begreber i Power BI](service-basic-concepts.md)
- Gyldigt installationslink fra udvikleren af skabelonprogrammet eller AppSource. 
- Tilladelse til at installere skabelonprogrammer. 

## <a name="install-a-template-app"></a>Installér et skabelonprogram

Du modtager måske et link til et skabelonprogram. Ellers kan du søge i AppSource efter et, der interesserer dig. I begge tilfælde kan du redigere det og selv distribuere det i din egen organisation, efter du har installeret det.

### <a name="search-appsource-from-a-browser"></a>Søg i AppSource fra en browser

Vælg dette link for at åbne AppSource, der er filtreret efter Power BI-programmer, i en browser:

- https://appsource.microsoft.com/marketplace/apps?product=power-bi

### <a name="search-appsource-from-the-power-bi-service"></a>Søg i AppSource fra Power BI-tjenesten

1. Vælg **Programmer** > **Hent programmer** i navigationsruden til venstre i Power BI-tjenesten.

    ![Hent apps](media/service-template-apps-install-distribute/power-bi-get-apps-arrow.png)

2. Vælg **Programmer** i AppSource.

    ![Søg i AppSource](media/service-template-apps-install-distribute/power-bi-appsource.png)

3. Gennemse, eller søg efter programmet, og vælg derefter **Hent det nu**.

4. Vælg **Installér** i dialogboksen.

    ![Installér app](media/service-template-apps-install-distribute/power-install-dialog.png) Hvis du har en Power BI Pro-licens, er programmet installeret med dets tilknyttede programarbejdsområde. Du kan tilpasse programmet i det tilknyttede arbejdsområde.

    Når installationen er fuldført, får du vist en meddelelse om, at dit nye program er klar.
4. Vælg **Gå til program**.
5. Vælg en af tre indstillinger under **Kom i gang med dit nye program**:

    ![Kom i gang med dit program](media/service-template-apps-create/power-bi-template-app-get-started.png)

    - **Udforsk programmet**: Grundlæggende udforskning af eksempeldata. Start her for at se nærmere på programmets layout. 
    - **Forbind data**: Skift datakilden fra eksempeldataene til din egen datakilde. Du kan omdefinere parametre for datasæt og legitimationsoplysninger for datakilden. Se [Kendte begrænsninger](service-template-apps-tips.md#known-limitations) i artiklen om tip til skabelonprogrammer. 
    - **Gå til arbejdsområde** (mest avancerede indstilling): Du kan foretage alle de ændringer, der er tilladt af programudvikleren.

    Eller du kan springe denne dialogboks over og få adgang til det tilknyttede arbejdsområde direkte via **Arbejdsområder** i navigationsruden til venstre.
    >[!NOTE]
    >Installation af en skabelonapp installerer både en *organisationsapp* og et *apparbejdsområde*. Læs mere om [distribution af apps i Power BI](service-create-distribute-apps.md).
 
6. Før du deler den med dine kolleger, er det en god idé at oprette forbindelse til dine egne data. Det kan også være en god idé at redigere rapporten eller dashboardet, så de fungerer for din organisation. På dette tidspunkt kan du også tilføje andre rapporter eller dashboards.

   Hvis du vælger et installationslink for en app, der ikke er angivet på AppSource, får du vist valideringsdialogboksen, hvor du skal bekræfte dit valg.

   ![Installér app](media/service-template-apps-install-distribute/power-install-unvalidated-dialog.png)

   >[!NOTE]
   >Du skal anmode om tilladelse fra administratoren for at installere skabelonapps, der ikke er vist på AppSource. Du kan finde flere oplysninger på Power BI[-administrationsportal, indstillingen Skabelonprogram](service-admin-portal.md#template-apps-settings).

## <a name="update-and-distribute-the-app"></a>Opdater og distribuer programmet

Når du har opdateret programmet til din organisation, er du klar til at udgive det. Fremgangsmåden er den samme som udgivelse af et hvilket som helst andet program.

1. Når du er færdig med tilpasningen, skal du vælge **Opdater program** i øverste højre hjørne af listevisningen af arbejdsområdet.  

    ![Start programinstallation](media/service-template-apps-install-distribute/power-bi-start-install-app.png)

2. Under **Detaljer** kan du redigere beskrivelsen og baggrundsfarven.

   ![Angiv beskrivelse og farve for programmet](media/service-template-apps-install-distribute/power-bi-install-app-details.png)

3. Under **Indhold** kan du vælge en landingsside enten på dashboardet eller i rapporten.

   ![Angiv programlandingsside](media/service-template-apps-install-distribute/power-bi-install-app-content.png)

4. Under **Adgang** giver du adgang til de valgte brugere eller til hele organisationen.  

   ![Angiv programadgang](media/service-template-apps-install-distribute/power-bi-install-access.png)

5. Vælg **Opdater program**. 

6. Når det er udgivet, kan du kopiere linket og dele det med alle, du har givet adgang til. Når du har delt det med dem, kan de også se det på fanen **Min organisation** i AppSource.

## <a name="next-steps"></a>Næste trin 

[Opret arbejdsområder med dine kolleger i Power BI](service-create-workspaces.md)





￼ 

 
