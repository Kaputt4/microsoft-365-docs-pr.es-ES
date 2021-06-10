---
title: Implementar aplicaciones en dispositivos
description: Información para agregar e implementar aplicaciones en Escritorio administrado de Microsoft dispositivos.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de línea de negocio, aplicaciones de LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922031"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="1dd1a-104">Implementar aplicaciones en dispositivos</span><span class="sxs-lookup"><span data-stu-id="1dd1a-104">Deploy apps to devices</span></span>
<span data-ttu-id="1dd1a-105">Parte de la incorporación a Escritorio administrado de Microsoft incluye agregar e implementar aplicaciones en los dispositivos del usuario.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="1dd1a-106">Una vez que estés usando el portal Escritorio administrado de Microsoft, puedes agregar e implementar tus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="1dd1a-107">El proceso general tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="1dd1a-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="1dd1a-108">[Agregar aplicaciones Escritorio administrado de Microsoft portal:](#1) pueden ser aplicaciones de línea de negocio (LOB) existentes o aplicaciones de Microsoft Store para Empresas que haya sincronizado con Intune.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="1dd1a-109">[Crear Azure Active Directory (AD) para la](#2) asignación de aplicaciones: usará estos grupos para administrar la asignación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="1dd1a-110">Asignar aplicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="1dd1a-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="1dd1a-111">Paso 1: Agregar aplicaciones a Escritorio administrado de Microsoft portal</span><span class="sxs-lookup"><span data-stu-id="1dd1a-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="1dd1a-112">Puedes agregar [win32 o](#lob-apps)Windows aplicaciones basadas en [](#msfb-apps) MSI o Microsoft Store para Empresas aplicaciones a Escritorio administrado de Microsoft y, a continuación, implementarlas en Escritorio administrado de Microsoft dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="1dd1a-113">Win32 o Windows aplicaciones basadas en MSI para Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="1dd1a-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="1dd1a-114">Puedes agregar las aplicaciones de línea de negocio (LOB) a Escritorio administrado de Microsoft portal.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="1dd1a-115">Para obtener información sobre los requisitos de las aplicaciones instaladas en Escritorio administrado de Microsoft dispositivos, consulte [Escritorio administrado de Microsoft de aplicaciones.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="1dd1a-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="1dd1a-116">En este procedimiento, seleccionarás el tipo de aplicación que quieres agregar y, a continuación, configurarás y cargarás el origen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="1dd1a-117">**Para agregar la aplicación de LOB o Windows aplicación a Escritorio administrado de Microsoft portal**</span><span class="sxs-lookup"><span data-stu-id="1dd1a-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="1dd1a-118">Puede iniciar sesión en Escritorio administrado de Microsoft portal o iniciar sesión en Intune y, a continuación, buscar Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="1dd1a-119">Mostraremos el inicio de sesión en Escritorio administrado de Microsoft portal.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="1dd1a-120">Inicie sesión en [Escritorio administrado de Microsoft portal de administración](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="1dd1a-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="1dd1a-121">En **Inventario,** seleccione **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="1dd1a-122">En la carga de trabajo Aplicaciones, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="1dd1a-123">En **Agregar aplicación,** selecciona **Aplicación de línea de negocio** o Windows aplicación **(Win32).**</span><span class="sxs-lookup"><span data-stu-id="1dd1a-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="1dd1a-124">Si seleccionaste **Aplicación** de línea de negocio, consulta Agregar una aplicación de línea de negocio de [Windows a Microsoft Intune](/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="1dd1a-125">Si **seleccionaste Windows aplicación (Win32),** consulta Administración de aplicaciones de [Win32](/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar Windows aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="1dd1a-126">Microsoft Store para Empresas aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1dd1a-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="1dd1a-127">Si no te has registrado con Microsoft Store para Empresas, puedes registrarte cuando compres aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="1dd1a-128">Después de tener las aplicaciones, puedes sincronizarlas con Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="1dd1a-129">**Para comprar aplicaciones desde el Microsoft Store para Empresas**</span><span class="sxs-lookup"><span data-stu-id="1dd1a-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="1dd1a-130">Inicie sesión en [Microsoft Store para Empresas](https://businessstore.microsoft.com) con su cuenta Microsoft Store para Empresas administrador.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="1dd1a-131">Seleccione **Tienda para mi grupo**.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="1dd1a-132">Usa Buscar para buscar la aplicación que quieras y selecciona la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="1dd1a-133">En los detalles del producto, selecciona **Obtener la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="1dd1a-134">Microsoft Store agrega la aplicación a **Los productos** de la organización.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="1dd1a-135">**Para forzar una sincronización entre Intune y Microsoft Store para Empresas**</span><span class="sxs-lookup"><span data-stu-id="1dd1a-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="1dd1a-136">Inicie sesión en el centro [Microsoft Endpoint Manager administración](https://go.microsoft.com/fwlink/?linkid=2109431).</span><span class="sxs-lookup"><span data-stu-id="1dd1a-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="1dd1a-137">Seleccione **Conectores de administración** de  >  **inquilinos y tokens**  >  **Microsoft Store para Empresas**.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="1dd1a-138">Selecciona **Sincronizar** para obtener las aplicaciones que has comprado de la Microsoft Store en Intune.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="1dd1a-139">**Para comprobar que una sincronización entre Intune y Microsoft Store para Empresas está activa**</span><span class="sxs-lookup"><span data-stu-id="1dd1a-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="1dd1a-140">Inicie sesión en [Microsoft Store para Empresas](https://businessstore.microsoft.com) con su cuenta Microsoft Store para Empresas administrador.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="1dd1a-141">Seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-141">Select **Manage**.</span></span>
3. <span data-ttu-id="1dd1a-142">Seleccione **Configuración** y, a continuación, **seleccione Distribuir**.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="1dd1a-143">En **Herramientas de administración,** compruebe que Intune aparece y que el estado es **Activo**.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="1dd1a-144">Paso 2: Crear grupos de Azure AD</span><span class="sxs-lookup"><span data-stu-id="1dd1a-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="1dd1a-145">Crea tres grupos de Azure AD para cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="1dd1a-146">En esta tabla se describen los grupos que necesitará (Disponible, Obligatorio y Desinstalar).</span><span class="sxs-lookup"><span data-stu-id="1dd1a-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="1dd1a-147">Tipo de asignación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1dd1a-147">App assignment type</span></span> |    <span data-ttu-id="1dd1a-148">Uso en grupo</span><span class="sxs-lookup"><span data-stu-id="1dd1a-148">Group use</span></span>    | <span data-ttu-id="1dd1a-149">Nombre de Ejemplo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="1dd1a-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="1dd1a-150">Disponible</span><span class="sxs-lookup"><span data-stu-id="1dd1a-150">Available</span></span> |  <span data-ttu-id="1dd1a-151">La aplicación estará disponible desde Portal de empresa o sitio web.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="1dd1a-152">MMD– *nombre de la aplicación:* disponible</span><span class="sxs-lookup"><span data-stu-id="1dd1a-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="1dd1a-153">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1dd1a-153">Required</span></span> |  <span data-ttu-id="1dd1a-154">La aplicación se instala en dispositivos de los grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="1dd1a-155">MMD– *nombre de la aplicación:* obligatorio</span><span class="sxs-lookup"><span data-stu-id="1dd1a-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="1dd1a-156">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="1dd1a-156">Uninstall</span></span> |  <span data-ttu-id="1dd1a-157">La aplicación se desinstala de los dispositivos de los grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="1dd1a-158">MMD : *nombre de la aplicación:* desinstalar</span><span class="sxs-lookup"><span data-stu-id="1dd1a-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="1dd1a-159">Agrega usuarios a estos grupos para que la aplicación esté disponible, instale la aplicación o quite la aplicación de su Escritorio administrado de Microsoft dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="1dd1a-160">Paso 3: Asignar aplicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="1dd1a-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="1dd1a-161">**Para asignar la aplicación a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="1dd1a-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="1dd1a-162">Inicie sesión en [Escritorio administrado de Microsoft portal de administración](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="1dd1a-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="1dd1a-163">En el panel Escritorio administrado, seleccione **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="1dd1a-164">En la carga de trabajo Aplicaciones, selecciona la aplicación a la que quieres asignar usuarios y selecciona **Asignar grupos de usuarios.**</span><span class="sxs-lookup"><span data-stu-id="1dd1a-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="1dd1a-165">Para la aplicación específica, selecciona un tipo de asignación (Disponible, Obligatorio, Desinstalar) y asigna el grupo adecuado.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="1dd1a-166">En el panel Asignar aplicaciones, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="1dd1a-167">Pasos para empezar con Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="1dd1a-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="1dd1a-168">Agregar y verificar los contactos de administración en el portal de administración </span><span class="sxs-lookup"><span data-stu-id="1dd1a-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="1dd1a-169">Ajustar el acceso condicional</span><span class="sxs-lookup"><span data-stu-id="1dd1a-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="1dd1a-170">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="1dd1a-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="1dd1a-171">Desplegar el portal de empresa de Intune</span><span class="sxs-lookup"><span data-stu-id="1dd1a-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="1dd1a-172">Habilitar Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="1dd1a-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="1dd1a-173">Instalar dispositivos</span><span class="sxs-lookup"><span data-stu-id="1dd1a-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="1dd1a-174">Prepare a los usuarios para que usen los dispositivos</span><span class="sxs-lookup"><span data-stu-id="1dd1a-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="1dd1a-175">Implementar aplicaciones (este tema)</span><span class="sxs-lookup"><span data-stu-id="1dd1a-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->