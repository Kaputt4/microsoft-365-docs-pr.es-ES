---
title: Obtener API de máquinas relacionadas con el dominio
description: Obtenga información sobre cómo usar la API Obtener máquinas relacionadas con el dominio para obtener máquinas que se comunicaron con o desde un dominio en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, domain, related, devices
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
ms.openlocfilehash: 3fffb87c486e8b6b89b5e868b96d02dfae496e0b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166880"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="557cf-104">Obtener API de máquinas relacionadas con el dominio</span><span class="sxs-lookup"><span data-stu-id="557cf-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="557cf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="557cf-105">**Applies to:**</span></span>
- [<span data-ttu-id="557cf-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="557cf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="557cf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="557cf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="557cf-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="557cf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="557cf-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="557cf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="557cf-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="557cf-110">API description</span></span>
<span data-ttu-id="557cf-111">Recupera una colección de [máquinas](machine.md) que se han comunicado a o desde una dirección de dominio determinada.</span><span class="sxs-lookup"><span data-stu-id="557cf-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="557cf-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="557cf-112">Limitations</span></span>
1. <span data-ttu-id="557cf-113">Puede consultar en dispositivos actualizados por última vez de acuerdo con el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="557cf-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="557cf-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="557cf-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="557cf-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="557cf-115">Permissions</span></span>
<span data-ttu-id="557cf-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="557cf-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="557cf-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="557cf-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="557cf-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="557cf-118">Permission type</span></span> |   <span data-ttu-id="557cf-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="557cf-119">Permission</span></span>  |   <span data-ttu-id="557cf-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="557cf-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="557cf-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="557cf-121">Application</span></span> |   <span data-ttu-id="557cf-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="557cf-122">Machine.Read.All</span></span> |  <span data-ttu-id="557cf-123">'Leer todos los perfiles de máquina'</span><span class="sxs-lookup"><span data-stu-id="557cf-123">'Read all machine profiles'</span></span>
<span data-ttu-id="557cf-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="557cf-124">Application</span></span> |   <span data-ttu-id="557cf-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="557cf-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="557cf-126">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="557cf-126">'Read and write all machine information'</span></span>
<span data-ttu-id="557cf-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="557cf-127">Delegated (work or school account)</span></span> | <span data-ttu-id="557cf-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="557cf-128">Machine.Read</span></span> | <span data-ttu-id="557cf-129">'Leer información de máquina'</span><span class="sxs-lookup"><span data-stu-id="557cf-129">'Read machine information'</span></span>
<span data-ttu-id="557cf-130">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="557cf-130">Delegated (work or school account)</span></span> | <span data-ttu-id="557cf-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="557cf-131">Machine.ReadWrite</span></span> | <span data-ttu-id="557cf-132">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="557cf-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="557cf-133">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="557cf-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="557cf-134">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="557cf-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="557cf-135">La respuesta incluirá solo dispositivos a los que el usuario pueda tener acceso, en función de la configuración del grupo de dispositivos (consulta [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="557cf-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="557cf-136">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="557cf-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="557cf-137">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="557cf-137">Request headers</span></span>

<span data-ttu-id="557cf-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="557cf-138">Name</span></span> | <span data-ttu-id="557cf-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="557cf-139">Type</span></span> | <span data-ttu-id="557cf-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="557cf-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="557cf-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="557cf-141">Authorization</span></span> | <span data-ttu-id="557cf-142">Cadena</span><span class="sxs-lookup"><span data-stu-id="557cf-142">String</span></span> | <span data-ttu-id="557cf-143">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="557cf-143">Bearer {token}.</span></span> <span data-ttu-id="557cf-144">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="557cf-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="557cf-145">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="557cf-145">Request body</span></span>
<span data-ttu-id="557cf-146">En blanco</span><span class="sxs-lookup"><span data-stu-id="557cf-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="557cf-147">Respuesta</span><span class="sxs-lookup"><span data-stu-id="557cf-147">Response</span></span>
<span data-ttu-id="557cf-148">Si se realiza correctamente y el dominio existe: 200 Aceptar con la lista de [entidades](machine.md) de máquina.</span><span class="sxs-lookup"><span data-stu-id="557cf-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="557cf-149">Si el dominio no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="557cf-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="557cf-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="557cf-150">Example</span></span>

<span data-ttu-id="557cf-151">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="557cf-151">**Request**</span></span>

<span data-ttu-id="557cf-152">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="557cf-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
