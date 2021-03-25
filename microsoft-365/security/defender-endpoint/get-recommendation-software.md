---
title: Obtener recomendaciones por software
description: Recupera una recomendación de seguridad relacionada con un software específico.
keywords: apis, api de gráficos, api admitidas, get, recomendación de seguridad, recomendación de seguridad para software, administración de amenazas y vulnerabilidades, api de administración de amenazas y vulnerabilidades
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
ms.openlocfilehash: 82479b0248ceee95321d269e3f48a4eeea3ad193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199506"
---
# <a name="get-recommendation-by-software"></a><span data-ttu-id="34c73-104">Obtener recomendaciones por software</span><span class="sxs-lookup"><span data-stu-id="34c73-104">Get recommendation by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="34c73-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="34c73-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="34c73-106">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="34c73-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="34c73-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="34c73-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="34c73-108">Recupera una recomendación de seguridad relacionada con un software específico.</span><span class="sxs-lookup"><span data-stu-id="34c73-108">Retrieves a security recommendation related to a specific software.</span></span>

## <a name="permissions"></a><span data-ttu-id="34c73-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="34c73-109">Permissions</span></span>
<span data-ttu-id="34c73-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="34c73-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="34c73-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34c73-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="34c73-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="34c73-112">Permission type</span></span> |   <span data-ttu-id="34c73-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="34c73-113">Permission</span></span>  |   <span data-ttu-id="34c73-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="34c73-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="34c73-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="34c73-115">Application</span></span> |   <span data-ttu-id="34c73-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="34c73-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="34c73-117">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="34c73-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="34c73-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="34c73-118">Delegated (work or school account)</span></span> | <span data-ttu-id="34c73-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="34c73-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="34c73-120">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="34c73-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="34c73-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="34c73-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a><span data-ttu-id="34c73-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="34c73-122">Request headers</span></span>

<span data-ttu-id="34c73-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="34c73-123">Name</span></span> | <span data-ttu-id="34c73-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="34c73-124">Type</span></span> | <span data-ttu-id="34c73-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="34c73-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="34c73-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="34c73-126">Authorization</span></span> | <span data-ttu-id="34c73-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="34c73-127">String</span></span> | <span data-ttu-id="34c73-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="34c73-128">Bearer {token}.</span></span> <span data-ttu-id="34c73-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="34c73-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="34c73-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="34c73-130">Request body</span></span>
<span data-ttu-id="34c73-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="34c73-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="34c73-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="34c73-132">Response</span></span>
<span data-ttu-id="34c73-133">Si se realiza correctamente, este método devuelve 200 Ok con el software asociado con las recomendaciones de seguridad en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="34c73-133">If successful, this method returns 200 OK with the software associated with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="34c73-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34c73-134">Example</span></span>

<span data-ttu-id="34c73-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="34c73-135">**Request**</span></span>

<span data-ttu-id="34c73-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="34c73-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

<span data-ttu-id="34c73-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="34c73-137">**Response**</span></span>

<span data-ttu-id="34c73-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="34c73-138">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="34c73-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="34c73-139">Related topics</span></span>
- [<span data-ttu-id="34c73-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="34c73-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="34c73-141">Recomendación & seguridad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="34c73-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
