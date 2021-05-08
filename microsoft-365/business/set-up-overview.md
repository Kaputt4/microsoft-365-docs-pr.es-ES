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
description: Obtenga información sobre los pasos de configuración Microsoft 365 Empresa Premium, desde suscribirse, agregar un dominio y usuarios, hasta configurar directivas de seguridad y mucho más.
ms.openlocfilehash: 008a5c51698589667acc0d01649f67dab33b4c58
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245072"
---
# <a name="overview-of-setup"></a>Información general sobre la configuración

Vea un breve vídeo sobre Microsoft 365 Empresa Premium instalación.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Si este vídeo le ha sido de ayuda, vea la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../business-video/index.yml).

La mayoría de los pasos de configuración se pueden realizar en la configuración guiada, pero también se enumeran las otras opciones.

## <a name="step-1-add-your-domain-and-users"></a>Paso 1: Agregar el dominio y los usuarios

   - **[Agregue el dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (si compró el dominio [durante](sign-up.md)el registro, este paso ya está listo).

   - **Agregar usuarios**. Puede agregar usuarios de cualquiera de las tres maneras siguientes:
        - En la [configuración guiada](set-up.md#add-users-in-the-wizard).
        - Use la sincronización de [directorios para agregar usuarios mediante Azure AD Conectar](../enterprise/set-up-directory-synchronization.md) si tiene un Active Directory local.
        - También puede agregar [usuarios más adelante](../admin/add-users/add-users.md) en el Centro de administración.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Paso 2: Configurar directivas de seguridad y configurar dispositivos 

  - Usa la [configuración guiada para](set-up.md#protect-your-organization) configurar directivas de dispositivo. 
  - También puede agregar más o editarlos más adelante en el Centro de [administración](view-policies-and-devices.md) y en el [portal de Intune.](/intune/tutorial-walkthrough-intune-portal)
  - El asistente para la configuración también configurará la configuración básica de protección contra amenazas y prevención de pérdida de datos.
  
  Además de la configuración de seguridad en el asistente para la configuración, puede aumentar la seguridad agregando la siguiente configuración:

- **Protección contra malware de correo electrónico**
- **Anti-phishing in Defender for Office 365**
- **Archivado de Exchange Online**
- **Azure Information Protection (Plan1)**

Para empezar, vea [Aumentar la protección contra amenazas](increase-threat-protection.md) y configurar las características de [cumplimiento](set-up-compliance.md).

Vea también [las 10 principales](/office365/admin/security-and-compliance/secure-your-business-data) formas de proteger su Microsoft 365 Empresa Premium para obtener una hoja de ruta de los procedimientos de seguridad recomendados.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Paso 3: Configurar y administrar Windows 10 dispositivos

Después de completar la configuración guiada, querrá proteger todos los Windows 10 de la organización.
  
- Windows 10 Pro es un [](pre-requisites-for-data-protection.md) requisito previo para Microsoft 365 Empresa Premium, pero si tiene Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, su suscripción le da derecho a una actualización a [Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).
- Siga los pasos de [secure Windows 10 pc para](secure-win-10-pcs.md) configurar directivas para Windows 10 dispositivos.

Al unir un dispositivo Windows 10 a Azure AD, las directivas que establezca para Windows 10 equipos se aplicarán a él. Para obtener más información, vea [Configurar Windows dispositivos para Microsoft 365 usuarios.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Paso 4: Instalar Aplicaciones Microsoft 365 para negocios
- Puede instalar automáticamente Office en los dispositivos Windows mediante el asistente [de instalación](set-up.md#deploy-office-365-client-apps).
- Permitir a [los usuarios instalar Office aplicaciones para](/office365/admin/setup/install-applications) Windows y dispositivos.
     
## <a name="advanced"></a>Opciones avanzadas
- **Usar Autopilot para configurar nuevos dispositivos**
            
     Puedes usar [Windows Autopilot](add-autopilot-devices-and-profile.md) para configurar automáticamente nuevos dispositivos **Windows 10** para un usuario, pero puede ser más fácil obtener [un](https://www.microsoft.com/solution-providers/search) partner que pueda hacerlo por ti. También puedes ir a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)y pedir a un experto en tecnología en la nube que configure los nuevos dispositivos que compres.

- **Acceder a recursos locales**

     - Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Empresa Premium para proteger los dispositivos Windows 10 y mantener el acceso a los recursos locales que requieren autenticación local. Siga los pasos de [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Empresa Premium](manage-windows-devices.md) to set this up. Este es el método preferido y los dispositivos en este estado se denominan dispositivos unidos a Azure AD híbrido.

    - Si su empresa tiene un Active Directory local que contiene algunos recursos locales (como recursos compartidos de archivos e impresoras), puede proporcionar a los dispositivos unidos a Azure AD acceso a estos recursos siguiendo los pasos que se indican a continuación: Obtener acceso a recursos locales desde un dispositivo unido a [Azure AD](access-resources.md)en Microsoft 365 Empresa Premium .

## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 vídeos de aprendizaje para empresas](../business-video/index.yml) (página de vínculos)