---
title: INICIAR API de investigación
description: Usa esta API para iniciar la investigación en un dispositivo.
keywords: api, api de gráfico, api admitidas, investigación
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
ms.openlocfilehash: 4bdbfbb20f3abb9829b2c8be83b9eaa6ec92cde7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187330"
---
# <a name="start-investigation-api"></a><span data-ttu-id="d14bb-104">INICIAR API de investigación</span><span class="sxs-lookup"><span data-stu-id="d14bb-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d14bb-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d14bb-105">**Applies to:**</span></span>
- [<span data-ttu-id="d14bb-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d14bb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d14bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d14bb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d14bb-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d14bb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d14bb-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d14bb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d14bb-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="d14bb-110">API description</span></span>
<span data-ttu-id="d14bb-111">Inicie una investigación automatizada en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d14bb-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="d14bb-112">Vea [Overview of automated investigations](automated-investigations.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d14bb-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="d14bb-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="d14bb-113">Limitations</span></span>
1. <span data-ttu-id="d14bb-114">Las limitaciones de velocidad para esta API son 50 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="d14bb-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d14bb-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="d14bb-115">Permissions</span></span>
<span data-ttu-id="d14bb-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="d14bb-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d14bb-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d14bb-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d14bb-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="d14bb-118">Permission type</span></span> |   <span data-ttu-id="d14bb-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="d14bb-119">Permission</span></span>  |   <span data-ttu-id="d14bb-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="d14bb-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d14bb-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d14bb-121">Application</span></span> |   <span data-ttu-id="d14bb-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d14bb-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="d14bb-123">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="d14bb-123">'Read and write all alerts'</span></span>
<span data-ttu-id="d14bb-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="d14bb-124">Delegated (work or school account)</span></span> | <span data-ttu-id="d14bb-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d14bb-125">Alert.ReadWrite</span></span> | <span data-ttu-id="d14bb-126">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="d14bb-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="d14bb-127">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="d14bb-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d14bb-128">El usuario debe tener al menos el siguiente permiso de función: "Acciones de corrección activas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d14bb-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d14bb-129">El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="d14bb-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="d14bb-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="d14bb-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="d14bb-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="d14bb-131">Request headers</span></span>

<span data-ttu-id="d14bb-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="d14bb-132">Name</span></span> | <span data-ttu-id="d14bb-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="d14bb-133">Type</span></span> | <span data-ttu-id="d14bb-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="d14bb-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="d14bb-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="d14bb-135">Authorization</span></span> | <span data-ttu-id="d14bb-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="d14bb-136">String</span></span> | <span data-ttu-id="d14bb-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="d14bb-137">Bearer {token}.</span></span> <span data-ttu-id="d14bb-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d14bb-138">**Required**.</span></span>
<span data-ttu-id="d14bb-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d14bb-139">Content-Type</span></span> | <span data-ttu-id="d14bb-140">string</span><span class="sxs-lookup"><span data-stu-id="d14bb-140">string</span></span> | <span data-ttu-id="d14bb-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="d14bb-141">application/json.</span></span> <span data-ttu-id="d14bb-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d14bb-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d14bb-143">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="d14bb-143">Request body</span></span>
<span data-ttu-id="d14bb-144">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="d14bb-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="d14bb-145">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d14bb-145">Parameter</span></span> | <span data-ttu-id="d14bb-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="d14bb-146">Type</span></span>    | <span data-ttu-id="d14bb-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="d14bb-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="d14bb-148">Comentario</span><span class="sxs-lookup"><span data-stu-id="d14bb-148">Comment</span></span> |   <span data-ttu-id="d14bb-149">Cadena</span><span class="sxs-lookup"><span data-stu-id="d14bb-149">String</span></span> |    <span data-ttu-id="d14bb-150">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="d14bb-150">Comment to associate with the action.</span></span> <span data-ttu-id="d14bb-151">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="d14bb-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="d14bb-152">Respuesta</span><span class="sxs-lookup"><span data-stu-id="d14bb-152">Response</span></span>
<span data-ttu-id="d14bb-153">Si se realiza correctamente, este método devuelve 201: código de respuesta creado e [Investigación](investigation.md) en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="d14bb-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="d14bb-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d14bb-154">Example</span></span>

<span data-ttu-id="d14bb-155">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="d14bb-155">**Request**</span></span>

<span data-ttu-id="d14bb-156">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d14bb-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
