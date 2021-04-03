---
title: Información general sobre la configuración
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Obtenga información sobre los pasos de configuración para Microsoft 365 Empresa Premium, desde suscribirse, agregar un dominio y usuarios, hasta configurar directivas de seguridad, etc.
ms.openlocfilehash: 749acbfdbde92ad97b09dc720c85dd850b76c9cf
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579942"
---
# <a name="overview-of-setup"></a>Información general sobre la configuración

Vea un breve vídeo sobre la configuración de Microsoft 365 Empresa Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Si este vídeo le ha sido de ayuda, vea la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

La mayoría de los pasos de configuración se pueden realizar en la configuración guiada, pero también se enumeran las otras opciones.

## <a name="step-1-add-your-domain-and-users"></a>Paso 1: Agregar el dominio y los usuarios

   - **[Agregue el dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (si compró el dominio [durante](sign-up.md)el registro, este paso ya está listo).

   - **Agregar usuarios**. Puede agregar usuarios de cualquiera de las tres maneras siguientes:
        - En la [configuración guiada](set-up.md#add-users-in-the-wizard).
        - Use la sincronización de [directorios para agregar usuarios mediante Azure AD Connect](../enterprise/set-up-directory-synchronization.md) si tiene un Active Directory local.
        - También puede agregar [usuarios más adelante](../admin/add-users/add-users.md) en el Centro de administración.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Paso 2: Configurar directivas de seguridad y configurar dispositivos 

  - Usa la [configuración guiada para](set-up.md#protect-your-organization) configurar directivas de dispositivo. 
  - También puede agregar más o editarlos más adelante en el Centro de [administración](view-policies-and-devices.md) y en el [portal de Intune.](/intune/tutorial-walkthrough-intune-portal)
  - El asistente para la configuración también configurará la configuración básica de protección contra amenazas y prevención de pérdida de datos.
  
  Además de la configuración de seguridad en el asistente para la configuración, puede aumentar la seguridad agregando la siguiente configuración:

- **Protección contra malware de correo electrónico**
- **Anti phishing en Defender para Office 365**
- **Archivado de Exchange Online**
- **Azure Information Protection (Plan1)**

Para empezar, vea [Aumentar la protección contra amenazas](increase-threat-protection.md) y configurar las características de [cumplimiento](set-up-compliance.md).

Vea también las 10 principales formas de proteger [Su Microsoft 365 Empresa Premium](/office365/admin/security-and-compliance/secure-your-business-data) para obtener una hoja de ruta de los procedimientos de seguridad recomendados.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Paso 3: Configurar y administrar dispositivos Windows 10

Después de completar la configuración guiada, querrás proteger todos los equipos con Windows 10 de tu organización.
  
- Windows 10 Pro es un requisito previo para Microsoft 365 Empresa Premium, pero si tienes Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, la suscripción te da derecho [a](pre-requisites-for-data-protection.md) una actualización a [Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).
- Sigue los pasos descritos en [Equipos seguros de Windows 10](secure-win-10-pcs.md) para configurar directivas para dispositivos Windows 10.

Cuando unes un dispositivo Windows 10 a Azure AD, se aplican las directivas que estableces para equipos con Windows 10. Para obtener más información, consulta [Configurar dispositivos Windows para usuarios de Microsoft 365.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Paso 4: Instalar aplicaciones de Microsoft 365 para empresas
- Puede instalar Office automáticamente en los dispositivos Windows mediante el asistente [para la instalación.](set-up.md#deploy-office-365-client-apps)
- Permitir a [los usuarios instalar aplicaciones de Office](/office365/admin/setup/install-applications) para Windows y dispositivos.
     
## <a name="advanced"></a>Opciones avanzadas
- **Usar Autopilot para configurar nuevos dispositivos**
            
     Puedes usar [Windows Autopilot](add-autopilot-devices-and-profile.md) para configurar automáticamente los nuevos dispositivos **Windows** 10 para un usuario, pero puede ser más fácil obtener [un](https://www.microsoft.com/solution-providers/search) partner que pueda hacerlo por ti. También puedes ir a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)y pedir a un experto en tecnología en la nube que configure los nuevos dispositivos que compres.

- **Acceder a recursos locales**

     - Si tu organización usa Windows Server Active Directory local, puedes configurar Microsoft 365 Empresa Premium para proteger tus dispositivos Windows 10, mientras mantienes el acceso a los recursos locales que requieren autenticación local. Sigue los pasos de [Habilitar dispositivos Windows 10](manage-windows-devices.md) unidos a un dominio para que Microsoft 365 Empresa Premium lo pueda administrar para configurarlo. Este es el método preferido y los dispositivos en este estado se denominan dispositivos unidos a Azure AD híbrido.

    - Si su empresa tiene un Active Directory local que contiene algunos recursos locales (como recursos compartidos de archivos e impresoras), puede proporcionar a los dispositivos unidos a Azure AD acceso a estos recursos siguiendo los pasos que se indican a continuación: Obtener acceso a recursos locales desde un dispositivo unido a Azure AD en [Microsoft 365 Empresa Premium.](access-resources.md)

## <a name="see-also"></a>Vea también

[Vídeos de aprendizaje de Microsoft 365 para empresas](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)