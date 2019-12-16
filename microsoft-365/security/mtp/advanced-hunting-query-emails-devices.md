---
title: Encuentre amenazas entre los dispositivos y mensajes de correo electrónico utilizando la búsqueda avanzada
description: Estudie los escenarios de búsqueda comunes y las consultas de ejemplo que cubran los dispositivos y correos electrónicos.
keywords: Búsqueda avanzada, datos de Office365, dispositivos Windows, normalización de correos electrónicos de Office365, correos electrónicos, búsqueda, búsqueda de amenazas, de ciberamenazas, consulta, telemetría, Microsoft 365, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b374aac84b309d18a88ee7248021b50a893e120c
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911622"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>Búsqueda de amenazas en dispositivos y mensajes de correo electrónico

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!include[Prerelease information](prerelease.md)]

La [Búsqueda avanzada](advanced-hunting-overview.md) en la Protección contra amenazas de Microsoft le permite buscar de forma proactiva amenazas en sus dispositivos Windows y en los correos electrónicos de Office 365. Éstos son algunos escenarios de búsqueda y consultas de ejemplo que puedan ayudarle a explorar la forma en que puede crear consultas que cubran tanto dispositivos como mensajes de correo electrónico.

## <a name="obtain-user-accounts-from-email-addresses"></a>Obtener cuentas de usuario a través de las direcciones de correo electrónico
Al crear consultas a través de [tablas que cubran dispositivos y mensajes de correo electrónico](advanced-hunting-schema-tables.md), puede que necesite obtener los nombres de las cuentas de usuario en las direcciones de correo electrónico del remitente o destinatario. Para ello, utilice el *host local* de la dirección de correo electrónico:

```
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

Esta técnica de normalización se utiliza en los siguientes escenarios.

## <a name="hunting-scenarios"></a>Escenarios de búsqueda

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Compruebe si entre sus dispositivos se encuentran archivos de un remitente malintencionado conocido.
Suponiendo que conozca la dirección de correo electrónico que envía archivos maliciosos, usted puede ejecutar esta consulta para determinar si los archivos de este remitente se encuentran entre sus dispositivos. Puede utilizar esta consulta para, por ejemplo, determinar el número de dispositivos afectados por una campaña de distribución de malware.

```
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
FileCreationEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Revisar los intentos de inicio de sesión después de recibir mensajes de correo electrónico malintencionados.
Esta consulta busca los 10 últimos inicios de sesión realizados por destinatarios de correo electrónico en un plazo de 30 minutos después de haber recibido mensajes de correo electrónico conocidos por parte del remitente malintencionado  Puede utilizar esta consulta para comprobar si las cuentas de los destinatarios del correo electrónico se han visto comprometidas.

```
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
LogonEvents
| project LogonTime = EventTime, AccountName, ComputerName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Revisar las actividades de PowerShell después de recibir mensajes de correo electrónico conocidos por parte del remitente malintencionado 
Los mensajes malintencionados suelen contener documentos y otros datos adjuntos especialmente diseñados para ejecutar comandos de PowerShell para ofrecer cargas adicionales. Si tiene conocimiento sobre mensajes de correo electrónico conocidos procedentes del remitente malintencionado, puede utilizar esta consulta para listar y revisar actividades de PowerShell que se hayan producido en un plazo de 30 minutos después de recibir un mensaje de correo electrónico de dicho remitente.  

```
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
ProcessCreationEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = EventTime, AccountName, ComputerName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)