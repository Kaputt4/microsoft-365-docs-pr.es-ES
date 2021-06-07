---
title: Obtener puntuación de exposición
description: Recupera la puntuación de exposición organizativa.
keywords: api, api de gráfico, api admitidas, obtener, puntuación de exposición, puntuación de exposición organizativa
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 9da87dcb64f8c62966382e3a2888f03c49149a09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770440"
---
# <a name="get-exposure-score"></a><span data-ttu-id="f28a8-104">Obtener puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="f28a8-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f28a8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f28a8-105">**Applies to:**</span></span>
- [<span data-ttu-id="f28a8-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f28a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f28a8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f28a8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f28a8-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="f28a8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f28a8-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f28a8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f28a8-110">Recupera la puntuación de exposición organizativa.</span><span class="sxs-lookup"><span data-stu-id="f28a8-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="f28a8-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="f28a8-111">Permissions</span></span>

<span data-ttu-id="f28a8-112">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="f28a8-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f28a8-113">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f28a8-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f28a8-114">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="f28a8-114">Permission type</span></span> | <span data-ttu-id="f28a8-115">Permiso</span><span class="sxs-lookup"><span data-stu-id="f28a8-115">Permission</span></span> | <span data-ttu-id="f28a8-116">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="f28a8-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f28a8-117">Aplicación</span><span class="sxs-lookup"><span data-stu-id="f28a8-117">Application</span></span> | <span data-ttu-id="f28a8-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="f28a8-118">Score.Read.All</span></span> | <span data-ttu-id="f28a8-119">'Leer puntuación de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="f28a8-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="f28a8-120">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="f28a8-120">Delegated (work or school account)</span></span> | <span data-ttu-id="f28a8-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="f28a8-121">Score.Read</span></span> | <span data-ttu-id="f28a8-122">'Leer puntuación de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="f28a8-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="f28a8-123">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="f28a8-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="f28a8-124">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="f28a8-124">Request headers</span></span>

<span data-ttu-id="f28a8-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="f28a8-125">Name</span></span> | <span data-ttu-id="f28a8-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="f28a8-126">Type</span></span> | <span data-ttu-id="f28a8-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="f28a8-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="f28a8-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="f28a8-128">Authorization</span></span> | <span data-ttu-id="f28a8-129">Cadena</span><span class="sxs-lookup"><span data-stu-id="f28a8-129">String</span></span> | <span data-ttu-id="f28a8-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="f28a8-130">Bearer {token}.</span></span> <span data-ttu-id="f28a8-131">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="f28a8-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f28a8-132">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="f28a8-132">Request body</span></span>

<span data-ttu-id="f28a8-133">En blanco</span><span class="sxs-lookup"><span data-stu-id="f28a8-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f28a8-134">Respuesta</span><span class="sxs-lookup"><span data-stu-id="f28a8-134">Response</span></span>

<span data-ttu-id="f28a8-135">Si se realiza correctamente, este método devuelve 200 Ok, con los datos de exposición en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="f28a8-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="f28a8-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f28a8-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="f28a8-137">Solicitud</span><span class="sxs-lookup"><span data-stu-id="f28a8-137">Request</span></span>

<span data-ttu-id="f28a8-138">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f28a8-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="f28a8-139">Respuesta</span><span class="sxs-lookup"><span data-stu-id="f28a8-139">Response</span></span>

<span data-ttu-id="f28a8-140">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="f28a8-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="f28a8-141">La lista de respuestas que se muestra aquí puede truncarse por brevedad.</span><span class="sxs-lookup"><span data-stu-id="f28a8-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="f28a8-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f28a8-142">See also</span></span>

- [<span data-ttu-id="f28a8-143">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="f28a8-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="f28a8-144">Puntuación de & vulnerabilidad de amenazas</span><span class="sxs-lookup"><span data-stu-id="f28a8-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
