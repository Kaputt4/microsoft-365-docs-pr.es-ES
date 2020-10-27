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
# <a name="deploy-apps-to-devices"></a>Implementar aplicaciones en dispositivos
Parte del escritorio administrado de incorporación a Microsoft incluye la adición e implementación de aplicaciones en los dispositivos del usuario. Una vez que esté usando Microsoft Managed Desktop portal, puede Agregar e implementar sus aplicaciones. 

El proceso general tiene el siguiente aspecto:
1. [Agregar aplicaciones a Microsoft Managed Desktop portal](#1) : esto puede ser una aplicación de línea de negocio (LOB) existente o aplicaciones de Microsoft Store para empresas que haya sincronizado con Intune. 
2. [Crear grupos de Azure Active Directory (ad) para la asignación de aplicaciones](#2) : estos grupos se usan para administrar la asignación de aplicaciones.
3. [Asignar aplicaciones a los usuarios](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Paso 1: agregar aplicaciones a Microsoft Managed Desktop portal
Puede agregar aplicaciones [Win32, o aplicaciones basadas en MSI de Windows](#lob-apps)o [aplicaciones de Microsoft Store for Business](#msfb-apps) a escritorio administrado por Microsoft y, a continuación, implementarlas en dispositivos de escritorio administrados por Microsoft.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 o aplicaciones basadas en MSI de Windows a escritorio administrado por Microsoft

Puede Agregar las aplicaciones de línea de negocio (LOB) a Microsoft Managed Desktop portal. Para obtener información sobre los requisitos de las aplicaciones instaladas en dispositivos de escritorio administrados por Microsoft, consulte requisitos de la [aplicación de escritorio administrada de Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

En este procedimiento, seleccionará el tipo de aplicación que desea agregar y, después, configurará y cargará el origen de la aplicación. 

**Para agregar la aplicación LOB o la aplicación de Windows a Microsoft Managed Desktop portal**

Puede iniciar sesión en el portal de escritorio administrado de Microsoft, o iniciar sesión en Intune y, a continuación, buscar Microsoft Managed Desktop. Se mostrará el inicio de sesión en Microsoft Managed Desktop portal. 

1.    Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mmdportal). 
2.    En **inventario** , seleccione **aplicaciones** .
3.    En la carga de trabajo de aplicaciones, seleccione **Agregar** .
4.    En **Agregar aplicación** , seleccione **aplicación de línea de negocio** o **aplicación de Windows (Win32)** .
    - Si seleccionó **aplicación de línea de negocio** , vea [Agregar una aplicación de línea de negocio de Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.
    - Si seleccionó **Windows App (Win32)** , vea [Administración de aplicaciones Win32](https://docs.microsoft.com/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar aplicaciones para Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Aplicaciones de Microsoft Store para empresas
Si no te has registrado en Microsoft Store para empresas, puedes registrarte en la tienda de aplicaciones. Una vez que tenga las aplicaciones, puede sincronizarlas con el escritorio administrado de Microsoft. 

**Para comprar aplicaciones de Microsoft Store para empresas**

1. Inicie sesión en [Microsoft Store para empresas](https://businessstore.microsoft.com) con su cuenta de administrador de Microsoft Store for Business.
2. Seleccione **comprar para mi grupo** .
3. Use la búsqueda para encontrar la aplicación que quiera y seleccione la aplicación.
4. En los detalles del producto, seleccione **obtener la aplicación** . Microsoft Store agrega la aplicación a **los productos** de la organización.

**Para forzar una sincronización entre Intune y Microsoft Store para empresas**
1. Inicie sesión en el [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione conectores de **Administración de inquilinos**  >  **y tokens**  >  **de Microsoft Store para empresas** .
3. Seleccione **sincronizar** para obtener las aplicaciones que ha comprado de Microsoft Store a Intune.

**Para comprobar que hay una sincronización activa entre Intune y Microsoft Store para empresas**
1. Inicie sesión en [Microsoft Store para empresas](https://businessstore.microsoft.com) con su cuenta de administrador de Microsoft Store for Business.
2. Seleccione **administrar** .
3. Seleccione **configuración** y, después, seleccione **distribuir** .
4. En **herramientas de administración** , compruebe que Intune aparece en la lista y que el estado es **activo** .  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Paso 2: crear grupos de Azure AD

Cree tres grupos de Azure AD para cada aplicación. En esta tabla se describen los grupos que necesitará (disponibles, obligatorios y de desinstalación). 

Tipo de asignación de aplicación |    Uso de grupo    | Nombre de ejemplo de Azure AD
--- | --- | ---
Disponible |  La aplicación estará disponible desde el sitio web o la aplicación del portal de empresa. | MMD: *nombre* de la aplicación: disponible
Necesario |  La aplicación se instala en los dispositivos de los grupos seleccionados. | MMD: *nombre* de la aplicación: obligatorio
Uninstall |  La aplicación se desinstala de los dispositivos de los grupos seleccionados. | MMD: *nombre* de la aplicación: desinstalar

Agregue los usuarios a estos grupos para hacer que la aplicación esté disponible, instalar la aplicación o quitar la aplicación de su dispositivo de escritorio administrado por Microsoft. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Paso 3: asignar aplicaciones a los usuarios

**Para asignar la aplicación a los usuarios**

1. Inicie sesión en el [portal de administración de escritorio administrado de Microsoft](https://aka.ms/mmdportal).
2. En el panel escritorio administrado, seleccione **aplicaciones** .
3. En la carga de trabajo de aplicaciones, seleccione la aplicación a la que desea asignar usuarios y seleccione **asignar grupos de usuarios** .
4. Para la aplicación específica, seleccione un tipo de asignación (disponible, obligatorio, desinstalar) y asigne el grupo adecuado.
5. En el panel asignar aplicaciones, seleccione **Aceptar** .


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar a trabajar con el escritorio administrado de Microsoft

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. [Ajustar el acceso condicional](conditional-access.md)
3. [Asignar licencias](assign-licenses.md)
4. [Desplegar el portal de empresa de Intune](company-portal.md)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. Implementación de aplicaciones (este tema)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
