---
title: Cancelar API de acción de máquina
description: Obtenga información sobre cómo cancelar una acción de máquina iniciada ya
keywords: apis, api de gráficos,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879801"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="16980-104">Cancelar API de acción de máquina</span><span class="sxs-lookup"><span data-stu-id="16980-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16980-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="16980-105">**Applies to:**</span></span>
- [<span data-ttu-id="16980-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="16980-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="16980-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="16980-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="16980-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="16980-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="16980-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="16980-109">API description</span></span>

<span data-ttu-id="16980-110">Cancelar una acción de máquina ya iniciada que aún no está en estado final (completada, cancelada, fallida).</span><span class="sxs-lookup"><span data-stu-id="16980-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="16980-111">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="16980-111">Limitations</span></span>

1.  <span data-ttu-id="16980-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="16980-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="16980-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="16980-113">Permissions</span></span>

<span data-ttu-id="16980-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="16980-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="16980-115">Para obtener más información, incluido cómo elegir permisos, vea [Get started](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="16980-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="16980-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="16980-116">Permission    type</span></span>     |     <span data-ttu-id="16980-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="16980-117">Permission</span></span>     |    <span data-ttu-id="16980-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="16980-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="16980-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="16980-119">Application</span></span>    |    <br><span data-ttu-id="16980-120">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="16980-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="16980-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="16980-121">Machine.Isolate</span></span>   <br><span data-ttu-id="16980-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="16980-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="16980-123">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="16980-123">Machine.Scan</span></span><br>   <span data-ttu-id="16980-124">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="16980-124">Machine.Offboard</span></span><br>   <span data-ttu-id="16980-125">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="16980-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="16980-126">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="16980-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="16980-127">Recopilar forenses</span><span class="sxs-lookup"><span data-stu-id="16980-127">Collect   forensics</span></span>   <br><span data-ttu-id="16980-128">Aislar máquina</span><span class="sxs-lookup"><span data-stu-id="16980-128">Isolate   machine</span></span><br><span data-ttu-id="16980-129">Restringir la ejecución de código</span><span class="sxs-lookup"><span data-stu-id="16980-129">Restrict   code execution</span></span><br>  <span data-ttu-id="16980-130">Máquina de digitalización</span><span class="sxs-lookup"><span data-stu-id="16980-130">Scan   machine</span></span><br>  <span data-ttu-id="16980-131">Máquina offboard</span><span class="sxs-lookup"><span data-stu-id="16980-131">Offboard   machine</span></span><br>   <span data-ttu-id="16980-132">Detener y poner en cuarentena</span><span class="sxs-lookup"><span data-stu-id="16980-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="16980-133">Ejecutar respuesta en directo en un equipo específico</span><span class="sxs-lookup"><span data-stu-id="16980-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="16980-134">Delegado (cuenta de trabajo o escuela)</span><span class="sxs-lookup"><span data-stu-id="16980-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="16980-135">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="16980-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="16980-136">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="16980-136">Machine.Isolate</span></span>    <br><span data-ttu-id="16980-137">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="16980-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="16980-138">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="16980-138">Machine.Scan</span></span><br>   <span data-ttu-id="16980-139">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="16980-139">Machine.Offboard</span></span><br>   <span data-ttu-id="16980-140">Machine.StopAndQuarantineMachine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="16980-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="16980-141">Recopilar forenses</span><span class="sxs-lookup"><span data-stu-id="16980-141">Collect   forensics</span></span><br>   <span data-ttu-id="16980-142">Aislar máquina</span><span class="sxs-lookup"><span data-stu-id="16980-142">Isolate   machine</span></span><br>  <span data-ttu-id="16980-143">Restringir la ejecución de código</span><span class="sxs-lookup"><span data-stu-id="16980-143">Restrict   code execution</span></span><br> <span data-ttu-id="16980-144">Máquina de digitalización</span><span class="sxs-lookup"><span data-stu-id="16980-144">Scan   machine</span></span><br><span data-ttu-id="16980-145">Máquina offboard</span><span class="sxs-lookup"><span data-stu-id="16980-145">Offboard   machine</span></span><br> <span data-ttu-id="16980-146">Detener y poner en cuarentena</span><span class="sxs-lookup"><span data-stu-id="16980-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="16980-147">Ejecutar respuesta en directo en un equipo específico</span><span class="sxs-lookup"><span data-stu-id="16980-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="16980-148">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="16980-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="16980-149">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="16980-149">Request headers</span></span>

| <span data-ttu-id="16980-150">Nombre</span><span class="sxs-lookup"><span data-stu-id="16980-150">Name</span></span>      | <span data-ttu-id="16980-151">Tipo</span><span class="sxs-lookup"><span data-stu-id="16980-151">Type</span></span> | <span data-ttu-id="16980-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="16980-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="16980-153">Authorization</span><span class="sxs-lookup"><span data-stu-id="16980-153">Authorization</span></span> | <span data-ttu-id="16980-154">Cadena</span><span class="sxs-lookup"><span data-stu-id="16980-154">String</span></span>   | <span data-ttu-id="16980-p103">{token} de portador. Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="16980-p103">Bearer {token}. Required.</span></span>   |
| <span data-ttu-id="16980-157">Content-Type</span><span class="sxs-lookup"><span data-stu-id="16980-157">Content-Type</span></span>  | <span data-ttu-id="16980-158">string</span><span class="sxs-lookup"><span data-stu-id="16980-158">string</span></span>   | <span data-ttu-id="16980-p104">application/json. Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="16980-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="16980-161">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="16980-161">Request body</span></span>

| <span data-ttu-id="16980-162">Parámetro</span><span class="sxs-lookup"><span data-stu-id="16980-162">Parameter</span></span> | <span data-ttu-id="16980-163">Tipo</span><span class="sxs-lookup"><span data-stu-id="16980-163">Type</span></span> | <span data-ttu-id="16980-164">Description</span><span class="sxs-lookup"><span data-stu-id="16980-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="16980-165">Comentario</span><span class="sxs-lookup"><span data-stu-id="16980-165">Comment</span></span>       | <span data-ttu-id="16980-166">Cadena</span><span class="sxs-lookup"><span data-stu-id="16980-166">String</span></span>   | <span data-ttu-id="16980-167">Comentario para asociarlo con la acción de cancelación.</span><span class="sxs-lookup"><span data-stu-id="16980-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="16980-168">Respuesta</span><span class="sxs-lookup"><span data-stu-id="16980-168">Response</span></span>

<span data-ttu-id="16980-169">Si se realiza correctamente, este método devuelve 200, código de respuesta Ok con una entidad Machine Action.</span><span class="sxs-lookup"><span data-stu-id="16980-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="16980-170">Si no se encontró la entidad de acción de la máquina con el identificador especificado: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="16980-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="16980-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16980-171">Example</span></span>

<span data-ttu-id="16980-172">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="16980-172">**Request**</span></span>

<span data-ttu-id="16980-173">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="16980-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="16980-174">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="16980-174">Related topic</span></span>

- [<span data-ttu-id="16980-175">Obtener API de acción de máquina</span><span class="sxs-lookup"><span data-stu-id="16980-175">Get machine action API</span></span>](get-machineaction-object.md)