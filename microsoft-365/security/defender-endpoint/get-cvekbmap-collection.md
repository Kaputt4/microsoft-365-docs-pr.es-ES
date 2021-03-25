---
title: Obtener API de mapa CVE-KB
description: Obtenga información sobre cómo usar la API de mapa Get CVE-KB para recuperar un mapa de CVE a KB y cve detalles en Microsoft Defender para endpoint.
keywords: apis, graph api, apis admitidas, get, cve, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166892"
---
# <a name="get-cve-kb-map-api"></a><span data-ttu-id="5aed4-104">Obtener API de mapa CVE-KB</span><span class="sxs-lookup"><span data-stu-id="5aed4-104">Get CVE-KB map API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5aed4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5aed4-105">**Applies to:**</span></span>
- [<span data-ttu-id="5aed4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5aed4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5aed4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5aed4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5aed4-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="5aed4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5aed4-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="5aed4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="5aed4-110">Recupera un mapa de CVE a los detalles de KB y CVE.</span><span class="sxs-lookup"><span data-stu-id="5aed4-110">Retrieves a map of CVE's to KB's and CVE details.</span></span>

## <a name="permissions"></a><span data-ttu-id="5aed4-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="5aed4-111">Permissions</span></span>
<span data-ttu-id="5aed4-112">El usuario necesita permisos de lectura.</span><span class="sxs-lookup"><span data-stu-id="5aed4-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="5aed4-113">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="5aed4-113">HTTP request</span></span>
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a><span data-ttu-id="5aed4-114">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="5aed4-114">Request headers</span></span>

<span data-ttu-id="5aed4-115">Encabezado</span><span class="sxs-lookup"><span data-stu-id="5aed4-115">Header</span></span> | <span data-ttu-id="5aed4-116">Valor</span><span class="sxs-lookup"><span data-stu-id="5aed4-116">Value</span></span> 
:---|:---
<span data-ttu-id="5aed4-117">Authorization</span><span class="sxs-lookup"><span data-stu-id="5aed4-117">Authorization</span></span> | <span data-ttu-id="5aed4-118">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="5aed4-118">Bearer {token}.</span></span> <span data-ttu-id="5aed4-119">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="5aed4-119">**Required**.</span></span>
<span data-ttu-id="5aed4-120">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="5aed4-120">Content type</span></span> | <span data-ttu-id="5aed4-121">application/json</span><span class="sxs-lookup"><span data-stu-id="5aed4-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="5aed4-122">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="5aed4-122">Request body</span></span>
<span data-ttu-id="5aed4-123">En blanco</span><span class="sxs-lookup"><span data-stu-id="5aed4-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5aed4-124">Respuesta</span><span class="sxs-lookup"><span data-stu-id="5aed4-124">Response</span></span>
<span data-ttu-id="5aed4-125">Si se realiza correctamente y existe la asignación: 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="5aed4-125">If successful and map exists - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="5aed4-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5aed4-126">Example</span></span>

<span data-ttu-id="5aed4-127">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="5aed4-127">**Request**</span></span>

<span data-ttu-id="5aed4-128">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5aed4-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

<span data-ttu-id="5aed4-129">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="5aed4-129">**Response**</span></span>

<span data-ttu-id="5aed4-130">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="5aed4-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
