---
title: Restringir api de ejecución de aplicaciones
description: Use esta API para crear llamadas relacionadas con la restricción de la ejecución de una aplicación.
keywords: api, api de gráfico, api admitidas, paquete de investigación de recopilación
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
ms.openlocfilehash: 7195e91a3a9b7aef6977c925f2c8689d3e461815
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771578"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="b426d-104">Restringir api de ejecución de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b426d-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b426d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b426d-105">**Applies to:**</span></span>
- [<span data-ttu-id="b426d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b426d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b426d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b426d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b426d-108">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b426d-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b426d-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b426d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b426d-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b426d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b426d-111">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="b426d-111">API description</span></span>
<span data-ttu-id="b426d-112">Restringir la ejecución de todas las aplicaciones en el dispositivo excepto un conjunto predefinido.</span><span class="sxs-lookup"><span data-stu-id="b426d-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="b426d-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="b426d-113">Limitations</span></span>
1. <span data-ttu-id="b426d-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="b426d-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="b426d-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="b426d-115">Permissions</span></span>
<span data-ttu-id="b426d-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="b426d-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b426d-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b426d-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b426d-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="b426d-118">Permission type</span></span> |   <span data-ttu-id="b426d-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="b426d-119">Permission</span></span>  |   <span data-ttu-id="b426d-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="b426d-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b426d-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="b426d-121">Application</span></span> |   <span data-ttu-id="b426d-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="b426d-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="b426d-123">'Restringir la ejecución de código'</span><span class="sxs-lookup"><span data-stu-id="b426d-123">'Restrict code execution'</span></span>
<span data-ttu-id="b426d-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="b426d-124">Delegated (work or school account)</span></span> | <span data-ttu-id="b426d-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="b426d-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="b426d-126">'Restringir la ejecución de código'</span><span class="sxs-lookup"><span data-stu-id="b426d-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="b426d-127">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="b426d-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b426d-128">El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="b426d-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b426d-129">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="b426d-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b426d-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="b426d-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="b426d-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="b426d-131">Request headers</span></span>

<span data-ttu-id="b426d-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="b426d-132">Name</span></span> | <span data-ttu-id="b426d-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="b426d-133">Type</span></span> | <span data-ttu-id="b426d-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="b426d-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="b426d-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="b426d-135">Authorization</span></span> | <span data-ttu-id="b426d-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="b426d-136">String</span></span> | <span data-ttu-id="b426d-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="b426d-137">Bearer {token}.</span></span> <span data-ttu-id="b426d-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="b426d-138">**Required**.</span></span>
<span data-ttu-id="b426d-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b426d-139">Content-Type</span></span> | <span data-ttu-id="b426d-140">cadena</span><span class="sxs-lookup"><span data-stu-id="b426d-140">string</span></span> | <span data-ttu-id="b426d-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="b426d-141">application/json.</span></span> <span data-ttu-id="b426d-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="b426d-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b426d-143">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="b426d-143">Request body</span></span>
<span data-ttu-id="b426d-144">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="b426d-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="b426d-145">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b426d-145">Parameter</span></span> | <span data-ttu-id="b426d-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="b426d-146">Type</span></span>    | <span data-ttu-id="b426d-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="b426d-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="b426d-148">Comentario</span><span class="sxs-lookup"><span data-stu-id="b426d-148">Comment</span></span> |   <span data-ttu-id="b426d-149">Cadena</span><span class="sxs-lookup"><span data-stu-id="b426d-149">String</span></span> |    <span data-ttu-id="b426d-150">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="b426d-150">Comment to associate with the action.</span></span> <span data-ttu-id="b426d-151">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="b426d-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="b426d-152">Respuesta</span><span class="sxs-lookup"><span data-stu-id="b426d-152">Response</span></span>
<span data-ttu-id="b426d-153">Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b426d-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="b426d-154">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b426d-154">Example</span></span>

<span data-ttu-id="b426d-155">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="b426d-155">**Request**</span></span>

<span data-ttu-id="b426d-156">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="b426d-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="b426d-157">Para quitar la restricción de ejecución de código de un dispositivo, consulta [Quitar restricción de aplicación.](unrestrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="b426d-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
