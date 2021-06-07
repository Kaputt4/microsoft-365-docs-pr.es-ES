---
title: Buscar dispositivos por API IP interna
description: Buscar dispositivos vistos con la IP interna solicitada en el intervalo de tiempo de 15 minutos antes y después de una marca de tiempo determinada
keywords: apis, api de gráfico, api admitidas, get, device, IP, find, find device, by ip, ip
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
ms.openlocfilehash: 46afa945ce86c35e3af1c542eb1a9770041b3430
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769442"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="d9250-104">Buscar dispositivos por API IP interna</span><span class="sxs-lookup"><span data-stu-id="d9250-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9250-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d9250-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="d9250-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="d9250-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d9250-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d9250-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d9250-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="d9250-108">API description</span></span>
<span data-ttu-id="d9250-109">Buscar [máquinas](machine.md) vistas con la IP interna solicitada en el intervalo de tiempo de 15 minutos antes y después de una marca de tiempo determinada.</span><span class="sxs-lookup"><span data-stu-id="d9250-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="d9250-110">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="d9250-110">Limitations</span></span>
1. <span data-ttu-id="d9250-111">La marca de tiempo especificada debe estar en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="d9250-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="d9250-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="d9250-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d9250-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="d9250-113">Permissions</span></span>
<span data-ttu-id="d9250-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="d9250-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d9250-115">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d9250-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d9250-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="d9250-116">Permission type</span></span> |   <span data-ttu-id="d9250-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="d9250-117">Permission</span></span>  |   <span data-ttu-id="d9250-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="d9250-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d9250-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d9250-119">Application</span></span> |   <span data-ttu-id="d9250-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="d9250-120">Machine.Read.All</span></span> |  <span data-ttu-id="d9250-121">'Leer todos los perfiles de máquina'</span><span class="sxs-lookup"><span data-stu-id="d9250-121">'Read all machine profiles'</span></span>
<span data-ttu-id="d9250-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d9250-122">Application</span></span> |   <span data-ttu-id="d9250-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d9250-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="d9250-124">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="d9250-124">'Read and write all machine information'</span></span>
<span data-ttu-id="d9250-125">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="d9250-125">Delegated (work or school account)</span></span> | <span data-ttu-id="d9250-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="d9250-126">Machine.Read</span></span> | <span data-ttu-id="d9250-127">'Leer información de máquina'</span><span class="sxs-lookup"><span data-stu-id="d9250-127">'Read machine information'</span></span>
<span data-ttu-id="d9250-128">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="d9250-128">Delegated (work or school account)</span></span> | <span data-ttu-id="d9250-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d9250-129">Machine.ReadWrite</span></span> | <span data-ttu-id="d9250-130">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="d9250-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="d9250-131">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="d9250-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="d9250-132">La respuesta incluirá solo los dispositivos a los que el usuario tenga acceso en función de la configuración del grupo de dispositivos (consulta [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d9250-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="d9250-133">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d9250-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="d9250-134">La respuesta incluirá solo los dispositivos a los que el usuario tenga acceso en función de la configuración del grupo de dispositivos (consulta [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d9250-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d9250-135">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="d9250-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="d9250-136">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="d9250-136">Request headers</span></span>

<span data-ttu-id="d9250-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="d9250-137">Name</span></span> | <span data-ttu-id="d9250-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="d9250-138">Type</span></span> | <span data-ttu-id="d9250-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9250-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="d9250-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="d9250-140">Authorization</span></span> | <span data-ttu-id="d9250-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="d9250-141">String</span></span> | <span data-ttu-id="d9250-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="d9250-142">Bearer {token}.</span></span> <span data-ttu-id="d9250-143">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d9250-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d9250-144">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="d9250-144">Request body</span></span>
<span data-ttu-id="d9250-145">En blanco</span><span class="sxs-lookup"><span data-stu-id="d9250-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d9250-146">Respuesta</span><span class="sxs-lookup"><span data-stu-id="d9250-146">Response</span></span>
<span data-ttu-id="d9250-147">Si se realiza correctamente: 200 Aceptar con una lista de las máquinas en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="d9250-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="d9250-148">Si la marca de tiempo no está en los últimos 30 días: 400 solicitudes no válidas.</span><span class="sxs-lookup"><span data-stu-id="d9250-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="d9250-149">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d9250-149">Example</span></span>

<span data-ttu-id="d9250-150">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="d9250-150">**Request**</span></span>

<span data-ttu-id="d9250-151">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d9250-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
