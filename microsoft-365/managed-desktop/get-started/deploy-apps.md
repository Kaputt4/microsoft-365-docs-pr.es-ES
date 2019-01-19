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
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Implementar aplicaciones en los dispositivos de escritorio administrado de Microsoft
Parte de incorporación a Microsoft Managed Desktop incluye agregar e implementar aplicaciones en los dispositivos del usuario. Una vez que usa el portal de escritorio administrado de Microsoft, puede agregar e implementar sus aplicaciones. 

El proceso general tiene este aspecto:
1. [Agregar aplicaciones al portal de Microsoft Managed Desktop](#1) : Esto puede ser existentes de aplicaciones de línea de negocio (LOB) o aplicaciones de Microsoft Store para la empresa que ha sincronizado con Intune. 
2. [Grupos de crear Azure Active Directory (AD) para la asignación de aplicaciones](#2) - utilizará estos grupos para administrar la asignación de aplicaciones.
3. [Asignar aplicaciones a los usuarios](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Paso 1: Agregar aplicaciones al portal de escritorio administrado de Microsoft
Puede agregar [Win32, aplicaciones basadas en MSI de Windows](#lob-apps)o [Almacenamiento de Microsoft para aplicaciones empresariales](#msfb-apps) a administrado de escritorio de Microsoft y, a continuación, implementarlas en los dispositivos de escritorio administrado de Microsoft.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Aplicaciones basadas en MSI de Win32 o de Windows a Microsoft administrado de escritorio

Puede agregar sus aplicaciones de línea de negocio (LOB) en el portal de Microsoft Managed Desktop. Para obtener información sobre los requisitos para las aplicaciones instaladas en los dispositivos de escritorio administrado de Microsoft, vea [requisitos de la aplicación de escritorio administrado de Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

En este procedimiento, seleccione qué tipo de aplicación que desea agregar y, a continuación, configurar y cargar el origen de la aplicación. 

**Para agregar la aplicación LOB o una aplicación de Windows al portal de escritorio administrado de Microsoft**

Puede inicie sesión en el portal de escritorio administrado de Microsoft, o inicie sesión en Intune y, a continuación, busque Microsoft Managed Desktop. Le mostraremos el inicio de sesión en el portal de Microsoft Managed Desktop. 

1.  Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mmdportal). 
2.  En el **inventario**, seleccione **aplicaciones**.
3.  En la carga de trabajo de aplicaciones, seleccione **Agregar**.
4.  En **Agregar aplicación**, seleccione **aplicación de línea de negocio** o **aplicación de Windows (Win32) - obtener una vista previa**.
    - Si ha seleccionado la **aplicación de línea de negocio**, consulte [Agregar una aplicación de línea de negocio de Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.
    - Si ha seleccionado **Mostrar una vista previa en la aplicación de Windows (Win32) -**, consulte [administración de aplicaciones de Win32](https://docs.microsoft.com/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Almacén de Microsoft para aplicaciones empresariales
Si se ha suscrito con Microsoft Store para la empresa, puede registrarse cuando compre para las aplicaciones. Una vez que sus aplicaciones, se puede sincronizar con Microsoft Managed Desktop. 

**Comprar aplicaciones de Microsoft Store para la empresa**

1. Inicie sesión en el [Almacén de Microsoft para la empresa](https://businessstore.microsoft.com) con su Store Microsoft para la cuenta de administrador empresarial.
2. Seleccione la **tienda para mi grupo**.
3. Usar la búsqueda para encontrar la aplicación que desee y seleccione la aplicación.
4. En los detalles del producto, seleccione **obtener la aplicación**. Microsoft Store agrega la aplicación a los **Servicios de & de productos** para su organización.

**Para forzar una sincronización entre Intune y Store de Microsoft para la empresa**
1. Inicie sesión en el [Portal de Azure](https://portal.azure.com/) como administrador de Intune o un administrador Global para el inquilino
2. Seleccione **todos los servicios > Intune**. Intune se encuentra en la supervisión + administración de sección.
3. En el panel Intune, seleccione **Aplicaciones de cliente**y, a continuación, seleccione el **Almacén de Microsoft para la empresa**.
4. Seleccione **Habilitar** esta opción para sincronizar su Store Microsoft para aplicaciones empresariales con Intune.
    - Si no lo ha hecho ya, inicio de sesión de seguridad y asociar su Microsoft almacenar para la cuenta de empresa con Intune
    - Seleccione el idioma en el que las aplicaciones de Microsoft Store para la empresa se mostrará en la consola Intune
    - Seleccione de **sincronización** para sincronizar su Store Microsoft para aplicaciones empresariales con Intune.
    - Compruebe que la sincronización entre Microsoft Store para la empresa y Intune está activa (el paso siguiente). 

**Para comprobar que una sincronización entre Intune y Store de Microsoft para la empresa está activa**
1. Inicie sesión en el [Almacén de Microsoft para la empresa](https://businessstore.microsoft.com) con su Store Microsoft para la cuenta de administrador empresarial.
2. Seleccione **Administrar**.
3. Seleccione **configuración** y, a continuación, seleccione **distribuir**.
4. En **Herramientas de administración**, compruebe que aparezca Intune y que el estado es **activo**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Paso 2: Crear grupos de Azure AD

Cree tres grupos de Azure AD para cada aplicación. En esta tabla se describe los grupos que necesitará (disponible, es necesario y desinstalar). 

Tipo de asignación de aplicación |   Uso de grupo   | Nombre de ejemplo Azure AD
--- | --- | ---
Disponible |  La aplicación estará disponible desde la aplicación de Portal de empresa o sitio Web. | MMD: *nombre de la aplicación* – disponible
Requerido |  La aplicación se instala en los dispositivos en los grupos seleccionados. | MMD – requerido un *nombre de la aplicación* :
Desinstalar |  TThe aplicación se ha desinstalado desde dispositivos en los grupos seleccionados. | MMD: *nombre de la aplicación* : desinstalar

Agregue los usuarios a estos grupos para hacer que la aplicación disponible, instalar la aplicación o bien quitar la aplicación de su dispositivo de escritorio de Microsoft administrado. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Paso 3: Asignar aplicaciones a los usuarios

**Para asignar la aplicación a los usuarios**

1. Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mmdportal).
2. En el panel de escritorio administrado, seleccione **aplicaciones**.
3. En la carga de trabajo de aplicaciones, seleccione la aplicación que desea asignar a los usuarios y seleccione **asignar grupos de usuarios**.
4. Para la aplicación específica, seleccione un tipo de asignación (disponible, es necesario, desinstalar) y asignar al grupo adecuado.
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