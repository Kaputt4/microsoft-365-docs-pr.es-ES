---
title: Obtener API de máquinas relacionadas con archivos
description: Obtenga información sobre cómo usar la API Obtener máquinas relacionadas con archivos para obtener una colección de máquinas relacionadas con un hash de archivo en Microsoft Defender para endpoint.
keywords: api, api de gráfico, api admitidas, get, dispositivos, hash
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
ms.openlocfilehash: 051bdad362e142446d248e90fad608fe5c0f016f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166816"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="d278a-104">Obtener API de máquinas relacionadas con archivos</span><span class="sxs-lookup"><span data-stu-id="d278a-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d278a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d278a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d278a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d278a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d278a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d278a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d278a-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="d278a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d278a-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d278a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d278a-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="d278a-110">API description</span></span>
<span data-ttu-id="d278a-111">Recupera una colección de [máquinas relacionadas](machine.md) con un hash de archivo determinado.</span><span class="sxs-lookup"><span data-stu-id="d278a-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="d278a-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="d278a-112">Limitations</span></span>
1. <span data-ttu-id="d278a-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="d278a-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d278a-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="d278a-114">Permissions</span></span>
<span data-ttu-id="d278a-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="d278a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d278a-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d278a-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d278a-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="d278a-117">Permission type</span></span> |   <span data-ttu-id="d278a-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="d278a-118">Permission</span></span>  |   <span data-ttu-id="d278a-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="d278a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d278a-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d278a-120">Application</span></span> |   <span data-ttu-id="d278a-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="d278a-121">Machine.Read.All</span></span> |  <span data-ttu-id="d278a-122">'Leer todos los perfiles de máquina'</span><span class="sxs-lookup"><span data-stu-id="d278a-122">'Read all machine profiles'</span></span>
<span data-ttu-id="d278a-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d278a-123">Application</span></span> |   <span data-ttu-id="d278a-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d278a-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="d278a-125">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="d278a-125">'Read and write all machine information'</span></span>
<span data-ttu-id="d278a-126">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="d278a-126">Delegated (work or school account)</span></span> | <span data-ttu-id="d278a-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="d278a-127">Machine.Read</span></span> | <span data-ttu-id="d278a-128">'Leer información de máquina'</span><span class="sxs-lookup"><span data-stu-id="d278a-128">'Read machine information'</span></span>
<span data-ttu-id="d278a-129">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="d278a-129">Delegated (work or school account)</span></span> | <span data-ttu-id="d278a-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d278a-130">Machine.ReadWrite</span></span> | <span data-ttu-id="d278a-131">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="d278a-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="d278a-132">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="d278a-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d278a-133">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d278a-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d278a-134">La respuesta incluirá solo dispositivos a los que el usuario tenga acceso, en función de la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d278a-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d278a-135">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="d278a-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="d278a-136">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="d278a-136">Request headers</span></span>

<span data-ttu-id="d278a-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="d278a-137">Name</span></span> | <span data-ttu-id="d278a-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="d278a-138">Type</span></span> | <span data-ttu-id="d278a-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="d278a-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="d278a-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="d278a-140">Authorization</span></span> | <span data-ttu-id="d278a-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="d278a-141">String</span></span> | <span data-ttu-id="d278a-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="d278a-142">Bearer {token}.</span></span> <span data-ttu-id="d278a-143">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d278a-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d278a-144">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="d278a-144">Request body</span></span>
<span data-ttu-id="d278a-145">En blanco</span><span class="sxs-lookup"><span data-stu-id="d278a-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d278a-146">Respuesta</span><span class="sxs-lookup"><span data-stu-id="d278a-146">Response</span></span>
<span data-ttu-id="d278a-147">Si se realiza correctamente y el archivo existe: 200 Aceptar con la lista [de](machine.md) entidades de máquina en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="d278a-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="d278a-148">Si el archivo no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="d278a-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="d278a-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d278a-149">Example</span></span>

<span data-ttu-id="d278a-150">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="d278a-150">**Request**</span></span>

<span data-ttu-id="d278a-151">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d278a-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
