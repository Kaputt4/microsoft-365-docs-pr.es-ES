---
title: Implementar la configuración configurable en Escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en Escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, implementación, implementación por fases, configuración configurable
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287806"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="cbca5-104">Implementar y realizar un seguimiento de la configuración configurable: Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="cbca5-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="cbca5-105">Después de realizar cambios en las categorías de configuración y la fase de una implementación, la página Estado de implementación le permite empezar a implementar la configuración en grupos.</span><span class="sxs-lookup"><span data-stu-id="cbca5-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="cbca5-106">Esta página muestra un resumen de cada configuración configurable.</span><span class="sxs-lookup"><span data-stu-id="cbca5-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="cbca5-107">Al abrir una categoría de configuración, puede implementar la configuración en grupos y realizar un seguimiento del progreso de estas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="cbca5-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="cbca5-108">Estados de implementación</span><span class="sxs-lookup"><span data-stu-id="cbca5-108">Deployment statuses</span></span>

<span data-ttu-id="cbca5-109">Estos son los estados que verá para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="cbca5-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="cbca5-110">Estado</span><span class="sxs-lookup"><span data-stu-id="cbca5-110">Status</span></span> | <span data-ttu-id="cbca5-111">Explicación</span><span class="sxs-lookup"><span data-stu-id="cbca5-111">Explanation</span></span>
--- | ---
<span data-ttu-id="cbca5-112">Implementar</span><span class="sxs-lookup"><span data-stu-id="cbca5-112">Deploy</span></span> | <span data-ttu-id="cbca5-113">El cambio está a la espera de implementarse en este grupo.</span><span class="sxs-lookup"><span data-stu-id="cbca5-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="cbca5-114">En curso</span><span class="sxs-lookup"><span data-stu-id="cbca5-114">In progress</span></span> | <span data-ttu-id="cbca5-115">El cambio se aplica a los dispositivos activos de este grupo.</span><span class="sxs-lookup"><span data-stu-id="cbca5-115">The change is being applied to active devices in this group.</span></span>
<span data-ttu-id="cbca5-116">Completo</span><span class="sxs-lookup"><span data-stu-id="cbca5-116">Complete</span></span> | <span data-ttu-id="cbca5-117">El cambio completado en todos los dispositivos activos de este grupo.</span><span class="sxs-lookup"><span data-stu-id="cbca5-117">The change completed on all active devices in this group.</span></span>
<span data-ttu-id="cbca5-118">Error</span><span class="sxs-lookup"><span data-stu-id="cbca5-118">Failed</span></span> | <span data-ttu-id="cbca5-119">El cambio no se pudo hacer en un 10 % de los dispositivos activos del grupo, por lo que se detuvo la implementación.</span><span class="sxs-lookup"><span data-stu-id="cbca5-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="cbca5-120">Se abrirá automáticamente una solicitud de soporte técnico con Escritorio administrado de Microsoft para solucionar problemas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="cbca5-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span>
<span data-ttu-id="cbca5-121">Reverted</span><span class="sxs-lookup"><span data-stu-id="cbca5-121">Reverted</span></span> | <span data-ttu-id="cbca5-122">El cambio se reviró al último cambio que se implementó correctamente en todos los grupos de implementación.</span><span class="sxs-lookup"><span data-stu-id="cbca5-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="cbca5-123">Implementar cambios</span><span class="sxs-lookup"><span data-stu-id="cbca5-123">Deploy changes</span></span>

<span data-ttu-id="cbca5-124">Mostraremos la imagen de fondo del escritorio en estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="cbca5-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="cbca5-125">Una vez que haya realizado una implementación, implemente los cambios desde la página Estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="cbca5-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span>

<span data-ttu-id="cbca5-126">**Para implementar cambios**</span><span class="sxs-lookup"><span data-stu-id="cbca5-126">**To deploy changes**</span></span>

1. <span data-ttu-id="cbca5-127">Inicie sesión en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="cbca5-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="cbca5-128">Busque la sección Escritorio administrado de Microsoft, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="cbca5-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="cbca5-129">En **área de trabajo** de estado de implementación, seleccione la configuración que desea implementar y, a continuación, seleccione la implementación por fases que desea implementar.</span><span class="sxs-lookup"><span data-stu-id="cbca5-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="cbca5-130">Seleccione **Implementar** para implementar el cambio en uno de los grupos de implementación.</span><span class="sxs-lookup"><span data-stu-id="cbca5-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE]
> <span data-ttu-id="cbca5-131">El icono de precaución naranja indica que hay un grupo anterior disponible para la implementación, ya que se recomienda implementar en orden.</span><span class="sxs-lookup"><span data-stu-id="cbca5-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="cbca5-132">Se recomienda implementar en grupos de implementación en este orden: Test, First, Fast y, a continuación, Broad.</span><span class="sxs-lookup"><span data-stu-id="cbca5-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="cbca5-133">Cuando los cambios se completan en cada grupo, el estado cambia a **Complete**.</span><span class="sxs-lookup"><span data-stu-id="cbca5-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="cbca5-134">Revertir implementación</span><span class="sxs-lookup"><span data-stu-id="cbca5-134">Revert deployment</span></span>

<span data-ttu-id="cbca5-135">Después de implementar un cambio, puede revertir desde **el estado de implementación**.</span><span class="sxs-lookup"><span data-stu-id="cbca5-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="cbca5-136">Cuando se revierte un cambio que está **en curso** o **completado,** se detiene la implementación actual.</span><span class="sxs-lookup"><span data-stu-id="cbca5-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="cbca5-137">La configuración volverá a la última versión que se implementó en todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="cbca5-137">The setting will revert to the last version that was deployed to all groups.</span></span>

<span data-ttu-id="cbca5-138">Mostraremos los pasos para revertir un cambio con la imagen en segundo plano de escritorio como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cbca5-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="cbca5-139">**Para revertir un cambio**</span><span class="sxs-lookup"><span data-stu-id="cbca5-139">**To revert a change**</span></span>

1. <span data-ttu-id="cbca5-140">Inicie sesión en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="cbca5-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="cbca5-141">Busque la sección Escritorio administrado de Microsoft, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="cbca5-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="cbca5-142">En **el área de trabajo** Estado de implementación, seleccione la configuración que desea revertir y, a continuación, seleccione la implementación por fases para revertir.</span><span class="sxs-lookup"><span data-stu-id="cbca5-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="cbca5-143">En **¿Necesita revertir este cambio?**, seleccione **Revertir implementación**.</span><span class="sxs-lookup"><span data-stu-id="cbca5-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="cbca5-144">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cbca5-144">Additional resources</span></span>

- [<span data-ttu-id="cbca5-145">Introducción a la configuración configurable</span><span class="sxs-lookup"><span data-stu-id="cbca5-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="cbca5-146">Referencia de parámetros configurables</span><span class="sxs-lookup"><span data-stu-id="cbca5-146">Configurable settings reference</span></span>](config-setting-ref.md) 
