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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d0efd97359440ffb3d4b39b6389b477203c56084
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985005"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="86455-104">API compatibles de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="86455-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="86455-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="86455-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="86455-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="86455-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="86455-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="86455-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="86455-108">URI de extremo y control de versiones</span><span class="sxs-lookup"><span data-stu-id="86455-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="86455-109">URI del extremo</span><span class="sxs-lookup"><span data-stu-id="86455-109">Endpoint URI</span></span>

> <span data-ttu-id="86455-110">El URI de base de servicio es: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="86455-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="86455-111">Las consultas basadas en OData tienen el prefijo '/api'.</span><span class="sxs-lookup"><span data-stu-id="86455-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="86455-112">Por ejemplo, para obtener alertas, puede enviar una solicitud GET a [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="86455-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="86455-113">Control de versiones</span><span class="sxs-lookup"><span data-stu-id="86455-113">Versioning</span></span>

> <span data-ttu-id="86455-114">La API admite el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="86455-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="86455-115">La versión actual es **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="86455-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="86455-116">Para usar una versión específica, use este formato: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="86455-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="86455-117">Por ejemplo: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="86455-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="86455-118">Si no especifica ninguna versión (por ejemplo, ) llegará a `https://api.securitycenter.microsoft.com/api/alerts` la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="86455-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="86455-119">Obtenga más información sobre las entidades admitidas individualmente en las que puede ejecutar llamadas API y detalles como valores de solicitud HTTP, encabezados de solicitud y respuestas esperadas.</span><span class="sxs-lookup"><span data-stu-id="86455-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="86455-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="86455-120">In this section</span></span>

<span data-ttu-id="86455-121">Tema</span><span class="sxs-lookup"><span data-stu-id="86455-121">Topic</span></span> | <span data-ttu-id="86455-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="86455-122">Description</span></span>
:---|:---
[<span data-ttu-id="86455-123">Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="86455-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="86455-124">Ejecutar consultas desde la API.</span><span class="sxs-lookup"><span data-stu-id="86455-124">Run queries from API.</span></span>
[<span data-ttu-id="86455-125">Propiedades y métodos de alerta</span><span class="sxs-lookup"><span data-stu-id="86455-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="86455-126">Ejecute llamadas API como \- obtener alertas, crear alertas, actualizar alertas y mucho más.</span><span class="sxs-lookup"><span data-stu-id="86455-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="86455-127">Exportar métodos de evaluación y propiedades por dispositivo</span><span class="sxs-lookup"><span data-stu-id="86455-127">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md) | <span data-ttu-id="86455-128">Ejecute llamadas api para recopilar evaluaciones de vulnerabilidades por dispositivo, como: evaluación de configuración segura de exportación, evaluación de inventario de software de exportación, evaluación de vulnerabilidades de software de exportación y evaluación de vulnerabilidades de software de exportación \- delta.</span><span class="sxs-lookup"><span data-stu-id="86455-128">Run API calls to gather vulnerability assessments on a per-device basis, such as: \- export secure configuration assessment, export software inventory assessment,  export software vulnerabilities assessment, and delta export software vulnerabilities assessment.</span></span>
[<span data-ttu-id="86455-129">Propiedades y métodos de investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="86455-129">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="86455-130">Ejecute llamadas API como \- obtener la colección de Investigación.</span><span class="sxs-lookup"><span data-stu-id="86455-130">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="86455-131">Obtener alertas relacionadas con dominios</span><span class="sxs-lookup"><span data-stu-id="86455-131">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="86455-132">Ejecute llamadas API como obtener dispositivos relacionados con \- el dominio, estadísticas de dominio y mucho más.</span><span class="sxs-lookup"><span data-stu-id="86455-132">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="86455-133">Propiedades y métodos de archivo</span><span class="sxs-lookup"><span data-stu-id="86455-133">File methods and properties</span></span>](files.md) | <span data-ttu-id="86455-134">Ejecute llamadas API como obtener información de archivos, alertas relacionadas con \- archivos, dispositivos relacionados con archivos y estadísticas de archivos.</span><span class="sxs-lookup"><span data-stu-id="86455-134">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="86455-135">Propiedades y métodos de indicadores</span><span class="sxs-lookup"><span data-stu-id="86455-135">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="86455-136">Ejecute una llamada a la API como \- obtener indicadores, crear indicadores y eliminar indicadores.</span><span class="sxs-lookup"><span data-stu-id="86455-136">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="86455-137">Obtener alertas relacionadas con IP</span><span class="sxs-lookup"><span data-stu-id="86455-137">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="86455-138">Ejecute llamadas API como \- obtener alertas relacionadas con IP y obtener estadísticas de IP.</span><span class="sxs-lookup"><span data-stu-id="86455-138">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="86455-139">Propiedades y métodos de máquina</span><span class="sxs-lookup"><span data-stu-id="86455-139">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="86455-140">Ejecute llamadas API como obtener dispositivos, obtener dispositivos por identificador, información sobre usuarios que han iniciado \- sesión, editar etiquetas y mucho más.</span><span class="sxs-lookup"><span data-stu-id="86455-140">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="86455-141">Métodos y propiedades de acción de máquina</span><span class="sxs-lookup"><span data-stu-id="86455-141">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="86455-142">Ejecute una llamada API como \- Aislamiento, Ejecutar examen antivirus y mucho más.</span><span class="sxs-lookup"><span data-stu-id="86455-142">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="86455-143">Propiedades y métodos estáticos</span><span class="sxs-lookup"><span data-stu-id="86455-143">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="86455-144">Ejecute llamadas API como \- obtener recomendación por identificador.</span><span class="sxs-lookup"><span data-stu-id="86455-144">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="86455-145">Propiedades y métodos de la actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="86455-145">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="86455-146">Ejecute una llamada API como obtener todas las tareas de corrección, obtener la tarea de corrección de dispositivos expuestos y \- obtener una tarea de corrección por identificador.</span><span class="sxs-lookup"><span data-stu-id="86455-146">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="86455-147">Propiedades y métodos de puntuación</span><span class="sxs-lookup"><span data-stu-id="86455-147">Score methods and properties</span></span>](score.md) | <span data-ttu-id="86455-148">Ejecuta llamadas API como obtener \- puntuación de exposición o obtener puntuación segura del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="86455-148">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="86455-149">Propiedades y métodos de software</span><span class="sxs-lookup"><span data-stu-id="86455-149">Software methods and properties</span></span>](software.md) | <span data-ttu-id="86455-150">Ejecute llamadas API como, \- por ejemplo, enumerar vulnerabilidades por software.</span><span class="sxs-lookup"><span data-stu-id="86455-150">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="86455-151">Métodos de usuario</span><span class="sxs-lookup"><span data-stu-id="86455-151">User methods</span></span>](user.md) | <span data-ttu-id="86455-152">Ejecute llamadas API como obtener alertas relacionadas con \- el usuario y dispositivos relacionados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="86455-152">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="86455-153">Propiedades y métodos de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="86455-153">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="86455-154">Ejecute llamadas API, como \- los dispositivos de lista por vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="86455-154">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="86455-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="86455-155">See also</span></span>

- [<span data-ttu-id="86455-156">Microsoft Defender para api de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="86455-156">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="86455-157">Notas de la versión de api de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="86455-157">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
