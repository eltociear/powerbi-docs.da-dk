---
title: Opret tilpassede Power BI-svarsider til Cortana
description: Opret tilpassede svarsider til Cortana i Power BI
services: powerbi
documentationcenter: 
author: yaron
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
ms.date: 12/20/2017
ms.author: mihart
ms.openlocfilehash: 79e10c7d47eb5105e0c3e79bd3451315eae6d27e
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/21/2017
---
# <a name="use-power-bi-service-or-power-bi-desktop-to-create-a-custom-answer-page-for-cortana"></a>Du kan bruge Power BI-tjenesten eller Power BI Desktop til at oprette en tilpasset svarside til Cortana
Få det fulde udbytte ud af Power BI ved at oprette særlige rapportsider, *Cortana-svarsider* (optræder undertiden også under benævnelsen "Cortana-svarkort"), udviklet specielt til at besvare Cortana spørgsmål.

![](media/service-cortana-answer-cards/power-bi-cortana.png)

> [!IMPORTANT]
> Hvis du prøver eksempelvisning af Cortana- og Power BI-**dashboard**, kan du springe resten af denne artikel over. Der er ingen krav om konfiguration, før Cortana er i stand til at søge i dine Power BI-dashboards.
> 
> 

## <a name="before-you-begin"></a>Inden du starter
Vi har fire dokumenter, der hjælper dig igennem konfiguration og anvendelse af Cortana til Power BI. Hvis du ikke allerede har gjort det, anbefaler vi, at du starter med at læse artikel 1. Og artikel 2 er vigtig, fordi den beskriver nogle trin, du skal tage, før du kan begynde at bruge Cortana-svarsiderne.

**Artikel 1** [Find ud af, hvordan Cortana og Power BI arbejder sammen](service-cortana-intro.md)

**Artikel 2**: [Søgning efter Power BI-rapporter: Aktivér Windows-integration mellem Cortana og Power BI](service-cortana-enable.md)

**Artikel 3**: Denne artikel

**Artikel 4**: [Fejlfinding af problemer](service-cortana-troubleshoot.md)

## <a name="create-a-cortana-answer-page-designed-specifically-for-cortana"></a>Opret en Cortana-svarside, der er udviklet specielt til Cortana
En *Cortana-svarside* i en rapport har en størrelse specielt afpasset til Cortana, så Cortana kan få den vist på skærmen som et svar på et spørgsmål.  Sådan opretter du en svarside til Cortana:

1. Det anbefales at starte med en [tom rapportside](power-bi-report-add-page.md).
2. I ruden **Visualiseringer** skal du vælge malerrulleikonet og vælge **Sidestørrelse > Type > Cortana**.
   
    ![](media/service-cortana-answer-cards/pbi-cortana-page-size-new.png)
3. Opret et visuelt element eller et sæt af visuelle elementer, der skal vises i Cortana som svar på et bestemt spørgsmål (eller en række spørgsmål).
4. Kontrollér, at alle visuelle elementer falder inden for sidens kanter.  Rediger eventuelt visningsindstillinger, datanavne, farver og baggrunde.  
   
    ![](media/service-cortana-answer-cards/pbi_cortana_modify-new.png)
5. Navngiv siden, og tilføj alternative navne.  Cortana bruger disse navne, når der søges efter resultater. I ruden **Visualiseringer** skal du vælge malerkostikonet og vælge **Sideoplysninger**. Aktivér Spørgsmål og svar for dette visuelle element ved at flytte skyderen til **Til**.
   
    ![](media/service-cortana-answer-cards/pbi_cortana_names-newer.png)
   
   > [!TIP]
   > Undgå at bruge ord, der også er kolonnenavne, for at få bedre resultater.
   > 
   > 
6. Hvis rapporten indeholder sideniveaufiltre, kan du eventuelt angive **Kræv enkeltvalg**. Cortana viser kun denne rapport som et svar, hvis et – og kun ét – af filterelementerne er angivet i spørgsmålet. **Kræv enkeltvalg** findes i bunden i ruden **Filtre**.
   
   > [!NOTE]
   > Du behøver ikke at indstille **Kræv enkeltvalg** for at bede Cortana om at vise en rapport med sideniveaufiltre.  "vis salg for Charlotte Lindseys" vil f.eks. vise svarsiden uanset indstillingen Kræver enkeltvalg.
   > 
   > 
   
     ![](media/service-cortana-answer-cards/pbi-cortana-single-selection-new.png)
   
      Hvis du beder Cortana om f.eks.:
   
   * "at vise salg efter lagernavn," vises denne svarside ikke, fordi du ikke inkluderede nogen af elementerne i det krævede sideniveaufilter.
   * "at vise salg for Cary Lindseys og Charlotte Lindseys", vises denne svarside ikke, fordi du har angivet mere end ét element fra det nødvendige sideniveaufilter.
   * "at vise salg for Charlotte Lindseys," vises denne svarside.
     
     "at vise salg", vises denne svarside ikke, fordi du ikke inkluderede nogen af elementerne i det krævede sideniveaufilter.

> [!IMPORTANT]
> Før Cortana kan få adgang til din Cortana-svarside, skal du [Aktivere datasættet for Cortana](service-cortana-enable.md).
> 
> 

## <a name="how-does-cortana-order-the-results"></a>Hvordan sorteres resultaterne af Cortana?
Resultater med svar med en høj score (f.eks et fuldstændigt match på et specificeret sidenavn) vil blive vist først som et *bedste match* i Cortana. Der kan forekomme flere bedste match, hvis der er mange Cortana-svarsider i Power BI. Svar med mellemstor eller lav score, f.eks. svar, der ikke er baseret på navnet på en svarside eller et spørgsmål med ord, som ikke er forstået af Power BI, angives som links neden under bedste match i Cortana.

> [!NOTE]
> Når et nyt datasæt eller en tilpasset Cortana-svarside er føjet til Power BI og er aktiveret for Cortana, kan det tage op til en halv time, før resultaterne begynder at blive vist i Cortana. Hvis du logger på og af Windows 10 eller på anden måde genstarter Cortana-processen i Windows 10, vil nyt indhold kunne vises med det samme.
> 
> 

## <a name="next-steps"></a>Næste trin
[Brug af Cortana med Power BI](service-cortana-intro.md)

Kan du stadigvæk ikke få Cortana til at fungere med Power BI?  Prøv [Cortana-fejlfindingsværktøj](service-cortana-troubleshoot.md).

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
