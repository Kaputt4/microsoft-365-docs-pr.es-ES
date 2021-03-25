---
title: Obtener información de alerta por API de id.
description: Obtenga información sobre cómo usar la API Obtener información de alerta por ID para recuperar una alerta específica por su identificador en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, alert, information, id
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
ms.openlocfilehash: f9130b054ccea762e6c5cc4f2952bbfa82d24b83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200430"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="53066-104">Obtener información de alerta por API de id.</span><span class="sxs-lookup"><span data-stu-id="53066-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="53066-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="53066-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="53066-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="53066-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="53066-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="53066-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="53066-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="53066-108">API description</span></span>
<span data-ttu-id="53066-109">Recupera alerta [específica por](alerts.md) su identificador.</span><span class="sxs-lookup"><span data-stu-id="53066-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="53066-110">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="53066-110">Limitations</span></span>
1. <span data-ttu-id="53066-111">Puede obtener las alertas por última vez actualizadas según el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="53066-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="53066-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="53066-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="53066-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="53066-113">Permissions</span></span>
<span data-ttu-id="53066-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="53066-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="53066-115">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="53066-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="53066-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="53066-116">Permission type</span></span> |   <span data-ttu-id="53066-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="53066-117">Permission</span></span>  |   <span data-ttu-id="53066-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="53066-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="53066-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="53066-119">Application</span></span> |   <span data-ttu-id="53066-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="53066-120">Alert.Read.All</span></span> |    <span data-ttu-id="53066-121">'Leer todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="53066-121">'Read all alerts'</span></span>
<span data-ttu-id="53066-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="53066-122">Application</span></span> |   <span data-ttu-id="53066-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="53066-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="53066-124">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="53066-124">'Read and write all alerts'</span></span>
<span data-ttu-id="53066-125">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="53066-125">Delegated (work or school account)</span></span> | <span data-ttu-id="53066-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="53066-126">Alert.Read</span></span> | <span data-ttu-id="53066-127">'Leer alertas'</span><span class="sxs-lookup"><span data-stu-id="53066-127">'Read alerts'</span></span>
<span data-ttu-id="53066-128">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="53066-128">Delegated (work or school account)</span></span> | <span data-ttu-id="53066-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="53066-129">Alert.ReadWrite</span></span> | <span data-ttu-id="53066-130">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="53066-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="53066-131">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="53066-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="53066-132">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="53066-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="53066-133">El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="53066-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="53066-134">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="53066-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="53066-135">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="53066-135">Request headers</span></span>

<span data-ttu-id="53066-136">Nombre</span><span class="sxs-lookup"><span data-stu-id="53066-136">Name</span></span> | <span data-ttu-id="53066-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="53066-137">Type</span></span> | <span data-ttu-id="53066-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="53066-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="53066-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="53066-139">Authorization</span></span> | <span data-ttu-id="53066-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="53066-140">String</span></span> | <span data-ttu-id="53066-141">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="53066-141">Bearer {token}.</span></span> <span data-ttu-id="53066-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="53066-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="53066-143">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="53066-143">Request body</span></span>
<span data-ttu-id="53066-144">En blanco</span><span class="sxs-lookup"><span data-stu-id="53066-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="53066-145">Respuesta</span><span class="sxs-lookup"><span data-stu-id="53066-145">Response</span></span>
<span data-ttu-id="53066-146">Si se realiza correctamente, este método devuelve 200 Ok y la entidad [alert](alerts.md) en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="53066-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="53066-147">Si no se encontró la alerta con el identificador especificado: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="53066-147">If alert with the specified id was not found - 404 Not Found.</span></span>
