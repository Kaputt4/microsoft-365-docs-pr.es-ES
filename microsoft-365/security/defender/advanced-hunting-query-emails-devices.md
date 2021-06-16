---
title: Buscar amenazas en dispositivos, correos electrónicos, aplicaciones e identidades con búsqueda avanzada
description: Estudiar escenarios comunes de búsqueda y consultas de ejemplo que cubren dispositivos, correos electrónicos, aplicaciones e identidades.
keywords: búsqueda avanzada, datos de Office365, dispositivos Windows, correos electrónicos de Office365 normalizar, correos electrónicos, aplicaciones, identidades, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: aacd0745ff507356035f8f460ed2b4307e9da6ed
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964878"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Buscar amenazas entre dispositivos, correos electrónicos, aplicaciones e identidades

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[La búsqueda](advanced-hunting-overview.md) avanzada en Microsoft 365 Defender permite buscar de forma proactiva amenazas en:
- Dispositivos administrados por Microsoft Defender para endpoint
- Correos electrónicos procesados por Microsoft 365
- Actividades de aplicación en la nube, eventos de autenticación y actividades de controlador de dominio que realiza el seguimiento de Microsoft Cloud App Security y Microsoft Defender for Identity

Con este nivel de visibilidad, puede buscar rápidamente amenazas que atraviesan secciones de la red, incluidas las intrusiones sofisticadas que llegan al correo electrónico o a la web, elevar los privilegios locales, adquirir credenciales de dominio con privilegios y moverse lateralmente a través de los dispositivos. 

Estas son técnicas generales y consultas de ejemplo basadas en diversos escenarios de búsqueda que pueden ayudarle a explorar cómo puede crear consultas al buscar amenazas tan sofisticadas.

## <a name="get-entity-info"></a>Obtener información de entidad
Use estas consultas para obtener información sobre las cuentas de usuario, los dispositivos y los archivos rápidamente. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Obtener cuentas de usuario a través de las direcciones de correo electrónico
Al crear consultas a través de [tablas que cubran dispositivos y mensajes de correo electrónico](advanced-hunting-schema-tables.md), puede que necesite obtener los nombres de las cuentas de usuario en las direcciones de correo electrónico del remitente o destinatario. Por lo general, puede hacerlo para la dirección de destinatario o remitente mediante el *host local* desde la dirección de correo electrónico.

En el fragmento de código siguiente, usamos la función [Kusto tostring()](/azure/data-explorer/kusto/query/tostringfunction) para extraer el host local justo antes de las direcciones de correo electrónico del destinatario de `@` la columna `RecipientEmailAddress` .

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
La siguiente consulta muestra cómo se puede usar este fragmento de código:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Combinar la tabla IdentityInfo

Puede obtener nombres de cuenta y otra información de cuenta combinando o uniendo la [tabla IdentityInfo](advanced-hunting-identityinfo-table.md). La siguiente consulta obtiene la lista de detecciones de phishing y malware de la tabla [EmailEvents](advanced-hunting-emailevents-table.md) y, a continuación, une esa información con la tabla para obtener información detallada sobre `IdentityInfo` cada destinatario. 

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

### <a name="get-device-information"></a>Obtener información del dispositivo
El [esquema de búsqueda avanzada](advanced-hunting-schema-tables.md) proporciona información extensa del dispositivo en varias tablas. Por ejemplo, la [tabla DeviceInfo proporciona](advanced-hunting-deviceinfo-table.md) información completa del dispositivo basada en datos de eventos agregados periódicamente. Esta consulta usa la tabla para comprobar si un usuario potencialmente comprometido ( ) ha iniciado sesión en cualquier dispositivo y, a continuación, enumera las alertas que se han desencadenado `DeviceInfo` `<account-name>` en esos dispositivos.

>[!Tip]
> Esta consulta se `kind=inner` usa para especificar una combinación [interna](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), que evita la desduplicación de los valores del lado izquierdo para `DeviceId` .

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

Use la siguiente consulta para obtener información sobre eventos relacionados con archivos. 

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


### <a name="get-network-event-information"></a>Obtener información de eventos de red

Use la siguiente consulta para obtener información sobre eventos relacionados con la red.

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

### <a name="get-device-agent-version-information"></a>Obtener información de versión del agente de dispositivo

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

Use la siguiente consulta de ejemplo para ver todos los dispositivos que ejecutan macOS con una versión anterior a Catalina.

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

Usa la siguiente consulta para obtener el estado de un dispositivo. En el siguiente ejemplo, la consulta comprueba si el dispositivo está incorporado.

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

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Enumerar las actividades de inicio de sesión de los usuarios que recibieron correos electrónicos que no se zapped correctamente
[La purga automática de hora cero (ZAP)](../office-365-security/zero-hour-auto-purge.md) aborda correos electrónicos malintencionados después de que se hayan recibido. Si SE produce un error en ZAP, es posible que el código malintencionado se ejecute en el dispositivo y deje las cuentas en peligro. Esta consulta busca la actividad de inicio de sesión realizada por los destinatarios de los correos electrónicos que ZAP no ha abordado correctamente.

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Obtener intentos de inicio de sesión por cuentas de dominio destinadas al robo de credenciales
Esta consulta identifica primero todas las alertas de acceso a credenciales de la `AlertInfo` tabla. A continuación, combina o une la tabla, que analiza los nombres de las cuentas de destino y filtra solo para cuentas unidas `AlertEvidence` a un dominio. Por último, comprueba la tabla para obtener todas las actividades de inicio de sesión de las cuentas de destino unidas `IdentityLogonEvents` al dominio.

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
Suponiendo que conoce una dirección de correo electrónico que envía archivos malintencionados ( ), puede ejecutar esta consulta para determinar si existen archivos de este `MaliciousSender@example.com` remitente en sus dispositivos. Puede usar esta consulta, por ejemplo, para identificar los dispositivos afectados por una campaña de distribución de malware.

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
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
Los mensajes malintencionados suelen contener documentos y otros datos adjuntos especialmente diseñados para ejecutar comandos de PowerShell para ofrecer cargas adicionales. Si conoce los correos electrónicos procedentes de un remitente malintencionado conocido ( ), puede usar esta consulta para enumerar y revisar las actividades de PowerShell que se produjeron en un plazo de 30 minutos después de recibir un correo electrónico del `MaliciousSender@example.com` remitente.  

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
