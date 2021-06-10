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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b9de7645abc59849b3ca28f64904b0ba49d4eef5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771902"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="337c7-104">Obtener información de alerta por API de id.</span><span class="sxs-lookup"><span data-stu-id="337c7-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="337c7-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="337c7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="337c7-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="337c7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="337c7-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="337c7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="337c7-108">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="337c7-108">API description</span></span>
<span data-ttu-id="337c7-109">Recupera alerta [específica por](alerts.md) su identificador.</span><span class="sxs-lookup"><span data-stu-id="337c7-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="337c7-110">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="337c7-110">Limitations</span></span>
1. <span data-ttu-id="337c7-111">Puede obtener las alertas por última vez actualizadas según el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="337c7-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="337c7-112">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="337c7-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="337c7-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="337c7-113">Permissions</span></span>
<span data-ttu-id="337c7-114">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="337c7-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="337c7-115">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="337c7-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="337c7-116">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="337c7-116">Permission type</span></span> |   <span data-ttu-id="337c7-117">Permiso</span><span class="sxs-lookup"><span data-stu-id="337c7-117">Permission</span></span>  |   <span data-ttu-id="337c7-118">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="337c7-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="337c7-119">Aplicación</span><span class="sxs-lookup"><span data-stu-id="337c7-119">Application</span></span> |   <span data-ttu-id="337c7-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="337c7-120">Alert.Read.All</span></span> |    <span data-ttu-id="337c7-121">'Leer todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="337c7-121">'Read all alerts'</span></span>
<span data-ttu-id="337c7-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="337c7-122">Application</span></span> |   <span data-ttu-id="337c7-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="337c7-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="337c7-124">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="337c7-124">'Read and write all alerts'</span></span>
<span data-ttu-id="337c7-125">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="337c7-125">Delegated (work or school account)</span></span> | <span data-ttu-id="337c7-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="337c7-126">Alert.Read</span></span> | <span data-ttu-id="337c7-127">'Leer alertas'</span><span class="sxs-lookup"><span data-stu-id="337c7-127">'Read alerts'</span></span>
<span data-ttu-id="337c7-128">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="337c7-128">Delegated (work or school account)</span></span> | <span data-ttu-id="337c7-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="337c7-129">Alert.ReadWrite</span></span> | <span data-ttu-id="337c7-130">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="337c7-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="337c7-131">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="337c7-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="337c7-132">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="337c7-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="337c7-133">El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="337c7-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="337c7-134">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="337c7-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="337c7-135">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="337c7-135">Request headers</span></span>

<span data-ttu-id="337c7-136">Nombre</span><span class="sxs-lookup"><span data-stu-id="337c7-136">Name</span></span> | <span data-ttu-id="337c7-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="337c7-137">Type</span></span> | <span data-ttu-id="337c7-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="337c7-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="337c7-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="337c7-139">Authorization</span></span> | <span data-ttu-id="337c7-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="337c7-140">String</span></span> | <span data-ttu-id="337c7-141">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="337c7-141">Bearer {token}.</span></span> <span data-ttu-id="337c7-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="337c7-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="337c7-143">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="337c7-143">Request body</span></span>
<span data-ttu-id="337c7-144">En blanco</span><span class="sxs-lookup"><span data-stu-id="337c7-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="337c7-145">Respuesta</span><span class="sxs-lookup"><span data-stu-id="337c7-145">Response</span></span>
<span data-ttu-id="337c7-146">Si se realiza correctamente, este método devuelve 200 Ok y la entidad [alert](alerts.md) en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="337c7-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="337c7-147">Si no se encontró la alerta con el identificador especificado: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="337c7-147">If alert with the specified id was not found - 404 Not Found.</span></span>
