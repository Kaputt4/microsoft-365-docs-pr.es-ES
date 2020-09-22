---
title: Actualizar la API de incidentes
description: Obtenga información sobre cómo actualizar incidentes mediante la API de Microsoft Threat Protection
keywords: actualización, API, incidente
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 8ad47453c7163bfac99c17f42986b818cdca603f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203645"
---
# <a name="update-incidents-api"></a><span data-ttu-id="ed3d6-104">Actualizar la API de incidentes</span><span class="sxs-lookup"><span data-stu-id="ed3d6-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ed3d6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ed3d6-105">**Applies to:**</span></span>
- <span data-ttu-id="ed3d6-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ed3d6-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="ed3d6-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ed3d6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="ed3d6-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="ed3d6-109">API description</span></span>
<span data-ttu-id="ed3d6-110">Actualiza las propiedades de un incidente existente.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="ed3d6-111">Las propiedades actualizables son: ```status``` ,, ```determination``` ```classification``` ```assignedTo``` y ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="ed3d6-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="ed3d6-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="ed3d6-112">Limitations</span></span>
1. <span data-ttu-id="ed3d6-113">Las limitaciones de frecuencia de esta API son 50 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="ed3d6-114">Puede establecer la ```determination``` sola si la clasificación se establece en TruePositive.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="ed3d6-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="ed3d6-115">Permissions</span></span>
<span data-ttu-id="ed3d6-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ed3d6-117">Para obtener más información, incluido cómo elegir permisos, consulte [acceso a las API de Microsoft Threat Protection](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="ed3d6-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="ed3d6-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="ed3d6-118">Permission type</span></span> |   <span data-ttu-id="ed3d6-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="ed3d6-119">Permission</span></span>  |   <span data-ttu-id="ed3d6-120">Nombre para mostrar del permiso</span><span class="sxs-lookup"><span data-stu-id="ed3d6-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ed3d6-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="ed3d6-121">Application</span></span> |   <span data-ttu-id="ed3d6-122">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="ed3d6-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="ed3d6-123">' Leer y escribir todos los incidentes '</span><span class="sxs-lookup"><span data-stu-id="ed3d6-123">'Read and write all incidents'</span></span>
<span data-ttu-id="ed3d6-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="ed3d6-124">Delegated (work or school account)</span></span> | <span data-ttu-id="ed3d6-125">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ed3d6-125">Incident.ReadWrite</span></span> | <span data-ttu-id="ed3d6-126">' Incidentes de lectura y escritura '</span><span class="sxs-lookup"><span data-stu-id="ed3d6-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="ed3d6-127">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="ed3d6-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ed3d6-128">El usuario debe tener permiso para actualizar el incidente en el portal.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="ed3d6-129">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="ed3d6-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="ed3d6-130">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="ed3d6-130">Request headers</span></span>

<span data-ttu-id="ed3d6-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="ed3d6-131">Name</span></span> | <span data-ttu-id="ed3d6-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="ed3d6-132">Type</span></span> | <span data-ttu-id="ed3d6-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed3d6-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="ed3d6-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="ed3d6-134">Authorization</span></span> | <span data-ttu-id="ed3d6-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="ed3d6-135">String</span></span> | <span data-ttu-id="ed3d6-136">{Token} de portador.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-136">Bearer {token}.</span></span> <span data-ttu-id="ed3d6-137">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-137">**Required**.</span></span>
<span data-ttu-id="ed3d6-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ed3d6-138">Content-Type</span></span> | <span data-ttu-id="ed3d6-139">Cadena</span><span class="sxs-lookup"><span data-stu-id="ed3d6-139">String</span></span> | <span data-ttu-id="ed3d6-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-140">application/json.</span></span> <span data-ttu-id="ed3d6-141">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ed3d6-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="ed3d6-142">Request body</span></span>
<span data-ttu-id="ed3d6-143">En el cuerpo de la solicitud, proporcione los valores de los campos relevantes que deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="ed3d6-144">Las propiedades existentes que no se incluyan en el cuerpo de la solicitud mantendrán los valores anteriores o se recalcularán según los cambios efectuados en otros valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="ed3d6-145">Para obtener el mejor rendimiento, no debe incluir valores existentes que no hayan cambiado.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="ed3d6-146">Propiedad</span><span class="sxs-lookup"><span data-stu-id="ed3d6-146">Property</span></span> | <span data-ttu-id="ed3d6-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="ed3d6-147">Type</span></span> | <span data-ttu-id="ed3d6-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed3d6-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="ed3d6-149">status</span><span class="sxs-lookup"><span data-stu-id="ed3d6-149">status</span></span> | <span data-ttu-id="ed3d6-150">Enum</span><span class="sxs-lookup"><span data-stu-id="ed3d6-150">Enum</span></span> | <span data-ttu-id="ed3d6-151">Especifica el estado actual de la alerta.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="ed3d6-152">Los valores posibles son ```Active``` : ```Resolved``` y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="ed3d6-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="ed3d6-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="ed3d6-153">assignedTo</span></span> | <span data-ttu-id="ed3d6-154">string</span><span class="sxs-lookup"><span data-stu-id="ed3d6-154">string</span></span> | <span data-ttu-id="ed3d6-155">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-155">Owner of the incident.</span></span>
<span data-ttu-id="ed3d6-156">classification</span><span class="sxs-lookup"><span data-stu-id="ed3d6-156">classification</span></span> | <span data-ttu-id="ed3d6-157">Enum</span><span class="sxs-lookup"><span data-stu-id="ed3d6-157">Enum</span></span> | <span data-ttu-id="ed3d6-158">Especificación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-158">Specification of the alert.</span></span> <span data-ttu-id="ed3d6-159">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="ed3d6-160">cálculo</span><span class="sxs-lookup"><span data-stu-id="ed3d6-160">determination</span></span> | <span data-ttu-id="ed3d6-161">Enum</span><span class="sxs-lookup"><span data-stu-id="ed3d6-161">Enum</span></span> | <span data-ttu-id="ed3d6-162">Especifica la determinación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="ed3d6-163">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="ed3d6-164">tags</span><span class="sxs-lookup"><span data-stu-id="ed3d6-164">tags</span></span> | <span data-ttu-id="ed3d6-165">Lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="ed3d6-165">string List</span></span> | <span data-ttu-id="ed3d6-166">Lista de etiquetas de incidente.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="ed3d6-167">Respuesta</span><span class="sxs-lookup"><span data-stu-id="ed3d6-167">Response</span></span>
<span data-ttu-id="ed3d6-168">Si se ejecuta correctamente, este método devuelve 200 OK y la entidad Incident en el cuerpo de la respuesta con las propiedades actualizadas.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="ed3d6-169">Si no se ha encontrado el incidente con el identificador especificado-404 no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="ed3d6-170">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed3d6-170">Example</span></span>

<span data-ttu-id="ed3d6-171">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="ed3d6-171">**Request**</span></span>

<span data-ttu-id="ed3d6-172">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ed3d6-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="ed3d6-173">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="ed3d6-173">Related topic</span></span>
- [<span data-ttu-id="ed3d6-174">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="ed3d6-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="ed3d6-175">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="ed3d6-175">List incidents</span></span>](api-list-incidents.md)
