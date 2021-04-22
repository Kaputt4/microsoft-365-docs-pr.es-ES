---
title: Obtener KBs ausentes por id. de software
description: Recupera las actualizaciones de seguridad que faltan por id. de software
keywords: apis, api de gráficos, api admitidas, get, list, file, information, software id, threat & api de administración de vulnerabilidades, Api de Microsoft Defender para Endpoint tvm
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 25ac8ce2c9fb17b2576f86dae1da984865b19018
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933894"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="2ed7e-104">Obtener KBs ausentes por id. de software</span><span class="sxs-lookup"><span data-stu-id="2ed7e-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ed7e-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2ed7e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2ed7e-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2ed7e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ed7e-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2ed7e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="2ed7e-108">Recupera KBs ausentes (actualizaciones de seguridad) por identificador de software</span><span class="sxs-lookup"><span data-stu-id="2ed7e-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="2ed7e-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="2ed7e-109">Permissions</span></span>

<span data-ttu-id="2ed7e-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="2ed7e-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2ed7e-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2ed7e-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="2ed7e-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="2ed7e-112">Permission type</span></span> |   <span data-ttu-id="2ed7e-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="2ed7e-113">Permission</span></span>   |   <span data-ttu-id="2ed7e-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="2ed7e-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2ed7e-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="2ed7e-115">Application</span></span> |<span data-ttu-id="2ed7e-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="2ed7e-116">Software.Read.All</span></span> |   <span data-ttu-id="2ed7e-117">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="2ed7e-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="2ed7e-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="2ed7e-118">Delegated (work or school account)</span></span> | <span data-ttu-id="2ed7e-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="2ed7e-119">Software.Read</span></span> |   <span data-ttu-id="2ed7e-120">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="2ed7e-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="2ed7e-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="2ed7e-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="2ed7e-122">Encabezado de solicitud</span><span class="sxs-lookup"><span data-stu-id="2ed7e-122">Request header</span></span>

<span data-ttu-id="2ed7e-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="2ed7e-123">Name</span></span> | <span data-ttu-id="2ed7e-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="2ed7e-124">Type</span></span> | <span data-ttu-id="2ed7e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ed7e-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="2ed7e-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="2ed7e-126">Authorization</span></span> | <span data-ttu-id="2ed7e-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="2ed7e-127">String</span></span> | <span data-ttu-id="2ed7e-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="2ed7e-128">Bearer {token}.</span></span> <span data-ttu-id="2ed7e-129">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="2ed7e-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2ed7e-130">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="2ed7e-130">Request body</span></span>

<span data-ttu-id="2ed7e-131">En blanco</span><span class="sxs-lookup"><span data-stu-id="2ed7e-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2ed7e-132">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2ed7e-132">Response</span></span>

<span data-ttu-id="2ed7e-133">Si se realiza correctamente, este método devuelve 200 Ok, con el software especificado que falta datos kb en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="2ed7e-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="2ed7e-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ed7e-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="2ed7e-135">Solicitud</span><span class="sxs-lookup"><span data-stu-id="2ed7e-135">Request</span></span>

<span data-ttu-id="2ed7e-136">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2ed7e-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="2ed7e-137">Respuesta</span><span class="sxs-lookup"><span data-stu-id="2ed7e-137">Response</span></span>

<span data-ttu-id="2ed7e-138">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="2ed7e-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="2ed7e-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2ed7e-139">Related topics</span></span>

- [<span data-ttu-id="2ed7e-140">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="2ed7e-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2ed7e-141">Inventario & de software de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="2ed7e-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
