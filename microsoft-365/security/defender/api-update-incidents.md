---
title: ACTUALIZAR LA API de incidentes
description: Obtenga información sobre cómo actualizar incidentes con la API Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e3b445b2f9612f0113f353450ca7bf0b8a1a2bb2
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730863"
---
# <a name="update-incidents-api"></a><span data-ttu-id="3cc3a-104">ACTUALIZAR LA API de incidentes</span><span class="sxs-lookup"><span data-stu-id="3cc3a-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3cc3a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3cc3a-105">**Applies to:**</span></span>

- [<span data-ttu-id="3cc3a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cc3a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="3cc3a-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3cc3a-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="3cc3a-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="3cc3a-109">API description</span></span>

<span data-ttu-id="3cc3a-110">Actualiza las propiedades del incidente existente.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-110">Updates properties of existing incident.</span></span> <span data-ttu-id="3cc3a-111">Las propiedades actualizables son: ```status``` , , , , y ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="3cc3a-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="3cc3a-112">Cuotas, asignación de recursos y otras restricciones</span><span class="sxs-lookup"><span data-stu-id="3cc3a-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="3cc3a-113">Puede hacer hasta 50 llamadas por minuto o 1500 llamadas por hora antes de alcanzar el umbral de limitación.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="3cc3a-114">Solo puede establecer la `determination` propiedad si está establecida en `classification` TruePositive.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="3cc3a-115">Si la solicitud está limitada, devolverá un `429` código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="3cc3a-116">El cuerpo de la respuesta indicará la hora en que puede empezar a realizar llamadas nuevas.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="3cc3a-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="3cc3a-117">Permissions</span></span>

<span data-ttu-id="3cc3a-118">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3cc3a-119">Para obtener más información, incluido cómo elegir permisos, vea [Access the Microsoft 365 Defender API](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="3cc3a-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="3cc3a-120">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="3cc3a-120">Permission type</span></span> | <span data-ttu-id="3cc3a-121">Permiso</span><span class="sxs-lookup"><span data-stu-id="3cc3a-121">Permission</span></span> | <span data-ttu-id="3cc3a-122">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="3cc3a-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="3cc3a-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="3cc3a-123">Application</span></span> | <span data-ttu-id="3cc3a-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3cc3a-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="3cc3a-125">Leer y escribir todos los incidentes</span><span class="sxs-lookup"><span data-stu-id="3cc3a-125">Read and write all incidents</span></span>
<span data-ttu-id="3cc3a-126">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="3cc3a-126">Delegated (work or school account)</span></span> | <span data-ttu-id="3cc3a-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3cc3a-127">Incident.ReadWrite</span></span> | <span data-ttu-id="3cc3a-128">Incidentes de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="3cc3a-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="3cc3a-129">Al obtener un token con credenciales de usuario, el usuario debe tener permiso para actualizar el incidente en el portal.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="3cc3a-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="3cc3a-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="3cc3a-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="3cc3a-131">Request headers</span></span>

<span data-ttu-id="3cc3a-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="3cc3a-132">Name</span></span> | <span data-ttu-id="3cc3a-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="3cc3a-133">Type</span></span> | <span data-ttu-id="3cc3a-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cc3a-134">Description</span></span>
-|-|-
<span data-ttu-id="3cc3a-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="3cc3a-135">Authorization</span></span> | <span data-ttu-id="3cc3a-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="3cc3a-136">String</span></span> | <span data-ttu-id="3cc3a-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-137">Bearer {token}.</span></span> <span data-ttu-id="3cc3a-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-138">**Required**.</span></span>
<span data-ttu-id="3cc3a-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3cc3a-139">Content-Type</span></span> | <span data-ttu-id="3cc3a-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="3cc3a-140">String</span></span> | <span data-ttu-id="3cc3a-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-141">application/json.</span></span> <span data-ttu-id="3cc3a-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3cc3a-143">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="3cc3a-143">Request body</span></span>

<span data-ttu-id="3cc3a-144">En el cuerpo de la solicitud, proporcione los valores de los campos que deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="3cc3a-145">Las propiedades existentes que no se incluyen en el cuerpo de la solicitud mantendrán sus valores, a menos que tengan que volver a calcularse debido a los cambios en los valores relacionados.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="3cc3a-146">Para obtener el mejor rendimiento, debe omitir los valores existentes que no han cambiado.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="3cc3a-147">Propiedad</span><span class="sxs-lookup"><span data-stu-id="3cc3a-147">Property</span></span> | <span data-ttu-id="3cc3a-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="3cc3a-148">Type</span></span> | <span data-ttu-id="3cc3a-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cc3a-149">Description</span></span>
-|-|-
<span data-ttu-id="3cc3a-150">status</span><span class="sxs-lookup"><span data-stu-id="3cc3a-150">status</span></span> | <span data-ttu-id="3cc3a-151">Enum</span><span class="sxs-lookup"><span data-stu-id="3cc3a-151">Enum</span></span> | <span data-ttu-id="3cc3a-152">Especifica el estado actual del incidente.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="3cc3a-153">Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="3cc3a-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="3cc3a-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="3cc3a-154">assignedTo</span></span> | <span data-ttu-id="3cc3a-155">cadena</span><span class="sxs-lookup"><span data-stu-id="3cc3a-155">string</span></span> | <span data-ttu-id="3cc3a-156">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-156">Owner of the incident.</span></span>
<span data-ttu-id="3cc3a-157">classification</span><span class="sxs-lookup"><span data-stu-id="3cc3a-157">classification</span></span> | <span data-ttu-id="3cc3a-158">Enum</span><span class="sxs-lookup"><span data-stu-id="3cc3a-158">Enum</span></span> | <span data-ttu-id="3cc3a-159">Especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-159">Specification of the incident.</span></span> <span data-ttu-id="3cc3a-160">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="3cc3a-161">determinación</span><span class="sxs-lookup"><span data-stu-id="3cc3a-161">determination</span></span> | <span data-ttu-id="3cc3a-162">Enum</span><span class="sxs-lookup"><span data-stu-id="3cc3a-162">Enum</span></span> | <span data-ttu-id="3cc3a-163">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="3cc3a-164">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="3cc3a-165">tags</span><span class="sxs-lookup"><span data-stu-id="3cc3a-165">tags</span></span> | <span data-ttu-id="3cc3a-166">lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="3cc3a-166">string List</span></span> | <span data-ttu-id="3cc3a-167">Lista de etiquetas de incidentes.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-167">List of Incident tags.</span></span>
<span data-ttu-id="3cc3a-168">comment</span><span class="sxs-lookup"><span data-stu-id="3cc3a-168">comment</span></span> | <span data-ttu-id="3cc3a-169">string</span><span class="sxs-lookup"><span data-stu-id="3cc3a-169">string</span></span> | <span data-ttu-id="3cc3a-170">Comentario que se agregará al incidente.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="3cc3a-171">Respuesta</span><span class="sxs-lookup"><span data-stu-id="3cc3a-171">Response</span></span>

<span data-ttu-id="3cc3a-172">Si se realiza correctamente, este método devuelve `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="3cc3a-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="3cc3a-173">El cuerpo de la respuesta contendrá la entidad incident con propiedades actualizadas.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="3cc3a-174">Si no se encontró un incidente con el identificador especificado, el método devuelve `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="3cc3a-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="3cc3a-175">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3cc3a-175">Example</span></span>

<span data-ttu-id="3cc3a-176">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="3cc3a-176">**Request**</span></span>

<span data-ttu-id="3cc3a-177">Este es un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3cc3a-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="3cc3a-178">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="3cc3a-178">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a><span data-ttu-id="3cc3a-179">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="3cc3a-179">Related articles</span></span>

- [<span data-ttu-id="3cc3a-180">Acceder a las API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cc3a-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="3cc3a-181">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="3cc3a-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="3cc3a-182">Comprender códigos de error</span><span class="sxs-lookup"><span data-stu-id="3cc3a-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="3cc3a-183">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="3cc3a-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="3cc3a-184">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="3cc3a-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="3cc3a-185">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="3cc3a-185">Incidents overview</span></span>](incidents-overview.md)
