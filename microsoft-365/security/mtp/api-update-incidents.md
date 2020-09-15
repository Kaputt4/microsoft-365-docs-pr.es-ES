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
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650520"
---
# <a name="update-incidents-api"></a><span data-ttu-id="a4d1f-104">Actualizar la API de incidentes</span><span class="sxs-lookup"><span data-stu-id="a4d1f-104">Update incidents API</span></span>

<span data-ttu-id="a4d1f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a4d1f-105">**Applies to:**</span></span>
- <span data-ttu-id="a4d1f-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a4d1f-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="a4d1f-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a4d1f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="a4d1f-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="a4d1f-109">API description</span></span>
<span data-ttu-id="a4d1f-110">Actualiza las propiedades de un incidente existente.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="a4d1f-111">Las propiedades actualizables son: ```status``` ,, ```determination``` ```classification``` ```assignedTo``` y ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="a4d1f-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="a4d1f-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="a4d1f-112">Limitations</span></span>
1. <span data-ttu-id="a4d1f-113">Las limitaciones de frecuencia de esta API son 50 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="a4d1f-114">Puede establecer la ```determination``` sola si la clasificación se establece en TruePositive.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="a4d1f-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="a4d1f-115">Permissions</span></span>
<span data-ttu-id="a4d1f-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a4d1f-117">Para obtener más información, incluido cómo elegir permisos, consulte [acceso a las API de Microsoft Threat Protection](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="a4d1f-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="a4d1f-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="a4d1f-118">Permission type</span></span> |   <span data-ttu-id="a4d1f-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="a4d1f-119">Permission</span></span>  |   <span data-ttu-id="a4d1f-120">Nombre para mostrar del permiso</span><span class="sxs-lookup"><span data-stu-id="a4d1f-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a4d1f-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="a4d1f-121">Application</span></span> |   <span data-ttu-id="a4d1f-122">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="a4d1f-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="a4d1f-123">' Leer y escribir todos los incidentes '</span><span class="sxs-lookup"><span data-stu-id="a4d1f-123">'Read and write all incidents'</span></span>
<span data-ttu-id="a4d1f-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="a4d1f-124">Delegated (work or school account)</span></span> | <span data-ttu-id="a4d1f-125">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a4d1f-125">Incident.ReadWrite</span></span> | <span data-ttu-id="a4d1f-126">' Incidentes de lectura y escritura '</span><span class="sxs-lookup"><span data-stu-id="a4d1f-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="a4d1f-127">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="a4d1f-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a4d1f-128">El usuario debe tener permiso para actualizar el incidente en el portal.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="a4d1f-129">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="a4d1f-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="a4d1f-130">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="a4d1f-130">Request headers</span></span>

<span data-ttu-id="a4d1f-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="a4d1f-131">Name</span></span> | <span data-ttu-id="a4d1f-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="a4d1f-132">Type</span></span> | <span data-ttu-id="a4d1f-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4d1f-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="a4d1f-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="a4d1f-134">Authorization</span></span> | <span data-ttu-id="a4d1f-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="a4d1f-135">String</span></span> | <span data-ttu-id="a4d1f-136">{Token} de portador.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-136">Bearer {token}.</span></span> <span data-ttu-id="a4d1f-137">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-137">**Required**.</span></span>
<span data-ttu-id="a4d1f-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a4d1f-138">Content-Type</span></span> | <span data-ttu-id="a4d1f-139">Cadena</span><span class="sxs-lookup"><span data-stu-id="a4d1f-139">String</span></span> | <span data-ttu-id="a4d1f-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-140">application/json.</span></span> <span data-ttu-id="a4d1f-141">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a4d1f-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="a4d1f-142">Request body</span></span>
<span data-ttu-id="a4d1f-143">En el cuerpo de la solicitud, proporcione los valores de los campos relevantes que deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="a4d1f-144">Las propiedades existentes que no se incluyan en el cuerpo de la solicitud mantendrán los valores anteriores o se recalcularán según los cambios efectuados en otros valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="a4d1f-145">Para obtener el mejor rendimiento, no debe incluir valores existentes que no hayan cambiado.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="a4d1f-146">Propiedad</span><span class="sxs-lookup"><span data-stu-id="a4d1f-146">Property</span></span> | <span data-ttu-id="a4d1f-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="a4d1f-147">Type</span></span> | <span data-ttu-id="a4d1f-148">Description</span><span class="sxs-lookup"><span data-stu-id="a4d1f-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="a4d1f-149">status</span><span class="sxs-lookup"><span data-stu-id="a4d1f-149">status</span></span> | <span data-ttu-id="a4d1f-150">Enum</span><span class="sxs-lookup"><span data-stu-id="a4d1f-150">Enum</span></span> | <span data-ttu-id="a4d1f-151">Especifica el estado actual de la alerta.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="a4d1f-152">Los valores posibles son ```Active``` : ```Resolved``` y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="a4d1f-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="a4d1f-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="a4d1f-153">assignedTo</span></span> | <span data-ttu-id="a4d1f-154">cadena</span><span class="sxs-lookup"><span data-stu-id="a4d1f-154">string</span></span> | <span data-ttu-id="a4d1f-155">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-155">Owner of the incident.</span></span>
<span data-ttu-id="a4d1f-156">classification</span><span class="sxs-lookup"><span data-stu-id="a4d1f-156">classification</span></span> | <span data-ttu-id="a4d1f-157">Enum</span><span class="sxs-lookup"><span data-stu-id="a4d1f-157">Enum</span></span> | <span data-ttu-id="a4d1f-158">Especificación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-158">Specification of the alert.</span></span> <span data-ttu-id="a4d1f-159">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="a4d1f-160">cálculo</span><span class="sxs-lookup"><span data-stu-id="a4d1f-160">determination</span></span> | <span data-ttu-id="a4d1f-161">Enum</span><span class="sxs-lookup"><span data-stu-id="a4d1f-161">Enum</span></span> | <span data-ttu-id="a4d1f-162">Especifica la determinación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="a4d1f-163">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="a4d1f-164">tags</span><span class="sxs-lookup"><span data-stu-id="a4d1f-164">tags</span></span> | <span data-ttu-id="a4d1f-165">Lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="a4d1f-165">string List</span></span> | <span data-ttu-id="a4d1f-166">Lista de etiquetas de incidente.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="a4d1f-167">Respuesta</span><span class="sxs-lookup"><span data-stu-id="a4d1f-167">Response</span></span>
<span data-ttu-id="a4d1f-168">Si se ejecuta correctamente, este método devuelve 200 OK y la entidad Incident en el cuerpo de la respuesta con las propiedades actualizadas.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="a4d1f-169">Si no se ha encontrado el incidente con el identificador especificado-404 no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="a4d1f-170">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4d1f-170">Example</span></span>

<span data-ttu-id="a4d1f-171">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="a4d1f-171">**Request**</span></span>

<span data-ttu-id="a4d1f-172">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a4d1f-172">Here is an example of the request.</span></span>

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


## <a name="related-topic"></a><span data-ttu-id="a4d1f-173">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="a4d1f-173">Related topic</span></span>
- [<span data-ttu-id="a4d1f-174">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="a4d1f-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="a4d1f-175">Enumerar incidentes</span><span class="sxs-lookup"><span data-stu-id="a4d1f-175">List incidents</span></span>](api-list-incidents.md)