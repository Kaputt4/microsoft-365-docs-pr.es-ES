---
title: Tabla DeviceAlertEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación de alertas en la tabla DeviceAlertEvents del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, microsoft defender para el punto de conexión, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, DeviceAlertEvents, alerta, gravedad, categoría
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
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: f4f6ecdc57d8602f49fb389c741c5e01dc1b41b5
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939655"
---
# <a name="devicealertevents"></a><span data-ttu-id="d845b-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="d845b-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d845b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d845b-105">**Applies to:**</span></span>
- [<span data-ttu-id="d845b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d845b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="d845b-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d845b-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d845b-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d845b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="d845b-109">La `DeviceAlertEvents` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre las alertas de Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d845b-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="d845b-110">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="d845b-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d845b-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d845b-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="d845b-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="d845b-112">Column name</span></span> | <span data-ttu-id="d845b-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d845b-113">Data type</span></span> | <span data-ttu-id="d845b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d845b-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="d845b-115">string</span><span class="sxs-lookup"><span data-stu-id="d845b-115">string</span></span> | <span data-ttu-id="d845b-116">Identificador único de alerta.</span><span class="sxs-lookup"><span data-stu-id="d845b-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="d845b-117">datetime</span><span class="sxs-lookup"><span data-stu-id="d845b-117">datetime</span></span> | <span data-ttu-id="d845b-118">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="d845b-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d845b-119">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-119">string</span></span> | <span data-ttu-id="d845b-120">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="d845b-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d845b-121">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-121">string</span></span> | <span data-ttu-id="d845b-122">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="d845b-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="d845b-123">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-123">string</span></span> | <span data-ttu-id="d845b-124">El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta.</span><span class="sxs-lookup"><span data-stu-id="d845b-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="d845b-125">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-125">string</span></span> | <span data-ttu-id="d845b-126">Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta</span><span class="sxs-lookup"><span data-stu-id="d845b-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="d845b-127">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-127">string</span></span> | <span data-ttu-id="d845b-128">Título de la alerta.</span><span class="sxs-lookup"><span data-stu-id="d845b-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="d845b-129">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-129">string</span></span> | <span data-ttu-id="d845b-130">Nombre del archivo donde se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="d845b-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="d845b-131">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-131">string</span></span> | <span data-ttu-id="d845b-132">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="d845b-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="d845b-133">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-133">string</span></span> | <span data-ttu-id="d845b-134">La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado.</span><span class="sxs-lookup"><span data-stu-id="d845b-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="d845b-135">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-135">string</span></span> | <span data-ttu-id="d845b-136">Dirección IP a la que se ha conectado</span><span class="sxs-lookup"><span data-stu-id="d845b-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="d845b-137">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-137">string</span></span> | <span data-ttu-id="d845b-138">MITRE ATT&técnicas de CK asociadas con la actividad que desencadenó la alerta</span><span class="sxs-lookup"><span data-stu-id="d845b-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="d845b-139">largo</span><span class="sxs-lookup"><span data-stu-id="d845b-139">long</span></span> | <span data-ttu-id="d845b-140">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="d845b-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d845b-141">Para identificar eventos únicos, esta columna debe usarse junto con las `DeviceName` columnas y `Timestamp`</span><span class="sxs-lookup"><span data-stu-id="d845b-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="d845b-142">cadena</span><span class="sxs-lookup"><span data-stu-id="d845b-142">string</span></span> | <span data-ttu-id="d845b-143">Tabla con el contenido detallado del evento</span><span class="sxs-lookup"><span data-stu-id="d845b-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d845b-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d845b-144">Related topics</span></span>
- [<span data-ttu-id="d845b-145">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="d845b-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d845b-146">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="d845b-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d845b-147">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="d845b-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
