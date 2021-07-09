---
title: Introducción a Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Obtenga información Microsoft 365 para empresas, cómo configurarla y cómo preparar los dispositivos y equipos de los usuarios para asegurarse de que están protegidos por Microsoft 365 para empresas.
ms.openlocfilehash: 2ab0079da7a8f30d481cdb3d3dc6d165b4a19e99
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339298"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Introducción a Microsoft 365 para empresas

## <a name="what-is-microsoft-365-for-business"></a>Qué es Microsoft 365 para empresas

Microsoft 365 para empresas es un conjunto completo de herramientas de colaboración y productividad empresarial, como Outlook, Word, Excel y otros productos Office, que siempre están actualizados. Puedes proteger los archivos de trabajo en todos los dispositivos iOS, Android y Windows 10 con seguridad de nivel empresarial que es fácil de administrar.

## <a name="watch-what-is-microsoft-365-business-premium"></a>Ver: Qué es Microsoft 365 Empresa Premium

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 para empresas está pensada para hasta 300 licencias. Si necesita más licencias, consulte la documentación de [Microsoft 365 Enterprise](../enterprise/index.yml) para obtener más información. 
  
## <a name="get-microsoft-365-for-business"></a>Obtener Microsoft 365 para empresas

- Si tiene un partner, se Microsoft 365 para empresas: Obtenga información Microsoft 365 para empresas [desde el Centro de partners de Microsoft](get-microsoft-365-business.md).
    
- Si no tiene un socio y desea obtener una Microsoft 365 para empresas, puede [comprarla aquí](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Configurar Microsoft 365 para empresas

 **Información general sobre Microsoft 365 configuración de business Suite**
  
En el siguiente diagrama se describe cómo los administradores Microsoft 365 para empresas. También describe los pasos para preparar los equipos Windows para Microsoft 365 para empresas. También puede agregar nuevos dispositivos en el Centro de administración de Microsoft 365 con [Windows AutoPilot](add-autopilot-devices-and-profile.md). Puedes usar AutoPilot para configurar y configurar previamente nuevos dispositivos para que estén listos para un uso productivo tan pronto como un usuario inicia sesión con sus credenciales Microsoft 365 para empresas.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

## <a name="watch-set-up-microsoft-365-business"></a>Ver: Configurar Microsoft 365 Empresa

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../business-video/index.yml).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Configurar Microsoft 365 para empresas (administrador)

Inicie sesión en [Centro de administración de Microsoft 365](https://admin.microsoft.com/adminportal/home) con sus credenciales de administrador global y complete los siguientes pasos para configurar Microsoft 365 para empresas. 
  
1. [Requisitos previos para proteger datos en dispositivos con Microsoft 365 para empresas](pre-requisites-for-data-protection.md)
    
    Lea primero los requisitos previos para asegurarse de que los dispositivos están listos para Microsoft 365 para empresas.
    
2. [Usar el Asistente para la instalación para configurar Microsoft 365 para empresas](set-up.md)
    
    Si se está moviendo permanentemente de un **Active Directory local a** la nube, puede ir a Centro de administración de Microsoft 365 y usar el asistente para la instalación para agregar los usuarios manualmente, o puede realizar una sincronización única con Azure AD Conectar. Hay dos formas de hacerlo: 
    
    - Si también tiene un servidor de Exchange 2010, Exchange 2013 o Exchange 2016, puede usar minimal hybrid para migrar rápidamente buzones de [Exchange](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)Microsoft 365 . Los pasos híbridos mínimos incluyen una sincronización única de usuarios con Azure AD y la migración de correo electrónico desde local a la nube. Una vez completada la migración de correo electrónico, la sincronización de directorios se desactivará automáticamente al usar este método.
    
    - Use el Asistente para sincronización de directorios para sincronizar los usuarios con la nube. Siga los pasos descritos en Configurar la sincronización de [directorios Microsoft 365](../enterprise/set-up-directory-synchronization.md) para completar este proceso. Después de sincronizar los usuarios con la nube, tendrá que desactivar la sincronización de directorios [para Microsoft 365](../enterprise/turn-off-directory-synchronization.md).
    
    También tendrá que dar a cada usuario que se agregó de esta manera una licencia para Microsoft 365 para empresas. Puede hacerlo en el asistente [para la](set-up.md) instalación o puede asignar licencias a [los usuarios.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2: Preparar dispositivos móviles

Siga los pasos descritos en Configurar dispositivos móviles para [Microsoft 365](set-up-mobile-devices.md) para que los usuarios empresariales instalen aplicaciones Office en dispositivos y asegúrese de que están protegidos por Microsoft 365 para empresas. 
  
### <a name="3-prepare-pcs"></a>3: Preparar equipos

Los administradores pueden seleccionar previamente la configuración de los equipos Windows 10 nuevos mediante [Windows AutoPilot](add-autopilot-devices-and-profile.md). Los usuarios pueden configurar sus dispositivos Windows 10 existentes o nuevos siguiendo los pasos de este tema: Configurar equipos Windows para Microsoft 365 usuarios [empresariales.](set-up-windows-devices.md) Para los dispositivos existentes, los usuarios **pueden mover** [archivos opcionalmente a OneDrive para la Empresa](move-files-to-onedrive.md). También pueden usar herramientas de terceros para mover archivos asociados Windows perfil a OneDrive.
  
Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 para empresas para proteger los dispositivos de Windows 10, al mismo tiempo que mantiene el acceso a los recursos locales que requieren autenticación local. Siga los pasos descritos en [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 for business](manage-windows-devices.md) to set this up. Se prefiere este método y los dispositivos en este estado se **denominan dispositivos** unidos a Azure AD híbrido. 
  
Si conserva un Active Directory local que contiene algunos recursos locales (como recursos compartidos de archivos e impresoras), puede proporcionar a los dispositivos unidos a **Azure AD** acceso a estos recursos siguiendo los pasos que se indican a continuación: Obtener acceso a recursos locales desde un dispositivo unido a Azure AD en [Microsoft 365](access-resources.md)para empresas.
  
  
## <a name="contact-support"></a>Ponerse en contacto con soporte técnico

 **Si necesita ponerse en contacto con soporte técnico:**
  
- Póngase en contacto con su partner.
    
- Como administrador Microsoft 365 para empresas, tiene acceso a nuestro equipo de soporte al cliente: Póngase en contacto con el soporte técnico para productos **[empresariales- Ayuda para administradores](../business-video/get-help-support.md)**
    
## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 documentación y recursos para empresas](./index.yml) (página de vínculos)\
[Administrar Microsoft 365 para empresas](manage.md) (artículo)\
[Migrar a Microsoft 365 para empresas](migrate-to-microsoft-365-business.md) (artículo)\
[Vídeos de aprendizaje de Microsoft 365 para empresas](../business-video/index.yml) (página de vínculo)