---
title: Propiedades y métodos de software
description: Recupera las alertas más recientes.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771422"
---
# <a name="software-resource-type"></a><span data-ttu-id="71341-104">Tipo de recurso software</span><span class="sxs-lookup"><span data-stu-id="71341-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71341-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="71341-105">**Applies to:**</span></span>
- [<span data-ttu-id="71341-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="71341-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71341-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71341-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="71341-108">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="71341-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="71341-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="71341-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="71341-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="71341-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="71341-111">Métodos</span><span class="sxs-lookup"><span data-stu-id="71341-111">Methods</span></span>

<span data-ttu-id="71341-112">Método</span><span class="sxs-lookup"><span data-stu-id="71341-112">Method</span></span> |<span data-ttu-id="71341-113">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="71341-113">Return Type</span></span> |<span data-ttu-id="71341-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="71341-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="71341-115">Enumerar software</span><span class="sxs-lookup"><span data-stu-id="71341-115">List software</span></span>](get-software.md) | <span data-ttu-id="71341-116">Colección de software</span><span class="sxs-lookup"><span data-stu-id="71341-116">Software collection</span></span> | <span data-ttu-id="71341-117">Enumerar el inventario de software de la organización.</span><span class="sxs-lookup"><span data-stu-id="71341-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="71341-118">Obtener software por identificación</span><span class="sxs-lookup"><span data-stu-id="71341-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="71341-119">Software</span><span class="sxs-lookup"><span data-stu-id="71341-119">Software</span></span> | <span data-ttu-id="71341-120">Obtener un software específico por su identificador de software.</span><span class="sxs-lookup"><span data-stu-id="71341-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="71341-121">Enumerar distribución de versión de software</span><span class="sxs-lookup"><span data-stu-id="71341-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="71341-122">Colección de distribución</span><span class="sxs-lookup"><span data-stu-id="71341-122">Distribution collection</span></span> | <span data-ttu-id="71341-123">Enumerar la distribución de la versión de software por identificador de software.</span><span class="sxs-lookup"><span data-stu-id="71341-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="71341-124">Enumerar máquinas por software</span><span class="sxs-lookup"><span data-stu-id="71341-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="71341-125">Colección MachineRef</span><span class="sxs-lookup"><span data-stu-id="71341-125">MachineRef collection</span></span> | <span data-ttu-id="71341-126">Recupera una lista de dispositivos asociados con el identificador de software.</span><span class="sxs-lookup"><span data-stu-id="71341-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="71341-127">Enumerar vulnerabilidades por software</span><span class="sxs-lookup"><span data-stu-id="71341-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="71341-128">[Colección Vulnerability](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="71341-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="71341-129">Recupera una lista de vulnerabilidades asociadas con el identificador de software.</span><span class="sxs-lookup"><span data-stu-id="71341-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="71341-130">Obtener los kB que faltan</span><span class="sxs-lookup"><span data-stu-id="71341-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="71341-131">Colección KB</span><span class="sxs-lookup"><span data-stu-id="71341-131">KB collection</span></span> | <span data-ttu-id="71341-132">Obtener una lista de KBs que faltan asociados con el identificador de software</span><span class="sxs-lookup"><span data-stu-id="71341-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="71341-133">Propiedades</span><span class="sxs-lookup"><span data-stu-id="71341-133">Properties</span></span>

<span data-ttu-id="71341-134">Propiedad</span><span class="sxs-lookup"><span data-stu-id="71341-134">Property</span></span> |   <span data-ttu-id="71341-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="71341-135">Type</span></span>   |   <span data-ttu-id="71341-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="71341-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="71341-137">id</span><span class="sxs-lookup"><span data-stu-id="71341-137">id</span></span> | <span data-ttu-id="71341-138">Cadena</span><span class="sxs-lookup"><span data-stu-id="71341-138">String</span></span> | <span data-ttu-id="71341-139">Id. de software</span><span class="sxs-lookup"><span data-stu-id="71341-139">Software ID</span></span>
<span data-ttu-id="71341-140">Nombre</span><span class="sxs-lookup"><span data-stu-id="71341-140">Name</span></span> | <span data-ttu-id="71341-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="71341-141">String</span></span> | <span data-ttu-id="71341-142">Nombre del software</span><span class="sxs-lookup"><span data-stu-id="71341-142">Software name</span></span>
<span data-ttu-id="71341-143">Proveedor</span><span class="sxs-lookup"><span data-stu-id="71341-143">Vendor</span></span> | <span data-ttu-id="71341-144">Cadena</span><span class="sxs-lookup"><span data-stu-id="71341-144">String</span></span> | <span data-ttu-id="71341-145">Nombre del proveedor de software</span><span class="sxs-lookup"><span data-stu-id="71341-145">Software vendor name</span></span>
<span data-ttu-id="71341-146">Debilidades</span><span class="sxs-lookup"><span data-stu-id="71341-146">Weaknesses</span></span> | <span data-ttu-id="71341-147">Long</span><span class="sxs-lookup"><span data-stu-id="71341-147">Long</span></span> | <span data-ttu-id="71341-148">Número de vulnerabilidades detectadas</span><span class="sxs-lookup"><span data-stu-id="71341-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="71341-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="71341-149">publicExploit</span></span> | <span data-ttu-id="71341-150">Boolean</span><span class="sxs-lookup"><span data-stu-id="71341-150">Boolean</span></span> | <span data-ttu-id="71341-151">Existe vulnerabilidad pública para algunas de las vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="71341-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="71341-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="71341-152">activeAlert</span></span> | <span data-ttu-id="71341-153">Boolean</span><span class="sxs-lookup"><span data-stu-id="71341-153">Boolean</span></span> | <span data-ttu-id="71341-154">La alerta activa está asociada con este software</span><span class="sxs-lookup"><span data-stu-id="71341-154">Active alert is associated with this software</span></span>
<span data-ttu-id="71341-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="71341-155">exposedMachines</span></span> | <span data-ttu-id="71341-156">Long</span><span class="sxs-lookup"><span data-stu-id="71341-156">Long</span></span> | <span data-ttu-id="71341-157">Número de dispositivos expuestos</span><span class="sxs-lookup"><span data-stu-id="71341-157">Number of exposed devices</span></span>
<span data-ttu-id="71341-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="71341-158">impactScore</span></span> | <span data-ttu-id="71341-159">Doble</span><span class="sxs-lookup"><span data-stu-id="71341-159">Double</span></span> | <span data-ttu-id="71341-160">Impacto de la puntuación de exposición de este software</span><span class="sxs-lookup"><span data-stu-id="71341-160">Exposure score impact of this software</span></span>
