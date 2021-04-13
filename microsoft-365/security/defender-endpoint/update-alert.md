---
title: ACTUALIZAR API de entidad de alerta
description: Obtén información sobre cómo actualizar una alerta de Microsoft Defender para endpoint mediante esta API. Puede actualizar las propiedades status, determination, classification y assignedTo.
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
ms.openlocfilehash: 94be185bd30cd36f456a66d5ae30a4361abc0c48
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688254"
---
# <a name="update-alert"></a><span data-ttu-id="2d7ed-105">Actualizar alerta</span><span class="sxs-lookup"><span data-stu-id="2d7ed-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2d7ed-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2d7ed-106">**Applies to:**</span></span>
- [<span data-ttu-id="2d7ed-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2d7ed-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2d7ed-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d7ed-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2d7ed-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2d7ed-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2d7ed-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2d7ed-111">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="2d7ed-111">API description</span></span>
<span data-ttu-id="2d7ed-112">Actualiza las propiedades [de](alerts.md)alert existente .</span><span class="sxs-lookup"><span data-stu-id="2d7ed-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="2d7ed-113">El envío **de comentarios** está disponible con o sin actualizar propiedades.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="2d7ed-114">Las propiedades actualizables son: ```status``` ```determination``` , y ```classification``` ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="2d7ed-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="2d7ed-115">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="2d7ed-115">Limitations</span></span>
1. <span data-ttu-id="2d7ed-116">Puede actualizar las alertas disponibles en la API.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="2d7ed-117">Vea [Enumerar alertas](get-alerts.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="2d7ed-118">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2d7ed-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="2d7ed-119">Permissions</span></span>
<span data-ttu-id="2d7ed-120">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2d7ed-121">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2d7ed-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2d7ed-122">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="2d7ed-122">Permission type</span></span> |   <span data-ttu-id="2d7ed-123">Permiso</span><span class="sxs-lookup"><span data-stu-id="2d7ed-123">Permission</span></span>  |   <span data-ttu-id="2d7ed-124">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="2d7ed-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2d7ed-125">Aplicación</span><span class="sxs-lookup"><span data-stu-id="2d7ed-125">Application</span></span> |   <span data-ttu-id="2d7ed-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="2d7ed-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="2d7ed-127">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="2d7ed-127">'Read and write all alerts'</span></span>
<span data-ttu-id="2d7ed-128">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="2d7ed-128">Delegated (work or school account)</span></span> | <span data-ttu-id="2d7ed-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2d7ed-129">Alert.ReadWrite</span></span> | <span data-ttu-id="2d7ed-130">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="2d7ed-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="2d7ed-131">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="2d7ed-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2d7ed-132">El usuario debe tener al menos el siguiente permiso de función: "Investigación de alertas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="2d7ed-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2d7ed-133">El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="2d7ed-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2d7ed-134">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="2d7ed-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="2d7ed-135">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="2d7ed-135">Request headers</span></span>

<span data-ttu-id="2d7ed-136">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d7ed-136">Name</span></span> | <span data-ttu-id="2d7ed-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="2d7ed-137">Type</span></span> | <span data-ttu-id="2d7ed-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d7ed-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="2d7ed-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="2d7ed-139">Authorization</span></span> | <span data-ttu-id="2d7ed-140">String</span><span class="sxs-lookup"><span data-stu-id="2d7ed-140">String</span></span> | <span data-ttu-id="2d7ed-141">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-141">Bearer {token}.</span></span> <span data-ttu-id="2d7ed-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-142">**Required**.</span></span>
<span data-ttu-id="2d7ed-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2d7ed-143">Content-Type</span></span> | <span data-ttu-id="2d7ed-144">Cadena</span><span class="sxs-lookup"><span data-stu-id="2d7ed-144">String</span></span> | <span data-ttu-id="2d7ed-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-145">application/json.</span></span> <span data-ttu-id="2d7ed-146">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2d7ed-147">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="2d7ed-147">Request body</span></span>
<span data-ttu-id="2d7ed-148">En el cuerpo de la solicitud, proporcione los valores de los campos relevantes que deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="2d7ed-149">Las propiedades existentes que no se incluyan en el cuerpo de la solicitud mantendrán los valores anteriores o se recalcularán según los cambios efectuados en otros valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="2d7ed-150">Para obtener el mejor rendimiento, no debe incluir valores existentes que no hayan cambiado.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="2d7ed-151">Propiedad</span><span class="sxs-lookup"><span data-stu-id="2d7ed-151">Property</span></span> | <span data-ttu-id="2d7ed-152">Tipo</span><span class="sxs-lookup"><span data-stu-id="2d7ed-152">Type</span></span> | <span data-ttu-id="2d7ed-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d7ed-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="2d7ed-154">status</span><span class="sxs-lookup"><span data-stu-id="2d7ed-154">status</span></span> | <span data-ttu-id="2d7ed-155">String</span><span class="sxs-lookup"><span data-stu-id="2d7ed-155">String</span></span> | <span data-ttu-id="2d7ed-156">Especifica el estado actual de la alerta.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="2d7ed-157">Los valores de propiedad son: 'New', 'InProgress' y 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="2d7ed-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="2d7ed-158">assignedTo</span></span> | <span data-ttu-id="2d7ed-159">String</span><span class="sxs-lookup"><span data-stu-id="2d7ed-159">String</span></span> | <span data-ttu-id="2d7ed-160">Propietario de la alerta</span><span class="sxs-lookup"><span data-stu-id="2d7ed-160">Owner of the alert</span></span>
<span data-ttu-id="2d7ed-161">classification</span><span class="sxs-lookup"><span data-stu-id="2d7ed-161">classification</span></span> | <span data-ttu-id="2d7ed-162">String</span><span class="sxs-lookup"><span data-stu-id="2d7ed-162">String</span></span> | <span data-ttu-id="2d7ed-163">Especifica la especificación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="2d7ed-164">Los valores de propiedad son: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="2d7ed-165">determinación</span><span class="sxs-lookup"><span data-stu-id="2d7ed-165">determination</span></span> | <span data-ttu-id="2d7ed-166">String</span><span class="sxs-lookup"><span data-stu-id="2d7ed-166">String</span></span> | <span data-ttu-id="2d7ed-167">Especifica la determinación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="2d7ed-168">Los valores de propiedad son: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="2d7ed-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="2d7ed-169">comment</span><span class="sxs-lookup"><span data-stu-id="2d7ed-169">comment</span></span> | <span data-ttu-id="2d7ed-170">String</span><span class="sxs-lookup"><span data-stu-id="2d7ed-170">String</span></span> | <span data-ttu-id="2d7ed-171">Comentario que se agregará a la alerta.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="2d7ed-172">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2d7ed-172">Response</span></span>
<span data-ttu-id="2d7ed-173">Si se realiza correctamente, este método devuelve 200 Ok y la entidad [alert](alerts.md) en el cuerpo de la respuesta con las propiedades actualizadas.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="2d7ed-174">Si no se encontró la alerta con el identificador especificado: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="2d7ed-175">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d7ed-175">Example</span></span>

<span data-ttu-id="2d7ed-176">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="2d7ed-176">**Request**</span></span>

<span data-ttu-id="2d7ed-177">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2d7ed-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
