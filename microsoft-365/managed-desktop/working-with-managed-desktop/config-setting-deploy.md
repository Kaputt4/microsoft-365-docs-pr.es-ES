---
title: Implementar opciones configurables en el escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en el escritorio administrado de Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, implementar, implementación por fases, configuración configurable
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: bfa769cab9f8d812fa2533232f66b0d4f8a4edb7
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390517"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="c52ba-104">Implementar y realizar un seguimiento de las opciones configurables-escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="c52ba-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="c52ba-105">Después de realizar cambios en las categorías de configuración y ensayar una implementación, la página estado de implementación le permite comenzar a implementar la configuración en grupos.</span><span class="sxs-lookup"><span data-stu-id="c52ba-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="c52ba-106">En esta página se muestra un resumen de cada configuración configurable.</span><span class="sxs-lookup"><span data-stu-id="c52ba-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="c52ba-107">Al abrir una categoría de configuración, puede implementar la configuración en grupos y realizar un seguimiento del progreso de estas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="c52ba-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="c52ba-108">Estados de implementación</span><span class="sxs-lookup"><span data-stu-id="c52ba-108">Deployment statuses</span></span> 

<span data-ttu-id="c52ba-109">Estos son los statues que verá para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="c52ba-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="c52ba-110">Estado</span><span class="sxs-lookup"><span data-stu-id="c52ba-110">Status</span></span>  | <span data-ttu-id="c52ba-111">Explicación</span><span class="sxs-lookup"><span data-stu-id="c52ba-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="c52ba-112">Implementación</span><span class="sxs-lookup"><span data-stu-id="c52ba-112">Deploy</span></span> | <span data-ttu-id="c52ba-113">El cambio está esperando a que se implemente en este grupo.</span><span class="sxs-lookup"><span data-stu-id="c52ba-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="c52ba-114">En curso</span><span class="sxs-lookup"><span data-stu-id="c52ba-114">In progress</span></span> | <span data-ttu-id="c52ba-115">El cambio se aplica a los dispositivos activos en este grupo.</span><span class="sxs-lookup"><span data-stu-id="c52ba-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="c52ba-116">Completar</span><span class="sxs-lookup"><span data-stu-id="c52ba-116">Complete</span></span> | <span data-ttu-id="c52ba-117">El cambio se completó en todos los dispositivos activos de este grupo.</span><span class="sxs-lookup"><span data-stu-id="c52ba-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="c52ba-118">Failed</span><span class="sxs-lookup"><span data-stu-id="c52ba-118">Failed</span></span> | <span data-ttu-id="c52ba-119">Se produjo un error en el cambio en un 10% de los dispositivos activos del grupo, por lo que se detuvo la implementación.</span><span class="sxs-lookup"><span data-stu-id="c52ba-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="c52ba-120">Se abrirá automáticamente una solicitud de soporte técnico con las operaciones de escritorio administradas de Microsoft para solucionar problemas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="c52ba-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="c52ba-121">Revierten</span><span class="sxs-lookup"><span data-stu-id="c52ba-121">Reverted</span></span> | <span data-ttu-id="c52ba-122">El cambio se revirtió al último cambio que se implementó correctamente en todos los grupos de implementación.</span><span class="sxs-lookup"><span data-stu-id="c52ba-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="c52ba-123">Implementar cambios</span><span class="sxs-lookup"><span data-stu-id="c52ba-123">Deploy changes</span></span>

<span data-ttu-id="c52ba-124">En estas instrucciones se mostrará la imagen de fondo del escritorio.</span><span class="sxs-lookup"><span data-stu-id="c52ba-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="c52ba-125">Una vez que haya ensayado una implementación, implemente los cambios desde la página estado de la implementación.</span><span class="sxs-lookup"><span data-stu-id="c52ba-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="c52ba-126">**Para implementar los cambios**</span><span class="sxs-lookup"><span data-stu-id="c52ba-126">**To deploy changes**</span></span>

1. <span data-ttu-id="c52ba-127">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c52ba-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c52ba-128">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="c52ba-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c52ba-129">En el área de trabajo del **Estado de implementación** , seleccione la configuración que desee implementar y, a continuación, seleccione la implementación preconfigurada que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="c52ba-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="c52ba-130">Seleccione **implementar** para implementar el cambio en uno de los grupos de implementación.</span><span class="sxs-lookup"><span data-stu-id="c52ba-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

![Introducción al estado de implementación de configuración configurable](images/deploy-cs-overview.png)

<span data-ttu-id="c52ba-132">Microsoft Managed Desktop recomienda implementar en grupos de implementación en este orden: test, First, Fast y, a continuación, general.</span><span class="sxs-lookup"><span data-stu-id="c52ba-132">Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="c52ba-133">Cuando se completen los cambios en cada grupo, el estado cambiará a **completa**.</span><span class="sxs-lookup"><span data-stu-id="c52ba-133">When changes complete in each group, the status changes to **Complete**.</span></span>

![Implementación de la configuración configurable completada](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="c52ba-135">Revertir la implementación</span><span class="sxs-lookup"><span data-stu-id="c52ba-135">Revert deployment</span></span>

<span data-ttu-id="c52ba-136">Después de implementar un cambio, puede revertir el estado de **implementación**.</span><span class="sxs-lookup"><span data-stu-id="c52ba-136">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="c52ba-137">Cuando se revierte un cambio que está **en curso** o **completado**, la implementación actual se detiene.</span><span class="sxs-lookup"><span data-stu-id="c52ba-137">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="c52ba-138">La configuración se revertirá a la última versión que se implementó en todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="c52ba-138">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="c52ba-139">Mostraremos los pasos para revertir un cambio con la imagen de fondo de escritorio como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c52ba-139">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="c52ba-140">**Para revertir un cambio**</span><span class="sxs-lookup"><span data-stu-id="c52ba-140">**To revert a change**</span></span>
1. <span data-ttu-id="c52ba-141">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c52ba-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c52ba-142">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="c52ba-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c52ba-143">En el área de trabajo del **Estado de implementación** , seleccione la configuración que desea revertir y, a continuación, seleccione la implementación preconfigurada que se va a revertir.</span><span class="sxs-lookup"><span data-stu-id="c52ba-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="c52ba-144">En **es necesario revertir este cambio**, seleccione **revertir la implementación**.</span><span class="sxs-lookup"><span data-stu-id="c52ba-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Reversión de implementación de la configuración configurable](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="c52ba-146">Otros recursos</span><span class="sxs-lookup"><span data-stu-id="c52ba-146">Additional resources</span></span>
- [<span data-ttu-id="c52ba-147">Información general de configuración configurable</span><span class="sxs-lookup"><span data-stu-id="c52ba-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="c52ba-148">Referencia de opciones configurables</span><span class="sxs-lookup"><span data-stu-id="c52ba-148">Configurable settings reference</span></span>](config-setting-ref.md) 
