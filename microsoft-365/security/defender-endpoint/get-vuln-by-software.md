---
title: Enumerar vulnerabilidades por software
description: Recupera una lista de vulnerabilidades en el software instalado.
keywords: apis, graph api, apis compatibles, get, vulnerabilities list, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: c28417d9782d14d890e771ed401f8ee5d3c26bc0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932768"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="773c6-104">Enumerar vulnerabilidades por software</span><span class="sxs-lookup"><span data-stu-id="773c6-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="773c6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="773c6-105">**Applies to:**</span></span>
- [<span data-ttu-id="773c6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="773c6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="773c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="773c6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="773c6-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="773c6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="773c6-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="773c6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="773c6-110">Recupera una lista de vulnerabilidades en el software instalado.</span><span class="sxs-lookup"><span data-stu-id="773c6-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="773c6-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="773c6-111">Permissions</span></span>
<span data-ttu-id="773c6-112">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="773c6-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="773c6-113">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="773c6-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="773c6-114">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="773c6-114">Permission type</span></span> |   <span data-ttu-id="773c6-115">Permiso</span><span class="sxs-lookup"><span data-stu-id="773c6-115">Permission</span></span>  |   <span data-ttu-id="773c6-116">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="773c6-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="773c6-117">Aplicación</span><span class="sxs-lookup"><span data-stu-id="773c6-117">Application</span></span> | <span data-ttu-id="773c6-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="773c6-118">Software.Read.All</span></span> | <span data-ttu-id="773c6-119">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="773c6-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="773c6-120">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="773c6-120">Delegated (work or school account)</span></span> | <span data-ttu-id="773c6-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="773c6-121">Software.Read</span></span> | <span data-ttu-id="773c6-122">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="773c6-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="773c6-123">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="773c6-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="773c6-124">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="773c6-124">Request headers</span></span>

| <span data-ttu-id="773c6-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="773c6-125">Name</span></span>        | <span data-ttu-id="773c6-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="773c6-126">Type</span></span> | <span data-ttu-id="773c6-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="773c6-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="773c6-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="773c6-128">Authorization</span></span> | <span data-ttu-id="773c6-129">Cadena</span><span class="sxs-lookup"><span data-stu-id="773c6-129">String</span></span> | <span data-ttu-id="773c6-130">Portador {token}. **Obligatorio**.</span><span class="sxs-lookup"><span data-stu-id="773c6-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="773c6-131">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="773c6-131">Request body</span></span>
<span data-ttu-id="773c6-132">En blanco</span><span class="sxs-lookup"><span data-stu-id="773c6-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="773c6-133">Respuesta</span><span class="sxs-lookup"><span data-stu-id="773c6-133">Response</span></span>
<span data-ttu-id="773c6-134">Si se realiza correctamente, este método devuelve 200 Ok con una lista de vulnerabilidades expuestas por el software especificado.</span><span class="sxs-lookup"><span data-stu-id="773c6-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="773c6-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="773c6-135">Example</span></span>

<span data-ttu-id="773c6-136">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="773c6-136">**Request**</span></span>

<span data-ttu-id="773c6-137">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="773c6-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="773c6-138">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="773c6-138">**Response**</span></span>

<span data-ttu-id="773c6-139">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="773c6-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
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

