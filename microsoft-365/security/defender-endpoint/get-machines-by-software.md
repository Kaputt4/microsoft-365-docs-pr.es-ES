---
title: Enumerar dispositivos por software
description: Recupera una lista de dispositivos que tienen instalado este software.
keywords: apis, api de gráficos, api admitidas, get, dispositivos de lista, lista de dispositivos, lista de dispositivos por software, Api de Microsoft Defender para Endpoint tvm
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 8312818fe06b5a25ae32bf1f9585a51fe8848de6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845383"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="6443b-104">Enumerar dispositivos por software</span><span class="sxs-lookup"><span data-stu-id="6443b-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6443b-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6443b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6443b-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="6443b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6443b-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6443b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6443b-108">Recupera una lista de referencias de dispositivo que tiene instalado este software.</span><span class="sxs-lookup"><span data-stu-id="6443b-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="6443b-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="6443b-109">Permissions</span></span>
<span data-ttu-id="6443b-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="6443b-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6443b-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6443b-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="6443b-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="6443b-112">Permission type</span></span> |   <span data-ttu-id="6443b-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="6443b-113">Permission</span></span>  |   <span data-ttu-id="6443b-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="6443b-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6443b-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="6443b-115">Application</span></span> | <span data-ttu-id="6443b-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="6443b-116">Software.Read.All</span></span> | <span data-ttu-id="6443b-117">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="6443b-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="6443b-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="6443b-118">Delegated (work or school account)</span></span> | <span data-ttu-id="6443b-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="6443b-119">Software.Read</span></span> | <span data-ttu-id="6443b-120">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="6443b-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="6443b-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="6443b-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="6443b-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="6443b-122">Request headers</span></span>

| <span data-ttu-id="6443b-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="6443b-123">Name</span></span>        | <span data-ttu-id="6443b-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="6443b-124">Type</span></span> | <span data-ttu-id="6443b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="6443b-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="6443b-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="6443b-126">Authorization</span></span> | <span data-ttu-id="6443b-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="6443b-127">String</span></span> | <span data-ttu-id="6443b-128">Portador {token}. **Obligatorio**.</span><span class="sxs-lookup"><span data-stu-id="6443b-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="6443b-129">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="6443b-129">Request body</span></span>
<span data-ttu-id="6443b-130">En blanco</span><span class="sxs-lookup"><span data-stu-id="6443b-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6443b-131">Respuesta</span><span class="sxs-lookup"><span data-stu-id="6443b-131">Response</span></span>
<span data-ttu-id="6443b-132">Si se realiza correctamente, este método devuelve 200 OK y una lista de dispositivos con el software instalado en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="6443b-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="6443b-133">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6443b-133">Example</span></span>

<span data-ttu-id="6443b-134">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="6443b-134">**Request**</span></span>

<span data-ttu-id="6443b-135">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6443b-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="6443b-136">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="6443b-136">**Response**</span></span>

<span data-ttu-id="6443b-137">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="6443b-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="6443b-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6443b-138">Related topics</span></span>
- [<span data-ttu-id="6443b-139">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="6443b-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="6443b-140">Inventario & de software de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="6443b-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
