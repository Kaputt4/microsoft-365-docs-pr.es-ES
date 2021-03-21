---
title: Implementar aplicaciones en dispositivos
description: Información para agregar e implementar aplicaciones en dispositivos de Escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones lob
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
Parte de la incorporación a Microsoft Managed Desktop incluye agregar e implementar aplicaciones en los dispositivos del usuario. Una vez que estés usando el portal de Escritorio administrado de Microsoft, puedes agregar e implementar tus aplicaciones. 

El proceso general tiene este aspecto:
1. [Agregar aplicaciones al portal](#1) de Escritorio administrado de Microsoft: pueden ser aplicaciones de línea de negocio (LOB) existentes o aplicaciones de Microsoft Store para empresas que haya sincronizado con Intune. 
2. [Crear grupos de Azure Active Directory (AD)](#2) para la asignación de aplicaciones: usará estos grupos para administrar la asignación de aplicaciones.
3. [Asignar aplicaciones a los usuarios](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Paso 1: Agregar aplicaciones al portal de Escritorio administrado de Microsoft
Puedes agregar aplicaciones basadas en Windows MSI o [Win32](#lob-apps)o microsoft [Store para](#msfb-apps) empresas a Microsoft Managed Desktop y, a continuación, implementarlas en dispositivos de Escritorio administrado de Microsoft.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Aplicaciones basadas en Msi de Windows o Win32 para Microsoft Managed Desktop

Puedes agregar las aplicaciones de línea de negocio (LOB) al portal de escritorio administrado de Microsoft. Para obtener información sobre los requisitos de las aplicaciones instaladas en dispositivos de Escritorio administrado de Microsoft, vea Requisitos de la aplicación [de Escritorio administrado de Microsoft.](../service-description/mmd-app-requirements.md)

En este procedimiento, seleccionarás el tipo de aplicación que quieres agregar y, a continuación, configurarás y cargarás el origen de la aplicación. 

**Para agregar la aplicación lob o la aplicación de Windows al portal de escritorio administrado de Microsoft**

Puede iniciar sesión en el portal de Escritorio administrado de Microsoft o iniciar sesión en Intune y, a continuación, buscar Microsoft Managed Desktop. Mostraremos el inicio de sesión en el portal de Escritorio administrado de Microsoft. 

1.    Inicie sesión en [el portal de administración de Escritorio administrado de Microsoft](https://aka.ms/mmdportal). 
2.    En **Inventario,** seleccione **Aplicaciones**.
3.    En la carga de trabajo Aplicaciones, seleccione **Agregar**.
4.    En **Agregar aplicación,** selecciona **Aplicación de línea de negocio** o Aplicación de Windows **(Win32).**
    - Si seleccionaste **Aplicación** de línea de negocio, consulta Agregar una aplicación de línea de negocio de [Windows a Microsoft Intune](/intune/lob-apps-windows) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de línea de negocio.
    - Si seleccionaste **la aplicación de Windows (Win32),** consulta Administración de aplicaciones de [Win32](/intune/apps-win32-app-management) para obtener instrucciones sobre cómo agregar y configurar aplicaciones de Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Aplicaciones de Microsoft Store para empresas
Si no te has registrado en Microsoft Store para empresas, puedes registrarte cuando compres aplicaciones. Después de tener las aplicaciones, puedes sincronizarlas con Microsoft Managed Desktop. 

**Para comprar aplicaciones en la Microsoft Store para empresas**

1. Inicia sesión en [microsoft store para empresas](https://businessstore.microsoft.com) con tu cuenta de administrador de microsoft store para empresas.
2. Seleccione **Tienda para mi grupo**.
3. Usa Buscar para buscar la aplicación que quieras y selecciona la aplicación.
4. En los detalles del producto, selecciona **Obtener la aplicación**. Microsoft Store agrega la aplicación a **Tus productos** para tu organización.

**Para forzar una sincronización entre Intune y Microsoft Store para empresas**
1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecciona **Tenant administration**  >  **Connectors and tokens** Microsoft Store for  >  **Business**.
3. Selecciona **Sincronizar** para obtener las aplicaciones que compraste de Microsoft Store en Intune.

**Para comprobar que está activa una sincronización entre Intune y Microsoft Store para empresas**
1. Inicia sesión en [microsoft store para empresas](https://businessstore.microsoft.com) con tu cuenta de administrador de microsoft store para empresas.
2. Seleccione **Administrar**.
3. Seleccione **Configuración** y, a continuación, **seleccione Distribuir**.
4. En **Herramientas de administración,** compruebe que Intune aparece y que el estado es **Activo**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Paso 2: Crear grupos de Azure AD

Crea tres grupos de Azure AD para cada aplicación. En esta tabla se describen los grupos que necesitará (Disponible, Obligatorio y Desinstalar). 

Tipo de asignación de aplicaciones |    Uso en grupo    | Nombre de Ejemplo de Azure AD
--- | --- | ---
Disponible |  La aplicación estará disponible desde la aplicación o el sitio web del Portal de empresa. | MMD– *nombre de la aplicación:* disponible
Obligatorio |  La aplicación se instala en dispositivos de los grupos seleccionados. | MMD– *nombre de la aplicación:* obligatorio
Uninstall |  La aplicación se desinstala de los dispositivos de los grupos seleccionados. | MMD : *nombre de la aplicación:* desinstalar

Agrega a los usuarios a estos grupos para que la aplicación esté disponible, instale la aplicación o quite la aplicación de su dispositivo de Escritorio administrado de Microsoft. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Paso 3: Asignar aplicaciones a los usuarios

**Para asignar la aplicación a los usuarios**

1. Inicie sesión en [el portal de administración de Escritorio administrado de Microsoft](https://aka.ms/mmdportal).
2. En el panel Escritorio administrado, seleccione **Aplicaciones**.
3. En la carga de trabajo Aplicaciones, selecciona la aplicación a la que quieres asignar usuarios y selecciona **Asignar grupos de usuarios.**
4. Para la aplicación específica, selecciona un tipo de asignación (Disponible, Obligatorio, Desinstalar) y asigna el grupo adecuado.
5. En el panel Asignar aplicaciones, seleccione **Aceptar**.


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

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