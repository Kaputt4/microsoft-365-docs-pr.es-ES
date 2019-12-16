---
title: Tabla EmailEvents en el esquema de búsqueda avanzada
description: Obtenga más información sobre los eventos de generación de alertas en la tabla AlertEvents en el esquema de búsqueda avanzada
keywords: Búsqueda, búsqueda avanzada, de amenazas, de ciberamenazas, consulta, telemetría, referencia del esquema, kusto, tabla, columna, tipo de datos, descripción, alertas, alerta, gravedad, categoría
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911642"
---
# <a name="alertevents"></a><span data-ttu-id="ae148-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="ae148-104">AlertEvents</span></span>

<span data-ttu-id="ae148-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ae148-105">**Applies to:**</span></span>
- <span data-ttu-id="ae148-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae148-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="ae148-107">El esquema en la `AlertEvents`tabla de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las alertas procesadas por la ATP de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ae148-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="ae148-108">Use esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="ae148-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ae148-109">Para obtener información sobre otras tablas en el esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ae148-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ae148-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="ae148-110">Column name</span></span> | <span data-ttu-id="ae148-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ae148-111">Data type</span></span> | <span data-ttu-id="ae148-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae148-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="ae148-113">string</span><span class="sxs-lookup"><span data-stu-id="ae148-113">string</span></span> | <span data-ttu-id="ae148-114">Identificador único de alerta.</span><span class="sxs-lookup"><span data-stu-id="ae148-114">Unique identifier for the bucket.</span></span> |
| `EventTime` | <span data-ttu-id="ae148-115">datetime</span><span class="sxs-lookup"><span data-stu-id="ae148-115">dateTime</span></span> | <span data-ttu-id="ae148-116">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="ae148-116">Date and time the report was recorded.</span></span> |
| `MachineId` | <span data-ttu-id="ae148-117">cadena</span><span class="sxs-lookup"><span data-stu-id="ae148-117">string</span></span> | <span data-ttu-id="ae148-118">Identificador único para la máquina del servicio</span><span class="sxs-lookup"><span data-stu-id="ae148-118">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="ae148-119">cadena</span><span class="sxs-lookup"><span data-stu-id="ae148-119">string</span></span> | <span data-ttu-id="ae148-120">Nombre de dominio completo (FQDN, por sus siglas en inglés) de la máquina</span><span class="sxs-lookup"><span data-stu-id="ae148-120">Fully qualified domain name (FQDN) of the pool</span></span> |
| `Severity` | <span data-ttu-id="ae148-121">cadena</span><span class="sxs-lookup"><span data-stu-id="ae148-121">string</span></span> | <span data-ttu-id="ae148-122">El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta.</span><span class="sxs-lookup"><span data-stu-id="ae148-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="ae148-123">cadena</span><span class="sxs-lookup"><span data-stu-id="ae148-123">string</span></span> | <span data-ttu-id="ae148-124">Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta</span><span class="sxs-lookup"><span data-stu-id="ae148-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="ae148-125">cadena</span><span class="sxs-lookup"><span data-stu-id="ae148-125">string</span></span> | <span data-ttu-id="ae148-126">Título de la alerta.</span><span class="sxs-lookup"><span data-stu-id="ae148-126">Title of the alert.</span></span> |
| `FileName` | <span data-ttu-id="ae148-127">cadena</span><span class="sxs-lookup"><span data-stu-id="ae148-127">string</span></span> | <span data-ttu-id="ae148-128">Nombre del archivo donde se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="ae148-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="ae148-129">cadena</span><span class="sxs-lookup"><span data-stu-id="ae148-129">string</span></span> | <span data-ttu-id="ae148-130">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="ae148-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="ae148-131">cadena</span><span class="sxs-lookup"><span data-stu-id="ae148-131">string</span></span> | <span data-ttu-id="ae148-132">La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado.</span><span class="sxs-lookup"><span data-stu-id="ae148-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="ae148-133">cadena</span><span class="sxs-lookup"><span data-stu-id="ae148-133">string</span></span> | <span data-ttu-id="ae148-134">Dirección IP a la que se ha conectado</span><span class="sxs-lookup"><span data-stu-id="ae148-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="ae148-135">largo</span><span class="sxs-lookup"><span data-stu-id="ae148-135">long</span></span> | <span data-ttu-id="ae148-136">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="ae148-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="ae148-137">Para identificar eventos únicos, esta columna debe utilizarse conjuntamente con las columnas ComputerName y EventTime.</span><span class="sxs-lookup"><span data-stu-id="ae148-137">To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns</span></span> |
| `Table` | <span data-ttu-id="ae148-138">cadena</span><span class="sxs-lookup"><span data-stu-id="ae148-138">string</span></span> | <span data-ttu-id="ae148-139">Tabla con el contenido detallado del evento</span><span class="sxs-lookup"><span data-stu-id="ae148-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ae148-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ae148-140">Related topics</span></span>
- [<span data-ttu-id="ae148-141">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="ae148-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ae148-142">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="ae148-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ae148-143">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="ae148-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ae148-144">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="ae148-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ae148-145">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="ae148-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ae148-146">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="ae148-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
