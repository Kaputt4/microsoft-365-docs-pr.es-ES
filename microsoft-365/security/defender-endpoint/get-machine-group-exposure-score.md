---
title: Puntuación de exposición de lista por grupo de dispositivos
description: Recupera una lista de puntuaciones de exposición por grupo de dispositivos.
keywords: api, api de gráfico, api admitidas, obtener, puntuación de exposición, grupo de dispositivos, puntuación de exposición de grupo de dispositivos
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a7f343db64174fe3c48eaf8b584b03b53921edcb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843619"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="30e9e-104">Puntuación de exposición de lista por grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="30e9e-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="30e9e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="30e9e-105">**Applies to:**</span></span>
- [<span data-ttu-id="30e9e-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="30e9e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="30e9e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30e9e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="30e9e-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="30e9e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="30e9e-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="30e9e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="30e9e-110">Recupera una colección de alertas relacionadas con una dirección de dominio determinada.</span><span class="sxs-lookup"><span data-stu-id="30e9e-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="30e9e-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="30e9e-111">Permissions</span></span>

<span data-ttu-id="30e9e-112">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="30e9e-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="30e9e-113">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="30e9e-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="30e9e-114">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="30e9e-114">Permission type</span></span> |   <span data-ttu-id="30e9e-115">Permiso</span><span class="sxs-lookup"><span data-stu-id="30e9e-115">Permission</span></span>  |   <span data-ttu-id="30e9e-116">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="30e9e-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="30e9e-117">Aplicación</span><span class="sxs-lookup"><span data-stu-id="30e9e-117">Application</span></span> | <span data-ttu-id="30e9e-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="30e9e-118">Score.Read.All</span></span> | <span data-ttu-id="30e9e-119">'Leer puntuación de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="30e9e-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="30e9e-120">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="30e9e-120">Delegated (work or school account)</span></span> | <span data-ttu-id="30e9e-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="30e9e-121">Score.Read</span></span> | <span data-ttu-id="30e9e-122">'Leer puntuación de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="30e9e-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="30e9e-123">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="30e9e-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="30e9e-124">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="30e9e-124">Request headers</span></span>

| <span data-ttu-id="30e9e-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="30e9e-125">Name</span></span>        | <span data-ttu-id="30e9e-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="30e9e-126">Type</span></span> | <span data-ttu-id="30e9e-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="30e9e-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="30e9e-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="30e9e-128">Authorization</span></span> | <span data-ttu-id="30e9e-129">Cadena</span><span class="sxs-lookup"><span data-stu-id="30e9e-129">String</span></span> | <span data-ttu-id="30e9e-130">Portador {token}. **Obligatorio**.</span><span class="sxs-lookup"><span data-stu-id="30e9e-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="30e9e-131">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="30e9e-131">Request body</span></span>

<span data-ttu-id="30e9e-132">En blanco</span><span class="sxs-lookup"><span data-stu-id="30e9e-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="30e9e-133">Respuesta</span><span class="sxs-lookup"><span data-stu-id="30e9e-133">Response</span></span>

<span data-ttu-id="30e9e-134">Si se realiza correctamente, este método devuelve 200 Ok, con una lista de la puntuación de exposición por datos de grupo de dispositivos en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="30e9e-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="30e9e-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30e9e-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="30e9e-136">Solicitud</span><span class="sxs-lookup"><span data-stu-id="30e9e-136">Request</span></span>

<span data-ttu-id="30e9e-137">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="30e9e-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="30e9e-138">Respuesta</span><span class="sxs-lookup"><span data-stu-id="30e9e-138">Response</span></span>

<span data-ttu-id="30e9e-139">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="30e9e-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="30e9e-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="30e9e-140">Related topics</span></span>

- [<span data-ttu-id="30e9e-141">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="30e9e-141">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="30e9e-142">Puntuación de & vulnerabilidad de amenazas</span><span class="sxs-lookup"><span data-stu-id="30e9e-142">Threat & Vulnerability exposure score</span></span>](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
