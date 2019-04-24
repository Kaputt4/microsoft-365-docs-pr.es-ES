---
title: Implementación de aplicaciones para dispositivos de escritorio administrados por Microsoft
description: Información para agregar e implementar aplicaciones en dispositivos de escritorio administrados por Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de LOB
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5ccb240460958d5978f4fd19e08652123790784e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282526"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="d22d8-104">Implementar aplicaciones en dispositivos de escritorio administrados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="d22d8-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d22d8-105">Parte del escritorio administrado de incorporación a Microsoft incluye la adición e implementación de aplicaciones en los dispositivos del usuario.</span><span class="sxs-lookup"><span data-stu-id="d22d8-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="d22d8-106">Una vez que esté usando Microsoft manAged Desktop portal, puede Agregar e implementar sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d22d8-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="d22d8-107">El proceso general tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="d22d8-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="d22d8-108">[Agregar aplicaciones a Microsoft Managed Desktop portal](#1) : esto puede ser una aplicación de línea de negocio (LOB) existente o aplicaciones de Microsoft Store para empresas que haya sincronizado con Intune.</span><span class="sxs-lookup"><span data-stu-id="d22d8-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="d22d8-109">[Crear grupos de Azure Active Directory (ad) para la asignación de aplicaciones](#2) : estos grupos se usan para administrar la asignación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d22d8-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="d22d8-110">Asignar aplicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="d22d8-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="d22d8-111">Paso 1: agregar aplicaciones a Microsoft manAged Desktop portal</span><span class="sxs-lookup"><span data-stu-id="d22d8-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="d22d8-112">Puede agregar aplicaciones [Win32, o aplicaciones basadas en MSI de Windows](#lob-apps)o [aplicaciones de Microsoft Store for Business](#msfb-apps) a escritorio administrado por Microsoft y, a continuación, implementarlas en dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d22d8-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="d22d8-113">Win32 o aplicaciones basadas en MSI de Windows a escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="d22d8-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="d22d8-114">Puede Agregar las aplicaciones de línea de negocio (LOB) a Microsoft manAged Desktop portal.</span><span class="sxs-lookup"><span data-stu-id="d22d8-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="d22d8-115">Para obtener información sobre los requisitos de las aplicaciones instaladas en dispositivos de escritorio administrados por Microsoft, consulte requisitos de la [aplicación de escritorio administrada de Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="d22d8-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="d22d8-116">En este procedimiento, seleccionará el tipo de aplicación que desea agregar y, después, configurará y cargará el origen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d22d8-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="d22d8-117">**Para agregar la aplicación LOB o la aplicación de Windows a Microsoft manAged Desktop portal**</span><span class="sxs-lookup"><span data-stu-id="d22d8-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="d22d8-118">Puede iniciar sesión en el portal de escritorio administrado de Microsoft, o iniciar sesión en Intune y, a continuación, buscar Microsoft manAged Desktop.</span><span class="sxs-lookup"><span data-stu-id="d22d8-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="d22d8-119">Se mostrará el inicio de sesión en Microsoft manAged Desktop portal.</span><span class="sxs-lookup"><span data-stu-id="d22d8-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="d22d8-120">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="d22d8-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="d22d8-121">En **inventario**, seleccione **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="d22d8-122">En la carga de trabajo de aplicaciones, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="d22d8-123">En **Agregar aplicación**, seleccione **aplicación de línea de negocio** o **aplicación de Windows (Win32): vista previa**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="d22d8-124">Si seleccionó **aplicación de línea de negocio**, vea [Agregar una aplicación de línea de negocio de Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="d22d8-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="d22d8-125">Si seleccionó **Windows App (Win32): vista previa**, vea [Administración de aplicaciones Win32](https://docs.microsoft.com/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="d22d8-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="d22d8-126">Aplicaciones de Microsoft Store para empresas</span><span class="sxs-lookup"><span data-stu-id="d22d8-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="d22d8-127">Si no te has registrado en Microsoft Store para empresas, puedes registrarte en la tienda de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d22d8-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="d22d8-128">Una vez que tenga las aplicaciones, puede sincronizarlas con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d22d8-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="d22d8-129">**Para comprar aplicaciones de Microsoft Store para empresas**</span><span class="sxs-lookup"><span data-stu-id="d22d8-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="d22d8-130">Inicie sesión en [Microsoft Store para empresas](https://businessstore.microsoft.com) con su cuenta de administrador de Microsoft Store for Business.</span><span class="sxs-lookup"><span data-stu-id="d22d8-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="d22d8-131">Seleccione **comprar para mi grupo**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="d22d8-132">Use la búsqueda para encontrar la aplicación que quiera y seleccione la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d22d8-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="d22d8-133">En los detalles del producto, seleccione **obtener la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="d22d8-134">Microsoft Store agrega la aplicación a **productos & Services** para la organización.</span><span class="sxs-lookup"><span data-stu-id="d22d8-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="d22d8-135">**Para forzar una sincronización entre Intune y Microsoft Store para empresas**</span><span class="sxs-lookup"><span data-stu-id="d22d8-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="d22d8-136">Iniciar sesión en [Azure portal](https://portal.azure.com/) como administrador de Intune o administrador global para su espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="d22d8-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="d22d8-137">Seleccione **todos los servicios > Intune**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-137">Select **All services > Intune**.</span></span> <span data-ttu-id="d22d8-138">Intune se encuentra en la sección Monitoring + Management.</span><span class="sxs-lookup"><span data-stu-id="d22d8-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="d22d8-139">En el panel Intune, seleccione **aplicaciones cliente**y, a continuación, seleccione **Microsoft Store para empresas**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="d22d8-140">Seleccione **Habilitar** para sincronizar las aplicaciones de Microsoft Store para empresas con Intune.</span><span class="sxs-lookup"><span data-stu-id="d22d8-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="d22d8-141">Si aún no lo ha hecho, Regístrese y asocie su cuenta de Microsoft Store for Business con Intune</span><span class="sxs-lookup"><span data-stu-id="d22d8-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="d22d8-142">Seleccione el idioma en el que se mostrarán las aplicaciones de Microsoft Store para empresas en la consola de Intune.</span><span class="sxs-lookup"><span data-stu-id="d22d8-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="d22d8-143">Seleccione **sincronizar** para sincronizar las aplicaciones de Microsoft Store para empresas con Intune.</span><span class="sxs-lookup"><span data-stu-id="d22d8-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="d22d8-144">Compruebe que la sincronización entre Microsoft Store para empresas y Intune esté activa (el siguiente paso).</span><span class="sxs-lookup"><span data-stu-id="d22d8-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="d22d8-145">**Para comprobar que hay una sincronización activa entre Intune y Microsoft Store para empresas**</span><span class="sxs-lookup"><span data-stu-id="d22d8-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="d22d8-146">Inicie sesión en [Microsoft Store para empresas](https://businessstore.microsoft.com) con su cuenta de administrador de Microsoft Store for Business.</span><span class="sxs-lookup"><span data-stu-id="d22d8-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="d22d8-147">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-147">Select **Manage**.</span></span>
3. <span data-ttu-id="d22d8-148">Seleccione **configuración** y, después, seleccione **distribuir**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="d22d8-149">En **herramientas de administración**, compruebe que Intune aparece en la lista y que el estado es **activo**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="d22d8-150">Paso 2: crear grupos de Azure AD</span><span class="sxs-lookup"><span data-stu-id="d22d8-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="d22d8-151">Cree tres grupos de Azure AD para cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="d22d8-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="d22d8-152">En esta tabla se describen los grupos que necesitará (disponibles, obligatorios y de desinstalación).</span><span class="sxs-lookup"><span data-stu-id="d22d8-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="d22d8-153">Tipo de asignación de aplicación</span><span class="sxs-lookup"><span data-stu-id="d22d8-153">App assignment type</span></span> |   <span data-ttu-id="d22d8-154">Uso de grupo</span><span class="sxs-lookup"><span data-stu-id="d22d8-154">Group use</span></span>   | <span data-ttu-id="d22d8-155">Nombre de ejemplo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="d22d8-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="d22d8-156">Disponible</span><span class="sxs-lookup"><span data-stu-id="d22d8-156">Available</span></span> |  <span data-ttu-id="d22d8-157">La aplicación estará disponible desde el sitio web o la aplicación del portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="d22d8-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="d22d8-158">MMD: *nombre* de la aplicación: disponible</span><span class="sxs-lookup"><span data-stu-id="d22d8-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="d22d8-159">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d22d8-159">Required</span></span> |  <span data-ttu-id="d22d8-160">La aplicación se instala en los dispositivos de los grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="d22d8-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="d22d8-161">MMD: *nombre* de la aplicación: obligatorio</span><span class="sxs-lookup"><span data-stu-id="d22d8-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="d22d8-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="d22d8-162">Uninstall</span></span> |  <span data-ttu-id="d22d8-163">La aplicación se desinstala de los dispositivos en los grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="d22d8-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="d22d8-164">MMD: *nombre* de la aplicación: desinstalar</span><span class="sxs-lookup"><span data-stu-id="d22d8-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="d22d8-165">Agregue los usuarios a estos grupos para hacer que la aplicación esté presente, instalar la aplicación o quitar la aplicación del dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d22d8-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="d22d8-166">Paso 3: asignar aplicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="d22d8-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="d22d8-167">**Para asignar la aplicación a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="d22d8-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="d22d8-168">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="d22d8-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="d22d8-169">En el panel escritorio administrado, seleccione **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="d22d8-170">En la carga de trabajo de aplicaciones, seleccione la aplicación a la que desea asignar usuarios y seleccione **asignar grupos de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="d22d8-171">Para la aplicación específica, seleccione un tipo de asignación (disponible, obligatorio, desinstalar) y asigne el grupo adecuado.</span><span class="sxs-lookup"><span data-stu-id="d22d8-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="d22d8-172">En el panel asignar aplicaciones, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d22d8-172">In the Assign Apps pane, select **OK**.</span></span>

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->