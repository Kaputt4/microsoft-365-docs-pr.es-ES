---
title: Obtener software por identificador
description: Recupera una lista de puntuaciones de exposición por grupo de dispositivos.
keywords: apis, graph api, apis admitidas, get, software, mdatp tvm api
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
ms.openlocfilehash: 57d6ccd2c5387d478b75cfb6fb32a5b1052e491c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198594"
---
# <a name="get-software-by-id"></a><span data-ttu-id="3e8cd-104">Obtener software por identificador</span><span class="sxs-lookup"><span data-stu-id="3e8cd-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3e8cd-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3e8cd-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="3e8cd-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="3e8cd-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3e8cd-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="3e8cd-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3e8cd-108">Recupera los detalles del software por identificador.</span><span class="sxs-lookup"><span data-stu-id="3e8cd-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="3e8cd-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="3e8cd-109">Permissions</span></span>
<span data-ttu-id="3e8cd-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="3e8cd-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3e8cd-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3e8cd-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="3e8cd-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="3e8cd-112">Permission type</span></span> |   <span data-ttu-id="3e8cd-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="3e8cd-113">Permission</span></span>  |   <span data-ttu-id="3e8cd-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="3e8cd-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3e8cd-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="3e8cd-115">Application</span></span> | <span data-ttu-id="3e8cd-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="3e8cd-116">Software.Read.All</span></span> | <span data-ttu-id="3e8cd-117">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="3e8cd-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="3e8cd-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="3e8cd-118">Delegated (work or school account)</span></span> | <span data-ttu-id="3e8cd-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="3e8cd-119">Software.Read</span></span> | <span data-ttu-id="3e8cd-120">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="3e8cd-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="3e8cd-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="3e8cd-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="3e8cd-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="3e8cd-122">Request headers</span></span>

| <span data-ttu-id="3e8cd-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="3e8cd-123">Name</span></span>        | <span data-ttu-id="3e8cd-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="3e8cd-124">Type</span></span> | <span data-ttu-id="3e8cd-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e8cd-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="3e8cd-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="3e8cd-126">Authorization</span></span> | <span data-ttu-id="3e8cd-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="3e8cd-127">String</span></span> | <span data-ttu-id="3e8cd-128">Portador {token}. **Obligatorio**.</span><span class="sxs-lookup"><span data-stu-id="3e8cd-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3e8cd-129">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="3e8cd-129">Request body</span></span>
<span data-ttu-id="3e8cd-130">En blanco</span><span class="sxs-lookup"><span data-stu-id="3e8cd-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3e8cd-131">Respuesta</span><span class="sxs-lookup"><span data-stu-id="3e8cd-131">Response</span></span>
<span data-ttu-id="3e8cd-132">Si se realiza correctamente, este método devuelve 200 Aceptar con los datos de software especificados en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="3e8cd-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="3e8cd-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e8cd-133">Example</span></span>

<span data-ttu-id="3e8cd-134">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="3e8cd-134">**Request**</span></span>

<span data-ttu-id="3e8cd-135">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3e8cd-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="3e8cd-136">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="3e8cd-136">**Response**</span></span>

<span data-ttu-id="3e8cd-137">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="3e8cd-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="3e8cd-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3e8cd-138">Related topics</span></span>
- [<span data-ttu-id="3e8cd-139">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="3e8cd-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="3e8cd-140">Inventario & de software de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="3e8cd-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
