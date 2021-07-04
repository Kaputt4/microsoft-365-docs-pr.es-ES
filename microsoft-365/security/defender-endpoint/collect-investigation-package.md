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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4cf60ea73ea907be9c10b2dd9562a0ea60127f2d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289900"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="4d989-104">RECOPILAR API de paquetes de investigación</span><span class="sxs-lookup"><span data-stu-id="4d989-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4d989-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4d989-105">**Applies to:**</span></span>
- [<span data-ttu-id="4d989-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4d989-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4d989-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d989-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="4d989-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="4d989-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4d989-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="4d989-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4d989-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="4d989-110">API description</span></span>

<span data-ttu-id="4d989-111">Recopilar el paquete de investigación de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4d989-111">Collect investigation package from a device.</span></span>

## <a name="limitations"></a><span data-ttu-id="4d989-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="4d989-112">Limitations</span></span>

1. <span data-ttu-id="4d989-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="4d989-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="4d989-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="4d989-114">Permissions</span></span>

<span data-ttu-id="4d989-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="4d989-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4d989-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4d989-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4d989-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="4d989-117">Permission type</span></span> | <span data-ttu-id="4d989-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="4d989-118">Permission</span></span> | <span data-ttu-id="4d989-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="4d989-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4d989-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="4d989-120">Application</span></span> | <span data-ttu-id="4d989-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="4d989-121">Machine.CollectForensics</span></span> | <span data-ttu-id="4d989-122">'Recopilar forenses'</span><span class="sxs-lookup"><span data-stu-id="4d989-122">'Collect forensics'</span></span>
<span data-ttu-id="4d989-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="4d989-123">Delegated (work or school account)</span></span> | <span data-ttu-id="4d989-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="4d989-124">Machine.CollectForensics</span></span> | <span data-ttu-id="4d989-125">'Recopilar forenses'</span><span class="sxs-lookup"><span data-stu-id="4d989-125">'Collect forensics'</span></span>

> [!NOTE]
> <span data-ttu-id="4d989-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="4d989-126">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="4d989-127">El usuario debe tener al menos el siguiente permiso de función: "Investigación de alertas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="4d989-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="4d989-128">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="4d989-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4d989-129">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="4d989-129">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="4d989-130">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="4d989-130">Request headers</span></span>

<span data-ttu-id="4d989-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="4d989-131">Name</span></span> | <span data-ttu-id="4d989-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="4d989-132">Type</span></span> | <span data-ttu-id="4d989-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d989-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="4d989-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="4d989-134">Authorization</span></span> | <span data-ttu-id="4d989-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="4d989-135">String</span></span> | <span data-ttu-id="4d989-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="4d989-136">Bearer {token}.</span></span> <span data-ttu-id="4d989-137">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="4d989-137">**Required**.</span></span>
<span data-ttu-id="4d989-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4d989-138">Content-Type</span></span> | <span data-ttu-id="4d989-139">cadena</span><span class="sxs-lookup"><span data-stu-id="4d989-139">string</span></span> | <span data-ttu-id="4d989-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="4d989-140">application/json.</span></span> <span data-ttu-id="4d989-141">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="4d989-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4d989-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="4d989-142">Request body</span></span>

<span data-ttu-id="4d989-143">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="4d989-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="4d989-144">Parámetro</span><span class="sxs-lookup"><span data-stu-id="4d989-144">Parameter</span></span> | <span data-ttu-id="4d989-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="4d989-145">Type</span></span> | <span data-ttu-id="4d989-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d989-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="4d989-147">Comentario</span><span class="sxs-lookup"><span data-stu-id="4d989-147">Comment</span></span> | <span data-ttu-id="4d989-148">Cadena</span><span class="sxs-lookup"><span data-stu-id="4d989-148">String</span></span> | <span data-ttu-id="4d989-149">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="4d989-149">Comment to associate with the action.</span></span> <span data-ttu-id="4d989-150">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="4d989-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="4d989-151">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4d989-151">Response</span></span>

<span data-ttu-id="4d989-152">Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="4d989-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="4d989-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d989-153">Example</span></span>

### <a name="request"></a><span data-ttu-id="4d989-154">Solicitud</span><span class="sxs-lookup"><span data-stu-id="4d989-154">Request</span></span>

<span data-ttu-id="4d989-155">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4d989-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
