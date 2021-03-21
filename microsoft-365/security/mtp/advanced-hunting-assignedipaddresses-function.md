---
title: Función AssignedIPAddresses() en búsqueda avanzada para Microsoft 365 Defender
description: Obtenga información sobre cómo usar la función AssignedIPAddresses() para obtener las direcciones IP más recientes asignadas a un dispositivo
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.openlocfilehash: c52f7b8bf5a93a75b3330a3377f3fab34b8e7837
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922925"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="f7908-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="f7908-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f7908-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f7908-105">**Applies to:**</span></span>
- <span data-ttu-id="f7908-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7908-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f7908-107">Usa la función de las consultas de búsqueda avanzadas para obtener rápidamente las direcciones IP más recientes que se han `AssignedIPAddresses()` asignado a un dispositivo. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f7908-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="f7908-108">Si especifica un argumento de marca de tiempo, esta función obtiene las direcciones IP más recientes en el momento especificado.</span><span class="sxs-lookup"><span data-stu-id="f7908-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="f7908-109">Esta función devuelve una tabla con las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="f7908-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="f7908-110">Column</span><span class="sxs-lookup"><span data-stu-id="f7908-110">Column</span></span> | <span data-ttu-id="f7908-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f7908-111">Data type</span></span> | <span data-ttu-id="f7908-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7908-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="f7908-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f7908-113">datetime</span></span> | <span data-ttu-id="f7908-114">Última hora en la que se observó el dispositivo con la dirección IP</span><span class="sxs-lookup"><span data-stu-id="f7908-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="f7908-115">string</span><span class="sxs-lookup"><span data-stu-id="f7908-115">string</span></span> | <span data-ttu-id="f7908-116">Dirección IP usada por el dispositivo</span><span class="sxs-lookup"><span data-stu-id="f7908-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="f7908-117">string</span><span class="sxs-lookup"><span data-stu-id="f7908-117">string</span></span> | <span data-ttu-id="f7908-118">Indica si la dirección IP es una dirección pública o privada</span><span class="sxs-lookup"><span data-stu-id="f7908-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="f7908-119">Entero</span><span class="sxs-lookup"><span data-stu-id="f7908-119">int</span></span> | <span data-ttu-id="f7908-120">Tipo de adaptador de red usado por el dispositivo al que se ha asignado la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="f7908-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="f7908-121">Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="f7908-121">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="f7908-122">Entero</span><span class="sxs-lookup"><span data-stu-id="f7908-122">int</span></span> | <span data-ttu-id="f7908-123">Redes a las que está conectado el adaptador con la dirección IP asignada.</span><span class="sxs-lookup"><span data-stu-id="f7908-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="f7908-124">Cada matriz JSON contiene el nombre de red, la categoría (público, privado o dominio), una descripción y una marca que indica si está conectada públicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="f7908-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="f7908-125">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7908-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="f7908-126">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f7908-126">Arguments</span></span>

- <span data-ttu-id="f7908-127">**x** o `DeviceId` valor que identifica el `DeviceName` dispositivo</span><span class="sxs-lookup"><span data-stu-id="f7908-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="f7908-128">**y:** valor (datetime) que indica a la función que obtenga las direcciones IP asignadas más `Timestamp` recientes a partir de una hora específica.</span><span class="sxs-lookup"><span data-stu-id="f7908-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="f7908-129">Si no se especifica, la función devuelve las direcciones IP más recientes.</span><span class="sxs-lookup"><span data-stu-id="f7908-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="f7908-130">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f7908-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="f7908-131">Obtener la lista de direcciones IP usadas por un dispositivo hace 24 horas</span><span class="sxs-lookup"><span data-stu-id="f7908-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="f7908-132">Obtener direcciones IP usadas por un dispositivo y buscar dispositivos que se comuniquen con él</span><span class="sxs-lookup"><span data-stu-id="f7908-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="f7908-133">Esta consulta usa la función para obtener direcciones IP asignadas para el dispositivo ( ) en `AssignedIPAddresses()` o antes de una fecha específica ( `example-device-name` `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="f7908-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="f7908-134">A continuación, usa las direcciones IP para buscar conexiones al dispositivo iniciadas por otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f7908-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="f7908-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f7908-135">Related topics</span></span>
- [<span data-ttu-id="f7908-136">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="f7908-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f7908-137">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="f7908-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f7908-138">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="f7908-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)