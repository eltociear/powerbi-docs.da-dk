---
title: Opret et SSL-certifikat
description: Omgåelsesvejledning til at oprette certifikater manuelt for udviklerserver
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 13926603d7a5bfee987439180151d64ef5c456c2
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/03/2019
ms.locfileid: "70237261"
---
# <a name="create-an-ssl-certificate"></a>Opret et SSL-certifikat

I denne artikel beskrives det, hvordan du opretter et SSL-certifikat.

Kør følgende kommando for at generere certifikatet ved hjælp af PowerShell `New-SelfSignedCertificate` cmdlet'en på Windows 8 eller nyere:

```cmd
pbiviz --create-cert
```

Værktøjet kræver installation af OpenSSL til Windows 7. OpenSSL-værktøjet skal være tilgængeligt fra kommandolinjen.

Hvis du vil installere OpenSSL, skal du gå ind på webstedet [OpenSSL](https://www.openssl.org) eller [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries).



## <a name="create-a-certificate-mac-os-x"></a>Opret et certifikat (Mac OS X)

Normalt er funktionen OpenSSL tilgængelig i operativsystemet Linux eller Mac OS X.

Du kan også installere værktøjet ved at køre en af følgende kommandoer:
* Fra *Brew*-pakkestyring:

    ```cmd
    brew install openssl
    brew link openssl --force
    ```

* Ved hjælp af *MacPorts*:

    ```cmd
    sudo port install openssl
    ```

Når du har installeret OpenSSL-værktøjet til oprettelse af et nyt certifikat, skal du køre følgende kommando:

```cmd
pbiviz --create-cert
```

## <a name="create-a-certificate-linux"></a>Opret et certifikat (Linux)

Hvis OpenSSL-værktøjet ikke er tilgængeligt på dit Linux-operativsystem, kan du installere det ved hjælp af en af følgende kommandoer:

* Til *APT*-pakkestyring:

    ```cmd
    sudo apt-get install openssl
    ```

* Til *Yellowdog Updater*:

    ```cmd
    yum install openssl
    ```

* Til *Redhat Package Manager*:

    ```cmd
    rpm install openssl
    ```

Hvis OpenSSL-programmet allerede er tilgængeligt i operativsystemet, skal du oprette et nyt certifikat ved at køre følgende kommando:

```cmd
pbiviz --create-cert
```

Alternativt kan du få OpenSSL-programmet ved at gå til webstedet [OpenSSL](https://www.openssl.org) eller [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries).

## <a name="generate-the-certificate-manually"></a>Generér certifikatet manuelt

Du kan angive certifikater, som er genereret af et hvilket som helst værktøj.

Hvis OpenSSL-programmet allerede er installeret på systemet, skal du generere et nyt certifikat ved at køre følgende kommandoer:

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

Du kan som regel finde webserver-certifikater til PowerBI-værktøjer ved at køre en af følgende:

* For den globale forekomst af værktøjerne:

    ```cmd
    %appdata%\npm\node_modules\PowerBI-visuals-tools\certs
    ```

* For den lokale forekomst af værktøjerne:

    ```cmd
    <custom visual project root>\node_modules\PowerBI-visuals-tools\certs
    ```

Hvis du bruger PEM-formatet, skal du gemme certifikatfilen som *PowerBICustomVisualTest_public.crt* og gemme privateKey som *PowerBICustomVisualTest_public.key*.

Hvis du bruger PFX-formatet, skal du gemme certifikatfilen som *PowerBICustomVisualTest_public.pfx*.

Hvis PFX-certifikatfilen kræver et adgangsudtryk, skal du gøre følgende:
1. I konfigurationsfilen skal du angive:

    ```cmd
    \PowerBI-visuals-tools\config.json
    ```

1. I afsnittet `server` skal du angive adgangsudtrykket ved at erstatte pladsholderen "*DIT ADGANGSUDTRYK*":

    ```cmd
    "server":{
        "root":"webRoot",
        "assetsRoute":"/assets",
        "privateKey":"certs/PowerBICustomVisualTest_private.key",
        "certificate":"certs/PowerBICustomVisualTest_public.crt",
        "pfx":"certs/PowerBICustomVisualTest_public.pfx",
        "port":"8080",
        "passphrase":"YOUR PASSPHRASE"
    }
    ```
