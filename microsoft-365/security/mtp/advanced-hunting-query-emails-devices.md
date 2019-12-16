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
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="a2ffa-104">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="a2ffa-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="a2ffa-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a2ffa-105">**Applies to:**</span></span>
- <span data-ttu-id="a2ffa-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2ffa-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="a2ffa-107">La [Búsqueda avanzada](advanced-hunting-overview.md) en la Protección contra amenazas de Microsoft le permite buscar de forma proactiva amenazas en sus dispositivos Windows y en los correos electrónicos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Office 365 emails.</span></span> <span data-ttu-id="a2ffa-108">Éstos son algunos escenarios de búsqueda y consultas de ejemplo que puedan ayudarle a explorar la forma en que puede crear consultas que cubran tanto dispositivos como mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="a2ffa-109">Obtener cuentas de usuario a través de las direcciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="a2ffa-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="a2ffa-110">Al crear consultas a través de [tablas que cubran dispositivos y mensajes de correo electrónico](advanced-hunting-schema-tables.md), puede que necesite obtener los nombres de las cuentas de usuario en las direcciones de correo electrónico del remitente o destinatario.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="a2ffa-111">Para ello, utilice el *host local* de la dirección de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="a2ffa-111">To do this use the *local-host* from the email address:</span></span>

```
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="a2ffa-112">Esta técnica de normalización se utiliza en los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="a2ffa-113">Escenarios de búsqueda</span><span class="sxs-lookup"><span data-stu-id="a2ffa-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="a2ffa-114">Compruebe si entre sus dispositivos se encuentran archivos de un remitente malintencionado conocido.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="a2ffa-115">Suponiendo que conozca la dirección de correo electrónico que envía archivos maliciosos, usted puede ejecutar esta consulta para determinar si los archivos de este remitente se encuentran entre sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="a2ffa-116">Puede utilizar esta consulta para, por ejemplo, determinar el número de dispositivos afectados por una campaña de distribución de malware.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="a2ffa-117">Revisar los intentos de inicio de sesión después de recibir mensajes de correo electrónico malintencionados.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="a2ffa-118">Esta consulta busca los 10 últimos inicios de sesión realizados por destinatarios de correo electrónico en un plazo de 30 minutos después de haber recibido mensajes de correo electrónico conocidos por parte del remitente malintencionado </span><span class="sxs-lookup"><span data-stu-id="a2ffa-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="a2ffa-119">Puede utilizar esta consulta para comprobar si las cuentas de los destinatarios del correo electrónico se han visto comprometidas.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="a2ffa-120">Revisar las actividades de PowerShell después de recibir mensajes de correo electrónico conocidos por parte del remitente malintencionado </span><span class="sxs-lookup"><span data-stu-id="a2ffa-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="a2ffa-121">Los mensajes malintencionados suelen contener documentos y otros datos adjuntos especialmente diseñados para ejecutar comandos de PowerShell para ofrecer cargas adicionales.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="a2ffa-122">Si tiene conocimiento sobre mensajes de correo electrónico conocidos procedentes del remitente malintencionado, puede utilizar esta consulta para listar y revisar actividades de PowerShell que se hayan producido en un plazo de 30 minutos después de recibir un mensaje de correo electrónico de dicho remitente.</span><span class="sxs-lookup"><span data-stu-id="a2ffa-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="a2ffa-123">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a2ffa-123">Related topics</span></span>
- [<span data-ttu-id="a2ffa-124">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="a2ffa-124">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a2ffa-125">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="a2ffa-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a2ffa-126">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="a2ffa-126">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a2ffa-127">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="a2ffa-127">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a2ffa-128">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="a2ffa-128">Apply query best practices</span></span>](advanced-hunting-best-practices.md)