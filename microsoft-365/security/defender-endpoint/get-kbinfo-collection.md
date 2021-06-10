---
title: Obtener API de colección KB
description: Recupera una colección de bases de conocimientos (KB) y detalles de KB con Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, kb
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
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167180"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="27163-104">Obtener API de colección KB</span><span class="sxs-lookup"><span data-stu-id="27163-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="27163-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="27163-105">**Applies to:**</span></span>
- [<span data-ttu-id="27163-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="27163-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="27163-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27163-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="27163-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="27163-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="27163-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="27163-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="27163-110">Recupera una colección de detalles de KB y KB.</span><span class="sxs-lookup"><span data-stu-id="27163-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="27163-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="27163-111">Permissions</span></span>
<span data-ttu-id="27163-112">El usuario necesita permisos de lectura.</span><span class="sxs-lookup"><span data-stu-id="27163-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="27163-113">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="27163-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="27163-114">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="27163-114">Request headers</span></span>

<span data-ttu-id="27163-115">Encabezado</span><span class="sxs-lookup"><span data-stu-id="27163-115">Header</span></span> | <span data-ttu-id="27163-116">Valor</span><span class="sxs-lookup"><span data-stu-id="27163-116">Value</span></span> 
:---|:---
<span data-ttu-id="27163-117">Authorization</span><span class="sxs-lookup"><span data-stu-id="27163-117">Authorization</span></span> | <span data-ttu-id="27163-118">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="27163-118">Bearer {token}.</span></span> <span data-ttu-id="27163-119">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="27163-119">**Required**.</span></span>
<span data-ttu-id="27163-120">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="27163-120">Content type</span></span> | <span data-ttu-id="27163-121">application/json</span><span class="sxs-lookup"><span data-stu-id="27163-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="27163-122">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="27163-122">Request body</span></span>
<span data-ttu-id="27163-123">En blanco</span><span class="sxs-lookup"><span data-stu-id="27163-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="27163-124">Respuesta</span><span class="sxs-lookup"><span data-stu-id="27163-124">Response</span></span>
<span data-ttu-id="27163-125">Si se realiza correctamente: 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="27163-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="27163-126">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27163-126">Example</span></span>

<span data-ttu-id="27163-127">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="27163-127">**Request**</span></span>

<span data-ttu-id="27163-128">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="27163-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="27163-129">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="27163-129">**Response**</span></span>

<span data-ttu-id="27163-130">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="27163-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
