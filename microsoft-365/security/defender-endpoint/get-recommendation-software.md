---
title: Obtener recomendación por software
description: Recupera una recomendación de seguridad relacionada con un software específico.
keywords: apis, api de gráficos, api admitidas, get, recomendación de seguridad, recomendación de seguridad para software, Administración de amenazas y vulnerabilidades, Administración de amenazas y vulnerabilidades api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9227987544e1cee1eeb4b65b5ae6bbf719558dd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845215"
---
# <a name="get-recommendation-by-software"></a><span data-ttu-id="39ef3-104">Obtener recomendación por software</span><span class="sxs-lookup"><span data-stu-id="39ef3-104">Get recommendation by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="39ef3-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="39ef3-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="39ef3-106">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="39ef3-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="39ef3-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="39ef3-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="39ef3-108">Recupera una recomendación de seguridad relacionada con un software específico.</span><span class="sxs-lookup"><span data-stu-id="39ef3-108">Retrieves a security recommendation related to a specific software.</span></span>

## <a name="permissions"></a><span data-ttu-id="39ef3-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="39ef3-109">Permissions</span></span>
<span data-ttu-id="39ef3-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="39ef3-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="39ef3-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="39ef3-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="39ef3-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="39ef3-112">Permission type</span></span> |   <span data-ttu-id="39ef3-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="39ef3-113">Permission</span></span>  |   <span data-ttu-id="39ef3-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="39ef3-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="39ef3-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="39ef3-115">Application</span></span> |   <span data-ttu-id="39ef3-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="39ef3-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="39ef3-117">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="39ef3-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="39ef3-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="39ef3-118">Delegated (work or school account)</span></span> | <span data-ttu-id="39ef3-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="39ef3-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="39ef3-120">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="39ef3-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="39ef3-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="39ef3-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a><span data-ttu-id="39ef3-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="39ef3-122">Request headers</span></span>

<span data-ttu-id="39ef3-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="39ef3-123">Name</span></span> | <span data-ttu-id="39ef3-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="39ef3-124">Type</span></span> | <span data-ttu-id="39ef3-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="39ef3-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="39ef3-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="39ef3-126">Authorization</span></span> | <span data-ttu-id="39ef3-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="39ef3-127">String</span></span> | <span data-ttu-id="39ef3-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="39ef3-128">Bearer {token}.</span></span> <span data-ttu-id="39ef3-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="39ef3-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="39ef3-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="39ef3-130">Request body</span></span>
<span data-ttu-id="39ef3-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="39ef3-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="39ef3-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="39ef3-132">Response</span></span>
<span data-ttu-id="39ef3-133">Si se realiza correctamente, este método devuelve 200 Ok con el software asociado con las recomendaciones de seguridad en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="39ef3-133">If successful, this method returns 200 OK with the software associated with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="39ef3-134">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39ef3-134">Example</span></span>

<span data-ttu-id="39ef3-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="39ef3-135">**Request**</span></span>

<span data-ttu-id="39ef3-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="39ef3-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

<span data-ttu-id="39ef3-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="39ef3-137">**Response**</span></span>

<span data-ttu-id="39ef3-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="39ef3-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a><span data-ttu-id="39ef3-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="39ef3-139">Related topics</span></span>
- [<span data-ttu-id="39ef3-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="39ef3-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="39ef3-141">Recomendación & seguridad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="39ef3-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
