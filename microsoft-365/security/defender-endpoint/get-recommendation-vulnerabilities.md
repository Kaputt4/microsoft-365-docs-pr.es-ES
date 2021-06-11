---
title: Enumerar vulnerabilidades por recomendación
description: Recupera una lista de vulnerabilidades asociadas con la recomendación de seguridad.
keywords: apis, api de gráficos, api admitidas, obtener, lista de vulnerabilidades, recomendación de seguridad, recomendación de seguridad para vulnerabilidades, Administración de amenazas y vulnerabilidades, Administración de amenazas y vulnerabilidades api
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
ms.openlocfilehash: d5a59c3cd57aa369b1edb46eebddffb84a2b8c78
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845167"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="70aa2-104">Enumerar vulnerabilidades por recomendación</span><span class="sxs-lookup"><span data-stu-id="70aa2-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="70aa2-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="70aa2-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="70aa2-106">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="70aa2-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="70aa2-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="70aa2-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="70aa2-108">Recupera una lista de vulnerabilidades asociadas con la recomendación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="70aa2-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="70aa2-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="70aa2-109">Permissions</span></span>
<span data-ttu-id="70aa2-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="70aa2-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="70aa2-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="70aa2-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="70aa2-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="70aa2-112">Permission type</span></span> |   <span data-ttu-id="70aa2-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="70aa2-113">Permission</span></span>  |   <span data-ttu-id="70aa2-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="70aa2-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="70aa2-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="70aa2-115">Application</span></span> |   <span data-ttu-id="70aa2-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="70aa2-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="70aa2-117">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="70aa2-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="70aa2-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="70aa2-118">Delegated (work or school account)</span></span> | <span data-ttu-id="70aa2-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="70aa2-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="70aa2-120">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="70aa2-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="70aa2-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="70aa2-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="70aa2-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="70aa2-122">Request headers</span></span>

<span data-ttu-id="70aa2-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="70aa2-123">Name</span></span> | <span data-ttu-id="70aa2-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="70aa2-124">Type</span></span> | <span data-ttu-id="70aa2-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="70aa2-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="70aa2-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="70aa2-126">Authorization</span></span> | <span data-ttu-id="70aa2-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="70aa2-127">String</span></span> | <span data-ttu-id="70aa2-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="70aa2-128">Bearer {token}.</span></span> <span data-ttu-id="70aa2-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="70aa2-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="70aa2-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="70aa2-130">Request body</span></span>
<span data-ttu-id="70aa2-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="70aa2-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="70aa2-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="70aa2-132">Response</span></span>
<span data-ttu-id="70aa2-133">Si se realiza correctamente, este método devuelve 200 Ok, con la lista de vulnerabilidades asociadas con la recomendación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="70aa2-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="70aa2-134">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="70aa2-134">Example</span></span>

<span data-ttu-id="70aa2-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="70aa2-135">**Request**</span></span>

<span data-ttu-id="70aa2-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="70aa2-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="70aa2-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="70aa2-137">**Response**</span></span>

<span data-ttu-id="70aa2-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="70aa2-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a><span data-ttu-id="70aa2-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="70aa2-139">Related topics</span></span>
- [<span data-ttu-id="70aa2-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="70aa2-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="70aa2-141">Recomendación & seguridad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="70aa2-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
