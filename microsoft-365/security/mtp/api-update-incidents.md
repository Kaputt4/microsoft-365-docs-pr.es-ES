---
title: Actualizar la API de incidentes
description: Obtenga información sobre cómo actualizar incidentes con la API de Microsoft 365 defender
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719409"
---
# <a name="update-incidents-api"></a><span data-ttu-id="438ab-104">Actualizar la API de incidentes</span><span class="sxs-lookup"><span data-stu-id="438ab-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="438ab-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="438ab-105">**Applies to:**</span></span>

- <span data-ttu-id="438ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="438ab-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="438ab-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="438ab-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="438ab-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="438ab-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="438ab-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="438ab-109">API description</span></span>

<span data-ttu-id="438ab-110">Actualiza las propiedades de un incidente existente.</span><span class="sxs-lookup"><span data-stu-id="438ab-110">Updates properties of existing incident.</span></span> <span data-ttu-id="438ab-111">Las propiedades actualizables son: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` y ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="438ab-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="438ab-112">Cuotas, asignación de recursos y otras restricciones</span><span class="sxs-lookup"><span data-stu-id="438ab-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="438ab-113">Puede realizar hasta 50 llamadas por minuto o 1500 llamadas por hora antes de alcanzar el umbral de limitación.</span><span class="sxs-lookup"><span data-stu-id="438ab-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="438ab-114">Puede establecer la `determination` propiedad solo si `classification` está establecida en TruePositive.</span><span class="sxs-lookup"><span data-stu-id="438ab-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="438ab-115">Si se limita la solicitud, se devolverá un `429` código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="438ab-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="438ab-116">El cuerpo de la respuesta indicará la hora en la que puede empezar a realizar nuevas llamadas.</span><span class="sxs-lookup"><span data-stu-id="438ab-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="438ab-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="438ab-117">Permissions</span></span>

<span data-ttu-id="438ab-118">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="438ab-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="438ab-119">Para obtener más información, incluido cómo elegir permisos, consulte [acceso a las API de Microsoft 365 defender](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="438ab-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="438ab-120">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="438ab-120">Permission type</span></span> | <span data-ttu-id="438ab-121">Permiso</span><span class="sxs-lookup"><span data-stu-id="438ab-121">Permission</span></span> | <span data-ttu-id="438ab-122">Nombre para mostrar del permiso</span><span class="sxs-lookup"><span data-stu-id="438ab-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="438ab-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="438ab-123">Application</span></span> | <span data-ttu-id="438ab-124">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="438ab-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="438ab-125">Leer y escribir todos los incidentes</span><span class="sxs-lookup"><span data-stu-id="438ab-125">Read and write all incidents</span></span>
<span data-ttu-id="438ab-126">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="438ab-126">Delegated (work or school account)</span></span> | <span data-ttu-id="438ab-127">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="438ab-127">Incident.ReadWrite</span></span> | <span data-ttu-id="438ab-128">Leer y escribir incidentes</span><span class="sxs-lookup"><span data-stu-id="438ab-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="438ab-129">Al obtener un token con credenciales de usuario, el usuario debe tener permiso para actualizar el incidente en el portal.</span><span class="sxs-lookup"><span data-stu-id="438ab-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="438ab-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="438ab-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="438ab-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="438ab-131">Request headers</span></span>

<span data-ttu-id="438ab-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="438ab-132">Name</span></span> | <span data-ttu-id="438ab-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="438ab-133">Type</span></span> | <span data-ttu-id="438ab-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="438ab-134">Description</span></span>
-|-|-
<span data-ttu-id="438ab-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="438ab-135">Authorization</span></span> | <span data-ttu-id="438ab-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="438ab-136">String</span></span> | <span data-ttu-id="438ab-137">{Token} de portador.</span><span class="sxs-lookup"><span data-stu-id="438ab-137">Bearer {token}.</span></span> <span data-ttu-id="438ab-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="438ab-138">**Required**.</span></span>
<span data-ttu-id="438ab-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="438ab-139">Content-Type</span></span> | <span data-ttu-id="438ab-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="438ab-140">String</span></span> | <span data-ttu-id="438ab-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="438ab-141">application/json.</span></span> <span data-ttu-id="438ab-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="438ab-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="438ab-143">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="438ab-143">Request body</span></span>

<span data-ttu-id="438ab-144">En el cuerpo de la solicitud, proporcione los valores de los campos que se deben actualizar.</span><span class="sxs-lookup"><span data-stu-id="438ab-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="438ab-145">Las propiedades existentes que no se incluyen en el cuerpo de la solicitud conservarán sus valores, a menos que se deban volver a calcular debido a cambios en los valores relacionados.</span><span class="sxs-lookup"><span data-stu-id="438ab-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="438ab-146">Para obtener el mejor rendimiento, debe omitir los valores existentes que no han cambiado.</span><span class="sxs-lookup"><span data-stu-id="438ab-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="438ab-147">Propiedad</span><span class="sxs-lookup"><span data-stu-id="438ab-147">Property</span></span> | <span data-ttu-id="438ab-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="438ab-148">Type</span></span> | <span data-ttu-id="438ab-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="438ab-149">Description</span></span>
-|-|-
<span data-ttu-id="438ab-150">status</span><span class="sxs-lookup"><span data-stu-id="438ab-150">status</span></span> | <span data-ttu-id="438ab-151">Enum</span><span class="sxs-lookup"><span data-stu-id="438ab-151">Enum</span></span> | <span data-ttu-id="438ab-152">Especifica el estado actual de la alerta.</span><span class="sxs-lookup"><span data-stu-id="438ab-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="438ab-153">Los valores posibles son: ```Active``` , ```Resolved``` y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="438ab-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="438ab-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="438ab-154">assignedTo</span></span> | <span data-ttu-id="438ab-155">cadena</span><span class="sxs-lookup"><span data-stu-id="438ab-155">string</span></span> | <span data-ttu-id="438ab-156">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="438ab-156">Owner of the incident.</span></span>
<span data-ttu-id="438ab-157">classification</span><span class="sxs-lookup"><span data-stu-id="438ab-157">classification</span></span> | <span data-ttu-id="438ab-158">Enum</span><span class="sxs-lookup"><span data-stu-id="438ab-158">Enum</span></span> | <span data-ttu-id="438ab-159">Especificación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="438ab-159">Specification of the alert.</span></span> <span data-ttu-id="438ab-160">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="438ab-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="438ab-161">cálculo</span><span class="sxs-lookup"><span data-stu-id="438ab-161">determination</span></span> | <span data-ttu-id="438ab-162">Enum</span><span class="sxs-lookup"><span data-stu-id="438ab-162">Enum</span></span> | <span data-ttu-id="438ab-163">Especifica la determinación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="438ab-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="438ab-164">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="438ab-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="438ab-165">tags</span><span class="sxs-lookup"><span data-stu-id="438ab-165">tags</span></span> | <span data-ttu-id="438ab-166">Lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="438ab-166">string List</span></span> | <span data-ttu-id="438ab-167">Lista de etiquetas de incidente.</span><span class="sxs-lookup"><span data-stu-id="438ab-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="438ab-168">Respuesta</span><span class="sxs-lookup"><span data-stu-id="438ab-168">Response</span></span>

<span data-ttu-id="438ab-169">Si se ejecuta correctamente, este método devuelve `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="438ab-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="438ab-170">El cuerpo de la respuesta contendrá la entidad incidente con propiedades actualizadas.</span><span class="sxs-lookup"><span data-stu-id="438ab-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="438ab-171">Si no se ha encontrado un incidente con el identificador especificado, el método devuelve `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="438ab-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="438ab-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="438ab-172">Example</span></span>

<span data-ttu-id="438ab-173">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="438ab-173">**Request**</span></span>

<span data-ttu-id="438ab-174">Este es un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="438ab-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="438ab-175">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="438ab-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="438ab-176">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="438ab-176">Related articles</span></span>

- [<span data-ttu-id="438ab-177">Acceso a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="438ab-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="438ab-178">Obtenga información sobre los límites de API y las licencias</span><span class="sxs-lookup"><span data-stu-id="438ab-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="438ab-179">Descripción de los códigos de error</span><span class="sxs-lookup"><span data-stu-id="438ab-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="438ab-180">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="438ab-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="438ab-181">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="438ab-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="438ab-182">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="438ab-182">Incidents overview</span></span>](incidents-overview.md)
