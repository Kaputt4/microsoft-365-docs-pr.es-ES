---
title: API de archivos de detenerse y poner en cuarentena
description: Obtén información sobre cómo dejar de ejecutar un archivo en un dispositivo y eliminar el archivo en Microsoft Defender para endpoint. Vea un ejemplo.
keywords: api, api de gráfico, api admitidas, archivo de detenerse y poner en cuarentena
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
ms.openlocfilehash: 670282f0f87092437bb1f3c6bf7be908e4649042
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199734"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="833ee-105">API de archivos de detenerse y poner en cuarentena</span><span class="sxs-lookup"><span data-stu-id="833ee-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="833ee-106">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="833ee-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="833ee-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="833ee-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="833ee-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="833ee-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="833ee-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="833ee-109">API description</span></span>
<span data-ttu-id="833ee-110">Detenga la ejecución de un archivo en un dispositivo y elimínelo.</span><span class="sxs-lookup"><span data-stu-id="833ee-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="833ee-111">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="833ee-111">Limitations</span></span>
1. <span data-ttu-id="833ee-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="833ee-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="833ee-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="833ee-113">Permissions</span></span>
<span data-ttu-id="833ee-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="833ee-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="833ee-115">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="833ee-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="833ee-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="833ee-116">Permission type</span></span> |   <span data-ttu-id="833ee-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="833ee-117">Permission</span></span>  |   <span data-ttu-id="833ee-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="833ee-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="833ee-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="833ee-119">Application</span></span> |   <span data-ttu-id="833ee-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="833ee-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="833ee-121">'Detener y poner en cuarentena'</span><span class="sxs-lookup"><span data-stu-id="833ee-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="833ee-122">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="833ee-122">Delegated (work or school account)</span></span> | <span data-ttu-id="833ee-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="833ee-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="833ee-124">'Detener y poner en cuarentena'</span><span class="sxs-lookup"><span data-stu-id="833ee-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="833ee-125">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="833ee-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="833ee-126">El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="833ee-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="833ee-127">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="833ee-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="833ee-128">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="833ee-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="833ee-129">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="833ee-129">Request headers</span></span>

<span data-ttu-id="833ee-130">Nombre</span><span class="sxs-lookup"><span data-stu-id="833ee-130">Name</span></span> | <span data-ttu-id="833ee-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="833ee-131">Type</span></span> | <span data-ttu-id="833ee-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="833ee-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="833ee-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="833ee-133">Authorization</span></span> | <span data-ttu-id="833ee-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="833ee-134">String</span></span> | <span data-ttu-id="833ee-135">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="833ee-135">Bearer {token}.</span></span> <span data-ttu-id="833ee-136">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="833ee-136">**Required**.</span></span>
<span data-ttu-id="833ee-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="833ee-137">Content-Type</span></span> | <span data-ttu-id="833ee-138">string</span><span class="sxs-lookup"><span data-stu-id="833ee-138">string</span></span> | <span data-ttu-id="833ee-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="833ee-139">application/json.</span></span> <span data-ttu-id="833ee-140">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="833ee-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="833ee-141">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="833ee-141">Request body</span></span>
<span data-ttu-id="833ee-142">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="833ee-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="833ee-143">Parámetro</span><span class="sxs-lookup"><span data-stu-id="833ee-143">Parameter</span></span> | <span data-ttu-id="833ee-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="833ee-144">Type</span></span>    | <span data-ttu-id="833ee-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="833ee-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="833ee-146">Comentario</span><span class="sxs-lookup"><span data-stu-id="833ee-146">Comment</span></span> |   <span data-ttu-id="833ee-147">Cadena</span><span class="sxs-lookup"><span data-stu-id="833ee-147">String</span></span> |    <span data-ttu-id="833ee-148">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="833ee-148">Comment to associate with the action.</span></span> <span data-ttu-id="833ee-149">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="833ee-149">**Required**.</span></span>
<span data-ttu-id="833ee-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="833ee-150">Sha1</span></span> |  <span data-ttu-id="833ee-151">Cadena</span><span class="sxs-lookup"><span data-stu-id="833ee-151">String</span></span>   | <span data-ttu-id="833ee-152">Sha1 del archivo para detener y poner en cuarentena en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="833ee-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="833ee-153">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="833ee-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="833ee-154">Respuesta</span><span class="sxs-lookup"><span data-stu-id="833ee-154">Response</span></span>
<span data-ttu-id="833ee-155">Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="833ee-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="833ee-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="833ee-156">Example</span></span>

<span data-ttu-id="833ee-157">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="833ee-157">**Request**</span></span>

<span data-ttu-id="833ee-158">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="833ee-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
