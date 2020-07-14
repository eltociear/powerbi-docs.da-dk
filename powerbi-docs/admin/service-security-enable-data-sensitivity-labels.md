---
title: Aktivér følsomhedsmærkater i Power BI
description: Få mere at vide om, hvordan du aktiverer følsomhedsmærkater i Power BI
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 07/06/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: 0fe1b7b1b8175511838005b7b63ca7543bbf939a
ms.sourcegitcommit: 181679a50c9d7f7faebcca3a3fc55461f594d9e7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/07/2020
ms.locfileid: "86034330"
---
# <a name="enable-sensitivity-labels-in-power-bi"></a>Aktivér følsomhedsmærkater i Power BI

Hvis [følsomhedsmærkater i Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) skal bruges i Power BI, skal de være aktiveret i lejeren. Denne artikel viser Power BI-lejeradministratorer, hvordan dette skal gøres. Du kan finde en oversigt over følsomhedsmærkater i Power BI under [Følsomhedsmærkater i Power BI](service-security-sensitivity-label-overview.md). Du kan finde oplysninger om at anvende følsomhedsmærkater i Power BI under [Anvendelse af følsomhedsmærkater](./service-security-apply-data-sensitivity-labels.md) 

Når følsomhedsmærkater aktiveres:

* Visse brugere og sikkerhedsgrupper i organisationen kan klassificere og [anvende følsomhedsmærkater](./service-security-apply-data-sensitivity-labels.md) på deres Power BI-rapporter, dashboards, datasæt og dataflows.
* Alle medlemmer af organisationen kan se disse mærkater.

Aktivering af følsomhedsmærkater kræver en licens til Microsoft Azure Information Protection. Du kan finde flere oplysninger under [Licensering](service-security-sensitivity-label-overview.md#licensing).

## <a name="enable-sensitivity-labels"></a>Aktivér følsomhedsmærkater

Gå til Power BI-**administratorportal**, åbn ruden **Lejerindstillinger**, og find afsnittet **Information Protection**.

![Find afsnittet Information Protection](media/service-security-enable-data-sensitivity-labels/enable-data-sensitivity-labels-01.png)

I afsnittet **Information Protection** skal du udføre følgende trin:
1. Åbn **Tillad, at brugere anvender følsomhedsmærkater til Power BI-indhold**.
1. Aktivér til/fra-funktionen.
1. Definer, hvem der kan anvende og ændre følsomhedsmærkater i Power BI-aktiver. Alle i din organisation kan som standard anvende følsomhedsmærkater. Du kan dog vælge kun at aktivere angivelse af følsomhedsmærkater for bestemte brugere eller sikkerhedsgrupper. Når du har valgt enten hele organisationen eller specifikke sikkerhedsgrupper, kan du udelade bestemte delmængder af brugere eller sikkerhedsgrupper.
   
   * Når følsomhedsmærkater er aktiveret for hele organisationen, er undtagelsen typisk sikkerhedsgrupper.
   * Når følsomhedsmærkater kun er aktiveret for bestemte brugere eller sikkerhedsgrupper, er undtagelsen normalt specifikke brugerne.  
    Denne fremgangsmåde gør det muligt at forhindre visse brugere i at anvende følsomhedsmærkater i Power BI, selvom de tilhører en gruppe, der har tilladelse til at gøre det.

1. Tryk på **Anvend**.

![Aktivér følsomhedsmærkater](media/service-security-enable-data-sensitivity-labels/enable-data-sensitivity-labels-02.png)

> [!IMPORTANT]
> Det er kun Power BI Pro-brugere, som har tilladelse til at *oprette* og *redigere* aktivet, og som er en del af den relevante sikkerhedsgruppe, der blev angivet i dette afsnit, der kan angive og redigere følsomhedsmærkaterne. Brugere, der ikke er en del af denne gruppe, kan ikke angive eller redigere mærkaten.  

## <a name="troubleshooting"></a>Fejlfinding

Power BI bruger følsomhedsmærkater fra Microsoft Azure Information Protection. Så hvis du får vist en fejlmeddelelse, når du forsøger at aktivere følsomhedsmærkater, kan det skyldes en af følgende årsager:

* Du har ikke en [licens](service-security-sensitivity-label-overview.md#licensing) til Microsoft Azure Information Protection.
* Følsomhedsmærkaterne er ikke blevet migreret til den version af Microsoft Azure Information Protection, som understøttes af Power BI. Få mere at vide om [migrering af følsomhedsmærkater](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels).
* Der er ikke defineret nogen følsomhedsmærkater fra Microsoft Azure Information Protection i organisationen. Bemærk, at en mærkat være en del af en publiceret politik, før den kan anvendes. [Få mere at vide om følsomhedsmærkater](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels), eller gå til [Microsoft Security and Compliance Center](https://sip.protection.office.com/sensitivity?flight=EnableMIPLabels) for at se, hvordan du definerer mærkater og publicerer politikker for din organisation.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

Se [Følsomhedsmærkater i Power BI](service-security-sensitivity-label-overview.md#limitations) for at få vist en liste over begrænsninger for følsomhedsmærkater i Power BI.

## <a name="next-steps"></a>Næste trin

Denne artikel indeholdt en beskrivelse af, hvordan du aktiverer følsomhedsmærkater i Power BI. Følgende artikler indeholder flere oplysninger om databeskyttelse i Power BI. 

* [Oversigt over følsomhedsmærkater i Power BI](service-security-sensitivity-label-overview.md)
* [Sådan anvendes følsomhedsmærkater i Power BI](../collaborate-share/service-security-apply-data-sensitivity-labels.md)
* [Brug af Microsoft Cloud App Security-kontrolelementer i Power BI](service-security-using-microsoft-cloud-app-security-controls.md)
* [Rapport over databeskyttelsesmålepunkter](service-security-data-protection-metrics-report.md)