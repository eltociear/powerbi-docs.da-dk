---
title: Oversigt over udrulningspipelines
description: Få mere at vide om udrulningspipelines i Power BI
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.date: 05/06/2020
ms.openlocfilehash: 5522d84cab235270a2eb368be02cfa0fb4e5eaa9
ms.sourcegitcommit: 10c5b6cd5e7070f96de8a9f1d9b95f3d242ac7f2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/21/2020
ms.locfileid: "86557135"
---
# <a name="introduction-to-deployment-pipelines-preview"></a>Introduktion til udrulningspipelines (prøveversion)

I dagens verden er analyser en vigtig del af beslutningsprocessen i næsten alle organisationer. Den voksende brug af Power BI som analyseværktøj kræver, at der bruges flere data, at analyserne tager sig godt ud, og de er brugervenlige. Først og fremmest skal Power BI dog altid være tilgængelig og pålidelig. BI-udviklere skal kunne samarbejde effektivt for at imødekomme disse krav.

Udrulningspipelines er et effektivt værktøj, der kan genbruges, og som gør det muligt for BI-udviklere i en virksomhed med en Premium-kapacitet at administrere livscyklussen for indhold i organisationen. En udrulningspipeline gør det muligt at udvikle og teste Power BI-indhold, f.eks. rapporter, dashboards og datasæt, før de forbruges af slutbrugere.

Værktøjet er designet som en pipeline med tre faser:

* **<a name="development"></a>Udvikling**
    
    Denne fase bruges til at designe, opbygge og overføre nyt indhold samme med andre udviklere. Dette er det første fase i udrulningspipelines.

* **<a name="test"></a>Test**

    Når indholdet er uploadet, og alle ændringer er foretaget i udviklingsfasen, kan indholdet flyttes til denne fase for at blive testet. Her er tre eksempler på, hvad der kan foretages i testmiljøet:

    * Del indhold med testere og reviewere

    * Indlæs og kør test med store datamængder

    * Test din app for at se, hvordan den vil se ud for slutbrugerne

* **<a name="production"></a>Produktion**

    Når du har testet indholdet, kan du bruge produktionsfasen til at dele den endelige version af dit indhold med virksomhedsbrugere på tværs af organisationen.

![Et skærmbillede af en udrulningspipeline med alle tre trin – udvikling, test og produktion – udfyldt.](media/deployment-pipelines-overview/deployment-pipelines.png)

## <a name="next-steps"></a>Næste trin

>[!div class="nextstepaction"]
>[Kom i gang med udrulningspipelines](deployment-pipelines-get-started.md)

>[!div class="nextstepaction"]
>[Om processen for udrulningspipelines](deployment-pipelines-process.md)

>[!div class="nextstepaction"]
>[Fejlfinding af udrulningspipelines](deployment-pipelines-troubleshooting.md)

>[!div class="nextstepaction"]
>[Bedste fremgangsmåder for udrulningspipelines](deployment-pipelines-best-practices.md)