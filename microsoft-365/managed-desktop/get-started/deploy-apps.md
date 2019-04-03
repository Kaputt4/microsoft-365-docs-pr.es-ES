---
title: Implementación de aplicaciones para dispositivos de escritorio administrados por Microsoft
description: Información para agregar e implementar aplicaciones en dispositivos de escritorio administrados por Microsoft.
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de LOB
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5ccb240460958d5978f4fd19e08652123790784e
ms.sourcegitcommit: 2211f57c268754d242d6331c188143f818f5a9f4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31039599"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Implementar aplicaciones en dispositivos de escritorio administrados por Microsoft
Parte del escritorio administrado de incorporación a Microsoft incluye la adición e implementación de aplicaciones en los dispositivos del usuario. Una vez que esté usando Microsoft manAged Desktop portal, puede Agregar e implementar sus aplicaciones. 

El proceso general tiene el siguiente aspecto:
1. [Agregar aplicaciones a Microsoft Managed Desktop portal](#1) : esto puede ser una aplicación de línea de negocio (LOB) existente o aplicaciones de Microsoft Store para empresas que haya sincronizado con Intune. 
2. [Crear grupos de Azure Active Directory (ad) para la asignación de aplicaciones](#2) : estos grupos se usan para administrar la asignación de aplicaciones.
3. [Asignar aplicaciones a los usuarios](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Paso 1: agregar aplicaciones a Microsoft manAged Desktop portal
Puede agregar aplicaciones [Win32, o aplicaciones basadas en MSI de Windows](#lob-apps)o [aplicaciones de Microsoft Store for Business](#msfb-apps) a escritorio administrado por Microsoft y, a continuación, implementarlas en dispositivos de escritorio administrados por Microsoft.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 o aplicaciones basadas en MSI de Windows a escritorio administrado por Microsoft

Puede Agregar las aplicaciones de línea de negocio (LOB) a Microsoft manAged Desktop portal. Para obtener información sobre los requisitos de las aplicaciones instaladas en dispositivos de escritorio administrados por Microsoft, consulte requisitos de la [aplicación de escritorio administrada de Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

En este procedimiento, seleccionará el tipo de aplicación que desea agregar y, después, configurará y cargará el origen de la aplicación. 

**Para agregar la aplicación LOB o la aplicación de Windows a Microsoft manAged Desktop portal**

Puede iniciar sesión en el portal de escritorio administrado de Microsoft, o iniciar sesión en Intune y, a continuación, buscar Microsoft manAged Desktop. Se mostrará el inicio de sesión en Microsoft manAged Desktop portal. 

1.  Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mmdportal). 
2.  En **inventario**, seleccione **aplicaciones**.
3.  En la carga de trabajo de aplicaciones, seleccione **Agregar**.
4.  En **Agregar aplicación**, seleccione **aplicación de línea de negocio** o **aplicación de Windows (Win32): vista previa**.
    - Si seleccionó **aplicación de línea de negocio**, vea [Agregar una aplicación de línea de negocio de Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.
    - Si seleccionó **Windows App (Win32): vista previa**, vea [Administración de aplicaciones Win32](https://docs.microsoft.com/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Aplicaciones de Microsoft Store para empresas
Si no te has registrado en Microsoft Store para empresas, puedes registrarte en la tienda de aplicaciones. Una vez que tenga las aplicaciones, puede sincronizarlas con el escritorio administrado de Microsoft. 

**Para comprar aplicaciones de Microsoft Store para empresas**

1. Inicie sesión en [Microsoft Store para empresas](https://businessstore.microsoft.com) con su cuenta de administrador de Microsoft Store for Business.
2. Seleccione **comprar para mi grupo**.
3. Use la búsqueda para encontrar la aplicación que quiera y seleccione la aplicación.
4. En los detalles del producto, seleccione **obtener la aplicación**. Microsoft Store agrega la aplicación a **productos & Services** para la organización.

**Para forzar una sincronización entre Intune y Microsoft Store para empresas**
1. Iniciar sesión en [Azure portal](https://portal.azure.com/) como administrador de Intune o administrador global para su espacio empresarial
2. Seleccione **todos los servicios > Intune**. Intune se encuentra en la sección Monitoring + Management.
3. En el panel Intune, seleccione **aplicaciones cliente**y, a continuación, seleccione **Microsoft Store para empresas**.
4. Seleccione **Habilitar** para sincronizar las aplicaciones de Microsoft Store para empresas con Intune.
    - Si aún no lo ha hecho, Regístrese y asocie su cuenta de Microsoft Store for Business con Intune
    - Seleccione el idioma en el que se mostrarán las aplicaciones de Microsoft Store para empresas en la consola de Intune.
    - Seleccione **sincronizar** para sincronizar las aplicaciones de Microsoft Store para empresas con Intune.
    - Compruebe que la sincronización entre Microsoft Store para empresas y Intune esté activa (el siguiente paso). 

**Para comprobar que hay una sincronización activa entre Intune y Microsoft Store para empresas**
1. Inicie sesión en [Microsoft Store para empresas](https://businessstore.microsoft.com) con su cuenta de administrador de Microsoft Store for Business.
2. Seleccione **administrar**.
3. Seleccione **configuración** y, después, seleccione **distribuir**.
4. En **herramientas de administración**, compruebe que Intune aparece en la lista y que el estado es **activo**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Paso 2: crear grupos de Azure AD

Cree tres grupos de Azure AD para cada aplicación. En esta tabla se describen los grupos que necesitará (disponibles, obligatorios y de desinstalación). 

Tipo de asignación de aplicación |   Uso de grupo   | Nombre de ejemplo de Azure AD
--- | --- | ---
Disponible |  La aplicación estará disponible desde el sitio web o la aplicación del portal de empresa. | MMD: *nombre* de la aplicación: disponible
Obligatorio |  La aplicación se instala en los dispositivos de los grupos seleccionados. | MMD: *nombre* de la aplicación: obligatorio
Uninstall |  La aplicación se desinstala de los dispositivos en los grupos seleccionados. | MMD: *nombre* de la aplicación: desinstalar

Agregue los usuarios a estos grupos para hacer que la aplicación esté presente, instalar la aplicación o quitar la aplicación del dispositivo de escritorio administrado por Microsoft. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Paso 3: asignar aplicaciones a los usuarios

**Para asignar la aplicación a los usuarios**

1. Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mmdportal).
2. En el panel escritorio administrado, seleccione **aplicaciones**.
3. En la carga de trabajo de aplicaciones, seleccione la aplicación a la que desea asignar usuarios y seleccione **asignar grupos de usuarios**.
4. Para la aplicación específica, seleccione un tipo de asignación (disponible, obligatorio, desinstalar) y asigne el grupo adecuado.
5. En el panel asignar aplicaciones, seleccione **Aceptar**.

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