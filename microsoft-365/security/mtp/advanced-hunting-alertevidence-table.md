---
title: Tabla AlertEvidence en el esquema de búsqueda avanzada
description: Información relacionada con las alertas en la tabla AlertEvidence del esquema de búsqueda avanzada
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430168"
---
# <a name="alertevidence"></a><span data-ttu-id="01c12-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="01c12-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01c12-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="01c12-105">**Applies to:**</span></span>
- <span data-ttu-id="01c12-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="01c12-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="01c12-107">La `AlertEvidence` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre diversas entidades (archivos, direcciones IP, direcciones URL, usuarios o dispositivos) asociadas con alertas de ATP de Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="01c12-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="01c12-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="01c12-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="01c12-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="01c12-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="01c12-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="01c12-110">Column name</span></span> | <span data-ttu-id="01c12-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="01c12-111">Data type</span></span> | <span data-ttu-id="01c12-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="01c12-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="01c12-113">datetime</span><span class="sxs-lookup"><span data-stu-id="01c12-113">datetime</span></span> | <span data-ttu-id="01c12-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="01c12-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="01c12-115">string</span><span class="sxs-lookup"><span data-stu-id="01c12-115">string</span></span> | <span data-ttu-id="01c12-116">Identificador único de alerta.</span><span class="sxs-lookup"><span data-stu-id="01c12-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="01c12-117">string</span><span class="sxs-lookup"><span data-stu-id="01c12-117">string</span></span> | <span data-ttu-id="01c12-118">Producto o servicio que ha proporcionado la información de alerta</span><span class="sxs-lookup"><span data-stu-id="01c12-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="01c12-119">string</span><span class="sxs-lookup"><span data-stu-id="01c12-119">string</span></span> | <span data-ttu-id="01c12-120">Tipo de objeto, como un archivo, un proceso, un dispositivo o un usuario</span><span class="sxs-lookup"><span data-stu-id="01c12-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="01c12-121">string</span><span class="sxs-lookup"><span data-stu-id="01c12-121">string</span></span> | <span data-ttu-id="01c12-122">Cómo interviene la entidad en una alerta, lo que indica si se ve afectada o si simplemente está relacionada.</span><span class="sxs-lookup"><span data-stu-id="01c12-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="01c12-123">string</span><span class="sxs-lookup"><span data-stu-id="01c12-123">string</span></span> | <span data-ttu-id="01c12-124">Indica si la entidad es el origen o el destino de una conexión de red.</span><span class="sxs-lookup"><span data-stu-id="01c12-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="01c12-125">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-125">string</span></span> | <span data-ttu-id="01c12-126">Nombre del archivo donde se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="01c12-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="01c12-127">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-127">string</span></span> | <span data-ttu-id="01c12-128">Carpeta que contiene el archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="01c12-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="01c12-129">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-129">string</span></span> | <span data-ttu-id="01c12-130">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="01c12-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="01c12-131">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-131">string</span></span> | <span data-ttu-id="01c12-132">SHA-256 del archivo donde se aplicó la acción registrada.</span><span class="sxs-lookup"><span data-stu-id="01c12-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="01c12-133">Este campo no suele rellenarse; use la columna SHA1 cuando esté disponible.</span><span class="sxs-lookup"><span data-stu-id="01c12-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="01c12-134">entero</span><span class="sxs-lookup"><span data-stu-id="01c12-134">int</span></span> | <span data-ttu-id="01c12-135">Tamaño del archivo en bytes</span><span class="sxs-lookup"><span data-stu-id="01c12-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="01c12-136">string</span><span class="sxs-lookup"><span data-stu-id="01c12-136">string</span></span> | <span data-ttu-id="01c12-137">Familia de malware en la que el archivo o proceso malintencionado se clasificó en</span><span class="sxs-lookup"><span data-stu-id="01c12-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="01c12-138">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-138">string</span></span> | <span data-ttu-id="01c12-139">Dirección IP a la que se ha conectado</span><span class="sxs-lookup"><span data-stu-id="01c12-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="01c12-140">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-140">string</span></span> | <span data-ttu-id="01c12-141">La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado.</span><span class="sxs-lookup"><span data-stu-id="01c12-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="01c12-142">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-142">string</span></span> | <span data-ttu-id="01c12-143">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="01c12-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="01c12-144">string</span><span class="sxs-lookup"><span data-stu-id="01c12-144">string</span></span> | <span data-ttu-id="01c12-145">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="01c12-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="01c12-146">string</span><span class="sxs-lookup"><span data-stu-id="01c12-146">string</span></span> | <span data-ttu-id="01c12-147">Identificador de seguridad (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="01c12-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="01c12-148">string</span><span class="sxs-lookup"><span data-stu-id="01c12-148">string</span></span> | <span data-ttu-id="01c12-149">Identificador único de la cuenta en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="01c12-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="01c12-150">string</span><span class="sxs-lookup"><span data-stu-id="01c12-150">string</span></span> | <span data-ttu-id="01c12-151">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="01c12-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="01c12-152">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-152">string</span></span> | <span data-ttu-id="01c12-153">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="01c12-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="01c12-154">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-154">string</span></span> | <span data-ttu-id="01c12-155">Dirección IP asignada al dispositivo local que se usa durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="01c12-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="01c12-156">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-156">string</span></span> | <span data-ttu-id="01c12-157">Identificador único de correo electrónico, generado por Office 365</span><span class="sxs-lookup"><span data-stu-id="01c12-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="01c12-158">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-158">string</span></span> | <span data-ttu-id="01c12-159">Asunto del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="01c12-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="01c12-160">cadena</span><span class="sxs-lookup"><span data-stu-id="01c12-160">string</span></span> | <span data-ttu-id="01c12-161">Identificador único de la aplicación</span><span class="sxs-lookup"><span data-stu-id="01c12-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="01c12-162">string</span><span class="sxs-lookup"><span data-stu-id="01c12-162">string</span></span> | <span data-ttu-id="01c12-163">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="01c12-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="01c12-164">string</span><span class="sxs-lookup"><span data-stu-id="01c12-164">string</span></span> | <span data-ttu-id="01c12-165">Línea de comandos usada para crear el nuevo proceso</span><span class="sxs-lookup"><span data-stu-id="01c12-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="01c12-166">string</span><span class="sxs-lookup"><span data-stu-id="01c12-166">string</span></span> | <span data-ttu-id="01c12-167">Información adicional sobre el evento en el formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="01c12-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="01c12-168">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="01c12-168">Related topics</span></span>
- [<span data-ttu-id="01c12-169">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="01c12-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="01c12-170">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="01c12-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="01c12-171">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="01c12-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="01c12-172">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="01c12-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="01c12-173">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="01c12-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="01c12-174">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="01c12-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
