---
title: Obtener API de incidentes
description: Obtenga información sobre cómo usar la API Obtener incidentes para obtener un único incidente en Microsoft 365 Defender.
keywords: apis, api de gráficos, api admitidas, get, file, hash
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
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289612"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="3ade8-104">Obtener API de información de incidentes</span><span class="sxs-lookup"><span data-stu-id="3ade8-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ade8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3ade8-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ade8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ade8-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3ade8-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="3ade8-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ade8-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="3ade8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3ade8-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="3ade8-109">API description</span></span>

<span data-ttu-id="3ade8-110">Recupera un incidente específico por su identificador</span><span class="sxs-lookup"><span data-stu-id="3ade8-110">Retrieves a specific incident by its ID</span></span>

## <a name="limitations"></a><span data-ttu-id="3ade8-111">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="3ade8-111">Limitations</span></span>

1. <span data-ttu-id="3ade8-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="3ade8-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3ade8-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="3ade8-113">Permissions</span></span>

<span data-ttu-id="3ade8-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="3ade8-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="3ade8-115">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="3ade8-115">Permission type</span></span> | <span data-ttu-id="3ade8-116">Permiso</span><span class="sxs-lookup"><span data-stu-id="3ade8-116">Permission</span></span> | <span data-ttu-id="3ade8-117">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="3ade8-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3ade8-118">Aplicación</span><span class="sxs-lookup"><span data-stu-id="3ade8-118">Application</span></span> | <span data-ttu-id="3ade8-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="3ade8-119">Incident.Read.All</span></span> | <span data-ttu-id="3ade8-120">'Leer todos los incidentes'</span><span class="sxs-lookup"><span data-stu-id="3ade8-120">'Read all Incidents'</span></span>
<span data-ttu-id="3ade8-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="3ade8-121">Application</span></span> | <span data-ttu-id="3ade8-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3ade8-122">Incident.ReadWrite.All</span></span> | <span data-ttu-id="3ade8-123">'Leer y escribir todos los incidentes'</span><span class="sxs-lookup"><span data-stu-id="3ade8-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="3ade8-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="3ade8-124">Delegated (work or school account)</span></span> | <span data-ttu-id="3ade8-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="3ade8-125">Incident.Read</span></span> | <span data-ttu-id="3ade8-126">'Leer incidentes'</span><span class="sxs-lookup"><span data-stu-id="3ade8-126">'Read Incidents'</span></span>
<span data-ttu-id="3ade8-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="3ade8-127">Delegated (work or school account)</span></span> | <span data-ttu-id="3ade8-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3ade8-128">Incident.ReadWrite</span></span> | <span data-ttu-id="3ade8-129">'Leer y escribir incidentes'</span><span class="sxs-lookup"><span data-stu-id="3ade8-129">'Read and write Incidents'</span></span>

> [!NOTE]
>
> <span data-ttu-id="3ade8-130">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="3ade8-130">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="3ade8-131">El usuario debe tener al menos el siguiente permiso de función: 'Ver datos'</span><span class="sxs-lookup"><span data-stu-id="3ade8-131">The user needs to have at least the following role permission: 'View Data'</span></span>
> - <span data-ttu-id="3ade8-132">La respuesta solo incluirá incidentes a los que el usuario esté expuesto</span><span class="sxs-lookup"><span data-stu-id="3ade8-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="3ade8-133">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="3ade8-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="3ade8-134">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="3ade8-134">Request headers</span></span>

<span data-ttu-id="3ade8-135">Nombre</span><span class="sxs-lookup"><span data-stu-id="3ade8-135">Name</span></span> | <span data-ttu-id="3ade8-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="3ade8-136">Type</span></span> | <span data-ttu-id="3ade8-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ade8-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="3ade8-138">Authorization</span><span class="sxs-lookup"><span data-stu-id="3ade8-138">Authorization</span></span> | <span data-ttu-id="3ade8-139">Cadena</span><span class="sxs-lookup"><span data-stu-id="3ade8-139">String</span></span> | <span data-ttu-id="3ade8-140">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="3ade8-140">Bearer {token}.</span></span> <span data-ttu-id="3ade8-141">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="3ade8-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3ade8-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="3ade8-142">Request body</span></span>

<span data-ttu-id="3ade8-143">En blanco</span><span class="sxs-lookup"><span data-stu-id="3ade8-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3ade8-144">Respuesta</span><span class="sxs-lookup"><span data-stu-id="3ade8-144">Response</span></span>

<span data-ttu-id="3ade8-145">Si se realiza correctamente, este método devuelve 200 Ok y la entidad incident en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="3ade8-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="3ade8-146">Si no se encontró un incidente con el identificador especificado: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="3ade8-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="3ade8-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ade8-147">Example</span></span>

<span data-ttu-id="3ade8-148">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="3ade8-148">**Request**</span></span>

<span data-ttu-id="3ade8-149">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3ade8-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
