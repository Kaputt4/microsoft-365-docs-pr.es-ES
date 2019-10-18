---
title: Introducción a Microsoft 365 Business
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Aprenda a configurar Microsoft 365 Business.
ms.openlocfilehash: ed302a79d125ffc9c6203d902f437749a5b0f8d4
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575906"
---
# <a name="get-started-with-microsoft-365-business"></a>Introducción a Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Qué es Microsoft 365 empresa

Microsoft 365 Business es un conjunto completo de herramientas de productividad y colaboración empresarial, como Outlook, Word, Excel y otros productos de Office que siempre están actualizados. Puede proteger sus archivos de trabajo en todos los dispositivos iOS, Android y Windows 10 con seguridad de nivel empresarial que es fácil de administrar.
  
Microsoft 365 empresa está destinada a un máximo de 300 licencias, si necesita más licencias, consulte la documentación de [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) para obtener más información. 
  
## <a name="get-microsoft-365-business"></a>Obtener Microsoft 365 Empresa

- Si tiene un partner, obtendrá Microsoft 365 Business: [Obtener Microsoft 365 Business desde el Centro de partners de Microsoft](get-microsoft-365-business.md).
    
- Si no tiene un partner y quiere obtener Microsoft 365 Business, puede [comprarlo aquí](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Configurar Microsoft 365 Empresa

 **Información general sobre la configuración de Microsoft 365 Business Suite**
  
El siguiente diagrama describe cómo los administradores configuran Microsoft 365 Business. También se describen los pasos para preparar equipos PC con Windows para Microsoft 365 Business. También puede agregar nuevos dispositivos desde el Centro de administración de Microsoft 365 Business con [Windows AutoPilot](add-autopilot-devices-and-profile.md). Puede usar AutoPilot para preparar y preconfigurar nuevos dispositivos para que estén listos para uso en producción en cuanto un usuario inicie sesión con sus credenciales de Microsoft 365 Business.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: configurar Microsoft 365 Business (Administrador)

Inicie sesión en el [centro de administración de Microsoft 365 Business](https://portal.office.com/adminportal/home) con las credenciales de administrador global y siga los pasos que hay a continuación para configurar Microsoft 365 Business. 
  
1. [Requisitos previos para proteger datos en dispositivos con Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    En primer lugar, lea los requisitos previos para asegurarse de que sus dispositivos están listos para Microsoft 365 Business.
    
2. [Configurar Microsoft 365 Business mediante el Asistente para configuración](set-up.md)
    
    Si va **a cambiar de forma permanente de un Active Directory local a la nube**, puede Agregar los usuarios manualmente en el centro de administración de negocios de Microsoft 365 mediante el Asistente para instalación, o bien puede realizar una sincronización única con Azure ad Connect. Puede realizar esto de dos maneras: 
    
  - Si también tiene un servidor de Exchange 2010, Exchange 2013 o Exchange 2016, puede usar la [mínima implementación híbrida para migrar rápidamente buzones de Exchange a Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). Los pasos de la opción híbrida mínima incluyen una única sincronización de usuarios a Azure AD, así como la migración del correo electrónico desde la implementación local a la nube. Una vez completada la migración de correo electrónico, la sincronización de directorios se desactiva automáticamente al usar este método.
    
  - Use el Asistente para sincronización de directorios de Office 365 para sincronizar los usuarios con la nube. Siga los pasos de [Configurar la sincronización de directorios en Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) para completar este proceso. Después de sincronizar los usuarios con la nube, tendrá que [Desactivar la sincronización de directorios](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    También tendrá que asignar una licencia de Microsoft 365 Empresa a cada usuario que se agregó de esta forma. Puede hacerlo en el Asistente de [configuración](set-up.md)o en [asignar licencias a usuarios en Office 365 para empresas](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: preparar dispositivos móviles

Siga los pasos descritos en[Configure Mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) to Install Office apps on Devices y asegúrese de que estén protegidos por Microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: preparar los equipos

Los administradores pueden seleccionar previamente la configuración de los nuevos dispositivos con Windows 10 PCs mediante [Windows AutoPilot](add-autopilot-devices-and-profile.md). Los usuarios pueden configurar sus dispositivos Windows 10 existentes o nuevos siguiendo los pasos de este tema: [set up Windows PC for Microsoft 365 Business users](set-up-windows-devices.md). Para los dispositivos existentes **,** los usuarios también pueden[mover archivos a OneDrive para la empresa](move-files-to-onedrive.md). También pueden usar herramientas de terceros para mover archivos asociados con el perfil de Windows a OneDrive.
  
Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business para proteger sus dispositivos con Windows 10 y mantener al mismo tiempo el acceso a los recursos locales que requieren autenticación local. Siga los pasos descritos en [enable Domain-joined Domain-Windows 10 Devices to be Managed Microsoft 365 Business](manage-windows-devices.md) to Configure this. Este es el método preferido y los dispositivos en este estado se denominan **dispositivos híbridos Unidos de Azure ad**. 
  
Si conserva un Active Directory local que contiene algunos recursos locales (como impresoras y recursos compartidos de archivos), puede conceder a los **dispositivos Unidos a Azure ad** acceso a estos recursos siguiendo los pasos que se indican a continuación: [acceso a recursos locales desde un Dispositivo unido a Azure AD en Microsoft 365 Business](access-resources.md).
  
Una vez que haya configurado los equipos con Windows 10, puede [instalar Office automáticamente](auto-install-or-uninstall-office.md) en los dispositivos. 
  
## <a name="contact-support"></a>Contactar soporte

 **Si necesita ponerse en contacto con soporte técnico:**
  
- Póngase en contacto con su partner.
    
- Como administrador de Microsoft 365 Business, tiene acceso a nuestro equipo de atención al cliente, ** [póngase en contacto con el soporte técnico para productos empresariales: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Temas relacionados
[Documentación y recursos de Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Administrar microsoft 365 Business](manage.md)[migrar a Microsoft 365 Business](migrate-to-microsoft-365-business.md)
  

