---
title: Obtener api de alertas relacionadas con archivos
description: Obtenga información sobre cómo usar la API Obtener alertas relacionadas con archivos para obtener una colección de alertas relacionadas con un hash de archivo determinado en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, file, hash
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
ms.openlocfilehash: b77946f4bfdb793ffbfdf102a7221df083fb92eb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770306"
---
# <a name="get-file-related-alerts-api"></a><span data-ttu-id="814ee-104">Obtener api de alertas relacionadas con archivos</span><span class="sxs-lookup"><span data-stu-id="814ee-104">Get file-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="814ee-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="814ee-105">**Applies to:**</span></span>
- [<span data-ttu-id="814ee-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="814ee-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="814ee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="814ee-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="814ee-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="814ee-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="814ee-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="814ee-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="814ee-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="814ee-110">API description</span></span>
<span data-ttu-id="814ee-111">Recupera una colección de alertas relacionadas con un hash de archivo determinado.</span><span class="sxs-lookup"><span data-stu-id="814ee-111">Retrieves a collection of alerts related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="814ee-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="814ee-112">Limitations</span></span>
1. <span data-ttu-id="814ee-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="814ee-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="814ee-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="814ee-114">Permissions</span></span>
<span data-ttu-id="814ee-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="814ee-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="814ee-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="814ee-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="814ee-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="814ee-117">Permission type</span></span> |   <span data-ttu-id="814ee-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="814ee-118">Permission</span></span>  |   <span data-ttu-id="814ee-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="814ee-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="814ee-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="814ee-120">Application</span></span> |   <span data-ttu-id="814ee-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="814ee-121">Alert.Read.All</span></span> |    <span data-ttu-id="814ee-122">'Leer todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="814ee-122">'Read all alerts'</span></span>
<span data-ttu-id="814ee-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="814ee-123">Application</span></span> |   <span data-ttu-id="814ee-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="814ee-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="814ee-125">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="814ee-125">'Read and write all alerts'</span></span>
<span data-ttu-id="814ee-126">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="814ee-126">Delegated (work or school account)</span></span> | <span data-ttu-id="814ee-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="814ee-127">Alert.Read</span></span> | <span data-ttu-id="814ee-128">'Leer alertas'</span><span class="sxs-lookup"><span data-stu-id="814ee-128">'Read alerts'</span></span>
<span data-ttu-id="814ee-129">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="814ee-129">Delegated (work or school account)</span></span> | <span data-ttu-id="814ee-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="814ee-130">Alert.ReadWrite</span></span> | <span data-ttu-id="814ee-131">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="814ee-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="814ee-132">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="814ee-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="814ee-133">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="814ee-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="814ee-134">La respuesta incluirá solo alertas, asociadas con dispositivos, a las que el usuario tiene acceso, según la configuración del grupo de dispositivos (vea [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="814ee-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="814ee-135">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="814ee-135">HTTP request</span></span>
```
GET /api/files/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="814ee-136">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="814ee-136">Request headers</span></span>

<span data-ttu-id="814ee-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="814ee-137">Name</span></span> | <span data-ttu-id="814ee-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="814ee-138">Type</span></span> | <span data-ttu-id="814ee-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="814ee-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="814ee-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="814ee-140">Authorization</span></span> | <span data-ttu-id="814ee-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="814ee-141">String</span></span> | <span data-ttu-id="814ee-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="814ee-142">Bearer {token}.</span></span> <span data-ttu-id="814ee-143">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="814ee-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="814ee-144">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="814ee-144">Request body</span></span>
<span data-ttu-id="814ee-145">En blanco</span><span class="sxs-lookup"><span data-stu-id="814ee-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="814ee-146">Respuesta</span><span class="sxs-lookup"><span data-stu-id="814ee-146">Response</span></span>
<span data-ttu-id="814ee-147">Si se realiza correctamente y el archivo existe: 200 Aceptar con la lista [de](alerts.md) entidades de alerta en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="814ee-147">If successful and file exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="814ee-148">Si el archivo no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="814ee-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="814ee-149">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="814ee-149">Example</span></span>

<span data-ttu-id="814ee-150">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="814ee-150">**Request**</span></span>

<span data-ttu-id="814ee-151">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="814ee-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/6532ec91d513acc05f43ee0aa3002599729fd3e1/alerts
```
