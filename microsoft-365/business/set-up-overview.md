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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Obtenga información sobre los pasos de configuración de Microsoft 365 Empresa Premium, desde suscribirse, agregar un dominio y usuarios, hasta configurar directivas de seguridad y mucho más.
ms.openlocfilehash: 46370166a9d5e8c9308b8947513e631c159f0b86
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842138"
---
# <a name="overview-of-setup"></a>Información general sobre la configuración

Vea un breve vídeo sobre la configuración de Microsoft 365 Empresa Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

La mayoría de los pasos de configuración se pueden realizar en la configuración guiada, pero también se enumeran las otras opciones.

## <a name="step-1-add-your-domain-and-users"></a>Paso 1: Agregar el dominio y los usuarios

   - **[Agregue su dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (si compró el dominio durante el [registro,](sign-up.md)este paso ya está listo).

   - **Agregar usuarios.** Puede agregar usuarios de cualquiera de las tres maneras siguientes:
        - En la [configuración guiada.](set-up.md#add-users-in-the-wizard)
        - Use la sincronización de [directorios para agregar usuarios mediante Azure AD Connect](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) si tiene un Active Directory local.
        - También puede agregar [usuarios más adelante en](add-users-m365b.md) el centro de administración.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Paso 2: Configurar directivas de seguridad y configurar dispositivos 

  - Usa la [configuración guiada para](set-up.md#protect-your-organization) configurar directivas de dispositivo. 
  - También puede agregar más o editarlos más adelante en el centro [de administración](view-policies-and-devices.md) y en el [portal de Intune.](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)
  - El asistente de configuración también configurará la protección contra amenazas básica y la configuración de prevención de pérdida de datos.
  
  Además de la configuración de seguridad del asistente para la configuración, puede aumentar la seguridad agregando la siguiente configuración:

- **Protección contra malware de correo electrónico**
- **Protección contra la suplantación de identidad en Defender para Office 365**
- **Archivado de Exchange Online**
- **Azure Information Protection (Plan1)**

Para empezar, vea aumentar [la protección contra amenazas](increase-threat-protection.md) y configurar las características de [cumplimiento.](set-up-compliance.md)

Vea también las 10 mejores formas de proteger [Microsoft 365 Empresa Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para obtener un mapa de ruta de los procedimientos de seguridad recomendados.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Paso 3: Configurar y administrar dispositivos Windows 10

Después de completar la configuración guiada, querrás proteger todos los equipos con Windows 10 de la organización.
  
- Windows 10 Pro es un requisito previo para Microsoft 365 Empresa Premium, pero si tienes Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, tu suscripción te da derecho [a](pre-requisites-for-data-protection.md) una actualización a [Windows 10 Pro.](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)
- Sigue los pasos de [los equipos windows 10](secure-win-10-pcs.md) seguros para configurar directivas para dispositivos Windows 10.

Al unir un dispositivo Windows 10 a Azure AD, se le aplican las directivas establecidas para equipos con Windows 10. Para obtener más información, vea [Configurar dispositivos Windows para usuarios de Microsoft 365.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Paso 4: Instalar Aplicaciones de Microsoft 365 para empresas
- Puede instalar Automáticamente Office en los dispositivos Windows mediante el asistente [para instalación.](set-up.md#deploy-office-365-client-apps)
- Permitir que los [usuarios instalen aplicaciones de Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows y dispositivos.
     
## <a name="advanced"></a>Opciones avanzadas
- **Usar Autopilot para configurar nuevos dispositivos**
            
     Puedes usar [Windows Autopilot](add-autopilot-devices-and-profile.md) para configurar automáticamente los nuevos dispositivos **Windows** 10 para un usuario, pero puede ser más fácil obtener [un](https://www.microsoft.com/solution-providers/search) partner que pueda hacerlo por ti. También puedes ir a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)y pedir a un experto en tecnología en la nube que configure los nuevos dispositivos que compres.

- **Acceder a recursos locales**

     - Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Empresa Premium para proteger sus dispositivos Windows 10, a la vez que mantiene el acceso a los recursos locales que requieren autenticación local. Siga los pasos descritos en Habilitar dispositivos Windows 10 unidos a un dominio para que [Microsoft 365 Empresa Premium](manage-windows-devices.md) lo pueda administrar para configurarlo. Este es el método preferido y los dispositivos en este estado se denominan dispositivos unidos a Azure AD híbrido.

    - Si su empresa tiene un Active Directory local que contiene algunos recursos locales (como archivos compartidos e impresoras), puede dar a los dispositivos unidos a Azure AD acceso a estos recursos siguiendo estos pasos: Obtenga acceso a los recursos locales desde un dispositivo unido a Azure AD en [Microsoft 365 Empresa Premium.](access-resources.md)

## <a name="see-also"></a>Vea también

[Vídeos de aprendizaje de Microsoft 365 para empresas](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
