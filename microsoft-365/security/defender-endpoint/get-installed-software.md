---
title: Obtener software instalado
description: Recupera una colección de software instalado relacionado con un identificador de dispositivo determinado.
keywords: apis, api de gráficos, api admitidas, obtener, lista, archivo, información, inventario de software, software instalado por dispositivo, api de & administración de vulnerabilidades amenazas, API de Tvm de Microsoft Defender para Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e13e2072ad1c18f3c6bf1abbbe95c95bb519dc3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841119"
---
# <a name="get-installed-software"></a><span data-ttu-id="13035-104">Obtener software instalado</span><span class="sxs-lookup"><span data-stu-id="13035-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="13035-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="13035-105">**Applies to:**</span></span>
- [<span data-ttu-id="13035-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="13035-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="13035-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13035-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="13035-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="13035-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="13035-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="13035-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="13035-110">Recupera una colección de software instalado relacionado con un identificador de dispositivo determinado.</span><span class="sxs-lookup"><span data-stu-id="13035-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="13035-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="13035-111">Permissions</span></span>
<span data-ttu-id="13035-112">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="13035-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="13035-113">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="13035-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="13035-114">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="13035-114">Permission type</span></span> |   <span data-ttu-id="13035-115">Permiso</span><span class="sxs-lookup"><span data-stu-id="13035-115">Permission</span></span>  |   <span data-ttu-id="13035-116">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="13035-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="13035-117">Aplicación</span><span class="sxs-lookup"><span data-stu-id="13035-117">Application</span></span> |<span data-ttu-id="13035-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="13035-118">Software.Read.All</span></span> |    <span data-ttu-id="13035-119">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="13035-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="13035-120">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="13035-120">Delegated (work or school account)</span></span> | <span data-ttu-id="13035-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="13035-121">Software.Read</span></span> |    <span data-ttu-id="13035-122">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="13035-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="13035-123">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="13035-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="13035-124">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="13035-124">Request headers</span></span>

<span data-ttu-id="13035-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="13035-125">Name</span></span> | <span data-ttu-id="13035-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="13035-126">Type</span></span> | <span data-ttu-id="13035-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="13035-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="13035-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="13035-128">Authorization</span></span> | <span data-ttu-id="13035-129">Cadena</span><span class="sxs-lookup"><span data-stu-id="13035-129">String</span></span> | <span data-ttu-id="13035-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="13035-130">Bearer {token}.</span></span> <span data-ttu-id="13035-131">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="13035-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="13035-132">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="13035-132">Request body</span></span>
<span data-ttu-id="13035-133">En blanco</span><span class="sxs-lookup"><span data-stu-id="13035-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="13035-134">Respuesta</span><span class="sxs-lookup"><span data-stu-id="13035-134">Response</span></span>
<span data-ttu-id="13035-135">Si se realiza correctamente, este método devuelve 200 Ok con la información de software instalada en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="13035-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="13035-136">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="13035-136">Example</span></span>

<span data-ttu-id="13035-137">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="13035-137">**Request**</span></span>

<span data-ttu-id="13035-138">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="13035-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="13035-139">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="13035-139">**Response**</span></span>

<span data-ttu-id="13035-140">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="13035-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="13035-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13035-141">See also</span></span>

- [<span data-ttu-id="13035-142">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="13035-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="13035-143">Inventario & de software de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="13035-143">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
