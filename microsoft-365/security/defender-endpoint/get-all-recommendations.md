---
title: Enumerar todas las recomendaciones
description: Recupera una lista de todas las recomendaciones de seguridad que afectan a la organización.
keywords: apis, graph api, apis compatibles, get, security recommendations, Microsoft Defender for Endpoint tvm api, Administración de amenazas y vulnerabilidades, Administración de amenazas y vulnerabilidades api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: eb009a01e36739ab5e9ec009d053a7bd4e177907
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841539"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="8b700-104">Enumerar todas las recomendaciones</span><span class="sxs-lookup"><span data-stu-id="8b700-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8b700-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8b700-105">**Applies to:**</span></span>
- [<span data-ttu-id="8b700-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="8b700-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8b700-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b700-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="8b700-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="8b700-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8b700-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="8b700-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8b700-110">Recupera una lista de todas las recomendaciones de seguridad que afectan a la organización.</span><span class="sxs-lookup"><span data-stu-id="8b700-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="8b700-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="8b700-111">Permissions</span></span>
<span data-ttu-id="8b700-112">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="8b700-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8b700-113">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8b700-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="8b700-114">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="8b700-114">Permission type</span></span> |   <span data-ttu-id="8b700-115">Permiso</span><span class="sxs-lookup"><span data-stu-id="8b700-115">Permission</span></span>  |   <span data-ttu-id="8b700-116">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="8b700-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8b700-117">Aplicación</span><span class="sxs-lookup"><span data-stu-id="8b700-117">Application</span></span> |   <span data-ttu-id="8b700-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="8b700-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="8b700-119">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="8b700-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="8b700-120">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="8b700-120">Delegated (work or school account)</span></span> | <span data-ttu-id="8b700-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="8b700-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="8b700-122">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="8b700-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="8b700-123">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="8b700-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="8b700-124">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="8b700-124">Request headers</span></span>

<span data-ttu-id="8b700-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b700-125">Name</span></span> | <span data-ttu-id="8b700-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="8b700-126">Type</span></span> | <span data-ttu-id="8b700-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b700-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="8b700-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="8b700-128">Authorization</span></span> | <span data-ttu-id="8b700-129">Cadena</span><span class="sxs-lookup"><span data-stu-id="8b700-129">String</span></span> | <span data-ttu-id="8b700-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="8b700-130">Bearer {token}.</span></span> <span data-ttu-id="8b700-131">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="8b700-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8b700-132">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="8b700-132">Request body</span></span>
<span data-ttu-id="8b700-133">En blanco</span><span class="sxs-lookup"><span data-stu-id="8b700-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8b700-134">Respuesta</span><span class="sxs-lookup"><span data-stu-id="8b700-134">Response</span></span>
<span data-ttu-id="8b700-135">Si se realiza correctamente, este método devuelve 200 Aceptar con la lista de recomendaciones de seguridad en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8b700-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="8b700-136">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8b700-136">Example</span></span>

<span data-ttu-id="8b700-137">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="8b700-137">**Request**</span></span>

<span data-ttu-id="8b700-138">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="8b700-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="8b700-139">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="8b700-139">**Response**</span></span>

<span data-ttu-id="8b700-140">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="8b700-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="8b700-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b700-141">See also</span></span>
- [<span data-ttu-id="8b700-142">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="8b700-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="8b700-143">Recomendación & seguridad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="8b700-143">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

