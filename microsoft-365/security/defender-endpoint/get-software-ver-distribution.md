---
title: Enumerar distribución de versión de software
description: Recupera una lista de la distribución de versiones de software de su organización
keywords: apis, api de gráficos, api admitidas, get, distribución de versiones de software, Api de Microsoft Defender para Endpoint tvm
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
ms.openlocfilehash: 7ac7fdf4c38846e2e8be614567ddb87a98e3a96c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772130"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="eab65-104">Enumerar distribución de versión de software</span><span class="sxs-lookup"><span data-stu-id="eab65-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eab65-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="eab65-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="eab65-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="eab65-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eab65-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="eab65-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="eab65-108">Recupera una lista de la distribución de versiones de software de su organización.</span><span class="sxs-lookup"><span data-stu-id="eab65-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="eab65-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="eab65-109">Permissions</span></span>
<span data-ttu-id="eab65-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="eab65-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="eab65-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="eab65-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="eab65-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="eab65-112">Permission type</span></span> |   <span data-ttu-id="eab65-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="eab65-113">Permission</span></span>  |   <span data-ttu-id="eab65-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="eab65-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="eab65-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="eab65-115">Application</span></span> | <span data-ttu-id="eab65-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="eab65-116">Software.Read.All</span></span> | <span data-ttu-id="eab65-117">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="eab65-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="eab65-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="eab65-118">Delegated (work or school account)</span></span> | <span data-ttu-id="eab65-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="eab65-119">Software.Read</span></span> | <span data-ttu-id="eab65-120">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="eab65-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="eab65-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="eab65-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="eab65-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="eab65-122">Request headers</span></span>

| <span data-ttu-id="eab65-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="eab65-123">Name</span></span>        | <span data-ttu-id="eab65-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="eab65-124">Type</span></span> | <span data-ttu-id="eab65-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="eab65-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="eab65-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="eab65-126">Authorization</span></span> | <span data-ttu-id="eab65-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="eab65-127">String</span></span> | <span data-ttu-id="eab65-128">Portador {token}. **Obligatorio**.</span><span class="sxs-lookup"><span data-stu-id="eab65-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="eab65-129">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="eab65-129">Request body</span></span>
<span data-ttu-id="eab65-130">En blanco</span><span class="sxs-lookup"><span data-stu-id="eab65-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="eab65-131">Respuesta</span><span class="sxs-lookup"><span data-stu-id="eab65-131">Response</span></span>
<span data-ttu-id="eab65-132">Si se realiza correctamente, este método devuelve 200 Ok con una lista de datos de distribuciones de software en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="eab65-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="eab65-133">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="eab65-133">Example</span></span>

<span data-ttu-id="eab65-134">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="eab65-134">**Request**</span></span>

<span data-ttu-id="eab65-135">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="eab65-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="eab65-136">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="eab65-136">**Response**</span></span>

<span data-ttu-id="eab65-137">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="eab65-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="eab65-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="eab65-138">Related topics</span></span>
- [<span data-ttu-id="eab65-139">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="eab65-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="eab65-140">Inventario & de software de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="eab65-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
