---
title: Implementar opciones configurables en el escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en el escritorio administrado de Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, implementar, implementación por fases, configuración configurable
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7e3827dc12c04d2c7952f9321a70714691c5ed47
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012305"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="f880d-104">Implementar y realizar un seguimiento de las opciones configurables-escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="f880d-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="f880d-105">Después de realizar cambios en las categorías de configuración y ensayar una implementación, la página estado de implementación le permite comenzar a implementar la configuración en grupos.</span><span class="sxs-lookup"><span data-stu-id="f880d-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="f880d-106">En esta página se muestra un resumen de cada configuración configurable.</span><span class="sxs-lookup"><span data-stu-id="f880d-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="f880d-107">Al abrir una categoría de configuración, puede implementar la configuración en grupos y realizar un seguimiento del progreso de estas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="f880d-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="f880d-108">Estados de implementación</span><span class="sxs-lookup"><span data-stu-id="f880d-108">Deployment statuses</span></span> 

<span data-ttu-id="f880d-109">Estos son los Estados que verá para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="f880d-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="f880d-110">Estado</span><span class="sxs-lookup"><span data-stu-id="f880d-110">Status</span></span>  | <span data-ttu-id="f880d-111">Explicación</span><span class="sxs-lookup"><span data-stu-id="f880d-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="f880d-112">Implementar</span><span class="sxs-lookup"><span data-stu-id="f880d-112">Deploy</span></span> | <span data-ttu-id="f880d-113">El cambio está esperando a que se implemente en este grupo.</span><span class="sxs-lookup"><span data-stu-id="f880d-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="f880d-114">En curso</span><span class="sxs-lookup"><span data-stu-id="f880d-114">In progress</span></span> | <span data-ttu-id="f880d-115">El cambio se aplica a los dispositivos activos en este grupo.</span><span class="sxs-lookup"><span data-stu-id="f880d-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="f880d-116">Completar</span><span class="sxs-lookup"><span data-stu-id="f880d-116">Complete</span></span> | <span data-ttu-id="f880d-117">El cambio se completó en todos los dispositivos activos de este grupo.</span><span class="sxs-lookup"><span data-stu-id="f880d-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="f880d-118">Error</span><span class="sxs-lookup"><span data-stu-id="f880d-118">Failed</span></span> | <span data-ttu-id="f880d-119">Se produjo un error en el cambio en un 10% de los dispositivos activos del grupo, por lo que se detuvo la implementación.</span><span class="sxs-lookup"><span data-stu-id="f880d-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="f880d-120">Se abrirá automáticamente una solicitud de soporte técnico con las operaciones de escritorio administradas de Microsoft para solucionar problemas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="f880d-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="f880d-121">Revierten</span><span class="sxs-lookup"><span data-stu-id="f880d-121">Reverted</span></span> | <span data-ttu-id="f880d-122">El cambio se revirtió al último cambio que se implementó correctamente en todos los grupos de implementación.</span><span class="sxs-lookup"><span data-stu-id="f880d-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="f880d-123">Implementar cambios</span><span class="sxs-lookup"><span data-stu-id="f880d-123">Deploy changes</span></span>

<span data-ttu-id="f880d-124">En estas instrucciones se mostrará la imagen de fondo del escritorio.</span><span class="sxs-lookup"><span data-stu-id="f880d-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="f880d-125">Una vez que haya ensayado una implementación, implemente los cambios desde la página estado de la implementación.</span><span class="sxs-lookup"><span data-stu-id="f880d-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="f880d-126">**Para implementar los cambios**</span><span class="sxs-lookup"><span data-stu-id="f880d-126">**To deploy changes**</span></span>

1. <span data-ttu-id="f880d-127">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="f880d-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="f880d-128">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="f880d-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="f880d-129">En el área de trabajo del **Estado de implementación** , seleccione la configuración que desee implementar y, a continuación, seleccione la implementación preconfigurada que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="f880d-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="f880d-130">Seleccione **implementar** para implementar el cambio en uno de los grupos de implementación.</span><span class="sxs-lookup"><span data-stu-id="f880d-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="f880d-131">![Información general sobre](images/1deployedit.png) la implementación de opciones de estado de implementación Microsoft Managed Desktop recomienda la implementación en grupos de implementación en este orden: test, First, Fast y, a continuación, general.</span><span class="sxs-lookup"><span data-stu-id="f880d-131">![Configurable settings deployment status overview](images/1deployedit.png) Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="f880d-132">Cuando se completen los cambios en cada grupo, el estado cambiará a **completa**.</span><span class="sxs-lookup"><span data-stu-id="f880d-132">When changes complete in each group, the status changes to **Complete**.</span></span>

![Implementación de la configuración configurable completada](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="f880d-134">Revertir la implementación</span><span class="sxs-lookup"><span data-stu-id="f880d-134">Revert deployment</span></span>

<span data-ttu-id="f880d-135">Después de implementar un cambio, puede revertir el estado de **implementación**.</span><span class="sxs-lookup"><span data-stu-id="f880d-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="f880d-136">Cuando se revierte un cambio que está **en curso** o **completado**, la implementación actual se detiene.</span><span class="sxs-lookup"><span data-stu-id="f880d-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="f880d-137">La configuración se revertirá a la última versión que se implementó en todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="f880d-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="f880d-138">Mostraremos los pasos para revertir un cambio con la imagen de fondo de escritorio como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f880d-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="f880d-139">**Para revertir un cambio**</span><span class="sxs-lookup"><span data-stu-id="f880d-139">**To revert a change**</span></span>
1. <span data-ttu-id="f880d-140">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="f880d-140">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="f880d-141">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="f880d-141">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="f880d-142">En el área de trabajo del **Estado de implementación** , seleccione la configuración que desea revertir y, a continuación, seleccione la implementación preconfigurada que se va a revertir.</span><span class="sxs-lookup"><span data-stu-id="f880d-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="f880d-143">En **es necesario revertir este cambio**, seleccione **revertir la implementación**.</span><span class="sxs-lookup"><span data-stu-id="f880d-143">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Reversión de implementación de la configuración configurable](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="f880d-145">Otros recursos</span><span class="sxs-lookup"><span data-stu-id="f880d-145">Additional resources</span></span>
- [<span data-ttu-id="f880d-146">Información general de configuración configurable</span><span class="sxs-lookup"><span data-stu-id="f880d-146">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="f880d-147">Referencia de parámetros configurables</span><span class="sxs-lookup"><span data-stu-id="f880d-147">Configurable settings reference</span></span>](config-setting-ref.md) 
