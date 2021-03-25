---
title: Obtener api de alertas relacionadas con el dominio
description: Obtenga información sobre cómo usar la API Obtener alertas relacionadas con el dominio para recuperar alertas relacionadas con una dirección de dominio determinada en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, domain, related, alerts
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
ms.openlocfilehash: f8de54072c0b0ebef69b8e5586fee058b971c51f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166868"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="60c31-104">Obtener api de alertas relacionadas con el dominio</span><span class="sxs-lookup"><span data-stu-id="60c31-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="60c31-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="60c31-105">**Applies to:**</span></span>
- [<span data-ttu-id="60c31-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="60c31-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="60c31-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60c31-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="60c31-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="60c31-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="60c31-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="60c31-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="60c31-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="60c31-110">API description</span></span>
<span data-ttu-id="60c31-111">Recupera una colección de [alertas relacionadas](alerts.md) con una dirección de dominio determinada.</span><span class="sxs-lookup"><span data-stu-id="60c31-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="60c31-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="60c31-112">Limitations</span></span>
1. <span data-ttu-id="60c31-113">Puede consultar las alertas actualizadas por última vez de acuerdo con el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="60c31-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="60c31-114">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="60c31-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="60c31-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="60c31-115">Permissions</span></span>
<span data-ttu-id="60c31-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="60c31-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="60c31-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="60c31-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="60c31-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="60c31-118">Permission type</span></span> |   <span data-ttu-id="60c31-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="60c31-119">Permission</span></span>  |   <span data-ttu-id="60c31-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="60c31-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="60c31-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="60c31-121">Application</span></span> |   <span data-ttu-id="60c31-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="60c31-122">Alert.Read.All</span></span> |    <span data-ttu-id="60c31-123">'Leer todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="60c31-123">'Read all alerts'</span></span>
<span data-ttu-id="60c31-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="60c31-124">Application</span></span> |   <span data-ttu-id="60c31-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="60c31-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="60c31-126">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="60c31-126">'Read and write all alerts'</span></span>
<span data-ttu-id="60c31-127">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="60c31-127">Delegated (work or school account)</span></span> | <span data-ttu-id="60c31-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="60c31-128">Alert.Read</span></span> | <span data-ttu-id="60c31-129">'Leer alertas'</span><span class="sxs-lookup"><span data-stu-id="60c31-129">'Read alerts'</span></span>
<span data-ttu-id="60c31-130">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="60c31-130">Delegated (work or school account)</span></span> | <span data-ttu-id="60c31-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="60c31-131">Alert.ReadWrite</span></span> | <span data-ttu-id="60c31-132">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="60c31-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="60c31-133">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="60c31-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="60c31-134">El usuario debe tener al menos el siguiente permiso de función: "Ver datos" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="60c31-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="60c31-135">La respuesta incluirá solo alertas, asociadas con dispositivos, a las que el usuario tiene acceso, según la configuración del grupo de dispositivos (vea [Crear y](machine-groups.md) administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="60c31-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="60c31-136">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="60c31-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="60c31-137">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="60c31-137">Request headers</span></span>

| <span data-ttu-id="60c31-138">Encabezado</span><span class="sxs-lookup"><span data-stu-id="60c31-138">Header</span></span>        | <span data-ttu-id="60c31-139">Valor</span><span class="sxs-lookup"><span data-stu-id="60c31-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="60c31-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="60c31-140">Authorization</span></span> | <span data-ttu-id="60c31-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="60c31-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="60c31-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="60c31-142">Request body</span></span>
<span data-ttu-id="60c31-143">En blanco</span><span class="sxs-lookup"><span data-stu-id="60c31-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="60c31-144">Respuesta</span><span class="sxs-lookup"><span data-stu-id="60c31-144">Response</span></span>
<span data-ttu-id="60c31-145">Si se realiza correctamente y el dominio existe: 200 Aceptar con la lista [de](alerts.md) entidades de alerta.</span><span class="sxs-lookup"><span data-stu-id="60c31-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="60c31-146">Si el dominio no existe: 404 No encontrado.</span><span class="sxs-lookup"><span data-stu-id="60c31-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="60c31-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60c31-147">Example</span></span>

<span data-ttu-id="60c31-148">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="60c31-148">**Request**</span></span>

<span data-ttu-id="60c31-149">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="60c31-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
