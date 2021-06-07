---
title: Tipo de recurso Investigación
description: Entidad de Microsoft Defender para Endpoint Investigation.
keywords: apis, api de gráficos, api admitidas, get, alerts, investigations
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 252b273995d48d523604802c0c4365a613d86dbe
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771734"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="e7a1e-104">Tipo de recurso Investigación</span><span class="sxs-lookup"><span data-stu-id="e7a1e-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e7a1e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e7a1e-105">**Applies to:**</span></span>
- [<span data-ttu-id="e7a1e-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e7a1e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e7a1e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7a1e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e7a1e-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e7a1e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e7a1e-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="e7a1e-110">Representa una entidad de investigación automatizada en Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="e7a1e-111">Vea [Overview of automated investigations](automated-investigations.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="e7a1e-112">Métodos</span><span class="sxs-lookup"><span data-stu-id="e7a1e-112">Methods</span></span>
<span data-ttu-id="e7a1e-113">Método</span><span class="sxs-lookup"><span data-stu-id="e7a1e-113">Method</span></span>|<span data-ttu-id="e7a1e-114">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e7a1e-114">Return Type</span></span> |<span data-ttu-id="e7a1e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7a1e-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="e7a1e-116">Enumerar investigaciones</span><span class="sxs-lookup"><span data-stu-id="e7a1e-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="e7a1e-117">Colección Investigation</span><span class="sxs-lookup"><span data-stu-id="e7a1e-117">Investigation collection</span></span> | <span data-ttu-id="e7a1e-118">Obtener colección de investigación</span><span class="sxs-lookup"><span data-stu-id="e7a1e-118">Get collection of Investigation</span></span>
[<span data-ttu-id="e7a1e-119">Obtener una sola investigación</span><span class="sxs-lookup"><span data-stu-id="e7a1e-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="e7a1e-120">Entidad de investigación</span><span class="sxs-lookup"><span data-stu-id="e7a1e-120">Investigation entity</span></span> | <span data-ttu-id="e7a1e-121">Obtiene una sola entidad Investigation.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="e7a1e-122">Iniciar investigación</span><span class="sxs-lookup"><span data-stu-id="e7a1e-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="e7a1e-123">Entidad de investigación</span><span class="sxs-lookup"><span data-stu-id="e7a1e-123">Investigation entity</span></span> | <span data-ttu-id="e7a1e-124">Inicia Investigación en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="e7a1e-125">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e7a1e-125">Properties</span></span>
<span data-ttu-id="e7a1e-126">Propiedad</span><span class="sxs-lookup"><span data-stu-id="e7a1e-126">Property</span></span> |  <span data-ttu-id="e7a1e-127">Tipo</span><span class="sxs-lookup"><span data-stu-id="e7a1e-127">Type</span></span>    |   <span data-ttu-id="e7a1e-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7a1e-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="e7a1e-129">id</span><span class="sxs-lookup"><span data-stu-id="e7a1e-129">id</span></span> | <span data-ttu-id="e7a1e-130">Cadena</span><span class="sxs-lookup"><span data-stu-id="e7a1e-130">String</span></span> | <span data-ttu-id="e7a1e-131">Identidad de la entidad de investigación.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="e7a1e-132">startTime</span><span class="sxs-lookup"><span data-stu-id="e7a1e-132">startTime</span></span> | <span data-ttu-id="e7a1e-133">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="e7a1e-133">DateTime Nullable</span></span> | <span data-ttu-id="e7a1e-134">La fecha y hora en que se creó la investigación.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="e7a1e-135">endTime</span><span class="sxs-lookup"><span data-stu-id="e7a1e-135">endTime</span></span> | <span data-ttu-id="e7a1e-136">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="e7a1e-136">DateTime Nullable</span></span> | <span data-ttu-id="e7a1e-137">La fecha y la hora en que se completó la investigación.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="e7a1e-138">cancelledBy</span><span class="sxs-lookup"><span data-stu-id="e7a1e-138">cancelledBy</span></span> | <span data-ttu-id="e7a1e-139">Cadena</span><span class="sxs-lookup"><span data-stu-id="e7a1e-139">String</span></span> | <span data-ttu-id="e7a1e-140">El identificador del usuario o aplicación que canceló esa investigación.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="e7a1e-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="e7a1e-141">investigationState</span></span> | <span data-ttu-id="e7a1e-142">Enum</span><span class="sxs-lookup"><span data-stu-id="e7a1e-142">Enum</span></span> | <span data-ttu-id="e7a1e-143">El estado actual de la investigación.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-143">The current state of the investigation.</span></span> <span data-ttu-id="e7a1e-144">Los valores posibles son: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="e7a1e-145">statusDetails</span><span class="sxs-lookup"><span data-stu-id="e7a1e-145">statusDetails</span></span> | <span data-ttu-id="e7a1e-146">Cadena</span><span class="sxs-lookup"><span data-stu-id="e7a1e-146">String</span></span> | <span data-ttu-id="e7a1e-147">Información adicional sobre el estado de la investigación.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="e7a1e-148">machineId</span><span class="sxs-lookup"><span data-stu-id="e7a1e-148">machineId</span></span> | <span data-ttu-id="e7a1e-149">Cadena</span><span class="sxs-lookup"><span data-stu-id="e7a1e-149">String</span></span> | <span data-ttu-id="e7a1e-150">El identificador del dispositivo en el que se ejecuta la investigación.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="e7a1e-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="e7a1e-151">computerDnsName</span></span> | <span data-ttu-id="e7a1e-152">Cadena</span><span class="sxs-lookup"><span data-stu-id="e7a1e-152">String</span></span> | <span data-ttu-id="e7a1e-153">Nombre del dispositivo en el que se ejecuta la investigación.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="e7a1e-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="e7a1e-154">triggeringAlertId</span></span> | <span data-ttu-id="e7a1e-155">Cadena</span><span class="sxs-lookup"><span data-stu-id="e7a1e-155">String</span></span> | <span data-ttu-id="e7a1e-156">El identificador de la alerta que desencadenó la investigación.</span><span class="sxs-lookup"><span data-stu-id="e7a1e-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="e7a1e-157">Representación json</span><span class="sxs-lookup"><span data-stu-id="e7a1e-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
