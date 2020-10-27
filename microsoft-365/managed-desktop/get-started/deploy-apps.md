---
title: Implementar aplicaciones en dispositivos
description: Información para agregar e implementar aplicaciones en dispositivos de escritorio administrados por Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769111"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="08b8f-104">Implementar aplicaciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="08b8f-104">Deploy apps to devices</span></span>
<span data-ttu-id="08b8f-105">Parte del escritorio administrado de incorporación a Microsoft incluye la adición e implementación de aplicaciones en los dispositivos del usuario.</span><span class="sxs-lookup"><span data-stu-id="08b8f-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="08b8f-106">Una vez que esté usando Microsoft Managed Desktop portal, puede Agregar e implementar sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="08b8f-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="08b8f-107">El proceso general tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="08b8f-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="08b8f-108">[Agregar aplicaciones a Microsoft Managed Desktop portal](#1) : esto puede ser una aplicación de línea de negocio (LOB) existente o aplicaciones de Microsoft Store para empresas que haya sincronizado con Intune.</span><span class="sxs-lookup"><span data-stu-id="08b8f-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="08b8f-109">[Crear grupos de Azure Active Directory (ad) para la asignación de aplicaciones](#2) : estos grupos se usan para administrar la asignación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="08b8f-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="08b8f-110">Asignar aplicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="08b8f-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="08b8f-111">Paso 1: agregar aplicaciones a Microsoft Managed Desktop portal</span><span class="sxs-lookup"><span data-stu-id="08b8f-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="08b8f-112">Puede agregar aplicaciones [Win32, o aplicaciones basadas en MSI de Windows](#lob-apps)o [aplicaciones de Microsoft Store for Business](#msfb-apps) a escritorio administrado por Microsoft y, a continuación, implementarlas en dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="08b8f-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="08b8f-113">Win32 o aplicaciones basadas en MSI de Windows a escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="08b8f-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="08b8f-114">Puede Agregar las aplicaciones de línea de negocio (LOB) a Microsoft Managed Desktop portal.</span><span class="sxs-lookup"><span data-stu-id="08b8f-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="08b8f-115">Para obtener información sobre los requisitos de las aplicaciones instaladas en dispositivos de escritorio administrados por Microsoft, consulte requisitos de la [aplicación de escritorio administrada de Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="08b8f-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="08b8f-116">En este procedimiento, seleccionará el tipo de aplicación que desea agregar y, después, configurará y cargará el origen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="08b8f-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="08b8f-117">**Para agregar la aplicación LOB o la aplicación de Windows a Microsoft Managed Desktop portal**</span><span class="sxs-lookup"><span data-stu-id="08b8f-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="08b8f-118">Puede iniciar sesión en el portal de escritorio administrado de Microsoft, o iniciar sesión en Intune y, a continuación, buscar Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="08b8f-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="08b8f-119">Se mostrará el inicio de sesión en Microsoft Managed Desktop portal.</span><span class="sxs-lookup"><span data-stu-id="08b8f-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="08b8f-120">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="08b8f-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="08b8f-121">En **inventario** , seleccione **aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-121">Under **Inventory** , select **Apps** .</span></span>
3.    <span data-ttu-id="08b8f-122">En la carga de trabajo de aplicaciones, seleccione **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-122">In the Apps workload, select **Add** .</span></span>
4.    <span data-ttu-id="08b8f-123">En **Agregar aplicación** , seleccione **aplicación de línea de negocio** o **aplicación de Windows (Win32)** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-123">In **Add app** , select **Line-of-business app** or **Windows app (Win32)** .</span></span>
    - <span data-ttu-id="08b8f-124">Si seleccionó **aplicación de línea de negocio** , vea [Agregar una aplicación de línea de negocio de Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="08b8f-124">If you selected **Line-of-business app** , see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="08b8f-125">Si seleccionó **Windows App (Win32)** , vea [Administración de aplicaciones Win32](https://docs.microsoft.com/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar aplicaciones para Windows.</span><span class="sxs-lookup"><span data-stu-id="08b8f-125">If you selected **Windows app (Win32)** , see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="08b8f-126">Aplicaciones de Microsoft Store para empresas</span><span class="sxs-lookup"><span data-stu-id="08b8f-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="08b8f-127">Si no te has registrado en Microsoft Store para empresas, puedes registrarte en la tienda de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="08b8f-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="08b8f-128">Una vez que tenga las aplicaciones, puede sincronizarlas con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="08b8f-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="08b8f-129">**Para comprar aplicaciones de Microsoft Store para empresas**</span><span class="sxs-lookup"><span data-stu-id="08b8f-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="08b8f-130">Inicie sesión en [Microsoft Store para empresas](https://businessstore.microsoft.com) con su cuenta de administrador de Microsoft Store for Business.</span><span class="sxs-lookup"><span data-stu-id="08b8f-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="08b8f-131">Seleccione **comprar para mi grupo** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-131">Select **Shop for my group** .</span></span>
3. <span data-ttu-id="08b8f-132">Use la búsqueda para encontrar la aplicación que quiera y seleccione la aplicación.</span><span class="sxs-lookup"><span data-stu-id="08b8f-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="08b8f-133">En los detalles del producto, seleccione **obtener la aplicación** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-133">On the product details, select **Get the App** .</span></span> <span data-ttu-id="08b8f-134">Microsoft Store agrega la aplicación a **los productos** de la organización.</span><span class="sxs-lookup"><span data-stu-id="08b8f-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="08b8f-135">**Para forzar una sincronización entre Intune y Microsoft Store para empresas**</span><span class="sxs-lookup"><span data-stu-id="08b8f-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="08b8f-136">Inicie sesión en el [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).</span><span class="sxs-lookup"><span data-stu-id="08b8f-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="08b8f-137">Seleccione conectores de **Administración de inquilinos**  >  **y tokens**  >  **de Microsoft Store para empresas** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business** .</span></span>
3. <span data-ttu-id="08b8f-138">Seleccione **sincronizar** para obtener las aplicaciones que ha comprado de Microsoft Store a Intune.</span><span class="sxs-lookup"><span data-stu-id="08b8f-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="08b8f-139">**Para comprobar que hay una sincronización activa entre Intune y Microsoft Store para empresas**</span><span class="sxs-lookup"><span data-stu-id="08b8f-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="08b8f-140">Inicie sesión en [Microsoft Store para empresas](https://businessstore.microsoft.com) con su cuenta de administrador de Microsoft Store for Business.</span><span class="sxs-lookup"><span data-stu-id="08b8f-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="08b8f-141">Seleccione **administrar** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-141">Select **Manage** .</span></span>
3. <span data-ttu-id="08b8f-142">Seleccione **configuración** y, después, seleccione **distribuir** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-142">Select **Settings** and then select **Distribute** .</span></span>
4. <span data-ttu-id="08b8f-143">En **herramientas de administración** , compruebe que Intune aparece en la lista y que el estado es **activo** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-143">Under **Management tools** , verify that Intune is listed and that the status is **Active** .</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="08b8f-144">Paso 2: crear grupos de Azure AD</span><span class="sxs-lookup"><span data-stu-id="08b8f-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="08b8f-145">Cree tres grupos de Azure AD para cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="08b8f-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="08b8f-146">En esta tabla se describen los grupos que necesitará (disponibles, obligatorios y de desinstalación).</span><span class="sxs-lookup"><span data-stu-id="08b8f-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="08b8f-147">Tipo de asignación de aplicación</span><span class="sxs-lookup"><span data-stu-id="08b8f-147">App assignment type</span></span> |    <span data-ttu-id="08b8f-148">Uso de grupo</span><span class="sxs-lookup"><span data-stu-id="08b8f-148">Group use</span></span>    | <span data-ttu-id="08b8f-149">Nombre de ejemplo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="08b8f-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="08b8f-150">Disponible</span><span class="sxs-lookup"><span data-stu-id="08b8f-150">Available</span></span> |  <span data-ttu-id="08b8f-151">La aplicación estará disponible desde el sitio web o la aplicación del portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="08b8f-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="08b8f-152">MMD: *nombre* de la aplicación: disponible</span><span class="sxs-lookup"><span data-stu-id="08b8f-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="08b8f-153">Necesario</span><span class="sxs-lookup"><span data-stu-id="08b8f-153">Required</span></span> |  <span data-ttu-id="08b8f-154">La aplicación se instala en los dispositivos de los grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="08b8f-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="08b8f-155">MMD: *nombre* de la aplicación: obligatorio</span><span class="sxs-lookup"><span data-stu-id="08b8f-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="08b8f-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="08b8f-156">Uninstall</span></span> |  <span data-ttu-id="08b8f-157">La aplicación se desinstala de los dispositivos de los grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="08b8f-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="08b8f-158">MMD: *nombre* de la aplicación: desinstalar</span><span class="sxs-lookup"><span data-stu-id="08b8f-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="08b8f-159">Agregue los usuarios a estos grupos para hacer que la aplicación esté disponible, instalar la aplicación o quitar la aplicación de su dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="08b8f-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="08b8f-160">Paso 3: asignar aplicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="08b8f-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="08b8f-161">**Para asignar la aplicación a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="08b8f-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="08b8f-162">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="08b8f-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="08b8f-163">En el panel escritorio administrado, seleccione **aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-163">In Managed Desktop pane, select **Apps** .</span></span>
3. <span data-ttu-id="08b8f-164">En la carga de trabajo de aplicaciones, seleccione la aplicación a la que desea asignar usuarios y seleccione **asignar grupos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups** .</span></span>
4. <span data-ttu-id="08b8f-165">Para la aplicación específica, seleccione un tipo de asignación (disponible, obligatorio, desinstalar) y asigne el grupo adecuado.</span><span class="sxs-lookup"><span data-stu-id="08b8f-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="08b8f-166">En el panel asignar aplicaciones, seleccione **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="08b8f-166">In the Assign Apps pane, select **OK** .</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="08b8f-167">Pasos para empezar a trabajar con el escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="08b8f-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="08b8f-168">Agregar y verificar los contactos de administración en el portal de administración </span><span class="sxs-lookup"><span data-stu-id="08b8f-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="08b8f-169">Ajustar el acceso condicional</span><span class="sxs-lookup"><span data-stu-id="08b8f-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="08b8f-170">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="08b8f-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="08b8f-171">Desplegar el portal de empresa de Intune</span><span class="sxs-lookup"><span data-stu-id="08b8f-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="08b8f-172">Habilitar Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="08b8f-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="08b8f-173">Instalar dispositivos</span><span class="sxs-lookup"><span data-stu-id="08b8f-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="08b8f-174">Prepare a los usuarios para que usen los dispositivos</span><span class="sxs-lookup"><span data-stu-id="08b8f-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="08b8f-175">Implementación de aplicaciones (este tema)</span><span class="sxs-lookup"><span data-stu-id="08b8f-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
