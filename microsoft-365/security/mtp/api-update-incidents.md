---
title: ACTUALIZAR LA API de incidentes
description: Obtenga información sobre cómo actualizar incidentes con la API de Microsoft 365 Defender
keywords: update, api, incident
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929075"
---
# <a name="update-incidents-api"></a><span data-ttu-id="48e0d-104">ACTUALIZAR LA API de incidentes</span><span class="sxs-lookup"><span data-stu-id="48e0d-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="48e0d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="48e0d-105">**Applies to:**</span></span>

- <span data-ttu-id="48e0d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48e0d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48e0d-107">Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="48e0d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="48e0d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="48e0d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="48e0d-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="48e0d-109">API description</span></span>

<span data-ttu-id="48e0d-110">Actualiza las propiedades del incidente existente.</span><span class="sxs-lookup"><span data-stu-id="48e0d-110">Updates properties of existing incident.</span></span> <span data-ttu-id="48e0d-111">Las propiedades actualizables son: ```status``` ```determination``` , , y ```classification``` ```assignedTo``` ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="48e0d-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="48e0d-112">Cuotas, asignación de recursos y otras restricciones</span><span class="sxs-lookup"><span data-stu-id="48e0d-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="48e0d-113">Puede realizar hasta 50 llamadas por minuto o 1500 llamadas por hora antes de alcanzar el umbral de limitación.</span><span class="sxs-lookup"><span data-stu-id="48e0d-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="48e0d-114">La propiedad sólo `determination` se puede establecer si se establece en `classification` TruePositive.</span><span class="sxs-lookup"><span data-stu-id="48e0d-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="48e0d-115">Si la solicitud está limitada, devolverá un código `429` de respuesta.</span><span class="sxs-lookup"><span data-stu-id="48e0d-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="48e0d-116">El cuerpo de la respuesta indicará la hora en que puede empezar a realizar nuevas llamadas.</span><span class="sxs-lookup"><span data-stu-id="48e0d-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="48e0d-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="48e0d-117">Permissions</span></span>

<span data-ttu-id="48e0d-118">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="48e0d-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="48e0d-119">Para obtener más información, incluido cómo elegir permisos, vea Obtener acceso a las API de [Microsoft 365 Defender.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="48e0d-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="48e0d-120">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="48e0d-120">Permission type</span></span> | <span data-ttu-id="48e0d-121">Permiso</span><span class="sxs-lookup"><span data-stu-id="48e0d-121">Permission</span></span> | <span data-ttu-id="48e0d-122">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="48e0d-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="48e0d-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="48e0d-123">Application</span></span> | <span data-ttu-id="48e0d-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="48e0d-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="48e0d-125">Leer y escribir todos los incidentes</span><span class="sxs-lookup"><span data-stu-id="48e0d-125">Read and write all incidents</span></span>
<span data-ttu-id="48e0d-126">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="48e0d-126">Delegated (work or school account)</span></span> | <span data-ttu-id="48e0d-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="48e0d-127">Incident.ReadWrite</span></span> | <span data-ttu-id="48e0d-128">Leer y escribir incidentes</span><span class="sxs-lookup"><span data-stu-id="48e0d-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="48e0d-129">Al obtener un token con credenciales de usuario, el usuario debe tener permiso para actualizar el incidente en el portal.</span><span class="sxs-lookup"><span data-stu-id="48e0d-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="48e0d-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="48e0d-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="48e0d-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="48e0d-131">Request headers</span></span>

<span data-ttu-id="48e0d-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="48e0d-132">Name</span></span> | <span data-ttu-id="48e0d-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="48e0d-133">Type</span></span> | <span data-ttu-id="48e0d-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="48e0d-134">Description</span></span>
-|-|-
<span data-ttu-id="48e0d-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="48e0d-135">Authorization</span></span> | <span data-ttu-id="48e0d-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="48e0d-136">String</span></span> | <span data-ttu-id="48e0d-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="48e0d-137">Bearer {token}.</span></span> <span data-ttu-id="48e0d-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="48e0d-138">**Required**.</span></span>
<span data-ttu-id="48e0d-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="48e0d-139">Content-Type</span></span> | <span data-ttu-id="48e0d-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="48e0d-140">String</span></span> | <span data-ttu-id="48e0d-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="48e0d-141">application/json.</span></span> <span data-ttu-id="48e0d-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="48e0d-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="48e0d-143">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="48e0d-143">Request body</span></span>

<span data-ttu-id="48e0d-144">En el cuerpo de la solicitud, proporcione los valores de los campos que se deben actualizar.</span><span class="sxs-lookup"><span data-stu-id="48e0d-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="48e0d-145">Las propiedades existentes que no se incluyen en el cuerpo de la solicitud mantendrán sus valores, a menos que tengan que volver a calcularse debido a cambios en los valores relacionados.</span><span class="sxs-lookup"><span data-stu-id="48e0d-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="48e0d-146">Para obtener el mejor rendimiento, debe omitir los valores existentes que no han cambiado.</span><span class="sxs-lookup"><span data-stu-id="48e0d-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="48e0d-147">Propiedad</span><span class="sxs-lookup"><span data-stu-id="48e0d-147">Property</span></span> | <span data-ttu-id="48e0d-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="48e0d-148">Type</span></span> | <span data-ttu-id="48e0d-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="48e0d-149">Description</span></span>
-|-|-
<span data-ttu-id="48e0d-150">status</span><span class="sxs-lookup"><span data-stu-id="48e0d-150">status</span></span> | <span data-ttu-id="48e0d-151">Enum</span><span class="sxs-lookup"><span data-stu-id="48e0d-151">Enum</span></span> | <span data-ttu-id="48e0d-152">Especifica el estado actual de la alerta.</span><span class="sxs-lookup"><span data-stu-id="48e0d-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="48e0d-153">Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="48e0d-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="48e0d-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="48e0d-154">assignedTo</span></span> | <span data-ttu-id="48e0d-155">string</span><span class="sxs-lookup"><span data-stu-id="48e0d-155">string</span></span> | <span data-ttu-id="48e0d-156">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="48e0d-156">Owner of the incident.</span></span>
<span data-ttu-id="48e0d-157">classification</span><span class="sxs-lookup"><span data-stu-id="48e0d-157">classification</span></span> | <span data-ttu-id="48e0d-158">Enum</span><span class="sxs-lookup"><span data-stu-id="48e0d-158">Enum</span></span> | <span data-ttu-id="48e0d-159">Especificación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="48e0d-159">Specification of the alert.</span></span> <span data-ttu-id="48e0d-160">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="48e0d-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="48e0d-161">determinación</span><span class="sxs-lookup"><span data-stu-id="48e0d-161">determination</span></span> | <span data-ttu-id="48e0d-162">Enum</span><span class="sxs-lookup"><span data-stu-id="48e0d-162">Enum</span></span> | <span data-ttu-id="48e0d-163">Especifica la determinación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="48e0d-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="48e0d-164">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="48e0d-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="48e0d-165">tags</span><span class="sxs-lookup"><span data-stu-id="48e0d-165">tags</span></span> | <span data-ttu-id="48e0d-166">lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="48e0d-166">string List</span></span> | <span data-ttu-id="48e0d-167">Lista de etiquetas de incidentes.</span><span class="sxs-lookup"><span data-stu-id="48e0d-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="48e0d-168">Respuesta</span><span class="sxs-lookup"><span data-stu-id="48e0d-168">Response</span></span>

<span data-ttu-id="48e0d-169">Si se realiza correctamente, este método devuelve `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="48e0d-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="48e0d-170">El cuerpo de la respuesta contendrá la entidad del incidente con propiedades actualizadas.</span><span class="sxs-lookup"><span data-stu-id="48e0d-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="48e0d-171">Si no se encontró un incidente con el identificador especificado, el método devuelve `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="48e0d-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="48e0d-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="48e0d-172">Example</span></span>

<span data-ttu-id="48e0d-173">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="48e0d-173">**Request**</span></span>

<span data-ttu-id="48e0d-174">Este es un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="48e0d-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="48e0d-175">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="48e0d-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="48e0d-176">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="48e0d-176">Related articles</span></span>

- [<span data-ttu-id="48e0d-177">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48e0d-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="48e0d-178">Más información sobre los límites de la API y las licencias</span><span class="sxs-lookup"><span data-stu-id="48e0d-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="48e0d-179">Comprender los códigos de error</span><span class="sxs-lookup"><span data-stu-id="48e0d-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="48e0d-180">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="48e0d-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="48e0d-181">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="48e0d-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="48e0d-182">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="48e0d-182">Incidents overview</span></span>](incidents-overview.md)
