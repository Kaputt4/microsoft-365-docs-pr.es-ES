---
title: Obtener puntuación segura para dispositivos
description: Recupera la puntuación segura del dispositivo de la organización.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
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
ms.technology: mde
ms.openlocfilehash: db4682d0d2fccd7504eb46d9099a9783408cfb73
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570941"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="eaec5-104">Obtener puntuación segura para dispositivos</span><span class="sxs-lookup"><span data-stu-id="eaec5-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eaec5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="eaec5-105">**Applies to:**</span></span>
- [<span data-ttu-id="eaec5-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="eaec5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eaec5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eaec5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="eaec5-108">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="eaec5-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="eaec5-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="eaec5-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eaec5-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="eaec5-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="eaec5-111">Recupera la [puntuación segura de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md).</span><span class="sxs-lookup"><span data-stu-id="eaec5-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="eaec5-112">Una puntuación segura de Microsoft más alta para dispositivos significa que los puntos de conexión son más resistentes frente a los ataques de amenazas de ciberseguridad.</span><span class="sxs-lookup"><span data-stu-id="eaec5-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="eaec5-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="eaec5-113">Permissions</span></span>

<span data-ttu-id="eaec5-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="eaec5-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="eaec5-115">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="eaec5-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="eaec5-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="eaec5-116">Permission type</span></span> |   <span data-ttu-id="eaec5-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="eaec5-117">Permission</span></span>  |   <span data-ttu-id="eaec5-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="eaec5-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="eaec5-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="eaec5-119">Application</span></span> |   <span data-ttu-id="eaec5-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="eaec5-120">Score.Read.Alll</span></span> |   <span data-ttu-id="eaec5-121">'Leer puntuación de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="eaec5-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="eaec5-122">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="eaec5-122">Delegated (work or school account)</span></span> | <span data-ttu-id="eaec5-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="eaec5-123">Score.Read</span></span> | <span data-ttu-id="eaec5-124">'Leer puntuación de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="eaec5-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="eaec5-125">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="eaec5-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="eaec5-126">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="eaec5-126">Request headers</span></span>

<span data-ttu-id="eaec5-127">Nombre</span><span class="sxs-lookup"><span data-stu-id="eaec5-127">Name</span></span> | <span data-ttu-id="eaec5-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="eaec5-128">Type</span></span> | <span data-ttu-id="eaec5-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="eaec5-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="eaec5-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="eaec5-130">Authorization</span></span> | <span data-ttu-id="eaec5-131">Cadena</span><span class="sxs-lookup"><span data-stu-id="eaec5-131">String</span></span> | <span data-ttu-id="eaec5-132">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="eaec5-132">Bearer {token}.</span></span> <span data-ttu-id="eaec5-133">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="eaec5-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="eaec5-134">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="eaec5-134">Request body</span></span>

<span data-ttu-id="eaec5-135">En blanco</span><span class="sxs-lookup"><span data-stu-id="eaec5-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="eaec5-136">Respuesta</span><span class="sxs-lookup"><span data-stu-id="eaec5-136">Response</span></span>

<span data-ttu-id="eaec5-137">Si se realiza correctamente, este método devuelve 200 OK, con los datos de puntuación seguros del dispositivo en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="eaec5-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="eaec5-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eaec5-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="eaec5-139">Solicitud</span><span class="sxs-lookup"><span data-stu-id="eaec5-139">Request</span></span>

<span data-ttu-id="eaec5-140">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="eaec5-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="eaec5-141">Respuesta</span><span class="sxs-lookup"><span data-stu-id="eaec5-141">Response</span></span>

<span data-ttu-id="eaec5-142">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="eaec5-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="eaec5-143">La lista de respuestas que se muestra aquí puede truncarse por brevedad.</span><span class="sxs-lookup"><span data-stu-id="eaec5-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="eaec5-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eaec5-144">See also</span></span>

- [<span data-ttu-id="eaec5-145">Consultas de OData con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="eaec5-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
