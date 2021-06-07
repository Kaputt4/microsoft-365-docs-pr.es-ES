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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ce0dc0ce255e9717082687bd1f8bf5941739261d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771710"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="e94d3-104">Enviar o actualizar API de indicadores</span><span class="sxs-lookup"><span data-stu-id="e94d3-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e94d3-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e94d3-105">**Applies to:**</span></span>
- [<span data-ttu-id="e94d3-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e94d3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e94d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e94d3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e94d3-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e94d3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e94d3-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e94d3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="e94d3-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="e94d3-110">API description</span></span>
<span data-ttu-id="e94d3-111">Envía o actualiza la nueva [entidad Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="e94d3-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="e94d3-112">No se admite la notación CIDR para IP.</span><span class="sxs-lookup"><span data-stu-id="e94d3-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="e94d3-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="e94d3-113">Limitations</span></span>
1. <span data-ttu-id="e94d3-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="e94d3-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="e94d3-115">Hay un límite de 15.000 indicadores activos por inquilino.</span><span class="sxs-lookup"><span data-stu-id="e94d3-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="e94d3-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="e94d3-116">Permissions</span></span>
<span data-ttu-id="e94d3-117">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="e94d3-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e94d3-118">Para obtener más información, incluido cómo elegir permisos, vea [Introducción](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e94d3-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="e94d3-119">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="e94d3-119">Permission type</span></span> |   <span data-ttu-id="e94d3-120">Permiso</span><span class="sxs-lookup"><span data-stu-id="e94d3-120">Permission</span></span>  |   <span data-ttu-id="e94d3-121">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="e94d3-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e94d3-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="e94d3-122">Application</span></span> |   <span data-ttu-id="e94d3-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e94d3-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="e94d3-124">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="e94d3-124">'Read and write Indicators'</span></span>
<span data-ttu-id="e94d3-125">Aplicación</span><span class="sxs-lookup"><span data-stu-id="e94d3-125">Application</span></span> |   <span data-ttu-id="e94d3-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e94d3-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="e94d3-127">'Leer y escribir todos los indicadores'</span><span class="sxs-lookup"><span data-stu-id="e94d3-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="e94d3-128">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="e94d3-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="e94d3-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e94d3-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="e94d3-130">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="e94d3-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="e94d3-131">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="e94d3-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="e94d3-132">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="e94d3-132">Request headers</span></span>

<span data-ttu-id="e94d3-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="e94d3-133">Name</span></span> | <span data-ttu-id="e94d3-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="e94d3-134">Type</span></span> | <span data-ttu-id="e94d3-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="e94d3-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="e94d3-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="e94d3-136">Authorization</span></span> | <span data-ttu-id="e94d3-137">Cadena</span><span class="sxs-lookup"><span data-stu-id="e94d3-137">String</span></span> | <span data-ttu-id="e94d3-138">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="e94d3-138">Bearer {token}.</span></span> <span data-ttu-id="e94d3-139">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="e94d3-139">**Required**.</span></span>
<span data-ttu-id="e94d3-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e94d3-140">Content-Type</span></span> | <span data-ttu-id="e94d3-141">cadena</span><span class="sxs-lookup"><span data-stu-id="e94d3-141">string</span></span> | <span data-ttu-id="e94d3-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="e94d3-142">application/json.</span></span> <span data-ttu-id="e94d3-143">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="e94d3-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e94d3-144">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="e94d3-144">Request body</span></span>
<span data-ttu-id="e94d3-145">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e94d3-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="e94d3-146">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e94d3-146">Parameter</span></span> | <span data-ttu-id="e94d3-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="e94d3-147">Type</span></span>    | <span data-ttu-id="e94d3-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="e94d3-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="e94d3-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="e94d3-149">indicatorValue</span></span> | <span data-ttu-id="e94d3-150">Cadena</span><span class="sxs-lookup"><span data-stu-id="e94d3-150">String</span></span> | <span data-ttu-id="e94d3-151">Identidad de la [entidad Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="e94d3-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="e94d3-152">**Required**</span><span class="sxs-lookup"><span data-stu-id="e94d3-152">**Required**</span></span>
<span data-ttu-id="e94d3-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="e94d3-153">indicatorType</span></span> | <span data-ttu-id="e94d3-154">Enum</span><span class="sxs-lookup"><span data-stu-id="e94d3-154">Enum</span></span> | <span data-ttu-id="e94d3-155">Tipo del indicador.</span><span class="sxs-lookup"><span data-stu-id="e94d3-155">Type of the indicator.</span></span> <span data-ttu-id="e94d3-156">Los valores posibles son: "FileSha1", "FileSha256", "IpAddress", "DomainName" y "Url".</span><span class="sxs-lookup"><span data-stu-id="e94d3-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="e94d3-157">**Required**</span><span class="sxs-lookup"><span data-stu-id="e94d3-157">**Required**</span></span>
<span data-ttu-id="e94d3-158">acción</span><span class="sxs-lookup"><span data-stu-id="e94d3-158">action</span></span> | <span data-ttu-id="e94d3-159">Enum</span><span class="sxs-lookup"><span data-stu-id="e94d3-159">Enum</span></span> | <span data-ttu-id="e94d3-160">La acción que se realizará si el indicador se detectará en la organización.</span><span class="sxs-lookup"><span data-stu-id="e94d3-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="e94d3-161">Los valores posibles son: "Alert", "AlertAndBlock" y "Allowed".</span><span class="sxs-lookup"><span data-stu-id="e94d3-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="e94d3-162">**Required**</span><span class="sxs-lookup"><span data-stu-id="e94d3-162">**Required**</span></span>
<span data-ttu-id="e94d3-163">aplicación</span><span class="sxs-lookup"><span data-stu-id="e94d3-163">application</span></span> | <span data-ttu-id="e94d3-164">Cadena</span><span class="sxs-lookup"><span data-stu-id="e94d3-164">String</span></span> | <span data-ttu-id="e94d3-165">La aplicación asociada al indicador.</span><span class="sxs-lookup"><span data-stu-id="e94d3-165">The application associated with the indicator.</span></span> <span data-ttu-id="e94d3-166">**Optional**</span><span class="sxs-lookup"><span data-stu-id="e94d3-166">**Optional**</span></span>
<span data-ttu-id="e94d3-167">title</span><span class="sxs-lookup"><span data-stu-id="e94d3-167">title</span></span> | <span data-ttu-id="e94d3-168">Cadena</span><span class="sxs-lookup"><span data-stu-id="e94d3-168">String</span></span> | <span data-ttu-id="e94d3-169">Título de alerta del indicador.</span><span class="sxs-lookup"><span data-stu-id="e94d3-169">Indicator alert title.</span></span> <span data-ttu-id="e94d3-170">**Required**</span><span class="sxs-lookup"><span data-stu-id="e94d3-170">**Required**</span></span>
<span data-ttu-id="e94d3-171">description</span><span class="sxs-lookup"><span data-stu-id="e94d3-171">description</span></span> | <span data-ttu-id="e94d3-172">Cadena</span><span class="sxs-lookup"><span data-stu-id="e94d3-172">String</span></span> | <span data-ttu-id="e94d3-173">Descripción del indicador.</span><span class="sxs-lookup"><span data-stu-id="e94d3-173">Description of the indicator.</span></span> <span data-ttu-id="e94d3-174">**Required**</span><span class="sxs-lookup"><span data-stu-id="e94d3-174">**Required**</span></span>
<span data-ttu-id="e94d3-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="e94d3-175">expirationTime</span></span> | <span data-ttu-id="e94d3-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e94d3-176">DateTimeOffset</span></span> | <span data-ttu-id="e94d3-177">La hora de expiración del indicador.</span><span class="sxs-lookup"><span data-stu-id="e94d3-177">The expiration time of the indicator.</span></span> <span data-ttu-id="e94d3-178">**Optional**</span><span class="sxs-lookup"><span data-stu-id="e94d3-178">**Optional**</span></span>
<span data-ttu-id="e94d3-179">severity</span><span class="sxs-lookup"><span data-stu-id="e94d3-179">severity</span></span> | <span data-ttu-id="e94d3-180">Enum</span><span class="sxs-lookup"><span data-stu-id="e94d3-180">Enum</span></span> | <span data-ttu-id="e94d3-181">Gravedad del indicador.</span><span class="sxs-lookup"><span data-stu-id="e94d3-181">The severity of the indicator.</span></span> <span data-ttu-id="e94d3-182">los valores posibles son: "Informational", "Low", "Medium" y "High".</span><span class="sxs-lookup"><span data-stu-id="e94d3-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="e94d3-183">**Optional**</span><span class="sxs-lookup"><span data-stu-id="e94d3-183">**Optional**</span></span>
<span data-ttu-id="e94d3-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="e94d3-184">recommendedActions</span></span> | <span data-ttu-id="e94d3-185">Cadena</span><span class="sxs-lookup"><span data-stu-id="e94d3-185">String</span></span> | <span data-ttu-id="e94d3-186">Acciones recomendadas de alerta del indicador TI.</span><span class="sxs-lookup"><span data-stu-id="e94d3-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="e94d3-187">**Optional**</span><span class="sxs-lookup"><span data-stu-id="e94d3-187">**Optional**</span></span>
<span data-ttu-id="e94d3-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="e94d3-188">rbacGroupNames</span></span> | <span data-ttu-id="e94d3-189">Cadena</span><span class="sxs-lookup"><span data-stu-id="e94d3-189">String</span></span> | <span data-ttu-id="e94d3-190">Lista separada por comas de nombres de grupo RBAC a los que se aplicaría el indicador.</span><span class="sxs-lookup"><span data-stu-id="e94d3-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="e94d3-191">**Optional**</span><span class="sxs-lookup"><span data-stu-id="e94d3-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="e94d3-192">Respuesta</span><span class="sxs-lookup"><span data-stu-id="e94d3-192">Response</span></span>
- <span data-ttu-id="e94d3-193">Si se realiza correctamente, este método devuelve 200: código de respuesta aceptar y la entidad [Indicator](ti-indicator.md) creada o actualizada en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e94d3-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="e94d3-194">Si no se realiza correctamente: este método devuelve 400 - Solicitud mala.</span><span class="sxs-lookup"><span data-stu-id="e94d3-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="e94d3-195">La solicitud incorrecta suele indicar un cuerpo incorrecto.</span><span class="sxs-lookup"><span data-stu-id="e94d3-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="e94d3-196">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e94d3-196">Example</span></span>

<span data-ttu-id="e94d3-197">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="e94d3-197">**Request**</span></span>

<span data-ttu-id="e94d3-198">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e94d3-198">Here is an example of the request.</span></span>

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

## <a name="related-topic"></a><span data-ttu-id="e94d3-199">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="e94d3-199">Related topic</span></span>
- [<span data-ttu-id="e94d3-200">Administrar indicadores</span><span class="sxs-lookup"><span data-stu-id="e94d3-200">Manage indicators</span></span>](manage-indicators.md)
