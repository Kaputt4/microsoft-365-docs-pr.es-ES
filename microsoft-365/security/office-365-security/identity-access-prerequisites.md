---
title: 'Trabajo de requisitos previos para implementar directivas de acceso a dispositivos e identidades: Microsoft 365 para Enterprise | Microsoft docs'
description: Describe los requisitos previos antes de implementar directivas y configuraciones de acceso a dispositivos e identidades.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/01/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: bd0b4efb1281d467a61e4aee792b507f0ca44181
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616565"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Trabajo de requisitos previos para implementar directivas de acceso a dispositivos e identidades

En este artículo se describen los requisitos previos que deben implementarse antes de poder implementar las directivas de identidad y acceso a dispositivos recomendadas. En este artículo también se analizan las configuraciones recomendadas del cliente de la plataforma predeterminada para proporcionar la mejor experiencia de inicio de sesión único (SSO) a los usuarios, así como los requisitos previos técnicos para el acceso condicional.

## <a name="prerequisites"></a>Requisitos previos

Antes de implementar las directivas recomendadas de identidad y acceso a dispositivos, hay varios requisitos previos que su organización debe cumplir para estos modelos de identidad y autenticación para Microsoft 365 y Office 365:

- Solo de nube
- Autenticación híbrida con sincronización de hash de contraseña (PHS)
- Híbrido con autenticación de paso a través (PTA)
- Federadas

En la siguiente tabla se detallan las características de los requisitos previos y su configuración que se aplican a todos los modelos de identidad, excepto donde se indique.

|Configuración|Exceptions|
|---|:---:|
|[Configurar PHS](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).  Esto debe estar habilitado para detectar las credenciales perdidas y actuar sobre ellas para el acceso condicional basado en riesgos. **Nota:** Esto es necesario independientemente de si su organización usa la autenticación federada.|Solo de nube|
|[Habilitar el inicio de sesión único sin problemas](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) para que los usuarios puedan iniciar sesión de forma automática en cuando están en sus dispositivos de la organización conectados a la red de la organización.|Solo en la nube y federado|
|[Configurar redes con nombre](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection recopila y analiza todos los datos de sesión disponibles para generar una puntuación de riesgo. Le recomendamos que especifique los intervalos de direcciones IP públicas de su organización para la red en la configuración de redes con nombre de Azure AD. El tráfico que proviene de estos intervalos recibe una puntuación de riesgo reducida y el tráfico externo al entorno de la organización recibe una puntuación de riesgo mayor.||
|[Registrar todos los usuarios para el restablecimiento de contraseña de autoservicio (SSPR) y la autenticación multifactor (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Le recomendamos que registre los usuarios para la autenticación multifactor de Azure AD con antelación. Azure AD Identity Protection hace uso de la autenticación multifactor de Azure AD para realizar comprobaciones de seguridad adicionales. Además, para la mejor experiencia de inicio de sesión, recomendamos a los usuarios que instalen la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) y la aplicación Microsoft Company Portal en sus dispositivos. Se pueden instalar desde la tienda de aplicaciones para cada plataforma.||
|[Habilitar el registro automático de dispositivos de equipos con Windows Unidos a un dominio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). El acceso condicional garantizará que los dispositivos que se conectan a las aplicaciones estén compatibles o Unidos a un dominio. Para permitir esto en equipos Windows, el dispositivo debe estar registrado con Azure AD.  En este artículo se explica cómo configurar el registro automático de dispositivos.|Solo de nube|
|**Preparar el equipo de soporte técnico**. Tenga preparado un plan para los usuarios que no puedan completar MFA. Esto podría ser agregarlos a un grupo de exclusión de directivas o registrar información nueva de MFA para ellos. Antes de realizar cualquiera de estos cambios relativos a la seguridad, debe asegurarse de que el usuario real esté realizando la solicitud. Un paso eficaz es exigir a los administradores de los usuarios que ayuden con la aprobación.||
|[Configurar la escritura diferida de contraseñas en AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). La escritura diferida de contraseña permite que Azure AD requiera que los usuarios cambien su contraseña local cuando se detecte una cuenta de riesgo elevado. Puede habilitar esta característica con Azure AD Connect de una de estas dos maneras: habilitar la **escritura diferida de contraseñas** en la pantalla características opcionales del Asistente para la instalación de Azure ad Connect, o bien habilitarla a través de Windows PowerShell.|Solo de nube|
|[Configurar la protección con contraseña de Azure ad](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad). La protección de contraseñas de Azure AD detecta y bloquea las contraseñas que son conocidas por ser vulnerables y sus variantes. Además, también puede bloquear los términos vulnerables adicionales que sean específicos de su organización. Las listas de contraseñas desvetadas global predeterminada se aplican automáticamente a todos los usuarios de un inquilino de Azure AD. Se puede definir entradas adicionales en una lista personalizada de contraseñas prohibidas. Cuando los usuarios cambien o restablezcan sus contraseñas, estas listas de contraseñas prohibidas se comprueban para exigir el uso de contraseñas seguras.||
|[Habilitar Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection). La protección de identidad de Azure AD le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización y configurar una directiva de corrección automatizada para el riesgo de inicio de sesión de usuario, el riesgo de inicio de sesión en el nivel bajo, medio y alto.||
|**Habilite la autenticación moderna** para [Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) y para [Skype empresarial online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). La autenticación moderna es un requisito previo para usar MFA. La autenticación moderna está habilitada de forma predeterminada para los clientes de Office 2016 y 2019, SharePoint y OneDrive para la empresa.||
|

## <a name="recommended-client-configurations"></a>Configuraciones de cliente recomendadas

En esta sección se describen las configuraciones de cliente de la plataforma predeterminada que recomendamos proporcionar la mejor experiencia SSO a los usuarios, así como los requisitos previos técnicos para el acceso condicional.

### <a name="windows-devices"></a>Dispositivos Windows

Se recomienda Windows 10 (versión 2004 o posterior), ya que Azure está diseñado para proporcionar la experiencia de SSO más sencilla posible tanto en local como en Azure AD. Los dispositivos basados en el trabajo o la escuela deben estar configurados para unirse a Azure AD directamente o si la organización usa una Unión de dominio AD local, dichos dispositivos deben [configurarse para que se registren de forma automática y silenciosa con Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Para los dispositivos Windows de BYOD, los usuarios pueden **Agregar una cuenta profesional o educativa**. Ten en cuenta que los usuarios del explorador Google Chrome en dispositivos Windows 10 deben [instalar una extensión](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) para obtener la misma experiencia de inicio de sesión sin problemas que los usuarios de Microsoft Edge. Además, si su organización tiene dispositivos Windows 8 o 8,1 Unidos a un dominio, puede instalar Microsoft Workplace join para equipos que no sean Windows 10. [Descargue el paquete para registrar](https://www.microsoft.com/download/details.aspx?id=53554) los dispositivos con Azure ad.

### <a name="ios-devices"></a>Dispositivos iOS

Se recomienda instalar la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) en los dispositivos de usuario antes de implementar el acceso condicional o las directivas de MFA. Como mínimo, la aplicación debe instalarse cuando se solicite a los usuarios que registren su dispositivo con Azure AD agregando una cuenta profesional o educativa, o bien cuando instalen la aplicación portal de empresa de Intune para inscribir su dispositivo en la administración. Esto depende de la Directiva de acceso condicional configurada.

### <a name="android-devices"></a>dispositivos Android

Recomendamos a los usuarios que instalen la [aplicación del portal de empresa de Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) y la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de que se implementen directivas de acceso condicional o cuando sean necesarias durante determinados intentos de autenticación. Después de la instalación de la aplicación, se puede pedir a los usuarios que se registren con Azure AD o que inscriban su dispositivo con Intune. Esto depende de la Directiva de acceso condicional configurada.

También recomendamos que los dispositivos de propiedad de la organización estén estandarizados en los OEM y versiones compatibles con Android for work o Samsung Knox para permitir que las cuentas de correo, sean administradas y protegidas por la Directiva MDM de Intune.

### <a name="recommended-email-clients"></a>Clientes de correo electrónico recomendados

Los siguientes clientes de correo electrónico son compatibles con la autenticación moderna y el acceso condicional.

|Plataforma|Cliente|Versión/Notas|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Habilitar la autenticación moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) <p> [Actualizaciones necesarias](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook para iOS|[Más reciente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook para Android|[Más reciente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 y 2016|
|**Linux**|No compatible||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas para proteger documentos

Se recomiendan los siguientes clientes cuando se ha aplicado una directiva de documentos seguros.

|Plataforma|Word/Excel/PowerPoint|OneNote|Aplicación OneDrive|Aplicación SharePoint|[Cliente de sincronización de OneDrive](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|Compatible.|Compatible.|N/D|N/D|Compatible.|
|Windows 10|Compatible.|Compatible.|N/D|N/D|Compatible.|
|Android|Compatible.|Compatible.|Compatible.|Compatible.|No aplicable|
|iOS|Compatible.|Compatible.|Compatible.|Compatible.|No aplicable|
|macOS|Compatible.|Compatible.|N/D|N/D|No compatible|
|Linux|No admitido|No admitido|No admitido|No admitido|No admitido|
|

### <a name="microsoft-365-client-support"></a>Soporte técnico para el cliente de Microsoft 365

Para obtener más información acerca de la compatibilidad de clientes en Microsoft 365, consulte los siguientes artículos:

- [Compatibilidad con aplicaciones cliente de Microsoft 365-acceso condicional](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Soporte técnico de Microsoft 365 Client App-autenticación moderna](../../enterprise/microsoft-365-client-support-modern-authentication.md)

## <a name="protecting-administrator-accounts"></a>Protección de las cuentas de administrador

Para Microsoft 365 E3 o E5 o con licencias independientes de Azure AD Premium P1 o P2, puede requerir MFA para las cuentas de administrador con una directiva de acceso condicional creada manualmente. Consulte [acceso condicional: solicitar MFA a los administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) para obtener información detallada.

Para las ediciones de Microsoft 365 u Office 365 que no admiten el acceso condicional, puede habilitar los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) para requerir MFA para todas las cuentas.

Estas son algunas recomendaciones adicionales:

- Use [Azure ad privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) para reducir el número de cuentas administrativas persistentes.
- [Use la administración de acceso con privilegios](../../compliance/privileged-access-management-overview.md) para proteger su organización de las infracciones que puedan usar las cuentas de administrador con privilegios existentes con acceso permanente a los datos confidenciales o a las opciones de configuración fundamentales.
- Cree y use cuentas independientes que tengan asignados [roles de administrador de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) *solo para la administración*. Los administradores deben tener su propia cuenta de usuario para uso no administrativo normal y solo usar una cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de función o trabajo.
- Siga los [procedimientos recomendados](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para proteger las cuentas con privilegios en Azure ad.

## <a name="next-step"></a>Paso siguiente

[![Paso 2: configurar las directivas de acceso condicional de acceso y de identidad comunes](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Configurar las directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md)
