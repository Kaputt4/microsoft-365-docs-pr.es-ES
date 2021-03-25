---
title: Obtener información de archivos relacionados con alertas
description: Recupera todos los archivos relacionados con una alerta específica con Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, obtener información de alerta, información de alertas, archivos relacionados
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 31cbbaee9a97c061b61cc9f7ecc71bb759aea081
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166991"
---
# <a name="get-alert-related-files-information-api"></a><span data-ttu-id="d3b5f-104">Obtener API de información de archivos relacionados con alertas</span><span class="sxs-lookup"><span data-stu-id="d3b5f-104">Get alert related files information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d3b5f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d3b5f-105">**Applies to:**</span></span>
- [<span data-ttu-id="d3b5f-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d3b5f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d3b5f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3b5f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
 
> <span data-ttu-id="d3b5f-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="d3b5f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d3b5f-109">Regístrate para la versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-109">Sign up for free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d3b5f-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="d3b5f-110">API description</span></span>
<span data-ttu-id="d3b5f-111">Recupera todos los archivos relacionados con una alerta específica.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-111">Retrieves all files related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="d3b5f-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="d3b5f-112">Limitations</span></span>
1. <span data-ttu-id="d3b5f-113">Puede consultar las alertas actualizadas por última vez de acuerdo con el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="d3b5f-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d3b5f-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="d3b5f-115">Permissions</span></span>
<span data-ttu-id="d3b5f-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d3b5f-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d3b5f-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d3b5f-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="d3b5f-118">Permission type</span></span> | <span data-ttu-id="d3b5f-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="d3b5f-119">Permission</span></span> | <span data-ttu-id="d3b5f-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="d3b5f-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d3b5f-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d3b5f-121">Application</span></span> | <span data-ttu-id="d3b5f-122">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="d3b5f-122">File.Read.All</span></span> | <span data-ttu-id="d3b5f-123">'Leer perfiles de archivo'</span><span class="sxs-lookup"><span data-stu-id="d3b5f-123">'Read file profiles'</span></span>
<span data-ttu-id="d3b5f-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="d3b5f-124">Delegated (work or school account)</span></span> | <span data-ttu-id="d3b5f-125">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="d3b5f-125">File.Read.All</span></span> | <span data-ttu-id="d3b5f-126">'Leer perfiles de archivo'</span><span class="sxs-lookup"><span data-stu-id="d3b5f-126">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="d3b5f-127">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="d3b5f-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d3b5f-128">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d3b5f-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d3b5f-129">El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d3b5f-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d3b5f-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="d3b5f-130">HTTP request</span></span>
```
GET /api/alerts/{id}/files
```

## <a name="request-headers"></a><span data-ttu-id="d3b5f-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="d3b5f-131">Request headers</span></span>

<span data-ttu-id="d3b5f-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="d3b5f-132">Name</span></span> | <span data-ttu-id="d3b5f-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="d3b5f-133">Type</span></span> | <span data-ttu-id="d3b5f-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3b5f-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="d3b5f-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="d3b5f-135">Authorization</span></span> | <span data-ttu-id="d3b5f-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="d3b5f-136">String</span></span> | <span data-ttu-id="d3b5f-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-137">Bearer {token}.</span></span> <span data-ttu-id="d3b5f-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d3b5f-139">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="d3b5f-139">Request body</span></span>
<span data-ttu-id="d3b5f-140">En blanco</span><span class="sxs-lookup"><span data-stu-id="d3b5f-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d3b5f-141">Respuesta</span><span class="sxs-lookup"><span data-stu-id="d3b5f-141">Response</span></span>
<span data-ttu-id="d3b5f-142">Si se realiza correctamente y existen alertas y archivos: 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-142">If successful and alert and files exist - 200 OK.</span></span> <span data-ttu-id="d3b5f-143">Si no se encuentra la alerta: 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="d3b5f-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3b5f-144">Example</span></span>

<span data-ttu-id="d3b5f-145">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="d3b5f-145">**Request**</span></span>

<span data-ttu-id="d3b5f-146">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/files
```

<span data-ttu-id="d3b5f-147">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="d3b5f-147">**Response**</span></span>

<span data-ttu-id="d3b5f-148">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="d3b5f-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files",
    "value": [
        {
            "sha1": "f2a00fd2f2de1be0214b8529f1e9f67096c1aa70",
            "sha256": "dcd71ef5fff4362a9f64cf3f96f14f2b11d6f428f3badbedcb9ff3361e7079aa",
            "md5": "8d5b7cc9a832e21d22503057e1fec8e9",
            "globalPrevalence": 29,
            "globalFirstObserved": "2019-03-23T23:54:06.0135204Z",
            "globalLastObserved": "2019-04-23T00:43:20.0489831Z",
            "size": 113984,
            "fileType": null,
            "isPeFile": true,
            "filePublisher": "Microsoft Corporation",
            "fileProductName": "Microsoft� Windows� Operating System",
            "signer": "Microsoft Corporation",
            "issuer": "Microsoft Code Signing PCA",
            "signerHash": "9dc17888b5cfad98b3cb35c1994e96227f061675",
            "isValidCertificate": true,
            "determinationType": "Unknown",
            "determinationValue": null
        }
        ...
    ]
}
```
