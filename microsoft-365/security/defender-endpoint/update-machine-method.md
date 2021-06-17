---
title: Actualizar API de entidad de máquina
description: Obtenga información sobre cómo actualizar las etiquetas de máquina mediante esta API. Puedes actualizar las etiquetas y las propiedades devicevalue.
keywords: apis, api de gráficos, api admitidas, get, alert, information, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985748"
---
# <a name="update-machine"></a><span data-ttu-id="625eb-105">Actualizar máquina</span><span class="sxs-lookup"><span data-stu-id="625eb-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="625eb-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="625eb-106">**Applies to:**</span></span>
- [<span data-ttu-id="625eb-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="625eb-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="625eb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="625eb-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="625eb-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="625eb-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="625eb-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="625eb-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="625eb-111">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="625eb-111">API description</span></span>
<span data-ttu-id="625eb-112">Actualiza las propiedades [de](machine.md)machine existente .</span><span class="sxs-lookup"><span data-stu-id="625eb-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="625eb-113">Las propiedades actualizables son: ```machineTags``` y ```deviceValue``` .</span><span class="sxs-lookup"><span data-stu-id="625eb-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="625eb-114">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="625eb-114">Limitations</span></span>
1. <span data-ttu-id="625eb-115">Puede actualizar las máquinas que están disponibles en la API.</span><span class="sxs-lookup"><span data-stu-id="625eb-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="625eb-116">La máquina de actualización solo anexa etiquetas a la colección de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="625eb-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="625eb-117">Si existen etiquetas, deben incluirse en la colección de etiquetas del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="625eb-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="625eb-118">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="625eb-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="625eb-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="625eb-119">Permissions</span></span>
<span data-ttu-id="625eb-120">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="625eb-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="625eb-121">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="625eb-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="625eb-122">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="625eb-122">Permission type</span></span> |   <span data-ttu-id="625eb-123">Permiso</span><span class="sxs-lookup"><span data-stu-id="625eb-123">Permission</span></span>  |   <span data-ttu-id="625eb-124">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="625eb-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="625eb-125">Aplicación</span><span class="sxs-lookup"><span data-stu-id="625eb-125">Application</span></span> |   <span data-ttu-id="625eb-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="625eb-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="625eb-127">'Leer y escribir información de máquina para todas las máquinas'</span><span class="sxs-lookup"><span data-stu-id="625eb-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="625eb-128">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="625eb-128">Delegated (work or school account)</span></span> | <span data-ttu-id="625eb-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="625eb-129">Machine.ReadWrite</span></span> | <span data-ttu-id="625eb-130">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="625eb-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="625eb-131">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="625eb-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="625eb-132">El usuario debe tener al menos el siguiente permiso de función: "Investigación de alertas".</span><span class="sxs-lookup"><span data-stu-id="625eb-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="625eb-133">Para obtener más información, vea [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="625eb-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="625eb-134">El usuario debe tener acceso al dispositivo asociado con la alerta, en función de la configuración del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="625eb-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="625eb-135">Para obtener más información, consulta [Crear y administrar grupos de dispositivos.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="625eb-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="625eb-136">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="625eb-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="625eb-137">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="625eb-137">Request headers</span></span>

<span data-ttu-id="625eb-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="625eb-138">Name</span></span> | <span data-ttu-id="625eb-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="625eb-139">Type</span></span> | <span data-ttu-id="625eb-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="625eb-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="625eb-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="625eb-141">Authorization</span></span> | <span data-ttu-id="625eb-142">String</span><span class="sxs-lookup"><span data-stu-id="625eb-142">String</span></span> | <span data-ttu-id="625eb-143">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="625eb-143">Bearer {token}.</span></span> <span data-ttu-id="625eb-144">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="625eb-144">**Required**.</span></span>
<span data-ttu-id="625eb-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="625eb-145">Content-Type</span></span> | <span data-ttu-id="625eb-146">Cadena</span><span class="sxs-lookup"><span data-stu-id="625eb-146">String</span></span> | <span data-ttu-id="625eb-147">application/json.</span><span class="sxs-lookup"><span data-stu-id="625eb-147">application/json.</span></span> <span data-ttu-id="625eb-148">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="625eb-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="625eb-149">Cuerpo de solicitud</span><span class="sxs-lookup"><span data-stu-id="625eb-149">Request body</span></span>
<span data-ttu-id="625eb-150">En el cuerpo de la solicitud, proporcione los valores de los campos relevantes que deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="625eb-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="625eb-151">Las propiedades existentes que no se incluyan en el cuerpo de la solicitud mantendrán los valores anteriores o se recalcularán según los cambios efectuados en otros valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="625eb-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="625eb-152">Para obtener el mejor rendimiento, no debe incluir valores existentes que no hayan cambiado.</span><span class="sxs-lookup"><span data-stu-id="625eb-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="625eb-153">Propiedad</span><span class="sxs-lookup"><span data-stu-id="625eb-153">Property</span></span> | <span data-ttu-id="625eb-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="625eb-154">Type</span></span> | <span data-ttu-id="625eb-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="625eb-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="625eb-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="625eb-156">machineTags</span></span> | <span data-ttu-id="625eb-157">Colección de cadenas</span><span class="sxs-lookup"><span data-stu-id="625eb-157">String collection</span></span> | <span data-ttu-id="625eb-158">Conjunto de [etiquetas de](machine.md) máquina.</span><span class="sxs-lookup"><span data-stu-id="625eb-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="625eb-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="625eb-159">deviceValue</span></span> | <span data-ttu-id="625eb-160">Enumeración que admite valores null</span><span class="sxs-lookup"><span data-stu-id="625eb-160">Nullable Enum</span></span> | <span data-ttu-id="625eb-161">El [valor del dispositivo](tvm-assign-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="625eb-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="625eb-162">Los valores posibles son: 'Normal', 'Low' y 'High'.</span><span class="sxs-lookup"><span data-stu-id="625eb-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="625eb-163">Respuesta</span><span class="sxs-lookup"><span data-stu-id="625eb-163">Response</span></span>
<span data-ttu-id="625eb-164">Si se realiza correctamente, este método devuelve 200 Ok y la entidad [de](machine.md) la máquina en el cuerpo de la respuesta con las propiedades actualizadas.</span><span class="sxs-lookup"><span data-stu-id="625eb-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="625eb-165">Si la colección de etiquetas de máquina en el cuerpo no contiene etiquetas de máquina existentes: 400 Entradas no válidas y un mensaje que informa de las etiquetas que faltan.</span><span class="sxs-lookup"><span data-stu-id="625eb-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="625eb-166">Si no se encontró el equipo con el identificador especificado: 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="625eb-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="625eb-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="625eb-167">Example</span></span>

<span data-ttu-id="625eb-168">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="625eb-168">**Request**</span></span>

<span data-ttu-id="625eb-169">Este es un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="625eb-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
