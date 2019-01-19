---
title: Implementar aplicaciones para dispositivos de escritorio administrado de Microsoft
description: Información para agregar e implementar aplicaciones en los dispositivos de escritorio administrado de Microsoft.
keywords: Administrado de escritorio de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones LOB
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341621"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="c73dc-104">Implementar aplicaciones en los dispositivos de escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c73dc-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="c73dc-p101">Parte de incorporación a Microsoft Managed Desktop incluye agregar e implementar aplicaciones en los dispositivos del usuario. Una vez que usa el portal de escritorio administrado de Microsoft, puede agregar e implementar sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c73dc-p101">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices. Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="c73dc-107">El proceso general tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="c73dc-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="c73dc-108">[Agregar aplicaciones al portal de Microsoft Managed Desktop](#1) : Esto puede ser existentes de aplicaciones de línea de negocio (LOB) o aplicaciones de Microsoft Store para la empresa que ha sincronizado con Intune.</span><span class="sxs-lookup"><span data-stu-id="c73dc-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="c73dc-109">[Grupos de crear Azure Active Directory (AD) para la asignación de aplicaciones](#2) - utilizará estos grupos para administrar la asignación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c73dc-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="c73dc-110">Asignar aplicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="c73dc-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="c73dc-111">Paso 1: Agregar aplicaciones al portal de escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c73dc-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="c73dc-112">Puede agregar [Win32, aplicaciones basadas en MSI de Windows](#lob-apps)o [Almacenamiento de Microsoft para aplicaciones empresariales](#msfb-apps) a administrado de escritorio de Microsoft y, a continuación, implementarlas en los dispositivos de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c73dc-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="c73dc-113">Aplicaciones basadas en MSI de Win32 o de Windows a Microsoft administrado de escritorio</span><span class="sxs-lookup"><span data-stu-id="c73dc-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="c73dc-p102">Puede agregar sus aplicaciones de línea de negocio (LOB) en el portal de Microsoft Managed Desktop. Para obtener información sobre los requisitos para las aplicaciones instaladas en los dispositivos de escritorio administrado de Microsoft, vea [requisitos de la aplicación de escritorio administrado de Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="c73dc-p102">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal. For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="c73dc-116">En este procedimiento, seleccione qué tipo de aplicación que desea agregar y, a continuación, configurar y cargar el origen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c73dc-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="c73dc-117">**Para agregar la aplicación LOB o una aplicación de Windows al portal de escritorio administrado de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="c73dc-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="c73dc-p103">Puede inicie sesión en el portal de escritorio administrado de Microsoft, o inicie sesión en Intune y, a continuación, busque Microsoft Managed Desktop. Le mostraremos el inicio de sesión en el portal de Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c73dc-p103">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop. We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="c73dc-120">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="c73dc-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="c73dc-121">En el **inventario**, seleccione **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="c73dc-122">En la carga de trabajo de aplicaciones, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="c73dc-123">En **Agregar aplicación**, seleccione **aplicación de línea de negocio** o **aplicación de Windows (Win32) - obtener una vista previa**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="c73dc-124">Si ha seleccionado la **aplicación de línea de negocio**, consulte [Agregar una aplicación de línea de negocio de Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="c73dc-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="c73dc-125">Si ha seleccionado **Mostrar una vista previa en la aplicación de Windows (Win32) -**, consulte [administración de aplicaciones de Win32](https://docs.microsoft.com/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="c73dc-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="c73dc-126">Almacén de Microsoft para aplicaciones empresariales</span><span class="sxs-lookup"><span data-stu-id="c73dc-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="c73dc-p104">Si se ha suscrito con Microsoft Store para la empresa, puede registrarse cuando compre para las aplicaciones. Una vez que sus aplicaciones, se puede sincronizar con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c73dc-p104">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps. After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="c73dc-129">**Comprar aplicaciones de Microsoft Store para la empresa**</span><span class="sxs-lookup"><span data-stu-id="c73dc-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="c73dc-130">Inicie sesión en el [Almacén de Microsoft para la empresa](https://businessstore.microsoft.com) con su Store Microsoft para la cuenta de administrador empresarial.</span><span class="sxs-lookup"><span data-stu-id="c73dc-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="c73dc-131">Seleccione la **tienda para mi grupo**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="c73dc-132">Usar la búsqueda para encontrar la aplicación que desee y seleccione la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c73dc-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="c73dc-p105">En los detalles del producto, seleccione **obtener la aplicación**. Microsoft Store agrega la aplicación a los **Servicios de & de productos** para su organización.</span><span class="sxs-lookup"><span data-stu-id="c73dc-p105">On the product details, select **Get the App**. Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="c73dc-135">**Para forzar una sincronización entre Intune y Store de Microsoft para la empresa**</span><span class="sxs-lookup"><span data-stu-id="c73dc-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="c73dc-136">Inicie sesión en el [Portal de Azure](https://portal.azure.com/) como administrador de Intune o un administrador Global para el inquilino</span><span class="sxs-lookup"><span data-stu-id="c73dc-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="c73dc-p106">Seleccione **todos los servicios > Intune**. Intune se encuentra en la supervisión + administración de sección.</span><span class="sxs-lookup"><span data-stu-id="c73dc-p106">Select **All services > Intune**. Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="c73dc-139">En el panel Intune, seleccione **Aplicaciones de cliente**y, a continuación, seleccione el **Almacén de Microsoft para la empresa**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="c73dc-140">Seleccione **Habilitar** esta opción para sincronizar su Store Microsoft para aplicaciones empresariales con Intune.</span><span class="sxs-lookup"><span data-stu-id="c73dc-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="c73dc-141">Si no lo ha hecho ya, inicio de sesión de seguridad y asociar su Microsoft almacenar para la cuenta de empresa con Intune</span><span class="sxs-lookup"><span data-stu-id="c73dc-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="c73dc-142">Seleccione el idioma en el que las aplicaciones de Microsoft Store para la empresa se mostrará en la consola Intune</span><span class="sxs-lookup"><span data-stu-id="c73dc-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="c73dc-143">Seleccione de **sincronización** para sincronizar su Store Microsoft para aplicaciones empresariales con Intune.</span><span class="sxs-lookup"><span data-stu-id="c73dc-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="c73dc-144">Compruebe que la sincronización entre Microsoft Store para la empresa y Intune está activa (el paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="c73dc-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="c73dc-145">**Para comprobar que una sincronización entre Intune y Store de Microsoft para la empresa está activa**</span><span class="sxs-lookup"><span data-stu-id="c73dc-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="c73dc-146">Inicie sesión en el [Almacén de Microsoft para la empresa](https://businessstore.microsoft.com) con su Store Microsoft para la cuenta de administrador empresarial.</span><span class="sxs-lookup"><span data-stu-id="c73dc-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="c73dc-147">Seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-147">Select **Manage**.</span></span>
3. <span data-ttu-id="c73dc-148">Seleccione **configuración** y, a continuación, seleccione **distribuir**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="c73dc-149">En **Herramientas de administración**, compruebe que aparezca Intune y que el estado es **activo**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="c73dc-150">Paso 2: Crear grupos de Azure AD</span><span class="sxs-lookup"><span data-stu-id="c73dc-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="c73dc-p107">Cree tres grupos de Azure AD para cada aplicación. En esta tabla se describe los grupos que necesitará (disponible, es necesario y desinstalar).</span><span class="sxs-lookup"><span data-stu-id="c73dc-p107">Create three Azure AD groups for each app. This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="c73dc-153">Tipo de asignación de aplicación</span><span class="sxs-lookup"><span data-stu-id="c73dc-153">App assignment type</span></span> |   <span data-ttu-id="c73dc-154">Uso de grupo</span><span class="sxs-lookup"><span data-stu-id="c73dc-154">Group use</span></span>   | <span data-ttu-id="c73dc-155">Nombre de ejemplo Azure AD</span><span class="sxs-lookup"><span data-stu-id="c73dc-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="c73dc-156">Disponible</span><span class="sxs-lookup"><span data-stu-id="c73dc-156">Available</span></span> |  <span data-ttu-id="c73dc-157">La aplicación estará disponible desde la aplicación de Portal de empresa o sitio Web.</span><span class="sxs-lookup"><span data-stu-id="c73dc-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="c73dc-158">MMD: *nombre de la aplicación* – disponible</span><span class="sxs-lookup"><span data-stu-id="c73dc-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="c73dc-159">Requerido</span><span class="sxs-lookup"><span data-stu-id="c73dc-159">Required</span></span> |  <span data-ttu-id="c73dc-160">La aplicación se instala en los dispositivos en los grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c73dc-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="c73dc-161">MMD – requerido un *nombre de la aplicación* :</span><span class="sxs-lookup"><span data-stu-id="c73dc-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="c73dc-162">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="c73dc-162">Uninstall</span></span> |  <span data-ttu-id="c73dc-163">TThe aplicación se ha desinstalado desde dispositivos en los grupos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c73dc-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="c73dc-164">MMD: *nombre de la aplicación* : desinstalar</span><span class="sxs-lookup"><span data-stu-id="c73dc-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="c73dc-165">Agregue los usuarios a estos grupos para hacer que la aplicación disponible, instalar la aplicación o bien quitar la aplicación de su dispositivo de escritorio de Microsoft administrado.</span><span class="sxs-lookup"><span data-stu-id="c73dc-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="c73dc-166">Paso 3: Asignar aplicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="c73dc-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="c73dc-167">**Para asignar la aplicación a los usuarios**</span><span class="sxs-lookup"><span data-stu-id="c73dc-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="c73dc-168">Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="c73dc-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="c73dc-169">En el panel de escritorio administrado, seleccione **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="c73dc-170">En la carga de trabajo de aplicaciones, seleccione la aplicación que desea asignar a los usuarios y seleccione **asignar grupos de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="c73dc-171">Para la aplicación específica, seleccione un tipo de asignación (disponible, es necesario, desinstalar) y asignar al grupo adecuado.</span><span class="sxs-lookup"><span data-stu-id="c73dc-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="c73dc-172">En el panel asignar aplicaciones, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c73dc-172">In the Assign Apps pane, select **OK**.</span></span>

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