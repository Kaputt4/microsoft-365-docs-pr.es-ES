---
title: Información general sobre la configuración
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Información general sobre la configuración de los pasos para Microsoft 365 Business.
ms.openlocfilehash: ae7ed0aab36a6e759e0f0c1fbc3d3183273a284e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074410"
---
# <a name="overview-of-setup"></a>Información general sobre el programa de instalación

La mayoría de los pasos de configuración pueden realizarse en el Asistente de configuración, pero también se incluyen otras opciones.


## <a name="step-1-add-your-domain-and-users"></a>Paso 1: agregar el dominio y los usuarios

   - **[Agregar el dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (si ha comprado su dominio durante el [Inicio de sesión](sign-up.md), este paso ya se ha realizado).

    - **Agregar usuarios**. Puede hacerlo de las tres maneras siguientes:
        - En el [Asistente](set-up.md#add-users-in-the-wizard).
        - Use la sincronización de directorios para [Agregar usuarios con Azure ad Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) si tiene un Active Directory local.
        - También puede [Agregar usuarios más adelante](add-users-m365b.md) en el centro de administración.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Paso 2: configurar directivas de seguridad y configurar dispositivos 

  - Use el [Asistente de configuración](set-up.md#set-up-security-policies-and-device-configurations) para configurar las directivas de dispositivo y seguridad. 
  - También puede agregar más o editarlos más adelante en el [centro de administración](view-policies-and-devices.md) y en el [portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)de Intune.
  - Además de la configuración de seguridad del asistente de configuración, puede aumentar la seguridad si agrega las siguientes opciones de configuración:

      - **Protección contra malware de correo electrónico**
      - **Vínculos seguros de la protección contra amenazas avanzada (ATP)**
      - **Datos adjuntos seguros ATP**
      - **Contra la suplantación de identidad ATP**
      - **Archivado de Exchange Online**
      - **Data Loss Prevention (DLP)**
      - **Azure Information Protection (Plan1**)

          Para empezar, vea [configurar las directivas de seguridad avanzada](set-up-advanced-security.md).

        Consulte también [las 10 formas principales de proteger su empresa de Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para obtener una guía de los procedimientos de seguridad recomendados.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Paso 3: configurar y administrar dispositivos con Windows 10

   Cuando se une a un dispositivo de Windows 10 a Azure AD, se le aplican las directivas que configuró en el [paso 2](#step-2-set-up-security-policies-and-configure-devices) .

   - Windows 10 Pro es un [requisito](pre-requisites-for-data-protection.md) previo para Microsoft 365 Business, pero si tiene Windows 7 Pro, Windows 8 Pro o Windows 8,1 Pro, su suscripción le da derecho a una [actualización a Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
    - Use el [Asistente](set-up.md#set-up-security-policies-and-device-configurations) para la instalación para configurar directivas para dispositivos con Windows 10.

## <a name="stes-4-install-office-365-business"></a>Stes 4: instalar Office 365 Business
- Puede instalar Office automáticamente en los dispositivos Windows mediante el Asistente de [configuración](set-up.md#deploy-office-365-client-apps).
- [Instalar Office](auto-install-or-uninstall-office.md) automáticamente desde el centro de administración.
- Permita que los usuarios [instalen aplicaciones de Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows y dispositivos.
     
## <a name="advanced"></a>Avanzadas
- **Usar AutoPilot para configurar nuevos dispositivos**
            
     Puede usar [Windows AutoPilot](add-autopilot-devices-and-profile.md) para preconfigurar automáticamente los **nuevos** dispositivos Windows 10 para un usuario, pero podría ser más fácil obtener un [asociado](https://www.microsoft.com/solution-providers/search) que lo haga por usted. También puede ir a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) y solicitar a un experto en la tecnología de la nube que configure los nuevos dispositivos que compre para usted.

- **Acceso a recursos locales**

     - Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business para proteger sus dispositivos con Windows 10 y mantener al mismo tiempo el acceso a los recursos locales que requieren autenticación local. Siga los pasos descritos en [enable Domain-joined Domain-Windows 10 Devices to be Managed Microsoft 365 Business](manage-windows-devices.md) to Configure this. Este es el método preferido y los dispositivos en este estado se denominan dispositivos híbridos Unidos de Azure AD.

    - Si su empresa tiene un Active Directory local que contiene algunos recursos locales (como impresoras y recursos compartidos de archivos), puede dar acceso a estos recursos a los dispositivos de Azure AD siguiendo los pasos que se indican a continuación: [acceso a recursos locales desde un Dispositivo unido a Azure AD en Microsoft 365 Business](access-resources.md).

  