---
title: Tabla DeviceInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre el sistema operativo, el nombre del equipo y otra información de máquina en la tabla DeviceInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machineinfo, DeviceInfo, dispositivo, máquina, sistema operativo, plataforma, usuarios
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
ms.openlocfilehash: f97947c2c9f02720facae4f0c3c29ff702416261
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023134"
---
# <a name="deviceinfo"></a><span data-ttu-id="c639f-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="c639f-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c639f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c639f-105">**Applies to:**</span></span>
- <span data-ttu-id="c639f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c639f-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="c639f-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c639f-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="c639f-108">La tabla del esquema de búsqueda avanzada contiene información sobre los dispositivos de la organización, incluida la versión del sistema operativo, los `DeviceInfo` usuarios activos y el nombre del equipo. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c639f-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="c639f-109">Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="c639f-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c639f-110">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c639f-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c639f-111">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="c639f-111">Column name</span></span> | <span data-ttu-id="c639f-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c639f-112">Data type</span></span> | <span data-ttu-id="c639f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c639f-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c639f-114">datetime</span><span class="sxs-lookup"><span data-stu-id="c639f-114">datetime</span></span> | <span data-ttu-id="c639f-115">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="c639f-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c639f-116">cadena</span><span class="sxs-lookup"><span data-stu-id="c639f-116">string</span></span> | <span data-ttu-id="c639f-117">Identificador único para el equipo en servicio</span><span class="sxs-lookup"><span data-stu-id="c639f-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c639f-118">cadena</span><span class="sxs-lookup"><span data-stu-id="c639f-118">string</span></span> | <span data-ttu-id="c639f-119">Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo</span><span class="sxs-lookup"><span data-stu-id="c639f-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="c639f-120">cadena</span><span class="sxs-lookup"><span data-stu-id="c639f-120">string</span></span> | <span data-ttu-id="c639f-121">Versión del agente de punto de conexión o sensor que se ejecuta en la máquina</span><span class="sxs-lookup"><span data-stu-id="c639f-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="c639f-122">string</span><span class="sxs-lookup"><span data-stu-id="c639f-122">string</span></span> | <span data-ttu-id="c639f-123">Dirección IP pública usada por el equipo incorporado para conectarse al servicio de Microsoft Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="c639f-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="c639f-124">Esta podría ser la dirección IP del propio equipo, un dispositivo NAT o un proxy</span><span class="sxs-lookup"><span data-stu-id="c639f-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="c639f-125">cadena</span><span class="sxs-lookup"><span data-stu-id="c639f-125">string</span></span> | <span data-ttu-id="c639f-126">Arquitectura del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c639f-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c639f-127">cadena</span><span class="sxs-lookup"><span data-stu-id="c639f-127">string</span></span> | <span data-ttu-id="c639f-128">Plataforma del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c639f-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c639f-129">Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7</span><span class="sxs-lookup"><span data-stu-id="c639f-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="c639f-130">string</span><span class="sxs-lookup"><span data-stu-id="c639f-130">string</span></span> | <span data-ttu-id="c639f-131">Versión de compilación del sistema operativo que se ejecuta en la máquina</span><span class="sxs-lookup"><span data-stu-id="c639f-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="c639f-132">boolean</span><span class="sxs-lookup"><span data-stu-id="c639f-132">boolean</span></span> | <span data-ttu-id="c639f-133">Indicador booleano de si la máquina está unida a Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c639f-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="c639f-134">string</span><span class="sxs-lookup"><span data-stu-id="c639f-134">string</span></span> | <span data-ttu-id="c639f-135">Identificador único del dispositivo en Azure AD</span><span class="sxs-lookup"><span data-stu-id="c639f-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="c639f-136">string</span><span class="sxs-lookup"><span data-stu-id="c639f-136">string</span></span> | <span data-ttu-id="c639f-137">Lista de todos los usuarios que han iniciado sesión en el equipo en el momento del evento en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="c639f-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="c639f-138">string</span><span class="sxs-lookup"><span data-stu-id="c639f-138">string</span></span> | <span data-ttu-id="c639f-139">Etiqueta de máquina agregada a través del Registro</span><span class="sxs-lookup"><span data-stu-id="c639f-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="c639f-140">cadena</span><span class="sxs-lookup"><span data-stu-id="c639f-140">string</span></span> | <span data-ttu-id="c639f-141">Versión del sistema operativo que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c639f-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="c639f-142">cadena</span><span class="sxs-lookup"><span data-stu-id="c639f-142">string</span></span> | <span data-ttu-id="c639f-143">Grupo de máquinas de la máquina.</span><span class="sxs-lookup"><span data-stu-id="c639f-143">Machine group of the machine.</span></span> <span data-ttu-id="c639f-144">Este grupo lo usa el control de acceso basado en roles para determinar el acceso a la máquina</span><span class="sxs-lookup"><span data-stu-id="c639f-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="c639f-145">largo</span><span class="sxs-lookup"><span data-stu-id="c639f-145">long</span></span> | <span data-ttu-id="c639f-146">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="c639f-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c639f-147">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp</span><span class="sxs-lookup"><span data-stu-id="c639f-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="c639f-148">string</span><span class="sxs-lookup"><span data-stu-id="c639f-148">string</span></span> | <span data-ttu-id="c639f-149">Información adicional sobre el evento en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="c639f-149">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="c639f-150">La tabla proporciona información del dispositivo basada en latidos, que son informes `DeviceInfo` periódicos o señales de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c639f-150">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="c639f-151">Cada quince minutos, el dispositivo envía un latido parcial que contiene atributos que cambian con frecuencia, como `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="c639f-151">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="c639f-152">Una vez al día, se envía un latido completo que contiene los atributos del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c639f-152">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="c639f-153">Puedes usar la siguiente consulta de ejemplo para obtener el estado más reciente de un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c639f-153">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="c639f-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c639f-154">Related topics</span></span>
- [<span data-ttu-id="c639f-155">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="c639f-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c639f-156">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="c639f-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c639f-157">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="c639f-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c639f-158">Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades</span><span class="sxs-lookup"><span data-stu-id="c639f-158">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c639f-159">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="c639f-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c639f-160">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="c639f-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
