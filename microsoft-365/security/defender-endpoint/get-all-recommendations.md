---
title: Enumerar todas las recomendaciones
description: Recupera una lista de todas las recomendaciones de seguridad que afectan a la organización.
keywords: apis, api de gráficos, api admitidas, get, recomendaciones de seguridad, api de Microsoft Defender para Endpoint tvm, administración de amenazas y vulnerabilidades, api de administración de amenazas y vulnerabilidades
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
ms.technology: mde
ms.openlocfilehash: 0cb0a1f8a42b419db960e5097667c335bf7f7877
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935022"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="6c602-104">Enumerar todas las recomendaciones</span><span class="sxs-lookup"><span data-stu-id="6c602-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6c602-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6c602-105">**Applies to:**</span></span>
- [<span data-ttu-id="6c602-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6c602-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6c602-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c602-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="6c602-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="6c602-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6c602-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6c602-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6c602-110">Recupera una lista de todas las recomendaciones de seguridad que afectan a la organización.</span><span class="sxs-lookup"><span data-stu-id="6c602-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="6c602-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="6c602-111">Permissions</span></span>
<span data-ttu-id="6c602-112">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="6c602-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6c602-113">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6c602-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="6c602-114">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="6c602-114">Permission type</span></span> |   <span data-ttu-id="6c602-115">Permiso</span><span class="sxs-lookup"><span data-stu-id="6c602-115">Permission</span></span>  |   <span data-ttu-id="6c602-116">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="6c602-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6c602-117">Aplicación</span><span class="sxs-lookup"><span data-stu-id="6c602-117">Application</span></span> |   <span data-ttu-id="6c602-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="6c602-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="6c602-119">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="6c602-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="6c602-120">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="6c602-120">Delegated (work or school account)</span></span> | <span data-ttu-id="6c602-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="6c602-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="6c602-122">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="6c602-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="6c602-123">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="6c602-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="6c602-124">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="6c602-124">Request headers</span></span>

<span data-ttu-id="6c602-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="6c602-125">Name</span></span> | <span data-ttu-id="6c602-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="6c602-126">Type</span></span> | <span data-ttu-id="6c602-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c602-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="6c602-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="6c602-128">Authorization</span></span> | <span data-ttu-id="6c602-129">Cadena</span><span class="sxs-lookup"><span data-stu-id="6c602-129">String</span></span> | <span data-ttu-id="6c602-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="6c602-130">Bearer {token}.</span></span> <span data-ttu-id="6c602-131">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="6c602-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6c602-132">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="6c602-132">Request body</span></span>
<span data-ttu-id="6c602-133">En blanco</span><span class="sxs-lookup"><span data-stu-id="6c602-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6c602-134">Respuesta</span><span class="sxs-lookup"><span data-stu-id="6c602-134">Response</span></span>
<span data-ttu-id="6c602-135">Si se realiza correctamente, este método devuelve 200 Aceptar con la lista de recomendaciones de seguridad en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="6c602-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="6c602-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c602-136">Example</span></span>

<span data-ttu-id="6c602-137">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="6c602-137">**Request**</span></span>

<span data-ttu-id="6c602-138">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6c602-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="6c602-139">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="6c602-139">**Response**</span></span>

<span data-ttu-id="6c602-140">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="6c602-140">Here is an example of the response.</span></span>


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
## <a name="see-also"></a><span data-ttu-id="6c602-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c602-141">See also</span></span>
- [<span data-ttu-id="6c602-142">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="6c602-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="6c602-143">Recomendación & seguridad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="6c602-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

