---
title: Obtener las vulnerabilidades detectadas
description: Recupera una colección de vulnerabilidades detectadas relacionadas con un identificador de dispositivo determinado.
keywords: apis, api de gráficos, api admitidas, obtener, lista, archivo, información, vulnerabilidades detectadas, api de & administración de vulnerabilidades amenazas, API de Microsoft Defender para Endpoint tvm
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ac7a9ef932f2640bbc5325f0154c0ceb48ae3018
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772298"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="4db34-104">Obtener las vulnerabilidades detectadas</span><span class="sxs-lookup"><span data-stu-id="4db34-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4db34-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4db34-105">**Applies to:**</span></span>
- [<span data-ttu-id="4db34-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4db34-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4db34-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4db34-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4db34-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="4db34-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4db34-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="4db34-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="4db34-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="4db34-110">API description</span></span>
<span data-ttu-id="4db34-111">Recupera una colección de vulnerabilidades detectadas relacionadas con un identificador de dispositivo determinado.</span><span class="sxs-lookup"><span data-stu-id="4db34-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="4db34-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="4db34-112">Limitations</span></span>
1. <span data-ttu-id="4db34-113">Las limitaciones de velocidad para esta API son 50 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="4db34-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="4db34-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="4db34-114">Permissions</span></span>

<span data-ttu-id="4db34-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="4db34-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4db34-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4db34-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4db34-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="4db34-117">Permission type</span></span> | <span data-ttu-id="4db34-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="4db34-118">Permission</span></span> | <span data-ttu-id="4db34-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="4db34-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4db34-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="4db34-120">Application</span></span> |<span data-ttu-id="4db34-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="4db34-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="4db34-122">'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="4db34-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="4db34-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="4db34-123">Delegated (work or school account)</span></span> | <span data-ttu-id="4db34-124">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="4db34-124">Vulnerability.Read</span></span> | <span data-ttu-id="4db34-125">'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="4db34-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="4db34-126">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="4db34-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="4db34-127">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="4db34-127">Request headers</span></span>

<span data-ttu-id="4db34-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="4db34-128">Name</span></span> | <span data-ttu-id="4db34-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="4db34-129">Type</span></span> | <span data-ttu-id="4db34-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="4db34-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="4db34-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="4db34-131">Authorization</span></span> | <span data-ttu-id="4db34-132">Cadena</span><span class="sxs-lookup"><span data-stu-id="4db34-132">String</span></span> | <span data-ttu-id="4db34-133">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="4db34-133">Bearer {token}.</span></span> <span data-ttu-id="4db34-134">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="4db34-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4db34-135">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="4db34-135">Request body</span></span>

<span data-ttu-id="4db34-136">En blanco</span><span class="sxs-lookup"><span data-stu-id="4db34-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4db34-137">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4db34-137">Response</span></span>

<span data-ttu-id="4db34-138">Si se realiza correctamente, este método devuelve 200 Aceptar con la información de vulnerabilidad detectada en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="4db34-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="4db34-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4db34-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="4db34-140">Solicitud</span><span class="sxs-lookup"><span data-stu-id="4db34-140">Request</span></span>

<span data-ttu-id="4db34-141">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4db34-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="4db34-142">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4db34-142">Response</span></span>

<span data-ttu-id="4db34-143">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="4db34-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a><span data-ttu-id="4db34-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4db34-144">See also</span></span>

- [<span data-ttu-id="4db34-145">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="4db34-145">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="4db34-146">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="4db34-146">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
