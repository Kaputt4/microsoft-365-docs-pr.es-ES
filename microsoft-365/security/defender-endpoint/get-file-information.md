---
title: OBTENER API de información de archivos
description: Obtenga información sobre cómo usar la API Obtener información de archivos para obtener un archivo mediante el identificador Sha1, Sha256 o MD5 en Microsoft Defender para endpoint.
keywords: apis, graph api, apis admitidas, get, file, information, sha1, sha256, md5
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b7877fb2d9b616b487d23befd0f0af35ce2c0753
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770301"
---
# <a name="get-file-information-api"></a><span data-ttu-id="e6aca-104">OBTENER API de información de archivos</span><span class="sxs-lookup"><span data-stu-id="e6aca-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e6aca-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e6aca-105">**Applies to:**</span></span>
- [<span data-ttu-id="e6aca-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e6aca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e6aca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6aca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e6aca-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="e6aca-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e6aca-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e6aca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e6aca-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="e6aca-110">API description</span></span>
<span data-ttu-id="e6aca-111">Recupera un [archivo por](files.md) identificador Sha1 o Sha256</span><span class="sxs-lookup"><span data-stu-id="e6aca-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="e6aca-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="e6aca-112">Limitations</span></span>
1. <span data-ttu-id="e6aca-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="e6aca-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e6aca-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="e6aca-114">Permissions</span></span>
<span data-ttu-id="e6aca-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="e6aca-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e6aca-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e6aca-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e6aca-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="e6aca-117">Permission type</span></span> |   <span data-ttu-id="e6aca-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="e6aca-118">Permission</span></span>  |   <span data-ttu-id="e6aca-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="e6aca-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e6aca-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="e6aca-120">Application</span></span> |   <span data-ttu-id="e6aca-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="e6aca-121">File.Read.All</span></span> | <span data-ttu-id="e6aca-122">'Leer todos los perfiles de archivo'</span><span class="sxs-lookup"><span data-stu-id="e6aca-122">'Read all file profiles'</span></span>
<span data-ttu-id="e6aca-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="e6aca-123">Delegated (work or school account)</span></span> | <span data-ttu-id="e6aca-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="e6aca-124">File.Read.All</span></span> |    <span data-ttu-id="e6aca-125">'Leer todos los perfiles de archivo'</span><span class="sxs-lookup"><span data-stu-id="e6aca-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="e6aca-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="e6aca-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e6aca-127">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="e6aca-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e6aca-128">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="e6aca-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="e6aca-129">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="e6aca-129">Request headers</span></span>

<span data-ttu-id="e6aca-130">Nombre</span><span class="sxs-lookup"><span data-stu-id="e6aca-130">Name</span></span> | <span data-ttu-id="e6aca-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6aca-131">Type</span></span> | <span data-ttu-id="e6aca-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6aca-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="e6aca-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="e6aca-133">Authorization</span></span> | <span data-ttu-id="e6aca-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="e6aca-134">String</span></span> | <span data-ttu-id="e6aca-135">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="e6aca-135">Bearer {token}.</span></span> <span data-ttu-id="e6aca-136">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="e6aca-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e6aca-137">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="e6aca-137">Request body</span></span>
<span data-ttu-id="e6aca-138">En blanco</span><span class="sxs-lookup"><span data-stu-id="e6aca-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e6aca-139">Respuesta</span><span class="sxs-lookup"><span data-stu-id="e6aca-139">Response</span></span>
<span data-ttu-id="e6aca-140">Si se realiza correctamente y el archivo existe: 200 Aceptar con la [entidad de](files.md) archivo en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="e6aca-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="e6aca-141">Si el archivo no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="e6aca-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="e6aca-142">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e6aca-142">Example</span></span>

<span data-ttu-id="e6aca-143">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="e6aca-143">**Request**</span></span>

<span data-ttu-id="e6aca-144">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e6aca-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="e6aca-145">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="e6aca-145">**Response**</span></span>

<span data-ttu-id="e6aca-146">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e6aca-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
