---
title: Usar el control de aplicaciones
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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289464"
---
# <a name="work-with-app-control"></a><span data-ttu-id="0ad5a-103">Usar el control de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0ad5a-103">Work with app control</span></span>

<span data-ttu-id="0ad5a-104">Una vez que se haya implementado el control de aplicaciones en el entorno, tanto usted como las operaciones de escritorio administradas de Microsoft tienen responsabilidades en curso.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="0ad5a-105">Por ejemplo, es posible que quiera agregar una nueva aplicación en el entorno o agregar (o quitar) un firmante de confianza.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="0ad5a-106">Para mejorar la seguridad, todas las aplicaciones deben estar firmadas con código antes de liberarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="0ad5a-107">Los detalles del publicador de una aplicación incluyen información sobre el firmante.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="0ad5a-108">Agregar una nueva aplicación</span><span class="sxs-lookup"><span data-stu-id="0ad5a-108">Add a new app</span></span>

<span data-ttu-id="0ad5a-109">Para agregar una nueva aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0ad5a-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="0ad5a-110">Agregue la aplicación a [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="0ad5a-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="0ad5a-111">Implemente la aplicación en cualquier dispositivo en el anillo de prueba.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="0ad5a-112">Pruebe la aplicación de acuerdo con los procesos de negocio estándar.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="0ad5a-113">Consulte el visor de eventos en **aplicaciones y servicios Logs\Microsoft\Windows\AppLocker**, buscando los eventos **8003** o **8006** .</span><span class="sxs-lookup"><span data-stu-id="0ad5a-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="0ad5a-114">Estos eventos indican que la aplicación estaría bloqueada.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="0ad5a-115">Para obtener más información sobre todos los eventos del bloqueador de aplicaciones y sus significados, vea [using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="0ad5a-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="0ad5a-116">Si encuentra alguno de estos eventos, abra una solicitud de firmante con Microsoft Managed Desktop Operations.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="0ad5a-117">Agregar (o quitar) un firmante de confianza</span><span class="sxs-lookup"><span data-stu-id="0ad5a-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="0ad5a-118">Al abrir una solicitud de firmante, primero deberá proporcionar algunos detalles importantes de Publisher.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="0ad5a-119">A continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0ad5a-119">Then follow these steps:</span></span>

1. <span data-ttu-id="0ad5a-120">[Recopilar detalles de Publisher](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="0ad5a-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="0ad5a-121">Abra un vale con las operaciones de escritorio administradas de Microsoft para solicitar la regla de firmante e incluya los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="0ad5a-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="0ad5a-122">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0ad5a-122">Application name</span></span> 
    - <span data-ttu-id="0ad5a-123">Versión de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0ad5a-123">Application version</span></span> 
    - <span data-ttu-id="0ad5a-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ad5a-124">Description</span></span> 
    - <span data-ttu-id="0ad5a-125">Tipo de cambio ("agregar" o "quitar")</span><span class="sxs-lookup"><span data-stu-id="0ad5a-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="0ad5a-126">Detalles de la editorial (por ejemplo: "O = <publisher name> , L = <location> , S = estado, C = país")</span><span class="sxs-lookup"><span data-stu-id="0ad5a-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="0ad5a-127">Para quitar la confianza de una aplicación, siga los mismos pasos, pero establezca **tipo de cambio** en *quitar*.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="0ad5a-128">Las operaciones implementarán progresivamente las directivas en los grupos de implementación siguiendo esta programación:</span><span class="sxs-lookup"><span data-stu-id="0ad5a-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="0ad5a-129">Grupo de implementación</span><span class="sxs-lookup"><span data-stu-id="0ad5a-129">Deployment group</span></span>  |<span data-ttu-id="0ad5a-130">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="0ad5a-130">Policy type</span></span>  |<span data-ttu-id="0ad5a-131">Timing</span><span class="sxs-lookup"><span data-stu-id="0ad5a-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0ad5a-132">Prueba</span><span class="sxs-lookup"><span data-stu-id="0ad5a-132">Test</span></span>     |  <span data-ttu-id="0ad5a-133">Auditoría</span><span class="sxs-lookup"><span data-stu-id="0ad5a-133">Audit</span></span>       |  <span data-ttu-id="0ad5a-134">Día 0</span><span class="sxs-lookup"><span data-stu-id="0ad5a-134">Day 0</span></span>       |
|<span data-ttu-id="0ad5a-135">Primero</span><span class="sxs-lookup"><span data-stu-id="0ad5a-135">First</span></span>     | <span data-ttu-id="0ad5a-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="0ad5a-136">Enforced</span></span>        | <span data-ttu-id="0ad5a-137">Día 1</span><span class="sxs-lookup"><span data-stu-id="0ad5a-137">Day 1</span></span>        |
|<span data-ttu-id="0ad5a-138">Rápida</span><span class="sxs-lookup"><span data-stu-id="0ad5a-138">Fast</span></span>     | <span data-ttu-id="0ad5a-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="0ad5a-139">Enforced</span></span>        |  <span data-ttu-id="0ad5a-140">Día 2</span><span class="sxs-lookup"><span data-stu-id="0ad5a-140">Day 2</span></span>       |
|<span data-ttu-id="0ad5a-141">Amplias</span><span class="sxs-lookup"><span data-stu-id="0ad5a-141">Broad</span></span>     | <span data-ttu-id="0ad5a-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="0ad5a-142">Enforced</span></span>        |  <span data-ttu-id="0ad5a-143">Día 3</span><span class="sxs-lookup"><span data-stu-id="0ad5a-143">Day 3</span></span>       |


<span data-ttu-id="0ad5a-144">Puede pausar o revertir la implementación en cualquier momento durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="0ad5a-145">Para ello, abra otra solicitud de servicio con operaciones.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="0ad5a-146">Si pausa la liberación de una regla de firmante, dicha regla debe revertirse o completarse antes de que se pueda iniciar otra implementación.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="0ad5a-147">Recopilar detalles de Publisher</span><span class="sxs-lookup"><span data-stu-id="0ad5a-147">Gather publisher details</span></span>

<span data-ttu-id="0ad5a-148">Para obtener acceso a los datos de Publisher para una aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0ad5a-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="0ad5a-149">Busque un dispositivo de escritorio administrado por Microsoft en el anillo de prueba que tiene una directiva de modo de auditoría aplicada.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="0ad5a-150">Intente instalar la aplicación en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="0ad5a-151">Abra el visor de eventos en ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="0ad5a-152">En el visor de eventos, vaya a **Logs\Microsoft\Windows de servicios y aplicaciones**y, a continuación, seleccione **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="0ad5a-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="0ad5a-153">Busque cualquier evento **8003** o **8006** y, a continuación, copie la información del evento:</span><span class="sxs-lookup"><span data-stu-id="0ad5a-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="0ad5a-154">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0ad5a-154">Application name</span></span> 
    - <span data-ttu-id="0ad5a-155">Versión de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0ad5a-155">Application version</span></span> 
    - <span data-ttu-id="0ad5a-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ad5a-156">Description</span></span> 
    - <span data-ttu-id="0ad5a-157">Detalles de la editorial (por ejemplo: "O = <publisher name> , L = <location> , S = estado, C = país")</span><span class="sxs-lookup"><span data-stu-id="0ad5a-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
