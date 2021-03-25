---
title: AISLAR API de máquina
description: Obtenga información sobre cómo usar la API de la máquina de aislar para aislar un dispositivo del acceso a la red externa en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, dispositivo aislado
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
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187841"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="05c39-104">AISLAR API de máquina</span><span class="sxs-lookup"><span data-stu-id="05c39-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="05c39-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="05c39-105">**Applies to:**</span></span>
- [<span data-ttu-id="05c39-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="05c39-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="05c39-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05c39-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="05c39-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="05c39-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="05c39-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="05c39-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="05c39-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="05c39-110">API description</span></span>
<span data-ttu-id="05c39-111">Aísla un dispositivo del acceso a la red externa.</span><span class="sxs-lookup"><span data-stu-id="05c39-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="05c39-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="05c39-112">Limitations</span></span>
1. <span data-ttu-id="05c39-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="05c39-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="05c39-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="05c39-114">Permissions</span></span>
<span data-ttu-id="05c39-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="05c39-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="05c39-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="05c39-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="05c39-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="05c39-117">Permission type</span></span> |   <span data-ttu-id="05c39-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="05c39-118">Permission</span></span>  |   <span data-ttu-id="05c39-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="05c39-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="05c39-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="05c39-120">Application</span></span> |   <span data-ttu-id="05c39-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="05c39-121">Machine.Isolate</span></span> |   <span data-ttu-id="05c39-122">'Aislar máquina'</span><span class="sxs-lookup"><span data-stu-id="05c39-122">'Isolate machine'</span></span>
<span data-ttu-id="05c39-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="05c39-123">Delegated (work or school account)</span></span> | <span data-ttu-id="05c39-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="05c39-124">Machine.Isolate</span></span> |  <span data-ttu-id="05c39-125">'Aislar máquina'</span><span class="sxs-lookup"><span data-stu-id="05c39-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="05c39-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="05c39-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="05c39-127">El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="05c39-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="05c39-128">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="05c39-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="05c39-129">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="05c39-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="05c39-130">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="05c39-130">Request headers</span></span>

<span data-ttu-id="05c39-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="05c39-131">Name</span></span> | <span data-ttu-id="05c39-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="05c39-132">Type</span></span> | <span data-ttu-id="05c39-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="05c39-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="05c39-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="05c39-134">Authorization</span></span> | <span data-ttu-id="05c39-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="05c39-135">String</span></span> | <span data-ttu-id="05c39-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="05c39-136">Bearer {token}.</span></span> <span data-ttu-id="05c39-137">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="05c39-137">**Required**.</span></span>
<span data-ttu-id="05c39-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="05c39-138">Content-Type</span></span> | <span data-ttu-id="05c39-139">string</span><span class="sxs-lookup"><span data-stu-id="05c39-139">string</span></span> | <span data-ttu-id="05c39-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="05c39-140">application/json.</span></span> <span data-ttu-id="05c39-141">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="05c39-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="05c39-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="05c39-142">Request body</span></span>
<span data-ttu-id="05c39-143">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="05c39-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="05c39-144">Parámetro</span><span class="sxs-lookup"><span data-stu-id="05c39-144">Parameter</span></span> | <span data-ttu-id="05c39-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="05c39-145">Type</span></span>    | <span data-ttu-id="05c39-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="05c39-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="05c39-147">Comentario</span><span class="sxs-lookup"><span data-stu-id="05c39-147">Comment</span></span> |   <span data-ttu-id="05c39-148">Cadena</span><span class="sxs-lookup"><span data-stu-id="05c39-148">String</span></span> |    <span data-ttu-id="05c39-149">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="05c39-149">Comment to associate with the action.</span></span> <span data-ttu-id="05c39-150">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="05c39-150">**Required**.</span></span>
<span data-ttu-id="05c39-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="05c39-151">IsolationType</span></span>   | <span data-ttu-id="05c39-152">Cadena</span><span class="sxs-lookup"><span data-stu-id="05c39-152">String</span></span> |  <span data-ttu-id="05c39-153">Tipo de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="05c39-153">Type of the isolation.</span></span> <span data-ttu-id="05c39-154">Los valores permitidos son: "Completo" o "Selectivo".</span><span class="sxs-lookup"><span data-stu-id="05c39-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="05c39-155">**IsolationType** controla el tipo de aislamiento que se debe realizar y puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="05c39-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="05c39-156">Full: aislamiento total</span><span class="sxs-lookup"><span data-stu-id="05c39-156">Full – Full isolation</span></span>
- <span data-ttu-id="05c39-157">Selectivo: restringir únicamente el acceso a la red de un conjunto limitado de aplicaciones (consulte Aislar dispositivos [de la red](respond-machine-alerts.md#isolate-devices-from-the-network) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="05c39-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="05c39-158">Respuesta</span><span class="sxs-lookup"><span data-stu-id="05c39-158">Response</span></span>
<span data-ttu-id="05c39-159">Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="05c39-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="05c39-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05c39-160">Example</span></span>

<span data-ttu-id="05c39-161">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="05c39-161">**Request**</span></span>

<span data-ttu-id="05c39-162">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="05c39-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="05c39-163">Para liberar un dispositivo del aislamiento, consulta [Liberar dispositivo de aislamiento.](unisolate-machine.md)</span><span class="sxs-lookup"><span data-stu-id="05c39-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>
