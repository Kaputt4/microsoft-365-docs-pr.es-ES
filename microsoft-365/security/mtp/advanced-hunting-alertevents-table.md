---
title: Tabla EmailEvents en el esquema de búsqueda avanzada
description: Obtenga más información sobre los eventos de generación de alertas en la tabla AlertEvents en el esquema de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, alertevents, alerta, gravedad, categoría
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9f341705d8247183b7e8a5271231c82faf8b386a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235099"
---
# <a name="alertevents"></a><span data-ttu-id="0e6a3-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="0e6a3-104">AlertEvents</span></span>

<span data-ttu-id="0e6a3-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0e6a3-105">**Applies to:**</span></span>
- <span data-ttu-id="0e6a3-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0e6a3-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="0e6a3-107">El esquema en la `AlertEvents`tabla de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las alertas procesadas por la ATP de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0e6a3-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="0e6a3-108">Use esta referencia para crear consultas que devuelvan información sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="0e6a3-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0e6a3-109">Para obtener información sobre otras tablas en el esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0e6a3-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0e6a3-110">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="0e6a3-110">Column name</span></span> | <span data-ttu-id="0e6a3-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0e6a3-111">Data type</span></span> | <span data-ttu-id="0e6a3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e6a3-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="0e6a3-113">string</span><span class="sxs-lookup"><span data-stu-id="0e6a3-113">string</span></span> | <span data-ttu-id="0e6a3-114">Identificador único de alerta.</span><span class="sxs-lookup"><span data-stu-id="0e6a3-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="0e6a3-115">datetime</span><span class="sxs-lookup"><span data-stu-id="0e6a3-115">datetime</span></span> | <span data-ttu-id="0e6a3-116">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="0e6a3-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0e6a3-117">cadena</span><span class="sxs-lookup"><span data-stu-id="0e6a3-117">string</span></span> | <span data-ttu-id="0e6a3-118">Identificador único para la máquina del servicio</span><span class="sxs-lookup"><span data-stu-id="0e6a3-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0e6a3-119">cadena</span><span class="sxs-lookup"><span data-stu-id="0e6a3-119">string</span></span> | <span data-ttu-id="0e6a3-120">Nombre de dominio completo (FQDN, por sus siglas en inglés) de la máquina</span><span class="sxs-lookup"><span data-stu-id="0e6a3-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="0e6a3-121">cadena</span><span class="sxs-lookup"><span data-stu-id="0e6a3-121">string</span></span> | <span data-ttu-id="0e6a3-122">El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta.</span><span class="sxs-lookup"><span data-stu-id="0e6a3-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="0e6a3-123">cadena</span><span class="sxs-lookup"><span data-stu-id="0e6a3-123">string</span></span> | <span data-ttu-id="0e6a3-124">Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta</span><span class="sxs-lookup"><span data-stu-id="0e6a3-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="0e6a3-125">cadena</span><span class="sxs-lookup"><span data-stu-id="0e6a3-125">string</span></span> | <span data-ttu-id="0e6a3-126">Título de la alerta.</span><span class="sxs-lookup"><span data-stu-id="0e6a3-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="0e6a3-127">cadena</span><span class="sxs-lookup"><span data-stu-id="0e6a3-127">string</span></span> | <span data-ttu-id="0e6a3-128">Nombre del archivo donde se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="0e6a3-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="0e6a3-129">cadena</span><span class="sxs-lookup"><span data-stu-id="0e6a3-129">string</span></span> | <span data-ttu-id="0e6a3-130">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="0e6a3-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="0e6a3-131">cadena</span><span class="sxs-lookup"><span data-stu-id="0e6a3-131">string</span></span> | <span data-ttu-id="0e6a3-132">La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado.</span><span class="sxs-lookup"><span data-stu-id="0e6a3-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="0e6a3-133">cadena</span><span class="sxs-lookup"><span data-stu-id="0e6a3-133">string</span></span> | <span data-ttu-id="0e6a3-134">Dirección IP a la que se ha conectado</span><span class="sxs-lookup"><span data-stu-id="0e6a3-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="0e6a3-135">largo</span><span class="sxs-lookup"><span data-stu-id="0e6a3-135">long</span></span> | <span data-ttu-id="0e6a3-136">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="0e6a3-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0e6a3-137">Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp.</span><span class="sxs-lookup"><span data-stu-id="0e6a3-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="0e6a3-138">cadena</span><span class="sxs-lookup"><span data-stu-id="0e6a3-138">string</span></span> | <span data-ttu-id="0e6a3-139">Tabla con el contenido detallado del evento</span><span class="sxs-lookup"><span data-stu-id="0e6a3-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0e6a3-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0e6a3-140">Related topics</span></span>
- [<span data-ttu-id="0e6a3-141">Búsqueda proactiva de amenazas</span><span class="sxs-lookup"><span data-stu-id="0e6a3-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0e6a3-142">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="0e6a3-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0e6a3-143">Usar consultas compartidas</span><span class="sxs-lookup"><span data-stu-id="0e6a3-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0e6a3-144">Búsqueda de amenazas en dispositivos y mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="0e6a3-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0e6a3-145">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="0e6a3-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0e6a3-146">Aplicar procedimientos recomendados de consulta</span><span class="sxs-lookup"><span data-stu-id="0e6a3-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
