---
title: Trabajo necesario para implementar directivas de acceso a dispositivos e identidades-Microsoft 365 Enterprise | Microsoft docs
description: Explica las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de identidad y acceso a dispositivos.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: c1af88f489072490777cc6f2c7edfc66fd038bdf
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544029"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Trabajo de requisitos previos para implementar directivas de acceso a dispositivos e identidades

En este artículo se describen los requisitos previos que deben implementarse antes de poder implementar las directivas de identidad y acceso a dispositivos recomendadas. En este artículo también se analizan las configuraciones de cliente de la plataforma predeterminada que recomendamos proporcionar la mejor experiencia SSO a los usuarios, así como los requisitos previos técnicos para el acceso condicional.


## <a name="prerequisites"></a>Requisitos previos

Antes de implementar las directivas de identidad y acceso de dispositivo recomendadas, hay varios requisitos previos que debe cumplir la organización. En la tabla siguiente se detallan los requisitos previos que se aplican a su entorno. 


| Configuración | Solo nube | Active Directory con sincronización de hash de contraseña |  Autenticación de paso a través |  Federación con AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Configurar la sincronización de hash de contraseña](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Esto debe estar habilitado para detectar las credenciales perdidas y actuar sobre ellas para el acceso condicional basado en riesgos. **Nota:** Esto es necesario independientemente de si su organización usa la autenticación administrada, como la autenticación de paso a través (PTA) o la autenticación federada. |    | Sí | Sí | Sí |
| [Habilite el inicio de sesión único sin problemas](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) para que los usuarios inicien sesión automáticamente en cuando están en sus dispositivos corporativos conectados a la red corporativa. |  | Sí | Sí |  |
| [Configurar redes con nombre](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection recopila y analiza todos los datos de sesión disponibles para generar una puntuación de riesgo. Le recomendamos que especifique los intervalos de direcciones IP públicas de su organización para la red en la configuración de redes con nombre de Azure AD. El tráfico que proviene de estos intervalos recibe una puntuación de riesgo reducida y el tráfico desde fuera del entorno corporativo recibe una puntuación de riesgo mayor. | Sí  | Sí | Sí | Sí |
|[Registrar todos los usuarios para el restablecimiento de contraseña de autoservicio (SSPR) y la autenticación multifactor (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Le recomendamos que registre los usuarios para Azure MFA por adelantado. Azure AD Identity Protection usa Azure MFA para realizar una comprobación de seguridad adicional. Además, para la mejor experiencia de inicio de sesión, recomendamos a los usuarios que instalen la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) y la aplicación Microsoft Company Portal en sus dispositivos. Se pueden instalar desde la tienda de aplicaciones para cada plataforma. | Sí | Sí | Sí | Sí |
| [Habilitar el registro automático de dispositivos de equipos con Windows Unidos a un dominio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). El acceso condicional garantizará que los dispositivos que se conectan a las aplicaciones estén compatibles o Unidos a un dominio. Para permitir esto en equipos Windows, el dispositivo debe estar registrado con Azure AD.  En este artículo se explica cómo configurar el registro automático de dispositivos. |   | Sí |  Sí |  Sí |
| **Preparar el equipo de soporte técnico**. Tenga preparado un plan para los usuarios que no puedan completar MFA. Esto podría ser agregarlos a un grupo de exclusión de directivas o registrar información nueva de MFA para ellos. Antes de realizar cualquiera de estos cambios relativos a la seguridad, debe asegurarse de que el usuario real esté realizando la solicitud. Un paso eficaz es exigir a los administradores de los usuarios que ayuden con la aprobación. | Sí | Sí | Sí | Sí |  
| [Configurar la escritura diferida de contraseñas en AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). La escritura diferida de contraseña permite que Azure AD requiera que los usuarios cambien su contraseña local cuando se detecte una cuenta de riesgo elevado. Puede habilitar esta característica con Azure AD Connect de una de estas dos maneras: habilitar la **escritura diferida de contraseñas** en la pantalla características opcionales del Asistente para la instalación de Azure ad Connect, o bien habilitarla a través de Windows PowerShell. |   | Sí | Sí | Sí |
| [Habilitar Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/enable). La protección de identidad de Azure AD le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización y configurar una directiva de corrección automatizada para el riesgo de inicio de sesión de usuario, el riesgo de inicio de sesión en el nivel bajo, medio y alto.  | Sí | Sí | Sí | Sí |
| **Habilite la autenticación moderna** para [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) y para [Skype empresarial online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). La autenticación moderna es un requisito previo para el uso de multi-factor Authentication (MFA). La autenticación moderna está habilitada de forma predeterminada para los clientes de Office 2016, SharePoint Online y OneDrive para la empresa. | Sí | Sí | Sí | Sí |
||||||



## <a name="recommended-client-configurations"></a>Configuraciones de cliente recomendadas
En esta sección se describen las configuraciones de cliente de la plataforma predeterminada que recomendamos proporcionar la mejor experiencia SSO a los usuarios, así como los requisitos previos técnicos para el acceso condicional.

### <a name="windows-devices"></a>Dispositivos Windows
Se recomienda Windows 10 (versión 1703 o posterior), ya que Azure se ha diseñado para proporcionar la experiencia de SSO más uniforme para local y Azure AD. Los dispositivos basados en el trabajo o la escuela deben estar configurados para unirse a Azure AD directamente o si la organización usa una Unión de dominio AD local, dichos dispositivos deben [configurarse para que se registren de forma automática y silenciosa con Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Para los dispositivos Windows de BYOD, los usuarios pueden **Agregar una cuenta profesional o educativa**. Tenga en cuenta que los usuarios de chrome-browser en Windows 10 necesitan [instalar una extensión](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) para obtener la misma experiencia de inicio de sesión suavizada que los usuarios de Edge/IE. Además, si su organización tiene dispositivos Windows 7 Unidos a un dominio, puede instalar Microsoft Workplace join para equipos que no sean Windows 10 [descargar el paquete para registrar](https://www.microsoft.com/download/details.aspx?id=53554) los dispositivos con Azure ad.

### <a name="ios-devices"></a>Dispositivos iOS
Se recomienda instalar la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) en los dispositivos de usuario antes de implementar directivas MFA o de acceso condicional. Como mínimo, la aplicación debe instalarse cuando se solicite a los usuarios que registren su dispositivo con Azure AD agregando una cuenta profesional o educativa, o bien cuando instalen la aplicación portal de empresa de Intune para inscribir su dispositivo en la administración. Esto depende de la directiva de acceso condicional configurada.

### <a name="android-devices"></a>dispositivos Android
Se recomienda que los usuarios instalen la [aplicación Portal de empresa de Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) y la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de que se implementen las directivas de acceso condicional o cuando sea necesario durante determinados intentos de autenticación. Después de la instalación de la aplicación, se puede pedir a los usuarios que se registren con Azure AD o que inscriban su dispositivo con Intune. Esto depende de la directiva de acceso condicional configurada.

También se recomienda que los dispositivos de propiedad corporativa (DQO) estén estandarizados en los OEM y versiones compatibles con Android for work o Samsung Knox para permitir las cuentas de correo, sean administradas y protegidas por la Directiva MDM de Intune.


### <a name="recommended-email-clients"></a>Clientes de correo electrónico recomendados
Los siguientes clientes de correo electrónico son compatibles con la autenticación moderna y el acceso condicional. 

|Plataforma|Cliente|Versión/Notas|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Habilitar autenticación moderna](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), [actualizaciones necesarias](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook para iOS|[Más reciente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook para Android|[Más reciente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|No compatible||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas para proteger documentos
Se recomiendan los siguientes clientes cuando se ha aplicado una directiva de documentos seguros.

|Plataforma|Word/Excel/PowerPoint|OneNote|Aplicación OneDrive|Aplicación SharePoint|Cliente de sincronización de OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Compatible.|Compatible.|N/D|N/D|Versión preliminar<sup>*</sup>|
|Windows 8.1|Compatible.|Compatible.|N/D|N/D|Versión preliminar<sup>*</sup>|
|Windows 10|Compatible.|Compatible.|N/D|N/D|Versión preliminar<sup>*</sup>|
|Windows Phone 10|No admitido|No admitido|No se admite|No se admite|No se admite|
|Android|Compatible.|Compatible.|Compatible.|Compatible.|No aplicable|
|iOS|Compatible.|Compatible.|Compatible.|Compatible.|No aplicable|
|macOS|Versión preliminar pública|Versión preliminar pública|N/D|N/D|No compatible|
|Linux|No admitido|No admitido|No admitido|No admitido|No admitido|

<sup>*</sup>Obtenga más información sobre el uso de acceso condicional con el [cliente de sincronización de OneDrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Compatibilidad de clientes con Office 365
Para obtener más información acerca de la compatibilidad con clientes de Office 365, vea los siguientes artículos:
- [Compatibilidad con aplicaciones cliente de Office 365: acceso condicional](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access)
- [Compatibilidad con aplicaciones cliente de Office 365: administración de aplicaciones móviles](https://docs.microsoft.com/office365/enterprise/office-365-client-support-mobile-application-management)
- [Compatibilidad con aplicaciones cliente de Office 365: autenticación moderna](https://docs.microsoft.com/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Protección de las cuentas de administrador
Azure AD ofrece una forma sencilla de empezar a proteger el acceso de administrador con una directiva de acceso condicional preconfigurada. En Azure AD, vaya a **acceso condicional** y busque esta directiva: **Directiva de línea de base: requerir MFA para administradores (versión preliminar)**. Seleccione esta directiva y, a continuación, seleccione **usar la Directiva inmediatamente**. 

Esta directiva requiere MFA para los siguientes roles:
- Administradores globales
- Administradores de SharePoint
- Administradores de Exchange
- Administradores de acceso condicional
- Administradores de seguridad

Para obtener más información, consulte [Directiva de seguridad de línea base para cuentas de administrador de Azure ad](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Entre las recomendaciones adicionales se incluyen las siguientes:
- Use Azure AD Privileged Identity Management para reducir el número de cuentas administrativas persistentes. Consulte [empezar a usar PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Use la administración de acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) para proteger a su organización de las infracciones que puedan usar las cuentas de administrador con privilegios existentes con acceso permanente a los datos confidenciales o al acceso a la configuración crítica. 
- Use las cuentas de administrador solo para la administración. Los administradores deben tener una cuenta de usuario independiente para uso no administrativo normal y solo deben usar su cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de trabajo. [Los roles de administrador de office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) tienen muchos más privilegios que los servicios de Office 365.
- Siga los procedimientos recomendados para proteger las cuentas con privilegios en Azure AD como se describe en este [artículo](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Pasos siguientes

[Configurar las directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md)

