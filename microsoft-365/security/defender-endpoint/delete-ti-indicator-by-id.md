---
title: Eliminar API de indicador.
description: Obtenga información sobre cómo usar la API Eliminar indicador para eliminar una entidad Indicator por id. en Microsoft Defender para endpoint.
keywords: apis, api pública, api admitidas, delete, indicador ti, entidad, id
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
ms.openlocfilehash: eaef6b25e2db72149a1a1128899d8a79a38a4c60
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771026"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="0148e-104">Eliminar API de indicador</span><span class="sxs-lookup"><span data-stu-id="0148e-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0148e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0148e-105">**Applies to:**</span></span>
- [<span data-ttu-id="0148e-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0148e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0148e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0148e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0148e-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0148e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0148e-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0148e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="0148e-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="0148e-110">API description</span></span>
<span data-ttu-id="0148e-111">Elimina una entidad [Indicator](ti-indicator.md) por identificador.</span><span class="sxs-lookup"><span data-stu-id="0148e-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="0148e-112">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="0148e-112">Limitations</span></span>
1. <span data-ttu-id="0148e-113">Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="0148e-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="0148e-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="0148e-114">Permissions</span></span>
<span data-ttu-id="0148e-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="0148e-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0148e-116">Para obtener más información, incluido cómo elegir permisos, vea [Introducción](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0148e-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="0148e-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="0148e-117">Permission type</span></span> |   <span data-ttu-id="0148e-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="0148e-118">Permission</span></span>  |   <span data-ttu-id="0148e-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="0148e-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0148e-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="0148e-120">Application</span></span> |   <span data-ttu-id="0148e-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0148e-121">Ti.ReadWrite</span></span> |  <span data-ttu-id="0148e-122">'Leer y escribir indicadores de TI'</span><span class="sxs-lookup"><span data-stu-id="0148e-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="0148e-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="0148e-123">Application</span></span> |   <span data-ttu-id="0148e-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0148e-124">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="0148e-125">Indicadores de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="0148e-125">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="0148e-126">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="0148e-126">HTTP request</span></span>
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="0148e-127">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="0148e-127">Request headers</span></span>

<span data-ttu-id="0148e-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="0148e-128">Name</span></span> | <span data-ttu-id="0148e-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="0148e-129">Type</span></span> | <span data-ttu-id="0148e-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="0148e-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="0148e-131">Authorization</span><span class="sxs-lookup"><span data-stu-id="0148e-131">Authorization</span></span> | <span data-ttu-id="0148e-132">Cadena</span><span class="sxs-lookup"><span data-stu-id="0148e-132">String</span></span> | <span data-ttu-id="0148e-133">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="0148e-133">Bearer {token}.</span></span> <span data-ttu-id="0148e-134">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="0148e-134">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0148e-135">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="0148e-135">Request body</span></span>
<span data-ttu-id="0148e-136">En blanco</span><span class="sxs-lookup"><span data-stu-id="0148e-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0148e-137">Respuesta</span><span class="sxs-lookup"><span data-stu-id="0148e-137">Response</span></span>
<span data-ttu-id="0148e-138">Si el indicador existe y se elimina correctamente: 204 Aceptar sin contenido.</span><span class="sxs-lookup"><span data-stu-id="0148e-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>
<span data-ttu-id="0148e-139">Si no se encontró Indicator con el identificador especificado- 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="0148e-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="0148e-140">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0148e-140">Example</span></span>

<span data-ttu-id="0148e-141">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="0148e-141">**Request**</span></span>

<span data-ttu-id="0148e-142">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="0148e-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
