---
title: API til eksport af Power BI-rapporter
description: Få mere at vide om, hvordan du eksporterer en integreret Power BI-rapport
author: KesemSharabi
ms.author: kesharab
ms.topic: how-to
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 07/13/2020
ms.openlocfilehash: 8e3ca6d9615a348fec928f13a561fbb97e719d6a
ms.sourcegitcommit: b60063c49ac39f8b28c448908ecbb44b54326335
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/12/2020
ms.locfileid: "88160366"
---
# <a name="export-power-bi-report-to-file-preview"></a>Eksportér Power BI-rapport til fil (prøveversion)

`exportToFile`-API'en muliggør eksport af en Power BI-rapport ved hjælp af et REST-kald. Følgende filformater understøttes:
* **PPTX** (PowerPoint)
* **PDF**
* **PNG**
    * Når du eksporterer til en PNG, komprimeres en rapport med flere sider til en zip-fil
    * Hver fil i zip-filen repræsenterer en rapportside
    * Sidenavnene er de samme som returværdierne for API'erne [Hent sider](https://docs.microsoft.com/rest/api/power-bi/reports/getpages) eller [Hent sider i gruppe](https://docs.microsoft.com/rest/api/power-bi/reports/getpagesingroup)

## <a name="usage-examples"></a>Eksempler på brug

Du kan bruge eksportfunktionen på flere forskellige måder. Her er nogle eksempler:

* **Knappen Send til udskriv** – I dit program kan du oprette en knap, der udløser et eksportjob, når der klikkes på den. Jobbet kan eksportere den viste rapport som en PDF eller en PPTX, og når den er fuldført, kan brugeren modtage filen som et download. Ved hjælp af bogmærker kan du eksportere rapporten i en bestemt tilstand, herunder konfigurerede filtre, udsnit og yderligere indstillinger. Da API'en er asynkron, kan det tage et stykke tid, før filen er tilgængelig.

* **Vedhæftet fil i mail** – send en automatiseret mail i angivne intervaller med en vedhæftet PDF-rapport. Dette scenarie kan være nyttigt, hvis du vil automatisere afsendelse af en ugentlig rapport til ledere.

## <a name="using-the-api"></a>Brug af API'en

Før du bruger API'en, skal du bekræfte, at følgende [lejerindstillinger for administratoren](../../admin/service-admin-portal.md#tenant-settings) er aktiveret:
* **Eksportér rapporter som PowerPoint-præsentationer eller PDF-dokumenter** – Aktiveret som standard.
* **Eksportér rapporter som billedfiler** – kræves kun til *PNG* og er deaktiveret som standard.

API'en er asynkron. Når API'en [exportToFile](https://docs.microsoft.com/rest/api/power-bi/reports/exporttofile) kaldes, udløses et eksportjob. Efter et eksportjob er udløst, kan du bruge [polling](https://docs.microsoft.com/rest/api/power-bi/reports/getexporttofilestatus) til at spore jobbet, indtil det er fuldført.

Under polling returnerer API'en et tal, der repræsenterer den mængde arbejde, der er fuldført. Arbejdet i hvert eksportjob beregnes på baggrund af det antal sider, rapporten indeholder. Alle sider har samme vægt. Hvis du f.eks. eksporterer en rapport med 10 sider, og polling returnerer 70, betyder det, at API'en har behandlet 7 ud af de 10 sider i eksportjobbet.

Når eksporten er fuldført, returnerer API-kaldet for polling en [URL-adresse til Power BI](https://docs.microsoft.com/rest/api/power-bi/reports/getfileofexporttofile), så filen kan hentes. URL-adressen er tilgængelig i 24 timer.

## <a name="supported-features"></a>Understøttede funktioner

### <a name="selecting-which-pages-to-print"></a>Valg af, hvilke sider der skal udskrives

Angiv de sider, du vil udskrive i henhold til returværdierne [Hent sider](https://docs.microsoft.com/rest/api/power-bi/reports/getpages) eller [Hent sider i gruppe](https://docs.microsoft.com/rest/api/power-bi/reports/getpagesingroup). Du kan også angive rækkefølgen af de sider, du vil eksportere.

### <a name="bookmarks"></a>Bogmærker

 Du kan bruge `exportToFile`-API'en til programmeringsmæssigt at eksportere en rapport i en bestemt tilstand, efter du har anvendt filtre på den. Det gør du ved hjælp af egenskaber for [bogmærker](../../consumer/end-user-bookmarks.md). Hvis du vil eksportere en rapport ved hjælp af bogmærker, skal du bruge [JavaScript-API'en til bogmærker](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bookmarks).

 Du kan f.eks. bruge bogmærkets `capturedBookmark.state`-metode til at hente de ændringer, som en bestemt bruger har foretaget i en rapport, og derefter eksportere den i dens nuværende tilstand.

[Personlige bogmærker](../../consumer/end-user-bookmarks.md#personal-bookmarks) og [vedvarende filtre](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) understøttes ikke.

### <a name="authentication"></a>Godkendelse

Du kan godkende ved hjælp af en bruger (eller masterbruger) eller en [tjenesteprincipal](embed-service-principal.md).

### <a name="row-level-security-rls"></a>Sikkerhed på rækkeniveau

Med [sikkerhed på rækkeniveau](embedded-row-level-security.md) kan du eksportere en rapport, der viser data, som kun er synlige for bestemte brugere. Hvis du f.eks. eksporterer en salgsrapport, der er defineret med områdebestemte roller, kan du filtrere rapporten programmeringsmæssigt, så det kun er et bestemt område, der vises.

Hvis du vil eksportere ved hjælp af sikkerhed på rækkeniveau, skal du have følgende tilladelser:
* Tilladelser til at skrive og dele data igen for det datasæt, som rapporten er knyttet til
* Hvis rapporten findes i et v1-arbejdsområde, skal du være administrator af arbejdsområdet
* Hvis rapporten findes i et v2-arbejdsområde, skal du være medlem eller administrator af arbejdsområdet

### <a name="data-protection"></a>Databeskyttelse

PDF- og PPTX-formaterne understøtter [følsomhedsmærkater](../../admin/service-security-sensitivity-label-overview.md). Hvis du eksporterer en rapport med et følsomhedsmærkat til en PDF eller en PPTX, vises rapporten med dens følsomhedsmærkater i den eksporterede fil.

En rapport med et følsomhedsmærkat kan ikke eksporteres til en PDF- eller PPTX-fil ved hjælp af en [tjenesteprincipal](embed-service-principal.md).

### <a name="localization"></a>Lokalisering

Når du bruger `exportToFile`-API'en, kan du overføre din foretrukne landestandard. Indstillingerne for lokalisering påvirker den måde, rapporten vises på, f.eks. ved at ændre formatering i henhold til den valgte landestandard.

## <a name="concurrent-requests"></a>Samtidige anmodninger

`exportToFile` understøtter samtidige anmodninger om eksportjob. I nedenstående tabel vises antallet af job, du kan køre samtidigt, afhængigt af hvilken SKU din rapport er placeret på. Samtidige anmodninger refererer til rapportsider. Hvis der f.eks. er 20 sider i én eksportanmodning på en A6 SKU, behandles de samtidigt. Dette tager stort set den samme tid som at sende 20 eksportanmodninger med én side hver.

Et job, der overskrider sit antal af samtidige anmodninger, afsluttes ikke. Hvis du f.eks. eksporterer tre sider i en A1 SKU, udføres det første job, og de sidste to venter på de næste to udførelsescyklusser.

|Azure SKU  |Office SKU  |Maksimalt antal samtidige rapportsider  |
|-----------|------------|-----------|
|A1         |EM1         |1          |
|A2         |EM2         |2          |
|A3         |EM3         |3          |
|A4         |P1          |6          |
|A5         |P2          |12         |
|A6         |P3          |24         |

## <a name="limitations"></a>Begrænsninger

* Den rapport, du eksporterer, skal være placeret i en Premium- eller Embedded-kapacitet.
* Datasættet for den rapport, du eksporterer, skal være placeret i en Premium- eller Embedded-kapacitet.
* I forbindelse med en offentlig prøveversion er antallet af Power BI-rapportsider, der kan eksporteres pr. time, begrænset til 50 pr. kapacitet.
* Eksporterede rapporter må ikke overstige en filstørrelse på 250 MB.
* Følsomhedsmærkater understøttes ikke, når du eksporterer til PNG.
* Det antal sider, der kan inkluderes i en eksporteret rapport, er 50. Hvis rapporten indeholder flere sider, returnerer API'en en fejl, og eksportjobbet annulleres.
* [Personlige bogmærker](../../consumer/end-user-bookmarks.md#personal-bookmarks) og [vedvarende filtre](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) understøttes ikke.
* De Power BI-visualiseringer, der er angivet nedenfor, understøttes ikke. Når der eksporteres en rapport, som indeholder disse visualiseringer, bliver de dele af rapporten, der indeholder disse visualiseringer, ikke gengivet, og der vises et fejlsymbol.
    * Ikke-certificerede Power BI-visualiseringer
    * R-visualiseringer
    * PowerApps
    * Python-visualiseringer
    * Visio

## <a name="code-examples"></a>Kodeeksempler

Når du opretter et eksportjob, er der tre trin, du skal følge:

1. [Afsendelse af en eksportanmodning.](#step-1---sending-an-export-request)
2. [Polling](#step-2---polling).
3. [Hentning af filen](#step-3---getting-the-file).
4. [Brug af filstream](#step-4---using-the-file-stream).

Dette afsnit indeholder eksempler på hvert trin.

### <a name="step-1---sending-an-export-request"></a>Trin 1 – Afsendelse af en eksportanmodning

Det første trin er at sende en eksportanmodning. I dette eksempel sendes der en eksportanmodning for en bestemt side.

```csharp
private async Task<string> PostExportRequest(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    IList<string> pageNames = null /* Get the page names from the GetPages REST API */)
{
    var powerBIReportExportConfiguration = new PowerBIReportExportConfiguration
    {
        Settings = new ExportReportSettings
        {
            Locale = "en-us",
        },
        // Note that page names differ from the page display names
        // To get the page names use the GetPages REST API
        Pages = pageNames?.Select(pn => new ExportReportPage(Name = pn)).ToList(),
    };

    var exportRequest = new ExportReportRequest
    {
        Format = format,
        PowerBIReportConfiguration = powerBIReportExportConfiguration,
    };

    // The 'Client' object is an instance of the Power BI .NET SDK
    var export = await Client.Reports.ExportToFileInGroupAsync(groupId, reportId, exportRequest);

    // Save the export ID, you'll need it for polling and getting the exported file
    return export.Id;
}
```

### <a name="step-2---polling"></a>Trin 2 – Polling

Når du har sendt en eksportanmodning, kan du bruge polling til at identificere, hvornår den eksportfil, du venter på, er klar.

```csharp
private async Task<HttpOperationResponse<Export>> PollExportRequest(
    Guid reportId,
    Guid groupId,
    string exportId /* Get from the PostExportRequest response */,
    int timeOutInMinutes,
    CancellationToken token)
{
    HttpOperationResponse<Export> httpMessage = null;
    Export exportStatus = null;
    DateTime startTime = DateTime.UtcNow;
    const int c_secToMillisec = 1000;
    do
    {
        if (DateTime.UtcNow.Subtract(startTime).TotalMinutes > timeOutInMinutes || token.IsCancellationRequested)
        {
            // Error handling for timeout and cancellations 
            return null;
        }

        // The 'Client' object is an instance of the Power BI .NET SDK
        httpMessage = await Client.Reports.GetExportToFileStatusInGroupWithHttpMessagesAsync(groupId, reportId, exportId);
        exportStatus = httpMessage.Body;

        // You can track the export progress using the PercentComplete that's part of the response
        SomeTextBox.Text = string.Format("{0} (Percent Complete : {1}%)", exportStatus.Status.ToString(), exportStatus.PercentComplete);
        if (exportStatus.Status == ExportState.Running || exportStatus.Status == ExportState.NotStarted)
        {
            // The recommended waiting time between polling requests can be found in the RetryAfter header
            // Note that this header is not always populated
            var retryAfter = httpMessage.Response.Headers.RetryAfter;
            var retryAfterInSec = retryAfter.Delta.Value.Seconds;
            await Task.Delay(retryAfterInSec * c_secToMillisec);
        }
    }
    // While not in a terminal state, keep polling
    while (exportStatus.Status != ExportState.Succeeded && exportStatus.Status != ExportState.Failed);

    return httpMessage;
}
```

### <a name="step-3---getting-the-file"></a>Trin 3 – Hentning af filen

Når polling returnerer en URL-adresse, kan du bruge dette eksempel til at få den modtagne fil.

```csharp
private async Task<ExportedFile> GetExportedFile(
    Guid reportId,
    Guid groupId,
    Export export /* Get from the PollExportRequest response */)
{
    if (export.Status == ExportState.Succeeded)
    {
        // The 'Client' object is an instance of the Power BI .NET SDK
        var fileStream = await Client.Reports.GetFileOfExportToFileAsync(groupId, reportId, export.Id);
        return new ExportedFile
        {
            FileStream = fileStream,
            FileSuffix = export.ResourceFileExtension,
        };
    }
    return null;
}

public class ExportedFile
{
    public Stream FileStream;
    public string FileSuffix;
}
```

### <a name="step-4---using-the-file-stream"></a>Trin 4 – Brug af filstreamen

Når du har filstreamen, kan du håndtere den på den måde, der passer bedst til dine behov. Du kan f.eks. sende en mail til den eller bruge den til at downloade de eksporterede rapporter.

### <a name="end-to-end-example"></a>Komplet eksempel

Dette er et komplet eksempel på eksport af en rapport. Dette eksempel omfatter følgende stadier:
1. [Afsendelse af eksportanmodningen](#step-1---sending-an-export-request).
2. [Polling](#step-2---polling).
3. [Hentning af filen](#step-3---getting-the-file).

```csharp
private async Task<ExportedFile> ExportPowerBIReport(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    int pollingtimeOutInMinutes,
    CancellationToken token,
    IList<string> pageNames = null  /* Get the page names from the GetPages REST API */)
{
    const int c_maxNumberOfRetries = 3; /* Can be set to any desired number */
    const int c_secToMillisec = 1000;
    try
    {
        Export export = null;
        int retryAttempt = 1;
        do
        {
            var exportId = await PostExportRequest(reportId, groupId, format, pageNames);
            var httpMessage = await PollExportRequest(reportId, groupId, exportId, pollingtimeOutInMinutes, token);
            export = httpMessage.Body;
            if (export == null)
            {
                // Error, failure in exporting the report
                return null;
            }
            if (export.Status == ExportState.Failed)
            {
                // Some failure cases indicate that the system is currently busy. The entire export operation can be retried after a certain delay
                // In such cases the recommended waiting time before retrying the entire export operation can be found in the RetryAfter header
                var retryAfter = httpMessage.Response.Headers.RetryAfter;
                if(retryAfter == null)
                {
                    // Failed state with no RetryAfter header indicates that the export failed permanently
                    return null;
                }

                var retryAfterInSec = retryAfter.Delta.Value.Seconds;
                await Task.Delay(retryAfterInSec * c_secToMillisec);
            }
        }
        while (export.Status != ExportState.Succeeded && retryAttempt++ < c_maxNumberOfRetries);

        if (export.Status != ExportState.Succeeded)
        {
            // Error, failure in exporting the report
            return null;
        }

        var exportedFile = await GetExportedFile(reportId, groupId, export);

        // Now you have the exported file stream ready to be used according to your specific needs
        // For example, saving the file can be done as follows:
        /*
            var pathOnDisk = @"C:\temp\" + export.ReportName + exportedFile.FileSuffix;

            using (var fileStream = File.Create(pathOnDisk))
            {
                exportedFile.FileStream.CopyTo(fileStream);
            }
        */

        return exportedFile;
    }
    catch
    {
        // Error handling
        throw;
    }
}
```

## <a name="next-steps"></a>Næste trin

Gennemse, hvordan du integrerer indhold for dine kunder og din organisation:

> [!div class="nextstepaction"]
>[Eksportér den sideinddelte rapport til fil](export-paginated-report.md)

> [!div class="nextstepaction"]
>[Integrer indhold for dine kunder](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Integrer til din organisation](embed-sample-for-your-organization.md)