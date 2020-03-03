---
title: Plan de Multi-Factor Authentication para implementaciones de Office 365
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre la autenticación multifactor en Office 365 y los pasos que debe seguir para configurarla.
ms.openlocfilehash: 2e2cbc9d6d966a9858fafb62f08d26893c9f4353
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361181"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a>Plan de Multi-Factor Authentication para implementaciones de Office 365

La autenticación multifactor (AM) es un método de autenticación que requiere el uso de más de un método de comprobación y agrega un segundo nivel de seguridad para inicios de sesión de usuario y transacciones. Funciona exigiendo dos o más de los siguientes métodos de comprobación:
  
- Un código de acceso generado de forma aleatoria
    
- Una llamada de teléfono
    
- Una tarjeta inteligente (física o virtual) 
    
- Un dispositivo biométrico 
    
## <a name="multi-factor-authentication-in-office-365"></a>Autenticación multifactor en Office 365

Office 365 usa la autenticación multifactor para ayudar a proporcionar la seguridad adicional y se administra desde el centro de administración de Microsoft 365. Office 365 ofrece el siguiente subconjunto de funciones de Azure Multi-Factor Authentication como parte de la suscripción: 
  
- La posibilidad de habilitar y exigir autenticación multifactor para usuarios finales
    
- El uso de una aplicación móvil (en línea y de contraseña de un solo uso [OTP]) como segundo factor de autenticación
    
- El uso de una llamada de teléfono como segundo factor de autenticación
    
- El uso de un mensaje de servicio de mensajes cortos (SMS) como segundo factor de autenticación
    
- Las contraseñas de aplicación de clientes que no sean de explorador (por ejemplo, el software de comunicaciones Microsoft Lync 2013)
    
- Saludos predeterminados de Microsoft durante las llamadas de teléfono de autenticación
    
Para obtener la lista completa de características adicionales, vea [la comparación de versiones de Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927). Siempre puede obtener la funcionalidad completa si compra el servicio Azure Multi-Factor Authentication. 
  
Obtendrá un subconjunto diferente de funciones dependiendo de si tiene una implementación de solo nube para Office 365 o una implementación híbrida con inicio de sesión único y Servicios de federación de Active Directory (AD FS). 
  
|**¿Dónde se administra el inquilino de Office 365?**|**Opciones de segundo factor de MFA**|
|:-----|:-----|
|Solo nube  <br/> |Azure Active Directory MFA (texto o llamada de teléfono)  <br/> |
|Configuración híbrida, administrada localmente  <br/> | Si administra identidades de usuario locales, tiene las siguientes opciones:  <br/>  Tarjeta inteligente física o virtual (AD FS)  <br/> [Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677) (módulo para AD FS)  <br/>  Azure AD MFA  <br/> |
   
  
En la siguiente figura se muestra cómo las aplicaciones de dispositivo de Office 2013 actualizadas (en Windows) permiten a los usuarios iniciar sesión con MFA. Las aplicaciones del dispositivo de Office 2013 admiten autenticación multifactor mediante el uso de la [Biblioteca de autenticación de Active Directory (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure AD hospeda una página web donde los usuarios pueden iniciar sesión. El proveedor de identidades puede ser Azure AD o un proveedor de identidades federadas como AD FS. La autenticación con usuarios federados sigue estos pasos:
  
1. Azure AD redirige al usuario a la página web de inicio de sesión hospedada por el proveedor de identidades de registro para el inquilino de Office 365. El proveedor de identidades se determina mediante el dominio especificado en el nombre de inicio de sesión del usuario.
    
2. El usuario inicia sesión en la página web de inicio de sesión en su dispositivo. 
    
3. El proveedor de identidades devuelve un token a Azure AD cuando el usuario inicia sesión correctamente.
    
4. Azure AD devuelve un token web de JSON (JWT) a la aplicación de dispositivo de Office y la aplicación de dispositivo se autentica mediante un JWT con Office 365. 
    
Esto se detalla en la figura siguiente:
  
![Autenticación moderna para las aplicaciones para dispositivo de Office 2013.](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a>Requisitos de software

Para habilitar MAF para aplicaciones cliente de Office 2013, debe tener instalado el software siguiente (la versión indicada a continuación o una versión posterior) en función de si tiene una [Instalaciones basadas en Hacer clic y ejecutar](#click-to-run-based-installations) o una [Instalaciones basadas en MSI](#msi-based-installations).
  
Para determinar si la instalación de Office se basa en Hacer clic y ejecutar o en MS:
  
1. Inicie Outlook 2013.
    
2. En el menú **archivo** , elija **cuenta de Office**.
    
3. En las instalaciones basadas en Hacer clic y ejecutar de Outlook 2013, aparecerá un elemento **Opciones de actualización**. En las instalaciones basadas en MSI, no aparecerá un elemento **Opciones de actualización**. 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a>Instalaciones basadas en Hacer clic y ejecutar

En el caso de las instalaciones basadas en Hacer clic y ejecutar, debe tener instalado el software siguiente, en la versión de archivo que se muestra a continuación o una versión de archivo posterior. Si la versión de archivo no es igual o mayor que la versión de archivo que aparece, actualícela siguiendo estos pasos.
  
|**Nombre del archivo**|**Ruta de instalación en el equipo**|**Versión de archivo**|
|:-----|:-----|:-----|
|MsoFalse. Biblioteca  <br/> |C:\Archivos de programa\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |15.0.4753.1001  <br/> |
|CSI. Biblioteca  <br/> |CSI.DLL C:\Archivos de programa\Microsoft Office 15\root\office15\csi.dll  <br/> |15.0.4753.1000  <br/> |
|Groove. EXE  <br/> |C:\Archivos de programa\Microsoft Office 15\root\office15\GROOVE.exe  <br/> |15.0.4763.1000  <br/> |
|Outlook. exe  <br/> |C:\Archivos de programa\Microsoft Office 15\root\office15\OUTLOOK.exe  <br/> |15.0.4753.1002  <br/> |
|Adal. Biblioteca  <br/> |C:\Archivos de programa\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |1.0.2016.624  <br/> |
|Iexplore. exe  <br/> |C:\Archivos de programa\Internet Explorer  <br/> |Varía  <br/> |
   
### <a name="msi-based-installations"></a>Instalaciones basadas en MSI

En el caso de las instalaciones basadas en MSI, debe tener instalado el software siguiente, en la versión de archivo que se muestra a continuación o una versión de archivo posterior. Si la versión de archivo no es igual o mayor que la versión de archivo que aparece, actualícela siguiendo el vínculo de la columna del artículo de Knowledge Base de actualización.
  
|**Nombre del archivo**|**Ruta de instalación en el equipo**|**Dónde obtener la actualización**|**Versión**|
|:-----|:-----|:-----|:-----|
|MsoFalse. Biblioteca  <br/> |C:\Archivos de programa\Archivos comunes\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |[KB3085480](https://support.microsoft.com/kb/3085480) <br/> |15.0.4753.1001  <br/> |
|CSI. Biblioteca  <br/> |C:\Archivos de programa\Archivos comunes\Microsoft Shared\OFFICE15\Csi.dll  <br/> |[KB3085504](https://support.microsoft.com/kb/3085504) <br/> |15.0.4753.1000  <br/> |
|Groove. exe  <br/> |C:\Archivos de programa\Microsoft Office\Office15\GROOVE.EXE  <br/> |[KB3085509](https://support.microsoft.com/kb/3085509) <br/> |15.0.4763.1000  <br/> |
|Outlook. exe  <br/> |C:\Archivos de programa\Microsoft Office\Office15\OUTLOOK.EXE  <br/> |[KB3085495](https://support.microsoft.com/kb/3085495) <br/> |15.0.4753.1002  <br/> |
|Adal. Biblioteca  <br/> |C:\Archivos de programa\Archivos comunes\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |[KB3055000](https://support.microsoft.com/kb/3055000) <br/> |1.0.2016.624  <br/> |
|Iexplore. exe  <br/> |C:\Archivos de programa\Internet Explorer  <br/> |[MS14-052](https://support.microsoft.com/kb/2977629) <br/> |No aplicable  <br/> |
   
## <a name="enable-mfa"></a>Habilitar MFA

Para habilitar MFA, debe completar estos procedimientos:
  
1. Habilitar clientes para autenticación moderna:
    
  - [Habilitar autenticación moderna para Office 2013 en dispositivos Windows](enable-modern-authentication.md) . 
    
  - Configurar Azure MFA con servicios de directorio de terceros.
    
    Consulte los [escenarios avanzados con la autenticación multifactor de Azure y soluciones VPN de terceros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obtener información sobre proveedores de identidades específicos aceptados para este programa. 
    
2. [Configurar autenticación multifactor para Office 365](set-up-multi-factor-authentication.md)
    
3. Indicar a los usuarios individuales cómo iniciar sesión por MFA: [Iniciar sesión en Office 365 con verificación en dos pasos](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)
    
> [!IMPORTANT]
> Si ha habilitado a los usuarios para Azure AD MFA y tienen dispositivos que ejecutan Office 2013 y no están habilitados para autenticación moderna, deben usar AppPasswords con esos dispositivos. Aquí encontrará más información sobre AppPasswords y cuándo, dónde y cómo debe usarse: [App Passwords con Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178). 
  
## <a name="faq"></a>Preguntas más frecuentes

[Artículo de wiki de preguntas más frecuentes sobre la autenticación moderna](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 **Problemas conocidos:**
  
[Autenticación moderna de Office 2013 y Office 365 ProPlus: Lo que debe saber antes de la integración](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Solución de problemas de Azure Multi-Factor Authentication**
  
Vea [Solucionar problemas de Azure MFA](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).
  
[Cómo solucionar problemas de inicio de sesión con autenticación moderna de Office 2013 al usar AD FS](https://support.microsoft.com/kb/3052203/)
  
 **Cuando no funcionan los identificadores alternativos:**
  
[Usar PowerShell para corregir UPN duplicados](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Script para corregir los nombres principales de usuario duplicados](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **Filtrado de acceso de cliente:**
  
[Autenticación moderna de Office 2013 y Office 365 ProPlus y directivas de filtrado de acceso: Lo que debe saber antes de la integración](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **¿Qué aplicaciones son compatibles con MFA?**
  
|**Windows**|**Mac**|**iOS**|**Teléfono Android**|**Tableta Android**|
|:-----|:-----|:-----|:-----|:-----|
|Esta versión es compatible con autenticación moderna para Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 y Skype Empresarial.  <br/> |Esta versión es compatible con autenticación moderna para Word 2016 para Mac, Excel 2016 para Mac y PowerPoint 2016 para Mac.  <br/> |Esta versión es compatible con autenticación moderna para Word para iPad, Excel para iPad y PowerPoint para iPad.  <br/> |Esta versión es compatible con autenticación moderna para Word para Android, Excel para Android y PowerPoint para Android.  <br/> |Esta versión es compatible con autenticación moderna para Word para Android, Excel para Android y PowerPoint para Android.  <br/> |
|Esta versión es compatible con autenticación moderna para Outlook 2013 y Outlook 2016.  <br/> |Esta versión es compatible con autenticación moderna para Outlook 2016 para Mac.  <br/> |Esta versión es compatible con autenticación moderna para Outlook para iPad.  <br/> |||
   

