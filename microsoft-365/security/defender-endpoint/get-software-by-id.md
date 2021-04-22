---
title: Obtener software por identificación
description: Recupera una lista de puntuaciones de exposición por grupo de dispositivos.
keywords: apis, api de gráficos, api admitidas, get, software, Api de Microsoft Defender para Endpoint tvm
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
ms.openlocfilehash: 31203e83570dbeb2404c9f1578301b5d6c18223c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934314"
---
# <a name="get-software-by-id"></a><span data-ttu-id="2d45d-104">Obtener software por identificación</span><span class="sxs-lookup"><span data-stu-id="2d45d-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2d45d-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2d45d-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2d45d-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2d45d-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2d45d-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2d45d-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2d45d-108">Recupera los detalles del software por identificador.</span><span class="sxs-lookup"><span data-stu-id="2d45d-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="2d45d-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="2d45d-109">Permissions</span></span>
<span data-ttu-id="2d45d-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="2d45d-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2d45d-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2d45d-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="2d45d-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="2d45d-112">Permission type</span></span> |   <span data-ttu-id="2d45d-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="2d45d-113">Permission</span></span>  |   <span data-ttu-id="2d45d-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="2d45d-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2d45d-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="2d45d-115">Application</span></span> | <span data-ttu-id="2d45d-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="2d45d-116">Software.Read.All</span></span> | <span data-ttu-id="2d45d-117">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="2d45d-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="2d45d-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="2d45d-118">Delegated (work or school account)</span></span> | <span data-ttu-id="2d45d-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="2d45d-119">Software.Read</span></span> | <span data-ttu-id="2d45d-120">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="2d45d-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="2d45d-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="2d45d-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="2d45d-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="2d45d-122">Request headers</span></span>

| <span data-ttu-id="2d45d-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d45d-123">Name</span></span>        | <span data-ttu-id="2d45d-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="2d45d-124">Type</span></span> | <span data-ttu-id="2d45d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d45d-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="2d45d-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="2d45d-126">Authorization</span></span> | <span data-ttu-id="2d45d-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="2d45d-127">String</span></span> | <span data-ttu-id="2d45d-128">Portador {token}. **Obligatorio**.</span><span class="sxs-lookup"><span data-stu-id="2d45d-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2d45d-129">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="2d45d-129">Request body</span></span>
<span data-ttu-id="2d45d-130">En blanco</span><span class="sxs-lookup"><span data-stu-id="2d45d-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2d45d-131">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2d45d-131">Response</span></span>
<span data-ttu-id="2d45d-132">Si se realiza correctamente, este método devuelve 200 Aceptar con los datos de software especificados en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="2d45d-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="2d45d-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d45d-133">Example</span></span>

<span data-ttu-id="2d45d-134">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="2d45d-134">**Request**</span></span>

<span data-ttu-id="2d45d-135">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2d45d-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="2d45d-136">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="2d45d-136">**Response**</span></span>

<span data-ttu-id="2d45d-137">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="2d45d-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a><span data-ttu-id="2d45d-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2d45d-138">Related topics</span></span>
- [<span data-ttu-id="2d45d-139">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="2d45d-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2d45d-140">Inventario & de software de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="2d45d-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
