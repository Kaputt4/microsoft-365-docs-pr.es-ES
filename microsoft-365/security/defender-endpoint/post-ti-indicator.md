---
title: Enviar o actualizar API de indicadores
description: Obtenga información sobre cómo usar la API Enviar o Actualizar indicador para enviar o actualizar una nueva entidad Indicator en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, submit, ti, indicator, update
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187362"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="d1ab4-104">Enviar o actualizar API de indicadores</span><span class="sxs-lookup"><span data-stu-id="d1ab4-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d1ab4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-105">**Applies to:**</span></span>
- [<span data-ttu-id="d1ab4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d1ab4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d1ab4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1ab4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d1ab4-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d1ab4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d1ab4-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="d1ab4-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="d1ab4-110">API description</span></span>
<span data-ttu-id="d1ab4-111">Envía o actualiza la nueva [entidad Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="d1ab4-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="d1ab4-112">No se admite la notación CIDR para IP.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="d1ab4-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="d1ab4-113">Limitations</span></span>
1. <span data-ttu-id="d1ab4-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="d1ab4-115">Hay un límite de 15.000 indicadores activos por inquilino.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="d1ab4-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="d1ab4-116">Permissions</span></span>
<span data-ttu-id="d1ab4-117">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d1ab4-118">Para obtener más información, incluido cómo elegir permisos, vea [Introducción](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d1ab4-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="d1ab4-119">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="d1ab4-119">Permission type</span></span> |   <span data-ttu-id="d1ab4-120">Permiso</span><span class="sxs-lookup"><span data-stu-id="d1ab4-120">Permission</span></span>  |   <span data-ttu-id="d1ab4-121">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="d1ab4-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d1ab4-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d1ab4-122">Application</span></span> |   <span data-ttu-id="d1ab4-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d1ab4-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="d1ab4-124">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="d1ab4-124">'Read and write Indicators'</span></span>
<span data-ttu-id="d1ab4-125">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d1ab4-125">Application</span></span> |   <span data-ttu-id="d1ab4-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d1ab4-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="d1ab4-127">'Leer y escribir todos los indicadores'</span><span class="sxs-lookup"><span data-stu-id="d1ab4-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="d1ab4-128">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="d1ab4-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="d1ab4-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d1ab4-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="d1ab4-130">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="d1ab4-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="d1ab4-131">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="d1ab4-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="d1ab4-132">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="d1ab4-132">Request headers</span></span>

<span data-ttu-id="d1ab4-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="d1ab4-133">Name</span></span> | <span data-ttu-id="d1ab4-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="d1ab4-134">Type</span></span> | <span data-ttu-id="d1ab4-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1ab4-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="d1ab4-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="d1ab4-136">Authorization</span></span> | <span data-ttu-id="d1ab4-137">Cadena</span><span class="sxs-lookup"><span data-stu-id="d1ab4-137">String</span></span> | <span data-ttu-id="d1ab4-138">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-138">Bearer {token}.</span></span> <span data-ttu-id="d1ab4-139">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-139">**Required**.</span></span>
<span data-ttu-id="d1ab4-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d1ab4-140">Content-Type</span></span> | <span data-ttu-id="d1ab4-141">string</span><span class="sxs-lookup"><span data-stu-id="d1ab4-141">string</span></span> | <span data-ttu-id="d1ab4-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-142">application/json.</span></span> <span data-ttu-id="d1ab4-143">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d1ab4-144">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="d1ab4-144">Request body</span></span>
<span data-ttu-id="d1ab4-145">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="d1ab4-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="d1ab4-146">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d1ab4-146">Parameter</span></span> | <span data-ttu-id="d1ab4-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="d1ab4-147">Type</span></span>    | <span data-ttu-id="d1ab4-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1ab4-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="d1ab4-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="d1ab4-149">indicatorValue</span></span> | <span data-ttu-id="d1ab4-150">Cadena</span><span class="sxs-lookup"><span data-stu-id="d1ab4-150">String</span></span> | <span data-ttu-id="d1ab4-151">Identidad de la [entidad Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="d1ab4-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="d1ab4-152">**Required**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-152">**Required**</span></span>
<span data-ttu-id="d1ab4-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="d1ab4-153">indicatorType</span></span> | <span data-ttu-id="d1ab4-154">Enum</span><span class="sxs-lookup"><span data-stu-id="d1ab4-154">Enum</span></span> | <span data-ttu-id="d1ab4-155">Tipo del indicador.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-155">Type of the indicator.</span></span> <span data-ttu-id="d1ab4-156">Los valores posibles son: "FileSha1", "FileSha256", "IpAddress", "DomainName" y "Url".</span><span class="sxs-lookup"><span data-stu-id="d1ab4-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="d1ab4-157">**Required**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-157">**Required**</span></span>
<span data-ttu-id="d1ab4-158">acción</span><span class="sxs-lookup"><span data-stu-id="d1ab4-158">action</span></span> | <span data-ttu-id="d1ab4-159">Enum</span><span class="sxs-lookup"><span data-stu-id="d1ab4-159">Enum</span></span> | <span data-ttu-id="d1ab4-160">La acción que se realizará si el indicador se detectará en la organización.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="d1ab4-161">Los valores posibles son: "Alert", "AlertAndBlock" y "Allowed".</span><span class="sxs-lookup"><span data-stu-id="d1ab4-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="d1ab4-162">**Required**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-162">**Required**</span></span>
<span data-ttu-id="d1ab4-163">aplicación</span><span class="sxs-lookup"><span data-stu-id="d1ab4-163">application</span></span> | <span data-ttu-id="d1ab4-164">Cadena</span><span class="sxs-lookup"><span data-stu-id="d1ab4-164">String</span></span> | <span data-ttu-id="d1ab4-165">La aplicación asociada al indicador.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-165">The application associated with the indicator.</span></span> <span data-ttu-id="d1ab4-166">**Optional**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-166">**Optional**</span></span>
<span data-ttu-id="d1ab4-167">title</span><span class="sxs-lookup"><span data-stu-id="d1ab4-167">title</span></span> | <span data-ttu-id="d1ab4-168">Cadena</span><span class="sxs-lookup"><span data-stu-id="d1ab4-168">String</span></span> | <span data-ttu-id="d1ab4-169">Título de alerta del indicador.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-169">Indicator alert title.</span></span> <span data-ttu-id="d1ab4-170">**Required**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-170">**Required**</span></span>
<span data-ttu-id="d1ab4-171">descripción</span><span class="sxs-lookup"><span data-stu-id="d1ab4-171">description</span></span> | <span data-ttu-id="d1ab4-172">Cadena</span><span class="sxs-lookup"><span data-stu-id="d1ab4-172">String</span></span> | <span data-ttu-id="d1ab4-173">Descripción del indicador.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-173">Description of the indicator.</span></span> <span data-ttu-id="d1ab4-174">**Required**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-174">**Required**</span></span>
<span data-ttu-id="d1ab4-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="d1ab4-175">expirationTime</span></span> | <span data-ttu-id="d1ab4-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d1ab4-176">DateTimeOffset</span></span> | <span data-ttu-id="d1ab4-177">La hora de expiración del indicador.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-177">The expiration time of the indicator.</span></span> <span data-ttu-id="d1ab4-178">**Optional**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-178">**Optional**</span></span>
<span data-ttu-id="d1ab4-179">severity</span><span class="sxs-lookup"><span data-stu-id="d1ab4-179">severity</span></span> | <span data-ttu-id="d1ab4-180">Enum</span><span class="sxs-lookup"><span data-stu-id="d1ab4-180">Enum</span></span> | <span data-ttu-id="d1ab4-181">Gravedad del indicador.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-181">The severity of the indicator.</span></span> <span data-ttu-id="d1ab4-182">los valores posibles son: "Informational", "Low", "Medium" y "High".</span><span class="sxs-lookup"><span data-stu-id="d1ab4-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="d1ab4-183">**Optional**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-183">**Optional**</span></span>
<span data-ttu-id="d1ab4-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="d1ab4-184">recommendedActions</span></span> | <span data-ttu-id="d1ab4-185">Cadena</span><span class="sxs-lookup"><span data-stu-id="d1ab4-185">String</span></span> | <span data-ttu-id="d1ab4-186">Acciones recomendadas de alerta del indicador TI.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="d1ab4-187">**Optional**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-187">**Optional**</span></span>
<span data-ttu-id="d1ab4-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="d1ab4-188">rbacGroupNames</span></span> | <span data-ttu-id="d1ab4-189">Cadena</span><span class="sxs-lookup"><span data-stu-id="d1ab4-189">String</span></span> | <span data-ttu-id="d1ab4-190">Lista separada por comas de nombres de grupo RBAC a los que se aplicaría el indicador.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="d1ab4-191">**Optional**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="d1ab4-192">Respuesta</span><span class="sxs-lookup"><span data-stu-id="d1ab4-192">Response</span></span>
- <span data-ttu-id="d1ab4-193">Si se realiza correctamente, este método devuelve 200: código de respuesta aceptar y la entidad [Indicator](ti-indicator.md) creada o actualizada en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="d1ab4-194">Si no se realiza correctamente: este método devuelve 400 - Solicitud mala.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="d1ab4-195">La solicitud incorrecta suele indicar un cuerpo incorrecto.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="d1ab4-196">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1ab4-196">Example</span></span>

<span data-ttu-id="d1ab4-197">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="d1ab4-197">**Request**</span></span>

<span data-ttu-id="d1ab4-198">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d1ab4-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="d1ab4-199">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="d1ab4-199">Related topic</span></span>
- [<span data-ttu-id="d1ab4-200">Administrar indicadores</span><span class="sxs-lookup"><span data-stu-id="d1ab4-200">Manage indicators</span></span>](manage-indicators.md)
