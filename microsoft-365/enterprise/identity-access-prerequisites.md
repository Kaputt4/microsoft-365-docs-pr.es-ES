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
ms.openlocfilehash: e97b16b3520d500737e0b397e8e2a515ecac9b3f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871814"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Trabajo de requisitos previos para la implementación de directivas de acceso de identidad y dispositivos

En este artículo se describe los requisitos previos que son necesarios para implementar antes de poder implementar la identidad recomendada y las directivas de acceso de dispositivo. En este artículo también se describe las configuraciones de cliente de plataforma predeterminada que se recomienda para proporcionar la mejor experiencia SSO a los usuarios, así como los requisitos previos técnicos para el acceso condicional.


## <a name="prerequisites"></a>Requisitos previos

Antes de implementar la identidad recomendada y las directivas de acceso de dispositivo, existen varios requisitos previos que debe cumplir con su organización. Vea la siguiente tabla para los requisitos previos que se aplican a su entorno. 


| Configuración | Solo nube | Active Directory con la sincronización de hash de contraseña |  Federación con AD FS |
| :------------- | :-----------: | :--------------: | :------------: |
|  [Configurar la sincronización de contraseñas Hash](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Esto debe estar habilitada para detectar credenciales perdidas y para que actúe en ellos de riesgo en función de acceso condicional. **Nota:** Esto es necesario, independientemente de si su organización usa autenticación administrada, al igual que la autenticación de paso a través (PTA) o autenticación federada. |    | Sí | Sí |
| [Habilitar un inicio de sesión único perfecta](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) para iniciar sesión automáticamente a los usuarios en cuando están en sus dispositivos corporativos conectados a la red corporativa. |  | Sí |  |
| [Configure había denominado redes](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Protección de identidad de AD Azure recopila y analiza todos los datos de sesión disponibles para generar una puntuación de riesgo. Se recomienda que especificar intervalos IP públicas de su organización para la red en Azure AD denominado configuración de redes. El tráfico procedente de estos intervalos recibe una puntuación de reducción del riesgo, por lo que se trata el tráfico desde fuera del entorno corporativo como puntuación de mayor riesgo. | Sí  | Sí | Sí |
|[Registrar todos los usuarios para restablecer contraseñas de autoservicio (SSPR) y la autenticación multifactor (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Se recomienda que registrar a los usuarios de MFA de Azure antes de tiempo. Protección de identidad de Azure AD hace uso de MFA de Azure para realizar la comprobación de seguridad adicionales. Además, para la mejor experiencia de inicio de sesión, se recomienda a los usuarios instalar la [Aplicación de autenticador de Microsoft](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) y la aplicación de Portal de empresa de Microsoft en sus dispositivos. Estos pueden instalarse desde el almacén de aplicación para cada plataforma. | Sí | Sí | Sí |
| [Habilitar el registro automático de dispositivos de equipos Windows unidos a dominio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). El acceso condicional puede garantizar que el dispositivo que se conecta al servicio sea un dispositivo unido a dominio o compatible. Para permitir esto en equipos Windows, el dispositivo debe estar registrado con Azure AD.  En este artículo se explica cómo configurar el registro automático de dispositivos. |   | Sí |  Sí |
| **Preparar el equipo de soporte técnico**. Tenga preparado un plan para los usuarios que no puedan completar MFA. Puede consistir en agregarlos a un grupo de exclusión de directivas o registrar nueva información MFA para ellos. Antes de llevar a cabo cualquiera de estos importantes cambios de seguridad, debe asegurarse de que sea el usuario real el que realice la solicitud. Un paso eficaz es exigir a los administradores de los usuarios que ayuden con la aprobación. | Sí | Sí | Sí |
| [Configurar la escritura diferida de contraseñas en AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). La escritura diferida de contraseñas permite a Azure AD exigir que los usuarios cambien sus contraseñas locales cuando se ha detectado un alto riesgo de cuenta comprometida. Puede habilitar esta característica mediante Azure AD Connect de dos maneras distintas. Puede habilitar la escritura diferida de contraseñas en la pantalla de características opcionales del asistente para la configuración de Azure AD Connect, o bien puede habilitarla a través de Windows PowerShell. |   | Sí | Sí |
| [Activar la protección de identidad de Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable). Protección de identidad de AD Azure permite detectar posibles vulnerabilidades que afectan a las identidades de la organización y configurar la directiva de la corrección automatizada a bajo, medio y el inicio de sesión de alto riesgo y el riesgo de usuario.  | Sí | Sí | Sí |
| **Habilitar la autenticación moderna** para [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) y [Skype para profesionales en línea](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Autenticación moderna es un requisito previo para usar la autenticación multifactor (MFA). Autenticación moderna está habilitada de forma predeterminada para Office 2016 clientes, SharePoint Online y OneDrive para la empresa. | Sí | Sí | Sí |
|||||



## <a name="recommended-client-configurations"></a>Configuraciones de cliente recomendadas
En esta sección se tratan las configuraciones de cliente de plataforma predeterminadas que se recomiendan para proporcionar la mejor experiencia de SSO a los usuarios, además de los requisitos técnicos previos para el acceso condicional.

### <a name="windows-devices"></a>Dispositivos Windows
Se recomienda Windows 10 (versión 1703 o posterior), ya que Azure se ha diseñado para proporcionar la experiencia de SSO más uniforme para local y Azure AD. Los dispositivos emitidos por una empresa o centro educativo deben configurarse para unirse a Azure AD directamente o, si la organización usa la unión a un dominio de AD local, para [registrarse de forma automática y silenciosa con Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

En el caso de los dispositivos Windows BYOD, los usuarios pueden usar "Agregar cuenta profesional o educativa". Tenga en cuenta que los usuarios del explorador Chrome en Windows 10 tienen que [instalar una extensión](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) para poder obtener la misma experiencia de inicio de sesión uniforme que los de Edge o IE. Además, si la organización tiene dispositivos Windows 7 unidos a dominio, puede instalar Microsoft Workplace Join para que los equipos que no sean Windows 10 [empaqueten para registrar](https://www.microsoft.com/download/details.aspx?id=53554) los dispositivos con Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS
Se recomienda instalar la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) en los dispositivos de usuario antes de implementar el acceso condicional o las directivas de MFA. Como mínimo, la aplicación debe instalarse cuando los usuarios se le pida que registrar su dispositivo con Azure AD mediante la adición de un trabajo o escuela cuenta o al instalar la aplicación de portal de empresa Intune inscribirse su dispositivo en administración. Esto depende de la directiva de acceso condicional configurado.

### <a name="android-devices"></a>Dispositivos Android
Se recomienda que los usuarios instalen la [aplicación Portal de empresa de Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
) y la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de que se implementen las directivas de acceso condicional o cuando sea necesario durante determinados intentos de autenticación. Después de la instalación de la aplicación, se puede pedir a los usuarios que se registren con Azure AD o que inscriban su dispositivo con Intune. Esto depende de la directiva de acceso condicional configurada.

También se recomienda que los dispositivos corporativos (COD) estén estandarizados en los OEM y que las versiones que admiten Android for Work o Samsung Knox permitan que las cuentas de correo electrónico sean administradas y protegidas mediante directivas de MDM de Intune.


### <a name="recommended-email-clients"></a>Clientes de correo electrónico recomendados
Los siguientes clientes de correo electrónico admiten la autenticación moderno y acceso condicional. 

|Plataforma|Cliente|Versión/Notas|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Habilitar autenticación moderna](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [Actualizaciones necesarias](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook para iOS|[Más reciente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook para Android|[Más reciente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**Mac OS**|Outlook|2016|
|**Linux**|No compatible||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas para proteger documentos
Si se ha aplicado una directiva de documentos seguros, se recomiendan los siguientes clientes.

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

<sup>*</sup>Obtenga más información acerca del uso de acceso condicional con el [Cliente de sincronización de OneDrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Compatibilidad de clientes con Office 365
Para obtener más información acerca de la compatibilidad con clientes de Office 365, vea los siguientes artículos:
- [Compatibilidad con aplicaciones cliente de Office 365 - acceso condicional](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Compatibilidad con aplicaciones cliente de Office 365 - administración de aplicaciones móviles](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Soporte de aplicación de cliente de Office 365 - autenticación moderna](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Protección de las cuentas de administrador
Azure Active Directory proporciona una manera sencilla para comenzar a proteger el acceso de administrador con una directiva de acceso condicional preconfigurado. Dentro de Azure AD, vaya al servidor blade de acceso condicional y busque esta directiva — **Directiva de línea de base: requieren MFA para los administradores de**. Haga clic en esta directiva y seleccione **inmediatamente la directiva de uso**. 

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
- Usar las cuentas de administrador de Office 365 sólo para la administración. Los administradores deben tener un usuario independiente de cuenta para el uso normal de no administrativas y utilizar sólo las cuentas administrativas cuando sea necesario para completar una tarea asociada a su función de trabajo. Roles de [Administrador de Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) tienen mucha más privilegios para servicios de Office 365.
- Siga los procedimientos recomendados para proteger las cuentas con privilegios en Azure AD tal como se describe en este [artículo](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Pasos siguientes

[Configurar la identidad común y las directivas de acceso de dispositivo](identity-access-policies.md)

