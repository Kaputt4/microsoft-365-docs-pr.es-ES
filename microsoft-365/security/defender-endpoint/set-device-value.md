---
title: ESTABLECER API de valor de dispositivo
description: Obtén información sobre cómo especificar el valor de un dispositivo mediante una API de Microsoft Defender para endpoints.
keywords: apis, api de gráficos, api admitidas, etiquetas, etiquetas de máquina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 76df62243db837ec91819497980ff1de2295e3b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498318"
---
# <a name="set-device-value-api"></a><span data-ttu-id="059a6-104">ESTABLECER API de valor de dispositivo</span><span class="sxs-lookup"><span data-stu-id="059a6-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="059a6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="059a6-105">**Applies to:**</span></span>
- [<span data-ttu-id="059a6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="059a6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="059a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="059a6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="059a6-108">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="059a6-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="059a6-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="059a6-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="059a6-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="059a6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="059a6-111">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="059a6-111">API description</span></span>

<span data-ttu-id="059a6-112">Establece el valor de dispositivo de un [equipo específico.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="059a6-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="059a6-113">Consulta [Asignar valores de dispositivo](tvm-assign-device-value.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="059a6-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="059a6-114">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="059a6-114">Limitations</span></span>

1. <span data-ttu-id="059a6-115">Puedes publicar en dispositivos vistos por última vez según el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="059a6-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="059a6-116">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="059a6-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="059a6-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="059a6-117">Permissions</span></span>

<span data-ttu-id="059a6-118">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="059a6-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="059a6-119">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="059a6-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="059a6-120">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="059a6-120">Permission type</span></span> |    <span data-ttu-id="059a6-121">Permiso</span><span class="sxs-lookup"><span data-stu-id="059a6-121">Permission</span></span>    |    <span data-ttu-id="059a6-122">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="059a6-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="059a6-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="059a6-123">Application</span></span> |    <span data-ttu-id="059a6-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="059a6-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="059a6-125">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="059a6-125">'Read and write all machine information'</span></span>
<span data-ttu-id="059a6-126">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="059a6-126">Delegated (work or school account)</span></span> | <span data-ttu-id="059a6-127">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="059a6-127">Machine.ReadWrite</span></span> | <span data-ttu-id="059a6-128">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="059a6-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="059a6-129">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="059a6-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="059a6-130">El usuario debe tener al menos el siguiente permiso de función: "Administrar la configuración de seguridad".</span><span class="sxs-lookup"><span data-stu-id="059a6-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="059a6-131">Para obtener más información (vea [Crear y administrar roles](user-roles.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="059a6-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="059a6-132">El usuario debe tener acceso a la máquina en función de la configuración del grupo de máquinas (vea [Crear y](machine-groups.md) administrar grupos de máquinas para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="059a6-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="059a6-133">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="059a6-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="059a6-134">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="059a6-134">Request headers</span></span>

<span data-ttu-id="059a6-135">Nombre</span><span class="sxs-lookup"><span data-stu-id="059a6-135">Name</span></span> | <span data-ttu-id="059a6-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="059a6-136">Type</span></span> | <span data-ttu-id="059a6-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="059a6-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="059a6-138">Authorization</span><span class="sxs-lookup"><span data-stu-id="059a6-138">Authorization</span></span> | <span data-ttu-id="059a6-139">Cadena</span><span class="sxs-lookup"><span data-stu-id="059a6-139">String</span></span> | <span data-ttu-id="059a6-140">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="059a6-140">Bearer {token}.</span></span> <span data-ttu-id="059a6-141">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="059a6-141">**Required**.</span></span>
<span data-ttu-id="059a6-142">Content-Type</span><span class="sxs-lookup"><span data-stu-id="059a6-142">Content-Type</span></span> | <span data-ttu-id="059a6-143">cadena</span><span class="sxs-lookup"><span data-stu-id="059a6-143">string</span></span> | <span data-ttu-id="059a6-144">application/json.</span><span class="sxs-lookup"><span data-stu-id="059a6-144">application/json.</span></span> <span data-ttu-id="059a6-145">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="059a6-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="059a6-146">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="059a6-146">Request body</span></span>

<span data-ttu-id="059a6-147">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="059a6-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="059a6-148">Parámetro</span><span class="sxs-lookup"><span data-stu-id="059a6-148">Parameter</span></span> |    <span data-ttu-id="059a6-149">Tipo</span><span class="sxs-lookup"><span data-stu-id="059a6-149">Type</span></span>    | <span data-ttu-id="059a6-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="059a6-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="059a6-151">DeviceValue</span><span class="sxs-lookup"><span data-stu-id="059a6-151">DeviceValue</span></span> |    <span data-ttu-id="059a6-152">Enum</span><span class="sxs-lookup"><span data-stu-id="059a6-152">Enum</span></span> |    <span data-ttu-id="059a6-153">Valor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="059a6-153">Device value.</span></span> <span data-ttu-id="059a6-154">Los valores permitidos son: 'Normal', 'Low' y 'High'.</span><span class="sxs-lookup"><span data-stu-id="059a6-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="059a6-155">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="059a6-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="059a6-156">Respuesta</span><span class="sxs-lookup"><span data-stu-id="059a6-156">Response</span></span>

<span data-ttu-id="059a6-157">Si se realiza correctamente, este método devuelve 200: código de respuesta Aceptar y la máquina actualizada en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="059a6-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="059a6-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="059a6-158">Example</span></span>

<span data-ttu-id="059a6-159">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="059a6-159">**Request**</span></span>

<span data-ttu-id="059a6-160">Este es un ejemplo de una solicitud que agrega etiqueta de máquina.</span><span class="sxs-lookup"><span data-stu-id="059a6-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
