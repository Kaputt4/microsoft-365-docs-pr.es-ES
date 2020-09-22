---
title: Buscar amenazas en dispositivos, mensajes de correo electrónico, aplicaciones e identidades con búsqueda avanzada
description: Estudie los escenarios de búsqueda y las consultas de ejemplo comunes que cubren los dispositivos, los correos electrónicos, las aplicaciones y las identidades.
keywords: características avanzadas de búsqueda, datos de Office365, dispositivos Windows, mensajes de correo electrónico de Office365, mensajes de correo electrónico, aplicaciones, identidades, caza de amenazas, búsqueda de amenazas en el ciberespacio, búsqueda, consulta, telemetría, Microsoft 365, protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 5b2ef4881eabea7e546eb8cd3d164b372b0018ee
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199846"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Buscar amenazas en dispositivos, mensajes de correo electrónico, aplicaciones e identidades

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

La [caza avanzada](advanced-hunting-overview.md) de la protección contra amenazas de Microsoft permite buscar de forma proactiva las amenazas en:
- Dispositivos administrados por ATP de Microsoft defender
- Mensajes de correo electrónico procesados por Microsoft 365
- Actividades de la aplicación de nube, eventos de autenticación y actividades del controlador de dominio a las que hace seguimiento Microsoft Cloud App Security y Azure ATP

Con este nivel de visibilidad, puede buscar rápidamente amenazas que atraviesan secciones de la red, incluidas las complejas intrusiones que llegan en el correo electrónico o en la web, elevan los privilegios locales, adquieren credenciales de dominio privilegiadas y se mueven al otro lado de sus dispositivos. 

Estas son las técnicas generales y las consultas de ejemplo basadas en diversos escenarios de caza que pueden ayudarle a aprender cómo puede crear consultas al buscar amenazas tan sofisticadas.

## <a name="get-entity-info"></a>Obtener información de la entidad
Use estas consultas para saber cómo puede obtener rápidamente información sobre las cuentas de usuario, los dispositivos y los archivos. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Obtener cuentas de usuario a través de las direcciones de correo electrónico
Al crear consultas a través de [tablas que cubran dispositivos y mensajes de correo electrónico](advanced-hunting-schema-tables.md), puede que necesite obtener los nombres de las cuentas de usuario en las direcciones de correo electrónico del remitente o destinatario. Por lo general, puede hacerlo para la dirección del destinatario o del remitente mediante el *host local* desde la dirección de correo electrónico.

En el fragmento de código siguiente, usamos la función [ToString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto para extraer el derecho de host local antes de las `@` direcciones de correo electrónico de destinatarios de la columna `RecipientEmailAddress` .

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

Puede obtener nombres de cuenta y otra información de la cuenta si combina o combina la [tabla IdentityInfo](advanced-hunting-identityinfo-table.md). La siguiente consulta obtiene la lista de detecciones de suplantación de identidad (phishing) y malware de la [tabla EmailEvents](advanced-hunting-emailevents-table.md) y, a continuación, combina esa información con la `IdentityInfo` tabla para obtener información detallada acerca de cada destinatario. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>Obtener información del dispositivo
El [esquema de búsqueda avanzada](advanced-hunting-schema-tables.md) proporciona una amplia información de dispositivos en varias tablas. Por ejemplo, la [tabla DeviceInfo](advanced-hunting-deviceinfo-table.md) proporciona información completa sobre dispositivos en función de los datos de eventos agregados con regularidad. Esta consulta usa la `DeviceInfo` tabla para comprobar si un usuario potencialmente comprometido ( `<account-name>` ) ha iniciado sesión en cualquier dispositivo y, a continuación, muestra las alertas que se han desencadenado en dichos dispositivos.

>[!Tip]
> Esta consulta usa `kind=inner` para especificar una [Unión interna](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), que impide la desduplicación de los valores del lado izquierdo `DeviceId` .

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

## <a name="hunting-scenarios"></a>Escenarios de búsqueda

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Enumerar las actividades de inicio de sesión de los usuarios que recibieron mensajes de correo electrónico que no se zapped correctamente
[La depuración automática de cero horas (ZAP)](../office-365-security/zero-hour-auto-purge.md) redirige los correos electrónicos malintencionados después de que se hayan recibido. Si se produce un error en ZAP, el código malintencionado se podría ejecutar eventualmente en el dispositivo y dejar cuentas en peligro. Esta consulta comprueba la actividad de inicio de sesión realizada por los destinatarios de los correos electrónicos que no se han tratado correctamente mediante ZAP.

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Obtener intentos de inicio de sesión por cuentas de dominio dirigidas por el robo de credenciales
Esta consulta identifica primero todas las alertas de acceso a credenciales en la `AlertInfo` tabla. A continuación, combina o une la `AlertEvidence` tabla, que analiza los nombres de las cuentas de destino y los filtros de las cuentas Unidas a un dominio únicamente. Por último, comprueba la `IdentityLogonEvents` tabla para obtener todas las actividades de inicio de sesión de las cuentas de destino Unidas a un dominio.

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
Suponiendo que conoce una dirección de correo electrónico que envía archivos malintencionados ( `MaliciousSender@example.com` ), puede ejecutar esta consulta para determinar si existen archivos de este remitente en los dispositivos. Puede usar esta consulta, por ejemplo, para identificar los dispositivos afectados por una campaña de distribución de malware.

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
| where MalwareFilterVerdict == "Malware"
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
Los mensajes malintencionados suelen contener documentos y otros datos adjuntos especialmente diseñados para ejecutar comandos de PowerShell para ofrecer cargas adicionales. Si conoce los mensajes de correo electrónico procedentes de un remitente malintencionado conocido ( `MaliciousSender@example.com` ), puede usar esta consulta para enumerar y revisar las actividades de PowerShell que se produjeron en un plazo de 30 minutos después de la recepción del correo electrónico del remitente.  

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
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
