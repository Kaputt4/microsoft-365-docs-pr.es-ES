---
title: Buscar dispositivos por API de etiqueta
description: Buscar todos los dispositivos que contienen etiqueta specifc
keywords: apis, api compatibles, get, device, find, find device, by tag, tag, tag
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 6460860828acd5ea0c3509e9eb06061d2a9a0cc2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200154"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="a66e4-104">Buscar dispositivos por API de etiqueta</span><span class="sxs-lookup"><span data-stu-id="a66e4-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a66e4-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a66e4-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a66e4-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="a66e4-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a66e4-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a66e4-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a66e4-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="a66e4-108">API description</span></span>
<span data-ttu-id="a66e4-109">Buscar [máquinas](machine.md) por [etiqueta](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="a66e4-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="a66e4-110">```startswith``` se admite la consulta.</span><span class="sxs-lookup"><span data-stu-id="a66e4-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="a66e4-111">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="a66e4-111">Limitations</span></span>
1. <span data-ttu-id="a66e4-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="a66e4-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="a66e4-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="a66e4-113">Permissions</span></span>
<span data-ttu-id="a66e4-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="a66e4-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a66e4-115">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a66e4-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a66e4-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="a66e4-116">Permission type</span></span> |   <span data-ttu-id="a66e4-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="a66e4-117">Permission</span></span>  |   <span data-ttu-id="a66e4-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="a66e4-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a66e4-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="a66e4-119">Application</span></span> |   <span data-ttu-id="a66e4-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="a66e4-120">Machine.Read.All</span></span> |  <span data-ttu-id="a66e4-121">'Leer todos los perfiles de máquina'</span><span class="sxs-lookup"><span data-stu-id="a66e4-121">'Read all machine profiles'</span></span>
<span data-ttu-id="a66e4-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="a66e4-122">Application</span></span> |   <span data-ttu-id="a66e4-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="a66e4-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="a66e4-124">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="a66e4-124">'Read and write all machine information'</span></span>
<span data-ttu-id="a66e4-125">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="a66e4-125">Delegated (work or school account)</span></span> | <span data-ttu-id="a66e4-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="a66e4-126">Machine.Read</span></span> | <span data-ttu-id="a66e4-127">'Leer información de máquina'</span><span class="sxs-lookup"><span data-stu-id="a66e4-127">'Read machine information'</span></span>
<span data-ttu-id="a66e4-128">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="a66e4-128">Delegated (work or school account)</span></span> | <span data-ttu-id="a66e4-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a66e4-129">Machine.ReadWrite</span></span> | <span data-ttu-id="a66e4-130">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="a66e4-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="a66e4-131">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="a66e4-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="a66e4-132">La respuesta incluirá solo los dispositivos a los que el usuario tenga acceso en función de la configuración del grupo de dispositivos (consulta [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="a66e4-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="a66e4-133">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="a66e4-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="a66e4-134">La respuesta incluirá solo los dispositivos a los que el usuario tenga acceso en función de la configuración del grupo de dispositivos (consulta [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="a66e4-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a66e4-135">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="a66e4-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="a66e4-136">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="a66e4-136">Request headers</span></span>

<span data-ttu-id="a66e4-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="a66e4-137">Name</span></span> | <span data-ttu-id="a66e4-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="a66e4-138">Type</span></span> | <span data-ttu-id="a66e4-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="a66e4-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="a66e4-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="a66e4-140">Authorization</span></span> | <span data-ttu-id="a66e4-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="a66e4-141">String</span></span> | <span data-ttu-id="a66e4-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="a66e4-142">Bearer {token}.</span></span> <span data-ttu-id="a66e4-143">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="a66e4-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="a66e4-144">Parámetros uri de solicitud</span><span class="sxs-lookup"><span data-stu-id="a66e4-144">Request URI parameters</span></span>

<span data-ttu-id="a66e4-145">Nombre</span><span class="sxs-lookup"><span data-stu-id="a66e4-145">Name</span></span> | <span data-ttu-id="a66e4-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="a66e4-146">Type</span></span> | <span data-ttu-id="a66e4-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="a66e4-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="a66e4-148">tag</span><span class="sxs-lookup"><span data-stu-id="a66e4-148">tag</span></span> | <span data-ttu-id="a66e4-149">Cadena</span><span class="sxs-lookup"><span data-stu-id="a66e4-149">String</span></span> | <span data-ttu-id="a66e4-150">El nombre de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="a66e4-150">The tag name.</span></span> <span data-ttu-id="a66e4-151">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="a66e4-151">**Required**.</span></span>
<span data-ttu-id="a66e4-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="a66e4-152">useStartsWithFilter</span></span> | <span data-ttu-id="a66e4-153">Booleano</span><span class="sxs-lookup"><span data-stu-id="a66e4-153">Boolean</span></span> | <span data-ttu-id="a66e4-154">Cuando se establece en true, la búsqueda buscará todos los dispositivos con el nombre de etiqueta que comiencen por la etiqueta dada en la consulta.</span><span class="sxs-lookup"><span data-stu-id="a66e4-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="a66e4-155">Valores predeterminados de falso.</span><span class="sxs-lookup"><span data-stu-id="a66e4-155">Defaults to false.</span></span> <span data-ttu-id="a66e4-156">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="a66e4-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a66e4-157">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="a66e4-157">Request body</span></span>
<span data-ttu-id="a66e4-158">En blanco</span><span class="sxs-lookup"><span data-stu-id="a66e4-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a66e4-159">Respuesta</span><span class="sxs-lookup"><span data-stu-id="a66e4-159">Response</span></span>
<span data-ttu-id="a66e4-160">Si se realiza correctamente: 200 Aceptar con una lista de las máquinas en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a66e4-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="a66e4-161">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a66e4-161">Example</span></span>

<span data-ttu-id="a66e4-162">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="a66e4-162">**Request**</span></span>

<span data-ttu-id="a66e4-163">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a66e4-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```