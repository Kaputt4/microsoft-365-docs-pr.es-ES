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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771386"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="71583-104">Tipo de recurso Indicator</span><span class="sxs-lookup"><span data-stu-id="71583-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71583-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="71583-105">**Applies to:**</span></span>
- [<span data-ttu-id="71583-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="71583-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71583-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71583-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="71583-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="71583-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="71583-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="71583-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="71583-110">Vea la página [Indicadores correspondiente](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) en el portal.</span><span class="sxs-lookup"><span data-stu-id="71583-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="71583-111">Método</span><span class="sxs-lookup"><span data-stu-id="71583-111">Method</span></span>|<span data-ttu-id="71583-112">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="71583-112">Return Type</span></span> |<span data-ttu-id="71583-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="71583-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="71583-114">Mostrar indicadores</span><span class="sxs-lookup"><span data-stu-id="71583-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="71583-115">[Indicador](ti-indicator.md) Colección</span><span class="sxs-lookup"><span data-stu-id="71583-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="71583-116">Enumerar [entidades de](ti-indicator.md) indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="71583-117">Enviar indicador</span><span class="sxs-lookup"><span data-stu-id="71583-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="71583-118">Indicador</span><span class="sxs-lookup"><span data-stu-id="71583-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="71583-119">Enviar o actualizar entidad [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="71583-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="71583-120">Indicadores de importación</span><span class="sxs-lookup"><span data-stu-id="71583-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="71583-121">[Indicador](ti-indicator.md) Colección</span><span class="sxs-lookup"><span data-stu-id="71583-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="71583-122">Enviar o actualizar [entidades de](ti-indicator.md) indicadores.</span><span class="sxs-lookup"><span data-stu-id="71583-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="71583-123">Eliminar indicador</span><span class="sxs-lookup"><span data-stu-id="71583-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="71583-124">Sin contenido</span><span class="sxs-lookup"><span data-stu-id="71583-124">No Content</span></span> | <span data-ttu-id="71583-125">Elimina la [entidad Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="71583-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="71583-126">Propiedades</span><span class="sxs-lookup"><span data-stu-id="71583-126">Properties</span></span>
<span data-ttu-id="71583-127">Propiedad</span><span class="sxs-lookup"><span data-stu-id="71583-127">Property</span></span> |  <span data-ttu-id="71583-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="71583-128">Type</span></span>    |   <span data-ttu-id="71583-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="71583-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="71583-130">id</span><span class="sxs-lookup"><span data-stu-id="71583-130">id</span></span> | <span data-ttu-id="71583-131">Cadena</span><span class="sxs-lookup"><span data-stu-id="71583-131">String</span></span> | <span data-ttu-id="71583-132">Identidad de la [entidad Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="71583-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="71583-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="71583-133">indicatorValue</span></span> | <span data-ttu-id="71583-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="71583-134">String</span></span> | <span data-ttu-id="71583-135">El valor del [indicador](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="71583-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="71583-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="71583-136">indicatorType</span></span> | <span data-ttu-id="71583-137">Enum</span><span class="sxs-lookup"><span data-stu-id="71583-137">Enum</span></span> | <span data-ttu-id="71583-138">Tipo del indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-138">Type of the indicator.</span></span> <span data-ttu-id="71583-139">Los valores posibles son: "FileSha1", "FileSha256", "IpAddress", "DomainName" y "Url".</span><span class="sxs-lookup"><span data-stu-id="71583-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="71583-140">aplicación</span><span class="sxs-lookup"><span data-stu-id="71583-140">application</span></span> | <span data-ttu-id="71583-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="71583-141">String</span></span> | <span data-ttu-id="71583-142">La aplicación asociada al indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="71583-143">acción</span><span class="sxs-lookup"><span data-stu-id="71583-143">action</span></span> | <span data-ttu-id="71583-144">Enum</span><span class="sxs-lookup"><span data-stu-id="71583-144">Enum</span></span> | <span data-ttu-id="71583-145">La acción que se realizará si el indicador se detectará en la organización.</span><span class="sxs-lookup"><span data-stu-id="71583-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="71583-146">Los valores posibles son: "Alert", "AlertAndBlock" y "Allowed".</span><span class="sxs-lookup"><span data-stu-id="71583-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="71583-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="71583-147">sourceType</span></span> | <span data-ttu-id="71583-148">Enum</span><span class="sxs-lookup"><span data-stu-id="71583-148">Enum</span></span> | <span data-ttu-id="71583-149">"Usuario" en caso de que el indicador creado por un usuario (por ejemplo, desde el portal), "AadApp" en caso de que se haya enviado mediante una aplicación automatizada a través de la API.</span><span class="sxs-lookup"><span data-stu-id="71583-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="71583-150">source</span><span class="sxs-lookup"><span data-stu-id="71583-150">source</span></span> | <span data-ttu-id="71583-151">cadena</span><span class="sxs-lookup"><span data-stu-id="71583-151">string</span></span> | <span data-ttu-id="71583-152">Nombre del usuario o aplicación que envió el indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="71583-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="71583-153">createdBy</span></span> | <span data-ttu-id="71583-154">String</span><span class="sxs-lookup"><span data-stu-id="71583-154">String</span></span> | <span data-ttu-id="71583-155">Identidad única del usuario/aplicación que envió el indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="71583-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="71583-156">lastUpdatedBy</span></span> | <span data-ttu-id="71583-157">Cadena</span><span class="sxs-lookup"><span data-stu-id="71583-157">String</span></span> | <span data-ttu-id="71583-158">Identidad del usuario/aplicación que actualizó por última vez el indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="71583-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="71583-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="71583-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="71583-160">DateTimeOffset</span></span> | <span data-ttu-id="71583-161">La fecha y hora en que se creó el indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="71583-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="71583-162">expirationTime</span></span> | <span data-ttu-id="71583-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="71583-163">DateTimeOffset</span></span> | <span data-ttu-id="71583-164">La hora de expiración del indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="71583-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="71583-165">lastUpdateTime</span></span> | <span data-ttu-id="71583-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="71583-166">DateTimeOffset</span></span> | <span data-ttu-id="71583-167">La última vez que se actualizó el indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="71583-168">severity</span><span class="sxs-lookup"><span data-stu-id="71583-168">severity</span></span> | <span data-ttu-id="71583-169">Enum</span><span class="sxs-lookup"><span data-stu-id="71583-169">Enum</span></span> | <span data-ttu-id="71583-170">Gravedad del indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-170">The severity of the indicator.</span></span> <span data-ttu-id="71583-171">los valores posibles son: "Informational", "Low", "Medium" y "High".</span><span class="sxs-lookup"><span data-stu-id="71583-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="71583-172">title</span><span class="sxs-lookup"><span data-stu-id="71583-172">title</span></span> | <span data-ttu-id="71583-173">Cadena</span><span class="sxs-lookup"><span data-stu-id="71583-173">String</span></span> | <span data-ttu-id="71583-174">Título del indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-174">Indicator title.</span></span>
<span data-ttu-id="71583-175">description</span><span class="sxs-lookup"><span data-stu-id="71583-175">description</span></span> | <span data-ttu-id="71583-176">Cadena</span><span class="sxs-lookup"><span data-stu-id="71583-176">String</span></span> | <span data-ttu-id="71583-177">Descripción del indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-177">Description of the indicator.</span></span>
<span data-ttu-id="71583-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="71583-178">recommendedActions</span></span> | <span data-ttu-id="71583-179">Cadena</span><span class="sxs-lookup"><span data-stu-id="71583-179">String</span></span> | <span data-ttu-id="71583-180">Acciones recomendadas para el indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="71583-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="71583-181">rbacGroupNames</span></span> | <span data-ttu-id="71583-182">Lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="71583-182">List of strings</span></span> | <span data-ttu-id="71583-183">Nombres de grupo de dispositivo RBAC donde se expone y activa el indicador.</span><span class="sxs-lookup"><span data-stu-id="71583-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="71583-184">Lista vacía en caso de que se exponga a todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="71583-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="71583-185">Representación json</span><span class="sxs-lookup"><span data-stu-id="71583-185">Json representation</span></span>

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
