---
title: Agregar o quitar API de etiquetas de máquina
description: Obtenga información sobre cómo usar la API Agregar o quitar etiquetas de máquina para agregar o quitar una etiqueta para una máquina en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, etiquetas, etiquetas de máquina
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
ms.openlocfilehash: 3818fc0050790b2c3b307f95ee0760c516cbf893
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769826"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="33dac-104">Agregar o quitar API de etiquetas de máquina</span><span class="sxs-lookup"><span data-stu-id="33dac-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="33dac-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="33dac-105">**Applies to:**</span></span>

- [<span data-ttu-id="33dac-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="33dac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="33dac-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="33dac-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="33dac-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="33dac-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="33dac-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="33dac-109">API description</span></span>

<span data-ttu-id="33dac-110">Agrega o quita etiqueta a una [máquina específica.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="33dac-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="33dac-111">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="33dac-111">Limitations</span></span>

1. <span data-ttu-id="33dac-112">Puede publicar en máquinas que se han visto por última vez de acuerdo con el período de retención configurado.</span><span class="sxs-lookup"><span data-stu-id="33dac-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="33dac-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="33dac-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="33dac-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="33dac-114">Permissions</span></span>

<span data-ttu-id="33dac-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="33dac-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="33dac-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="33dac-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="33dac-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="33dac-117">Permission type</span></span> |    <span data-ttu-id="33dac-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="33dac-118">Permission</span></span>    |    <span data-ttu-id="33dac-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="33dac-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="33dac-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="33dac-120">Application</span></span> |    <span data-ttu-id="33dac-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="33dac-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="33dac-122">'Leer y escribir toda la información de la máquina'</span><span class="sxs-lookup"><span data-stu-id="33dac-122">'Read and write all machine information'</span></span>
<span data-ttu-id="33dac-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="33dac-123">Delegated (work or school account)</span></span> | <span data-ttu-id="33dac-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="33dac-124">Machine.ReadWrite</span></span> | <span data-ttu-id="33dac-125">'Leer y escribir información de máquina'</span><span class="sxs-lookup"><span data-stu-id="33dac-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="33dac-126">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="33dac-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="33dac-127">El usuario debe tener al menos el siguiente permiso de función: "Administrar la configuración de seguridad".</span><span class="sxs-lookup"><span data-stu-id="33dac-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="33dac-128">Para obtener más información (vea [Crear y administrar roles](user-roles.md) para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="33dac-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="33dac-129">El usuario debe tener acceso a la máquina en función de la configuración del grupo de máquinas (vea [Crear y](machine-groups.md) administrar grupos de máquinas para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="33dac-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="33dac-130">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="33dac-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="33dac-131">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="33dac-131">Request headers</span></span>

<span data-ttu-id="33dac-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="33dac-132">Name</span></span> | <span data-ttu-id="33dac-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="33dac-133">Type</span></span> | <span data-ttu-id="33dac-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="33dac-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="33dac-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="33dac-135">Authorization</span></span> | <span data-ttu-id="33dac-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="33dac-136">String</span></span> | <span data-ttu-id="33dac-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="33dac-137">Bearer {token}.</span></span> <span data-ttu-id="33dac-138">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="33dac-138">**Required**.</span></span>
<span data-ttu-id="33dac-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="33dac-139">Content-Type</span></span> | <span data-ttu-id="33dac-140">cadena</span><span class="sxs-lookup"><span data-stu-id="33dac-140">string</span></span> | <span data-ttu-id="33dac-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="33dac-141">application/json.</span></span> <span data-ttu-id="33dac-142">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="33dac-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="33dac-143">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="33dac-143">Request body</span></span>

<span data-ttu-id="33dac-144">En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="33dac-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="33dac-145">Parámetro</span><span class="sxs-lookup"><span data-stu-id="33dac-145">Parameter</span></span> |    <span data-ttu-id="33dac-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="33dac-146">Type</span></span>    | <span data-ttu-id="33dac-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="33dac-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="33dac-148">Valor</span><span class="sxs-lookup"><span data-stu-id="33dac-148">Value</span></span> |    <span data-ttu-id="33dac-149">Cadena</span><span class="sxs-lookup"><span data-stu-id="33dac-149">String</span></span> |    <span data-ttu-id="33dac-150">El nombre de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="33dac-150">The tag name.</span></span> <span data-ttu-id="33dac-151">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="33dac-151">**Required**.</span></span>
<span data-ttu-id="33dac-152">Acción</span><span class="sxs-lookup"><span data-stu-id="33dac-152">Action</span></span>    | <span data-ttu-id="33dac-153">Enum</span><span class="sxs-lookup"><span data-stu-id="33dac-153">Enum</span></span> |    <span data-ttu-id="33dac-154">Agregar o quitar.</span><span class="sxs-lookup"><span data-stu-id="33dac-154">Add or Remove.</span></span> <span data-ttu-id="33dac-155">Los valores permitidos son: "Agregar" o "Quitar".</span><span class="sxs-lookup"><span data-stu-id="33dac-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="33dac-156">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="33dac-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="33dac-157">Respuesta</span><span class="sxs-lookup"><span data-stu-id="33dac-157">Response</span></span>

<span data-ttu-id="33dac-158">Si se realiza correctamente, este método devuelve 200: código de respuesta Aceptar y la máquina actualizada en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="33dac-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="33dac-159">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="33dac-159">Example</span></span>

<span data-ttu-id="33dac-160">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="33dac-160">**Request**</span></span>

<span data-ttu-id="33dac-161">Este es un ejemplo de una solicitud que agrega etiqueta de máquina.</span><span class="sxs-lookup"><span data-stu-id="33dac-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="33dac-162">Para quitar la etiqueta de máquina, establece la acción en "Quitar" en lugar de "Agregar" en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="33dac-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
