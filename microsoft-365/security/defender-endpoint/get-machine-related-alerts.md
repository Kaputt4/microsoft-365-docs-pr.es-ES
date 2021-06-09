---
title: Obtener api de alertas relacionadas con la máquina
description: Aprende a usar la API Obtener alertas relacionadas con la máquina para recuperar todas las alertas relacionadas con un dispositivo específico en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, dispositivos, relacionados, alertas
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: bf445332fed7b8661c510bf60f36088b79e2d8df
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770030"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="39508-104">Obtener api de alertas relacionadas con la máquina</span><span class="sxs-lookup"><span data-stu-id="39508-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="39508-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="39508-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="39508-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="39508-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="39508-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="39508-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="39508-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="39508-108">API description</span></span>
<span data-ttu-id="39508-109">Recupera todas las [alertas](alerts.md) relacionadas con un dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="39508-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="39508-110">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="39508-110">Limitations</span></span>
1. <span data-ttu-id="39508-111">Puede consultar en dispositivos actualizados por última vez de acuerdo con el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="39508-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="39508-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="39508-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="39508-113">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="39508-113">Permission type</span></span> |   <span data-ttu-id="39508-114">Permiso</span><span class="sxs-lookup"><span data-stu-id="39508-114">Permission</span></span>  |   <span data-ttu-id="39508-115">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="39508-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="39508-116">Aplicación</span><span class="sxs-lookup"><span data-stu-id="39508-116">Application</span></span> |   <span data-ttu-id="39508-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="39508-117">Alert.Read.All</span></span> |    <span data-ttu-id="39508-118">'Leer todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="39508-118">'Read all alerts'</span></span>
<span data-ttu-id="39508-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="39508-119">Application</span></span> |   <span data-ttu-id="39508-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="39508-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="39508-121">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="39508-121">'Read and write all alerts'</span></span>
<span data-ttu-id="39508-122">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="39508-122">Delegated (work or school account)</span></span> | <span data-ttu-id="39508-123">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="39508-123">Alert.Read</span></span> | <span data-ttu-id="39508-124">'Leer alertas'</span><span class="sxs-lookup"><span data-stu-id="39508-124">'Read alerts'</span></span>
<span data-ttu-id="39508-125">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="39508-125">Delegated (work or school account)</span></span> | <span data-ttu-id="39508-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="39508-126">Alert.ReadWrite</span></span> | <span data-ttu-id="39508-127">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="39508-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="39508-128">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="39508-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="39508-129">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="39508-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="39508-130">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="39508-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="39508-131">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="39508-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="39508-132">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="39508-132">Request headers</span></span>

<span data-ttu-id="39508-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="39508-133">Name</span></span> | <span data-ttu-id="39508-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="39508-134">Type</span></span> | <span data-ttu-id="39508-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="39508-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="39508-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="39508-136">Authorization</span></span> | <span data-ttu-id="39508-137">Cadena</span><span class="sxs-lookup"><span data-stu-id="39508-137">String</span></span> | <span data-ttu-id="39508-138">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="39508-138">Bearer {token}.</span></span> <span data-ttu-id="39508-139">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="39508-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="39508-140">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="39508-140">Request body</span></span>
<span data-ttu-id="39508-141">En blanco</span><span class="sxs-lookup"><span data-stu-id="39508-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="39508-142">Respuesta</span><span class="sxs-lookup"><span data-stu-id="39508-142">Response</span></span>
<span data-ttu-id="39508-143">Si se realiza correctamente y el dispositivo existe: 200 Aceptar con la lista [de](alerts.md) entidades de alerta en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="39508-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="39508-144">Si no se encontró el dispositivo: 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="39508-144">If device was not found - 404 Not Found.</span></span>
