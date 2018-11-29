---
title: Acceso a recursos desde un dispositivo unido a AD Azure en Microsoft 365 Business local
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Obtenga información sobre cómo obtener acceso a los recursos locales como aplicaciones de línea de negocio, recursos compartidos de archivos e impresoras de Azure Active Directory se unió a 10 Windows dispositivo.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871186"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Acceso a recursos desde un dispositivo unido a AD Azure en Microsoft 365 Business local

Cualquier dispositivo de 10 de Windows Azure Active Directory se unió a tendrá acceso a todos los recursos basados en la nube, como las aplicaciones de Office 365 y puede estar protegido por Microsoft 365 empresarial. Para permitir también el acceso a los recursos locales como aplicaciones de línea de negocio (LOB), recursos compartidos de archivos e impresoras, debe sincronizar su Active Directory local con Azure Active Directory mediante el uso de [Azure Connect de AD](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). Consulte [Introducción a la administración de dispositivos en Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) para obtener más información. 
  
## <a name="run-azure-ad-connect"></a>Conectar ejecutar Azure AD

Complete los pasos siguientes para habilitar los dispositivos de Azure AD se unió a la organización tener acceso a los recursos locales.
  
1. Para sincronizar los usuarios, grupos y contactos de Active Directory local en Azure Active Directory, ejecute al Asistente para la sincronización de directorios y Azure Connect de AD como se describe en [Configurar la sincronización de Active directory para Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. Una vez haya finalizado la sincronización de directorios, asegúrese de que los dispositivos de Windows 10 de su organización estén Azure AD se unió a. En este paso se realiza individualmente en cada dispositivo 10 de Windows. Para obtener información detallada, vea [configurar los dispositivos de Windows para los usuarios de Microsoft Business de 365](set-up-windows-devices.md) . 
    
3. Una vez que los dispositivos de 10 de Windows Azure AD Unido, todos los usuarios deben reiniciar sus dispositivos y el inicio de sesión con sus credenciales de Microsoft 365 empresarial. Todos los dispositivos tendrán acceso a los recursos de local así como ahora.
    
No hay pasos adicionales necesarios para obtener acceso a recursos para Azure AD se unió a dispositivos en local. Esto es una función integrada disponible en 10 de Windows. 
  
Si su organización no está preparada implementar en la Azure AD se unió a configuración de dispositivo se ha descrito anteriormente, considere la posibilidad de configuración de seguridad de la [configuración de dispositivo se unió híbrida Azure AD](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Consideraciones al unirse a los dispositivos de Windows para Azure AD

Si se encuentra Azure AD que se unen a un dispositivo de Windows que anteriormente se ha unido a un dominio o en un grupo de trabajo, debe tener en cuenta las siguientes limitaciones:
  
- Cuando se une un dispositivo de Azure AD, crea un nuevo usuario sin hacer referencia a un perfil existente. Para solucionar este problema, los perfiles deben migrarse manualmente. Un perfil de usuario contiene información como favoritos, archivos locales, configuración del explorador, configuración del menú Inicio, etcetera. Un enfoque mejor es encontrar una herramienta de terceros para asignar los archivos existentes y la configuración para el nuevo perfil
    
- Si el dispositivo está utilizando objetos de directiva de grupo (GPO), es posible que algunos GPO no tiene un comparable de [Proveedor de servicios de configuración](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) en Intune. Ejecute la [herramienta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para averiguar los CSP comparables para los GPO existentes. 
    
- Los usuarios no podrán autenticarse en las aplicaciones que dependen de la autenticación de Active Directory. Para abordar los problemas con esto evaluar el uso de una aplicación heredada y considere la posibilidad de actualizar a una aplicación que usa autenticación moderno si es posible.
    
- Descubrimiento de impresora de Active Directory no funcionará. Para solucionar este problema, proporcione las rutas de acceso directo de impresora para todos los usuarios o sacar provecho de [Impresión de la nube híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
    

