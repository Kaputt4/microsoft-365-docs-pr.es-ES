---
title: Obtener puntuación segura del dispositivo
description: Recupera la puntuación segura del dispositivo de la organización.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 921334c937e3f211b032a5d24d4244d9a6fb3d61
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166883"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="222d6-104">Obtener puntuación segura del dispositivo</span><span class="sxs-lookup"><span data-stu-id="222d6-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="222d6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="222d6-105">**Applies to:**</span></span>
- [<span data-ttu-id="222d6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="222d6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="222d6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="222d6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="222d6-108">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="222d6-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="222d6-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="222d6-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="222d6-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="222d6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="222d6-111">Recupera la [puntuación segura de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md).</span><span class="sxs-lookup"><span data-stu-id="222d6-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="222d6-112">Una puntuación segura de Microsoft más alta para dispositivos significa que los puntos de conexión son más resistentes frente a los ataques de amenazas de ciberseguridad.</span><span class="sxs-lookup"><span data-stu-id="222d6-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="222d6-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="222d6-113">Permissions</span></span>

<span data-ttu-id="222d6-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="222d6-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="222d6-115">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="222d6-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="222d6-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="222d6-116">Permission type</span></span> |   <span data-ttu-id="222d6-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="222d6-117">Permission</span></span>  |   <span data-ttu-id="222d6-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="222d6-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="222d6-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="222d6-119">Application</span></span> |   <span data-ttu-id="222d6-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="222d6-120">Score.Read.Alll</span></span> |   <span data-ttu-id="222d6-121">'Leer puntuación de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="222d6-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="222d6-122">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="222d6-122">Delegated (work or school account)</span></span> | <span data-ttu-id="222d6-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="222d6-123">Score.Read</span></span> | <span data-ttu-id="222d6-124">'Leer puntuación de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="222d6-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="222d6-125">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="222d6-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="222d6-126">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="222d6-126">Request headers</span></span>

<span data-ttu-id="222d6-127">Nombre</span><span class="sxs-lookup"><span data-stu-id="222d6-127">Name</span></span> | <span data-ttu-id="222d6-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="222d6-128">Type</span></span> | <span data-ttu-id="222d6-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="222d6-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="222d6-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="222d6-130">Authorization</span></span> | <span data-ttu-id="222d6-131">Cadena</span><span class="sxs-lookup"><span data-stu-id="222d6-131">String</span></span> | <span data-ttu-id="222d6-132">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="222d6-132">Bearer {token}.</span></span> <span data-ttu-id="222d6-133">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="222d6-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="222d6-134">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="222d6-134">Request body</span></span>

<span data-ttu-id="222d6-135">En blanco</span><span class="sxs-lookup"><span data-stu-id="222d6-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="222d6-136">Respuesta</span><span class="sxs-lookup"><span data-stu-id="222d6-136">Response</span></span>

<span data-ttu-id="222d6-137">Si se realiza correctamente, este método devuelve 200 OK, con los datos de puntuación seguros del dispositivo en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="222d6-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="222d6-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="222d6-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="222d6-139">Solicitud</span><span class="sxs-lookup"><span data-stu-id="222d6-139">Request</span></span>

<span data-ttu-id="222d6-140">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="222d6-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="222d6-141">Respuesta</span><span class="sxs-lookup"><span data-stu-id="222d6-141">Response</span></span>

<span data-ttu-id="222d6-142">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="222d6-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="222d6-143">La lista de respuestas que se muestra aquí puede truncarse por brevedad.</span><span class="sxs-lookup"><span data-stu-id="222d6-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="222d6-144">Ver también</span><span class="sxs-lookup"><span data-stu-id="222d6-144">See also</span></span>

- [<span data-ttu-id="222d6-145">Consultas de OData con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="222d6-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
