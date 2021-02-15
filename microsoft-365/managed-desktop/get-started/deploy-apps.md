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
# <a name="deploy-apps-to-devices"></a>Implementar aplicaciones en dispositivos
Parte de la incorporación al Escritorio administrado de Microsoft incluye agregar e implementar aplicaciones en los dispositivos del usuario. Una vez que use el portal de Escritorio administrado de Microsoft, puede agregar e implementar las aplicaciones. 

El proceso general tiene este aspecto:
1. [Agregar aplicaciones al portal](#1) de escritorio administrado de Microsoft: pueden ser aplicaciones de línea de negocio (LOB) existentes o aplicaciones de la Microsoft Store para Empresas que hayas sincronizado con Intune. 
2. [Crear grupos de Azure Active Directory (AD)](#2) para la asignación de aplicaciones: usará estos grupos para administrar la asignación de aplicaciones.
3. [Asignar aplicaciones a los usuarios](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Paso 1: Agregar aplicaciones al portal de Escritorio administrado de Microsoft
Puedes agregar aplicaciones basadas en [Win32 o MSI](#lob-apps)de Windows, o aplicaciones de la [Microsoft Store](#msfb-apps) para Empresas al Escritorio administrado de Microsoft y, a continuación, implementarlas en dispositivos de Escritorio administrado de Microsoft.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Aplicaciones basadas en MSI de Windows o Win32 a Escritorio administrado de Microsoft

Puede agregar las aplicaciones de línea de negocio (LOB) al portal de Escritorio administrado de Microsoft. Para obtener información sobre los requisitos de las aplicaciones instaladas en dispositivos de Escritorio administrado de Microsoft, vea Requisitos de aplicaciones de [Escritorio administrado de Microsoft.](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)

En este procedimiento, seleccionarás el tipo de aplicación que quieres agregar y, a continuación, configurarás y cargarás el origen de la aplicación. 

**Para agregar la aplicación de LÍNEA DEB o la aplicación de Windows al portal de Escritorio administrado de Microsoft**

Puede iniciar sesión en el portal de Escritorio administrado de Microsoft o iniciar sesión en Intune y, a continuación, buscar escritorio administrado de Microsoft. Mostraremos el inicio de sesión en el portal de Escritorio administrado de Microsoft. 

1.    Inicie sesión en el [portal de administración de escritorio administrado de Microsoft.](https://aka.ms/mmdportal) 
2.    En **Inventario,** seleccione **Aplicaciones.**
3.    En la carga de trabajo Aplicaciones, seleccione **Agregar**.
4.    En **Agregar aplicación,** selecciona **aplicación de línea de negocio** o aplicación de Windows **(Win32).**
    - Si has seleccionado **la** aplicación de línea de negocio, consulta Agregar una aplicación de línea de negocio de [Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.
    - Si seleccionaste **la aplicación de Windows (Win32),** consulta administración de aplicaciones de [Win32](https://docs.microsoft.com/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Aplicaciones de la Microsoft Store para Empresas
Si no te has registrado en la Microsoft Store para Empresas, puedes registrarte cuando compres aplicaciones. Una vez que tenga las aplicaciones, puede sincronizarlas con escritorio administrado de Microsoft. 

**Para comprar aplicaciones desde la Microsoft Store para Empresas**

1. Inicia sesión en [la Microsoft Store para Empresas](https://businessstore.microsoft.com) con tu cuenta de administrador de la Microsoft Store para Empresas.
2. Selecciona **Tienda para mi grupo.**
3. Usa La búsqueda para encontrar la aplicación que quieres y selecciona la aplicación.
4. En los detalles del producto, seleccione **Obtener la aplicación.** Microsoft Store agrega la aplicación a **Los productos** de la organización.

**Para forzar una sincronización entre Intune y la Microsoft Store para Empresas**
1. Inicie sesión en el Centro [de administración de Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. Seleccione **Conectores de administración** de  >  **inquilinos y tokens** de la Microsoft Store para  >  **Empresas.**
3. Selecciona **Sincronizar** para obtener las aplicaciones que has comprado de Microsoft Store en Intune.

**Para comprobar que está activa una sincronización entre Intune y la Microsoft Store para Empresas**
1. Inicia sesión en [la Microsoft Store para Empresas](https://businessstore.microsoft.com) con tu cuenta de administrador de la Microsoft Store para Empresas.
2. Seleccione **Administrar**.
3. Seleccione **Configuración** y, a continuación, **seleccione Distribuir**.
4. En **Herramientas de administración,** compruebe que Intune aparece en la lista y que el estado es **Activo.**  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Paso 2: Crear grupos de Azure AD

Cree tres grupos de Azure AD para cada aplicación. En esta tabla se describen los grupos que necesitará (Disponible, Requerido y Desinstalar). 

Tipo de asignación de aplicación |    Uso de grupos    | Ejemplo de nombre de Azure AD
--- | --- | ---
Disponible |  La aplicación estará disponible desde la aplicación o el sitio web del Portal de empresa. | MMD– *nombre de la aplicación:* disponible
Obligatorio |  La aplicación se instala en dispositivos de los grupos seleccionados. | MMD: *nombre de la aplicación:* obligatorio
Uninstall |  La aplicación se desinstala de los dispositivos de los grupos seleccionados. | MMD – *nombre de la aplicación* – Desinstalar

Agregue los usuarios a estos grupos para que la aplicación esté disponible, instale la aplicación o quite la aplicación de su dispositivo de Escritorio administrado de Microsoft. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Paso 3: Asignar aplicaciones a los usuarios

**Para asignar la aplicación a los usuarios**

1. Inicie sesión en el [portal de administración de escritorio administrado de Microsoft.](https://aka.ms/mmdportal)
2. En el panel Escritorio administrado, seleccione **Aplicaciones.**
3. En la carga de trabajo Aplicaciones, seleccione la aplicación a la que desea asignar usuarios y seleccione **Asignar grupos de usuarios.**
4. Para la aplicación específica, seleccione un tipo de asignación (Disponible, Requerido, Desinstalar) y asigne el grupo adecuado.
5. En el panel Asignar aplicaciones, seleccione **Aceptar**.


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar a usar el Escritorio administrado de Microsoft

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. [Ajustar el acceso condicional](conditional-access.md)
3. [Asignar licencias](assign-licenses.md)
4. [Desplegar el portal de empresa de Intune](company-portal.md)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. Implementar aplicaciones (este tema)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
