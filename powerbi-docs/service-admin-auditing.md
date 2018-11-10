---
title: Brug af overvågning i din organisation
description: Få mere at vide om, hvordan du kan bruge overvågning med Power BI til at overvåge og undersøge udførte handlinger. Du kan bruge Security & Compliance Center eller PowerShell.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 294fb3a0142908ce0ab068e075ce39f950a0b124
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973344"
---
# <a name="using-auditing-within-your-organization"></a>Brug af overvågning i din organisation

Det kan være vigtigt at vide, hvem der udfører en bestemt handling på et element i din Power BI-lejer, for at hjælpe din organisation med at opfylde sine krav, for eksempel efterleve lovmæssig kravoverholdelse og datastyring. Brug overvågning i Power BI, hvis du vil overvåge brugernes handlinger, f.eks. "Vis rapport" og "Vis dashboard". Du kan ikke bruge overvågning til at overvåge tilladelser.

Du arbejder med overvågning i Office 365 Security and Compliance Center eller ved hjælp af PowerShell. Vi behandler begge dele i denne artikel. Du kan filtrere overvågningsdataene efter datointerval, bruger, dashboard, rapport, datasæt og aktivitetstype. Du kan også downloade aktiviteterne i en CSV-fil (fil med kommaseparerede værdier), der kan analyseres offline.

## <a name="requirements"></a>Krav

Du skal opfylde disse krav for at få adgang til overvågningslogger:

- Du skal have en Exchange Online-licens (inkluderet i Office 365 Enterprise E3- og E5- abonnementer) for at få adgang til sektionen overvågning i Office 365 Security & Compliance Center.

- Du skal enten være global administrator eller have en Exchange-administratorrolle, der giver adgang til overvågningsloggen. Exchange-administratorroller styres via Exchange Administration. Du kan finde flere oplysninger under [Tilladelser i Exchange Online](/exchange/permissions-exo/permissions-exo/).

- Hvis du har adgang til overvågningsloggen, men du ikke er global administrator eller administrator af Power BI-tjenesten, vil du ikke have adgang til portalen Power BI Administration. I dette tilfælde skal du have en direkte forbindelse til [Office 365 Security & Compliance Center](https://sip.protection.office.com/#/unifiedauditlog).

- Hvis du vil have vist overvågningslogs for Power BI i din lejer, skal du have mindst én Exchange-postkasselicens i din lejer.

## <a name="accessing-your-audit-logs"></a>Adgang til dine overvågningslogge

For at få adgang til logfiler skal du først sørge for, at log er aktiveret i Power BI. Du kan finde flere oplysninger i [Overvågningslogs](service-admin-portal.md#audit-logs) i dokumentationen til administrationsportalen. Der kan være op til 48 timers forsinkelse, fra at du aktiverer overvågning, til at du får vist data i overvågningsloggen. Hvis du ikke får vist data med det samme, skal du tjekke overvågningsloggene senere. Der kan være en lignende forsinkelse mellem at få tilladelse til at få vist overvågningslogge og til at kunne åbne logfilerne.

Power BI-overvågningslogs er tilgængelige direkte via [Office 365 Security & Compliance Center](https://sip.protection.office.com/#/unifiedauditlog). Der er også et link fra Power BI-administrationsportalen:

1. Vælg **tandhjulsikonet** øverst til højre i Power BI, og vælg derefter **Administrationsportal**.

   ![Administrationsportal](media/service-admin-auditing/powerbi-admin.png)

1. Vælg **Overvågningslogger**.

1. Vælg **Gå til O365 Administration**.

   ![Gå til O365 Administration](media/service-admin-auditing/audit-log-o365-admin-center.png)

Hvis du vil give konti, der ikke er administratorkonti, adgang til overvågningslogfilen, skal du tildele tilladelser i Exchange Online-administration. Du kan for eksempel tildele en bruger til en eksisterende rollegruppe, f.eks. administration af organisation, eller du kan oprette en ny rollegruppe med rollen Overvågningslogger. Du kan finde flere oplysninger under [Tilladelser i Exchange Online](/exchange/permissions-exo/permissions-exo/).

## <a name="search-only-power-bi-activities"></a>Søg kun i Power BI-aktiviteter

Begræns resultaterne til aktiviteter, der kun er for Power BI, ved at følge disse trin. Se [listen over aktiviteter, der overvåges af Power BI](#list-of-activities-audited-by-power-bi) senere i denne artikel for at få et overblik.

1. På siden **Søgning i overvågningslog** under **Søg** skal du vælge rullelisten for **Aktiviteter**.

2. Vælg **Power BI-aktiviteter**.

   ![Søgning i overvågningslogfil](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. Vælg et vilkårligt sted uden for markeringsfeltet for at lukke det.

Dine søgninger filtreres nu kun på aktiviteter i Power BI.

## <a name="search-the-audit-logs-by-date"></a>Søg i overvågningslogfilerne efter dato

Du kan søge i logfilerne efter datointerval ved hjælp af felterne **Startdato** og **Slutdato**. De sidste syv dage er valgt som standard. Datoen og klokkeslættet vises i UTC-format (Coordinated Universal Time). Det maksimale datointerval, du kan angive, er 90 dage. 

Der vises en fejlmeddelelse, hvis det angivne datointerval er større end 90 dage. Hvis du bruger det maksimale datointerval på 90 dage, skal du vælge det aktuelle klokkeslæt som **Startdato**. Ellers får du vist en fejlmeddelelse om, at startdatoen ligger tidligere end slutdatoen. Hvis du har slået overvågning til inden for de sidste 90 dage, kan datointervallet ikke starte før den dato, hvor overvågning blev slået til.

![](media/service-admin-auditing/search-audit-log-by-date.png)

## <a name="search-the-audit-logs-by-users"></a>Søg i overvågningslogfilerne efter brugere

Du kan søge efter overvågningslogposter for aktiviteter, der er udført af bestemte brugere. Det gør du ved at angive et eller flere brugernavne i feltet **Brugere**. Brugernavnet ligner en e-mailadresse. Det er den konto, som brugerne logger på Power BI med. Lad dette felt være tomt for at returnere poster for alle brugere (og tjenestekonti) i din organisation.

![Søg efter dato](media/service-admin-auditing/search-audit-log-by-user.png)

## <a name="view-search-results"></a>Få vist søgeresultaterne

Når du har valgt **Søg**, indlæses søgeresultaterne, og efter et øjeblik vises de under **Resultater**. Når du er færdig med søgningen, vises antallet af fundne resultater. Der kan maksimalt vises 1000 hændelser. Hvis mere end 1000 hændelser opfylder søgekriterierne, vises de 1000 seneste hændelser.

### <a name="view-the-main-results"></a>Få vist de vigtigste resultater

Området **Resultater** indeholder følgende oplysninger om hver hændelse, der returneres af søgningen. Vælg en kolonneoverskrift under **Resultater** for at sortere resultaterne.

| **Kolonne** | **Definition** |
| --- | --- |
| Dato |Den dato og det klokkeslæt (i UTC-format), da hændelsen fandt sted. |
| IP-adresse |IP-adressen på den enhed, der blev brugt, da aktiviteten blev logført. IP-adressen vises i enten et IPv4- eller IPv6-adresseformat. |
| Bruger |Brugeren (eller tjenestekontoen), som udførte den handling, der udløste hændelsen. |
| Aktivitet |Den aktivitet, der blev udført af brugeren. Denne værdi svarer til de aktiviteter, som du har valgt på rullelisten **Aktiviteter**. For en hændelse fra Exchange-administratorens overvågningslogfil er værdien i denne kolonne en Exchange-cmdlet . |
| Element |Det objekt, der blev oprettet eller ændret som følge af den tilsvarende aktivitet. For eksempel den fil, der blev vist eller ændret, eller den brugerkonto, som blev opdateret. Ikke alle aktiviteter har en værdi i denne kolonne. |
| Detaljer |Yderligere oplysninger om en aktivitet. Igen er det ikke alle aktiviteter, der har en værdi. |

### <a name="view-the-details-for-an-event"></a>Få vist oplysninger om en hændelse

Du kan få vist flere oplysninger om en hændelse ved at klikke på hændelsesposten på listen over søgeresultater. Siden **Detaljer**, som indeholder de detaljerede egenskaber fra hændelsesposten, vises. De egenskaber, der skal vises, afhænger af den Office 365-tjeneste, hændelsen finder sted i. 

Vælg **Flere oplysninger** for at få vist disse detaljer. Alle poster i Power BI har en værdi på 20 for egenskaben RecordType. Du kan finde oplysninger om andre egenskaber i [Detaljerede egenskaber i overvågningsloggen](/office365/securitycompliance/detailed-properties-in-the-office-365-audit-log/).

   ![Overvågningsoplysninger](media/service-admin-auditing/audit-details.png)

## <a name="export-search-results"></a>Eksporter søgeresultaterne

Følg disse trin for at eksportere Power BI-overvågningslogfilen til en csv-fil.

1. Vælg **Eksportér resultater**.

1. Vælg enten **Gem indlæste resultater** eller **Download alle resultater**.

    ![Eksportér resultater](media/service-admin-auditing/export-auditing-results.png)

## <a name="use-powershell-to-search-audit-logs"></a>Brug PowerShell til at søge efter overvågningslogs

Du kan også bruge PowerShell til at få adgang til overvågningslogfilerne baseret på dit logon. Følgende eksempel viser, hvordan du bruger kommandoen [Search-UnifiedAuditLog](/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog?view=exchange-ps/) til at trække Power BI-overvågningslogposter.

Hvis du vil bruge kommandoen [New-PSSession](/powershell/module/microsoft.powershell.core/new-pssession/), skal din konto have en Exchange Online-licens tildelt, og du skal have adgang til overvågningslogfilen for din lejer. Du kan finde flere oplysninger om at oprette forbindelse til Exchange Online under [Opret forbindelse til Exchange Online PowerShell](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell/).

```powershell
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2018 -EndDate 9/15/2018 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

Hvis du vil se et andet eksempel på brug af PowerShell med overvågningslogs, skal du se [Brug af Power BI-overvågningslog og PowerShell til at tildele Power BI Pro-licenser](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/).

## <a name="activities-audited-by-power-bi"></a>Aktiviteter, der overvåges af Power BI

Følgende aktiviteter overvåges af Power BI.

* AddDatasourceToGateway
* AddGroupMembers
* AnalyzedByExternalApplication
* AnalyzeInExcel
* AttachDataflowStorageAccount
* BindToGateway
* ChangeCapacityState
* ChangeGatewayAdministrators
* ChangeGatewayDatasourceUsers
* CreateApp
* CreateDashboard
* CreateDataflow
* CreateDataset
* CreateEmailSubscription
* CreateFolder
* CreateGateway
* CreateGroup
* CreateOrgApp
* CreateReport
* DeleteComment
* DeleteDashboard
* DeleteDataflow
* DeleteDataset
* DeleteEmailSubscription
* DeleteFolder
* DeleteGateway
* DeleteGroup
* DeleteGroupMembers
* DeleteOrgApp
* DeleteReport
* DownloadReport
* EditDataset
* EditReport
* ExportDataflow
* ExportReport
* ExportTile
* GenerateDataflowSasToken
* GenerateEmbedToken
* GetDatasources
* Importér
* InstallApp
* MigrateWorkspaceIntoCapacity
* OptInForProTrial
* PostComment
* PrintDashboard
* PrintReport
* PublishToWebReport
* RefreshDataset
* RemoveDatasourceFromGateway
* RemoveWorkspacesFromCapacity
* RenameDashboard
* SetAllConnections
* SetScheduledRefresh
* SetScheduledRefreshOnDataflow
* ShareDashboard
* ShareReport
* TakeOverDataset
* TakeOverDatasource
* UnpublishApp
* UpdateApp
* UpdateCapacityAdmins
* UpdateCapacityDisplayName
* UpdateCapacityResourceGovernanceSettings
* UpdateCapacityUsersAssignment
* UpdatedAdminFeatureSwitch
* UpdateDataflow
* UpdateDatasetParameters
* UpdateDatasourceCredentials
* UpdateDatasources
* UpdateEmailSubscription
* UpdateFolder
* UpdateFolderAccess
* ViewDashboard
* ViewDataflow
* ViewReport
* ViewTile
* ViewUsageMetrics

## <a name="next-steps"></a>Næste trin

[Hvad er Power BI-administration?](service-admin-administering-power-bi-in-your-organization.md)  

[Power BI-administrationsportal](service-admin-portal.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
