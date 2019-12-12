---
title: Implementar opciones configurables en el escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en el escritorio administrado de Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, implementar, implementación por fases, configuración configurable
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 244070c7fd2d5c98f87990bcb4ef6de96ca5a90c
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962247"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="58f78-104">Implementar y realizar un seguimiento de las opciones configurables-escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="58f78-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="58f78-105">Después de realizar cambios en las categorías de configuración y ensayar una implementación, la página estado de implementación le permite comenzar a implementar la configuración en grupos.</span><span class="sxs-lookup"><span data-stu-id="58f78-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="58f78-106">En esta página se muestra un resumen de cada configuración configurable.</span><span class="sxs-lookup"><span data-stu-id="58f78-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="58f78-107">Al abrir una categoría de configuración, puede implementar la configuración en grupos y realizar un seguimiento del progreso de estas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="58f78-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="58f78-108">Estados de implementación</span><span class="sxs-lookup"><span data-stu-id="58f78-108">Deployment statuses</span></span> 

<span data-ttu-id="58f78-109">Estos son los Estados que verá para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="58f78-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="58f78-110">Estado</span><span class="sxs-lookup"><span data-stu-id="58f78-110">Status</span></span>  | <span data-ttu-id="58f78-111">Explicación</span><span class="sxs-lookup"><span data-stu-id="58f78-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="58f78-112">Implementación</span><span class="sxs-lookup"><span data-stu-id="58f78-112">Deploy</span></span> | <span data-ttu-id="58f78-113">El cambio está esperando a que se implemente en este grupo.</span><span class="sxs-lookup"><span data-stu-id="58f78-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="58f78-114">En curso</span><span class="sxs-lookup"><span data-stu-id="58f78-114">In progress</span></span> | <span data-ttu-id="58f78-115">El cambio se aplica a los dispositivos activos en este grupo.</span><span class="sxs-lookup"><span data-stu-id="58f78-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="58f78-116">Completar</span><span class="sxs-lookup"><span data-stu-id="58f78-116">Complete</span></span> | <span data-ttu-id="58f78-117">El cambio se completó en todos los dispositivos activos de este grupo.</span><span class="sxs-lookup"><span data-stu-id="58f78-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="58f78-118">Error</span><span class="sxs-lookup"><span data-stu-id="58f78-118">Failed</span></span> | <span data-ttu-id="58f78-119">Se produjo un error en el cambio en un 10% de los dispositivos activos del grupo, por lo que se detuvo la implementación.</span><span class="sxs-lookup"><span data-stu-id="58f78-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="58f78-120">Se abrirá automáticamente una solicitud de soporte técnico con las operaciones de escritorio administradas de Microsoft para solucionar problemas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="58f78-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="58f78-121">Revierten</span><span class="sxs-lookup"><span data-stu-id="58f78-121">Reverted</span></span> | <span data-ttu-id="58f78-122">El cambio se revirtió al último cambio que se implementó correctamente en todos los grupos de implementación.</span><span class="sxs-lookup"><span data-stu-id="58f78-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="58f78-123">Implementar cambios</span><span class="sxs-lookup"><span data-stu-id="58f78-123">Deploy changes</span></span>

<span data-ttu-id="58f78-124">En estas instrucciones se mostrará la imagen de fondo del escritorio.</span><span class="sxs-lookup"><span data-stu-id="58f78-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="58f78-125">Una vez que haya ensayado una implementación, implemente los cambios desde la página estado de la implementación.</span><span class="sxs-lookup"><span data-stu-id="58f78-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="58f78-126">**Para implementar los cambios**</span><span class="sxs-lookup"><span data-stu-id="58f78-126">**To deploy changes**</span></span>

1. <span data-ttu-id="58f78-127">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="58f78-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="58f78-128">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="58f78-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="58f78-129">En el área de trabajo del **Estado de implementación** , seleccione la configuración que desee implementar y, a continuación, seleccione la implementación preconfigurada que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="58f78-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="58f78-130">Seleccione **implementar** para implementar el cambio en uno de los grupos de implementación.</span><span class="sxs-lookup"><span data-stu-id="58f78-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="58f78-131">![Área de trabajo de estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="58f78-131">![Deployment status workspace.</span></span> <span data-ttu-id="58f78-132">Panel sitios de confianza a la derecha.</span><span class="sxs-lookup"><span data-stu-id="58f78-132">Trusted sites pane on the right.</span></span> <span data-ttu-id="58f78-133">En la sección grupos de implementación hay tres columnas: grupos de implementación, dispositivos y estado.</span><span class="sxs-lookup"><span data-stu-id="58f78-133">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="58f78-134">En la columna Estado, se resalta "implementar".](images/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="58f78-134">In the status column, "deploy" is highlighted.](images/1deployedit.png)</span></span>
<span data-ttu-id="58f78-135">Se recomienda implementar en los grupos de implementación en este orden: probar, primero, rápido y, a continuación, general.</span><span class="sxs-lookup"><span data-stu-id="58f78-135">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="58f78-136">Cuando se completen los cambios en cada grupo, el estado cambiará a **completa**.</span><span class="sxs-lookup"><span data-stu-id="58f78-136">When changes complete in each group, the status changes to **Complete**.</span></span>

![Área de trabajo del estado de implementación con columnas para la fecha actualizada, versión, prueba, primera, rápida y amplia.](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="58f78-139">Revertir la implementación</span><span class="sxs-lookup"><span data-stu-id="58f78-139">Revert deployment</span></span>

<span data-ttu-id="58f78-140">Después de implementar un cambio, puede revertir el estado de **implementación**.</span><span class="sxs-lookup"><span data-stu-id="58f78-140">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="58f78-141">Cuando se revierte un cambio que está **en curso** o **completado**, la implementación actual se detiene.</span><span class="sxs-lookup"><span data-stu-id="58f78-141">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="58f78-142">La configuración se revertirá a la última versión que se implementó en todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="58f78-142">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="58f78-143">Mostraremos los pasos para revertir un cambio con la imagen de fondo de escritorio como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="58f78-143">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="58f78-144">**Para revertir un cambio**</span><span class="sxs-lookup"><span data-stu-id="58f78-144">**To revert a change**</span></span>
1. <span data-ttu-id="58f78-145">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="58f78-145">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="58f78-146">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="58f78-146">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="58f78-147">En el área de trabajo del **Estado de implementación** , seleccione la configuración que desea revertir y, a continuación, seleccione la implementación preconfigurada que se va a revertir.</span><span class="sxs-lookup"><span data-stu-id="58f78-147">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="58f78-148">En **¿necesita revertir este cambio?**, seleccione **revertir implementación**.</span><span class="sxs-lookup"><span data-stu-id="58f78-148">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![Área de trabajo de estado de implementación.](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="58f78-152">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="58f78-152">Additional resources</span></span>
- [<span data-ttu-id="58f78-153">Información general de configuración configurable</span><span class="sxs-lookup"><span data-stu-id="58f78-153">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="58f78-154">Referencia de parámetros configurables</span><span class="sxs-lookup"><span data-stu-id="58f78-154">Configurable settings reference</span></span>](config-setting-ref.md) 
