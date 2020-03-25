---
title: Tabla AlertEvidence en el esquema de búsqueda avanzada
description: Información sobre archivos, direcciones de red, usuarios o dispositivos asociados con alertas generadas en la tabla AlertEvidence del esquema de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, equipo, usuario, cuenta
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
ms.openlocfilehash: 1a58d1e5db2ea8689d4909e6e9c47b08a6e94d34
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929238"
---
# <a name="alertevidence"></a><span data-ttu-id="72b27-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="72b27-104">AlertEvidence</span></span>

<span data-ttu-id="72b27-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="72b27-105">**Applies to:**</span></span>
- <span data-ttu-id="72b27-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="72b27-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="72b27-107">La `AlertEvidence` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre diversas entidades (archivos, direcciones IP, direcciones URL, usuarios o dispositivos) asociadas con alertas de ATP de microsoft defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="72b27-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="72b27-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="72b27-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="72b27-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="72b27-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="72b27-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="72b27-110">Column name</span></span> | <span data-ttu-id="72b27-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="72b27-111">Data type</span></span> | <span data-ttu-id="72b27-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="72b27-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="72b27-113">datetime</span><span class="sxs-lookup"><span data-stu-id="72b27-113">datetime</span></span> | <span data-ttu-id="72b27-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="72b27-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="72b27-115">string</span><span class="sxs-lookup"><span data-stu-id="72b27-115">string</span></span> | <span data-ttu-id="72b27-116">Identificador único de alerta.</span><span class="sxs-lookup"><span data-stu-id="72b27-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="72b27-117">string</span><span class="sxs-lookup"><span data-stu-id="72b27-117">string</span></span> | <span data-ttu-id="72b27-118">Tipo de objeto, como un archivo, un proceso, un dispositivo o un usuario</span><span class="sxs-lookup"><span data-stu-id="72b27-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="72b27-119">string</span><span class="sxs-lookup"><span data-stu-id="72b27-119">string</span></span> | <span data-ttu-id="72b27-120">Cómo interviene la entidad en una alerta, lo que indica si se ve afectada o si simplemente está relacionada.</span><span class="sxs-lookup"><span data-stu-id="72b27-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="72b27-121">string</span><span class="sxs-lookup"><span data-stu-id="72b27-121">string</span></span> | <span data-ttu-id="72b27-122">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="72b27-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="72b27-123">cadena</span><span class="sxs-lookup"><span data-stu-id="72b27-123">string</span></span> | <span data-ttu-id="72b27-124">SHA-256 del archivo donde se aplicó la acción registrada.</span><span class="sxs-lookup"><span data-stu-id="72b27-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="72b27-125">Este campo no suele rellenarse; use la columna SHA1 cuando esté disponible.</span><span class="sxs-lookup"><span data-stu-id="72b27-125">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="72b27-126">string</span><span class="sxs-lookup"><span data-stu-id="72b27-126">string</span></span> | <span data-ttu-id="72b27-127">Dirección IP a la que se ha conectado</span><span class="sxs-lookup"><span data-stu-id="72b27-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="72b27-128">string</span><span class="sxs-lookup"><span data-stu-id="72b27-128">string</span></span> | <span data-ttu-id="72b27-129">La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado.</span><span class="sxs-lookup"><span data-stu-id="72b27-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="72b27-130">cadena</span><span class="sxs-lookup"><span data-stu-id="72b27-130">string</span></span> | <span data-ttu-id="72b27-131">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="72b27-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="72b27-132">string</span><span class="sxs-lookup"><span data-stu-id="72b27-132">string</span></span> | <span data-ttu-id="72b27-133">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="72b27-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="72b27-134">string</span><span class="sxs-lookup"><span data-stu-id="72b27-134">string</span></span> | <span data-ttu-id="72b27-135">Identificador de seguridad (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="72b27-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="72b27-136">string</span><span class="sxs-lookup"><span data-stu-id="72b27-136">string</span></span> | <span data-ttu-id="72b27-137">Identificador único de la cuenta en Azure AD</span><span class="sxs-lookup"><span data-stu-id="72b27-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="72b27-138">string</span><span class="sxs-lookup"><span data-stu-id="72b27-138">string</span></span> | <span data-ttu-id="72b27-139">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="72b27-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="72b27-140">string</span><span class="sxs-lookup"><span data-stu-id="72b27-140">string</span></span> | <span data-ttu-id="72b27-141">Familia de malware en la que el archivo o proceso malintencionado se clasificó en</span><span class="sxs-lookup"><span data-stu-id="72b27-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="72b27-142">string</span><span class="sxs-lookup"><span data-stu-id="72b27-142">string</span></span> | <span data-ttu-id="72b27-143">Indica si la entidad es el origen o el destino de una conexión de red.</span><span class="sxs-lookup"><span data-stu-id="72b27-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="72b27-144">string</span><span class="sxs-lookup"><span data-stu-id="72b27-144">string</span></span> | <span data-ttu-id="72b27-145">Información adicional sobre el evento en el formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="72b27-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="72b27-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="72b27-146">Related topics</span></span>
- [<span data-ttu-id="72b27-147">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="72b27-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="72b27-148">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="72b27-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="72b27-149">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="72b27-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="72b27-150">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="72b27-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="72b27-151">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="72b27-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="72b27-152">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="72b27-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
