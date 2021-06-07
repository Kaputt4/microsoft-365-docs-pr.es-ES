---
title: Enumerar dispositivos por recomendación
description: Recupera una lista de dispositivos asociados con la recomendación de seguridad.
keywords: apis, api de gráficos, api admitidas, get, recomendación de seguridad para dispositivos vulnerables, Administración de amenazas y vulnerabilidades, api Administración de amenazas y vulnerabilidades
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
ms.openlocfilehash: 6c762a15051444ec950e92998317db4f7e51783c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771818"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="a9ff5-104">Enumerar dispositivos por recomendación</span><span class="sxs-lookup"><span data-stu-id="a9ff5-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a9ff5-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a9ff5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="a9ff5-106">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a9ff5-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a9ff5-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a9ff5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a9ff5-108">Recupera una lista de dispositivos asociados con la recomendación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a9ff5-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="a9ff5-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="a9ff5-109">Permissions</span></span>
<span data-ttu-id="a9ff5-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="a9ff5-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a9ff5-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9ff5-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="a9ff5-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="a9ff5-112">Permission type</span></span> |   <span data-ttu-id="a9ff5-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="a9ff5-113">Permission</span></span>  |   <span data-ttu-id="a9ff5-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="a9ff5-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a9ff5-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="a9ff5-115">Application</span></span> |   <span data-ttu-id="a9ff5-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="a9ff5-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="a9ff5-117">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="a9ff5-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="a9ff5-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="a9ff5-118">Delegated (work or school account)</span></span> | <span data-ttu-id="a9ff5-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="a9ff5-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="a9ff5-120">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="a9ff5-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="a9ff5-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="a9ff5-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="a9ff5-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="a9ff5-122">Request headers</span></span>

<span data-ttu-id="a9ff5-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="a9ff5-123">Name</span></span> | <span data-ttu-id="a9ff5-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="a9ff5-124">Type</span></span> | <span data-ttu-id="a9ff5-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9ff5-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="a9ff5-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="a9ff5-126">Authorization</span></span> | <span data-ttu-id="a9ff5-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="a9ff5-127">String</span></span> | <span data-ttu-id="a9ff5-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="a9ff5-128">Bearer {token}.</span></span> <span data-ttu-id="a9ff5-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="a9ff5-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a9ff5-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="a9ff5-130">Request body</span></span>
<span data-ttu-id="a9ff5-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="a9ff5-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a9ff5-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="a9ff5-132">Response</span></span>
<span data-ttu-id="a9ff5-133">Si se realiza correctamente, este método devuelve 200 Aceptar con la lista de dispositivos asociados con la recomendación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a9ff5-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="a9ff5-134">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a9ff5-134">Example</span></span>

<span data-ttu-id="a9ff5-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="a9ff5-135">**Request**</span></span>

<span data-ttu-id="a9ff5-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a9ff5-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="a9ff5-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="a9ff5-137">**Response**</span></span>

<span data-ttu-id="a9ff5-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a9ff5-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="a9ff5-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a9ff5-139">Related topics</span></span>
- [<span data-ttu-id="a9ff5-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="a9ff5-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="a9ff5-141">Recomendación & seguridad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="a9ff5-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
