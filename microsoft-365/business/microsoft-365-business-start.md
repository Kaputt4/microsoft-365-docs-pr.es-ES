---
title: Introducción a Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Aprenda a configurar Microsoft 365 empresarial.
ms.openlocfilehash: 1c4adc64f62f7d4ae5038603804aa10e48d8a6e1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871801"
---
# <a name="get-started-with-microsoft-365-business"></a>Introducción a Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Qué es Microsoft 365 Business

Microsoft 365 Business es un conjunto completo de herramientas de productividad y colaboración empresarial, como Outlook, Word, Excel y otros productos de Office que siempre están actualizados. Puede proteger sus archivos de trabajo en todos los dispositivos iOS, Android y Windows 10 con seguridad de nivel empresarial que es fácil de administrar.
  
Microsoft 365 empresarial está pensada para licencias hasta 300, si necesita más licencias, consulte la documentación de [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) para obtener más información. 
  
## <a name="get-microsoft-365-business"></a>Obtener Microsoft 365 Empresa

- Si tiene un partner, obtendrá Microsoft 365 Business: [Obtener Microsoft 365 Business desde el Centro de partners de Microsoft](get-microsoft-365-business.md).
    
- Si no tiene un socio y desea obtener Microsoft 365 empresarial, puede [comprar aquí](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Configurar Microsoft 365 Business

 **Información general de Microsoft 365 Business Suite configuración**
  
En el siguiente diagrama se describe cómo los administradores configuración Microsoft 365 empresarial. También describe los pasos para preparar los equipos con Windows para la empresa de Microsoft 365. También puede agregar nuevos dispositivos en el centro de administración de Microsoft 365 empresarial con el [Piloto automático de Windows](add-autopilot-devices-and-profile.md). Puede usar el piloto automático para instalar y configurar previamente nuevos dispositivos, introducción listo para su uso productivo tan pronto como un usuario inicia sesión con sus credenciales de Microsoft 365 empresarial.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: configurar Microsoft 365 Business (Admin)

Inicie sesión en el [centro de administración de Microsoft 365 Business](https://portal.office.com/adminportal/home) con las credenciales de administrador global y siga los pasos que hay a continuación para configurar Microsoft 365 Business. 
  
1. [Requisitos previos para proteger datos en dispositivos con Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    En primer lugar, lea los requisitos previos para asegurarse de que sus dispositivos están listos para Microsoft 365 Business.
    
2. [Configurar Microsoft 365 Business mediante el Asistente para configuración](set-up.md)
    
    Si se encuentra **permanentemente mover de un Active Directory local a la nube**, puede agregar los usuarios manualmente en el centro de administración de Microsoft 365 empresarial mediante el Asistente para la instalación, o puede hacer una sincronización única con Azure Connect de AD. Hay dos formas de hacer esto: 
    
  - Si también tiene un Exchange 2010, Exchange 2013 o 2016 de Exchange server, puede [Usar híbrida mínima para migrar rápidamente los buzones de Exchange a Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). Los pasos híbrida mínima incluyen una única sincronización de usuarios para Azure AD así como migración desde local a la nube de correo electrónico. Una vez completada la migración de correo electrónico, la sincronización de directorios se desactiva automáticamente cuando se usa este método.
    
  - Use el Asistente para sincronización de directorios de Office 365 para sincronizar los usuarios con la nube. Siga los pasos de [Configurar la sincronización de directorios en Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) para completar este proceso. Después de sincronizar los usuarios con la nube, tendrá que [Desactivar la sincronización de directorios](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    También deberá dar a cada usuario que se ha agregado esta forma una licencia para Microsoft Business de 365. Esto se puede hacer en el [Asistente para la instalación](set-up.md)o en la [asignación de licencias a los usuarios de Office 365 para la empresa](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: preparación de dispositivos móviles

Siga los pasos de[Configurar dispositivos móviles para los usuarios empresariales de 365 de Microsoft](set-up-mobile-devices.md) para instalar aplicaciones de Office en los dispositivos y asegurándose de que estén protegidas por Microsoft 365 empresarial. 
  
### <a name="3-prepare-pcs"></a>3: preparar equipos

Los administradores pueden seleccionar previa a la configuración para los nuevos dispositivos Windows 10 PCs mediante el uso de [Piloto automático de Windows](add-autopilot-devices-and-profile.md). Los usuarios pueden configurar sus dispositivos de Windows 10 nuevos o existentes siguiendo los pasos descritos en este tema: [configurar los equipos con Windows para los usuarios de Microsoft Business de 365](set-up-windows-devices.md). Dispositivos existentes de los usuarios también pueden **, opcionalmente,**[mueva los archivos a OneDrive para la empresa](move-files-to-onedrive.md). También pueden usar herramientas de terceros para mover los archivos asociados con el perfil de Windows OneDrive.
  
Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 empresarial para proteger los dispositivos de Windows 10, al tiempo que mantiene el acceso a los recursos locales que requieren autenticación local. Siga los pasos descritos en [Habilitar unido a un dominio de Windows 10 dispositivos sea administrado por Microsoft 365 Business](manage-windows-devices.md) para realizar esta configuración. Este es el método preferido y dispositivos en este estado se denominan **híbrida Azure AD se unió a dispositivos**. 
  
Si conservar un local de Active Directory que contiene algunos recursos (por ejemplo, recursos compartidos de archivos e impresoras) local, puede otorgar el acceso de **dispositivos Azure unido a AD** a estos recursos siguiendo los pasos descritos aquí: [acceso local recursos desde un Dispositivo Azure unido a AD en Microsoft 365 Business](access-resources.md).
  
Una vez haya configurado Windows 10 PCs, puede [instalar automáticamente Office](auto-install-or-uninstall-office.md) en los dispositivos. 
  
## <a name="contact-support"></a>Contactar soporte

 **Si necesita ponerse en contacto con soporte técnico:**
  
- Póngase en contacto con su partner.
    
- Como un administrador de Microsoft 365 empresarial, tiene acceso a nuestro equipo de soporte al cliente, ** [en soporte técnico para productos de negocio: Ayuda de administración](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Temas relacionados
[Documentación y recursos de Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Administrar Microsoft 365 Business](manage.md) [Migrar a Microsoft 365 Business](migrate-to-microsoft-365-business.md)
  

