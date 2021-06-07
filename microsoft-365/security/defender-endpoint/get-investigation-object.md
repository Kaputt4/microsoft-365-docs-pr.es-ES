---
title: OBTENER API de objetos de investigación
description: Usar esta API para crear llamadas relacionadas con obtener el objeto Investigation
keywords: apis, api de gráfico, api admitidas, objeto Investigation
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
ms.openlocfilehash: 001b8dcf4b0bfd2550f41454fc840602a6e4361f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770138"
---
# <a name="get-investigation-api"></a><span data-ttu-id="6159d-104">Obtener API de investigación</span><span class="sxs-lookup"><span data-stu-id="6159d-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6159d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6159d-105">**Applies to:**</span></span>
- [<span data-ttu-id="6159d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6159d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6159d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6159d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6159d-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="6159d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6159d-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6159d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6159d-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="6159d-110">API description</span></span>
<span data-ttu-id="6159d-111">Recupera investigación [específica por](investigation.md) su identificador.</span><span class="sxs-lookup"><span data-stu-id="6159d-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="6159d-112">Id. puede ser el identificador de investigación o el identificador de alerta desencadenante de la investigación.</span><span class="sxs-lookup"><span data-stu-id="6159d-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="6159d-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="6159d-113">Limitations</span></span>
1. <span data-ttu-id="6159d-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="6159d-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="6159d-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="6159d-115">Permissions</span></span>
<span data-ttu-id="6159d-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="6159d-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6159d-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6159d-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6159d-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="6159d-118">Permission type</span></span> |   <span data-ttu-id="6159d-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="6159d-119">Permission</span></span>  |   <span data-ttu-id="6159d-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="6159d-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6159d-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="6159d-121">Application</span></span> |   <span data-ttu-id="6159d-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="6159d-122">Alert.Read.All</span></span> |    <span data-ttu-id="6159d-123">'Leer todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="6159d-123">'Read all alerts'</span></span>
<span data-ttu-id="6159d-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="6159d-124">Application</span></span> |   <span data-ttu-id="6159d-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="6159d-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="6159d-126">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="6159d-126">'Read and write all alerts'</span></span>
<span data-ttu-id="6159d-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="6159d-127">Delegated (work or school account)</span></span> | <span data-ttu-id="6159d-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="6159d-128">Alert.Read</span></span> | <span data-ttu-id="6159d-129">'Leer alertas'</span><span class="sxs-lookup"><span data-stu-id="6159d-129">'Read alerts'</span></span>
<span data-ttu-id="6159d-130">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="6159d-130">Delegated (work or school account)</span></span> | <span data-ttu-id="6159d-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6159d-131">Alert.ReadWrite</span></span> | <span data-ttu-id="6159d-132">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="6159d-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="6159d-133">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="6159d-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6159d-134">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="6159d-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6159d-135">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="6159d-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="6159d-136">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="6159d-136">Request headers</span></span>

<span data-ttu-id="6159d-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="6159d-137">Name</span></span> | <span data-ttu-id="6159d-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="6159d-138">Type</span></span> | <span data-ttu-id="6159d-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="6159d-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="6159d-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="6159d-140">Authorization</span></span> | <span data-ttu-id="6159d-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="6159d-141">String</span></span> | <span data-ttu-id="6159d-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="6159d-142">Bearer {token}.</span></span> <span data-ttu-id="6159d-143">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="6159d-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6159d-144">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="6159d-144">Request body</span></span>
<span data-ttu-id="6159d-145">En blanco</span><span class="sxs-lookup"><span data-stu-id="6159d-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6159d-146">Respuesta</span><span class="sxs-lookup"><span data-stu-id="6159d-146">Response</span></span>
<span data-ttu-id="6159d-147">Si se realiza correctamente, este método devuelve 200, código de respuesta Ok con una [entidad Investigations.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="6159d-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

