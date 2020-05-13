---
title: Planeación de multi-factor Authentication para implementaciones de Microsoft 365
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
description: Obtenga más información sobre la autenticación multifactor en Microsoft 365 y los pasos que debe seguir para configurarla.
ms.openlocfilehash: 6d28e9e7db825aa9030196396ad420028dc1c881
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213133"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a>Planeación de multi-factor Authentication para implementaciones de Microsoft 365

La autenticación multifactor (AM) es un método de autenticación que requiere el uso de más de un método de comprobación y agrega un segundo nivel de seguridad para inicios de sesión de usuario y transacciones. Funciona solicitando un paso de comprobación de adición con información más allá de la contraseña de la cuenta de usuario, como por ejemplo:
  
- Un código de verificación generado aleatoriamente enviado a su smartphone
    
- Una llamada de teléfono
    
- Una tarjeta inteligente (física o virtual) 
    
- Un dispositivo biométrico 
    
## <a name="mfa-in-microsoft-365"></a>MFA en Microsoft 365

Microsoft 365 usa MFA para ayudar a proporcionar la seguridad adicional y se administra desde el centro de administración de Microsoft 365. Microsoft 365 ofrece el siguiente subconjunto de capacidades de [Azure multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) como parte de la suscripción: 
  
- La capacidad de habilitar y exigir MFA a los usuarios finales
    
- El uso de una aplicación móvil (en línea y de contraseña de un solo uso [OTP]) como segundo factor de autenticación
    
- El uso de una llamada de teléfono como segundo factor de autenticación
    
- El uso de un mensaje de texto de servicio de mensajes cortos (SMS) como segundo factor de autenticación
    
- Contraseñas de aplicación para clientes que no son exploradores (por ejemplo, el software de comunicaciones Microsoft Lync 2013)
    
- Saludos predeterminados de Microsoft durante las llamadas de teléfono de autenticación
    
Para obtener una lista completa de las características agregadas, consulte [Azure multi-factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927). Siempre puede obtener la funcionalidad completa mediante la compra de [licencias de Azure multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing). 
  
Se obtiene un subconjunto diferente de funcionalidades en función de si se usa la identidad solo en la nube cuando las cuentas de usuario existen en Microsoft 365 o una configuración híbrida con inicio de sesión único y servicios de Federación de Active Directory (AD FS). 
  
|**¿Dónde se administra Microsoft 365?**|**Opciones de segundo factor de MFA**|
|:-----|:-----|
|Solo nube  <br/> | Azure multi-factor Authentication (texto o llamada telefónica)  <br/> |
|Configuración híbrida, administrada localmente  <br/> | Si administra identidades de usuario locales, tiene las siguientes opciones:  <br/> -Tarjeta inteligente física o virtual (AD FS)  <br/> -Azure multi-factor Authentication (módulo para AD FS)  <br/>  -Azure multi-factor Authentication  <br/> |
   
Las aplicaciones para dispositivos de Office 2013 admiten MFA mediante el uso de la [biblioteca de autenticación de Active Directory (Adal)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure Active Directory (Azure AD) hospeda una página web en la que los usuarios pueden iniciar sesión. El proveedor de identidades puede ser Azure AD o un proveedor de identidades federadas como AD FS. La autenticación con usuarios federados sigue estos pasos:
  
1. Azure AD redirige al usuario a la Página Web de inicio de sesión hospedada por el proveedor de identidades del registro de la organización. El proveedor de identidades se determina mediante el dominio especificado en el nombre de inicio de sesión del usuario.
    
2. El usuario inicia sesión en la página web de inicio de sesión en su dispositivo. 
    
3. El proveedor de identidades devuelve un token a Azure AD cuando el usuario inicia sesión correctamente.
    
4. Azure AD devuelve un token Web de JSON (JWT) a la aplicación de dispositivo de Office y la aplicación de dispositivo se autentica con un JWT con Microsoft 365. 
    
  
## <a name="requirements-for-office-2013-client-apps"></a>Requisitos para aplicaciones cliente de Office 2013

Para habilitar MAF para aplicaciones cliente de Office 2013, debe tener instalado el software siguiente (la versión indicada a continuación o una versión posterior) en función de si tiene una [Instalaciones basadas en Hacer clic y ejecutar](#click-to-run-based-installations) o una [Instalaciones basadas en MSI](#msi-based-installations).
  
Para determinar si la instalación de Office se basa en Hacer clic y ejecutar o en MS:
  
1. Inicie Outlook 2013.
    
2. En el menú **archivo** , elija **cuenta de Office**.
    
3. En las instalaciones basadas en Hacer clic y ejecutar de Outlook 2013, aparecerá un elemento **Opciones de actualización**. En las instalaciones basadas en MSI, no aparecerá un elemento **Opciones de actualización**. 
    
    ![Cómo reconocer si su instalación de Office 2013 es hacer clic y ejecutar o basada en MSI](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

Sor obtener más información, consulte el [artículo de preguntas más frecuentes sobre la autenticación moderna](https://go.microsoft.com/fwlink/p/?LinkId=530064).
  
### <a name="click-to-run-based-installations"></a>Instalaciones basadas en Hacer clic y ejecutar

En el caso de las instalaciones basadas en hacer clic y ejecutar, debe tener instalado el software siguiente, con la versión de archivo que se muestra a continuación o una versión de archivo posterior. Si la versión de archivo no es igual o mayor que la versión de archivo que aparece, actualícela siguiendo estos pasos.
  
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

Para habilitar MFA en la suscripción, siga estos pasos:
  
1. Si es necesario: 

  - [Habilite la autenticación moderna para Office 2013 en dispositivos Windows](enable-modern-authentication.md).
    
  - Configurar Azure multi-factor Authentication con servicios de directorio de terceros.
    
    Consulte [escenarios avanzados con la autenticación multifactor de Azure y soluciones VPN de terceros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obtener información sobre proveedores de identidades específicos aceptados para este programa. 
    
2. [Configure la MFA para Microsoft 365](set-up-multi-factor-authentication.md).
    
3. Informe a los usuarios individuales sobre cómo iniciar sesión mediante MFA. Consulte [iniciar sesión en Microsoft 365 con MFA](https://support.office.com/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb).

> [!IMPORTANT]
> Si ha habilitado a los usuarios para la autenticación multifactor de Azure y tiene los dispositivos que ejecutan Office 2013 que no están habilitados para la autenticación moderna, deberán usar contraseñas de aplicación en estos dispositivos. Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) para obtener más información.
  
## <a name="faq"></a>Preguntas más frecuentes

[Artículo de wiki de preguntas más frecuentes sobre la autenticación moderna](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a>Problemas conocidos

[Office 2013 y aplicaciones de Microsoft 365 para la autenticación moderna empresarial: aspectos que deben conocerse antes de la incorporación](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Solución de problemas de Azure Multi-Factor Authentication**
  
Consulte [troubleshoot Azure multi-factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).
  
[Cómo solucionar problemas de inicio de sesión con autenticación moderna de Office 2013 al usar AD FS](https://support.microsoft.com/kb/3052203/)
  
 **Cuando no funcionan los identificadores alternativos:**
  
[Usar PowerShell para corregir UPN duplicados](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Script para corregir los nombres principales de usuario duplicados](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **Filtrado de acceso de cliente:**
  
[Office 2013 y Microsoft 365 aplicaciones para la autenticación moderna para empresas y directivas de filtrado de acceso de cliente: lo que debe saber antes de la incorporación](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **¿Qué aplicaciones son compatibles con MFA?**
  
|**Windows**|**Mac**|**iOS**|**Teléfono Android**|**Tableta Android**|
|:-----|:-----|:-----|:-----|:-----|
|Esta versión es compatible con autenticación moderna para Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 y Skype Empresarial.  <br/> |Esta versión es compatible con autenticación moderna para Word 2016 para Mac, Excel 2016 para Mac y PowerPoint 2016 para Mac.  <br/> |Esta versión es compatible con autenticación moderna para Word para iPad, Excel para iPad y PowerPoint para iPad.  <br/> |Esta versión es compatible con autenticación moderna para Word para Android, Excel para Android y PowerPoint para Android.  <br/> |Esta versión es compatible con autenticación moderna para Word para Android, Excel para Android y PowerPoint para Android.  <br/> |
|Esta versión es compatible con autenticación moderna para Outlook 2013 y Outlook 2016.  <br/> |Esta versión es compatible con autenticación moderna para Outlook 2016 para Mac.  <br/> |Esta versión es compatible con autenticación moderna para Outlook para iPad.  <br/> |||
   

