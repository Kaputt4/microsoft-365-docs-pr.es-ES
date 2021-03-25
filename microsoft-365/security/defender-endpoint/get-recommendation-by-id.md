---
title: Obtener recomendación por id.
description: Recupera una recomendación de seguridad por su identificador.
keywords: apis, api de gráficos, api admitidas, get, recomendación de seguridad, recomendación de seguridad por identificador, administración de amenazas y vulnerabilidades, api de administración de amenazas y vulnerabilidades
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
ms.openlocfilehash: 45a151fc5855a4a2b1ba63a50b54737c90e6bdd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199518"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="ffd25-104">Obtener recomendación por identificador</span><span class="sxs-lookup"><span data-stu-id="ffd25-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ffd25-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ffd25-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ffd25-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="ffd25-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ffd25-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ffd25-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ffd25-108">Recupera una recomendación de seguridad por su identificador.</span><span class="sxs-lookup"><span data-stu-id="ffd25-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="ffd25-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="ffd25-109">Permissions</span></span>
<span data-ttu-id="ffd25-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="ffd25-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ffd25-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ffd25-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="ffd25-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="ffd25-112">Permission type</span></span> |   <span data-ttu-id="ffd25-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="ffd25-113">Permission</span></span>  |   <span data-ttu-id="ffd25-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="ffd25-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ffd25-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="ffd25-115">Application</span></span> |   <span data-ttu-id="ffd25-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="ffd25-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="ffd25-117">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="ffd25-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="ffd25-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="ffd25-118">Delegated (work or school account)</span></span> | <span data-ttu-id="ffd25-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="ffd25-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="ffd25-120">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="ffd25-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="ffd25-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="ffd25-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="ffd25-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="ffd25-122">Request headers</span></span>

<span data-ttu-id="ffd25-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="ffd25-123">Name</span></span> | <span data-ttu-id="ffd25-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="ffd25-124">Type</span></span> | <span data-ttu-id="ffd25-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffd25-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="ffd25-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="ffd25-126">Authorization</span></span> | <span data-ttu-id="ffd25-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="ffd25-127">String</span></span> | <span data-ttu-id="ffd25-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="ffd25-128">Bearer {token}.</span></span> <span data-ttu-id="ffd25-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="ffd25-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ffd25-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="ffd25-130">Request body</span></span>
<span data-ttu-id="ffd25-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="ffd25-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ffd25-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="ffd25-132">Response</span></span>
<span data-ttu-id="ffd25-133">Si se realiza correctamente, este método devuelve 200 Aceptar con las recomendaciones de seguridad del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="ffd25-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="ffd25-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ffd25-134">Example</span></span>

<span data-ttu-id="ffd25-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="ffd25-135">**Request**</span></span>

<span data-ttu-id="ffd25-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ffd25-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="ffd25-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="ffd25-137">**Response**</span></span>

<span data-ttu-id="ffd25-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="ffd25-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="ffd25-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ffd25-139">Related topics</span></span>
- [<span data-ttu-id="ffd25-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="ffd25-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="ffd25-141">Recomendación & seguridad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="ffd25-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
