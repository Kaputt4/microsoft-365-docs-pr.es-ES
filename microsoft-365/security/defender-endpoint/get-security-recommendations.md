---
title: Obtener recomendaciones de seguridad
description: Recupera una colección de recomendaciones de seguridad relacionadas con un identificador de dispositivo determinado.
keywords: apis, api de gráficos, api compatibles, get, list, file, information, security recommendation per device, threat & vulnerability management api, Api de Microsoft Defender para Endpoint tvm
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
ms.openlocfilehash: bc209687d51b3e05bfcfd6028042ba5912b877f6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935310"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="26bf4-104">Obtener recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="26bf4-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="26bf4-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="26bf4-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="26bf4-106">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="26bf4-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="26bf4-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="26bf4-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="26bf4-108">Recupera una colección de recomendaciones de seguridad relacionadas con un identificador de dispositivo determinado.</span><span class="sxs-lookup"><span data-stu-id="26bf4-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="26bf4-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="26bf4-109">Permissions</span></span>
<span data-ttu-id="26bf4-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="26bf4-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="26bf4-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="26bf4-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="26bf4-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="26bf4-112">Permission type</span></span> |   <span data-ttu-id="26bf4-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="26bf4-113">Permission</span></span>  |   <span data-ttu-id="26bf4-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="26bf4-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="26bf4-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="26bf4-115">Application</span></span> | <span data-ttu-id="26bf4-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="26bf4-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="26bf4-117">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="26bf4-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="26bf4-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="26bf4-118">Delegated (work or school account)</span></span> | <span data-ttu-id="26bf4-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="26bf4-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="26bf4-120">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="26bf4-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="26bf4-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="26bf4-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="26bf4-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="26bf4-122">Request headers</span></span>

<span data-ttu-id="26bf4-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="26bf4-123">Name</span></span> | <span data-ttu-id="26bf4-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="26bf4-124">Type</span></span> | <span data-ttu-id="26bf4-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="26bf4-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="26bf4-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="26bf4-126">Authorization</span></span> | <span data-ttu-id="26bf4-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="26bf4-127">String</span></span> | <span data-ttu-id="26bf4-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="26bf4-128">Bearer {token}.</span></span> <span data-ttu-id="26bf4-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="26bf4-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="26bf4-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="26bf4-130">Request body</span></span>
<span data-ttu-id="26bf4-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="26bf4-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="26bf4-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="26bf4-132">Response</span></span>
<span data-ttu-id="26bf4-133">Si se realiza correctamente, este método devuelve 200 Aceptar con las recomendaciones de seguridad del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="26bf4-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="26bf4-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26bf4-134">Example</span></span>

<span data-ttu-id="26bf4-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="26bf4-135">**Request**</span></span>

<span data-ttu-id="26bf4-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="26bf4-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="26bf4-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="26bf4-137">**Response**</span></span>

<span data-ttu-id="26bf4-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="26bf4-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="26bf4-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="26bf4-139">Related topics</span></span>
- [<span data-ttu-id="26bf4-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="26bf4-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="26bf4-141">Recomendación & seguridad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="26bf4-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
