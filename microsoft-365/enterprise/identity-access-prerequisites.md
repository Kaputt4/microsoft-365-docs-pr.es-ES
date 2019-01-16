---
title: Trabajo de requisitos previos para la implementación de identidad y dispositivo acceder a las directivas - Microsoft 365 Enterprise | Documentos de Microsoft
description: Explica las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de identidad y acceso a dispositivos.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ee517e774e0606c62efdc67d869ad0aca5a41640
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871814"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Trabajo de requisitos previos para la implementación de directivas de acceso de identidad y dispositivos

En este artículo se describe los requisitos previos que necesitan implementarse antes de poder implementar la identidad recomendada y las directivas de acceso de dispositivo. En este artículo también se describe las configuraciones de cliente de plataforma predeterminada que se recomienda para proporcionar la mejor experiencia SSO a los usuarios, así como los requisitos previos técnicos para el acceso condicional.


## <a name="prerequisites"></a>Requisitos previos

Antes de implementar la identidad recomendada y las directivas de acceso de dispositivo, existen varios requisitos previos que debe cumplir con su organización. En la siguiente tabla se detalla los requisitos previos que se aplican a su entorno. 


| Configuración | Solo nube | Active Directory con la sincronización de hash de contraseña |  Autenticación de paso a través |  Federación con AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Configurar la sincronización de contraseñas Hash](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Debe habilitarse para detectar credenciales perdidas y para que actúe en ellos para acceso condicional basado en riesgo. **Nota:** Esto es necesario, independientemente de si su organización usa autenticación administrada, al igual que la autenticación de paso a través (PTA) o autenticación federada. |    | Sí | Sí | Sí |
| [Habilitar inicio de sesión único perfecta](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) para iniciar sesión automáticamente a los usuarios en cuando están en sus dispositivos corporativos conectados a la red corporativa. |  | Sí | Sí |  |
| [Configure había denominado redes](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Protección de identidad de AD Azure recopila y analiza todos los datos de sesión disponibles para generar una puntuación de riesgo. Se recomienda que especificar intervalos IP públicas de su organización para la red en Azure AD denominado configuración de redes. El tráfico procedente de estos intervalos recibe una puntuación de reducción del riesgo, y el tráfico desde fuera del entorno corporativo recibe una puntuación más alta de riesgo. | Sí  | Sí | Sí | Sí |
|[Registrar todos los usuarios para restablecer contraseñas de autoservicio (SSPR) y la autenticación multifactor (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Se recomienda que registrar a los usuarios de MFA de Azure antes de tiempo. Protección de identidad de Azure AD hace uso de MFA de Azure para realizar la comprobación de seguridad adicionales. Además, para la mejor experiencia de inicio de sesión, se recomienda a los usuarios instalar la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) y la aplicación de Portal de empresa de Microsoft en sus dispositivos. Estos pueden instalarse desde el almacén de aplicación para cada plataforma. | Sí | Sí | Sí | Sí |
| [Habilitar el registro de dispositivo automática de los equipos unidos a un dominio de Windows](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). Acceso condicional se asegurará de dispositivos que se conectan a las aplicaciones están unidos a un dominio o compatible. Para admitir esto en equipos con Windows, el dispositivo debe estar registrado con Azure AD.  En este artículo se describe cómo configurar el registro de dispositivo automática. |   | Sí |  Sí |  Sí |
| **Prepare el equipo de soporte**. Tener un plan en lugar de los usuarios que no se puede completar MFA. Esto podría ser agregándolos a un grupo de exclusión de la directiva, o registrar la nueva información de MFA para ellos. Antes de realizar cualquiera de estos cambios afectan a la seguridad, debe asegurarse de que el usuario real realiza la solicitud. Los administradores de los usuarios ayudar con la aprobación de la necesidad de realizar es un paso eficaz. | Sí | Sí | Sí | Sí |  
| [Configure la reescritura de contraseña en AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Reescritura de contraseña permite Azure AD requerir que los usuarios cambien sus contraseñas local cuando se detecta un compromiso de cuenta de alto riesgo. Puede habilitar esta característica con Azure Connect de AD en una de estas dos formas: puede habilitar la **Reescritura de contraseña** en la pantalla de las características opcionales del Asistente para el programa de instalación de Azure Connect AD o habilitar a través de Windows PowerShell. |   | Sí | Sí | Sí |
| [Activar la protección de identidad de Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable). Protección de identidad de AD de Azure permite detectar posibles vulnerabilidades que afectan a las identidades de la organización y configurar una directiva de la corrección automatizada a bajo, medio y el inicio de sesión de alto riesgo y el riesgo de usuario.  | Sí | Sí | Sí | Sí |
| **Habilitar la autenticación moderna** para [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) y [Skype para profesionales en línea](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Autenticación moderna es un requisito previo para usar la autenticación multifactor (MFA). Autenticación moderna está habilitada de forma predeterminada para Office 2016 clientes, SharePoint Online y OneDrive para la empresa. | Sí | Sí | Sí | Sí |
||||||



## <a name="recommended-client-configurations"></a>Configuraciones de cliente recomendadas
En esta sección se describe las configuraciones de cliente de plataforma predeterminada que se recomienda para proporcionar la mejor experiencia SSO a los usuarios, así como los requisitos previos técnicos para el acceso condicional.

### <a name="windows-devices"></a>Dispositivos Windows
Se recomienda el 10 de Windows (versión 1703 o posterior), como Azure está diseñada para proporcionar el SSO más fluida experiencia posibles para local y Azure AD. Trabajo o emitido school dispositivos deben configurarse para unirse a Azure AD directamente o si los usos de la organización local unirse a un dominio AD, esos dispositivos deben estar [configurado para automáticamente y registrar en modo silencioso con Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Para los dispositivos de Windows BYOD, los usuarios pueden usar **Agregar trabajo o escuela cuenta**. Tenga en cuenta que los usuarios del explorador de Chrome en Windows 10 necesitan para [instalar una extensión](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) para obtener la misma suave inicio de sesión de experiencia que los usuarios de IE/perimetral. Además, si su organización tiene dispositivos unido a un dominio de Windows 7, puede instalar unirse a área de trabajo de Microsoft para [descargar el paquete para registrar](https://www.microsoft.com/download/details.aspx?id=53554) los equipos que no sean Windows 10 los dispositivos con Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS
Se recomienda instalar la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) en los dispositivos de usuario antes de implementar el acceso condicional o las directivas de MFA. Como mínimo, la aplicación debe instalarse cuando los usuarios están más frecuentes para registrar sus dispositivos con Azure AD mediante la adición de un trabajo o escuela cuenta, o al instalar la aplicación de portal de empresa Intune inscribirse su dispositivo en administración. Esto depende de la directiva de acceso condicional configurado.

### <a name="android-devices"></a>Dispositivos Android
Se recomienda que los usuarios instalen la [aplicación Portal de empresa de Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) y la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de que se implementen las directivas de acceso condicional o cuando sea necesario durante determinados intentos de autenticación. Después de la instalación de la aplicación, se puede pedir a los usuarios que se registren con Azure AD o que inscriban su dispositivo con Intune. Esto depende de la directiva de acceso condicional configurada.

También se recomienda que los dispositivos que pertenecen corporativo (COD) están estandarizados en los OEM y las versiones que admiten Android para el trabajo o Samsung Knox permitir que las cuentas de correo, administrar y proteger mediante una directiva de MDM Intune.


### <a name="recommended-email-clients"></a>Clientes de correo electrónico recomendados
Los siguientes clientes de correo electrónico admiten la autenticación moderna y acceso condicional. 

|Plataforma|Cliente|Versión/Notas|
|:-------|:-----|:------------|
|**Windows**|Outlook|2013, 2016 [Habilitar autenticación moderna](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [actualizaciones obligatorias](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook para iOS|[Más reciente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook para Android|[Más reciente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**Mac OS**|Outlook|2016|
|**Linux**|No compatible||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas para proteger documentos
Se recomiendan los siguientes clientes cuando se ha aplicado una directiva de documentos seguros.

|Plataforma|Word, Excel y PowerPoint|OneNote|Aplicación OneDrive|Aplicación SharePoint|Cliente de sincronización de OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Compatible.|Compatible.|No aplicable|No aplicable|Versión preliminar<sup>*</sup>|
|Windows 8.1|Compatible.|Compatible.|No aplicable|No aplicable|Versión preliminar<sup>*</sup>|
|Windows 10|Compatible.|Compatible.|No aplicable|No aplicable|Versión preliminar<sup>*</sup>|
|Windows Phone 10|No compatible|No se admite|No se admite|No se admite|No se admite|
|Android|Compatible.|Admitido|Admitido|Compatible.|No aplicable|
|iOS|Compatible.|Admitido|Admitido|Compatible.|No aplicable|
|Mac OS|Versión preliminar pública|Versión preliminar pública|No aplicable|No aplicable|No compatible|
|Linux|No compatible|No compatible|No compatible|No compatible|No se admite|

<sup>*</sup>Obtenga más información acerca del uso de acceso condicional con el [cliente de sincronización de OneDrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Compatibilidad de clientes con Office 365
Para obtener más información acerca de la compatibilidad con clientes de Office 365, vea los siguientes artículos:
- [Compatibilidad con aplicaciones cliente de Office 365 - acceso condicional](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Compatibilidad con aplicaciones cliente de Office 365 - administración de aplicaciones móviles](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Soporte de aplicación de cliente de Office 365 - autenticación moderna](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Protección de las cuentas de administrador
Azure AD proporciona una manera sencilla para comenzar a proteger el acceso de administrador con una directiva de acceso condicional preconfigurado. En Azure AD, vaya a **acceso condicional** y busque esta directiva — **Directiva de línea de base: requieren MFA para los administradores de**. Seleccione esta directiva y, a continuación, seleccione **Directiva de uso inmediatamente**. 

Esta directiva requiere MFA para las siguientes funciones:
- Administradores globales
- Administradores de SharePoint
- Administradores de Exchange
- Administradores de acceso condicional
- Administradores de seguridad

Para obtener más información, vea [Directiva de seguridad de línea de base para las cuentas de administración de Azure AD](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Recomendaciones adicionales son las siguientes:
- Use la administración de identidades con privilegios de Azure AD para reducir el número de cuentas administrativas persistentes. Vea [empezar a usar PIM](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Usar administración de acceso con privilegios en Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview) para proteger la organización de las infracciones que se pueden usar los existentes con privilegios de cuentas de administrador con acceso permanente a los datos confidenciales o acceso a la configuración de configuración crítica. 
- Usar las cuentas de administrador de Office 365 sólo para la administración. Los administradores deben tener un usuario independiente de cuenta para el uso normal de no administrativas y utilizar sólo las cuentas administrativas cuando sea necesario para completar una tarea asociada a su función de trabajo. Roles de [Administrador de Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) tienen mucha más privilegios que Servicios de Office 365.
- Siga los procedimientos recomendados para proteger las cuentas con privilegios en Azure AD tal como se describe en este [artículo](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Pasos siguientes

[Configurar la identidad común y las directivas de acceso de dispositivo](identity-access-policies.md)

