---
title: Introducción al control de aplicaciones
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430464"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="6e7d5-103">Introducción al control de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="6e7d5-103">Get started with app control</span></span>

<span data-ttu-id="6e7d5-104">Antes de habilitar el control de aplicaciones en su entorno, asegúrese de revisar y comprender cómo lo implementa Escritorio administrado de [Microsoft](../service-description/app-control.md) y sus roles y responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="6e7d5-105">Escritorio administrado de Microsoft simplifica el control de aplicaciones al ocuparse de los aspectos más difíciles de obtener una directiva base segura.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="6e7d5-106">Los administradores de TI aún deben probar las aplicaciones en el anillo de prueba y revisar los registros en busca de advertencias o errores.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="6e7d5-107">Si una aplicación necesita una exención, puedes presentar una solicitud, o la operación de escritorio administrado de Microsoft podría, en función de quién la detecte primero.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="6e7d5-108">Implementación inicial de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="6e7d5-108">Initial deployment of apps</span></span>

<span data-ttu-id="6e7d5-109">Al implementar aplicaciones por primera vez, Escritorio administrado de Microsoft debe evaluar su comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="6e7d5-110">Los pasos exactos para habilitar el control de aplicaciones dependen de si los dispositivos ya se han implementado en el entorno.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="6e7d5-111">Dispositivos que aún no están en uso</span><span class="sxs-lookup"><span data-stu-id="6e7d5-111">Devices not yet in use</span></span>

<span data-ttu-id="6e7d5-112">Si aún no tiene ningún dispositivo en uso, abra un vale de servicio con operaciones de Escritorio administrado de Microsoft solicitando que activemos el control de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="6e7d5-113">Las operaciones implementarán de forma progresiva directivas en grupos de implementación siguiendo esta programación:</span><span class="sxs-lookup"><span data-stu-id="6e7d5-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="6e7d5-114">Grupo de implementación</span><span class="sxs-lookup"><span data-stu-id="6e7d5-114">Deployment group</span></span>  |<span data-ttu-id="6e7d5-115">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="6e7d5-115">Policy type</span></span>  |<span data-ttu-id="6e7d5-116">Timing</span><span class="sxs-lookup"><span data-stu-id="6e7d5-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="6e7d5-117">Prueba</span><span class="sxs-lookup"><span data-stu-id="6e7d5-117">Test</span></span>     |  <span data-ttu-id="6e7d5-118">Auditoría</span><span class="sxs-lookup"><span data-stu-id="6e7d5-118">Audit</span></span>       |  <span data-ttu-id="6e7d5-119">Día 0</span><span class="sxs-lookup"><span data-stu-id="6e7d5-119">Day 0</span></span>       |
|<span data-ttu-id="6e7d5-120">Primero</span><span class="sxs-lookup"><span data-stu-id="6e7d5-120">First</span></span>     | <span data-ttu-id="6e7d5-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="6e7d5-121">Enforced</span></span>        | <span data-ttu-id="6e7d5-122">Día 1</span><span class="sxs-lookup"><span data-stu-id="6e7d5-122">Day 1</span></span>        |
|<span data-ttu-id="6e7d5-123">Rápida</span><span class="sxs-lookup"><span data-stu-id="6e7d5-123">Fast</span></span>     | <span data-ttu-id="6e7d5-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="6e7d5-124">Enforced</span></span>        |  <span data-ttu-id="6e7d5-125">Día 2</span><span class="sxs-lookup"><span data-stu-id="6e7d5-125">Day 2</span></span>       |
|<span data-ttu-id="6e7d5-126">Amplias</span><span class="sxs-lookup"><span data-stu-id="6e7d5-126">Broad</span></span>     | <span data-ttu-id="6e7d5-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="6e7d5-127">Enforced</span></span>        |  <span data-ttu-id="6e7d5-128">Día 3</span><span class="sxs-lookup"><span data-stu-id="6e7d5-128">Day 3</span></span>       |

<span data-ttu-id="6e7d5-129">Siempre puede abrir otra solicitud de servicio para pausar o revertir parte de esta implementación en cualquier momento durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="6e7d5-130">Dispositivos que ya están en uso</span><span class="sxs-lookup"><span data-stu-id="6e7d5-130">Devices already in use</span></span>

<span data-ttu-id="6e7d5-131">Si ya tiene al menos un dispositivo de Escritorio administrado de Microsoft en uso, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6e7d5-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="6e7d5-132">Abra un vale de servicio con operaciones de escritorio administrado de Microsoft solicitando que activemos el control de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="6e7d5-133">Las operaciones implementarán una [directiva de auditoría](../service-description/app-control.md#audit-policy) en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="6e7d5-134">[Pruebe las aplicaciones](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver si alguna se bloquearía.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="6e7d5-135">Si se bloqueara una aplicación, abra una solicitud [de firmante.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)</span><span class="sxs-lookup"><span data-stu-id="6e7d5-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="6e7d5-136">Una vez que haya completado las pruebas (independientemente de los resultados), notifique a las operaciones y notifique las solicitudes de firmante pendientes.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="6e7d5-137">Las operaciones implementarán de forma progresiva directivas en grupos de implementación siguiendo esta programación:</span><span class="sxs-lookup"><span data-stu-id="6e7d5-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="6e7d5-138">Grupo de implementación</span><span class="sxs-lookup"><span data-stu-id="6e7d5-138">Deployment group</span></span>  |<span data-ttu-id="6e7d5-139">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="6e7d5-139">Policy type</span></span>  |<span data-ttu-id="6e7d5-140">Timing</span><span class="sxs-lookup"><span data-stu-id="6e7d5-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="6e7d5-141">Prueba</span><span class="sxs-lookup"><span data-stu-id="6e7d5-141">Test</span></span>     |  <span data-ttu-id="6e7d5-142">Auditoría</span><span class="sxs-lookup"><span data-stu-id="6e7d5-142">Audit</span></span>       |  <span data-ttu-id="6e7d5-143">Día 0</span><span class="sxs-lookup"><span data-stu-id="6e7d5-143">Day 0</span></span>       |
|<span data-ttu-id="6e7d5-144">Primero</span><span class="sxs-lookup"><span data-stu-id="6e7d5-144">First</span></span>     | <span data-ttu-id="6e7d5-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="6e7d5-145">Enforced</span></span>        | <span data-ttu-id="6e7d5-146">Día 1</span><span class="sxs-lookup"><span data-stu-id="6e7d5-146">Day 1</span></span>        |
|<span data-ttu-id="6e7d5-147">Rápida</span><span class="sxs-lookup"><span data-stu-id="6e7d5-147">Fast</span></span>     | <span data-ttu-id="6e7d5-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="6e7d5-148">Enforced</span></span>        |  <span data-ttu-id="6e7d5-149">En pausa, lanzamiento a petición</span><span class="sxs-lookup"><span data-stu-id="6e7d5-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="6e7d5-150">Amplias</span><span class="sxs-lookup"><span data-stu-id="6e7d5-150">Broad</span></span>     | <span data-ttu-id="6e7d5-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="6e7d5-151">Enforced</span></span>        |  <span data-ttu-id="6e7d5-152">En pausa, lanzamiento a petición</span><span class="sxs-lookup"><span data-stu-id="6e7d5-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="6e7d5-153">Siempre puede abrir otra solicitud de servicio para pausar o revertir parte de esta implementación en cualquier momento durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="6e7d5-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



