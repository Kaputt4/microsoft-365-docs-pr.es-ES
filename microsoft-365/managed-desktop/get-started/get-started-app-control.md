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
# <a name="get-started-with-app-control"></a><span data-ttu-id="8cd31-103">Introducción al control de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="8cd31-103">Get started with app control</span></span>

<span data-ttu-id="8cd31-104">Antes de habilitar el control de aplicaciones en el entorno, asegúrese de revisar y comprender [cómo Microsoft Managed Desktop lo implementa](../service-description/app-control.md) y sus roles y responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="8cd31-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="8cd31-105">Microsoft Managed Desktop simplifica el control de aplicaciones, ya que se ocupa de los aspectos más desafiantes de obtener una directiva de base segura.</span><span class="sxs-lookup"><span data-stu-id="8cd31-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="8cd31-106">Los administradores de TI todavía deben probar sus aplicaciones en el anillo de prueba y revisar los registros en busca de advertencias o errores.</span><span class="sxs-lookup"><span data-stu-id="8cd31-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="8cd31-107">Si una aplicación necesita una exención, puede archivar una solicitud, o la operación de escritorio administrada de Microsoft podría, en función de quién la detecte primero.</span><span class="sxs-lookup"><span data-stu-id="8cd31-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="8cd31-108">Implementación inicial de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="8cd31-108">Initial deployment of apps</span></span>

<span data-ttu-id="8cd31-109">Cuando se implementan las aplicaciones por primera vez, las necesidades del escritorio administrado por Microsoft deben evaluar su comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="8cd31-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="8cd31-110">Los pasos exactos para habilitar el control de aplicaciones dependen de si ya se han implementado los dispositivos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="8cd31-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="8cd31-111">Dispositivos que todavía no están en uso</span><span class="sxs-lookup"><span data-stu-id="8cd31-111">Devices not yet in use</span></span>

<span data-ttu-id="8cd31-112">Si aún no tiene ningún dispositivo en uso, abra un vale de servicio con Microsoft Managed Desktop Operations solicitando que se active el control de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8cd31-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="8cd31-113">Las operaciones implementarán progresivamente las directivas en los grupos de implementación siguiendo esta programación:</span><span class="sxs-lookup"><span data-stu-id="8cd31-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="8cd31-114">Grupo de implementación</span><span class="sxs-lookup"><span data-stu-id="8cd31-114">Deployment group</span></span>  |<span data-ttu-id="8cd31-115">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="8cd31-115">Policy type</span></span>  |<span data-ttu-id="8cd31-116">Timing</span><span class="sxs-lookup"><span data-stu-id="8cd31-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8cd31-117">Prueba</span><span class="sxs-lookup"><span data-stu-id="8cd31-117">Test</span></span>     |  <span data-ttu-id="8cd31-118">Auditoría</span><span class="sxs-lookup"><span data-stu-id="8cd31-118">Audit</span></span>       |  <span data-ttu-id="8cd31-119">Día 0</span><span class="sxs-lookup"><span data-stu-id="8cd31-119">Day 0</span></span>       |
|<span data-ttu-id="8cd31-120">Primero</span><span class="sxs-lookup"><span data-stu-id="8cd31-120">First</span></span>     | <span data-ttu-id="8cd31-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="8cd31-121">Enforced</span></span>        | <span data-ttu-id="8cd31-122">Día 1</span><span class="sxs-lookup"><span data-stu-id="8cd31-122">Day 1</span></span>        |
|<span data-ttu-id="8cd31-123">Rápida</span><span class="sxs-lookup"><span data-stu-id="8cd31-123">Fast</span></span>     | <span data-ttu-id="8cd31-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="8cd31-124">Enforced</span></span>        |  <span data-ttu-id="8cd31-125">Día 2</span><span class="sxs-lookup"><span data-stu-id="8cd31-125">Day 2</span></span>       |
|<span data-ttu-id="8cd31-126">Amplias</span><span class="sxs-lookup"><span data-stu-id="8cd31-126">Broad</span></span>     | <span data-ttu-id="8cd31-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="8cd31-127">Enforced</span></span>        |  <span data-ttu-id="8cd31-128">Día 3</span><span class="sxs-lookup"><span data-stu-id="8cd31-128">Day 3</span></span>       |

<span data-ttu-id="8cd31-129">Siempre puede abrir otra solicitud de servicio para pausar o revertir una parte de esta implementación en cualquier momento durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="8cd31-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="8cd31-130">Dispositivos que ya están en uso</span><span class="sxs-lookup"><span data-stu-id="8cd31-130">Devices already in use</span></span>

<span data-ttu-id="8cd31-131">Si ya tiene al menos un dispositivo de escritorio administrado de Microsoft en uso, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8cd31-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="8cd31-132">Abrir un vale de servicio con Microsoft Managed Desktop Operations solicitando que se active el control de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8cd31-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="8cd31-133">Operaciones implementará una [Directiva de auditoría](../service-description/app-control.md#audit-policy) para todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8cd31-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="8cd31-134">[Pruebe las aplicaciones](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver si alguna se bloquea.</span><span class="sxs-lookup"><span data-stu-id="8cd31-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="8cd31-135">Si se bloquea una aplicación, abra una [solicitud de firmante](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="8cd31-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="8cd31-136">Una vez que haya completado las pruebas (independientemente de los resultados), avise a las operaciones y anote las solicitudes de firma pendientes.</span><span class="sxs-lookup"><span data-stu-id="8cd31-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="8cd31-137">Las operaciones implementarán progresivamente las directivas en los grupos de implementación siguiendo esta programación:</span><span class="sxs-lookup"><span data-stu-id="8cd31-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="8cd31-138">Grupo de implementación</span><span class="sxs-lookup"><span data-stu-id="8cd31-138">Deployment group</span></span>  |<span data-ttu-id="8cd31-139">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="8cd31-139">Policy type</span></span>  |<span data-ttu-id="8cd31-140">Timing</span><span class="sxs-lookup"><span data-stu-id="8cd31-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8cd31-141">Prueba</span><span class="sxs-lookup"><span data-stu-id="8cd31-141">Test</span></span>     |  <span data-ttu-id="8cd31-142">Auditoría</span><span class="sxs-lookup"><span data-stu-id="8cd31-142">Audit</span></span>       |  <span data-ttu-id="8cd31-143">Día 0</span><span class="sxs-lookup"><span data-stu-id="8cd31-143">Day 0</span></span>       |
|<span data-ttu-id="8cd31-144">Primero</span><span class="sxs-lookup"><span data-stu-id="8cd31-144">First</span></span>     | <span data-ttu-id="8cd31-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="8cd31-145">Enforced</span></span>        | <span data-ttu-id="8cd31-146">Día 1</span><span class="sxs-lookup"><span data-stu-id="8cd31-146">Day 1</span></span>        |
|<span data-ttu-id="8cd31-147">Rápida</span><span class="sxs-lookup"><span data-stu-id="8cd31-147">Fast</span></span>     | <span data-ttu-id="8cd31-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="8cd31-148">Enforced</span></span>        |  <span data-ttu-id="8cd31-149">Pausado, implementación a petición</span><span class="sxs-lookup"><span data-stu-id="8cd31-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="8cd31-150">Amplias</span><span class="sxs-lookup"><span data-stu-id="8cd31-150">Broad</span></span>     | <span data-ttu-id="8cd31-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="8cd31-151">Enforced</span></span>        |  <span data-ttu-id="8cd31-152">Pausado, implementación a petición</span><span class="sxs-lookup"><span data-stu-id="8cd31-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="8cd31-153">Siempre puede abrir otra solicitud de servicio para pausar o revertir una parte de esta implementación en cualquier momento durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="8cd31-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



