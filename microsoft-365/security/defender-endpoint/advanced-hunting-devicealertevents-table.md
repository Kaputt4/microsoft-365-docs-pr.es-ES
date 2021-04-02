---
title: Tabla DeviceAlertEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación de alertas en la tabla DeviceAlertEvents del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, DeviceAlertEvents, alerta, gravedad, categoría
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
ms.openlocfilehash: 66ecdc8fbcde04d78f2deede5f4e296a7f051ef0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499159"
---
# <a name="devicealertevents"></a><span data-ttu-id="3ef1f-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="3ef1f-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ef1f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3ef1f-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ef1f-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3ef1f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="3ef1f-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3ef1f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3ef1f-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="3ef1f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="3ef1f-109">La `DeviceAlertEvents` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre alertas en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3ef1f-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="3ef1f-110">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3ef1f-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="3ef1f-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3ef1f-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="3ef1f-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="3ef1f-112">Column name</span></span> | <span data-ttu-id="3ef1f-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="3ef1f-113">Data type</span></span> | <span data-ttu-id="3ef1f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ef1f-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="3ef1f-115">string</span><span class="sxs-lookup"><span data-stu-id="3ef1f-115">string</span></span> | <span data-ttu-id="3ef1f-116">Identificador único de alerta.</span><span class="sxs-lookup"><span data-stu-id="3ef1f-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="3ef1f-117">datetime</span><span class="sxs-lookup"><span data-stu-id="3ef1f-117">datetime</span></span> | <span data-ttu-id="3ef1f-118">Fecha y hora en que se registró el evento.</span><span class="sxs-lookup"><span data-stu-id="3ef1f-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="3ef1f-119">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-119">string</span></span> | <span data-ttu-id="3ef1f-120">Identificador único del dispositivo en el servicio</span><span class="sxs-lookup"><span data-stu-id="3ef1f-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3ef1f-121">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-121">string</span></span> | <span data-ttu-id="3ef1f-122">Nombre de dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3ef1f-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="3ef1f-123">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-123">string</span></span> | <span data-ttu-id="3ef1f-124">El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta.</span><span class="sxs-lookup"><span data-stu-id="3ef1f-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="3ef1f-125">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-125">string</span></span> | <span data-ttu-id="3ef1f-126">Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta</span><span class="sxs-lookup"><span data-stu-id="3ef1f-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="3ef1f-127">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-127">string</span></span> | <span data-ttu-id="3ef1f-128">Título de la alerta.</span><span class="sxs-lookup"><span data-stu-id="3ef1f-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="3ef1f-129">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-129">string</span></span> | <span data-ttu-id="3ef1f-130">Nombre del archivo donde se aplicó la acción registrada</span><span class="sxs-lookup"><span data-stu-id="3ef1f-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="3ef1f-131">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-131">string</span></span> | <span data-ttu-id="3ef1f-132">SHA-1 del archivo donde fue aplicada la acción registrada</span><span class="sxs-lookup"><span data-stu-id="3ef1f-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="3ef1f-133">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-133">string</span></span> | <span data-ttu-id="3ef1f-134">La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado.</span><span class="sxs-lookup"><span data-stu-id="3ef1f-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="3ef1f-135">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-135">string</span></span> | <span data-ttu-id="3ef1f-136">Dirección IP a la que se ha conectado</span><span class="sxs-lookup"><span data-stu-id="3ef1f-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="3ef1f-137">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-137">string</span></span> | <span data-ttu-id="3ef1f-138">MITRE ATT&técnicas de CK asociadas con la actividad que desencadenó la alerta</span><span class="sxs-lookup"><span data-stu-id="3ef1f-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="3ef1f-139">largo</span><span class="sxs-lookup"><span data-stu-id="3ef1f-139">long</span></span> | <span data-ttu-id="3ef1f-140">Identificador de eventos basado en un contador de repetición.</span><span class="sxs-lookup"><span data-stu-id="3ef1f-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="3ef1f-141">Para identificar eventos únicos, esta columna debe usarse junto con las `DeviceName` columnas y `Timestamp`</span><span class="sxs-lookup"><span data-stu-id="3ef1f-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="3ef1f-142">cadena</span><span class="sxs-lookup"><span data-stu-id="3ef1f-142">string</span></span> | <span data-ttu-id="3ef1f-143">Tabla con el contenido detallado del evento</span><span class="sxs-lookup"><span data-stu-id="3ef1f-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3ef1f-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3ef1f-144">Related topics</span></span>
- [<span data-ttu-id="3ef1f-145">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="3ef1f-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3ef1f-146">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="3ef1f-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3ef1f-147">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="3ef1f-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
