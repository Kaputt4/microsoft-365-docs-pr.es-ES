---
title: Implementar opciones configurables en el escritorio administrado de Microsoft
description: Implementar y realizar un seguimiento de los cambios de configuración configurables en el escritorio administrado de Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, implementar, implementación por fases, configuración configurable
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.openlocfilehash: d6e669ecb2e00158dd3ce6712014244fa2f081c9
ms.sourcegitcommit: b838e1dc7a98fcce1bdf7b76173f5f04f16be703
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "30175782"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="93c44-104">Implementar y realizar un seguimiento de las opciones configurables-escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="93c44-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="93c44-p101">Después de realizar cambios en las categorías de configuración y ensayar una implementación, puede implementar y realizar un seguimiento del progreso de la implementación en el estado de la implementación. En esta página se muestra un resumen de cada configuración configurable. Abra una categoría de configuración para ver cada implementación y sus detalles, para implementar los cambios.</span><span class="sxs-lookup"><span data-stu-id="93c44-p101">After you make changes to your setting categories and stage a deployment, you can deploy and track progress for the deployment on Deployment status. This page shows a summary of each configurable setting. Open a setting category to see each deployment and their details, to deploy the changes.</span></span> 

## <a name="deployment-statuses"></a><span data-ttu-id="93c44-108">Estados de implementación</span><span class="sxs-lookup"><span data-stu-id="93c44-108">Deployment statuses</span></span> 

<span data-ttu-id="93c44-109">Estos son los statues que verá para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="93c44-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="93c44-110">Estado</span><span class="sxs-lookup"><span data-stu-id="93c44-110">Status</span></span>  | <span data-ttu-id="93c44-111">Explicación</span><span class="sxs-lookup"><span data-stu-id="93c44-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="93c44-112">Implementar</span><span class="sxs-lookup"><span data-stu-id="93c44-112">Deploy</span></span> | <span data-ttu-id="93c44-113">El cambio está esperando a que se implemente en este anillo.</span><span class="sxs-lookup"><span data-stu-id="93c44-113">Your change is waiting to be deployed to this ring.</span></span>
<span data-ttu-id="93c44-114">En curso</span><span class="sxs-lookup"><span data-stu-id="93c44-114">In progress</span></span> | <span data-ttu-id="93c44-115">El cambio se aplica a los dispositivos activos en este anillo.</span><span class="sxs-lookup"><span data-stu-id="93c44-115">The change is being applied to active devices in this ring.</span></span> 
<span data-ttu-id="93c44-116">Completa</span><span class="sxs-lookup"><span data-stu-id="93c44-116">Complete</span></span> | <span data-ttu-id="93c44-117">El cambio se completó en todos los dispositivos activos en este anillo.</span><span class="sxs-lookup"><span data-stu-id="93c44-117">The change completed on all active devices in this ring.</span></span> 
<span data-ttu-id="93c44-118">Failed</span><span class="sxs-lookup"><span data-stu-id="93c44-118">Failed</span></span> | <span data-ttu-id="93c44-119">Se produjo un error en el cambio en un 10% de los dispositivos activos en el anillo, por lo que se detuvo la implementación.</span><span class="sxs-lookup"><span data-stu-id="93c44-119">The change failed on a 10 percent of active devices in the ring, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="93c44-120">Se abrirá automáticamente una solicitud de soporte técnico con las operaciones de escritorio administradas de Microsoft para solucionar problemas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="93c44-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="93c44-121">Revierten</span><span class="sxs-lookup"><span data-stu-id="93c44-121">Reverted</span></span> | <span data-ttu-id="93c44-122">El cambio se revirtió al último cambio que se implementó correctamente en todos los anillos de implementación.</span><span class="sxs-lookup"><span data-stu-id="93c44-122">The change was reverted to the last change that was successfully deployed to all deployment rings.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="93c44-123">Implementar cambios</span><span class="sxs-lookup"><span data-stu-id="93c44-123">Deploy changes</span></span>

<span data-ttu-id="93c44-p102">En estas instrucciones se mostrará la imagen de fondo del escritorio. Una vez que haya ensayado una implementación, implemente los cambios desde el estado de implementación.</span><span class="sxs-lookup"><span data-stu-id="93c44-p102">We’ll show Desktop background picture in these instructions. After you’ve staged a deployment, you deploy changes from Deployment status.</span></span> 

<span data-ttu-id="93c44-126">**Para implementar los cambios**</span><span class="sxs-lookup"><span data-stu-id="93c44-126">**To deploy changes**</span></span>

1. <span data-ttu-id="93c44-127">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="93c44-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="93c44-128">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="93c44-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="93c44-129">En el área de trabajo del **Estado de implementación** , seleccione la configuración que desee implementar y, a continuación, seleccione la implementación preconfigurada que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="93c44-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="93c44-130">Seleccione **implementar** para implementar el cambio en uno de los anillos de implementación.</span><span class="sxs-lookup"><span data-stu-id="93c44-130">Select **Deploy** to deploy the change to one of the deployment rings.</span></span>

![Introducción al estado de implementación de configuración configurable](images/deploy-cs-overview.png)

<span data-ttu-id="93c44-132">Microsoft manAged Desktop recomienda la implementación en los anillos de implementación en este orden: test, First, Fast y, a continuación, amplio.</span><span class="sxs-lookup"><span data-stu-id="93c44-132">Microsoft Managed Desktop recommends deploying to deployment rings in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="93c44-133">Cuando se completen los cambios en cada timbre, el estado cambiará a **completa**.</span><span class="sxs-lookup"><span data-stu-id="93c44-133">When changes complete in each ring, the status changes to **Complete**.</span></span>

![Implementación de la configuración configurable completada](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="93c44-135">Revertir la implementación</span><span class="sxs-lookup"><span data-stu-id="93c44-135">Revert deployment</span></span>

<span data-ttu-id="93c44-136">En estas instrucciones se mostrará la imagen de fondo del escritorio.</span><span class="sxs-lookup"><span data-stu-id="93c44-136">We’ll show Desktop background picture in these instructions.</span></span> 

<span data-ttu-id="93c44-p103">Después de implementar un cambio, puede revertir el estado de **implementación**. Cuando se revierte un cambio que está **en curso** o **completado**, la implementación actual se detiene. La configuración se revertirá a la última versión que se implementó en todos los anillos.</span><span class="sxs-lookup"><span data-stu-id="93c44-p103">After you’ve deployed a change, you can revert from **Deployment status**. When you revert a change that is **In progress** or **Complete**, the current deployment stops. The setting will revert to the last version that was deployed to all rings.</span></span> 

<span data-ttu-id="93c44-140">**Para revertir un cambio**</span><span class="sxs-lookup"><span data-stu-id="93c44-140">**To revert a change**</span></span>
1. <span data-ttu-id="93c44-141">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="93c44-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="93c44-142">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="93c44-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="93c44-143">En el área de trabajo del **Estado de implementación** , seleccione la configuración que desea revertir y, a continuación, seleccione la implementación preconfigurada que se va a revertir.</span><span class="sxs-lookup"><span data-stu-id="93c44-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="93c44-144">En **es necesario revertir este cambio**, seleccione **revertir la implementación**.</span><span class="sxs-lookup"><span data-stu-id="93c44-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Reversión de implementación de la configuración configurable](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="93c44-146">Otros recursos</span><span class="sxs-lookup"><span data-stu-id="93c44-146">Additional resources</span></span>
- [<span data-ttu-id="93c44-147">Información general de configuración configurable</span><span class="sxs-lookup"><span data-stu-id="93c44-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="93c44-148">Referencia de opciones conFigurables</span><span class="sxs-lookup"><span data-stu-id="93c44-148">Configurable settings reference</span></span>](config-setting-ref.md) 