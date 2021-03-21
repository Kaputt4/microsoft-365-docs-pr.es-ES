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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917645"
---
# <a name="work-with-app-control"></a><span data-ttu-id="cae0c-103">Usar el control de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="cae0c-103">Work with app control</span></span>

<span data-ttu-id="cae0c-104">Una vez implementado el control de la aplicación en el entorno, tanto tú como las operaciones de escritorio administrado de Microsoft tienen responsabilidades continuas.</span><span class="sxs-lookup"><span data-stu-id="cae0c-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="cae0c-105">Por ejemplo, es posible que quieras agregar una nueva aplicación en el entorno o agregar (o quitar) un firmante de confianza.</span><span class="sxs-lookup"><span data-stu-id="cae0c-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="cae0c-106">Para mejorar la seguridad, todas las aplicaciones deben estar firmadas con código antes de liberarlas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cae0c-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="cae0c-107">Los detalles del editor de una aplicación incluyen información sobre el firmante.</span><span class="sxs-lookup"><span data-stu-id="cae0c-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="cae0c-108">Agregar una nueva aplicación</span><span class="sxs-lookup"><span data-stu-id="cae0c-108">Add a new app</span></span>

<span data-ttu-id="cae0c-109">Para agregar una nueva aplicación, sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cae0c-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="cae0c-110">Agregar la aplicación a [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="cae0c-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="cae0c-111">Implementa la aplicación en cualquier dispositivo en el anillo de prueba.</span><span class="sxs-lookup"><span data-stu-id="cae0c-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="cae0c-112">Prueba la aplicación según tus procesos empresariales estándar.</span><span class="sxs-lookup"><span data-stu-id="cae0c-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="cae0c-113">Comprueba Visor de eventos en Registros de aplicaciones y **servicios\Microsoft\Windows\AppLocker** y busca cualquier **evento 8003** **o 8006.**</span><span class="sxs-lookup"><span data-stu-id="cae0c-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="cae0c-114">Estos eventos indican que la aplicación se bloquearía.</span><span class="sxs-lookup"><span data-stu-id="cae0c-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="cae0c-115">Para obtener más información acerca de todos los eventos de App Locker y sus significados, consulta [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="cae0c-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="cae0c-116">Si encuentra alguno de estos eventos, abra una solicitud de firmante con Operaciones de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cae0c-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="cae0c-117">Agregar (o quitar) un firmante de confianza</span><span class="sxs-lookup"><span data-stu-id="cae0c-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="cae0c-118">Cuando abra una solicitud de firmante, primero deberá proporcionar algunos detalles importantes del editor.</span><span class="sxs-lookup"><span data-stu-id="cae0c-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="cae0c-119">A continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cae0c-119">Then follow these steps:</span></span>

1. <span data-ttu-id="cae0c-120">[Recopilar detalles del editor](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="cae0c-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="cae0c-121">Abra un vale con Operaciones de escritorio administrado de Microsoft para solicitar la regla de firmante e incluya los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="cae0c-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="cae0c-122">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="cae0c-122">Application name</span></span> 
    - <span data-ttu-id="cae0c-123">Versión de la aplicación</span><span class="sxs-lookup"><span data-stu-id="cae0c-123">Application version</span></span> 
    - <span data-ttu-id="cae0c-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="cae0c-124">Description</span></span> 
    - <span data-ttu-id="cae0c-125">Tipo de cambio ("agregar" o "quitar")</span><span class="sxs-lookup"><span data-stu-id="cae0c-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="cae0c-126">Detalles del publicador (por ejemplo: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="cae0c-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="cae0c-127">Para quitar la confianza de una aplicación, siga los mismos pasos, pero establezca **Cambiar tipo** para *quitar*.</span><span class="sxs-lookup"><span data-stu-id="cae0c-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="cae0c-128">Las operaciones implementarán de forma progresiva directivas en grupos de implementación siguiendo esta programación:</span><span class="sxs-lookup"><span data-stu-id="cae0c-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="cae0c-129">Grupo de implementación</span><span class="sxs-lookup"><span data-stu-id="cae0c-129">Deployment group</span></span>  |<span data-ttu-id="cae0c-130">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="cae0c-130">Policy type</span></span>  |<span data-ttu-id="cae0c-131">Timing</span><span class="sxs-lookup"><span data-stu-id="cae0c-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cae0c-132">Prueba</span><span class="sxs-lookup"><span data-stu-id="cae0c-132">Test</span></span>     |  <span data-ttu-id="cae0c-133">Auditoría</span><span class="sxs-lookup"><span data-stu-id="cae0c-133">Audit</span></span>       |  <span data-ttu-id="cae0c-134">Día 0</span><span class="sxs-lookup"><span data-stu-id="cae0c-134">Day 0</span></span>       |
|<span data-ttu-id="cae0c-135">Primero</span><span class="sxs-lookup"><span data-stu-id="cae0c-135">First</span></span>     | <span data-ttu-id="cae0c-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="cae0c-136">Enforced</span></span>        | <span data-ttu-id="cae0c-137">Día 1</span><span class="sxs-lookup"><span data-stu-id="cae0c-137">Day 1</span></span>        |
|<span data-ttu-id="cae0c-138">Rápida</span><span class="sxs-lookup"><span data-stu-id="cae0c-138">Fast</span></span>     | <span data-ttu-id="cae0c-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="cae0c-139">Enforced</span></span>        |  <span data-ttu-id="cae0c-140">Día 2</span><span class="sxs-lookup"><span data-stu-id="cae0c-140">Day 2</span></span>       |
|<span data-ttu-id="cae0c-141">Amplias</span><span class="sxs-lookup"><span data-stu-id="cae0c-141">Broad</span></span>     | <span data-ttu-id="cae0c-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="cae0c-142">Enforced</span></span>        |  <span data-ttu-id="cae0c-143">Día 3</span><span class="sxs-lookup"><span data-stu-id="cae0c-143">Day 3</span></span>       |


<span data-ttu-id="cae0c-144">Puede pausar o revertir la implementación en cualquier momento durante el lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="cae0c-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="cae0c-145">Para ello, abra otra solicitud de servicio con Operations.</span><span class="sxs-lookup"><span data-stu-id="cae0c-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="cae0c-146">Si pausa la versión de una regla de firmante, esa regla debe revertirse o completarse antes de que se pueda iniciar otra implementación.</span><span class="sxs-lookup"><span data-stu-id="cae0c-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="cae0c-147">Recopilar detalles del editor</span><span class="sxs-lookup"><span data-stu-id="cae0c-147">Gather publisher details</span></span>

<span data-ttu-id="cae0c-148">Para obtener acceso a los datos del editor de una aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cae0c-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="cae0c-149">Busque un dispositivo de Escritorio administrado de Microsoft en el anillo De prueba que tenga aplicada una directiva de modo de auditoría.</span><span class="sxs-lookup"><span data-stu-id="cae0c-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="cae0c-150">Intente instalar la aplicación en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cae0c-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="cae0c-151">Abre el Visor de eventos en ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cae0c-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="cae0c-152">En el Visor de eventos, vaya **a Registros de aplicaciones y servicios\Microsoft\Windows** y, a continuación, seleccione **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="cae0c-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="cae0c-153">Busque cualquier **evento 8003** **u 8006** y, a continuación, copie la información del evento:</span><span class="sxs-lookup"><span data-stu-id="cae0c-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="cae0c-154">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="cae0c-154">Application name</span></span> 
    - <span data-ttu-id="cae0c-155">Versión de la aplicación</span><span class="sxs-lookup"><span data-stu-id="cae0c-155">Application version</span></span> 
    - <span data-ttu-id="cae0c-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="cae0c-156">Description</span></span> 
    - <span data-ttu-id="cae0c-157">Detalles del publicador (por ejemplo: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="cae0c-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>