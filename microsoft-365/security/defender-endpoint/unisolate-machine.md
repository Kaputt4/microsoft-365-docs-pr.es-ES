---
title: Liberar dispositivo de la API de aislamiento
description: Usa esta API para crear llamadas relacionadas para liberar un dispositivo del aislamiento.
keywords: api, api de gráfico, api admitidas, quitar el dispositivo del aislamiento
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
ms.openlocfilehash: 3ed2e7968464320e41e47ad734026bdd9b323ceb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771278"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="a7fe2-104">Liberar dispositivo de la API de aislamiento</span><span class="sxs-lookup"><span data-stu-id="a7fe2-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a7fe2-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a7fe2-105">**Applies to:**</span></span> 
- [<span data-ttu-id="a7fe2-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a7fe2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a7fe2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7fe2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="a7fe2-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="a7fe2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a7fe2-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a7fe2-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="a7fe2-110">API description</span></span>
<span data-ttu-id="a7fe2-111">Deshacer el aislamiento de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="a7fe2-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="a7fe2-112">Limitations</span></span>
1. <span data-ttu-id="a7fe2-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="a7fe2-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="a7fe2-114">Permissions</span></span>
<span data-ttu-id="a7fe2-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a7fe2-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a7fe2-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a7fe2-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="a7fe2-117">Permission type</span></span> |   <span data-ttu-id="a7fe2-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="a7fe2-118">Permission</span></span>  |   <span data-ttu-id="a7fe2-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="a7fe2-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a7fe2-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="a7fe2-120">Application</span></span> |   <span data-ttu-id="a7fe2-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="a7fe2-121">Machine.Isolate</span></span> |   <span data-ttu-id="a7fe2-122">'Aislar máquina'</span><span class="sxs-lookup"><span data-stu-id="a7fe2-122">'Isolate machine'</span></span>
<span data-ttu-id="a7fe2-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="a7fe2-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="a7fe2-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="a7fe2-124">Machine.Isolate</span></span> |   <span data-ttu-id="a7fe2-125">'Aislar máquina'</span><span class="sxs-lookup"><span data-stu-id="a7fe2-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="a7fe2-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="a7fe2-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a7fe2-127">El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="a7fe2-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="a7fe2-128">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="a7fe2-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a7fe2-129">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="a7fe2-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="a7fe2-130">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="a7fe2-130">Request headers</span></span>

<span data-ttu-id="a7fe2-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7fe2-131">Name</span></span> | <span data-ttu-id="a7fe2-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="a7fe2-132">Type</span></span> | <span data-ttu-id="a7fe2-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7fe2-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="a7fe2-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="a7fe2-134">Authorization</span></span> | <span data-ttu-id="a7fe2-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="a7fe2-135">String</span></span> | <span data-ttu-id="a7fe2-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-136">Bearer {token}.</span></span> <span data-ttu-id="a7fe2-137">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-137">**Required**.</span></span>
<span data-ttu-id="a7fe2-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a7fe2-138">Content-Type</span></span> | <span data-ttu-id="a7fe2-139">cadena</span><span class="sxs-lookup"><span data-stu-id="a7fe2-139">string</span></span> | <span data-ttu-id="a7fe2-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-140">application/json.</span></span> <span data-ttu-id="a7fe2-141">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a7fe2-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="a7fe2-142">Request body</span></span>
<span data-ttu-id="a7fe2-143">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a7fe2-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="a7fe2-144">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a7fe2-144">Parameter</span></span> | <span data-ttu-id="a7fe2-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="a7fe2-145">Type</span></span>    | <span data-ttu-id="a7fe2-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7fe2-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="a7fe2-147">Comentario</span><span class="sxs-lookup"><span data-stu-id="a7fe2-147">Comment</span></span> |   <span data-ttu-id="a7fe2-148">Cadena</span><span class="sxs-lookup"><span data-stu-id="a7fe2-148">String</span></span> |    <span data-ttu-id="a7fe2-149">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-149">Comment to associate with the action.</span></span> <span data-ttu-id="a7fe2-150">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="a7fe2-151">Respuesta</span><span class="sxs-lookup"><span data-stu-id="a7fe2-151">Response</span></span>
<span data-ttu-id="a7fe2-152">Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="a7fe2-153">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7fe2-153">Example</span></span>

<span data-ttu-id="a7fe2-154">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="a7fe2-154">**Request**</span></span>

<span data-ttu-id="a7fe2-155">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a7fe2-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="a7fe2-156">Para aislar un dispositivo, consulta [Aislar dispositivo](isolate-machine.md).</span><span class="sxs-lookup"><span data-stu-id="a7fe2-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>

