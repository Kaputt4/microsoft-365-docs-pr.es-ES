---
title: Tipo de recurso Indicator
description: Especifique los detalles de la entidad y defina la expiración del indicador mediante Microsoft Defender para endpoint.
keywords: apis, api admitidas, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187314"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="d5e81-104">Tipo de recurso Indicator</span><span class="sxs-lookup"><span data-stu-id="d5e81-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d5e81-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d5e81-105">**Applies to:**</span></span>
- [<span data-ttu-id="d5e81-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d5e81-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d5e81-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5e81-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d5e81-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="d5e81-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d5e81-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d5e81-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="d5e81-110">Vea la página [Indicadores correspondiente](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) en el portal.</span><span class="sxs-lookup"><span data-stu-id="d5e81-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="d5e81-111">Método</span><span class="sxs-lookup"><span data-stu-id="d5e81-111">Method</span></span>|<span data-ttu-id="d5e81-112">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d5e81-112">Return Type</span></span> |<span data-ttu-id="d5e81-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5e81-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="d5e81-114">Enumerar indicadores</span><span class="sxs-lookup"><span data-stu-id="d5e81-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="d5e81-115">[Indicador](ti-indicator.md) Colección</span><span class="sxs-lookup"><span data-stu-id="d5e81-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="d5e81-116">Enumerar [entidades de](ti-indicator.md) indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="d5e81-117">Indicador Enviar</span><span class="sxs-lookup"><span data-stu-id="d5e81-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="d5e81-118">Indicador</span><span class="sxs-lookup"><span data-stu-id="d5e81-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="d5e81-119">Enviar o actualizar entidad [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="d5e81-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="d5e81-120">Importar indicadores</span><span class="sxs-lookup"><span data-stu-id="d5e81-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="d5e81-121">[Indicador](ti-indicator.md) Colección</span><span class="sxs-lookup"><span data-stu-id="d5e81-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="d5e81-122">Enviar o actualizar [entidades de](ti-indicator.md) indicadores.</span><span class="sxs-lookup"><span data-stu-id="d5e81-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="d5e81-123">Eliminar indicador</span><span class="sxs-lookup"><span data-stu-id="d5e81-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="d5e81-124">Sin contenido</span><span class="sxs-lookup"><span data-stu-id="d5e81-124">No Content</span></span> | <span data-ttu-id="d5e81-125">Elimina la [entidad Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="d5e81-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="d5e81-126">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d5e81-126">Properties</span></span>
<span data-ttu-id="d5e81-127">Propiedad</span><span class="sxs-lookup"><span data-stu-id="d5e81-127">Property</span></span> |  <span data-ttu-id="d5e81-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="d5e81-128">Type</span></span>    |   <span data-ttu-id="d5e81-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5e81-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="d5e81-130">id</span><span class="sxs-lookup"><span data-stu-id="d5e81-130">id</span></span> | <span data-ttu-id="d5e81-131">Cadena</span><span class="sxs-lookup"><span data-stu-id="d5e81-131">String</span></span> | <span data-ttu-id="d5e81-132">Identidad de la [entidad Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="d5e81-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="d5e81-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="d5e81-133">indicatorValue</span></span> | <span data-ttu-id="d5e81-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="d5e81-134">String</span></span> | <span data-ttu-id="d5e81-135">El valor del [indicador](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="d5e81-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="d5e81-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="d5e81-136">indicatorType</span></span> | <span data-ttu-id="d5e81-137">Enum</span><span class="sxs-lookup"><span data-stu-id="d5e81-137">Enum</span></span> | <span data-ttu-id="d5e81-138">Tipo del indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-138">Type of the indicator.</span></span> <span data-ttu-id="d5e81-139">Los valores posibles son: "FileSha1", "FileSha256", "IpAddress", "DomainName" y "Url".</span><span class="sxs-lookup"><span data-stu-id="d5e81-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="d5e81-140">aplicación</span><span class="sxs-lookup"><span data-stu-id="d5e81-140">application</span></span> | <span data-ttu-id="d5e81-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="d5e81-141">String</span></span> | <span data-ttu-id="d5e81-142">La aplicación asociada al indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="d5e81-143">acción</span><span class="sxs-lookup"><span data-stu-id="d5e81-143">action</span></span> | <span data-ttu-id="d5e81-144">Enum</span><span class="sxs-lookup"><span data-stu-id="d5e81-144">Enum</span></span> | <span data-ttu-id="d5e81-145">La acción que se realizará si el indicador se detectará en la organización.</span><span class="sxs-lookup"><span data-stu-id="d5e81-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="d5e81-146">Los valores posibles son: "Alert", "AlertAndBlock" y "Allowed".</span><span class="sxs-lookup"><span data-stu-id="d5e81-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="d5e81-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="d5e81-147">sourceType</span></span> | <span data-ttu-id="d5e81-148">Enum</span><span class="sxs-lookup"><span data-stu-id="d5e81-148">Enum</span></span> | <span data-ttu-id="d5e81-149">"Usuario" en caso de que el indicador creado por un usuario (por ejemplo, desde el portal), "AadApp" en caso de que se haya enviado mediante una aplicación automatizada a través de la API.</span><span class="sxs-lookup"><span data-stu-id="d5e81-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="d5e81-150">source</span><span class="sxs-lookup"><span data-stu-id="d5e81-150">source</span></span> | <span data-ttu-id="d5e81-151">string</span><span class="sxs-lookup"><span data-stu-id="d5e81-151">string</span></span> | <span data-ttu-id="d5e81-152">Nombre del usuario o aplicación que envió el indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="d5e81-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="d5e81-153">createdBy</span></span> | <span data-ttu-id="d5e81-154">String</span><span class="sxs-lookup"><span data-stu-id="d5e81-154">String</span></span> | <span data-ttu-id="d5e81-155">Identidad única del usuario/aplicación que envió el indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="d5e81-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="d5e81-156">lastUpdatedBy</span></span> | <span data-ttu-id="d5e81-157">Cadena</span><span class="sxs-lookup"><span data-stu-id="d5e81-157">String</span></span> | <span data-ttu-id="d5e81-158">Identidad del usuario/aplicación que actualizó por última vez el indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="d5e81-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="d5e81-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="d5e81-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d5e81-160">DateTimeOffset</span></span> | <span data-ttu-id="d5e81-161">La fecha y hora en que se creó el indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="d5e81-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="d5e81-162">expirationTime</span></span> | <span data-ttu-id="d5e81-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d5e81-163">DateTimeOffset</span></span> | <span data-ttu-id="d5e81-164">La hora de expiración del indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="d5e81-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="d5e81-165">lastUpdateTime</span></span> | <span data-ttu-id="d5e81-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d5e81-166">DateTimeOffset</span></span> | <span data-ttu-id="d5e81-167">La última vez que se actualizó el indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="d5e81-168">severity</span><span class="sxs-lookup"><span data-stu-id="d5e81-168">severity</span></span> | <span data-ttu-id="d5e81-169">Enum</span><span class="sxs-lookup"><span data-stu-id="d5e81-169">Enum</span></span> | <span data-ttu-id="d5e81-170">Gravedad del indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-170">The severity of the indicator.</span></span> <span data-ttu-id="d5e81-171">los valores posibles son: "Informational", "Low", "Medium" y "High".</span><span class="sxs-lookup"><span data-stu-id="d5e81-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="d5e81-172">title</span><span class="sxs-lookup"><span data-stu-id="d5e81-172">title</span></span> | <span data-ttu-id="d5e81-173">Cadena</span><span class="sxs-lookup"><span data-stu-id="d5e81-173">String</span></span> | <span data-ttu-id="d5e81-174">Título del indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-174">Indicator title.</span></span>
<span data-ttu-id="d5e81-175">descripción</span><span class="sxs-lookup"><span data-stu-id="d5e81-175">description</span></span> | <span data-ttu-id="d5e81-176">Cadena</span><span class="sxs-lookup"><span data-stu-id="d5e81-176">String</span></span> | <span data-ttu-id="d5e81-177">Descripción del indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-177">Description of the indicator.</span></span>
<span data-ttu-id="d5e81-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="d5e81-178">recommendedActions</span></span> | <span data-ttu-id="d5e81-179">Cadena</span><span class="sxs-lookup"><span data-stu-id="d5e81-179">String</span></span> | <span data-ttu-id="d5e81-180">Acciones recomendadas para el indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="d5e81-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="d5e81-181">rbacGroupNames</span></span> | <span data-ttu-id="d5e81-182">Lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="d5e81-182">List of strings</span></span> | <span data-ttu-id="d5e81-183">Nombres de grupo de dispositivo RBAC donde se expone y activa el indicador.</span><span class="sxs-lookup"><span data-stu-id="d5e81-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="d5e81-184">Lista vacía en caso de que se exponga a todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d5e81-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="d5e81-185">Representación json</span><span class="sxs-lookup"><span data-stu-id="d5e81-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
