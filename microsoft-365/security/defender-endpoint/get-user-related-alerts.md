---
title: Obtener la API de alertas relacionadas con el usuario
description: Recupera una colección de alertas relacionadas con un identificador de usuario determinado mediante Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, user, related, alerts
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769934"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="0bdc7-104">Obtener la API de alertas relacionadas con el usuario</span><span class="sxs-lookup"><span data-stu-id="0bdc7-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0bdc7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-105">**Applies to:**</span></span>
- [<span data-ttu-id="0bdc7-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0bdc7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0bdc7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0bdc7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0bdc7-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0bdc7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0bdc7-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="0bdc7-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="0bdc7-110">API description</span></span>
<span data-ttu-id="0bdc7-111">Recupera una colección de alertas relacionadas con un identificador de usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="0bdc7-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="0bdc7-112">Limitations</span></span>
1. <span data-ttu-id="0bdc7-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="0bdc7-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="0bdc7-114">Permissions</span></span>
<span data-ttu-id="0bdc7-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0bdc7-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0bdc7-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0bdc7-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="0bdc7-117">Permission type</span></span> |   <span data-ttu-id="0bdc7-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="0bdc7-118">Permission</span></span>  |   <span data-ttu-id="0bdc7-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="0bdc7-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0bdc7-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="0bdc7-120">Application</span></span> |   <span data-ttu-id="0bdc7-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="0bdc7-121">Alert.Read.All</span></span> |    <span data-ttu-id="0bdc7-122">'Leer todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="0bdc7-122">'Read all alerts'</span></span>
<span data-ttu-id="0bdc7-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="0bdc7-123">Application</span></span> |   <span data-ttu-id="0bdc7-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0bdc7-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="0bdc7-125">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="0bdc7-125">'Read and write all alerts'</span></span>
<span data-ttu-id="0bdc7-126">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="0bdc7-126">Delegated (work or school account)</span></span> | <span data-ttu-id="0bdc7-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="0bdc7-127">Alert.Read</span></span> | <span data-ttu-id="0bdc7-128">'Leer alertas'</span><span class="sxs-lookup"><span data-stu-id="0bdc7-128">'Read alerts'</span></span>
<span data-ttu-id="0bdc7-129">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="0bdc7-129">Delegated (work or school account)</span></span> | <span data-ttu-id="0bdc7-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0bdc7-130">Alert.ReadWrite</span></span> | <span data-ttu-id="0bdc7-131">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="0bdc7-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="0bdc7-132">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="0bdc7-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0bdc7-133">El usuario debe tener al menos el siguiente permiso de función: "Ver datos".</span><span class="sxs-lookup"><span data-stu-id="0bdc7-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="0bdc7-134">Para obtener más información, vea [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0bdc7-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="0bdc7-135">La respuesta incluirá solo alertas, asociadas con dispositivos, a las que el usuario tiene acceso, según la configuración del grupo de dispositivos (vea [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="0bdc7-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0bdc7-136">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="0bdc7-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="0bdc7-137">**El identificador no es el UPN completo, sino solo el nombre de usuario. (por ejemplo, para recuperar alertas para user1@contoso.com usar /api/users/user1/alerts)**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="0bdc7-138">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="0bdc7-138">Request headers</span></span>

<span data-ttu-id="0bdc7-139">Nombre</span><span class="sxs-lookup"><span data-stu-id="0bdc7-139">Name</span></span> | <span data-ttu-id="0bdc7-140">Tipo</span><span class="sxs-lookup"><span data-stu-id="0bdc7-140">Type</span></span> | <span data-ttu-id="0bdc7-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bdc7-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="0bdc7-142">Authorization</span><span class="sxs-lookup"><span data-stu-id="0bdc7-142">Authorization</span></span> | <span data-ttu-id="0bdc7-143">Cadena</span><span class="sxs-lookup"><span data-stu-id="0bdc7-143">String</span></span> | <span data-ttu-id="0bdc7-144">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-144">Bearer {token}.</span></span> <span data-ttu-id="0bdc7-145">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0bdc7-146">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="0bdc7-146">Request body</span></span>
<span data-ttu-id="0bdc7-147">En blanco</span><span class="sxs-lookup"><span data-stu-id="0bdc7-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0bdc7-148">Respuesta</span><span class="sxs-lookup"><span data-stu-id="0bdc7-148">Response</span></span>
<span data-ttu-id="0bdc7-149">Si se realiza correctamente y el usuario existe: 200 Aceptar.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="0bdc7-150">Si el usuario no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="0bdc7-151">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0bdc7-151">Example</span></span>

<span data-ttu-id="0bdc7-152">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="0bdc7-152">**Request**</span></span>

<span data-ttu-id="0bdc7-153">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="0bdc7-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
