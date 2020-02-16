---
title: Tabla DeviceInfo en el esquema de búsqueda avanzada
description: Información sobre el sistema operativo, el nombre del equipo y otros datos del equipo en la tabla DeviceInfo del esquema de búsqueda avanzada
keywords: caza avanzado, cazar amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machineinfo, DeviceInfo, dispositivo, máquina, so, plataforma , los usuarios
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
ms.openlocfilehash: 58fd70ce62fc2e15f703063d1f8efe62df02c57d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087979"
---
# <a name="deviceinfo"></a><span data-ttu-id="e5808-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="e5808-104">DeviceInfo</span></span>

<span data-ttu-id="e5808-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e5808-105">**Applies to:**</span></span>
- <span data-ttu-id="e5808-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5808-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e5808-107">La `DeviceInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los equipos de la organización, incluida la versión del sistema operativo, los usuarios activos y el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="e5808-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="e5808-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="e5808-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e5808-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e5808-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e5808-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="e5808-110">Column name</span></span> | <span data-ttu-id="e5808-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e5808-111">Data type</span></span> | <span data-ttu-id="e5808-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5808-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e5808-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e5808-113">datetime</span></span> | <span data-ttu-id="e5808-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="e5808-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e5808-115">string</span><span class="sxs-lookup"><span data-stu-id="e5808-115">string</span></span> | <span data-ttu-id="e5808-116">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="e5808-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e5808-117">string</span><span class="sxs-lookup"><span data-stu-id="e5808-117">string</span></span> | <span data-ttu-id="e5808-118">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="e5808-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="e5808-119">string</span><span class="sxs-lookup"><span data-stu-id="e5808-119">string</span></span> | <span data-ttu-id="e5808-120">Versión del agente de extremo o del sensor que se ejecuta en el equipo</span><span class="sxs-lookup"><span data-stu-id="e5808-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="e5808-121">string</span><span class="sxs-lookup"><span data-stu-id="e5808-121">string</span></span> | <span data-ttu-id="e5808-122">Dirección IP pública usada por el equipo incorporado para conectarse al servicio ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="e5808-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="e5808-123">Podría ser la dirección IP del equipo, un dispositivo NAT o un proxy</span><span class="sxs-lookup"><span data-stu-id="e5808-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="e5808-124">string</span><span class="sxs-lookup"><span data-stu-id="e5808-124">string</span></span> | <span data-ttu-id="e5808-125">Arquitectura del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e5808-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="e5808-126">cadena</span><span class="sxs-lookup"><span data-stu-id="e5808-126">string</span></span> | <span data-ttu-id="e5808-127">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e5808-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="e5808-128">Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="e5808-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="e5808-129">string</span><span class="sxs-lookup"><span data-stu-id="e5808-129">string</span></span> | <span data-ttu-id="e5808-130">Versión de compilación del sistema operativo que se ejecuta en el equipo</span><span class="sxs-lookup"><span data-stu-id="e5808-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="e5808-131">boolean</span><span class="sxs-lookup"><span data-stu-id="e5808-131">boolean</span></span> | <span data-ttu-id="e5808-132">Indicador booleano de si el equipo está unido a Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e5808-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="e5808-133">string</span><span class="sxs-lookup"><span data-stu-id="e5808-133">string</span></span> | <span data-ttu-id="e5808-134">Lista de todos los usuarios que han iniciado sesión en el equipo en el momento del evento en el formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="e5808-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="e5808-135">string</span><span class="sxs-lookup"><span data-stu-id="e5808-135">string</span></span> | <span data-ttu-id="e5808-136">Etiqueta de máquina agregada a través del registro</span><span class="sxs-lookup"><span data-stu-id="e5808-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="e5808-137">largo</span><span class="sxs-lookup"><span data-stu-id="e5808-137">long</span></span> | <span data-ttu-id="e5808-138">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="e5808-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e5808-139">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp.</span><span class="sxs-lookup"><span data-stu-id="e5808-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="e5808-140">string</span><span class="sxs-lookup"><span data-stu-id="e5808-140">string</span></span> | <span data-ttu-id="e5808-141">Versión del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e5808-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="e5808-142">string</span><span class="sxs-lookup"><span data-stu-id="e5808-142">string</span></span> | <span data-ttu-id="e5808-143">Grupo de máquinas del equipo.</span><span class="sxs-lookup"><span data-stu-id="e5808-143">Machine group of the machine.</span></span> <span data-ttu-id="e5808-144">El control de acceso basado en roles usa este grupo para determinar el acceso al equipo</span><span class="sxs-lookup"><span data-stu-id="e5808-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e5808-145">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e5808-145">Related topics</span></span>
- [<span data-ttu-id="e5808-146">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="e5808-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e5808-147">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="e5808-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e5808-148">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="e5808-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e5808-149">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="e5808-149">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e5808-150">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="e5808-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e5808-151">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="e5808-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
