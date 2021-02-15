---
title: Implementar aplicaciones en dispositivos
description: Información para agregar e implementar aplicaciones en dispositivos de Escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de LÍNEA DEB
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
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="79856-104">Implementar aplicaciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="79856-104">Deploy apps to devices</span></span>
<span data-ttu-id="79856-105">Parte de la incorporación al Escritorio administrado de Microsoft incluye agregar e implementar aplicaciones en los dispositivos del usuario.</span><span class="sxs-lookup"><span data-stu-id="79856-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="79856-106">Una vez que use el portal de Escritorio administrado de Microsoft, puede agregar e implementar las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="79856-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="79856-107">El proceso general tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="79856-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="79856-108">[Agregar aplicaciones al portal](#1) de escritorio administrado de Microsoft: pueden ser aplicaciones de línea de negocio (LOB) existentes o aplicaciones de la Microsoft Store para Empresas que hayas sincronizado con Intune.</span><span class="sxs-lookup"><span data-stu-id="79856-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="79856-109">[Crear grupos de Azure Active Directory (AD)](#2) para la asignación de aplicaciones: usará estos grupos para administrar la asignación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="79856-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="79856-110">Asignar aplicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="79856-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="79856-111">Paso 1: Agregar aplicaciones al portal de Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="79856-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="79856-112">Puedes agregar aplicaciones basadas en [Win32 o MSI](#lob-apps)de Windows, o aplicaciones de la [Microsoft Store](#msfb-apps) para Empresas al Escritorio administrado de Microsoft y, a continuación, implementarlas en dispositivos de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79856-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="79856-113">Aplicaciones basadas en MSI de Windows o Win32 a Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="79856-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="79856-114">Puede agregar las aplicaciones de línea de negocio (LOB) al portal de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79856-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="79856-115">Para obtener información sobre los requisitos de las aplicaciones instaladas en dispositivos de Escritorio administrado de Microsoft, vea Requisitos de aplicaciones de [Escritorio administrado de Microsoft.](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)</span><span class="sxs-lookup"><span data-stu-id="79856-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="79856-116">En este procedimiento, seleccionarás el tipo de aplicación que quieres agregar y, a continuación, configurarás y cargarás el origen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="79856-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="79856-117">**Para agregar la aplicación de LÍNEA DEB o la aplicación de Windows al portal de Escritorio administrado de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="79856-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="79856-118">Puede iniciar sesión en el portal de Escritorio administrado de Microsoft o iniciar sesión en Intune y, a continuación, buscar escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79856-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="79856-119">Mostraremos el inicio de sesión en el portal de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79856-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="79856-120">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="79856-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="79856-121">En **Inventario,** seleccione **Aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="79856-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="79856-122">En la carga de trabajo Aplicaciones, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="79856-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="79856-123">En **Agregar aplicación,** selecciona **aplicación de línea de negocio** o aplicación de Windows **(Win32).**</span><span class="sxs-lookup"><span data-stu-id="79856-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="79856-124">Si has seleccionado **la** aplicación de línea de negocio, consulta Agregar una aplicación de línea de negocio de [Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="79856-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="79856-125">Si seleccionaste **la aplicación de Windows (Win32),** consulta administración de aplicaciones de [Win32](https://docs.microsoft.com/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="79856-125">If you selected **Windows app (Win32)**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="79856-126">Aplicaciones de la Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="79856-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="79856-127">Si no te has registrado en la Microsoft Store para Empresas, puedes registrarte cuando compres aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="79856-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="79856-128">Una vez que tenga las aplicaciones, puede sincronizarlas con escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79856-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="79856-129">**Para comprar aplicaciones desde la Microsoft Store para Empresas**</span><span class="sxs-lookup"><span data-stu-id="79856-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="79856-130">Inicia sesión en [la Microsoft Store para Empresas](https://businessstore.microsoft.com) con tu cuenta de administrador de la Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="79856-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="79856-131">Selecciona **Tienda para mi grupo.**</span><span class="sxs-lookup"><span data-stu-id="79856-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="79856-132">Usa La búsqueda para encontrar la aplicación que quieres y selecciona la aplicación.</span><span class="sxs-lookup"><span data-stu-id="79856-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="79856-133">En los detalles del producto, seleccione **Obtener la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="79856-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="79856-134">Microsoft Store agrega la aplicación a **Los productos** de la organización.</span><span class="sxs-lookup"><span data-stu-id="79856-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="79856-135">**Para forzar una sincronización entre Intune y la Microsoft Store para Empresas**</span><span class="sxs-lookup"><span data-stu-id="79856-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="79856-136">Inicie sesión en el Centro [de administración de Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="79856-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="79856-137">Seleccione **Conectores de administración** de  >  **inquilinos y tokens** de la Microsoft Store para  >  **Empresas.**</span><span class="sxs-lookup"><span data-stu-id="79856-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="79856-138">Selecciona **Sincronizar** para obtener las aplicaciones que has comprado de Microsoft Store en Intune.</span><span class="sxs-lookup"><span data-stu-id="79856-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="79856-139">**Para comprobar que está activa una sincronización entre Intune y la Microsoft Store para Empresas**</span><span class="sxs-lookup"><span data-stu-id="79856-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="79856-140">Inicia sesión en [la Microsoft Store para Empresas](https://businessstore.microsoft.com) con tu cuenta de administrador de la Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="79856-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="79856-141">Seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="79856-141">Select **Manage**.</span></span>
3. <span data-ttu-id="79856-142">Seleccione **Configuración** y, a continuación, **seleccione Distribuir**.</span><span class="sxs-lookup"><span data-stu-id="79856-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="79856-143">En **Herramientas de administración,** compruebe que Intune aparece en la lista y que el estado es **Activo.**</span><span class="sxs-lookup"><span data-stu-id="79856-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="79856-144">Paso 2: Crear grupos de Azure AD</span><span class="sxs-lookup"><span data-stu-id="79856-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="79856-145">Cree tres grupos de Azure AD para cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="79856-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="79856-146">En esta tabla se describen los grupos que necesitará (Disponible, Requerido y Desinstalar).</span><span class="sxs-lookup"><span data-stu-id="79856-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="79856-147">Tipo de asignación de aplicación</span><span class="sxs-lookup"><span data-stu-id="79856-147">App assignment type</span></span> |    <span data-ttu-id="79856-148">Uso de grupos</span><span class="sxs-lookup"><span data-stu-id="79856-148">Group use</span></span>    | <span data-ttu-id="79856-149">Ejemplo de nombre de Azure AD</span><span class="sxs-lookup"><span data-stu-id="79856-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="79856-150">Disponible</span><span class="sxs-lookup"><span data-stu-id="79856-150">Available</span></span> |  <span data-ttu-id="79856-151">La aplicación estará disponible desde la aplicación o el sitio web del Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="79856-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="79856-152">MMD– *nombre de la aplicación:* disponible</span><span class="sxs-lookup"><span data-stu-id="79856-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="79856-153">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="79856-153">Required</span></span> |  <span data-ttu-id="79856-154">La aplicación se instala en dispositivos de los grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="79856-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="79856-155">MMD: *nombre de la aplicación:* obligatorio</span><span class="sxs-lookup"><span data-stu-id="79856-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="79856-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="79856-156">Uninstall</span></span> |  <span data-ttu-id="79856-157">La aplicación se desinstala de los dispositivos de los grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="79856-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="79856-158">MMD – *nombre de la aplicación* – Desinstalar</span><span class="sxs-lookup"><span data-stu-id="79856-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="79856-159">Agregue los usuarios a estos grupos para que la aplicación esté disponible, instale la aplicación o quite la aplicación de su dispositivo de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79856-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="79856-160">Paso 3: Asignar aplicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="79856-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="79856-161">**Para asignar la aplicación a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="79856-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="79856-162">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="79856-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="79856-163">En el panel Escritorio administrado, seleccione **Aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="79856-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="79856-164">En la carga de trabajo Aplicaciones, seleccione la aplicación a la que desea asignar usuarios y seleccione **Asignar grupos de usuarios.**</span><span class="sxs-lookup"><span data-stu-id="79856-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="79856-165">Para la aplicación específica, seleccione un tipo de asignación (Disponible, Requerido, Desinstalar) y asigne el grupo adecuado.</span><span class="sxs-lookup"><span data-stu-id="79856-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="79856-166">En el panel Asignar aplicaciones, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="79856-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="79856-167">Pasos para empezar a usar el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="79856-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="79856-168">Agregar y verificar los contactos de administración en el portal de administración </span><span class="sxs-lookup"><span data-stu-id="79856-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="79856-169">Ajustar el acceso condicional</span><span class="sxs-lookup"><span data-stu-id="79856-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="79856-170">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="79856-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="79856-171">Desplegar el portal de empresa de Intune</span><span class="sxs-lookup"><span data-stu-id="79856-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="79856-172">Habilitar Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="79856-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="79856-173">Instalar dispositivos</span><span class="sxs-lookup"><span data-stu-id="79856-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="79856-174">Prepare a los usuarios para que usen los dispositivos</span><span class="sxs-lookup"><span data-stu-id="79856-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="79856-175">Implementar aplicaciones (este tema)</span><span class="sxs-lookup"><span data-stu-id="79856-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
