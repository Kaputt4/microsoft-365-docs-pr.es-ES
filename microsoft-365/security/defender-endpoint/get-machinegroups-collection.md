---
title: Obtener LA API de recopilación de grupos de máquinas RBAC
description: Obtenga información sobre cómo usar la API de colección Get KB para recuperar una colección de grupos de dispositivos RBAC en Protección contra amenazas avanzada de Microsoft Defender.
keywords: apis, api de gráficos, api admitidas, get, RBAC, group
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167024"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="e45ec-104">Obtener API de colección KB</span><span class="sxs-lookup"><span data-stu-id="e45ec-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e45ec-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e45ec-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="e45ec-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="e45ec-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e45ec-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e45ec-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="e45ec-108">Recupera una colección de grupos de dispositivos RBAC.</span><span class="sxs-lookup"><span data-stu-id="e45ec-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="e45ec-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="e45ec-109">Permissions</span></span>
<span data-ttu-id="e45ec-110">El usuario necesita permisos de lectura.</span><span class="sxs-lookup"><span data-stu-id="e45ec-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="e45ec-111">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="e45ec-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="e45ec-112">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="e45ec-112">Request headers</span></span>

<span data-ttu-id="e45ec-113">Encabezado</span><span class="sxs-lookup"><span data-stu-id="e45ec-113">Header</span></span> | <span data-ttu-id="e45ec-114">Valor</span><span class="sxs-lookup"><span data-stu-id="e45ec-114">Value</span></span> 
:---|:---
<span data-ttu-id="e45ec-115">Authorization</span><span class="sxs-lookup"><span data-stu-id="e45ec-115">Authorization</span></span> | <span data-ttu-id="e45ec-116">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="e45ec-116">Bearer {token}.</span></span> <span data-ttu-id="e45ec-117">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="e45ec-117">**Required**.</span></span>
<span data-ttu-id="e45ec-118">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="e45ec-118">Content type</span></span> | <span data-ttu-id="e45ec-119">application/json</span><span class="sxs-lookup"><span data-stu-id="e45ec-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="e45ec-120">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="e45ec-120">Request body</span></span>
<span data-ttu-id="e45ec-121">En blanco</span><span class="sxs-lookup"><span data-stu-id="e45ec-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e45ec-122">Respuesta</span><span class="sxs-lookup"><span data-stu-id="e45ec-122">Response</span></span>
<span data-ttu-id="e45ec-123">Si se realiza correctamente: 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="e45ec-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="e45ec-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e45ec-124">Example</span></span>

<span data-ttu-id="e45ec-125">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="e45ec-125">**Request**</span></span>

<span data-ttu-id="e45ec-126">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e45ec-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="e45ec-127">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="e45ec-127">**Response**</span></span>

<span data-ttu-id="e45ec-128">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e45ec-128">Here is an example of the response.</span></span>
<span data-ttu-id="e45ec-129">El identificador de campo contiene el identificador de **grupo de** dispositivos y es igual al **campo rbacGroupId** en la información de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e45ec-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="e45ec-130">El **campo desagrupado** solo se aplica a un grupo para todos los dispositivos que no se han asignado a ningún grupo.</span><span class="sxs-lookup"><span data-stu-id="e45ec-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="e45ec-131">Este grupo, como siempre, tiene el nombre "UnassignedGroup".</span><span class="sxs-lookup"><span data-stu-id="e45ec-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
