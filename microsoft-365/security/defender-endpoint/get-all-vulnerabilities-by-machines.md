---
title: Obtener todas las vulnerabilidades por máquina y software
description: Recupera una lista de todas las vulnerabilidades que afectan a la organización por máquina y software
keywords: apis, graph api, apis admitidas, get, vulnerability information, mdatp tvm api
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
ms.openlocfilehash: f7d67948e3b3e7a1a878386a397d2f4a6e8e998e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166904"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="b9211-104">Enumerar las vulnerabilidades por máquina y software</span><span class="sxs-lookup"><span data-stu-id="b9211-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9211-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b9211-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9211-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b9211-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9211-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9211-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b9211-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b9211-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b9211-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b9211-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="b9211-110">Recupera una lista de todas las vulnerabilidades que afectan a la organización por [máquina](machine.md) y [software](software.md).</span><span class="sxs-lookup"><span data-stu-id="b9211-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="b9211-111">Si la vulnerabilidad tiene un KB de corrección, aparecerá en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b9211-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="b9211-112">Admite [consultas de OData V4](https://www.odata.org/documentation/).</span><span class="sxs-lookup"><span data-stu-id="b9211-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="b9211-113">OData ```$filter``` se admite en todas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="b9211-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="b9211-114">Se trata de una excelente API para [la integración de Power BI.](api-power-bi.md)</span><span class="sxs-lookup"><span data-stu-id="b9211-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="b9211-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="b9211-115">Permissions</span></span>
<span data-ttu-id="b9211-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="b9211-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b9211-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b9211-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b9211-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="b9211-118">Permission type</span></span> |   <span data-ttu-id="b9211-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="b9211-119">Permission</span></span>  |   <span data-ttu-id="b9211-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="b9211-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b9211-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="b9211-121">Application</span></span> |   <span data-ttu-id="b9211-122">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="b9211-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="b9211-123">'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="b9211-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="b9211-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="b9211-124">Delegated (work or school account)</span></span> | <span data-ttu-id="b9211-125">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="b9211-125">Vulnerability.Read</span></span> |   <span data-ttu-id="b9211-126">'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="b9211-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b9211-127">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="b9211-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="b9211-128">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="b9211-128">Request headers</span></span>

<span data-ttu-id="b9211-129">Nombre</span><span class="sxs-lookup"><span data-stu-id="b9211-129">Name</span></span> | <span data-ttu-id="b9211-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="b9211-130">Type</span></span> | <span data-ttu-id="b9211-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9211-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="b9211-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="b9211-132">Authorization</span></span> | <span data-ttu-id="b9211-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="b9211-133">String</span></span> | <span data-ttu-id="b9211-134">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="b9211-134">Bearer {token}.</span></span> <span data-ttu-id="b9211-135">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="b9211-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b9211-136">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="b9211-136">Request body</span></span>
<span data-ttu-id="b9211-137">En blanco</span><span class="sxs-lookup"><span data-stu-id="b9211-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b9211-138">Respuesta</span><span class="sxs-lookup"><span data-stu-id="b9211-138">Response</span></span>
<span data-ttu-id="b9211-139">Si se realiza correctamente, este método devuelve 200 Ok con la lista de vulnerabilidades en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="b9211-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="b9211-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9211-140">Example</span></span>

<span data-ttu-id="b9211-141">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="b9211-141">**Request**</span></span>

<span data-ttu-id="b9211-142">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="b9211-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="b9211-143">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="b9211-143">**Response**</span></span>

<span data-ttu-id="b9211-144">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b9211-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="b9211-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9211-145">See also</span></span>

- [<span data-ttu-id="b9211-146">Administración de vulnerabilidades y amenazas basadas en riesgos</span><span class="sxs-lookup"><span data-stu-id="b9211-146">Risk-based threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b9211-147">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="b9211-147">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
