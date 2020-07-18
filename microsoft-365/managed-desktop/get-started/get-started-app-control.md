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
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170714"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="9d88f-103">Introducción al control de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="9d88f-103">Get started with app control</span></span>

<span data-ttu-id="9d88f-104">Antes de habilitar el control de aplicaciones en el entorno, asegúrese de revisar y comprender [cómo Microsoft Managed Desktop lo implementa](../service-description/app-control.md) y sus roles y responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="9d88f-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="9d88f-105">Microsoft Managed Desktop simplifica el control de aplicaciones, ya que se ocupa de los aspectos más desafiantes de obtener una directiva de base segura.</span><span class="sxs-lookup"><span data-stu-id="9d88f-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="9d88f-106">Los administradores de TI todavía deben probar sus aplicaciones en el anillo de prueba y revisar los registros en busca de advertencias o errores.</span><span class="sxs-lookup"><span data-stu-id="9d88f-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="9d88f-107">Si una aplicación necesita una exención, puede archivar una solicitud, o la operación de escritorio administrada de Microsoft podría, en función de quién la detecte primero.</span><span class="sxs-lookup"><span data-stu-id="9d88f-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="9d88f-108">Implementación inicial de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="9d88f-108">Initial deployment of apps</span></span>

<span data-ttu-id="9d88f-109">Cuando se implementan las aplicaciones por primera vez, las necesidades del escritorio administrado por Microsoft deben evaluar su comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="9d88f-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="9d88f-110">Los pasos exactos para habilitar el control de aplicaciones dependen de si ya se han implementado los dispositivos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="9d88f-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="9d88f-111">Dispositivos que ya están en uso</span><span class="sxs-lookup"><span data-stu-id="9d88f-111">Devices already in use</span></span>

<span data-ttu-id="9d88f-112">Si ya tiene al menos un dispositivo de escritorio administrado de Microsoft en uso, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9d88f-112">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="9d88f-113">Abrir un vale de servicio con Microsoft Managed Desktop Operations solicitando que se active el control de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9d88f-113">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="9d88f-114">Operaciones implementará una [Directiva de auditoría](../service-description/app-control.md#audit-policy) para todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9d88f-114">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="9d88f-115">[Pruebe las aplicaciones](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver si alguna se bloquea.</span><span class="sxs-lookup"><span data-stu-id="9d88f-115">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="9d88f-116">Si se bloquea una aplicación, abra una [solicitud de firmante](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="9d88f-116">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="9d88f-117">Una vez que haya completado las pruebas (independientemente de los resultados), avise a las operaciones y anote las solicitudes de firma pendientes.</span><span class="sxs-lookup"><span data-stu-id="9d88f-117">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="9d88f-118">Las operaciones implementarán progresivamente las directivas en los grupos de implementación siguiendo esta programación:</span><span class="sxs-lookup"><span data-stu-id="9d88f-118">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="9d88f-119">Grupo de implementación</span><span class="sxs-lookup"><span data-stu-id="9d88f-119">Deployment group</span></span>  |<span data-ttu-id="9d88f-120">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="9d88f-120">Policy type</span></span>  |<span data-ttu-id="9d88f-121">Timing</span><span class="sxs-lookup"><span data-stu-id="9d88f-121">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9d88f-122">Prueba</span><span class="sxs-lookup"><span data-stu-id="9d88f-122">Test</span></span>     |  <span data-ttu-id="9d88f-123">Auditoría</span><span class="sxs-lookup"><span data-stu-id="9d88f-123">Audit</span></span>       |  <span data-ttu-id="9d88f-124">Día 0</span><span class="sxs-lookup"><span data-stu-id="9d88f-124">Day 0</span></span>       |
|<span data-ttu-id="9d88f-125">Primero</span><span class="sxs-lookup"><span data-stu-id="9d88f-125">First</span></span>     | <span data-ttu-id="9d88f-126">Enforced</span><span class="sxs-lookup"><span data-stu-id="9d88f-126">Enforced</span></span>        | <span data-ttu-id="9d88f-127">Día 1</span><span class="sxs-lookup"><span data-stu-id="9d88f-127">Day 1</span></span>        |
|<span data-ttu-id="9d88f-128">Rápida</span><span class="sxs-lookup"><span data-stu-id="9d88f-128">Fast</span></span>     | <span data-ttu-id="9d88f-129">Enforced</span><span class="sxs-lookup"><span data-stu-id="9d88f-129">Enforced</span></span>        |  <span data-ttu-id="9d88f-130">Día 3</span><span class="sxs-lookup"><span data-stu-id="9d88f-130">Day 3</span></span>       |
|<span data-ttu-id="9d88f-131">Amplias</span><span class="sxs-lookup"><span data-stu-id="9d88f-131">Broad</span></span>     | <span data-ttu-id="9d88f-132">Enforced</span><span class="sxs-lookup"><span data-stu-id="9d88f-132">Enforced</span></span>        |  <span data-ttu-id="9d88f-133">Día 7</span><span class="sxs-lookup"><span data-stu-id="9d88f-133">Day 7</span></span>       |

<span data-ttu-id="9d88f-134">Siempre puede abrir otra solicitud de servicio para pausar o revertir una parte de esta implementación en cualquier momento durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="9d88f-134">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="9d88f-135">Dispositivos que todavía no están en uso</span><span class="sxs-lookup"><span data-stu-id="9d88f-135">Devices not yet in use</span></span>

<span data-ttu-id="9d88f-136">Si aún no tiene ningún dispositivo en uso, abra un vale de servicio con Microsoft Managed Desktop Operations solicitando que se active el control de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9d88f-136">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="9d88f-137">Las operaciones implementarán progresivamente las directivas en los grupos de implementación siguiendo esta programación:</span><span class="sxs-lookup"><span data-stu-id="9d88f-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="9d88f-138">Grupo de implementación</span><span class="sxs-lookup"><span data-stu-id="9d88f-138">Deployment group</span></span>  |<span data-ttu-id="9d88f-139">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="9d88f-139">Policy type</span></span>  |<span data-ttu-id="9d88f-140">Timing</span><span class="sxs-lookup"><span data-stu-id="9d88f-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9d88f-141">Prueba</span><span class="sxs-lookup"><span data-stu-id="9d88f-141">Test</span></span>     |  <span data-ttu-id="9d88f-142">Auditoría</span><span class="sxs-lookup"><span data-stu-id="9d88f-142">Audit</span></span>       |  <span data-ttu-id="9d88f-143">Día 0</span><span class="sxs-lookup"><span data-stu-id="9d88f-143">Day 0</span></span>       |
|<span data-ttu-id="9d88f-144">Primero</span><span class="sxs-lookup"><span data-stu-id="9d88f-144">First</span></span>     | <span data-ttu-id="9d88f-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="9d88f-145">Enforced</span></span>        | <span data-ttu-id="9d88f-146">Día 1</span><span class="sxs-lookup"><span data-stu-id="9d88f-146">Day 1</span></span>        |
|<span data-ttu-id="9d88f-147">Rápida</span><span class="sxs-lookup"><span data-stu-id="9d88f-147">Fast</span></span>     | <span data-ttu-id="9d88f-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="9d88f-148">Enforced</span></span>        |  <span data-ttu-id="9d88f-149">Día 3</span><span class="sxs-lookup"><span data-stu-id="9d88f-149">Day 3</span></span>       |
|<span data-ttu-id="9d88f-150">Amplias</span><span class="sxs-lookup"><span data-stu-id="9d88f-150">Broad</span></span>     | <span data-ttu-id="9d88f-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="9d88f-151">Enforced</span></span>        |  <span data-ttu-id="9d88f-152">Día 7</span><span class="sxs-lookup"><span data-stu-id="9d88f-152">Day 7</span></span>       |

<span data-ttu-id="9d88f-153">Siempre puede abrir otra solicitud de servicio para pausar o revertir una parte de esta implementación en cualquier momento durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="9d88f-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

