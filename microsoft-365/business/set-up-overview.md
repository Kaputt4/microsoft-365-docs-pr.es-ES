---
title: Información general sobre la configuración
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Obtenga información sobre los pasos de configuración para Microsoft 365 empresa Premium, suscribirse, agregar un dominio y usuarios, configurar directivas de seguridad y mucho más.
ms.openlocfilehash: 8b26d423d4f62ee8f9ea4a61eb8f7efa72ee26cb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633363"
---
# <a name="overview-of-setup"></a>Información general sobre la configuración

Vea un breve vídeo sobre la configuración de Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

La mayoría de los pasos de configuración pueden realizarse en el Asistente de configuración, pero también se muestran otras opciones.

## <a name="step-1-add-your-domain-and-users"></a>Paso 1: agregar el dominio y los usuarios

   - **[Agregar el dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (si ha comprado su dominio durante el [registro](sign-up.md), este paso ya se ha realizado).

    - **Agregar usuarios**. Puede Agregar usuarios de las tres maneras siguientes:
        - En el [Asistente](set-up.md#add-users-in-the-wizard).
        - Use la sincronización de directorios para [Agregar usuarios con Azure ad Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) si tiene un Active Directory local.
        - También puede [Agregar usuarios más adelante](add-users-m365b.md) en el centro de administración.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Paso 2: configurar directivas de seguridad y configurar dispositivos 

  - Use el [Asistente](set-up.md#protect-your-organization) para la instalación para configurar las directivas del dispositivo. 
  - También puede agregar más o editarlos más adelante en el [centro de administración](view-policies-and-devices.md) y en el [portal de Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - El Asistente para la instalación también configurará la protección contra amenazas básica y la configuración de prevención de pérdida de datos.
  
  Además de la configuración de seguridad del asistente de configuración, puede aumentar la seguridad si agrega las siguientes opciones de configuración:

- **Protección contra malware de correo electrónico**
- **Contra la suplantación de identidad ATP**
- **Archivado de Exchange Online**
- **Azure Information Protection (Plan1**)

Para empezar, consulte [aumentar la protección contra amenazas](increase-threat-protection.md) y [configurar las características de cumplimiento](set-up-compliance.md).

Consulte también [las 10 principales formas de proteger su Microsoft 365 empresa Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para obtener una guía básica de los procedimientos de seguridad.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Paso 3: configurar y administrar dispositivos con Windows 10

Después de ejecutar el Asistente para la configuración, querrá proctect todos los equipos de la Windwos 10 en su organización.
  
- Windows 10 Pro es un [requisito previo](pre-requisites-for-data-protection.md) para Microsoft 365 empresa Premium, pero si tiene Windows 7 Pro, Windows 8 Pro o Windows 8,1 Pro, su suscripción le da derecho a una [actualización a Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Siga los pasos que se indican en [proteger equipos con Windows 10](secure-win-10-pcs.md) para configurar directivas para dispositivos con Windows 10.

Cuando se une a un dispositivo de Windows 10 a Azure AD, se aplican las directivas que configuras para los equipos con Windows 10. Para obtener más información, consulte [configurar dispositivos Windows para usuarios de Microsoft 365](set-up-windows-devices.md).

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Paso 4: instalar Microsoft 365 apps for Business
- Puede instalar Office automáticamente en los dispositivos Windows mediante el Asistente de [configuración](set-up.md#deploy-office-365-client-apps).
- Permita que los usuarios [instalen aplicaciones de Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows y dispositivos.
     
## <a name="advanced"></a>Avanzadas
- **Usar AutoPilot para configurar nuevos dispositivos**
            
     Puede usar [Windows AutoPilot](add-autopilot-devices-and-profile.md) para preconfigurar automáticamente los **nuevos** dispositivos Windows 10 para un usuario, pero podría ser más fácil obtener un [asociado](https://www.microsoft.com/solution-providers/search) que lo haga por usted. También puede ir a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)y solicitar a un experto en la tecnología de la nube que configure nuevos dispositivos que compre.

- **Acceder a recursos locales**

     - Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business Premium para proteger sus dispositivos con Windows 10, a la vez que mantiene el acceso a los recursos locales que requieren autenticación local. Siga los pasos descritos en [enable Domain-joined Domain-Windows 10 Devices to be Managed Microsoft 365 Business Premium](manage-windows-devices.md) para configurarlo. Este es el método preferido y los dispositivos de este estado se denominan dispositivos híbridos Unidos de Azure AD.

    - Si su empresa tiene Active Directory local que contiene algunos recursos locales (como impresoras y recursos compartidos de archivos), puede dar acceso a estos recursos a los dispositivos de Azure AD siguiendo los pasos que se indican a continuación: [acceso a los recursos locales desde un dispositivo unido a Azure ad en Microsoft 365 Business Premium](access-resources.md).

## <a name="see-also"></a>Vea también

[Vídeos de aprendizaje de Microsoft 365 para empresas](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
