---
title: API compatibles de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtenga información sobre las entidades específicas admitidas de Microsoft Defender para puntos de conexión a las que puede crear llamadas a la API.
keywords: apis, api admitidas, actor, alertas, dispositivo, usuario, dominio, ip, archivo, consultas avanzadas, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 656aa26d80db73bfc52511f9dd94e58e771f3ac6
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073846"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="2933f-104">API compatibles de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2933f-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2933f-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2933f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2933f-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2933f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2933f-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2933f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="2933f-108">URI de extremo y control de versiones</span><span class="sxs-lookup"><span data-stu-id="2933f-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="2933f-109">URI del extremo</span><span class="sxs-lookup"><span data-stu-id="2933f-109">Endpoint URI</span></span>

> <span data-ttu-id="2933f-110">El URI de base de servicio es: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="2933f-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="2933f-111">Las consultas basadas en OData tienen el prefijo '/api'.</span><span class="sxs-lookup"><span data-stu-id="2933f-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="2933f-112">Por ejemplo, para obtener alertas, puede enviar una solicitud GET a [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="2933f-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="2933f-113">Control de versiones</span><span class="sxs-lookup"><span data-stu-id="2933f-113">Versioning</span></span>

> <span data-ttu-id="2933f-114">La API admite el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="2933f-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="2933f-115">La versión actual es **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="2933f-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="2933f-116">Para usar una versión específica, use este formato: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="2933f-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="2933f-117">Por ejemplo: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="2933f-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="2933f-118">Si no especifica ninguna versión (por ejemplo, ) llegará a `https://api.securitycenter.microsoft.com/api/alerts` la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="2933f-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="2933f-119">Obtenga más información sobre las entidades admitidas individualmente en las que puede ejecutar llamadas API y detalles como valores de solicitud HTTP, encabezados de solicitud y respuestas esperadas.</span><span class="sxs-lookup"><span data-stu-id="2933f-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2933f-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2933f-120">In this section</span></span>

<span data-ttu-id="2933f-121">Tema</span><span class="sxs-lookup"><span data-stu-id="2933f-121">Topic</span></span> | <span data-ttu-id="2933f-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2933f-122">Description</span></span>
:---|:---
[<span data-ttu-id="2933f-123">Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="2933f-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="2933f-124">Ejecutar consultas desde la API.</span><span class="sxs-lookup"><span data-stu-id="2933f-124">Run queries from API.</span></span>
[<span data-ttu-id="2933f-125">Propiedades y métodos de alerta</span><span class="sxs-lookup"><span data-stu-id="2933f-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="2933f-126">Ejecute llamadas API como \- obtener alertas, crear alertas, actualizar alertas y mucho más.</span><span class="sxs-lookup"><span data-stu-id="2933f-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="2933f-127">Propiedades y métodos de investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="2933f-127">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="2933f-128">Ejecute llamadas API como \- obtener la colección de Investigación.</span><span class="sxs-lookup"><span data-stu-id="2933f-128">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="2933f-129">Obtener alertas relacionadas con dominios</span><span class="sxs-lookup"><span data-stu-id="2933f-129">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="2933f-130">Ejecute llamadas API como obtener dispositivos relacionados con \- el dominio, estadísticas de dominio y mucho más.</span><span class="sxs-lookup"><span data-stu-id="2933f-130">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="2933f-131">Propiedades y métodos de archivo</span><span class="sxs-lookup"><span data-stu-id="2933f-131">File methods and properties</span></span>](files.md) | <span data-ttu-id="2933f-132">Ejecute llamadas API como obtener información de archivos, alertas relacionadas con \- archivos, dispositivos relacionados con archivos y estadísticas de archivos.</span><span class="sxs-lookup"><span data-stu-id="2933f-132">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="2933f-133">Propiedades y métodos de indicadores</span><span class="sxs-lookup"><span data-stu-id="2933f-133">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="2933f-134">Ejecute una llamada a la API como \- obtener indicadores, crear indicadores y eliminar indicadores.</span><span class="sxs-lookup"><span data-stu-id="2933f-134">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="2933f-135">Obtener alertas relacionadas con IP</span><span class="sxs-lookup"><span data-stu-id="2933f-135">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="2933f-136">Ejecute llamadas API como \- obtener alertas relacionadas con IP y obtener estadísticas de IP.</span><span class="sxs-lookup"><span data-stu-id="2933f-136">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="2933f-137">Propiedades y métodos de máquina</span><span class="sxs-lookup"><span data-stu-id="2933f-137">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="2933f-138">Ejecute llamadas API como obtener dispositivos, obtener dispositivos por identificador, información sobre usuarios que han iniciado \- sesión, editar etiquetas y mucho más.</span><span class="sxs-lookup"><span data-stu-id="2933f-138">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="2933f-139">Métodos y propiedades de acción de máquina</span><span class="sxs-lookup"><span data-stu-id="2933f-139">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="2933f-140">Ejecute una llamada API como \- Aislamiento, Ejecutar examen antivirus y mucho más.</span><span class="sxs-lookup"><span data-stu-id="2933f-140">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="2933f-141">Propiedades y métodos estáticos.</span><span class="sxs-lookup"><span data-stu-id="2933f-141">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="2933f-142">Ejecute llamadas API como \- obtener recomendación por identificador.</span><span class="sxs-lookup"><span data-stu-id="2933f-142">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="2933f-143">Propiedades y métodos de puntuación</span><span class="sxs-lookup"><span data-stu-id="2933f-143">Score methods and properties</span></span>](score.md) | <span data-ttu-id="2933f-144">Ejecuta llamadas API como obtener \- puntuación de exposición o obtener puntuación segura del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2933f-144">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="2933f-145">Propiedades y métodos de software</span><span class="sxs-lookup"><span data-stu-id="2933f-145">Software methods and properties</span></span>](software.md) | <span data-ttu-id="2933f-146">Ejecute llamadas API como, \- por ejemplo, enumerar vulnerabilidades por software.</span><span class="sxs-lookup"><span data-stu-id="2933f-146">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="2933f-147">Métodos de usuario</span><span class="sxs-lookup"><span data-stu-id="2933f-147">User methods</span></span>](user.md) | <span data-ttu-id="2933f-148">Ejecute llamadas API como obtener alertas relacionadas con \- el usuario y dispositivos relacionados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="2933f-148">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="2933f-149">Propiedades y métodos de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="2933f-149">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="2933f-150">Ejecute llamadas API, como \- los dispositivos de lista por vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="2933f-150">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="2933f-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2933f-151">See also</span></span>

- [<span data-ttu-id="2933f-152">Microsoft Defender para api de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2933f-152">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="2933f-153">Notas de la versión de api de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="2933f-153">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
