---
title: Función AssignedIPAddresses() en búsqueda avanzada para Microsoft Defender para endpoint
description: Obtenga información sobre cómo usar la función AssignedIPAddresses() para obtener las direcciones IP más recientes asignadas a un dispositivo
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, ATP de Microsoft Defender, Microsoft Defender para endpoint, Windows Defender, WINDOWS DEFENDER ATP, protección contra amenazas avanzada de Windows Defender, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 08ab7ff5bac917a027e4380a46ab1cb2cf0a1312
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072435"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="68244-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="68244-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

><span data-ttu-id="68244-105">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="68244-105">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="68244-106">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="68244-106">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="68244-107">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="68244-107">**Applies to:**</span></span>
- [<span data-ttu-id="68244-108">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="68244-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="68244-109">Usa la función de las consultas de búsqueda avanzadas para obtener rápidamente las direcciones IP más recientes que se han `AssignedIPAddresses()` asignado a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68244-109">Use the `AssignedIPAddresses()` function in your advanced hunting queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="68244-110">Si especifica un argumento de marca de tiempo, esta función obtiene las direcciones IP más recientes en el momento especificado.</span><span class="sxs-lookup"><span data-stu-id="68244-110">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span>

<span data-ttu-id="68244-111">Esta función devuelve una tabla con las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="68244-111">This function returns a table with the following columns:</span></span>

<span data-ttu-id="68244-112">Column</span><span class="sxs-lookup"><span data-stu-id="68244-112">Column</span></span> | <span data-ttu-id="68244-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="68244-113">Data type</span></span> | <span data-ttu-id="68244-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="68244-114">Description</span></span>
-|-|-
`Timestamp` | <span data-ttu-id="68244-115">datetime</span><span class="sxs-lookup"><span data-stu-id="68244-115">datetime</span></span> | <span data-ttu-id="68244-116">Última hora en la que se observó el dispositivo con la dirección IP</span><span class="sxs-lookup"><span data-stu-id="68244-116">Latest time when the device was observed using the IP address</span></span>
`IPAddress` | <span data-ttu-id="68244-117">string</span><span class="sxs-lookup"><span data-stu-id="68244-117">string</span></span> | <span data-ttu-id="68244-118">Dirección IP usada por el dispositivo</span><span class="sxs-lookup"><span data-stu-id="68244-118">IP address used by the device</span></span>
`IPType` | <span data-ttu-id="68244-119">string</span><span class="sxs-lookup"><span data-stu-id="68244-119">string</span></span> | <span data-ttu-id="68244-120">Indica si la dirección IP es una dirección pública o privada</span><span class="sxs-lookup"><span data-stu-id="68244-120">Indicates whether the IP address is a public or private address</span></span>
`NetworkAdapterType` | <span data-ttu-id="68244-121">Entero</span><span class="sxs-lookup"><span data-stu-id="68244-121">int</span></span> | <span data-ttu-id="68244-122">Tipo de adaptador de red usado por el dispositivo al que se ha asignado la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="68244-122">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="68244-123">Para obtener los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="68244-123">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span>
`ConnectedNetworks` | <span data-ttu-id="68244-124">Entero</span><span class="sxs-lookup"><span data-stu-id="68244-124">int</span></span> | <span data-ttu-id="68244-125">Redes a las que está conectado el adaptador con la dirección IP asignada.</span><span class="sxs-lookup"><span data-stu-id="68244-125">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="68244-126">Cada matriz JSON contiene el nombre de red, la categoría (público, privado o dominio), una descripción y una marca que indica si está conectada públicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="68244-126">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span>

## <a name="syntax"></a><span data-ttu-id="68244-127">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68244-127">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="68244-128">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68244-128">Arguments</span></span>

- <span data-ttu-id="68244-129">**x** o `DeviceId` valor que identifica el `DeviceName` dispositivo</span><span class="sxs-lookup"><span data-stu-id="68244-129">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="68244-130">**y:** valor (datetime) que indica a la función que obtenga las direcciones IP asignadas más `Timestamp` recientes a partir de una hora específica.</span><span class="sxs-lookup"><span data-stu-id="68244-130">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="68244-131">Si no se especifica, la función devuelve las direcciones IP más recientes.</span><span class="sxs-lookup"><span data-stu-id="68244-131">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="68244-132">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="68244-132">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="68244-133">Obtener la lista de direcciones IP usadas por un dispositivo hace 24 horas</span><span class="sxs-lookup"><span data-stu-id="68244-133">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="68244-134">Obtener direcciones IP usadas por un dispositivo y buscar dispositivos que se comuniquen con él</span><span class="sxs-lookup"><span data-stu-id="68244-134">Get IP addresses used by a device and find devices communicating with it</span></span>

<span data-ttu-id="68244-135">Esta consulta usa la función para obtener direcciones IP asignadas para el dispositivo ( ) en `AssignedIPAddresses()` o antes de una fecha específica ( `example-device-name` `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="68244-135">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="68244-136">A continuación, usa las direcciones IP para buscar conexiones al dispositivo iniciadas por otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="68244-136">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="68244-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="68244-137">Related topics</span></span>

- [<span data-ttu-id="68244-138">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="68244-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="68244-139">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="68244-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="68244-140">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="68244-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
