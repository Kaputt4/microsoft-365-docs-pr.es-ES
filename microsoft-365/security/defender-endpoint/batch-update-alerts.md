---
title: API de entidades de alerta de actualización por lotes
description: Obtenga información sobre cómo actualizar alertas de Microsoft Defender para endpoints en un lote mediante esta API. Puede actualizar las propiedades status, determination, classification y assignedTo.
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
ms.technology: mde
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167087"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="fdfa7-105">Alertas de actualización por lotes</span><span class="sxs-lookup"><span data-stu-id="fdfa7-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fdfa7-106">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="fdfa7-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="fdfa7-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="fdfa7-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fdfa7-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="fdfa7-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="fdfa7-109">API description</span></span>
<span data-ttu-id="fdfa7-110">Actualiza las propiedades de un lote de alertas [existentes](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="fdfa7-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>
<br><span data-ttu-id="fdfa7-111">El envío **de comentarios** está disponible con o sin actualizar propiedades.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-111">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="fdfa7-112">Las propiedades actualizables son: `status` `determination` , y `classification` `assignedTo` .</span><span class="sxs-lookup"><span data-stu-id="fdfa7-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>


## <a name="limitations"></a><span data-ttu-id="fdfa7-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="fdfa7-113">Limitations</span></span>
1. <span data-ttu-id="fdfa7-114">Puede actualizar las alertas que están disponibles en la API.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="fdfa7-115">Vea [Enumerar alertas](get-alerts.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="fdfa7-116">Las limitaciones de velocidad para esta API son 10 llamadas por minuto y 500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="fdfa7-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="fdfa7-117">Permissions</span></span>
<span data-ttu-id="fdfa7-118">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="fdfa7-119">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="fdfa7-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="fdfa7-120">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="fdfa7-120">Permission type</span></span> |   <span data-ttu-id="fdfa7-121">Permiso</span><span class="sxs-lookup"><span data-stu-id="fdfa7-121">Permission</span></span>  |   <span data-ttu-id="fdfa7-122">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="fdfa7-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="fdfa7-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="fdfa7-123">Application</span></span> |   <span data-ttu-id="fdfa7-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fdfa7-124">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="fdfa7-125">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="fdfa7-125">'Read and write all alerts'</span></span>
<span data-ttu-id="fdfa7-126">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="fdfa7-126">Delegated (work or school account)</span></span> | <span data-ttu-id="fdfa7-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="fdfa7-127">Alert.ReadWrite</span></span> | <span data-ttu-id="fdfa7-128">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="fdfa7-128">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="fdfa7-129">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="fdfa7-129">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="fdfa7-130">El usuario debe tener al menos el siguiente permiso de función: "Investigación de alertas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="fdfa7-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="fdfa7-131">El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="fdfa7-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="fdfa7-132">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="fdfa7-132">HTTP request</span></span>
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="fdfa7-133">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="fdfa7-133">Request headers</span></span>

<span data-ttu-id="fdfa7-134">Nombre</span><span class="sxs-lookup"><span data-stu-id="fdfa7-134">Name</span></span> | <span data-ttu-id="fdfa7-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="fdfa7-135">Type</span></span> | <span data-ttu-id="fdfa7-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdfa7-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="fdfa7-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="fdfa7-137">Authorization</span></span> | <span data-ttu-id="fdfa7-138">Cadena</span><span class="sxs-lookup"><span data-stu-id="fdfa7-138">String</span></span> | <span data-ttu-id="fdfa7-139">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-139">Bearer {token}.</span></span> <span data-ttu-id="fdfa7-140">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-140">**Required**.</span></span>
<span data-ttu-id="fdfa7-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="fdfa7-141">Content-Type</span></span> | <span data-ttu-id="fdfa7-142">Cadena</span><span class="sxs-lookup"><span data-stu-id="fdfa7-142">String</span></span> | <span data-ttu-id="fdfa7-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-143">application/json.</span></span> <span data-ttu-id="fdfa7-144">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="fdfa7-145">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="fdfa7-145">Request body</span></span>
<span data-ttu-id="fdfa7-146">En el cuerpo de la solicitud, proporcione los IDs de las alertas que se actualizarán y los valores de los campos relevantes que desea actualizar para estas alertas.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>
<br><span data-ttu-id="fdfa7-147">Las propiedades existentes que no se incluyan en el cuerpo de la solicitud mantendrán los valores anteriores o se recalcularán según los cambios efectuados en otros valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="fdfa7-148">Para obtener el mejor rendimiento no debe incluir valores existentes que no hayan cambiado.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="fdfa7-149">Propiedad</span><span class="sxs-lookup"><span data-stu-id="fdfa7-149">Property</span></span> | <span data-ttu-id="fdfa7-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="fdfa7-150">Type</span></span> | <span data-ttu-id="fdfa7-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdfa7-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="fdfa7-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="fdfa7-152">alertIds</span></span> | <span data-ttu-id="fdfa7-153">Cadena de &lt; lista&gt;</span><span class="sxs-lookup"><span data-stu-id="fdfa7-153">List&lt;String&gt;</span></span>| <span data-ttu-id="fdfa7-154">Una lista de los IDs de las alertas que se actualizarán.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="fdfa7-155">**Required**</span><span class="sxs-lookup"><span data-stu-id="fdfa7-155">**Required**</span></span>
<span data-ttu-id="fdfa7-156">status</span><span class="sxs-lookup"><span data-stu-id="fdfa7-156">status</span></span> | <span data-ttu-id="fdfa7-157">Cadena</span><span class="sxs-lookup"><span data-stu-id="fdfa7-157">String</span></span> | <span data-ttu-id="fdfa7-158">Especifica el estado actualizado de las alertas especificadas.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="fdfa7-159">Los valores de propiedad son: 'New', 'InProgress' y 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="fdfa7-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="fdfa7-160">assignedTo</span></span> | <span data-ttu-id="fdfa7-161">Cadena</span><span class="sxs-lookup"><span data-stu-id="fdfa7-161">String</span></span> | <span data-ttu-id="fdfa7-162">Propietario de las alertas especificadas</span><span class="sxs-lookup"><span data-stu-id="fdfa7-162">Owner of the specified alerts</span></span>
<span data-ttu-id="fdfa7-163">classification</span><span class="sxs-lookup"><span data-stu-id="fdfa7-163">classification</span></span> | <span data-ttu-id="fdfa7-164">String</span><span class="sxs-lookup"><span data-stu-id="fdfa7-164">String</span></span> | <span data-ttu-id="fdfa7-165">Especifica la especificación de las alertas especificadas.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="fdfa7-166">Los valores de propiedad son: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="fdfa7-167">determinación</span><span class="sxs-lookup"><span data-stu-id="fdfa7-167">determination</span></span> | <span data-ttu-id="fdfa7-168">Cadena</span><span class="sxs-lookup"><span data-stu-id="fdfa7-168">String</span></span> | <span data-ttu-id="fdfa7-169">Especifica la determinación de las alertas especificadas.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="fdfa7-170">Los valores de propiedad son: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="fdfa7-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="fdfa7-171">comment</span><span class="sxs-lookup"><span data-stu-id="fdfa7-171">comment</span></span> | <span data-ttu-id="fdfa7-172">String</span><span class="sxs-lookup"><span data-stu-id="fdfa7-172">String</span></span> | <span data-ttu-id="fdfa7-173">Comentario que se agregará a las alertas especificadas.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="fdfa7-174">Respuesta</span><span class="sxs-lookup"><span data-stu-id="fdfa7-174">Response</span></span>
<span data-ttu-id="fdfa7-175">Si se realiza correctamente, este método devuelve 200 Ok, con un cuerpo de respuesta vacío.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-175">If successful, this method returns 200 OK, with an empty response body.</span></span>


## <a name="example"></a><span data-ttu-id="fdfa7-176">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdfa7-176">Example</span></span>

<span data-ttu-id="fdfa7-177">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="fdfa7-177">**Request**</span></span>

<span data-ttu-id="fdfa7-178">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="fdfa7-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
