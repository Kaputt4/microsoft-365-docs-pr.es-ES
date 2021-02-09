---
title: Tabla DeviceInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre el sistema operativo, el nombre del equipo y otra información de máquina en la tabla DeviceInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machineinfo, DeviceInfo, dispositivo, máquina, sistema operativo, plataforma, usuarios
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
ms.openlocfilehash: 6462096a6c1b44ee11299f652a54f261d0355523
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145372"
---
# <a name="deviceinfo"></a><span data-ttu-id="81f13-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="81f13-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="81f13-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="81f13-105">**Applies to:**</span></span>
- <span data-ttu-id="81f13-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81f13-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="81f13-107">La tabla del esquema de búsqueda avanzada contiene información acerca de las máquinas de la organización, incluida la versión del sistema operativo, los usuarios `DeviceInfo` activos y el nombre del equipo. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="81f13-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="81f13-108">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="81f13-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="81f13-109">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="81f13-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="81f13-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="81f13-110">Column name</span></span> | <span data-ttu-id="81f13-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="81f13-111">Data type</span></span> | <span data-ttu-id="81f13-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="81f13-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="81f13-113">datetime</span><span class="sxs-lookup"><span data-stu-id="81f13-113">datetime</span></span> | <span data-ttu-id="81f13-114">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="81f13-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="81f13-115">cadena</span><span class="sxs-lookup"><span data-stu-id="81f13-115">string</span></span> | <span data-ttu-id="81f13-116">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="81f13-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="81f13-117">cadena</span><span class="sxs-lookup"><span data-stu-id="81f13-117">string</span></span> | <span data-ttu-id="81f13-118">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="81f13-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="81f13-119">cadena</span><span class="sxs-lookup"><span data-stu-id="81f13-119">string</span></span> | <span data-ttu-id="81f13-120">Versión del agente de extremo o sensor que se ejecuta en la máquina</span><span class="sxs-lookup"><span data-stu-id="81f13-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="81f13-121">string</span><span class="sxs-lookup"><span data-stu-id="81f13-121">string</span></span> | <span data-ttu-id="81f13-122">Dirección IP pública usada por el equipo incorporado para conectarse al servicio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="81f13-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="81f13-123">Podría ser la dirección IP del propio equipo, un dispositivo NAT o un proxy.</span><span class="sxs-lookup"><span data-stu-id="81f13-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="81f13-124">cadena</span><span class="sxs-lookup"><span data-stu-id="81f13-124">string</span></span> | <span data-ttu-id="81f13-125">Arquitectura del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="81f13-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="81f13-126">cadena</span><span class="sxs-lookup"><span data-stu-id="81f13-126">string</span></span> | <span data-ttu-id="81f13-127">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="81f13-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="81f13-128">Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7</span><span class="sxs-lookup"><span data-stu-id="81f13-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="81f13-129">string</span><span class="sxs-lookup"><span data-stu-id="81f13-129">string</span></span> | <span data-ttu-id="81f13-130">Versión de compilación del sistema operativo que se ejecuta en el equipo</span><span class="sxs-lookup"><span data-stu-id="81f13-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="81f13-131">boolean</span><span class="sxs-lookup"><span data-stu-id="81f13-131">boolean</span></span> | <span data-ttu-id="81f13-132">Indicador booleano de si la máquina está unida a Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="81f13-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `DeviceObjectId` | <span data-ttu-id="81f13-133">string</span><span class="sxs-lookup"><span data-stu-id="81f13-133">string</span></span> | <span data-ttu-id="81f13-134">Identificador único del dispositivo en Azure AD</span><span class="sxs-lookup"><span data-stu-id="81f13-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="81f13-135">string</span><span class="sxs-lookup"><span data-stu-id="81f13-135">string</span></span> | <span data-ttu-id="81f13-136">Lista de todos los usuarios que han iniciado sesión en el equipo en el momento del evento en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="81f13-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="81f13-137">string</span><span class="sxs-lookup"><span data-stu-id="81f13-137">string</span></span> | <span data-ttu-id="81f13-138">Etiqueta de máquina agregada a través del Registro</span><span class="sxs-lookup"><span data-stu-id="81f13-138">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="81f13-139">largo</span><span class="sxs-lookup"><span data-stu-id="81f13-139">long</span></span> | <span data-ttu-id="81f13-140">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="81f13-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="81f13-141">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp</span><span class="sxs-lookup"><span data-stu-id="81f13-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="81f13-142">string</span><span class="sxs-lookup"><span data-stu-id="81f13-142">string</span></span> | <span data-ttu-id="81f13-143">Información adicional sobre el evento en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="81f13-143">Additional information about the event in JSON array format</span></span> |
| `OSVersion` | <span data-ttu-id="81f13-144">cadena</span><span class="sxs-lookup"><span data-stu-id="81f13-144">string</span></span> | <span data-ttu-id="81f13-145">Versión del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="81f13-145">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="81f13-146">cadena</span><span class="sxs-lookup"><span data-stu-id="81f13-146">string</span></span> | <span data-ttu-id="81f13-147">Grupo de máquinas de la máquina.</span><span class="sxs-lookup"><span data-stu-id="81f13-147">Machine group of the machine.</span></span> <span data-ttu-id="81f13-148">Este grupo lo usa el control de acceso basado en roles para determinar el acceso a la máquina.</span><span class="sxs-lookup"><span data-stu-id="81f13-148">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="81f13-149">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="81f13-149">Related topics</span></span>
- [<span data-ttu-id="81f13-150">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="81f13-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="81f13-151">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="81f13-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="81f13-152">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="81f13-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="81f13-153">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="81f13-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="81f13-154">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="81f13-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="81f13-155">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="81f13-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
