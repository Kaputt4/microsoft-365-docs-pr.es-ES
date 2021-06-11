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
ms.openlocfilehash: a321a3aec9bbd0e7e405b82b7cbd56cf214694ca
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845209"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="cad7b-104">Enumerar dispositivos por recomendación</span><span class="sxs-lookup"><span data-stu-id="cad7b-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cad7b-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cad7b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="cad7b-106">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="cad7b-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cad7b-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="cad7b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="cad7b-108">Recupera una lista de dispositivos asociados con la recomendación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cad7b-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="cad7b-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="cad7b-109">Permissions</span></span>
<span data-ttu-id="cad7b-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="cad7b-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cad7b-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="cad7b-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="cad7b-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="cad7b-112">Permission type</span></span> |   <span data-ttu-id="cad7b-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="cad7b-113">Permission</span></span>  |   <span data-ttu-id="cad7b-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="cad7b-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cad7b-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="cad7b-115">Application</span></span> |   <span data-ttu-id="cad7b-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="cad7b-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="cad7b-117">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="cad7b-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="cad7b-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="cad7b-118">Delegated (work or school account)</span></span> | <span data-ttu-id="cad7b-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="cad7b-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="cad7b-120">'Leer información de recomendación de seguridad de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="cad7b-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="cad7b-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="cad7b-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="cad7b-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="cad7b-122">Request headers</span></span>

<span data-ttu-id="cad7b-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="cad7b-123">Name</span></span> | <span data-ttu-id="cad7b-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="cad7b-124">Type</span></span> | <span data-ttu-id="cad7b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="cad7b-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="cad7b-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="cad7b-126">Authorization</span></span> | <span data-ttu-id="cad7b-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="cad7b-127">String</span></span> | <span data-ttu-id="cad7b-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="cad7b-128">Bearer {token}.</span></span> <span data-ttu-id="cad7b-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="cad7b-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cad7b-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="cad7b-130">Request body</span></span>
<span data-ttu-id="cad7b-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="cad7b-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cad7b-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="cad7b-132">Response</span></span>
<span data-ttu-id="cad7b-133">Si se realiza correctamente, este método devuelve 200 Aceptar con la lista de dispositivos asociados con la recomendación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cad7b-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="cad7b-134">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cad7b-134">Example</span></span>

<span data-ttu-id="cad7b-135">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="cad7b-135">**Request**</span></span>

<span data-ttu-id="cad7b-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cad7b-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="cad7b-137">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="cad7b-137">**Response**</span></span>

<span data-ttu-id="cad7b-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="cad7b-138">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="cad7b-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cad7b-139">Related topics</span></span>
- [<span data-ttu-id="cad7b-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="cad7b-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="cad7b-141">Recomendación & seguridad de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="cad7b-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
