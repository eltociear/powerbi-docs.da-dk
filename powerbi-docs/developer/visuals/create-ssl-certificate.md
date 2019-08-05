---
title: Oprettelse af SSL-certifikat
description: Omgåelsesvejledning til at oprette certifikater manuelt for udviklerserver
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 3287e8a7eb1c36c3f0d8a1fc24faa0442de2dddf
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425430"
---
# <a name="creating-ssl-certificate"></a>Oprettelse af SSL-certifikat

Kør følgende kommando for at generere certifikatet ved hjælp af PowerShell-cmdlet'en New-SelfSignedCertificate på Windows 8 eller nyere.

Værktøjet kræver installation af OpenSSL til **Windows** **7**. Værktøjet `openssll` skal være tilgængelig fra kommandolinjen.

Hvis du vil installere OpenSSL, skal du gå til [https://www.openssl.org](https://www.openssl.org) eller [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries)

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-mac-os-x"></a>Opret certifikat (Mac OS X)

OpenSSL-værktøjet er som regel tilgængelig på Linux- og Mac OS X-operativsystemerne.

Ellers kan du installere fra

*Brew*-pakkestyring

```cmd
brew install openssl
brew link openssl --force
```

eller ved hjælp af *MacPorts*

```cmd
sudo port install openssl
```

Efter installationen af OpenSSL til generering af et nyt certifikat skal du kalde:

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-linux"></a>Opret certifikat (Linux)

Hvis OpenSSL-værktøjet ikke er tilgængeligt på dit Linux-operativsystem, kan du installere det ved hjælp af følgende kommandoer.

Til *APT*-pakkestyring:

```cmd
sudo apt-get install openssl
```

Til *Yellowdog Updater*:

```cmd
yum install openssl
```

Til *Redhat Package Manager*:

```cmd
rpm install openssl
```

Hvis OpenSSL allerede er tilgængelig på dit operativsystem, skal du kalde

```cmd
pbiviz --create-cert
```

for at generere et nyt certifikat.

Eller hente det via [https://www.openssl.org](https://www.openssl.org) eller [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries)

## <a name="generate-certificate-manually"></a>Generér certifikat manuelt

Du kan angive certifikater, der er genereret af et hvilket som helst værktøj.

Hvis du har installeret OpenSSL på dit system, kan du køre følgende kommando for at generere et nyt certifikat

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

Normalt findes webservercertifikaterne PowerBI-visuals-tools under

```cmd
%appdata%\npm\node_modules\PowerBI-visuals-tools\certs
```

for den globale forekomst af værktøjerne

eller

```cmd
<custom visual project root>\node_modules\PowerBI-visuals-tools\certs
```

for den lokale forekomst af værktøjerne.

Du bør gemme certifikatfilen som `PowerBICustomVisualTest_public.cer` og PrivateKey som `PowerBICustomVisualTest_public.key`, hvis du bruger PEM-formatet.
Gem certifikatfilen som `PowerBICustomVisualTest_public.pfx`, hvis du bruger PFX-formatet.

Hvis PFX-certifikatfilen kræver et adgangsudtryk, skal du angive

```cmd
\PowerBI-visuals-tools\config.json
```

i serversektionen:

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
