---
title: Opret forbindelse til Xero med Power BI
description: Xero til Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: d09936f2cce1d7835efdb82929d9e8eed2291163
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "61156255"
---
# <a name="connect-to-xero-with-power-bi"></a>Opret forbindelse til Xero med Power BI
Xero er en brugervenlig online regnskabssoftware, der er udviklet specielt til små virksomheder. Opret overbevisende visualiseringer baseret på din bogføring i Xero med denne Power BI-indholdspakke. Standarddashboardet indeholder mange metrikværdier for små virksomheder, f.eks. likviditet, indtægter i forhold til udgifter, avancetendens, debitordage og afkastningsgrad.

Opret forbindelse til [Xero-indholdspakken](https://app.powerbi.com/getdata/services/xero) til Power BI, eller få mere at vide om integration af [Xero og Power BI](https://help.xero.com/Power-BI).

## <a name="how-to-connect"></a>Sådan opretter du forbindelse
1. Vælg **Hent data** nederst i venstre navigationsrude.
   
   ![](media/service-connect-to-xero/getdata.png)
2. Vælg **Hent** i feltet **Tjenester**.
   
   ![](media/service-connect-to-xero/services.png)
3. Vælg **Xero** \>  **Hent**.
   
   ![](media/service-connect-to-xero/connect.png)
4. Angiv et kaldenavn for den organisation, der er knyttet til din Xero-konto. Du kan kalde den hvad som helst. Det er hovedsageligt for at hjælpe brugere med flere Xero-organisationer med at skelne dem fra hinanden. Se detaljer [nedenfor](#FindingParams).
   
   ![](media/service-connect-to-xero/params.png)
5. Som **Godkendelsesmetode** skal du vælge **OAuth**, og når du bliver bedt om det, skal du logge på din Xero-konto og vælge den organisation, du vil oprette forbindelse til. Når logonprocessen er fuldført, skal du vælge **Log på** for at starte indlæsningsprocessen.
   
    ![](media/service-connect-to-xero/creds.png)
   
    ![](media/service-connect-to-xero/creds2.png)
6. Efter godkendelsen starter importprocessen automatisk. Når processen er fuldført, vises et nyt dashboard samt en ny rapport og model i navigationsruden. Vælg dashboardet for at få vist de importerede data.
   
     ![](media/service-connect-to-xero/dashboard.png)

**Hvad nu?**

* Prøv [at stille et spørgsmål i feltet Spørgsmål og svar](consumer/end-user-q-and-a.md) øverst i dashboard'et
* [Rediger felterne](service-dashboard-edit-tile.md) i dashboard'et.
* [Vælg et felt](consumer/end-user-tiles.md) for at åbne den underliggende rapport.
* Selvom dit datasæt opdateres dagligt, kan du ændre tidsplanen for opdatering eller prøve at opdatere det efter behov ved hjælp af **Opdater nu**

## <a name="whats-included"></a>Det følgende er inkluderet
Indholdspakkens dashboard indeholder felter og metrikværdier, der dækker en lang række områder med tilsvarende rapporter, hvor man kan få flere oplysninger:  

| Område | Dashboardfelter | Rapport |
| --- | --- | --- |
| Penge |Dagligt Cashflow <br>Indbetal <br>Udbetal <br>Ultimosaldo efter konto <br>Closing balance today |Konti |
| Kunde |Faktureret salg <br>Faktureret salg efter kunde <br>Faktureret Salgsvækst tendens <br>Fakturaer forfalden <br>Udestående tilgodehavender <br>Forfalden tilgodehavender |Kunde <br>Lager |
| Leverandør |Køb faktureres <br>Faktureret indkøb efter leverandør <br>Køb faktureres væksttendens <br> Fakturaer forfaldsdato <br>Udestående skyldige beløb <br>Overskredne skyldige beløb |Leverandører <br>Lager |
| Lager |Månedlige salgsbeløb efter produkt |Lager |
| Resultatopgørelse |Månedlige resultatopgørelse <br>Overskud dette regnskabsår <br>Overskud denne måned <br>Mest populære udgift konti |Resultatopgørelse |
| Balancen |Samlede aktiver <br>Samlede passiver <br>Lighed |Balancen |
| Tilstand |Likviditetsgrad <br>Bruttoavance procentdel <br> Returner af samlede aktiver <br>Samlede passiver aktie forholdet mellem |Tilstand <br>Ordliste og tekniske noter |

Datasættet indeholder også følgende tabeller til at tilpasse dine rapporter og dashboards:  

* Adresser  
* Alerts  
* Bank-sætningen daglig saldo  
* Bank-sætninger.  
* Kontakter  
* Udgift krav  
* Linje Fakturaelementer  
* Fakturaer  
* Elementer  
* Slutningen af måneden  
* Organisation  
* Generelle kontooversigt  
* Xero-konti

## <a name="system-requirements"></a>Systemkrav
Følgende roller er påkrævet for at få adgang til Xero-indholdspakken: "Standard + Rapporter" eller "Rådgiver".

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Søgning efter parametre
Angiv et navn på din organisation, der skal spores i Power BI. Det giver dig mulighed for at oprette forbindelse til flere forskellige organisationer. Bemærk, at du ikke kan oprette forbindelse til den samme organisation flere gange, da det påvirker den planlagte opdatering.   

## <a name="troubleshooting"></a>Fejlfinding
* Xero-brugere skal have følgende roller for at få adgang til Xero-indholdspakken til Power BI: "Standard + Rapporter" eller "Rådgiver". Indholdspakken er afhængig af de brugerbaserede tilladelser til at få adgang til rapportdata via Power BI.  
* Hvis du får vist en fejl noget tid inde i indlæsningen, skal du kontrollere, hvor lang tid det tog, før du fik vist denne fejlmeddelelse. Bemærk, at det adgangstoken, der leveres af Xero, kun er gyldigt i 30 min. Så konti med flere data, end der kan ikke indlæses inden for dette tidsrum, mislykkes. Vi arbejder aktivt for at forbedre dette.
* Under indlæsningen er felterne på dashboardet i en generisk indlæsningstilstand. Dette ændres antageligt ikke, før indlæsningen er fuldført. Hvis du får en meddelelse om, at din indlæsning er fuldført, men felterne stadig er under indlæsning, skal du prøve at opdatere dashboardfelterne ved hjælp af den ... i øverste højre hjørne af dashboardet.
* Hvis din indholdspakke ikke opdateres, skal du kontrollere, om du har oprettet forbindelse til den samme organisation mere end én gang i Power BI. Xero tillader kun en enkelt aktiv forbindelse til en organisation, og du kan få vist en fejl, der angiver, at dine legitimationsoplysninger er ugyldige, hvis du opretter forbindelse til den samme mere end én gang.  
* Hvis du har problemer med at oprette forbindelse til Xero-indholdspakken til Power BI, f.eks. fejlmeddelelser eller meget langsom indlæsning, skal du først rydde din cache/cookies og genstarte browseren, og derefter skal du oprette forbindelse til Power BI igen.  

Hvis du oplever andre problemer, hvis problemet er vedvarende, skal du oprette en supportanmodning på http://support.powerbi.com.

## <a name="next-steps"></a>Næste trin
[Kom i gang med Power BI](service-get-started.md)

[Hent data i Power BI](service-get-data.md)

