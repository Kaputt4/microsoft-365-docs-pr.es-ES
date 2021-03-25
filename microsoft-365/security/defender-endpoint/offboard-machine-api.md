---
title: API de máquina fuera de la máquina
description: Aprende a usar una API para salir de un dispositivo desde Windows Defender Protección contra amenazas avanzada (WDATP).
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
ms.openlocfilehash: 0b3fa5a5daba1aa09eef0f733c7439848ce66a2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187346"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="4ded1-104">API de máquina fuera de la máquina</span><span class="sxs-lookup"><span data-stu-id="4ded1-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4ded1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4ded1-105">**Applies to:**</span></span>
- [<span data-ttu-id="4ded1-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4ded1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4ded1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ded1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4ded1-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4ded1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4ded1-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="4ded1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4ded1-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="4ded1-110">API description</span></span>
<span data-ttu-id="4ded1-111">Dispositivo offboard de Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="4ded1-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="4ded1-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="4ded1-112">Limitations</span></span>
 - <span data-ttu-id="4ded1-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="4ded1-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="4ded1-114">Esta API se admite en Windows 10, versión 1703 y versiones posteriores, o Windows Server 2019 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4ded1-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="4ded1-115">Esta API no se admite en dispositivos MacOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="4ded1-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="4ded1-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="4ded1-116">Permissions</span></span>
<span data-ttu-id="4ded1-117">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="4ded1-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4ded1-118">Para obtener más información, incluido cómo elegir permisos, consulte [Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4ded1-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4ded1-119">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="4ded1-119">Permission type</span></span> |   <span data-ttu-id="4ded1-120">Permiso</span><span class="sxs-lookup"><span data-stu-id="4ded1-120">Permission</span></span>  |   <span data-ttu-id="4ded1-121">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="4ded1-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4ded1-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="4ded1-122">Application</span></span> |   <span data-ttu-id="4ded1-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="4ded1-123">Machine.Offboard</span></span> |  <span data-ttu-id="4ded1-124">'Offboard machine'</span><span class="sxs-lookup"><span data-stu-id="4ded1-124">'Offboard machine'</span></span>
<span data-ttu-id="4ded1-125">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="4ded1-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="4ded1-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="4ded1-126">Machine.Offboard</span></span> |  <span data-ttu-id="4ded1-127">'Offboard machine'</span><span class="sxs-lookup"><span data-stu-id="4ded1-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="4ded1-128">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="4ded1-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4ded1-129">El usuario necesita el rol ad "Administrador global"</span><span class="sxs-lookup"><span data-stu-id="4ded1-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="4ded1-130">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="4ded1-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4ded1-131">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="4ded1-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="4ded1-132">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="4ded1-132">Request headers</span></span>

<span data-ttu-id="4ded1-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="4ded1-133">Name</span></span> | <span data-ttu-id="4ded1-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="4ded1-134">Type</span></span> | <span data-ttu-id="4ded1-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ded1-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="4ded1-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="4ded1-136">Authorization</span></span> | <span data-ttu-id="4ded1-137">Cadena</span><span class="sxs-lookup"><span data-stu-id="4ded1-137">String</span></span> | <span data-ttu-id="4ded1-138">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="4ded1-138">Bearer {token}.</span></span> <span data-ttu-id="4ded1-139">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="4ded1-139">**Required**.</span></span>
<span data-ttu-id="4ded1-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4ded1-140">Content-Type</span></span> | <span data-ttu-id="4ded1-141">string</span><span class="sxs-lookup"><span data-stu-id="4ded1-141">string</span></span> | <span data-ttu-id="4ded1-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="4ded1-142">application/json.</span></span> <span data-ttu-id="4ded1-143">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="4ded1-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4ded1-144">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="4ded1-144">Request body</span></span>
<span data-ttu-id="4ded1-145">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="4ded1-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="4ded1-146">Parámetro</span><span class="sxs-lookup"><span data-stu-id="4ded1-146">Parameter</span></span> | <span data-ttu-id="4ded1-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="4ded1-147">Type</span></span>    | <span data-ttu-id="4ded1-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ded1-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="4ded1-149">Comentario</span><span class="sxs-lookup"><span data-stu-id="4ded1-149">Comment</span></span> |   <span data-ttu-id="4ded1-150">Cadena</span><span class="sxs-lookup"><span data-stu-id="4ded1-150">String</span></span> |    <span data-ttu-id="4ded1-151">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="4ded1-151">Comment to associate with the action.</span></span> <span data-ttu-id="4ded1-152">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="4ded1-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="4ded1-153">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4ded1-153">Response</span></span>
<span data-ttu-id="4ded1-154">Si se realiza correctamente, este método devuelve 201: código de respuesta creado y [Acción de](machineaction.md) máquina en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="4ded1-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="4ded1-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ded1-155">Example</span></span>

<span data-ttu-id="4ded1-156">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="4ded1-156">**Request**</span></span>

<span data-ttu-id="4ded1-157">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4ded1-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
