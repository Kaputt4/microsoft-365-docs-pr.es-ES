---
title: Obtener todas las vulnerabilidades
description: Recupera una lista de todas las vulnerabilidades que afectan a la organización
keywords: apis, graph api, apis admitidas, get, vulnerability information, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: e9dd7e7d87e9343b0aae93e7ba47d89f9ed4bf41
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769010"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="94d0b-104">Enumerar vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="94d0b-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="94d0b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="94d0b-105">**Applies to:**</span></span>
- [<span data-ttu-id="94d0b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="94d0b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="94d0b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94d0b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="94d0b-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="94d0b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="94d0b-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="94d0b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="94d0b-110">Recupera una lista de todas las vulnerabilidades que afectan a la organización.</span><span class="sxs-lookup"><span data-stu-id="94d0b-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="94d0b-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="94d0b-111">Permissions</span></span>
<span data-ttu-id="94d0b-112">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="94d0b-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="94d0b-113">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="94d0b-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="94d0b-114">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="94d0b-114">Permission type</span></span> |   <span data-ttu-id="94d0b-115">Permiso</span><span class="sxs-lookup"><span data-stu-id="94d0b-115">Permission</span></span>  |   <span data-ttu-id="94d0b-116">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="94d0b-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="94d0b-117">Aplicación</span><span class="sxs-lookup"><span data-stu-id="94d0b-117">Application</span></span> |   <span data-ttu-id="94d0b-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="94d0b-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="94d0b-119">'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="94d0b-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="94d0b-120">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="94d0b-120">Delegated (work or school account)</span></span> | <span data-ttu-id="94d0b-121">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="94d0b-121">Vulnerability.Read</span></span> |   <span data-ttu-id="94d0b-122">'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="94d0b-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="94d0b-123">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="94d0b-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="94d0b-124">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="94d0b-124">Request headers</span></span>

<span data-ttu-id="94d0b-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="94d0b-125">Name</span></span> | <span data-ttu-id="94d0b-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="94d0b-126">Type</span></span> | <span data-ttu-id="94d0b-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="94d0b-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="94d0b-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="94d0b-128">Authorization</span></span> | <span data-ttu-id="94d0b-129">Cadena</span><span class="sxs-lookup"><span data-stu-id="94d0b-129">String</span></span> | <span data-ttu-id="94d0b-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="94d0b-130">Bearer {token}.</span></span> <span data-ttu-id="94d0b-131">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="94d0b-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="94d0b-132">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="94d0b-132">Request body</span></span>
<span data-ttu-id="94d0b-133">En blanco</span><span class="sxs-lookup"><span data-stu-id="94d0b-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="94d0b-134">Respuesta</span><span class="sxs-lookup"><span data-stu-id="94d0b-134">Response</span></span>
<span data-ttu-id="94d0b-135">Si se realiza correctamente, este método devuelve 200 Ok con la lista de vulnerabilidades en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="94d0b-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="94d0b-136">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="94d0b-136">Example</span></span>

<span data-ttu-id="94d0b-137">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="94d0b-137">**Request**</span></span>

<span data-ttu-id="94d0b-138">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="94d0b-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="94d0b-139">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="94d0b-139">**Response**</span></span>

<span data-ttu-id="94d0b-140">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="94d0b-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
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

## <a name="see-also"></a><span data-ttu-id="94d0b-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94d0b-141">See also</span></span>
- [<span data-ttu-id="94d0b-142">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="94d0b-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="94d0b-143">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="94d0b-143">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
