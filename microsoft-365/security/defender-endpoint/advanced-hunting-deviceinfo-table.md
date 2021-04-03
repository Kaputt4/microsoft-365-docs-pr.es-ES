---
title: Tabla DeviceInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre el sistema operativo, el nombre del equipo y otra información del dispositivo en la tabla DeviceInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, deviceinfo, dispositivo, sistema operativo, plataforma, usuarios, DeviceInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500829"
---
# <a name="deviceinfo"></a><span data-ttu-id="539fa-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="539fa-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="539fa-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="539fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="539fa-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="539fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="539fa-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="539fa-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="539fa-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="539fa-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="539fa-109">La tabla del esquema de búsqueda avanzada contiene información sobre los dispositivos de la organización, incluida su versión del sistema operativo, los `DeviceInfo` usuarios activos y el nombre del equipo. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="539fa-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="539fa-110">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="539fa-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="539fa-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="539fa-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="539fa-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="539fa-112">Column name</span></span> | <span data-ttu-id="539fa-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="539fa-113">Data type</span></span> | <span data-ttu-id="539fa-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="539fa-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="539fa-115">datetime</span><span class="sxs-lookup"><span data-stu-id="539fa-115">datetime</span></span> | <span data-ttu-id="539fa-116">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="539fa-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="539fa-117">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-117">string</span></span> | <span data-ttu-id="539fa-118">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="539fa-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="539fa-119">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-119">string</span></span> | <span data-ttu-id="539fa-120">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="539fa-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="539fa-121">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-121">string</span></span> | <span data-ttu-id="539fa-122">Versión del agente de punto de conexión o sensor que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="539fa-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="539fa-123">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-123">string</span></span> | <span data-ttu-id="539fa-124">Dirección IP pública usada por el dispositivo incorporado para conectarse al servicio Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="539fa-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="539fa-125">Podría ser la dirección IP del propio dispositivo, un dispositivo NAT o un proxy</span><span class="sxs-lookup"><span data-stu-id="539fa-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="539fa-126">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-126">string</span></span> | <span data-ttu-id="539fa-127">Arquitectura del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="539fa-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="539fa-128">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-128">string</span></span> | <span data-ttu-id="539fa-129">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="539fa-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="539fa-130">Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7</span><span class="sxs-lookup"><span data-stu-id="539fa-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="539fa-131">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-131">string</span></span> | <span data-ttu-id="539fa-132">Versión de compilación del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="539fa-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="539fa-133">boolean</span><span class="sxs-lookup"><span data-stu-id="539fa-133">boolean</span></span> | <span data-ttu-id="539fa-134">Indicador booleano de si el dispositivo está unido a Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="539fa-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="539fa-135">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-135">string</span></span> | <span data-ttu-id="539fa-136">Lista de todos los usuarios que han iniciado sesión en el dispositivo en el momento del evento en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="539fa-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="539fa-137">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-137">string</span></span> | <span data-ttu-id="539fa-138">Etiqueta de dispositivo agregada a través del Registro</span><span class="sxs-lookup"><span data-stu-id="539fa-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="539fa-139">largo</span><span class="sxs-lookup"><span data-stu-id="539fa-139">long</span></span> | <span data-ttu-id="539fa-140">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="539fa-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="539fa-141">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp</span><span class="sxs-lookup"><span data-stu-id="539fa-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="539fa-142">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-142">string</span></span> | <span data-ttu-id="539fa-143">Versión del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="539fa-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="539fa-144">cadena</span><span class="sxs-lookup"><span data-stu-id="539fa-144">string</span></span> | <span data-ttu-id="539fa-145">Grupo de máquinas de la máquina.</span><span class="sxs-lookup"><span data-stu-id="539fa-145">Machine group of the machine.</span></span> <span data-ttu-id="539fa-146">Este grupo lo usa el control de acceso basado en roles para determinar el acceso a la máquina</span><span class="sxs-lookup"><span data-stu-id="539fa-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="539fa-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="539fa-147">Related topics</span></span>
- [<span data-ttu-id="539fa-148">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="539fa-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="539fa-149">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="539fa-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="539fa-150">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="539fa-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
