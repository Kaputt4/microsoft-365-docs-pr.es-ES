---
title: Obtener KBs ausentes por id. de dispositivo
description: Recupera las actualizaciones de seguridad que faltan por id. de dispositivo
keywords: apis, api de gráfico, api admitidas, get, list, file, information, device id, threat & vulnerability management api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 908ddf531a5a20b9811084ba534a152ad6158170
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198854"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="21da4-104">Obtener KBs ausentes por id. de dispositivo</span><span class="sxs-lookup"><span data-stu-id="21da4-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="21da4-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="21da4-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="21da4-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="21da4-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="21da4-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="21da4-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="21da4-108">Recupera KBs ausentes (actualizaciones de seguridad) por identificador de dispositivo</span><span class="sxs-lookup"><span data-stu-id="21da4-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="21da4-109">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="21da4-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="21da4-110">Encabezado de solicitud</span><span class="sxs-lookup"><span data-stu-id="21da4-110">Request header</span></span>

<span data-ttu-id="21da4-111">Nombre</span><span class="sxs-lookup"><span data-stu-id="21da4-111">Name</span></span> | <span data-ttu-id="21da4-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="21da4-112">Type</span></span> | <span data-ttu-id="21da4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="21da4-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="21da4-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="21da4-114">Authorization</span></span> | <span data-ttu-id="21da4-115">Cadena</span><span class="sxs-lookup"><span data-stu-id="21da4-115">String</span></span> | <span data-ttu-id="21da4-116">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="21da4-116">Bearer {token}.</span></span> <span data-ttu-id="21da4-117">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="21da4-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="21da4-118">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="21da4-118">Request body</span></span>

<span data-ttu-id="21da4-119">En blanco</span><span class="sxs-lookup"><span data-stu-id="21da4-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="21da4-120">Respuesta</span><span class="sxs-lookup"><span data-stu-id="21da4-120">Response</span></span>

<span data-ttu-id="21da4-121">Si se realiza correctamente, este método devuelve 200 Ok, con el dispositivo especificado que falta datos kb en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="21da4-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="21da4-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21da4-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="21da4-123">Solicitud</span><span class="sxs-lookup"><span data-stu-id="21da4-123">Request</span></span>

<span data-ttu-id="21da4-124">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="21da4-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="21da4-125">Respuesta</span><span class="sxs-lookup"><span data-stu-id="21da4-125">Response</span></span>

<span data-ttu-id="21da4-126">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="21da4-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="21da4-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="21da4-127">Related topics</span></span>

- [<span data-ttu-id="21da4-128">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="21da4-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="21da4-129">Inventario & de software de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="21da4-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
