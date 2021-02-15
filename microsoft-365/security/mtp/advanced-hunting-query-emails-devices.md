---
title: Buscar amenazas en dispositivos, correos electrónicos, aplicaciones e identidades con búsqueda avanzada
description: Estudiar escenarios de búsqueda comunes y consultas de ejemplo que cubren dispositivos, correos electrónicos, aplicaciones e identidades.
keywords: búsqueda avanzada, datos de Office365, dispositivos Windows, normalizar los correos electrónicos de Office365, correos electrónicos, aplicaciones, identidades, búsqueda de amenazas, búsqueda de ciberamenazas, búsqueda, consulta, telemetría, Microsoft 365, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b408f574ab4b89806be9154394f49c00a7fd1e99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932255"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="ddd22-104">Búsqueda de amenazas en dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="ddd22-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ddd22-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ddd22-105">**Applies to:**</span></span>
- <span data-ttu-id="ddd22-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ddd22-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ddd22-107">[La búsqueda](advanced-hunting-overview.md) avanzada en Microsoft 365 Defender le permite buscar de forma proactiva amenazas en:</span><span class="sxs-lookup"><span data-stu-id="ddd22-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="ddd22-108">Dispositivos administrados por Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="ddd22-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="ddd22-109">Correos electrónicos procesados por Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ddd22-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="ddd22-110">Actividades de aplicaciones en la nube, eventos de autenticación y actividades de controlador de dominio que realiza Microsoft Cloud App Security y Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="ddd22-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="ddd22-111">Con este nivel de visibilidad, puede buscar rápidamente las amenazas que atraviesan secciones de la red, incluidas las sofisticadas intrusiones que llegan al correo electrónico o a la web, elevar privilegios locales, adquirir credenciales de dominio con privilegios y moverse lateralmente a través de sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddd22-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="ddd22-112">Estas son técnicas generales y consultas de ejemplo basadas en diversos escenarios de búsqueda que pueden ayudarle a explorar cómo puede crear consultas al buscar amenazas sofisticadas.</span><span class="sxs-lookup"><span data-stu-id="ddd22-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="ddd22-113">Obtener información de entidad</span><span class="sxs-lookup"><span data-stu-id="ddd22-113">Get entity info</span></span>
<span data-ttu-id="ddd22-114">Usa estas consultas para obtener información sobre cómo obtener rápidamente información sobre cuentas de usuario, dispositivos y archivos.</span><span class="sxs-lookup"><span data-stu-id="ddd22-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="ddd22-115">Obtener cuentas de usuario a través de las direcciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="ddd22-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="ddd22-116">Al crear consultas a través de [tablas que cubran dispositivos y mensajes de correo electrónico](advanced-hunting-schema-tables.md), puede que necesite obtener los nombres de las cuentas de usuario en las direcciones de correo electrónico del remitente o destinatario.</span><span class="sxs-lookup"><span data-stu-id="ddd22-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="ddd22-117">Por lo general, puede hacerlo para la dirección del destinatario o del remitente mediante el *host local* de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ddd22-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="ddd22-118">En el fragmento de código siguiente, usamos la función [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto para extraer el host local justo antes de las direcciones de correo electrónico del destinatario de la `@` columna `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="ddd22-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="ddd22-119">La consulta siguiente muestra cómo se puede usar este fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="ddd22-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="ddd22-120">Combinar la tabla IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="ddd22-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="ddd22-121">Puede obtener nombres de cuenta y otra información de cuenta si combina o se une a la [tabla IdentityInfo](advanced-hunting-identityinfo-table.md).</span><span class="sxs-lookup"><span data-stu-id="ddd22-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="ddd22-122">La consulta siguiente obtiene la lista de detecciones de suplantación de identidad (phishing) y malware de la tabla [EmailEvents](advanced-hunting-emailevents-table.md) y, a continuación, une esa información con la tabla para obtener información detallada sobre `IdentityInfo` cada destinatario.</span><span class="sxs-lookup"><span data-stu-id="ddd22-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="ddd22-123">Obtener información del dispositivo</span><span class="sxs-lookup"><span data-stu-id="ddd22-123">Get device information</span></span>
<span data-ttu-id="ddd22-124">El [esquema de búsqueda avanzada proporciona](advanced-hunting-schema-tables.md) información extensa del dispositivo en varias tablas.</span><span class="sxs-lookup"><span data-stu-id="ddd22-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="ddd22-125">Por ejemplo, la [tabla DeviceInfo proporciona](advanced-hunting-deviceinfo-table.md) información completa del dispositivo en función de los datos de eventos agregados periódicamente.</span><span class="sxs-lookup"><span data-stu-id="ddd22-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="ddd22-126">Esta consulta usa la tabla para comprobar si un usuario potencialmente comprometido ( ) ha iniciado sesión en algún dispositivo y, a continuación, enumera las alertas que se han desencadenado `DeviceInfo` `<account-name>` en esos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddd22-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="ddd22-127">Esta consulta se usa para especificar una combinación interna , que `kind=inner` evita la [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)desduplicación de los valores del lado izquierdo para `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="ddd22-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="ddd22-128">Escenarios de búsqueda</span><span class="sxs-lookup"><span data-stu-id="ddd22-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="ddd22-129">Enumerar las actividades de inicio de sesión de los usuarios que recibieron mensajes de correo electrónico que no se recortaron correctamente</span><span class="sxs-lookup"><span data-stu-id="ddd22-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="ddd22-130">[La purga automática (ZAP)](../office-365-security/zero-hour-auto-purge.md) de cero horas resuelve los correos electrónicos malintencionados después de que se hayan recibido.</span><span class="sxs-lookup"><span data-stu-id="ddd22-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="ddd22-131">Si se produce un error en ZAP, es posible que el código malintencionado se ejecute en el dispositivo y deje las cuentas en peligro.</span><span class="sxs-lookup"><span data-stu-id="ddd22-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="ddd22-132">Esta consulta comprueba la actividad de inicio de sesión realizada por los destinatarios de los correos electrónicos que ZAP no ha abordado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ddd22-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="ddd22-133">Obtener intentos de inicio de sesión por cuentas de dominio destinadas al robo de credenciales</span><span class="sxs-lookup"><span data-stu-id="ddd22-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="ddd22-134">Esta consulta identifica primero todas las alertas de acceso a credenciales de la `AlertInfo` tabla.</span><span class="sxs-lookup"><span data-stu-id="ddd22-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="ddd22-135">A continuación, combina o une la tabla, que analiza los nombres de las cuentas de destino y filtra solo para las cuentas unidas `AlertEvidence` a un dominio.</span><span class="sxs-lookup"><span data-stu-id="ddd22-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="ddd22-136">Por último, comprueba la tabla para obtener todas las actividades de inicio de sesión de las cuentas de destino unidas `IdentityLogonEvents` al dominio.</span><span class="sxs-lookup"><span data-stu-id="ddd22-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="ddd22-137">Compruebe si entre sus dispositivos se encuentran archivos de un remitente malintencionado conocido.</span><span class="sxs-lookup"><span data-stu-id="ddd22-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="ddd22-138">Suponiendo que conoce una dirección de correo electrónico que envía archivos malintencionados ( ), puede ejecutar esta consulta para determinar si existen archivos de este remitente `MaliciousSender@example.com` en sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddd22-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="ddd22-139">Puedes usar esta consulta, por ejemplo, para identificar los dispositivos afectados por una campaña de distribución de malware.</span><span class="sxs-lookup"><span data-stu-id="ddd22-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="ddd22-140">Revisar los intentos de inicio de sesión después de recibir mensajes de correo electrónico malintencionados.</span><span class="sxs-lookup"><span data-stu-id="ddd22-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="ddd22-141">Esta consulta busca los 10 últimos inicios de sesión realizados por destinatarios de correo electrónico en un plazo de 30 minutos después de haber recibido mensajes de correo electrónico conocidos por parte del remitente malintencionado </span><span class="sxs-lookup"><span data-stu-id="ddd22-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="ddd22-142">Puede utilizar esta consulta para comprobar si las cuentas de los destinatarios del correo electrónico se han visto comprometidas.</span><span class="sxs-lookup"><span data-stu-id="ddd22-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="ddd22-143">Revisar las actividades de PowerShell después de recibir mensajes de correo electrónico conocidos por parte del remitente malintencionado </span><span class="sxs-lookup"><span data-stu-id="ddd22-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="ddd22-144">Los mensajes malintencionados suelen contener documentos y otros datos adjuntos especialmente diseñados para ejecutar comandos de PowerShell para ofrecer cargas adicionales.</span><span class="sxs-lookup"><span data-stu-id="ddd22-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="ddd22-145">Si conoce los correos electrónicos procedentes de un remitente malintencionado conocido ( ), puede usar esta consulta para enumerar y revisar las actividades de PowerShell que se produjeron en un plazo de 30 minutos después de recibir un correo electrónico del `MaliciousSender@example.com` remitente.</span><span class="sxs-lookup"><span data-stu-id="ddd22-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="ddd22-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ddd22-146">Related topics</span></span>
- [<span data-ttu-id="ddd22-147">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="ddd22-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ddd22-148">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="ddd22-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ddd22-149">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="ddd22-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="ddd22-150">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="ddd22-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ddd22-151">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="ddd22-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ddd22-152">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="ddd22-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
