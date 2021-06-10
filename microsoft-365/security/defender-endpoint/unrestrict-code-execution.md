---
title: Quitar la API de restricción de aplicaciones
description: Use esta API para crear llamadas relacionadas con la eliminación de una restricción de la ejecución de aplicaciones.
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
ms.openlocfilehash: 989e44647a5f0661bfdefa184c6c26f4cdf2b456
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770882"
---
# <a name="remove-app-restriction-api"></a><span data-ttu-id="d9ad6-104">Quitar la API de restricción de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d9ad6-104">Remove app restriction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d9ad6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d9ad6-105">**Applies to:**</span></span>
- [<span data-ttu-id="d9ad6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d9ad6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d9ad6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9ad6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d9ad6-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="d9ad6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d9ad6-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d9ad6-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="d9ad6-110">API description</span></span>
<span data-ttu-id="d9ad6-111">Habilitar la ejecución de cualquier aplicación en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-111">Enable execution of any application on the device.</span></span>


## <a name="limitations"></a><span data-ttu-id="d9ad6-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="d9ad6-112">Limitations</span></span>
1. <span data-ttu-id="d9ad6-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="d9ad6-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="d9ad6-114">Permissions</span></span>
<span data-ttu-id="d9ad6-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d9ad6-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d9ad6-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d9ad6-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="d9ad6-117">Permission type</span></span> |   <span data-ttu-id="d9ad6-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="d9ad6-118">Permission</span></span>  |   <span data-ttu-id="d9ad6-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="d9ad6-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d9ad6-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d9ad6-120">Application</span></span> |   <span data-ttu-id="d9ad6-121">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="d9ad6-121">Machine.RestrictExecution</span></span> | <span data-ttu-id="d9ad6-122">'Restringir la ejecución de código'</span><span class="sxs-lookup"><span data-stu-id="d9ad6-122">'Restrict code execution'</span></span>
<span data-ttu-id="d9ad6-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="d9ad6-123">Delegated (work or school account)</span></span> | <span data-ttu-id="d9ad6-124">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="d9ad6-124">Machine.RestrictExecution</span></span> | <span data-ttu-id="d9ad6-125">'Restringir la ejecución de código'</span><span class="sxs-lookup"><span data-stu-id="d9ad6-125">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="d9ad6-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="d9ad6-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d9ad6-127">El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d9ad6-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d9ad6-128">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d9ad6-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d9ad6-129">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="d9ad6-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unrestrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="d9ad6-130">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="d9ad6-130">Request headers</span></span>
<span data-ttu-id="d9ad6-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="d9ad6-131">Name</span></span> | <span data-ttu-id="d9ad6-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="d9ad6-132">Type</span></span> | <span data-ttu-id="d9ad6-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9ad6-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="d9ad6-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="d9ad6-134">Authorization</span></span> | <span data-ttu-id="d9ad6-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="d9ad6-135">String</span></span> | <span data-ttu-id="d9ad6-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-136">Bearer {token}.</span></span> <span data-ttu-id="d9ad6-137">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-137">**Required**.</span></span>
<span data-ttu-id="d9ad6-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d9ad6-138">Content-Type</span></span> | <span data-ttu-id="d9ad6-139">cadena</span><span class="sxs-lookup"><span data-stu-id="d9ad6-139">string</span></span> | <span data-ttu-id="d9ad6-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-140">application/json.</span></span> <span data-ttu-id="d9ad6-141">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d9ad6-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="d9ad6-142">Request body</span></span>
<span data-ttu-id="d9ad6-143">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="d9ad6-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="d9ad6-144">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d9ad6-144">Parameter</span></span> | <span data-ttu-id="d9ad6-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="d9ad6-145">Type</span></span>    | <span data-ttu-id="d9ad6-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9ad6-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="d9ad6-147">Comentario</span><span class="sxs-lookup"><span data-stu-id="d9ad6-147">Comment</span></span> |   <span data-ttu-id="d9ad6-148">Cadena</span><span class="sxs-lookup"><span data-stu-id="d9ad6-148">String</span></span> | <span data-ttu-id="d9ad6-149">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-149">Comment to associate with the action.</span></span> <span data-ttu-id="d9ad6-150">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="d9ad6-151">Respuesta</span><span class="sxs-lookup"><span data-stu-id="d9ad6-151">Response</span></span>
<span data-ttu-id="d9ad6-152">Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="d9ad6-153">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d9ad6-153">Example</span></span>

<span data-ttu-id="d9ad6-154">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="d9ad6-154">**Request**</span></span>

<span data-ttu-id="d9ad6-155">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d9ad6-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unrestrictCodeExecution 
```

```json
{
  "Comment": "Unrestrict code execution since machine was cleaned and validated"
}

```


<span data-ttu-id="d9ad6-156">Para restringir la ejecución de código en un dispositivo, consulta [Restringir la ejecución de la aplicación](restrict-code-execution.md).</span><span class="sxs-lookup"><span data-stu-id="d9ad6-156">To restrict code execution on a device, see [Restrict app execution](restrict-code-execution.md).</span></span>
