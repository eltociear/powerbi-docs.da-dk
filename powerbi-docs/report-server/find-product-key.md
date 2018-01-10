---
title: "Sådan finder du produktnøglen til din rapportserver"
description: "Se, hvordan du finder produktnøglen til din Power BI-rapportserver, så du kan installere din server i et produktionsmiljø."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 13bf32939630a813f2f942fc2075f25c7bc1374a
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/06/2018
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

## <a name="purchased-software-assurance-agreeemnt"></a>Har købt en Software Assurance-aftale
Hvis du har en SQL Server Enterprise SA-aftale, kan du få din produktnøgle fra [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/). Se efter den seneste version af SQL Server under den seneste servicepakke. Hvis du ikke kan se versionen der, skal du se under RTM-frigivelsen af den seneste SQL Server-version.

> [!NOTE]
> Du skal kigge under downloadsektionen. Ikke i nøglesektionen.
> 
> 

![](media/find-product-key/vlsc-download.png "Volume Licensing Service Center")

## <a name="next-steps"></a>Næste trin
[Hurtigstart: Installér Power BI-rapportserver](quickstart-install-report-server.md)  
[Installér Power BI Desktop optimeret til Power BI-rapportserver](install-powerbi-desktop.md)  
[Installer Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)

