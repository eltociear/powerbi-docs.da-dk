---
title: Brug af overvågning i din organisation
description: Få mere at vide om, hvordan du kan bruge overvågning med Power BI til at overvåge og undersøge udførte handlinger. Du kan bruge Security & Compliance Center eller PowerShell.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 559ff45974274420e2545228720000359d5fe971
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906861"
---
# <a name="use-auditing-within-your-organization"></a>Brug af overvågning i din organisation

At vide, hvem der udfører en bestemt handling på et element i din Power BI kan lejer være vigtigt at hjælpe din organisation, opfylde sine krav, som efterleve LOVMÆSSIG kravoverholdelse og datastyring. Brug Power BI, overvågning, hvis du vil overvåge handlinger, der udføres af brugere, f.eks. "Vis rapport" og "Vis Dashboard". Du kan ikke bruge overvågning til at overvåge tilladelser.

Du arbejder med overvågning i Office 365 Security and Compliance Center eller ved hjælp af PowerShell. Overvågning er afhængig af funktionaliteten i Exchange Online, som er klargjort automatisk til at understøtte Power BI.

Du kan filtrere overvågningsdataene efter datointerval, bruger, dashboard, rapport, datasæt og aktivitetstype. Du kan også downloade aktiviteterne i en csv (kommasepareret værdi)-fil, der kan analyseres offline.

## <a name="requirements"></a>Krav

Du skal opfylde disse krav for at få adgang til overvågningslogger:

* Du skal enten være global administrator eller tildelt rollen Audit Logs eller View-Only Audit Logs i Exchange Online til at få adgang til overvågningsloggen. Som standard grupperne administration af overholdelse af angivne standarder og administration af organisation rolle, der følger med disse roller, der er tildelt på den **tilladelser** side i Exchange administration.

    Hvis du vil give adgang til overvågningsloggen bruger uden administrative konti, skal du tilføje brugeren som medlem af en af disse rollegrupper. Hvis du vil gøre det en anden måde, du kan oprette en brugerdefineret rollegruppe i Exchange administration, tildele rollen overvågningslogger eller View-Only overvågningslogge til denne gruppe og derefter tilføje den ikke-administratorkonto til den nye rollegruppe. Du kan finde flere oplysninger under [Administrer rollegrupper i Exchange Online](/Exchange/permissions-exo/role-groups).

    Hvis du ikke kan få adgang til Exchange Administration via Microsoft 365 Administration, skal du gå til https://outlook.office365.com/ecp og logge på ved hjælp af dine legitimationsoplysninger.

* Hvis du har adgang til overvågningsloggen, men ikke er en global administrator eller administrator af Power BI-tjenesten, kan du ikke har adgang til Power BI-administrationsportalen. I dette tilfælde skal du bruge et direkte link til [Office 365 Security & Compliance Center](https://sip.protection.office.com/#/unifiedauditlog).

## <a name="access-your-audit-logs"></a>Få adgang til dine overvågningslogge

For at få adgang til logfiler, du først sørge for at aktivere logføring i Power BI. Du kan finde flere oplysninger i [Overvågningslogs](service-admin-portal.md#audit-logs) i dokumentationen til administrationsportalen. Der kan være op til 48 timer forsinkelse mellem det tidspunkt, hvor du aktiverer overvågning og hvornår du kan få vist overvågningsdataene. Hvis du ikke får vist data med det samme, skal du tjekke overvågningsloggene senere. Der kan være en lignende forsinkelse mellem at få tilladelse til at få vist overvågningslogge og til at kunne åbne logfilerne.

Power BI-overvågningslogs er tilgængelige direkte via [Office 365 Security & Compliance Center](https://sip.protection.office.com/#/unifiedauditlog). Der er også et link fra Power BI-administrationsportalen:

1. I Power BI, skal du vælge den **tandhjulsikonet** i øverste højre hjørne, vælg derefter **administrationsportalen**.

   ![Skærmbillede af menuen gear rullelisten med indstillingen Admin-portalen påpeges.](media/service-admin-auditing/powerbi-admin.png)

1. Vælg **Overvågningslogger**.

1. Vælg **Gå til O365 Administration**.

   ![Skærmbillede af administrationsportalen til audit logfører indstilling og farten til påpeges, indstillinger for Microsoft O365 Admin Center.](media/service-admin-auditing/audit-log-o365-admin-center.png)

## <a name="search-only-power-bi-activities"></a>Søg kun i Power BI-aktiviteter

Begræns resultaterne til aktiviteter, der kun er for Power BI, ved at følge disse trin. Se listen over [aktiviteter, der overvåges af Power BI](#activities-audited-by-power-bi) senere i denne artikel for at få et overblik.

1. På den **overvågningslogfil** siden under **Search**, skal du vælge rullelisten for **aktiviteter**.

2. Vælg **Power BI-aktiviteter**.

   ![Skærmbillede af Audit log search med Power BI-aktiviteter påpeges.](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. Vælg et vilkårligt sted uden for markeringsfeltet for at lukke det.

Dine søgninger Returner kun Power BI-aktiviteter.

## <a name="search-the-audit-logs-by-date"></a>Søg i overvågningslogfilerne efter dato

Du kan søge i logfilerne efter datointerval ved hjælp af felterne **Startdato** og **Slutdato**. Standardindstillingen er de seneste syv dage. Visningen præsenterer dato og klokkeslæt i Coordinated Universal Time (UTC)-format. Det maksimale datointerval, du kan angive, er 90 dage. 

Du får vist en fejlmeddelelse, hvis det angivne datointerval er større end 90 dage. Hvis du bruger det maksimale datointerval på 90 dage, skal du vælge det aktuelle klokkeslæt som **Startdato**. Ellers får du vist en fejlmeddelelse om, at startdatoen ligger tidligere end slutdatoen. Hvis du har slået overvågning til inden for de sidste 90 dage, kan datointervallet ikke starte før den dato, hvor overvågning blev slået til.

![Skærmbillede af Audit log search med startdato og slutdato for indstillinger påpeges.](media/service-admin-auditing/search-audit-log-by-date.png)

## <a name="search-the-audit-logs-by-users"></a>Søg i overvågningslogfilerne efter brugere

Du kan søge efter overvågningslogposter for aktiviteter, der er udført af bestemte brugere. Angiv en eller flere brugernavne i den **brugere** felt. Brugernavnet ligner en mailadresse. Det er den konto, som brugerne logger på Power BI. Lad dette felt være tomt for at returnere poster for alle brugere (og tjenestekonti) i din organisation.

![Søg efter brugere](media/service-admin-auditing/search-audit-log-by-user.png)

## <a name="view-search-results"></a>Få vist søgeresultaterne

Når du har valgt **Search**, indlæses søgeresultaterne. Efter et øjeblik, de vises **resultater**. Når du er færdig med søgningen, vises visningen af antallet af fundne resultater. **Overvågningslogfil** vises maksimalt 1000 hændelser. Hvis mere end 1000 hændelser opfylder søgekriterierne, viser appen de nyeste 1000 hændelser.

### <a name="view-the-main-results"></a>Få vist de vigtigste resultater

Den **resultater** område har følgende oplysninger for hver hændelse, der returneres af søgningen. Vælg en kolonneoverskrift under **Resultater** for at sortere resultaterne.

| **Kolonne** | **Definition** |
| --- | --- |
| Dato |Den dato og det klokkeslæt (i UTC-format), da hændelsen fandt sted. |
| IP-adresse |IP-adressen på den enhed, der bruges til den registrerede aktivitet. Appen Viser IP-adressen i enten et IPv4- eller IPv6-adresseformat. |
| Bruger |Brugeren (eller tjenestekontoen), som udførte den handling, der udløste hændelsen. |
| Aktivitet |Den aktivitet, der blev udført af brugeren. Denne værdi svarer til de aktiviteter, som du har valgt på rullelisten **Aktiviteter**. For en hændelse fra Exchange-administratorens overvågningslogfil er værdien i denne kolonne en Exchange-cmdlet . |
| Element |Objektet, der oprettes eller ændres på grund af den tilsvarende aktivitet. For eksempel viste eller ændrede filen, eller den opdaterede brugerkonto. Ikke alle aktiviteter har en værdi i denne kolonne. |
| Detaljer |Yderligere oplysninger om en aktivitet. Igen, ikke alle aktiviteter har en værdi. |

### <a name="view-the-details-for-an-event"></a>Få vist oplysninger om en hændelse

For at få vist flere detaljer om en hændelse, skal du vælge hændelsesposten på listen over søgeresultater. A **detaljer** vises en side, der indeholder de detaljerede egenskaber fra hændelsesposten. Den **detaljer** side viser egenskaberne afhængigt af den Office 365-tjeneste, hændelsen finder sted.

Vælg **Flere oplysninger** for at få vist disse detaljer. Alle poster i Power BI har en værdi på 20 for egenskaben RecordType. Du kan finde oplysninger om andre egenskaber i [Detaljerede egenskaber i overvågningsloggen](/office365/securitycompliance/detailed-properties-in-the-office-365-audit-log/).

   ![Skærmbillede af dialogboksen audit oplysninger med mulighed for flere oplysninger om påpeges.](media/service-admin-auditing/audit-details.png)

## <a name="export-search-results"></a>Eksporter søgeresultaterne

For at eksportere Power BI-overvågningslogfilen til en CSV-fil, skal du følge disse trin.

1. Vælg **Eksportér resultater**.

1. Vælg enten **Gem indlæste resultater** eller **Download alle resultater**.

    ![Skærmbillede af eksport resultater indstilling.](media/service-admin-auditing/export-auditing-results.png)

## <a name="use-powershell-to-search-audit-logs"></a>Brug PowerShell til at søge efter overvågningslogs

Du kan også bruge PowerShell til at få adgang til overvågningslogfilerne baseret på dit logon. I følgende eksempel kan du se, hvordan du opretter forbindelse til Exchange Online PowerShell og derefter bruger kommandoen [Search-UnifiedAuditLog](/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog?view=exchange-ps/) til at trække poster fra Power BI-overvågningsloggen. Hvis du vil køre scriptet skal en administrator skal tildele dig de nødvendige tilladelser, som beskrevet i den [krav](#requirements) afsnit.

```powershell
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2018 -EndDate 9/15/2018 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

Du kan finde flere oplysninger om at oprette forbindelse til Exchange Online under [Opret forbindelse til Exchange Online PowerShell](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell/). Hvis du vil se et andet eksempel på brug af PowerShell med overvågningslogs, skal du se [Brug af Power BI-overvågningslog og PowerShell til at tildele Power BI Pro-licenser](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/).

## <a name="activities-audited-by-power-bi"></a>Aktiviteter, der overvåges af Power BI

Følgende aktiviteter, der overvåges af Power BI:

| Brugervenligt navn                                     | Handlingsnavn                              | Noter                                  |
|---------------------------------------------------|---------------------------------------------|------------------------------------------|
| Datakilde er føjet til Power BI-gateway             | AddDatasourceToGateway                      |                                          |
| Adgang til Power BI-mapper er tilføjet                      | AddFolderAccess                             | Ikke anvendt i øjeblikket                       |
| Power BI-gruppemedlemmer er tilføjet                      | AddGroupMembers                             |                                          |
| Administratoren har knyttet dataflowlagerkontoen til lejer | AdminAttachedDataflowStorageAccountToTenant | Anvendes ikke i øjeblikket                       |
| Analyseret Power BI-datasæt                         | AnalyzedByExternalApplication               |                                          |
| Power BI-rapport er analyseret                          | AnalyzeInExcel                              |                                          |
| Bundne Power BI-datasæt til gateway                | BindToGateway                               |                                          |
| Kapacitetstilstand er ændret                            | ChangeCapacityState                         |                                          |
| Kapacitet for brugertildeling er ændret                  | UpdateCapacityUsersAssignment               |                                          |
| Power BI-datasætforbindelser er ændret              | SetAllConnections                           |                                          |
| Ændrede administratorer af Power BI-gateway                   | ChangeGatewayAdministrators                 |                                          |
| Ændrede brugere af datakilde fra Power BI-gateway        | ChangeGatewayDatasourceUsers                |                                          |
| Power BI organisationsindholdspakke er oprettet      | CreateOrgApp                                |                                          |
| Power BI-app er oprettet                              | CreateApp                                   |                                          |
| Power BI-dashboard er oprettet                        | CreateDashboard                             |                                          |
| Power BI-dataflow er oprettet                         | CreateDataflow                              |                                          |
| Power BI-datasæt er oprettet                          | CreateDataset                               |                                          |
| Power BI-mailabonnement er oprettet               | CreateEmailSubscription                     |                                          |
| Power BI-mappe er oprettet                           | CreateFolder                                |                                          |
| Oprettet Power BI-gateway                          | CreateGateway                               |                                          |
| Power BI-gruppe er oprettet                            | CreateGroup                                 |                                          |
| Power BI-rapport er oprettet                           | CreateReport                                |                                          |
| Dataflowet er overført til ekstern lagerkonto     | DataflowMigratedToExternalStorageAccount    | Ikke anvendt i øjeblikket                       |
| Dataflowtilladelser er tilføjet                        | DataflowPermissionsAdded                    | Ikke anvendt i øjeblikket                       |
| Dataflowtilladelser er fjernet                      | DataflowPermissionsRemoved                  | Ikke anvendt i øjeblikket                       |
| Power BI-organisationsindholdspakke er slettet      | DeleteOrgApp                                |                                          |
| Power BI-kommentar er slettet                          | DeleteComment                               |                                          |
| Power BI-dashboard er slettet                        | DeleteDashboard                             | Anvendes ikke i øjeblikket                       |
| Power BI-dataflow er slettet                         | DeleteDataflow                              | Anvendes ikke i øjeblikket                       |
| Power BI-datasæt er slettet                          | DeleteDataset                               |                                          |
| Power BI-mailabonnement er slettet               | DeleteEmailSubscription                     |                                          |
| Power BI-mappe er slettet                           | DeleteFolder                                |                                          |
| Adgang til Power BI-mapper er slettet                    | DeleteFolderAccess                          | Anvendes ikke i øjeblikket                       |
| Slettet Power BI-gateway                          | DeleteGateway                               |                                          |
| Power BI-gruppe er slettet                            | DeleteGroup                                 |                                          |
| Power BI-rapport er slettet                           | DeleteReport                                |                                          |
| Datakilder til Power BI-datasæt er fundet          | GetDatasources                              |                                          |
| Downloadet Power BI-rapport                        | DownloadReport                              |                                          |
| Power BI-certificeringstilladelse blev redigeret          | EditCertificationPermission                 | Ikke anvendt i øjeblikket                       |
| Power BI-dashboard er redigeret                         | EditDashboard                               | Anvendes ikke i øjeblikket                       |
| Power BI-datasæt er redigeret                           | EditDataset                                 |                                          |
| Egenskaber for Power BI-datasæt er redigeret                | EditDatasetProperties                       | Ikke anvendt i øjeblikket                       |
| Power BI-rapport er redigeret                            | EditReport                                  |                                          |
| Power BI-dataflow er eksporteret                        | ExportDataflow                              |                                          |
| Visualiseringsdata for Power BI-rapporten er eksporteret              | ExportReport                                |                                          |
| Power BI-feltdata er eksporteret                       | ExportTile                                  |                                          |
| Dataflowtilladelser blev ikke tilføjet                | FailedToAddDataflowPermissions              | Ikke anvendt i øjeblikket                       |
| Dataflowtilladelser blev ikke fjernet             | FailedToRemoveDataflowPermissions           | Anvendes ikke i øjeblikket                       |
| SAS-token til Power BI dataflow er oprettet             | GenerateDataflowSasToken                    |                                          |
| Integrationstoken til Power BI er oprettet                    | GenerateEmbedToken                          |                                          |
| Fil er importeret i Power BI                         | Importér                                      |                                          |
| Power BI-app er installeret                            | InstallApp                                  |                                          |
| Arbejdsområde er overført til en kapacitet                  | MigrateWorkspaceIntoCapacity                |                                          |
| Power BI-kommentar er postet                           | PostComment                                 |                                          |
| Power BI-dashboard er udskrevet                        | PrintDashboard                              |                                          |
| Power BI-rapportside er udskrevet                      | PrintReport                                 |                                          |
| Power BI-rapport er publiceret på internettet                  | PublishToWebReport                          |                                          |
| Power BI-dataflowhemmelighed er modtaget fra Key Vault  | ReceiveDataflowSecretFromKeyVault           | Anvendes ikke i øjeblikket                       |
| Datakilde fjernet fra Power BI-gateway         | RemoveDatasourceFromGateway                 |                                          |
| Power BI-gruppemedlemmer er fjernet                    | DeleteGroupMembers                          |                                          |
| Arbejdsområde er fjernet fra en kapacitet                 | RemoveWorkspacesFromCapacity                |                                          |
| Power BI-dashboard er omdøbt                        | RenameDashboard                             |                                          |
| Der er anmodet om opdatering af Power BI-dataflowet               | RequestDataflowRefresh                      | Anvendes ikke i øjeblikket                       |
| Der er anmodet om opdatering af Power BI-datasættet                | RefreshDataset                              |                                          |
| Power BI-arbejdsområder er hentet                     | GetWorkspaces                               |                                          |
| Angiv planlagt opdatering af Power BI-dataflow        | SetScheduledRefreshOnDataflow               |                                          |
| Angiv planlagt opdatering af Power BI-datasæt         | SetScheduledRefresh                         |                                          |
| Power BI-dashboard er delt                         | ShareDashboard                              |                                          |
| Power BI-rapport er delt                            | ShareReport                                 |                                          |
| Påbegyndt udvidet prøveperiode med Power BI                   | OptInForExtendedProTrial                    | Anvendes ikke i øjeblikket                       |
| Power BI-prøveperiode er startet                            | OptInForProTrial                            |                                          |
| Power BI-datakilde er overtaget                   | TakeOverDatasource                          |                                          |
| Power BI-datasæt er overtaget                        | TakeOverDataset                             |                                          |
| Publicering af Power BI-app er fjernet                          | UnpublishApp                                |                                          |
| Opdater indstillinger for ressourcestyring af kapacitet      | UpdateCapacityResourceGovernanceSettings    | Findes i øjeblikket ikke i Microsoft 365 Administration |
| Kapacitetsadministrator er opdateret                            | UpdateCapacityAdmins                        |                                          |
| Vist navn for kapacitet er opdateret                     | UpdateCapacityDisplayName                   |                                          |
| Power BI-indstillinger for organisation er opdateret          | UpdatedAdminFeatureSwitch                   |                                          |
| Power BI-appen er opdateret                              | UpdateApp                                   |                                          |
| Power BI-dataflowet er opdateret                         | UpdateDataflow                              |                                          |
| Datakilder til Power BI-datasæt er opdateret             | UpdateDatasources                           |                                          |
| Parametre for Power BI-datasæt er opdateret               | UpdateDatasetParameters                     |                                          |
| Power BI-mailabonnement er opdateret               | UpdateEmailSubscription                     |                                          |
| Power BI-mappe er opdateret                           | UpdateFolder                                |                                          |
| Adgang til Power BI-mappe er opdateret                    | UpdateFolderAccess                          |                                          |
| Legitimationsoplysninger for Power BI-gatewaydatakilde er opdateret  | UpdateDatasourceCredentials                 |                                          |
| Power BI-dashboard er vist                         | ViewDashboard                               |                                          |
| Power BI-dataflow er vist                          | ViewDataflow                                |                                          |
| Power BI-rapport er vist                            | ViewReport                                  |                                          |
| Power BI-felt er vist                              | ViewTile                                    |                                          |
| Power BI-forbrugsdata er vist                     | ViewUsageMetrics                            |                                          |
|                                                   |                                             |                                          |

## <a name="next-steps"></a>Næste trin

[Hvad er Power BI-administration?](service-admin-administering-power-bi-in-your-organization.md)  

[Power BI-administrationsportal](service-admin-portal.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](http://community.powerbi.com/)
