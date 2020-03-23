---
title: Power BI-API'er, der bruger politik for automatisk opbevaring for data i realtid
description: Få mere at vide om politikken for automatisk opbevaring i Power BI-tjenesten
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 3ac4c28b3f07cb1a19e241089b54ee4594a7a7dd
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/14/2020
ms.locfileid: "79378288"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Politik for automatisk opbevaring for data i realtid

Politikken for automatisk opbevaring i Power BI-tjenesten er en parameter for en forespørgselsstreng, som gør det muligt for en standardopbevaringspolitik at rydde op i gamle data automatisk, samtidig med at en konstant strøm af nye data overføres til dit dashboard. Den første opbevaringspolitik kaldes *FIFO (først ind – først ud)* . Når den er aktiveret, samles dataene i en tabel, indtil den når 200.000 rækker. Når der er flere end 200.000 rækker med data, slettes de ældste rækker fra datasættet. På den måde gemmes mellem 200.000 og 210.000 rækker med de nyeste data.  
  
<center>

![opbevaringspolitik](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Politikkerne for opbevaring er aktiveret, når du opretter dine datasæt. Du skal blot føje parameteren "default retention policy" til dit kald til POST-datasæt og angive den til lig med *basicFIFO*.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}