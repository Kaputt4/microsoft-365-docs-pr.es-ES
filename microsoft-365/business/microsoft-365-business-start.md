---
title: Introducción a Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Obtenga más información sobre Microsoft 365 para empresas, cómo configurarlo y cómo preparar los dispositivos de los usuarios y los equipos para asegurarse de que están protegidos por Microsoft 365 para la empresa.
ms.openlocfilehash: a09b7c676f0e095d2a9db16daa56e19fb7a3baae
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402014"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Introducción a Microsoft 365 para empresas

## <a name="what-is-microsoft-365-for-business"></a>¿Qué es Microsoft 365 para empresas?

Microsoft 365 para empresas es un conjunto completo de herramientas de productividad y colaboración empresarial, como Outlook, Word, Excel y otros productos de Office, que siempre están actualizadas. Puede proteger sus archivos de trabajo en todos los dispositivos iOS, Android y Windows 10 con seguridad de nivel empresarial que sea fácil de administrar.

Vea este vídeo para obtener una introducción rápida a Microsoft 365 para empresas.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 para empresas está destinado a un máximo de 300 licencias. Si necesita más licencias, consulte la documentación de [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) para obtener más información. 
  
## <a name="get-microsoft-365-for-business"></a>Obtener Microsoft 365 para empresas

- Si tiene un partner, recibirá Microsoft 365 para empresas: [consiga microsoft 365 para empresas desde el centro de Partners de Microsoft](get-microsoft-365-business.md).
    
- Si no tiene un partner y quiere obtener Microsoft 365 for Business, puede [comprarlo aquí](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Configurar Microsoft 365 para empresas

 **Información general sobre la configuración de Microsoft 365 para Business Suite**
  
El siguiente diagrama describe cómo los administradores configuran Microsoft 365 para empresas. También se describen los pasos necesarios para preparar los equipos con Windows para Microsoft 365 para la empresa. También puede agregar nuevos dispositivos en el centro de administración de Microsoft 365 con [Windows AutoPilot](add-autopilot-devices-and-profile.md). Puede usar AutoPilot para configurar y preconfigurar nuevos dispositivos para que estén listos para un uso productivo en cuanto un usuario inicie sesión con sus credenciales de Microsoft 365 para empresas.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Vea este vídeo para obtener información general sobre la configuración de Microsoft 365 para empresas.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: configurar Microsoft 365 para empresas (Administrador)

Inicie sesión en el [centro de administración de microsoft 365](https://portal.office.com/adminportal/home) con sus credenciales de administrador global y complete los siguientes pasos para configurar Microsoft 365 para empresas. 
  
1. [Requisitos previos para proteger datos en dispositivos con Microsoft 365 para empresas](pre-requisites-for-data-protection.md)
    
    Lea primero los requisitos previos para asegurarse de que sus dispositivos están listos para Microsoft 365 para empresas.
    
2. [Usar el Asistente para la instalación para configurar Microsoft 365 para empresas](set-up.md)
    
    Si va a **cambiar de forma permanente de un Active Directory local a la nube**, puede ir al centro de administración de Microsoft 365 y usar el Asistente de configuración para agregar los usuarios de forma manual o puede realizar una sincronización única con Azure ad Connect. Puede realizar esto de dos maneras: 
    
    - Si también tiene un servidor de Exchange 2010, Exchange 2013 o Exchange 2016, puede usar la [mínima implementación híbrida para migrar rápidamente buzones de Exchange a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate). Los pasos mínimos híbridos incluyen una sincronización de usuarios de una sola vez a Azure AD y la migración de correo electrónico de local a la nube. Una vez completada la migración de correo electrónico, la sincronización de directorios se desactiva automáticamente cuando se usa este método.
    
    - Use el Asistente para sincronización de directorios para sincronizar los usuarios con la nube. Siga los pasos descritos en [configurar la sincronización de directorios para Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) para completar este proceso. Después de sincronizar los usuarios con la nube, tendrá que [desactivar la sincronización de directorios para Office 365](https://docs.microsoft.com/office365/enterprise/turn-off-directory-synchronization).
    
    También tendrá que dar a cada usuario que se agregó de este modo una licencia a Microsoft 365 para empresas. Puede hacerlo en el Asistente de [configuración](set-up.md) o puede [asignar licencias a usuarios en Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users).
    
### <a name="2-prepare-mobile-devices"></a>2: preparar dispositivos móviles

Siga los pasos descritos en [set up Mobile devices for Microsoft 365 for Business users](set-up-mobile-devices.md) to Install Office apps on Devices y asegúrese de que estén protegidos por Microsoft 365 para empresas. 
  
### <a name="3-prepare-pcs"></a>3: preparar los equipos

Los administradores pueden seleccionar previamente la configuración de los nuevos equipos con Windows 10 con [Windows AutoPilot](add-autopilot-devices-and-profile.md). Los usuarios pueden configurar sus dispositivos Windows 10 nuevos o existentes siguiendo los pasos descritos en este tema: [set up Windows PCS for Microsoft 365 for Business users](set-up-windows-devices.md). Para los dispositivos existentes, los usuarios pueden [mover archivos a OneDrive para la empresa de](move-files-to-onedrive.md) **forma opcional** . También pueden usar herramientas de terceros para mover archivos asociados con el perfil de Windows a OneDrive.
  
Si su organización usa Active Directory de Windows Server local, puede configurar Microsoft 365 para la empresa para que proteja los dispositivos con Windows 10, a la vez que mantiene el acceso a los recursos locales que requieren autenticación local. Siga los pasos descritos en [enable Domain-joined Domain-Windows 10 Devices to be Managed Microsoft 365 for Business](manage-windows-devices.md) para configurar esto. Se prefiere este método y los dispositivos de este estado se denominan **dispositivos híbridos Unidos de Azure ad**. 
  
Si conserva un Active Directory local que contiene algunos recursos locales (como impresoras y recursos compartidos de archivos), puede conceder a los **dispositivos Unidos a Azure ad** acceso a estos recursos siguiendo los pasos que se indican a continuación: [acceso a recursos locales desde un dispositivo unido a Azure ad en Microsoft 365 para empresas](access-resources.md).
  
  
## <a name="contact-support"></a>Contactar soporte

 **Si necesita ponerse en contacto con soporte técnico:**
  
- Póngase en contacto con su partner.
    
- Como administrador de Microsoft 365 para empresas, tiene acceso a nuestro equipo de soporte técnico al cliente: ** [contactar con el soporte técnico para productos empresariales: ayuda para administradores](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)**
    
## <a name="see-also"></a>Consulte también

[Documentación y recursos de Microsoft 365 para la empresa](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Administración de microsoft 365 para empresas](manage.md)[migrar a Microsoft 365 para empresas](migrate-to-microsoft-365-business.md)

[Vídeos de aprendizaje de Microsoft 365 para empresas](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
