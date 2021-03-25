---
title: Enumerar software
description: Recupera una lista de inventario de software
keywords: apis, api de gráficos, api compatibles, get, list, file, information, software inventory, threat & vulnerability management api, mdatp tvm api
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
ms.openlocfilehash: 867fb57f61bd98b7c0afabd20b27e68d6bf45ef7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198570"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="796ba-104">Enumerar API de inventario de software</span><span class="sxs-lookup"><span data-stu-id="796ba-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="796ba-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="796ba-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="796ba-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="796ba-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="796ba-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="796ba-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="796ba-108">Recupera el inventario de software de la organización.</span><span class="sxs-lookup"><span data-stu-id="796ba-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="796ba-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="796ba-109">Permissions</span></span>
<span data-ttu-id="796ba-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="796ba-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="796ba-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="796ba-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="796ba-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="796ba-112">Permission type</span></span> |   <span data-ttu-id="796ba-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="796ba-113">Permission</span></span>  |   <span data-ttu-id="796ba-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="796ba-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="796ba-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="796ba-115">Application</span></span> |<span data-ttu-id="796ba-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="796ba-116">Software.Read.All</span></span> |    <span data-ttu-id="796ba-117">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="796ba-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="796ba-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="796ba-118">Delegated (work or school account)</span></span> | <span data-ttu-id="796ba-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="796ba-119">Software.Read</span></span> |    <span data-ttu-id="796ba-120">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="796ba-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="796ba-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="796ba-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="796ba-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="796ba-122">Request headers</span></span>

<span data-ttu-id="796ba-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="796ba-123">Name</span></span> | <span data-ttu-id="796ba-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="796ba-124">Type</span></span> | <span data-ttu-id="796ba-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="796ba-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="796ba-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="796ba-126">Authorization</span></span> | <span data-ttu-id="796ba-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="796ba-127">String</span></span> | <span data-ttu-id="796ba-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="796ba-128">Bearer {token}.</span></span> <span data-ttu-id="796ba-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="796ba-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="796ba-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="796ba-130">Request body</span></span>
<span data-ttu-id="796ba-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="796ba-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="796ba-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="796ba-132">Response</span></span>
<span data-ttu-id="796ba-133">Si se realiza correctamente, este método devuelve 200 Aceptar con el inventario de software en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="796ba-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="796ba-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="796ba-134">Example</span></span>

<span data-ttu-id="796ba-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="796ba-135">**Request**</span></span>

<span data-ttu-id="796ba-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="796ba-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="796ba-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="796ba-137">**Response**</span></span>

<span data-ttu-id="796ba-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="796ba-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="796ba-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="796ba-139">Related topics</span></span>
- [<span data-ttu-id="796ba-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="796ba-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="796ba-141">Inventario & de software de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="796ba-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
