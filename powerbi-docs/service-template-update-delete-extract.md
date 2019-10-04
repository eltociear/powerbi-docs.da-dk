---
title: Opdater, slet og udtræk en Power BI-skabelonapp
description: Sådan opdaterer, sletter og udtrækker du en skabelonapp.
author: teddybercovitz
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/23/2019
ms.author: tebercov
ms.openlocfilehash: 2cf655c25bb58ec001bac52b55aea74f887f08d9
ms.sourcegitcommit: 3885ae11e695f875a82c212ca157e401db8337c4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/24/2019
ms.locfileid: "71207642"
---
# <a name="update-delete-and-extract-template-app"></a>Opdater, slet og udtræk en skabelonapp

Nu, hvor programmet er i produktion, kan du starte forfra i testfasen uden at afbryde programmet i produktion.
## <a name="update-your-app"></a>Opret dit program

Hvis du har foretaget ændringer i Power BI Desktop, skal du starte med trin (1). Hvis du ikke har foretaget ændringer i Power BI Desktop, skal du starte med trin (4).

1. Upload det opdaterede datasæt, og overskriv det eksisterende datasæt. **Sørg for at bruge nøjagtigt det samme navn på datasættet**. Hvis du bruger et andet navn, oprettes det et nyt datasæt for brugere, der opdaterer appen.
![overskriv datasæt](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset.png)
1. Importér PBIX-filen fra din computer.
![overskriv datasæt](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset2.png)
1. Bekræft overskrivningen.
![overskriv datasæt](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset3.png)

1. I ruden **Udgivelsesadministration** skal du vælge **Opret program**.
1. Gå tilbage gennem oprettelsesprocessen for programmet.
1. Når du har angivet **Branding**, **Indhold**, **Kontrolelement** og **Adgang**, skal du vælge **Opret app** igen.
1. Vælg **Luk**, og gå tilbage til **Udgivelsesadministration**.

   Du kan nu se, at du har to versioner: Versionen i produktion samt en ny version i test.

    ![To versioner af et skabelonprogram](media/service-template-apps-update-extract-delete/power-bi-template-app-update.png)

5. Når du er klar til at hæve dit program til præproduktion med henblik på yderligere test uden for din lejer, skal du gå tilbage til ruden Udgivelsesadministration og vælge **Send app videre** ud for **Test**.
6. Dit link er nu live. Send det til Cloud-partnerportalen (CCP) igen ved at følge trinnene for [opdatering af tilbud på Power BI-app](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-update-existing-offer).
7. Du skal **publicere** dit tilbud igen på Cloud Partner Portal og også have det valideret igen.

   >[!NOTE]
   >Du kan først sende din app videre til produktionsfasen, når appen er blevet godkendt af Cloud-partnerportalen, og du har publiceret den.

### <a name="update-behavior"></a>Funktionsmåde ved opdatering

1. Når du opdaterer appen, kan installationsprogrammet for skabelonappen [opdatere en skabelonapp](service-template-apps-install-distribute.md#update-a-template-app) i det allerede installerede arbejdsområde uden at miste forbindelsen til konfigurationen.
1. Se installationsprogrammets [funktionsmåde for overskrivning](service-template-apps-install-distribute.md#overwrite-behavior) for at få mere at vide om, hvordan ændringer i datasættet påvirker den installerede skabelonapp.
1. Når du opdaterer (overskriver) en skabelonapp, vender den først tilbage til eksempeldata og genopretter derefter automatisk forbindelsen til brugerens konfiguration (parametre og godkendelse). Indtil opdateringen er fuldført, vises eksemplet på databanneret i rapporterne, på dashboards og i organisationsappen.
1. Hvis du har føjet en ny forespørgselsparameter til det opdaterede datasæt, der kræver brugerinput, skal du markere afkrydsningsfeltet *påkrævet*. Så sendes der en forespørgsel til installationsprogrammet med forbindelsesstrengen, når appen er opdateret.
 ![påkrævede parametre](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset4.png)

## <a name="extract-workspace"></a>Udtræk arbejdsområde
Det er nu lettere end nogensinde før at gå tilbage til den tidligere version af en skabelonapp med funktionen til udtrækning. I følgende trin udtrækkes en bestemt version af en app fra forskellige versionsfaser til et nyt arbejdsområde:

1. I ruden til administration af versioner skal du trykke på **(...)**  og derefter på **Udtræk**.

    ![udtræk version af skabelonapp](media/service-template-apps-update-extract-delete/power-bi-template-app-extract.png) ![udtræk version af skabelonapp](media/service-template-apps-update-extract-delete/power-bi-template-app-extract-dialog.png)
2. Angiv et navn til det udtrukne arbejdsområde i dialogboksen. der tilføjes et nyt arbejdsområde.

Den nye version af dit arbejdsområde nulstilles, og du kan fortsætte med at udvikle og distribuere skabelonappen fra det arbejdsområde, der er udtrukket for nylig.

## <a name="delete-template-app-version"></a>Slet version af skabelonapp
Arbejdsområdet for en skabelonapp er kilden til en aktiv, distribueret skabelonapp. For at beskytte brugere af skabelonappen er det ikke muligt at slette et arbejdsområde uden først at fjerne alle oprettede versioner af appen i arbejdsområdet.
Hvis du sletter en appversion, sletter du også URL-adressen til appen, og den vil ikke længere fungere.

1. I ruden til administration af versioner skal du vælge ellipsen **(...)**  og derefter **Slet**.
 ![Slet version af skabelonapp](media/service-template-apps-update-extract-delete/power-bi-template-app-delete.png)
  ![Slet version af skabelonapp](media/service-template-apps-update-extract-delete/power-bi-template-app-delete-dialog.png)

>[!NOTE]
>Sørg for, at du ikke sletter den appversion, der anvendes af kunder eller **AppSource**. Hvis du gør det, virker de ikke længere.

## <a name="next-steps"></a>Næste trin

Se, hvordan dine kunder kan interagere med dit skabelonprogram under [Installér, tilpas og distribuer skabelonprogrammer i din organisation](service-template-apps-install-distribute.md).

Du kan se yderligere oplysninger om, hvordan du distribuerer dit program under [Power BI-programtilbud](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).
