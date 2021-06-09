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
ms.openlocfilehash: 071b0e7597d334fe06d5045e06a5c4d82dd65609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845395"
---
# <a name="get-exposure-score"></a><span data-ttu-id="61586-104">Obtener puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="61586-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61586-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="61586-105">**Applies to:**</span></span>
- [<span data-ttu-id="61586-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="61586-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="61586-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61586-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="61586-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="61586-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="61586-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="61586-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="61586-110">Recupera la puntuación de exposición organizativa.</span><span class="sxs-lookup"><span data-stu-id="61586-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="61586-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="61586-111">Permissions</span></span>

<span data-ttu-id="61586-112">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="61586-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="61586-113">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="61586-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="61586-114">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="61586-114">Permission type</span></span> | <span data-ttu-id="61586-115">Permiso</span><span class="sxs-lookup"><span data-stu-id="61586-115">Permission</span></span> | <span data-ttu-id="61586-116">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="61586-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="61586-117">Aplicación</span><span class="sxs-lookup"><span data-stu-id="61586-117">Application</span></span> | <span data-ttu-id="61586-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="61586-118">Score.Read.All</span></span> | <span data-ttu-id="61586-119">'Leer puntuación de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="61586-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="61586-120">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="61586-120">Delegated (work or school account)</span></span> | <span data-ttu-id="61586-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="61586-121">Score.Read</span></span> | <span data-ttu-id="61586-122">'Leer puntuación de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="61586-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="61586-123">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="61586-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="61586-124">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="61586-124">Request headers</span></span>

<span data-ttu-id="61586-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="61586-125">Name</span></span> | <span data-ttu-id="61586-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="61586-126">Type</span></span> | <span data-ttu-id="61586-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="61586-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="61586-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="61586-128">Authorization</span></span> | <span data-ttu-id="61586-129">Cadena</span><span class="sxs-lookup"><span data-stu-id="61586-129">String</span></span> | <span data-ttu-id="61586-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="61586-130">Bearer {token}.</span></span> <span data-ttu-id="61586-131">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="61586-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="61586-132">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="61586-132">Request body</span></span>

<span data-ttu-id="61586-133">En blanco</span><span class="sxs-lookup"><span data-stu-id="61586-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="61586-134">Respuesta</span><span class="sxs-lookup"><span data-stu-id="61586-134">Response</span></span>

<span data-ttu-id="61586-135">Si se realiza correctamente, este método devuelve 200 Ok, con los datos de exposición en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="61586-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="61586-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61586-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="61586-137">Solicitud</span><span class="sxs-lookup"><span data-stu-id="61586-137">Request</span></span>

<span data-ttu-id="61586-138">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="61586-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="61586-139">Respuesta</span><span class="sxs-lookup"><span data-stu-id="61586-139">Response</span></span>

<span data-ttu-id="61586-140">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="61586-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="61586-141">La lista de respuestas que se muestra aquí puede truncarse por brevedad.</span><span class="sxs-lookup"><span data-stu-id="61586-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="61586-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61586-142">See also</span></span>

- [<span data-ttu-id="61586-143">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="61586-143">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="61586-144">Puntuación de & vulnerabilidad de amenazas</span><span class="sxs-lookup"><span data-stu-id="61586-144">Threat & Vulnerability exposure score</span></span>](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
