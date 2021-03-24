---
title: Función DeviceFromIP() en búsqueda avanzada para Microsoft 365 Defender
description: Obtenga información sobre cómo usar la función DeviceFromIP() para obtener los dispositivos a los que se ha asignado una dirección IP específica
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, dispositivo, devicefromIP, función, enriquecimiento
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
ms.openlocfilehash: d2996021a84186adc6656927dbdc910db4d037de
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071571"
---
# <a name="devicefromip"></a><span data-ttu-id="3bd95-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="3bd95-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3bd95-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3bd95-105">**Applies to:**</span></span>
- <span data-ttu-id="3bd95-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3bd95-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="3bd95-107">Usa la función de las consultas de búsqueda avanzadas para obtener rápidamente la lista de dispositivos que se han asignado a una dirección IP determinada `DeviceFromIP()` en un momento dado. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3bd95-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="3bd95-108">Esta función devuelve una tabla con las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="3bd95-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="3bd95-109">Column</span><span class="sxs-lookup"><span data-stu-id="3bd95-109">Column</span></span> | <span data-ttu-id="3bd95-110">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="3bd95-110">Data type</span></span> | <span data-ttu-id="3bd95-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3bd95-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="3bd95-112">string</span><span class="sxs-lookup"><span data-stu-id="3bd95-112">string</span></span> | <span data-ttu-id="3bd95-113">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="3bd95-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="3bd95-114">string</span><span class="sxs-lookup"><span data-stu-id="3bd95-114">string</span></span> | <span data-ttu-id="3bd95-115">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="3bd95-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="3bd95-116">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bd95-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="3bd95-117">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3bd95-117">Arguments</span></span>

<span data-ttu-id="3bd95-118">Esta función se invoca como parte de una consulta.</span><span class="sxs-lookup"><span data-stu-id="3bd95-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="3bd95-119">**x**: el primer parámetro suele ser ya una columna de la consulta.</span><span class="sxs-lookup"><span data-stu-id="3bd95-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="3bd95-120">En este caso, es la columna denominada , la dirección IP para la que desea ver una lista de dispositivos que se le han `IP` asignado.</span><span class="sxs-lookup"><span data-stu-id="3bd95-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="3bd95-121">Debe ser una dirección IP local.</span><span class="sxs-lookup"><span data-stu-id="3bd95-121">It should be a local IP address.</span></span> <span data-ttu-id="3bd95-122">No se admiten direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="3bd95-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="3bd95-123">**y**— Un segundo parámetro opcional es el , que indica a la función que obtenga los `Timestamp` dispositivos asignados más recientes a partir de una hora específica.</span><span class="sxs-lookup"><span data-stu-id="3bd95-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="3bd95-124">Si no se especifica, la función devuelve los registros disponibles más recientes.</span><span class="sxs-lookup"><span data-stu-id="3bd95-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="3bd95-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3bd95-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="3bd95-126">Obtener los dispositivos más recientes a los que se han asignado direcciones IP específicas</span><span class="sxs-lookup"><span data-stu-id="3bd95-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="3bd95-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3bd95-127">Related topics</span></span>
- [<span data-ttu-id="3bd95-128">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3bd95-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3bd95-129">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="3bd95-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3bd95-130">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="3bd95-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
