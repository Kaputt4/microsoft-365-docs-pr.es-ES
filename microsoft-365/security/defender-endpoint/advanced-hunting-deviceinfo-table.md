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
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075104"
---
# <a name="deviceinfo"></a><span data-ttu-id="60987-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="60987-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="60987-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="60987-105">**Applies to:**</span></span>
- [<span data-ttu-id="60987-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="60987-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="60987-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="60987-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="60987-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="60987-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="60987-109">La tabla del esquema de búsqueda avanzada contiene información sobre los dispositivos de la organización, incluida su versión del sistema operativo, los `DeviceInfo` usuarios activos y el nombre del equipo. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="60987-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="60987-110">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="60987-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="60987-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="60987-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="60987-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="60987-112">Column name</span></span> | <span data-ttu-id="60987-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="60987-113">Data type</span></span> | <span data-ttu-id="60987-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="60987-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="60987-115">datetime</span><span class="sxs-lookup"><span data-stu-id="60987-115">datetime</span></span> | <span data-ttu-id="60987-116">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="60987-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="60987-117">cadena</span><span class="sxs-lookup"><span data-stu-id="60987-117">string</span></span> | <span data-ttu-id="60987-118">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="60987-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="60987-119">string</span><span class="sxs-lookup"><span data-stu-id="60987-119">string</span></span> | <span data-ttu-id="60987-120">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="60987-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="60987-121">string</span><span class="sxs-lookup"><span data-stu-id="60987-121">string</span></span> | <span data-ttu-id="60987-122">Versión del agente de punto de conexión o sensor que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="60987-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="60987-123">string</span><span class="sxs-lookup"><span data-stu-id="60987-123">string</span></span> | <span data-ttu-id="60987-124">Dirección IP pública usada por el dispositivo incorporado para conectarse al servicio Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="60987-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="60987-125">Podría ser la dirección IP del propio dispositivo, un dispositivo NAT o un proxy</span><span class="sxs-lookup"><span data-stu-id="60987-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="60987-126">string</span><span class="sxs-lookup"><span data-stu-id="60987-126">string</span></span> | <span data-ttu-id="60987-127">Arquitectura del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="60987-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="60987-128">string</span><span class="sxs-lookup"><span data-stu-id="60987-128">string</span></span> | <span data-ttu-id="60987-129">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60987-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="60987-130">Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7</span><span class="sxs-lookup"><span data-stu-id="60987-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="60987-131">string</span><span class="sxs-lookup"><span data-stu-id="60987-131">string</span></span> | <span data-ttu-id="60987-132">Versión de compilación del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="60987-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="60987-133">boolean</span><span class="sxs-lookup"><span data-stu-id="60987-133">boolean</span></span> | <span data-ttu-id="60987-134">Indicador booleano de si el dispositivo está unido a Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="60987-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="60987-135">string</span><span class="sxs-lookup"><span data-stu-id="60987-135">string</span></span> | <span data-ttu-id="60987-136">Lista de todos los usuarios que han iniciado sesión en el dispositivo en el momento del evento en formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="60987-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="60987-137">string</span><span class="sxs-lookup"><span data-stu-id="60987-137">string</span></span> | <span data-ttu-id="60987-138">Etiqueta de dispositivo agregada a través del Registro</span><span class="sxs-lookup"><span data-stu-id="60987-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="60987-139">largo</span><span class="sxs-lookup"><span data-stu-id="60987-139">long</span></span> | <span data-ttu-id="60987-140">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="60987-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="60987-141">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp</span><span class="sxs-lookup"><span data-stu-id="60987-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="60987-142">string</span><span class="sxs-lookup"><span data-stu-id="60987-142">string</span></span> | <span data-ttu-id="60987-143">Versión del sistema operativo que se ejecuta en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="60987-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="60987-144">string</span><span class="sxs-lookup"><span data-stu-id="60987-144">string</span></span> | <span data-ttu-id="60987-145">Grupo de máquinas de la máquina.</span><span class="sxs-lookup"><span data-stu-id="60987-145">Machine group of the machine.</span></span> <span data-ttu-id="60987-146">Este grupo lo usa el control de acceso basado en roles para determinar el acceso a la máquina</span><span class="sxs-lookup"><span data-stu-id="60987-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="60987-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="60987-147">Related topics</span></span>
- [<span data-ttu-id="60987-148">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="60987-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="60987-149">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="60987-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="60987-150">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="60987-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
