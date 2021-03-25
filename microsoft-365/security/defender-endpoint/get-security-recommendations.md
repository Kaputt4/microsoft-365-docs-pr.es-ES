---
title: Obtener recomendaciones de seguridad
description: Recupera una colección de recomendaciones de seguridad relacionadas con un identificador de dispositivo determinado.
keywords: apis, api de gráficos, api compatibles, get, list, file, information, security recommendation per device, threat & vulnerability management api, mdatp tvm api
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
ms.openlocfilehash: 6c65926985c7c8a194ab87c44c3fc269488c463c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199776"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="b0593-104">Obtener recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="b0593-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0593-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b0593-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="b0593-106">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b0593-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b0593-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b0593-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b0593-108">Recupera una colección de recomendaciones de seguridad relacionadas con un identificador de dispositivo determinado.</span><span class="sxs-lookup"><span data-stu-id="b0593-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="b0593-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="b0593-109">Permissions</span></span>
<span data-ttu-id="b0593-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="b0593-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b0593-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b0593-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b0593-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="b0593-112">Permission type</span></span> |   <span data-ttu-id="b0593-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="b0593-113">Permission</span></span>  |   <span data-ttu-id="b0593-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="b0593-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b0593-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="b0593-115">Application</span></span> | <span data-ttu-id="b0593-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="b0593-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="b0593-117">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="b0593-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="b0593-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="b0593-118">Delegated (work or school account)</span></span> | <span data-ttu-id="b0593-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="b0593-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="b0593-120">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="b0593-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b0593-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="b0593-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="b0593-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="b0593-122">Request headers</span></span>

<span data-ttu-id="b0593-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="b0593-123">Name</span></span> | <span data-ttu-id="b0593-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0593-124">Type</span></span> | <span data-ttu-id="b0593-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0593-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="b0593-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="b0593-126">Authorization</span></span> | <span data-ttu-id="b0593-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="b0593-127">String</span></span> | <span data-ttu-id="b0593-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="b0593-128">Bearer {token}.</span></span> <span data-ttu-id="b0593-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="b0593-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b0593-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="b0593-130">Request body</span></span>
<span data-ttu-id="b0593-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="b0593-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b0593-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="b0593-132">Response</span></span>
<span data-ttu-id="b0593-133">Si se realiza correctamente, este método devuelve 200 Aceptar con las recomendaciones de seguridad del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="b0593-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="b0593-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0593-134">Example</span></span>

<span data-ttu-id="b0593-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="b0593-135">**Request**</span></span>

<span data-ttu-id="b0593-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="b0593-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="b0593-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="b0593-137">**Response**</span></span>

<span data-ttu-id="b0593-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b0593-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="b0593-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b0593-139">Related topics</span></span>
- [<span data-ttu-id="b0593-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="b0593-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b0593-141">Recomendación & seguridad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="b0593-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
