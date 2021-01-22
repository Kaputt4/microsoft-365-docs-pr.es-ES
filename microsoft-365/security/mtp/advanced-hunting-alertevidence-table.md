---
title: Tabla AlertEvidence en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada a las alertas en la tabla AlertEvidence del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, máquina, usuario, cuenta
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
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932315"
---
# <a name="alertevidence"></a><span data-ttu-id="c118a-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="c118a-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c118a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c118a-105">**Applies to:**</span></span>
- <span data-ttu-id="c118a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c118a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c118a-107">La tabla del esquema de búsqueda avanzada contiene información sobre diversas entidades (archivos, direcciones IP, direcciones URL, usuarios o dispositivos) asociadas con alertas de Microsoft Defender para Endpoint, Microsoft Defender para `AlertEvidence` Office 365, Microsoft Cloud App Security y Microsoft Defender para Identidad. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c118a-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="c118a-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="c118a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c118a-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c118a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c118a-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="c118a-110">Column name</span></span> | <span data-ttu-id="c118a-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c118a-111">Data type</span></span> | <span data-ttu-id="c118a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c118a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c118a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c118a-113">datetime</span></span> | <span data-ttu-id="c118a-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="c118a-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="c118a-115">string</span><span class="sxs-lookup"><span data-stu-id="c118a-115">string</span></span> | <span data-ttu-id="c118a-116">Identificador único de alerta.</span><span class="sxs-lookup"><span data-stu-id="c118a-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="c118a-117">string</span><span class="sxs-lookup"><span data-stu-id="c118a-117">string</span></span> | <span data-ttu-id="c118a-118">Producto o servicio que proporcionaba la información de alerta</span><span class="sxs-lookup"><span data-stu-id="c118a-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="c118a-119">string</span><span class="sxs-lookup"><span data-stu-id="c118a-119">string</span></span> | <span data-ttu-id="c118a-120">Tipo de objeto, como un archivo, un proceso, un dispositivo o un usuario</span><span class="sxs-lookup"><span data-stu-id="c118a-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="c118a-121">string</span><span class="sxs-lookup"><span data-stu-id="c118a-121">string</span></span> | <span data-ttu-id="c118a-122">Cómo participa la entidad en una alerta, indicando si está afectada o simplemente relacionada</span><span class="sxs-lookup"><span data-stu-id="c118a-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="c118a-123">string</span><span class="sxs-lookup"><span data-stu-id="c118a-123">string</span></span> | <span data-ttu-id="c118a-124">Indica si la entidad es el origen o el destino de una conexión de red</span><span class="sxs-lookup"><span data-stu-id="c118a-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="c118a-125">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-125">string</span></span> | <span data-ttu-id="c118a-126">Nombre del archivo donde se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="c118a-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="c118a-127">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-127">string</span></span> | <span data-ttu-id="c118a-128">Carpeta que contiene el archivo al que se aplicó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="c118a-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="c118a-129">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-129">string</span></span> | <span data-ttu-id="c118a-130">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="c118a-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="c118a-131">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-131">string</span></span> | <span data-ttu-id="c118a-132">SHA-256 del archivo donde se aplicó la acción registrada.</span><span class="sxs-lookup"><span data-stu-id="c118a-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="c118a-133">Este campo normalmente no se rellena; use la columna SHA1 cuando esté disponible.</span><span class="sxs-lookup"><span data-stu-id="c118a-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="c118a-134">entero</span><span class="sxs-lookup"><span data-stu-id="c118a-134">int</span></span> | <span data-ttu-id="c118a-135">Tamaño del archivo en bytes</span><span class="sxs-lookup"><span data-stu-id="c118a-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="c118a-136">string</span><span class="sxs-lookup"><span data-stu-id="c118a-136">string</span></span> | <span data-ttu-id="c118a-137">Familia de malware en la que se ha clasificado el archivo o proceso sospechoso o malintencionado</span><span class="sxs-lookup"><span data-stu-id="c118a-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="c118a-138">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-138">string</span></span> | <span data-ttu-id="c118a-139">Dirección IP a la que se ha conectado</span><span class="sxs-lookup"><span data-stu-id="c118a-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="c118a-140">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-140">string</span></span> | <span data-ttu-id="c118a-141">La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado.</span><span class="sxs-lookup"><span data-stu-id="c118a-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="c118a-142">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-142">string</span></span> | <span data-ttu-id="c118a-143">Nombre de usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="c118a-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c118a-144">string</span><span class="sxs-lookup"><span data-stu-id="c118a-144">string</span></span> | <span data-ttu-id="c118a-145">Dominio de la cuenta</span><span class="sxs-lookup"><span data-stu-id="c118a-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="c118a-146">string</span><span class="sxs-lookup"><span data-stu-id="c118a-146">string</span></span> | <span data-ttu-id="c118a-147">Identificador de seguridad (SID) de la cuenta</span><span class="sxs-lookup"><span data-stu-id="c118a-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="c118a-148">string</span><span class="sxs-lookup"><span data-stu-id="c118a-148">string</span></span> | <span data-ttu-id="c118a-149">Identificador único de la cuenta en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c118a-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="c118a-150">string</span><span class="sxs-lookup"><span data-stu-id="c118a-150">string</span></span> | <span data-ttu-id="c118a-151">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="c118a-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c118a-152">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-152">string</span></span> | <span data-ttu-id="c118a-153">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="c118a-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="c118a-154">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-154">string</span></span> | <span data-ttu-id="c118a-155">Dirección IP asignada al dispositivo local usado durante la comunicación</span><span class="sxs-lookup"><span data-stu-id="c118a-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="c118a-156">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-156">string</span></span> | <span data-ttu-id="c118a-157">Identificador único de correo electrónico, generado por Office 365</span><span class="sxs-lookup"><span data-stu-id="c118a-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="c118a-158">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-158">string</span></span> | <span data-ttu-id="c118a-159">Asunto del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c118a-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="c118a-160">cadena</span><span class="sxs-lookup"><span data-stu-id="c118a-160">string</span></span> | <span data-ttu-id="c118a-161">Identificador único de la aplicación</span><span class="sxs-lookup"><span data-stu-id="c118a-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="c118a-162">string</span><span class="sxs-lookup"><span data-stu-id="c118a-162">string</span></span> | <span data-ttu-id="c118a-163">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="c118a-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="c118a-164">string</span><span class="sxs-lookup"><span data-stu-id="c118a-164">string</span></span> | <span data-ttu-id="c118a-165">Línea de comandos usada para crear el nuevo proceso</span><span class="sxs-lookup"><span data-stu-id="c118a-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="c118a-166">string</span><span class="sxs-lookup"><span data-stu-id="c118a-166">string</span></span> | <span data-ttu-id="c118a-167">Información adicional sobre el evento en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="c118a-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c118a-168">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c118a-168">Related topics</span></span>
- [<span data-ttu-id="c118a-169">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="c118a-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c118a-170">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="c118a-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c118a-171">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="c118a-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c118a-172">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="c118a-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c118a-173">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="c118a-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c118a-174">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="c118a-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
