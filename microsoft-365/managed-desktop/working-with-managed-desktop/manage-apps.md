---
title: Administrar aplicaciones en Escritorio administrado de Microsoft
description: Información sobre cómo actualizar aplicaciones de línea de negocio que se implementan en Escritorio administrado de Microsoft dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
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
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="7ffbc-104">Administrar aplicaciones de línea de negocio en el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ffbc-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="7ffbc-105">Hay un par de formas de administrar las actualizaciones de aplicaciones para las aplicaciones que has incorporado a Escritorio administrado de Microsoft e implementadas en tus dispositivos Escritorio administrado de Microsoft dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="7ffbc-106">Puedes realizar actualizaciones de aplicaciones en Escritorio administrado de Microsoft portal o Intune.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="7ffbc-107">Actualizar aplicaciones de línea de negocio en Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ffbc-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="7ffbc-108">**Para actualizar las aplicaciones de línea de negocio en Escritorio administrado de Microsoft portal**</span><span class="sxs-lookup"><span data-stu-id="7ffbc-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="7ffbc-109">Inicie sesión en [Escritorio administrado de Microsoft portal de administración](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="7ffbc-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="7ffbc-110">En **Inventario,** seleccione **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="7ffbc-111">Selecciona la aplicación que quieres actualizar y, a continuación, selecciona **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="7ffbc-112">En **Administrar**, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="7ffbc-113">Haz **clic en Archivo de paquete de** la aplicación y, a continuación, busca para cargar un nuevo archivo de paquete de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="7ffbc-114">Seleccione **Archivo de paquete de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-114">Select **App package file**.</span></span>
7. <span data-ttu-id="7ffbc-115">Selecciona el icono de carpeta y busca la ubicación del archivo de la aplicación actualizado.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="7ffbc-116">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-116">Select **Open**.</span></span> <span data-ttu-id="7ffbc-117">La información de la aplicación se actualiza con la información del paquete.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="7ffbc-118">Comprueba que **la versión de la aplicación** refleja el paquete de la aplicación actualizado.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="7ffbc-119">La aplicación actualizada se implementará en los dispositivos del usuario.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="7ffbc-120">Actualizar aplicaciones de línea de negocio en Intune</span><span class="sxs-lookup"><span data-stu-id="7ffbc-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="7ffbc-121">**Para actualizar las aplicaciones de línea de negocio en Intune**</span><span class="sxs-lookup"><span data-stu-id="7ffbc-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="7ffbc-122">Inicie sesión en [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="7ffbc-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="7ffbc-123">Seleccione **Todos los servicios**  >  **intune**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="7ffbc-124">Intune se encuentra en la **sección Supervisión y** administración.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="7ffbc-125">Seleccione **Aplicaciones cliente > aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="7ffbc-126">Busca y selecciona la aplicación en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="7ffbc-127">En la **hoja Información** general, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="7ffbc-128">Seleccione **Archivo de paquete de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-128">Select **App package file**.</span></span>
7. <span data-ttu-id="7ffbc-129">Selecciona el icono de carpeta y busca la ubicación del archivo de la aplicación actualizado.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="7ffbc-130">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-130">Select **Open**.</span></span> <span data-ttu-id="7ffbc-131">La información de la aplicación se actualiza con la información del paquete.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="7ffbc-132">Comprueba que **la versión de la aplicación** refleja el paquete de la aplicación actualizado.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="7ffbc-133">Revertir una aplicación a una versión anterior</span><span class="sxs-lookup"><span data-stu-id="7ffbc-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="7ffbc-134">Si se encuentra un error cuando se implementa una nueva versión de una aplicación, puedes revertir a una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="7ffbc-135">El proceso Windows descrito aquí es para aplicaciones donde el tipo aparece como una aplicación de línea de negocio **msi** o una aplicación Windows **(Win 32) - versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="7ffbc-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="7ffbc-136">**Para revertir una aplicación de línea de negocio a una versión anterior**</span><span class="sxs-lookup"><span data-stu-id="7ffbc-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="7ffbc-137">Inicie sesión en [Escritorio administrado de Microsoft portal de administración](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="7ffbc-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="7ffbc-138">En **Inventario,** seleccione **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="7ffbc-139">Selecciona la aplicación que necesitas revertir y, a continuación, selecciona **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="7ffbc-140">En **Administrar**, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="7ffbc-141">Para Windows aplicaciones de línea de negocio **MSI,** seleccione Información de la aplicación **y,** a continuación, en **Omitir** versión de la aplicación, **seleccione Sí**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="7ffbc-142">Para **Windows aplicación (Win 32):** vista previa de aplicaciones, seleccione **Información** de la aplicación, seleccione Reglas de detección **y,** a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="7ffbc-143">Si hay una regla MSI, compruebe que la comprobación **de la** versión del producto MSI está establecida en **No**.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="7ffbc-144">[Upload una versión anterior del archivo de origen de la aplicación](../get-started/deploy-apps.md) a Escritorio administrado de Microsoft portal de administración.</span><span class="sxs-lookup"><span data-stu-id="7ffbc-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

