---
title: Administrar aplicaciones en el escritorio administrado por Microsoft
description: Información sobre cómo actualizar las aplicaciones de línea de negocio que se implementan en dispositivos de escritorio administrados por Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600687"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="a6bb8-104">Administrar aplicaciones de línea de negocio en el escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="a6bb8-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="a6bb8-105">Hay un par de maneras de administrar las actualizaciones de aplicaciones para las aplicaciones que haya incorporado en el escritorio administrado de Microsoft y que se hayan implementado en sus dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a6bb8-106">Puede realizar actualizaciones de aplicaciones en el portal de escritorio administrado de Microsoft o Intune.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="a6bb8-107">Actualizar las aplicaciones de línea de negocio en el escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="a6bb8-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="a6bb8-108">**Para actualizar las aplicaciones de línea de negocio en el portal de escritorio administrado de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="a6bb8-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="a6bb8-109">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="a6bb8-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="a6bb8-110">En **inventario**, seleccione **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="a6bb8-111">Seleccione la aplicación que desea actualizar y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="a6bb8-112">En **administrar**, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="a6bb8-113">Haga clic en **archivo de paquete de aplicaciones**y, a continuación, busque cargar un nuevo archivo de paquete de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="a6bb8-114">Seleccione **archivo de paquete de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-114">Select **App package file**.</span></span>
7. <span data-ttu-id="a6bb8-115">Seleccione el icono de carpeta y vaya a la ubicación del archivo de aplicación actualizado.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="a6bb8-116">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-116">Select **Open**.</span></span> <span data-ttu-id="a6bb8-117">La información de la aplicación se actualiza con la información del paquete.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="a6bb8-118">Compruebe que la versión de la **aplicación** refleja el paquete de la aplicación actualizado.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="a6bb8-119">La aplicación actualizada se implementará en los dispositivos del usuario.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="a6bb8-120">Actualizar las aplicaciones de línea de negocio en Intune</span><span class="sxs-lookup"><span data-stu-id="a6bb8-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="a6bb8-121">**Para actualizar las aplicaciones de línea de negocio en Intune**</span><span class="sxs-lookup"><span data-stu-id="a6bb8-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="a6bb8-122">Inicie sesión en [Azure portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a6bb8-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a6bb8-123">Seleccione **todos los servicios** > de**Intune**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="a6bb8-124">Intune se encuentra en la sección **Monitoring + Management** .</span><span class="sxs-lookup"><span data-stu-id="a6bb8-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="a6bb8-125">Seleccione aplicaciones **cliente > aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="a6bb8-126">Busque y seleccione su aplicación en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="a6bb8-127">En la hoja **información general** , seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="a6bb8-128">Seleccione **archivo de paquete de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-128">Select **App package file**.</span></span>
7. <span data-ttu-id="a6bb8-129">Seleccione el icono de carpeta y vaya a la ubicación del archivo de aplicación actualizado.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="a6bb8-130">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-130">Select **Open**.</span></span> <span data-ttu-id="a6bb8-131">La información de la aplicación se actualiza con la información del paquete.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="a6bb8-132">Compruebe que la versión de la **aplicación** refleja el paquete de la aplicación actualizado.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="a6bb8-133">Revertir una aplicación a una versión anterior</span><span class="sxs-lookup"><span data-stu-id="a6bb8-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="a6bb8-134">Si se produce un error cuando se implementa una nueva versión de una aplicación, puede volver a una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="a6bb8-135">El proceso descrito aquí es para las aplicaciones donde tipo aparece como **aplicación MSI de línea de negocio de Windows** o aplicación de **windows (Win 32)-vista previa**</span><span class="sxs-lookup"><span data-stu-id="a6bb8-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="a6bb8-136">**Para volver a una versión anterior de una aplicación de línea de negocio**</span><span class="sxs-lookup"><span data-stu-id="a6bb8-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="a6bb8-137">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="a6bb8-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="a6bb8-138">En **inventario**, seleccione **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="a6bb8-139">Seleccione la aplicación que necesita volver y, después, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="a6bb8-140">En **administrar**, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="a6bb8-141">Para las aplicaciones MSI de la **aplicación de línea de negocio de Windows** , seleccione información de la **aplicación**y, a continuación, en **omitir versión**de la aplicación, seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="a6bb8-142">Para **Windows App (Win 32): vista previa** de aplicaciones, seleccione información de la **aplicación**, seleccione **reglas de detección**y, después, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="a6bb8-143">Si hay una regla MSI, compruebe que la **comprobación de la versión del producto MSI** esté establecida en **no**.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="a6bb8-144">[Cargue una versión anterior del archivo de origen de la aplicación en el](../get-started/deploy-apps.md) portal de administración de escritorio administrada de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a6bb8-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

