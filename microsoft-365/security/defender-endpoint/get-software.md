---
title: Enumerar software
description: Recupera una lista de inventario de software
keywords: apis, api de gráficos, api compatibles, get, list, file, information, software inventory, threat & administración de vulnerabilidades api, Api de Microsoft Defender para Endpoint tvm
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
ms.openlocfilehash: f7e71c58396fd4b3ed40ba88aab5c2757ae41a41
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771086"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="c1143-104">Enumerar API de inventario de software</span><span class="sxs-lookup"><span data-stu-id="c1143-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c1143-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c1143-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c1143-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="c1143-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c1143-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c1143-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="c1143-108">Recupera el inventario de software de la organización.</span><span class="sxs-lookup"><span data-stu-id="c1143-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="c1143-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="c1143-109">Permissions</span></span>
<span data-ttu-id="c1143-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="c1143-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c1143-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c1143-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="c1143-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="c1143-112">Permission type</span></span> |   <span data-ttu-id="c1143-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="c1143-113">Permission</span></span>  |   <span data-ttu-id="c1143-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="c1143-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c1143-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="c1143-115">Application</span></span> |<span data-ttu-id="c1143-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="c1143-116">Software.Read.All</span></span> |    <span data-ttu-id="c1143-117">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="c1143-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="c1143-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="c1143-118">Delegated (work or school account)</span></span> | <span data-ttu-id="c1143-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="c1143-119">Software.Read</span></span> |    <span data-ttu-id="c1143-120">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="c1143-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="c1143-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="c1143-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="c1143-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="c1143-122">Request headers</span></span>

<span data-ttu-id="c1143-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="c1143-123">Name</span></span> | <span data-ttu-id="c1143-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="c1143-124">Type</span></span> | <span data-ttu-id="c1143-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1143-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="c1143-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="c1143-126">Authorization</span></span> | <span data-ttu-id="c1143-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="c1143-127">String</span></span> | <span data-ttu-id="c1143-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="c1143-128">Bearer {token}.</span></span> <span data-ttu-id="c1143-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="c1143-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c1143-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="c1143-130">Request body</span></span>
<span data-ttu-id="c1143-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="c1143-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c1143-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="c1143-132">Response</span></span>
<span data-ttu-id="c1143-133">Si se realiza correctamente, este método devuelve 200 Aceptar con el inventario de software en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c1143-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="c1143-134">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c1143-134">Example</span></span>

<span data-ttu-id="c1143-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="c1143-135">**Request**</span></span>

<span data-ttu-id="c1143-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c1143-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="c1143-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="c1143-137">**Response**</span></span>

<span data-ttu-id="c1143-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="c1143-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="c1143-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c1143-139">Related topics</span></span>
- [<span data-ttu-id="c1143-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="c1143-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="c1143-141">Inventario & de software de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="c1143-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
