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
# <a name="deploy-apps-to-devices"></a>Implementar aplicaciones en dispositivos
Parte de la incorporación a Escritorio administrado de Microsoft incluye agregar e implementar aplicaciones en los dispositivos del usuario. Una vez que estés usando el portal Escritorio administrado de Microsoft, puedes agregar e implementar tus aplicaciones. 

El proceso general tiene este aspecto:
1. [Agregar aplicaciones Escritorio administrado de Microsoft portal:](#1) pueden ser aplicaciones de línea de negocio (LOB) existentes o aplicaciones de Microsoft Store para Empresas que haya sincronizado con Intune. 
2. [Crear Azure Active Directory (AD) para la](#2) asignación de aplicaciones: usará estos grupos para administrar la asignación de aplicaciones.
3. [Asignar aplicaciones a los usuarios](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Paso 1: Agregar aplicaciones a Escritorio administrado de Microsoft portal
Puedes agregar [win32 o](#lob-apps)Windows aplicaciones basadas en [](#msfb-apps) MSI o Microsoft Store para Empresas aplicaciones a Escritorio administrado de Microsoft y, a continuación, implementarlas en Escritorio administrado de Microsoft dispositivos.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 o Windows aplicaciones basadas en MSI para Escritorio administrado de Microsoft

Puedes agregar las aplicaciones de línea de negocio (LOB) a Escritorio administrado de Microsoft portal. Para obtener información sobre los requisitos de las aplicaciones instaladas en Escritorio administrado de Microsoft dispositivos, consulte [Escritorio administrado de Microsoft de aplicaciones.](../service-description/mmd-app-requirements.md)

En este procedimiento, seleccionarás el tipo de aplicación que quieres agregar y, a continuación, configurarás y cargarás el origen de la aplicación. 

**Para agregar la aplicación de LOB o Windows aplicación a Escritorio administrado de Microsoft portal**

Puede iniciar sesión en Escritorio administrado de Microsoft portal o iniciar sesión en Intune y, a continuación, buscar Escritorio administrado de Microsoft. Mostraremos el inicio de sesión en Escritorio administrado de Microsoft portal. 

1.    Inicie sesión en [Escritorio administrado de Microsoft portal de administración](https://aka.ms/mmdportal). 
2.    En **Inventario,** seleccione **Aplicaciones**.
3.    En la carga de trabajo Aplicaciones, seleccione **Agregar**.
4.    En **Agregar aplicación,** selecciona **Aplicación de línea de negocio** o Windows aplicación **(Win32).**
    - Si seleccionaste **Aplicación** de línea de negocio, consulta Agregar una aplicación de línea de negocio de [Windows a Microsoft Intune](/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.
    - Si **seleccionaste Windows aplicación (Win32),** consulta Administración de aplicaciones de [Win32](/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar Windows aplicaciones.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store para Empresas aplicaciones
Si no te has registrado con Microsoft Store para Empresas, puedes registrarte cuando compres aplicaciones. Después de tener las aplicaciones, puedes sincronizarlas con Escritorio administrado de Microsoft. 

**Para comprar aplicaciones desde el Microsoft Store para Empresas**

1. Inicie sesión en [Microsoft Store para Empresas](https://businessstore.microsoft.com) con su cuenta Microsoft Store para Empresas administrador.
2. Seleccione **Tienda para mi grupo**.
3. Usa Buscar para buscar la aplicación que quieras y selecciona la aplicación.
4. En los detalles del producto, selecciona **Obtener la aplicación**. Microsoft Store agrega la aplicación a **Los productos** de la organización.

**Para forzar una sincronización entre Intune y Microsoft Store para Empresas**
1. Inicie sesión en el centro [Microsoft Endpoint Manager administración](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Conectores de administración** de  >  **inquilinos y tokens**  >  **Microsoft Store para Empresas**.
3. Selecciona **Sincronizar** para obtener las aplicaciones que has comprado de la Microsoft Store en Intune.

**Para comprobar que una sincronización entre Intune y Microsoft Store para Empresas está activa**
1. Inicie sesión en [Microsoft Store para Empresas](https://businessstore.microsoft.com) con su cuenta Microsoft Store para Empresas administrador.
2. Seleccione **Administrar**.
3. Seleccione **Configuración** y, a continuación, **seleccione Distribuir**.
4. En **Herramientas de administración,** compruebe que Intune aparece y que el estado es **Activo**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Paso 2: Crear grupos de Azure AD

Crea tres grupos de Azure AD para cada aplicación. En esta tabla se describen los grupos que necesitará (Disponible, Obligatorio y Desinstalar). 

Tipo de asignación de aplicaciones |    Uso en grupo    | Nombre de Ejemplo de Azure AD
--- | --- | ---
Disponible |  La aplicación estará disponible desde Portal de empresa o sitio web. | MMD– *nombre de la aplicación:* disponible
Obligatorio |  La aplicación se instala en dispositivos de los grupos seleccionados. | MMD– *nombre de la aplicación:* obligatorio
Desinstalar |  La aplicación se desinstala de los dispositivos de los grupos seleccionados. | MMD : *nombre de la aplicación:* desinstalar

Agrega usuarios a estos grupos para que la aplicación esté disponible, instale la aplicación o quite la aplicación de su Escritorio administrado de Microsoft dispositivo. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Paso 3: Asignar aplicaciones a los usuarios

**Para asignar la aplicación a los usuarios**

1. Inicie sesión en [Escritorio administrado de Microsoft portal de administración](https://aka.ms/mmdportal).
2. En el panel Escritorio administrado, seleccione **Aplicaciones**.
3. En la carga de trabajo Aplicaciones, selecciona la aplicación a la que quieres asignar usuarios y selecciona **Asignar grupos de usuarios.**
4. Para la aplicación específica, selecciona un tipo de asignación (Disponible, Obligatorio, Desinstalar) y asigna el grupo adecuado.
5. En el panel Asignar aplicaciones, seleccione **Aceptar**.


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Escritorio administrado de Microsoft

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