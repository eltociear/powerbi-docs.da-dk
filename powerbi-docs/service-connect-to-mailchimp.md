---
title: Opret forbindelse til MailChimp med Power BI
description: MailChimp til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: f54841b77d79854334ddb6d93ccdc9b5926201ac
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2018
ms.locfileid: "37136688"
---
# <a name="connect-to-mailchimp-with-power-bi"></a>Opret forbindelse til MailChimp med Power BI
Power BI-indholdspakken henter data fra din MailChimp-konto og opretter et dashboard, et sæt rapporter og et datasæt, så du kan udforske dine data. Hent analyser for at oprette [MailChimp-dashboards](https://powerbi.microsoft.com/integrations/mailchimp) og hurtigt spotte tendenser i dine kampagner, rapporter og individuelle abonnenter. Dataene er indstillet til daglig opdatering for at sikre, at de data, du overvåger, er opdaterede.

Opret forbindelse til [MailChimp-indholdspakken](https://app.powerbi.com/getdata/services/mailchimp) til Power BI.

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
    ![](media/service-connect-to-mailchimp/pbi_getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-mailchimp/pbi_getservices.png)
3. Vælg **MailChimp** \> **Hent**.
   
   ![](media/service-connect-to-mailchimp/mailchimp.png)
4. Som Godkendelsesmetode skal du vælge **oAuth2** \> **Log på**.
   
    Når du bliver spurgt, skal du angive dine legitimationsoplysninger til MailChimp og følge godkendelsesprocessen.
   
    Første gang, du opretter forbindelse, vil du blive bedt om at give Power BI skrivebeskyttet adgang til din konto. Vælg **Tillad** for at starte importprocessen, som kan tage et par minutter, afhængigt af mængden af data på din konto.
   
    ![](media/service-connect-to-mailchimp/allow.png)
5. Efter import af data i Power BI får du vist et nyt dashboard og datasæt samt en ny rapport i venstre navigationsrude. Dette er standarddashboardet, som Power BI oprettede for at vise dine data. Du kan ændre dette dashboard for at vise dine data, som du ønsker.
   
   ![](media/service-connect-to-mailchimp/pbi_mailchimpnewdash.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](power-bi-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](service-dashboard-tiles.md) for at åbne den underliggende rapport.
* Dit datasæt vil være planlagt til daglig opdatering. Du kan dog ændre tidsplanen for opdatering eller forsøge at opdatere efter behov ved hjælp af **Opdater nu**

## <a name="next-steps"></a>Næste trin
[Hvad er Power BI?](power-bi-overview.md)

[Power BI – Grundlæggende begreber](service-basic-concepts.md)

