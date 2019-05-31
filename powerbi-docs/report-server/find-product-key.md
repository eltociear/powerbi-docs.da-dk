---
title: Sådan finder du produktnøglen til din rapportserver
description: Se, hvordan du finder produktnøglen til din Power BI-rapportserver, så du kan installere din server i et produktionsmiljø.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 10/24/2018
ms.author: maggies
ms.openlocfilehash: 42057ba7cea04f432a39d649c9a4eecc34a0883d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "64769620"
---
# <a name="how-to-find-your-report-server-product-key"></a>Sådan finder du produktnøglen til din rapportserver
Se, hvordan du finder produktnøglen til din Power BI-rapportserver, så du kan installere din server i et produktionsmiljø.

<iframe width="640" height="360" src="https://www.youtube.com/embed/6CQnf-NGtpU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

Du har downloadet Power BI-rapportserver, og du har en SQL Server Enterprise Software Assurance-aftale. Eller du har købt Power BI Premium. Du vil installere serveren i et produktionsmiljø, men du skal bruge en produktnøgle til formålet. Hvor er produktnøglen? 

Produktnøglen kan være placeret to forskellige steder. Det afhænger af, hvad du har købt.

## <a name="purchased-power-bi-premium"></a>Har købt Power BI Premium
Hvis du har købt Power BI Premium, finder du produktnøglen til Power BI-rapportserver under fanen **Kapacitetsindstillinger** på Power BI-administrationsportalen. Den kan kun tilgås af globale administratorer eller brugere, som er tildelt rollen som administrator af Power BI-tjenesten.

![Nøgle til Power BI-rapportserver i Premium-indstillinger](media/find-product-key/pbirs-product-key.png)

Når du vælger **Power BI-rapportserver-nøgle**, vises der en dialogboks med din produktnøgle. Du kan kopiere den og bruge den med installationen.

![Produktnøgle til Power BI-rapportserver](media/find-product-key/pbirs-product-key-dialog.png)

## <a name="purchased-software-assurance-agreement"></a>Har købt en Software Assurance-aftale
Hvis du har en SQL Server Enterprise SA-aftale, kan du få din produktnøgle fra [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/). Se efter den seneste version af SQL Server under den seneste servicepakke. Hvis du ikke kan se versionen der, skal du se under RTM-frigivelsen af den seneste SQL Server-version.

> [!NOTE]
> Du skal kigge under downloadsektionen. Ikke i nøglesektionen.
> 
> 

![](media/find-product-key/vlsc-download.png "Volume Licensing Service Center")

## <a name="next-steps"></a>Næste trin
[Installer Power BI-rapportserver](install-report-server.md)  
[Installer Power BI Desktop optimeret til Power BI-rapportserver](install-powerbi-desktop.md)  
[Download Report Builder](https://www.microsoft.com/download/details.aspx?id=53613)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

