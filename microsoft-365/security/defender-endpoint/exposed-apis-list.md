---
title: Compatible con Microsoft Defender para LAS API de punto de conexión
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
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198332"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="2e994-104">Compatible con Microsoft Defender para LAS API de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2e994-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2e994-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2e994-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2e994-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2e994-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2e994-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2e994-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="2e994-108">URI de extremo y control de versiones</span><span class="sxs-lookup"><span data-stu-id="2e994-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="2e994-109">URI del extremo:            </span><span class="sxs-lookup"><span data-stu-id="2e994-109">Endpoint URI:</span></span>

> <span data-ttu-id="2e994-110">El URI de base de servicio es: https://api.securitycenter.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2e994-110">The service base URI is: https://api.securitycenter.microsoft.com</span></span>
> 
> <span data-ttu-id="2e994-111">Las consultas basadas en OData tienen el prefijo '/api'.</span><span class="sxs-lookup"><span data-stu-id="2e994-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="2e994-112">Por ejemplo, para obtener alertas, puede enviar una solicitud GET a https://api.securitycenter.microsoft.com/api/alerts</span><span class="sxs-lookup"><span data-stu-id="2e994-112">For example, to get Alerts you can send GET request to https://api.securitycenter.microsoft.com/api/alerts</span></span>

### <a name="versioning"></a><span data-ttu-id="2e994-113">Control de versiones:</span><span class="sxs-lookup"><span data-stu-id="2e994-113">Versioning:</span></span>

> <span data-ttu-id="2e994-114">La API admite el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="2e994-114">The API supports versioning.</span></span>
> 
> <span data-ttu-id="2e994-115">La versión actual es **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="2e994-115">The current version is **V1.0**.</span></span>
> 
> <span data-ttu-id="2e994-116">Para usar una versión específica, use este formato: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="2e994-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="2e994-117">Por ejemplo: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="2e994-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
> 
> <span data-ttu-id="2e994-118">Si no especifica ninguna versión (por ejemplo, ) llegará a https://api.securitycenter.microsoft.com/api/alerts la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="2e994-118">If you don't specify any version (e.g. https://api.securitycenter.microsoft.com/api/alerts ) you will get to the latest version.</span></span>


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="2e994-119">Obtenga más información sobre las entidades admitidas individualmente en las que puede ejecutar llamadas API y detalles como valores de solicitud HTTP, encabezados de solicitud y respuestas esperadas.</span><span class="sxs-lookup"><span data-stu-id="2e994-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2e994-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2e994-120">In this section</span></span>

<span data-ttu-id="2e994-121">Tema</span><span class="sxs-lookup"><span data-stu-id="2e994-121">Topic</span></span> | <span data-ttu-id="2e994-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e994-122">Description</span></span>
:---|:---
<span data-ttu-id="2e994-123">Búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="2e994-123">Advanced Hunting</span></span> | <span data-ttu-id="2e994-124">Ejecutar consultas desde la API.</span><span class="sxs-lookup"><span data-stu-id="2e994-124">Run queries from API.</span></span>
<span data-ttu-id="2e994-125">Alertas</span><span class="sxs-lookup"><span data-stu-id="2e994-125">Alerts</span></span> | <span data-ttu-id="2e994-126">Ejecute llamadas API como obtener alertas, crear alertas, actualizar alertas y mucho más.</span><span class="sxs-lookup"><span data-stu-id="2e994-126">Run API calls such as get alerts, create alert, update alert and more.</span></span>
<span data-ttu-id="2e994-127">Dominios</span><span class="sxs-lookup"><span data-stu-id="2e994-127">Domains</span></span> | <span data-ttu-id="2e994-128">Ejecute llamadas API como obtener dispositivos relacionados con el dominio, estadísticas de dominio y mucho más.</span><span class="sxs-lookup"><span data-stu-id="2e994-128">Run API calls such as get domain-related devices, domain statistics and more.</span></span>
<span data-ttu-id="2e994-129">Archivos</span><span class="sxs-lookup"><span data-stu-id="2e994-129">Files</span></span> | <span data-ttu-id="2e994-130">Ejecute llamadas API como obtener información de archivos, alertas relacionadas con archivos, dispositivos relacionados con archivos y estadísticas de archivos.</span><span class="sxs-lookup"><span data-stu-id="2e994-130">Run API calls such as get file information, file related alerts, file related devices, and file statistics.</span></span>
<span data-ttu-id="2e994-131">IP</span><span class="sxs-lookup"><span data-stu-id="2e994-131">IPs</span></span> | <span data-ttu-id="2e994-132">Ejecute llamadas API como obtener alertas relacionadas con IP y obtener estadísticas de IP.</span><span class="sxs-lookup"><span data-stu-id="2e994-132">Run API calls such as get IP-related alerts and get IP statistics.</span></span>
<span data-ttu-id="2e994-133">Equipos</span><span class="sxs-lookup"><span data-stu-id="2e994-133">Machines</span></span> | <span data-ttu-id="2e994-134">Ejecute llamadas API como obtener dispositivos, obtener dispositivos por identificador, información sobre usuarios que han iniciado sesión, editar etiquetas y mucho más.</span><span class="sxs-lookup"><span data-stu-id="2e994-134">Run API calls such as get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
<span data-ttu-id="2e994-135">Acciones de la máquina</span><span class="sxs-lookup"><span data-stu-id="2e994-135">Machine Actions</span></span> | <span data-ttu-id="2e994-136">Ejecute una llamada API como Aislamiento, Ejecutar examen antivirus y mucho más.</span><span class="sxs-lookup"><span data-stu-id="2e994-136">Run API call such as Isolation, Run anti-virus scan and more.</span></span>
<span data-ttu-id="2e994-137">Indicadores</span><span class="sxs-lookup"><span data-stu-id="2e994-137">Indicators</span></span> | <span data-ttu-id="2e994-138">Ejecute una llamada api como crear indicador, obtener indicadores y eliminar indicadores.</span><span class="sxs-lookup"><span data-stu-id="2e994-138">Run API call such as create Indicator, get Indicators and delete Indicators.</span></span>
<span data-ttu-id="2e994-139">Usuarios</span><span class="sxs-lookup"><span data-stu-id="2e994-139">Users</span></span> | <span data-ttu-id="2e994-140">Ejecute llamadas API como obtener alertas relacionadas con el usuario y dispositivos relacionados con el usuario.</span><span class="sxs-lookup"><span data-stu-id="2e994-140">Run API calls such as get user-related alerts and user-related devices.</span></span>
<span data-ttu-id="2e994-141">Puntuación</span><span class="sxs-lookup"><span data-stu-id="2e994-141">Score</span></span> | <span data-ttu-id="2e994-142">Ejecuta llamadas API como obtener puntuación de exposición o obtener puntuación segura del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2e994-142">Run API calls such as get exposure score or get device secure score.</span></span>
<span data-ttu-id="2e994-143">Software</span><span class="sxs-lookup"><span data-stu-id="2e994-143">Software</span></span> | <span data-ttu-id="2e994-144">Ejecute llamadas API como, por ejemplo, enumerar vulnerabilidades por software.</span><span class="sxs-lookup"><span data-stu-id="2e994-144">Run API calls such as list vulnerabilities by software.</span></span>
<span data-ttu-id="2e994-145">Vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="2e994-145">Vulnerability</span></span> | <span data-ttu-id="2e994-146">Ejecute llamadas API, como los dispositivos de lista por vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="2e994-146">Run API calls such as list devices by vulnerability.</span></span>
<span data-ttu-id="2e994-147">Recomendación</span><span class="sxs-lookup"><span data-stu-id="2e994-147">Recommendation</span></span> | <span data-ttu-id="2e994-148">Ejecute llamadas API como Obtener recomendación por identificador.</span><span class="sxs-lookup"><span data-stu-id="2e994-148">Run API calls such as Get recommendation by ID.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e994-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e994-149">See also</span></span>
- [<span data-ttu-id="2e994-150">Microsoft Defender para api de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2e994-150">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
