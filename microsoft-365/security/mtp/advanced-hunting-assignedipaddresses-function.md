---
title: La función AssignedIPAddresses () en la caza avanzada para la protección contra amenazas de Microsoft
description: Obtenga información sobre cómo usar la función AssignedIPAddresses () para obtener las direcciones IP más recientes asignadas a un dispositivo.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.openlocfilehash: 685132e3f5c303f21fde3702725a84e24383e679
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198252"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="e0d1e-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="e0d1e-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e0d1e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e0d1e-105">**Applies to:**</span></span>
- <span data-ttu-id="e0d1e-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0d1e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e0d1e-107">Use la `AssignedIPAddresses()` función para obtener rápidamente las direcciones IP más recientes que se han asignado a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e0d1e-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="e0d1e-108">Si especifica un argumento timestamp, esta función obtiene las direcciones IP más recientes a la hora especificada.</span><span class="sxs-lookup"><span data-stu-id="e0d1e-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="e0d1e-109">Esta función devuelve una tabla con las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="e0d1e-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="e0d1e-110">Columna</span><span class="sxs-lookup"><span data-stu-id="e0d1e-110">Column</span></span> | <span data-ttu-id="e0d1e-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e0d1e-111">Data type</span></span> | <span data-ttu-id="e0d1e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0d1e-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="e0d1e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e0d1e-113">datetime</span></span> | <span data-ttu-id="e0d1e-114">La última hora a la que se observó el dispositivo con la dirección IP</span><span class="sxs-lookup"><span data-stu-id="e0d1e-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="e0d1e-115">string</span><span class="sxs-lookup"><span data-stu-id="e0d1e-115">string</span></span> | <span data-ttu-id="e0d1e-116">Dirección IP usada por el dispositivo</span><span class="sxs-lookup"><span data-stu-id="e0d1e-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="e0d1e-117">string</span><span class="sxs-lookup"><span data-stu-id="e0d1e-117">string</span></span> | <span data-ttu-id="e0d1e-118">Indica si la dirección IP es una dirección pública o privada</span><span class="sxs-lookup"><span data-stu-id="e0d1e-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="e0d1e-119">entero</span><span class="sxs-lookup"><span data-stu-id="e0d1e-119">int</span></span> | <span data-ttu-id="e0d1e-120">Tipo de adaptador de red usado por el dispositivo al que se ha asignado la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="e0d1e-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="e0d1e-121">Para obtener los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) .</span><span class="sxs-lookup"><span data-stu-id="e0d1e-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="e0d1e-122">entero</span><span class="sxs-lookup"><span data-stu-id="e0d1e-122">int</span></span> | <span data-ttu-id="e0d1e-123">Redes a las que está conectado el adaptador con la dirección IP asignada.</span><span class="sxs-lookup"><span data-stu-id="e0d1e-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="e0d1e-124">Cada matriz JSON contiene el nombre de red, la categoría (pública, privada o de dominio), una descripción y una marca que indica si está conectado públicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="e0d1e-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="e0d1e-125">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0d1e-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="e0d1e-126">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e0d1e-126">Arguments</span></span>

- <span data-ttu-id="e0d1e-127">**x**— `DeviceId` o `DeviceName` valor que identifica el dispositivo</span><span class="sxs-lookup"><span data-stu-id="e0d1e-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="e0d1e-128">**y**: `Timestamp` (DateTime) que indica a la función que debe obtener las direcciones IP asignadas más recientemente de una hora específica.</span><span class="sxs-lookup"><span data-stu-id="e0d1e-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="e0d1e-129">Si no se especifica, la función devuelve las direcciones IP más recientes.</span><span class="sxs-lookup"><span data-stu-id="e0d1e-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="e0d1e-130">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e0d1e-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="e0d1e-131">Obtener la lista de direcciones IP que usa un dispositivo hace 24 horas</span><span class="sxs-lookup"><span data-stu-id="e0d1e-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="e0d1e-132">Obtener las direcciones IP usadas por un dispositivo y buscar dispositivos que se comunican con ella</span><span class="sxs-lookup"><span data-stu-id="e0d1e-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="e0d1e-133">Esta consulta usa la `AssignedIPAddresses()` función para obtener las direcciones IP asignadas para el dispositivo ( `example-device-name` ) en o antes de una fecha específica ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="e0d1e-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="e0d1e-134">A continuación, usa las direcciones IP para buscar conexiones al dispositivo Iniciado por otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e0d1e-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a><span data-ttu-id="e0d1e-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e0d1e-135">Related topics</span></span>
- [<span data-ttu-id="e0d1e-136">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="e0d1e-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e0d1e-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="e0d1e-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e0d1e-138">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="e0d1e-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
