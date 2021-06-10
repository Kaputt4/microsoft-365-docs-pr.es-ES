---
title: Buscar información del dispositivo por API IP interna
description: Use esta API para crear llamadas relacionadas con la búsqueda de una entrada de dispositivo alrededor de una marca de tiempo específica por IP interna.
keywords: ip, apis, api de gráficos, api admitidas, buscar dispositivo, información del dispositivo
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167144"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="b038e-104">Buscar información del dispositivo por API IP interna</span><span class="sxs-lookup"><span data-stu-id="b038e-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b038e-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b038e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="b038e-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b038e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b038e-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b038e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b038e-108">Buscar un dispositivo por IP interna.</span><span class="sxs-lookup"><span data-stu-id="b038e-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="b038e-109">La marca de tiempo debe estar dentro de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="b038e-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="b038e-110">Permisos</span><span class="sxs-lookup"><span data-stu-id="b038e-110">Permissions</span></span>
<span data-ttu-id="b038e-111">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="b038e-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b038e-112">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b038e-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b038e-113">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="b038e-113">Permission type</span></span> | <span data-ttu-id="b038e-114">Permiso</span><span class="sxs-lookup"><span data-stu-id="b038e-114">Permission</span></span> | <span data-ttu-id="b038e-115">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="b038e-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b038e-116">Aplicación</span><span class="sxs-lookup"><span data-stu-id="b038e-116">Application</span></span> | <span data-ttu-id="b038e-117">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="b038e-117">Machine.Read.All</span></span> | <span data-ttu-id="b038e-118">'Leer todos los perfiles de máquina'</span><span class="sxs-lookup"><span data-stu-id="b038e-118">'Read all machine profiles'</span></span>
<span data-ttu-id="b038e-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="b038e-119">Application</span></span> | <span data-ttu-id="b038e-120">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b038e-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="b038e-121">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="b038e-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b038e-122">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="b038e-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="b038e-123">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="b038e-123">Request headers</span></span>

<span data-ttu-id="b038e-124">Nombre</span><span class="sxs-lookup"><span data-stu-id="b038e-124">Name</span></span> | <span data-ttu-id="b038e-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="b038e-125">Type</span></span> | <span data-ttu-id="b038e-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="b038e-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="b038e-127">Authorization</span><span class="sxs-lookup"><span data-stu-id="b038e-127">Authorization</span></span> | <span data-ttu-id="b038e-128">Cadena</span><span class="sxs-lookup"><span data-stu-id="b038e-128">String</span></span> | <span data-ttu-id="b038e-129">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="b038e-129">Bearer {token}.</span></span> <span data-ttu-id="b038e-130">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="b038e-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b038e-131">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="b038e-131">Request body</span></span>
<span data-ttu-id="b038e-132">En blanco</span><span class="sxs-lookup"><span data-stu-id="b038e-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b038e-133">Respuesta</span><span class="sxs-lookup"><span data-stu-id="b038e-133">Response</span></span>
<span data-ttu-id="b038e-134">Si se realiza correctamente y la máquina existe: 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="b038e-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="b038e-135">Si no se encuentra ninguna máquina: 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="b038e-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="b038e-136">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b038e-136">Example</span></span>

<span data-ttu-id="b038e-137">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="b038e-137">**Request**</span></span>

<span data-ttu-id="b038e-138">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="b038e-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="b038e-139">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="b038e-139">**Response**</span></span>

<span data-ttu-id="b038e-140">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b038e-140">Here is an example of the response.</span></span>

<span data-ttu-id="b038e-141">La respuesta devolverá una lista de todos los dispositivos que informaron de esta dirección IP en los dieciséis minutos antes y después de la marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="b038e-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
