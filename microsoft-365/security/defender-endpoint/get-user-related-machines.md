---
title: Obtener api de máquinas relacionadas con el usuario
description: Obtenga información sobre cómo usar la API Obtener máquinas relacionadas con el usuario para recuperar una colección de dispositivos relacionados con un identificador de usuario en Microsoft Defender para endpoint.
keywords: api, api de gráfico, api admitidas, obtener, usuario, alertas relacionadas con el usuario
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
ms.openlocfilehash: ead0558bfff90c29ec8717fbb39876afda5c42af
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229460"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="e2012-104">Obtener api de máquinas relacionadas con el usuario</span><span class="sxs-lookup"><span data-stu-id="e2012-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2012-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e2012-105">**Applies to:**</span></span>
- [<span data-ttu-id="e2012-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e2012-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e2012-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2012-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e2012-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e2012-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e2012-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e2012-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="e2012-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="e2012-110">API description</span></span>
<span data-ttu-id="e2012-111">Recupera una colección de dispositivos relacionados con un identificador de usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="e2012-111">Retrieves a collection of devices related to a given user ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="e2012-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="e2012-112">Limitations</span></span>

<span data-ttu-id="e2012-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="e2012-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="e2012-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="e2012-114">Permissions</span></span>

<span data-ttu-id="e2012-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="e2012-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e2012-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e2012-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e2012-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="e2012-117">Permission type</span></span> |<span data-ttu-id="e2012-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="e2012-118">Permission</span></span>|<span data-ttu-id="e2012-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="e2012-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e2012-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="e2012-120">Application</span></span> |<span data-ttu-id="e2012-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="e2012-121">Machine.Read.All</span></span>|<span data-ttu-id="e2012-122">'Leer todos los perfiles de máquina'</span><span class="sxs-lookup"><span data-stu-id="e2012-122">'Read all machine profiles'</span></span>
<span data-ttu-id="e2012-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="e2012-123">Application</span></span> |<span data-ttu-id="e2012-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e2012-124">Machine.ReadWrite.All</span></span> |<span data-ttu-id="e2012-125">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="e2012-125">'Read and write all machine information'</span></span>
<span data-ttu-id="e2012-126">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="e2012-126">Delegated (work or school account)</span></span> | <span data-ttu-id="e2012-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="e2012-127">Machine.Read</span></span> | <span data-ttu-id="e2012-128">'Leer información de máquina'</span><span class="sxs-lookup"><span data-stu-id="e2012-128">'Read machine information'</span></span>
<span data-ttu-id="e2012-129">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="e2012-129">Delegated (work or school account)</span></span> | <span data-ttu-id="e2012-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e2012-130">Machine.ReadWrite</span></span> | <span data-ttu-id="e2012-131">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="e2012-131">'Read and write machine information'</span></span>

> [!NOTE]
> <span data-ttu-id="e2012-132">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="e2012-132">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="e2012-133">El usuario debe tener al menos el siguiente permiso de función: "Ver datos".</span><span class="sxs-lookup"><span data-stu-id="e2012-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="e2012-134">Para obtener más información, vea [Create and manage roles](user-roles.md))</span><span class="sxs-lookup"><span data-stu-id="e2012-134">For more information, see [Create and manage roles](user-roles.md))</span></span>
> - <span data-ttu-id="e2012-135">La respuesta incluirá solo los dispositivos a los que el usuario pueda tener acceso, en función de la configuración del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e2012-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="e2012-136">Para obtener más información, consulta [Crear y administrar grupos de dispositivos.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="e2012-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="e2012-137">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="e2012-137">HTTP request</span></span>

```http
GET /api/users/{id}/machines
```

<span data-ttu-id="e2012-138">**El identificador no es el UPN completo, sino solo el nombre de usuario. (por ejemplo, para recuperar máquinas para user1@contoso.com usar /api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="e2012-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="e2012-139">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="e2012-139">Request headers</span></span>

<span data-ttu-id="e2012-140">Nombre</span><span class="sxs-lookup"><span data-stu-id="e2012-140">Name</span></span> | <span data-ttu-id="e2012-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="e2012-141">Type</span></span> | <span data-ttu-id="e2012-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2012-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="e2012-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="e2012-143">Authorization</span></span> | <span data-ttu-id="e2012-144">Cadena</span><span class="sxs-lookup"><span data-stu-id="e2012-144">String</span></span> | <span data-ttu-id="e2012-145">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="e2012-145">Bearer {token}.</span></span> <span data-ttu-id="e2012-146">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="e2012-146">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e2012-147">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="e2012-147">Request body</span></span>

<span data-ttu-id="e2012-148">En blanco</span><span class="sxs-lookup"><span data-stu-id="e2012-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e2012-149">Respuesta</span><span class="sxs-lookup"><span data-stu-id="e2012-149">Response</span></span>

<span data-ttu-id="e2012-150">Si se realiza correctamente y el usuario existe: 200 Aceptar con la lista de [entidades](machine.md) de máquina en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="e2012-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="e2012-151">Si el usuario no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="e2012-151">If user does not exist - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="e2012-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2012-152">Example</span></span>

### <a name="request"></a><span data-ttu-id="e2012-153">Solicitud</span><span class="sxs-lookup"><span data-stu-id="e2012-153">Request</span></span>

<span data-ttu-id="e2012-154">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e2012-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
