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
description: Obtenga información sobre Microsoft 365 para empresas, cómo configurarlo y cómo preparar los dispositivos y equipos de los usuarios para asegurarse de que están protegidos por Microsoft 365 para empresas.
ms.openlocfilehash: 9430dc7aa637be3fdb833150b83e96caacc82170
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912970"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Introducción a Microsoft 365 para empresas

## <a name="what-is-microsoft-365-for-business"></a>Qué es Microsoft 365 para empresas

Microsoft 365 para empresas es un conjunto completo de herramientas de colaboración y productividad empresarial, como Outlook, Word, Excel y otros productos de Office, que siempre están actualizados. Puedes proteger los archivos de trabajo en todos los dispositivos iOS, Android y Windows 10 con seguridad de nivel empresarial que sea fácil de administrar.

Vea este vídeo para obtener una introducción rápida a Microsoft 365 para empresas.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 para empresas está diseñado para hasta 300 licencias. Si necesita más licencias, consulte la documentación de [Microsoft 365 Enterprise](../enterprise/index.yml) para obtener más información. 
  
## <a name="get-microsoft-365-for-business"></a>Obtener Microsoft 365 para empresas

- Si tiene un partner, tendrá Microsoft 365 para empresas: Obtenga [Microsoft 365](get-microsoft-365-business.md)para empresas desde el Centro de partners de Microsoft .
    
- Si no tiene un socio y desea obtener Microsoft 365 para empresas, puede [comprarlo aquí](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Configurar Microsoft 365 para empresas

 **Información general sobre la configuración de Microsoft 365 para business Suite**
  
En el siguiente diagrama se describe cómo los administradores establecen Microsoft 365 para empresas. También describe los pasos para preparar equipos Windows para Microsoft 365 para empresas. También puedes agregar nuevos dispositivos en el Centro de administración de Microsoft 365 con [Windows AutoPilot](add-autopilot-devices-and-profile.md). Puedes usar AutoPilot para configurar y configurar previamente nuevos dispositivos para que estén listos para un uso productivo tan pronto como un usuario inicia sesión con sus credenciales de Microsoft 365 para empresas.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Vea este vídeo para obtener información general sobre la configuración de Microsoft 365 para empresas.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Si este vídeo le ha sido de ayuda, vea la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Configurar Microsoft 365 para empresas (administrador)

Inicie sesión en el Centro de [administración de Microsoft 365](https://portal.office.com/adminportal/home) con sus credenciales de administrador global y siga estos pasos para configurar Microsoft 365 para empresas. 
  
1. [Requisitos previos para proteger datos en dispositivos con Microsoft 365 para empresas](pre-requisites-for-data-protection.md)
    
    Lea primero los requisitos previos para asegurarse de que los dispositivos están listos para Microsoft 365 para empresas.
    
2. [Usar el Asistente para configuración para configurar Microsoft 365 para empresas](set-up.md)
    
    Si se está moviendo permanentemente de un **Active Directory local a** la nube, puede ir al Centro de administración de Microsoft 365 y usar el Asistente para la instalación para agregar los usuarios manualmente, o bien puede realizar una sincronización única con Azure AD Connect. Puede realizar esto de dos maneras: 
    
    - Si también tiene un servidor de Exchange 2010, Exchange 2013 o Exchange 2016, puede usar un entorno híbrido mínimo para migrar rápidamente buzones de Exchange a [Microsoft 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate). Los pasos híbridos mínimos incluyen una sincronización única de usuarios con Azure AD y la migración de correo electrónico desde local a la nube. Una vez completada la migración de correo electrónico, la sincronización de directorios se desactivará automáticamente al usar este método.
    
    - Use el Asistente para sincronización de directorios para sincronizar los usuarios con la nube. Siga los pasos descritos [en Configurar la sincronización de directorios para Microsoft 365](../enterprise/set-up-directory-synchronization.md) para completar este proceso. Después de sincronizar los usuarios con la nube, tendrá que desactivar la sincronización de [directorios para Microsoft 365](../enterprise/turn-off-directory-synchronization.md).
    
    También tendrás que dar una licencia a cada usuario que se agregó de esta manera a Microsoft 365 para empresas. Puede hacerlo en el asistente [para la](set-up.md) instalación o puede asignar licencias a [los usuarios.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2: Preparar dispositivos móviles

Siga los pasos descritos en Configurar dispositivos móviles para usuarios de [Microsoft 365](set-up-mobile-devices.md) para empresas para instalar aplicaciones de Office en dispositivos y asegurarse de que están protegidos por Microsoft 365 para empresas. 
  
### <a name="3-prepare-pcs"></a>3: Preparar equipos

Los administradores pueden seleccionar previamente la configuración de los nuevos equipos con Windows 10 mediante [Windows AutoPilot](add-autopilot-devices-and-profile.md). Los usuarios pueden configurar sus dispositivos Windows 10 existentes o nuevos siguiendo los pasos descritos en este tema: Configurar equipos windows para usuarios de [Microsoft 365](set-up-windows-devices.md)para empresas. Para los dispositivos existentes, los usuarios **pueden mover** [archivos opcionalmente a OneDrive para la Empresa](move-files-to-onedrive.md). También pueden usar herramientas de terceros para mover archivos asociados con el perfil de Windows a OneDrive.
  
Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 para empresas para proteger sus dispositivos Windows 10, mientras mantiene el acceso a los recursos locales que requieren autenticación local. Sigue los pasos de Habilitar dispositivos Windows 10 unidos a un dominio para que [Microsoft 365](manage-windows-devices.md) para empresas puedan administrarlo para configurarlo. Se prefiere este método y los dispositivos en este estado se **denominan dispositivos** unidos a Azure AD híbrido. 
  
Si conserva un Active Directory local que contiene algunos recursos locales (como archivos compartidos e impresoras), puede proporcionar a los dispositivos unidos a **Azure AD** acceso a estos recursos siguiendo los pasos que se indican a continuación: Obtener acceso a recursos locales desde un dispositivo unido a Azure AD en [Microsoft 365](access-resources.md)para empresas.
  
  
## <a name="contact-support"></a>Ponerse en contacto con el soporte técnico

 **Si necesita ponerse en contacto con soporte técnico:**
  
- Póngase en contacto con su partner.
    
- Como administrador de Microsoft 365 para empresas, tiene acceso a nuestro equipo de soporte al cliente: Póngase en contacto con el soporte técnico para productos **[empresariales - Ayuda para administradores](../admin/contact-support-for-business-products.md)**
    
## <a name="see-also"></a>Vea también

[Documentación y recursos de Microsoft 365 para empresas](./index.yml)
  
[Administrar Microsoft 365 para empresas](manage.md)[Migrar a Microsoft 365 para empresas](migrate-to-microsoft-365-business.md)

[Vídeos de aprendizaje de Microsoft 365 para empresas](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)