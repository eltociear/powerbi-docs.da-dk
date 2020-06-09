---
title: Oprettelsesapp for tjenesteprincipal
description: Oprettelsesapp for tjenesteprincipal
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 05/20/2020
ms.custom: include file
ms.openlocfilehash: 0fe3e1743cb8853d6626b59b748d70bfcc292dbd
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315760"
---
1. Log på [Microsoft Azure](https://ms.portal.azure.com/#allservices).

2. Søg efter **appregistreringer**, og klik på linket **Appregistreringer**.

    ![azure-appregistrering](media/embedded-service-principal/azure-app-registration.png)

3. Klik på **Ny registrering**.

    ![ny registrering](media/embedded-service-principal/new-registration.png)

4. Udfyld de påkrævede oplysninger:
    * **Navn** – Angiv et navn til programmet
    * **Understøttede kontotyper** – Vælg understøttede kontotyper
    * (Valgfrit) **URI til omdirigering** – Angiv en URI, hvis det er nødvendigt

5. Klik på **Registrer**.

6. Efter registrering er *program-id'et* tilgængeligt via fanen **Oversigt**. Kopiér og gem *program-id'et* til senere brug.

    ![program-id](media/embedded-service-principal/application-id.png)