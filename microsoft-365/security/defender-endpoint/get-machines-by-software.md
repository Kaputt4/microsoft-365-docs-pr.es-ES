---
title: Enumerar dispositivos por software
description: Recupera una lista de dispositivos que tienen instalado este software.
keywords: apis, api de gráfico, api admitidas, get, dispositivos de lista, lista de dispositivos, lista de dispositivos por software, api de mdatp tvm
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
ms.openlocfilehash: 78cccee6380f0c403aab21eac4f07b64b8f8d510
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200394"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="0f21c-104">Enumerar dispositivos por software</span><span class="sxs-lookup"><span data-stu-id="0f21c-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0f21c-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0f21c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0f21c-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="0f21c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0f21c-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0f21c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="0f21c-108">Recupera una lista de referencias de dispositivo que tiene instalado este software.</span><span class="sxs-lookup"><span data-stu-id="0f21c-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="0f21c-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="0f21c-109">Permissions</span></span>
<span data-ttu-id="0f21c-110">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="0f21c-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0f21c-111">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0f21c-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="0f21c-112">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="0f21c-112">Permission type</span></span> |   <span data-ttu-id="0f21c-113">Permiso</span><span class="sxs-lookup"><span data-stu-id="0f21c-113">Permission</span></span>  |   <span data-ttu-id="0f21c-114">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="0f21c-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0f21c-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="0f21c-115">Application</span></span> | <span data-ttu-id="0f21c-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="0f21c-116">Software.Read.All</span></span> | <span data-ttu-id="0f21c-117">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="0f21c-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="0f21c-118">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="0f21c-118">Delegated (work or school account)</span></span> | <span data-ttu-id="0f21c-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="0f21c-119">Software.Read</span></span> | <span data-ttu-id="0f21c-120">'Leer información de software de administración de amenazas y vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="0f21c-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="0f21c-121">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="0f21c-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="0f21c-122">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="0f21c-122">Request headers</span></span>

| <span data-ttu-id="0f21c-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="0f21c-123">Name</span></span>        | <span data-ttu-id="0f21c-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="0f21c-124">Type</span></span> | <span data-ttu-id="0f21c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f21c-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="0f21c-126">Authorization</span><span class="sxs-lookup"><span data-stu-id="0f21c-126">Authorization</span></span> | <span data-ttu-id="0f21c-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="0f21c-127">String</span></span> | <span data-ttu-id="0f21c-128">Portador {token}. **Obligatorio**.</span><span class="sxs-lookup"><span data-stu-id="0f21c-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="0f21c-129">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="0f21c-129">Request body</span></span>
<span data-ttu-id="0f21c-130">En blanco</span><span class="sxs-lookup"><span data-stu-id="0f21c-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0f21c-131">Respuesta</span><span class="sxs-lookup"><span data-stu-id="0f21c-131">Response</span></span>
<span data-ttu-id="0f21c-132">Si se realiza correctamente, este método devuelve 200 OK y una lista de dispositivos con el software instalado en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="0f21c-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="0f21c-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f21c-133">Example</span></span>

<span data-ttu-id="0f21c-134">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="0f21c-134">**Request**</span></span>

<span data-ttu-id="0f21c-135">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="0f21c-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="0f21c-136">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="0f21c-136">**Response**</span></span>

<span data-ttu-id="0f21c-137">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="0f21c-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="0f21c-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0f21c-138">Related topics</span></span>
- [<span data-ttu-id="0f21c-139">Administración de vulnerabilidades basada & riesgos</span><span class="sxs-lookup"><span data-stu-id="0f21c-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="0f21c-140">Inventario & de software de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="0f21c-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
