---
title: RECOPILAR API de paquetes de investigación
description: Usa esta API para crear llamadas relacionadas con la recopilación de un paquete de investigación desde un dispositivo.
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
ms.technology: mde
ms.openlocfilehash: 1e24236aae1922705c1711042f0426251a979ede
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167084"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="bc099-104">RECOPILAR API de paquetes de investigación</span><span class="sxs-lookup"><span data-stu-id="bc099-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc099-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bc099-105">**Applies to:**</span></span>
- [<span data-ttu-id="bc099-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bc099-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bc099-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc099-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="bc099-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="bc099-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bc099-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bc099-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="bc099-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="bc099-110">API description</span></span>
<span data-ttu-id="bc099-111">Recopilar el paquete de investigación de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bc099-111">Collect investigation package from a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="bc099-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="bc099-112">Limitations</span></span>
1. <span data-ttu-id="bc099-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="bc099-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="bc099-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="bc099-114">Permissions</span></span>
<span data-ttu-id="bc099-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="bc099-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bc099-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bc099-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bc099-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="bc099-117">Permission type</span></span> |   <span data-ttu-id="bc099-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="bc099-118">Permission</span></span>  |   <span data-ttu-id="bc099-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="bc099-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bc099-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="bc099-120">Application</span></span> |   <span data-ttu-id="bc099-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="bc099-121">Machine.CollectForensics</span></span> |  <span data-ttu-id="bc099-122">'Recopilar forenses'</span><span class="sxs-lookup"><span data-stu-id="bc099-122">'Collect forensics'</span></span>
<span data-ttu-id="bc099-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="bc099-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="bc099-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="bc099-124">Machine.CollectForensics</span></span> |  <span data-ttu-id="bc099-125">'Recopilar forenses'</span><span class="sxs-lookup"><span data-stu-id="bc099-125">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="bc099-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="bc099-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="bc099-127">El usuario debe tener al menos el siguiente permiso de función: "Investigación de alertas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="bc099-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="bc099-128">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="bc099-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="bc099-129">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="bc099-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="bc099-130">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="bc099-130">Request headers</span></span>

<span data-ttu-id="bc099-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="bc099-131">Name</span></span> | <span data-ttu-id="bc099-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="bc099-132">Type</span></span> | <span data-ttu-id="bc099-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc099-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="bc099-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="bc099-134">Authorization</span></span> | <span data-ttu-id="bc099-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="bc099-135">String</span></span> | <span data-ttu-id="bc099-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="bc099-136">Bearer {token}.</span></span> <span data-ttu-id="bc099-137">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="bc099-137">**Required**.</span></span>
<span data-ttu-id="bc099-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="bc099-138">Content-Type</span></span> | <span data-ttu-id="bc099-139">string</span><span class="sxs-lookup"><span data-stu-id="bc099-139">string</span></span> | <span data-ttu-id="bc099-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="bc099-140">application/json.</span></span> <span data-ttu-id="bc099-141">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="bc099-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="bc099-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="bc099-142">Request body</span></span>
<span data-ttu-id="bc099-143">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="bc099-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="bc099-144">Parámetro</span><span class="sxs-lookup"><span data-stu-id="bc099-144">Parameter</span></span> | <span data-ttu-id="bc099-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="bc099-145">Type</span></span>    | <span data-ttu-id="bc099-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc099-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="bc099-147">Comentario</span><span class="sxs-lookup"><span data-stu-id="bc099-147">Comment</span></span> |   <span data-ttu-id="bc099-148">Cadena</span><span class="sxs-lookup"><span data-stu-id="bc099-148">String</span></span> |    <span data-ttu-id="bc099-149">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="bc099-149">Comment to associate with the action.</span></span> <span data-ttu-id="bc099-150">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="bc099-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="bc099-151">Respuesta</span><span class="sxs-lookup"><span data-stu-id="bc099-151">Response</span></span>
<span data-ttu-id="bc099-152">Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="bc099-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="bc099-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc099-153">Example</span></span>

<span data-ttu-id="bc099-154">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="bc099-154">**Request**</span></span>

<span data-ttu-id="bc099-155">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="bc099-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
