---
title: Búsqueda de amenazas entre dispositivos, correos electrónicos, aplicaciones e identidades con búsqueda avanzada
description: Estudiar escenarios de búsqueda comunes y consultas de ejemplo que cubren dispositivos, correos electrónicos, aplicaciones e identidades.
keywords: búsqueda avanzada, datos de Office365, dispositivos Windows, correos electrónicos de Office365 normalizar, correos electrónicos, aplicaciones, identidades, búsqueda de amenazas, búsqueda de ciberamenazas, búsqueda, consulta, telemetría, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 740f9c5e683297f2a4d990cad5fdbc8c6295ed57
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481864"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Buscar amenazas entre dispositivos, correos electrónicos, aplicaciones e identidades

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[La búsqueda avanzada](advanced-hunting-overview.md) en Microsoft 365 Defender le permite buscar amenazas de forma proactiva en:
- Dispositivos administrados por Microsoft Defender para punto de conexión
- Correos electrónicos procesados por Microsoft 365
- Actividades de aplicación en la nube, eventos de autenticación y actividades de controlador de dominio a las que Microsoft Defender for Cloud Apps y Microsoft Defender for Identity

Con este nivel de visibilidad, puede buscar rápidamente amenazas que atraviesan secciones de la red, incluidas intrusiones sofisticadas que llegan al correo electrónico o a la web, elevar privilegios locales, adquirir credenciales de dominio con privilegios y moverse lateralmente a través de los dispositivos. 

Estas son técnicas generales y consultas de ejemplo basadas en diversos escenarios de búsqueda que pueden ayudarle a explorar cómo puede crear consultas al buscar amenazas sofisticadas.

## <a name="get-entity-info"></a>Obtener información de entidad
Use estas consultas para obtener información sobre las cuentas de usuario, los dispositivos y los archivos rápidamente. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Obtener cuentas de usuario a través de las direcciones de correo electrónico
Al crear consultas a través de [tablas que cubran dispositivos y mensajes de correo electrónico](advanced-hunting-schema-tables.md), puede que necesite obtener los nombres de las cuentas de usuario en las direcciones de correo electrónico del remitente o destinatario. Por lo general, puede hacerlo para el destinatario o la dirección del remitente mediante el *host local* de la dirección de correo electrónico.

En el fragmento de código siguiente, usamos la función [kusto tostring()](/azure/data-explorer/kusto/query/tostringfunction) para extraer el host local justo antes de las `@` direcciones de correo electrónico del destinatario en la columna `RecipientEmailAddress`.

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
En la consulta siguiente se muestra cómo se puede usar este fragmento de código:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Combinación de la tabla IdentityInfo

Puede obtener nombres de cuenta y otra información de cuenta mediante la combinación o unión de la [tabla IdentityInfo](advanced-hunting-identityinfo-table.md). En la consulta siguiente se obtiene la lista de detecciones de phishing y malware de la [tabla EmailEvents](advanced-hunting-emailevents-table.md) y, a continuación, se une esa información con la `IdentityInfo` tabla para obtener información detallada sobre cada destinatario. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

Vea este [breve vídeo](https://www.youtube.com/watch?v=8qZx7Pp5XgM) para obtener información sobre cómo puede usar Lenguaje de consulta Kusto para combinar tablas.  

### <a name="get-device-information"></a>Obtener información del dispositivo

El [esquema de búsqueda avanzada](advanced-hunting-schema-tables.md) proporciona una amplia información del dispositivo en varias tablas. Por ejemplo, la [tabla DeviceInfo](advanced-hunting-deviceinfo-table.md) proporciona información completa del dispositivo basada en los datos de eventos agregados periódicamente. Esta consulta usa la `DeviceInfo` tabla para comprobar si un usuario potencialmente en peligro (`<account-name>`) ha iniciado sesión en algún dispositivo y, a continuación, enumera las alertas que se han desencadenado en esos dispositivos.

>[!Tip]
> Esta consulta usa `kind=inner` para especificar una [combinación interna](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), lo que evita la desduplicación de valores del lado izquierdo para `DeviceId`.

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```


### <a name="get-file-event-information"></a>Obtener información de eventos de archivo

Use la siguiente consulta para obtener información sobre los eventos relacionados con archivos. 

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceFileEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="get-network-event-information"></a>Obtención de información de eventos de red

Use la consulta siguiente para obtener información sobre los eventos relacionados con la red.

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-agent-version-information"></a>Obtener información de la versión del agente de dispositivo

Use la siguiente consulta para obtener la versión del agente que se ejecuta en un dispositivo.

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="example-query-for-macos-devices"></a>Consulta de ejemplo para dispositivos macOS

Use la consulta de ejemplo siguiente para ver todos los dispositivos que ejecutan macOS con una versión anterior a Catalina.

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OSPlatform == "macOS" and  OSVersion !contains "10.15" and OSVersion !contains "11."
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-status-info"></a>Obtener información de estado del dispositivo

Use la siguiente consulta para obtener el estado de un dispositivo. En el ejemplo siguiente, la consulta comprueba si el dispositivo está incorporado.

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OnboardingStatus != "Onboarded"
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


## <a name="hunting-scenarios"></a>Escenarios de búsqueda

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Enumerar las actividades de inicio de sesión de los usuarios que recibieron correos electrónicos que no se han zapped correctamente

[La purga automática de cero horas (ZAP)](../office-365-security/zero-hour-auto-purge.md) aborda los correos electrónicos malintencionados después de recibirlos. Si se produce un error en ZAP, el código malintencionado podría ejecutarse en el dispositivo y dejar las cuentas en peligro. Esta consulta comprueba la actividad de inicio de sesión realizada por los destinatarios de los correos electrónicos que zap no ha abordado correctamente.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Obtención de intentos de inicio de sesión por cuentas de dominio destinadas al robo de credenciales

Esta consulta identifica primero todas las alertas de acceso a credenciales de la `AlertInfo` tabla. A continuación, combina o une la `AlertEvidence` tabla, que analiza solo los nombres de las cuentas de destino y los filtros de las cuentas unidas a un dominio. Por último, comprueba la `IdentityLogonEvents` tabla para obtener todas las actividades de inicio de sesión de las cuentas de destino unidas al dominio.

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Compruebe si entre sus dispositivos se encuentran archivos de un remitente malintencionado conocido.

Suponiendo que conoce una dirección de correo electrónico que envía archivos malintencionados (`MaliciousSender@example.com`), puede ejecutar esta consulta para determinar si existen archivos de este remitente en los dispositivos. Puede usar esta consulta, por ejemplo, para identificar los dispositivos afectados por una campaña de distribución de malware.

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256, DeviceName, DeviceId
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Revisar los intentos de inicio de sesión después de recibir mensajes de correo electrónico malintencionados.

Esta consulta busca los 10 últimos inicios de sesión realizados por destinatarios de correo electrónico en un plazo de 30 minutos después de haber recibido mensajes de correo electrónico conocidos por parte del remitente malintencionado  Puede utilizar esta consulta para comprobar si las cuentas de los destinatarios del correo electrónico se han visto comprometidas.

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where ThreatTypes has "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Revisar las actividades de PowerShell después de recibir mensajes de correo electrónico conocidos por parte del remitente malintencionado 

Los mensajes malintencionados suelen contener documentos y otros datos adjuntos especialmente diseñados para ejecutar comandos de PowerShell para ofrecer cargas adicionales. Si conoce los correos electrónicos procedentes de un remitente malintencionado conocido (`MaliciousSender@example.com`), puede usar esta consulta para enumerar y revisar las actividades de PowerShell que se produjeron en un plazo de 30 minutos después de recibir un correo electrónico del remitente.  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
