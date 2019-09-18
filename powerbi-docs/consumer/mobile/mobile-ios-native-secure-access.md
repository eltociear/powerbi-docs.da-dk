---
title: Beskyttelse af data i Power BI med identifikation af oprindelig enhed
description: Få mere at vide om, hvordan du konfigurerer din iOS-app til at kræve yderligere identifikation, før du kan få adgang til dine data i Power BI
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/07/2019
ms.author: mshenhav
ms.openlocfilehash: b7418c9579a439a18a30a967947c15d58693fd44
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/16/2019
ms.locfileid: "66816817"
---
# <a name="protect-power-bi-app-with-face-id-touch-id-or-passcode"></a>Beskyt Power BI-app med Face ID, Touch ID eller adgangskode 

I mange tilfælde er de data, der administreres i Power BI fortrolige og skal beskyttes, så kun godkendte brugere har adgang til dem. 

Med Power BI-appen til iOS kan du beskytte dine data ved at konfigurere yderligere identifikation. Du skal angive Face ID, Touch ID eller en adgangskode, hver gang du starter appen, eller når du flytter appen fra baggrunden til forgrunden.

| ![iPhone](./media/tutorial-mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](./media/tutorial-mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhone-telefoner |iPad-tablets |

## <a name="turn-on-face-id-touch-id-or-passcode-in-app-setting"></a>Slå Face ID, Touch ID eller adgangskoden til i appindstillingerne

Hvis du vil bruge yderligere identifikation i Power BI, skal du gå til appindstillingen under **Beskyttelse af personlige oplysninger og sikkerhed**. Du kan se indstillingen til aktivering af Face ID, Touch ID eller adgangskode, afhængigt af din enheds egenskaber.

![Indstillingssiden for Power BI-appen til iOS](./media/mobile-ios-native-secure-access/mobile-ios-native-secured-setting.png)

Når denne indstilling er aktiveret, bliver du bedt om at angive dit id, før du kan få adgang til appen, hver gang du starter Power BI eller flytter appen fra baggrunden. 

En eventuel anmodning om Face ID, Touch ID eller adgangskode kommer fra iOS, afhængigt af enhedens egenskab. Hvis din enhed understøtter Face ID, skal du bruge Face ID. Hvis den enhed understøtter Touch ID, skal du bruge Touch ID. Hvis ingen af delene understøttes, skal du angive en adgangskode.

![iOS Face ID i Power BI](./media/mobile-ios-native-secure-access/mobile-ios-native-secured-faceid.png)

## <a name="use-mdm-to-enforce-face-id-touch-id-or-passcode"></a>Brug MDM til at gennemtvinge Face ID, Touch ID eller adgangskode

Nogle organisationer har politikker for sikkerhed og krav til overholdelse af angivne standarder, der gennemtvinger yderligere identifikation, før du kan få adgang til følsomme virksomhedsdata. 

Power BI-appen til iOS gør det muligt for administratorer at styre denne indstilling ved at pushe konfigurationsindstillingerne for appen fra Microsoft Intune og andre MDM-løsninger (Mobile Device Management). Administratorer kan bruge appbeskyttelsespolitikken til at aktivere denne indstilling for alle brugere eller en gruppe af brugere.

|Nøgle  |Type  |Beskrivelse  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Boolesk | Standardværdien er False. <br>Når den er angivet til True, gennemtvinger appen, at brugerne skal identificere sig selv med Face ID, Touch ID eller adgangskode, før de er i stand til at få vist alle Power BI-data i appen. Brugere, der ikke har Face ID, Touch ID eller en adgangskode konfigureret på deres enhed, skal konfigurere dette, før de kan få adgang til Power BI.  |

## <a name="next-steps"></a>Næste trin

[Brug MDM til at fjernkonfigurere Power BI-appen til iOS](mobile-app-configuration.md)
