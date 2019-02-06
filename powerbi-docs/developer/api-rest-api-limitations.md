---
title: Begrænsninger for REST-API'er til Power BI
description: Der er følgende begrænsninger for Power BI REST-API'en
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: ebca3dd6bcdbb831960da111fc167f59b5ab0623
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762001"
---
# <a name="power-bi-rest-api-limitations"></a>Begrænsninger for REST-API'er til Power BI  
  
**Til POST-rækker**
  
* Maks. 75 kolonner
* Maks. 75 tabeller
* Maks. 10.000 rækker pr. enkelt anmodning om POST-rækker  
* 1.000.000 rækker tilføjet pr. time pr. datasæt  
* Maks. 5 ventende anmodninger om POST-rækker pr. datasæt  
* 120 anmodninger om POST-rækker pr. minut pr. datasæt
* Hvis tabellen indeholder 250.000 rækker eller flere, 120 anmodninger om POST-rækker pr. time pr. datasæt
* Maks. 200.000 rækker, der lagres pr. tabel i FIFO datasæt
* Maks. 5.000.000 rækker, der lagres pr. tabel i 'none rentention policy'-datasæt  
* 4.000 tegn pr. værdi for strengkolonne i POST-rækkehandling
  
## <a name="see-also"></a>Se også

[Grænser og begrænsninger for Azure AD-tjenesten](https://docs.microsoft.com/azure/active-directory/active-directory-service-limits-restrictions)   
[Oversigt over Power BI REST-API](https://docs.microsoft.com/rest/api/power-bi/)