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
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794236"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="d6ef2-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="d6ef2-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="d6ef2-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d6ef2-105">**Applies to:**</span></span>
- <span data-ttu-id="d6ef2-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ef2-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d6ef2-107">Use la `AssignedIPAddresses()` función para obtener rápidamente las direcciones IP más recientes que se han asignado a un dispositivo o las direcciones IP más recientes desde un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="d6ef2-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="d6ef2-108">Esta función devuelve una tabla con las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="d6ef2-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="d6ef2-109">Columna</span><span class="sxs-lookup"><span data-stu-id="d6ef2-109">Column</span></span> | <span data-ttu-id="d6ef2-110">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d6ef2-110">Data type</span></span> | <span data-ttu-id="d6ef2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6ef2-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="d6ef2-112">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d6ef2-112">Timestamp</span></span> | <span data-ttu-id="d6ef2-113">datetime</span><span class="sxs-lookup"><span data-stu-id="d6ef2-113">datetime</span></span> | <span data-ttu-id="d6ef2-114">La última hora a la que se observó el dispositivo con la dirección IP</span><span class="sxs-lookup"><span data-stu-id="d6ef2-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="d6ef2-115">IPAddress</span><span class="sxs-lookup"><span data-stu-id="d6ef2-115">IPAddress</span></span> | <span data-ttu-id="d6ef2-116">string</span><span class="sxs-lookup"><span data-stu-id="d6ef2-116">string</span></span> | <span data-ttu-id="d6ef2-117">Dirección IP usada por el dispositivo</span><span class="sxs-lookup"><span data-stu-id="d6ef2-117">IP address used by the device</span></span> |
| <span data-ttu-id="d6ef2-118">IPType</span><span class="sxs-lookup"><span data-stu-id="d6ef2-118">IPType</span></span> | <span data-ttu-id="d6ef2-119">string</span><span class="sxs-lookup"><span data-stu-id="d6ef2-119">string</span></span> | <span data-ttu-id="d6ef2-120">Indica si la dirección IP es una dirección pública o privada</span><span class="sxs-lookup"><span data-stu-id="d6ef2-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="d6ef2-121">NetworkAdapterType</span><span class="sxs-lookup"><span data-stu-id="d6ef2-121">NetworkAdapterType</span></span> | <span data-ttu-id="d6ef2-122">int</span><span class="sxs-lookup"><span data-stu-id="d6ef2-122">int</span></span> | <span data-ttu-id="d6ef2-123">Tipo de adaptador de red usado por el dispositivo al que se ha asignado la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="d6ef2-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="d6ef2-124">Para obtener los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) .</span><span class="sxs-lookup"><span data-stu-id="d6ef2-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="d6ef2-125">ConnectedNetworks</span><span class="sxs-lookup"><span data-stu-id="d6ef2-125">ConnectedNetworks</span></span> | <span data-ttu-id="d6ef2-126">int</span><span class="sxs-lookup"><span data-stu-id="d6ef2-126">int</span></span> | <span data-ttu-id="d6ef2-127">Redes a las que está conectado el adaptador con la dirección IP asignada.</span><span class="sxs-lookup"><span data-stu-id="d6ef2-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="d6ef2-128">Cada matriz JSON contiene el nombre de red, la categoría (pública, privada o de dominio), una descripción y una marca que indica si está conectado públicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="d6ef2-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="d6ef2-129">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6ef2-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="d6ef2-130">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d6ef2-130">Arguments</span></span>

- <span data-ttu-id="d6ef2-131">**x** — `DeviceId` o `DeviceName` valor que identifica el dispositivo</span><span class="sxs-lookup"><span data-stu-id="d6ef2-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="d6ef2-132">**y** : `Timestamp` (DateTime) valor que indica el punto específico en el tiempo en el que se obtienen las direcciones IP más recientes.</span><span class="sxs-lookup"><span data-stu-id="d6ef2-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="d6ef2-133">Si no se especifica, la función devuelve las direcciones IP más recientes.</span><span class="sxs-lookup"><span data-stu-id="d6ef2-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="d6ef2-134">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d6ef2-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="d6ef2-135">Obtener la lista de direcciones IP que usa un dispositivo hace 24 horas</span><span class="sxs-lookup"><span data-stu-id="d6ef2-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="d6ef2-136">Obtener las direcciones IP usadas por un dispositivo y buscar dispositivos que se comunican con ella</span><span class="sxs-lookup"><span data-stu-id="d6ef2-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="d6ef2-137">Esta consulta usa la `AssignedIPAddresses()` función para obtener las direcciones IP asignadas para el dispositivo ( `example-device-name` ) en o antes de una fecha específica ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="d6ef2-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="d6ef2-138">A continuación, usa las direcciones IP para buscar conexiones al dispositivo Iniciado por otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d6ef2-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="d6ef2-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d6ef2-139">Related topics</span></span>
- [<span data-ttu-id="d6ef2-140">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="d6ef2-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d6ef2-141">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="d6ef2-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d6ef2-142">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="d6ef2-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)