---
title: Ejecutar LA API de detección antivirus
description: Usa esta API para crear llamadas relacionadas con la ejecución de un examen antivirus en un dispositivo.
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
ms.technology: mde
ms.openlocfilehash: d0db45daa786c1a44272e4d02153af3fe658e781
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200214"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="94ddc-104">Ejecutar LA API de detección antivirus</span><span class="sxs-lookup"><span data-stu-id="94ddc-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="94ddc-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="94ddc-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="94ddc-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="94ddc-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="94ddc-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="94ddc-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="94ddc-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="94ddc-108">API description</span></span>
<span data-ttu-id="94ddc-109">Inicie el examen de Antivirus de Microsoft Defender en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="94ddc-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="94ddc-110">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="94ddc-110">Limitations</span></span>
1. <span data-ttu-id="94ddc-111">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="94ddc-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="94ddc-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="94ddc-112">Permissions</span></span>
<span data-ttu-id="94ddc-113">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="94ddc-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="94ddc-114">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="94ddc-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="94ddc-115">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="94ddc-115">Permission type</span></span> |   <span data-ttu-id="94ddc-116">Permiso</span><span class="sxs-lookup"><span data-stu-id="94ddc-116">Permission</span></span>  |   <span data-ttu-id="94ddc-117">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="94ddc-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="94ddc-118">Aplicación</span><span class="sxs-lookup"><span data-stu-id="94ddc-118">Application</span></span> |   <span data-ttu-id="94ddc-119">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="94ddc-119">Machine.Scan</span></span> |  <span data-ttu-id="94ddc-120">'Máquina de digitalización'</span><span class="sxs-lookup"><span data-stu-id="94ddc-120">'Scan machine'</span></span>
<span data-ttu-id="94ddc-121">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="94ddc-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="94ddc-122">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="94ddc-122">Machine.Scan</span></span> |  <span data-ttu-id="94ddc-123">'Máquina de digitalización'</span><span class="sxs-lookup"><span data-stu-id="94ddc-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="94ddc-124">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="94ddc-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="94ddc-125">El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="94ddc-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="94ddc-126">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="94ddc-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="94ddc-127">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="94ddc-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="94ddc-128">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="94ddc-128">Request headers</span></span>

<span data-ttu-id="94ddc-129">Nombre</span><span class="sxs-lookup"><span data-stu-id="94ddc-129">Name</span></span> | <span data-ttu-id="94ddc-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="94ddc-130">Type</span></span> | <span data-ttu-id="94ddc-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="94ddc-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="94ddc-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="94ddc-132">Authorization</span></span> | <span data-ttu-id="94ddc-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="94ddc-133">String</span></span> | <span data-ttu-id="94ddc-134">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="94ddc-134">Bearer {token}.</span></span> <span data-ttu-id="94ddc-135">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="94ddc-135">**Required**.</span></span>
<span data-ttu-id="94ddc-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="94ddc-136">Content-Type</span></span> | <span data-ttu-id="94ddc-137">string</span><span class="sxs-lookup"><span data-stu-id="94ddc-137">string</span></span> | <span data-ttu-id="94ddc-138">application/json</span><span class="sxs-lookup"><span data-stu-id="94ddc-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="94ddc-139">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="94ddc-139">Request body</span></span>
<span data-ttu-id="94ddc-140">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="94ddc-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="94ddc-141">Parámetro</span><span class="sxs-lookup"><span data-stu-id="94ddc-141">Parameter</span></span> | <span data-ttu-id="94ddc-142">Tipo</span><span class="sxs-lookup"><span data-stu-id="94ddc-142">Type</span></span>    | <span data-ttu-id="94ddc-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="94ddc-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="94ddc-144">Comentario</span><span class="sxs-lookup"><span data-stu-id="94ddc-144">Comment</span></span> |   <span data-ttu-id="94ddc-145">Cadena</span><span class="sxs-lookup"><span data-stu-id="94ddc-145">String</span></span> | <span data-ttu-id="94ddc-146">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="94ddc-146">Comment to associate with the action.</span></span> <span data-ttu-id="94ddc-147">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="94ddc-147">**Required**.</span></span>
<span data-ttu-id="94ddc-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="94ddc-148">ScanType</span></span>|   <span data-ttu-id="94ddc-149">Cadena</span><span class="sxs-lookup"><span data-stu-id="94ddc-149">String</span></span>  | <span data-ttu-id="94ddc-150">Define el tipo de examen.</span><span class="sxs-lookup"><span data-stu-id="94ddc-150">Defines the type of the Scan.</span></span> <span data-ttu-id="94ddc-151">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="94ddc-151">**Required**.</span></span>

<span data-ttu-id="94ddc-152">**ScanType** controla el tipo de examen que se va a realizar y puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="94ddc-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="94ddc-153">**Rápido:** realizar un examen rápido en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="94ddc-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="94ddc-154">**Completo:** realizar un examen completo en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="94ddc-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="94ddc-155">Respuesta</span><span class="sxs-lookup"><span data-stu-id="94ddc-155">Response</span></span>
<span data-ttu-id="94ddc-156">Si se realiza correctamente, este método devuelve 201, Código de respuesta creado y _Objeto MachineAction_ en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="94ddc-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="94ddc-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94ddc-157">Example</span></span>

<span data-ttu-id="94ddc-158">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="94ddc-158">**Request**</span></span>

<span data-ttu-id="94ddc-159">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="94ddc-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

