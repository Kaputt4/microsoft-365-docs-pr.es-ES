---
title: 'Trabajo de requisitos previos para implementar directivas de acceso a dispositivos e identidades: Microsoft 365 para empresas | Microsoft Docs'
description: En este artículo se describen los requisitos previos que debe cumplir para usar configuraciones y directivas de acceso a dispositivos e identidades.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
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
ms.technology: mdo
ms.openlocfilehash: 53d64d869b80c6fe5c6e0954a00af5b6f5359356
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233091"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Trabajo de requisitos previos para implementar directivas de acceso a dispositivos e identidades

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- Azure

En este artículo se describen los requisitos previos que los administradores deben cumplir para usar directivas recomendadas de acceso a dispositivos e identidades, y para usar el acceso condicional. También se analizan los valores predeterminados recomendados para configurar plataformas cliente para la mejor experiencia de inicio de sesión único (SSO).

## <a name="prerequisites"></a>Requisitos previos

Antes de usar las directivas de acceso a dispositivos e identidades que se recomiendan, la organización debe cumplir los requisitos previos. Los requisitos son diferentes para los distintos modelos de identidad y autenticación enumerados:

- Solo de nube
- Híbrido con autenticación de sincronización de hash de contraseña (PHS)
- Híbrido con autenticación de paso a través (PTA)
- Federado

En la tabla siguiente se detallan las características de requisitos previos y su configuración que se aplican a todos los modelos de identidad, excepto cuando se indica.

|Configuración|Exceptions|
|---|:---:|
|[Configurar PHS](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).  Esto debe habilitarse para detectar credenciales filtradas y actuar en ellas para el acceso condicional basado en riesgos. **Nota:** Esto es necesario independientemente de si su organización usa la autenticación federada.|Solo de nube|
|[Habilitar el inicio de sesión único sin](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) problemas para iniciar sesión automáticamente a los usuarios cuando se encuentran en sus dispositivos de la organización conectados a la red de la organización.|Solo en la nube y federada|
|[Configurar ubicaciones con nombre.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) Azure AD Identity Protection recopila y analiza todos los datos de sesión disponibles para generar una puntuación de riesgo. Se recomienda especificar los intervalos IP públicos de la organización para la red en la configuración de ubicaciones con nombre de Azure AD. El tráfico procedente de estos intervalos tiene una puntuación de riesgo reducida y el tráfico de fuera del entorno de la organización tiene una puntuación de riesgo más alta.||
|[Registre todos los usuarios para el restablecimiento de contraseña de autoservicio (SSPR) y la autenticación multifactor (MFA).](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) Te recomendamos que registres usuarios para Azure AD Multi-Factor Authentication con antelación. Azure AD Identity Protection usa Azure AD Multi-Factor Authentication para realizar comprobaciones de seguridad adicionales. Además, para obtener la mejor experiencia de inicio de sesión, se recomienda que los usuarios instalen la aplicación [Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) y la aplicación Portal de empresa de Microsoft en sus dispositivos. Estos se pueden instalar desde la tienda de aplicaciones para cada plataforma.||
|[Habilitar el registro automático de dispositivos de equipos Windows unidos a un dominio.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup) El acceso condicional garantizará que los dispositivos que se conectan a las aplicaciones estén unidos a un dominio o sean compatibles. Para permitir esto en equipos Windows, el dispositivo debe estar registrado con Azure AD.  En este artículo se explica cómo configurar el registro automático de dispositivos.|Solo de nube|
|**Preparar el equipo de soporte técnico**. Tenga preparado un plan para los usuarios que no puedan completar MFA. Esto podría ser agregarlos a un grupo de exclusión de directivas o registrar nueva información de MFA para ellos. Antes de realizar cualquiera de estos cambios confidenciales de seguridad, debe asegurarse de que el usuario real realiza la solicitud. Un paso eficaz es exigir a los administradores de los usuarios que ayuden con la aprobación.||
|[Configurar la escritura diferida de contraseñas en AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). La escritura reescribición de contraseñas permite a Azure AD requerir que los usuarios cambien sus contraseñas locales cuando se detecta un riesgo de cuenta de alto riesgo. Puede habilitar esta característica con Azure AD Connect de  una de estas dos maneras: habilitar la escritura escritura ante contraseñas en la pantalla de características opcionales del Asistente para la instalación de Azure AD Connect o habilitarla a través de Windows PowerShell.|Solo de nube|
|[Configurar la protección con contraseña de Azure AD.](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) La protección de contraseñas de Azure AD detecta y bloquea las contraseñas que son conocidas por ser vulnerables y sus variantes. Además, también puede bloquear los términos vulnerables adicionales que sean específicos de su organización. Las listas de contraseñas desvetadas global predeterminada se aplican automáticamente a todos los usuarios de un inquilino de Azure AD. Se puede definir entradas adicionales en una lista personalizada de contraseñas prohibidas. Cuando los usuarios cambien o restablezcan sus contraseñas, estas listas de contraseñas prohibidas se comprueban para exigir el uso de contraseñas seguras.||
|[Habilite Azure Active Directory Identity Protection.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection) Azure AD Identity Protection le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización y configurar una directiva de corrección automatizada a riesgo de inicio de sesión bajo, medio y alto y riesgo de usuario.||
|**Habilite la autenticación** moderna [para Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) y para Skype Empresarial [Online.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) La autenticación moderna es un requisito previo para usar MFA. La autenticación moderna está habilitada de forma predeterminada para los clientes de Office 2016 y 2019, SharePoint y OneDrive para la Empresa.||
|

## <a name="recommended-client-configurations"></a>Configuraciones de cliente recomendadas

En esta sección se describen las configuraciones de cliente de plataforma predeterminadas que se recomiendan para proporcionar la mejor experiencia de SSO a los usuarios, así como los requisitos previos técnicos para el acceso condicional.

### <a name="windows-devices"></a>Dispositivos Windows

Recomendamos Windows 10 (versión 2004 o posterior), ya que Azure está diseñado para proporcionar la experiencia de SSO más fluida posible tanto para el entorno local como para Azure AD. Los dispositivos emitidos por el trabajo o la escuela deben configurarse para unirse a Azure AD directamente o si la organización usa la unión a un dominio local de AD, esos dispositivos deben configurarse para registrarse automáticamente y de forma silenciosa con [Azure AD.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

Para dispositivos WINDOWS BYOD, los usuarios pueden usar **Agregar cuenta de trabajo o escuela.** Ten en cuenta que los usuarios del explorador [](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) Google Chrome en dispositivos Windows 10 necesitan instalar una extensión para obtener la misma experiencia de inicio de sesión sin problemas que los usuarios de Microsoft Edge. Además, si tu organización tiene dispositivos Windows 8 o 8.1 unidos a un dominio, puedes instalar Microsoft Workplace Join para equipos que no son windows 10. [Descarga el paquete para registrar los](https://www.microsoft.com/download/details.aspx?id=53554) dispositivos con Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS

Se recomienda instalar la aplicación [Microsoft Authenticator en](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) dispositivos de usuario antes de implementar directivas de ACCESO condicional o MFA. Como mínimo, la aplicación debe instalarse cuando se pida a los usuarios que registren su dispositivo con Azure AD agregando una cuenta de trabajo o educativa, o cuando instalen la aplicación portal de empresa de Intune para inscribir su dispositivo en la administración. Esto depende de la directiva de acceso condicional configurada.

### <a name="android-devices"></a>dispositivos Android

Se recomienda que los usuarios instalen la aplicación Portal de empresa de [Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) y la aplicación [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de implementar directivas de acceso condicional o cuando sea necesario durante determinados intentos de autenticación. Después de la instalación de la aplicación, se puede pedir a los usuarios que se registren con Azure AD o que inscriban su dispositivo con Intune. Esto depende de la directiva de acceso condicional configurada.

También recomendamos que los dispositivos propiedad de la organización estén estandarizados en OEM y versiones compatibles con Android for Work o Samsung Knox para permitir que las cuentas de correo se administren y se protegerán mediante la directiva MDM de Intune.

### <a name="recommended-email-clients"></a>Clientes de correo electrónico recomendados

Los siguientes clientes de correo electrónico admiten la autenticación moderna y el acceso condicional.

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
|Windows 8.1|Compatible|Compatible|N/D|N/D|Compatible|
|Windows 10|Compatible|Compatible|N/D|N/D|Compatible|
|Android|Compatible|Compatible|Compatible|Compatible|No aplicable|
|iOS|Compatible|Compatible|Compatible|Compatible|No aplicable|
|macOS|Compatible|Compatible|N/D|N/D|No compatible|
|Linux|No admitido|No admitido|No admitido|No admitido|No admitido|
|

### <a name="microsoft-365-client-support"></a>Soporte técnico para el cliente de Microsoft 365

Para obtener más información acerca de la compatibilidad con clientes en Microsoft 365, vea los siguientes artículos:

- [Compatibilidad con aplicaciones cliente de Microsoft 365: acceso condicional](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Compatibilidad con aplicaciones cliente de Microsoft 365: autenticación multifactor](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>Protección de cuentas de administrador

Para Microsoft 365 E3 o E5 o con licencias de Azure AD Premium P1 o P2 independientes, puede requerir MFA para cuentas de administrador con una directiva de acceso condicional creada manualmente. Consulta [Acceso condicional: requerir MFA para los administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) para obtener más información.

Para las ediciones de Microsoft 365 u Office 365 que [](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) no admiten el acceso condicional, puede habilitar los valores predeterminados de seguridad para requerir MFA para todas las cuentas.

Estas son algunas recomendaciones adicionales:

- Use [Azure AD Privileged Identity Management para](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) reducir el número de cuentas administrativas persistentes.
- [Use la administración de acceso](../../compliance/privileged-access-management-overview.md) con privilegios para proteger su organización de infracciones que pueden usar cuentas de administrador con privilegios existentes con acceso permanente a datos confidenciales o acceso a opciones de configuración críticas.
- Cree y use cuentas independientes a las que se asignan roles de [administrador de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) *solo para la administración.* Los administradores deben tener su propia cuenta de usuario para uso no administrativo normal y usar solo una cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de rol o trabajo.
- Siga [los procedimientos recomendados](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para proteger cuentas con privilegios en Azure AD.

## <a name="next-step"></a>Paso siguiente

[![Paso 2: Configurar las directivas comunes de acceso y identidad de acceso condicional](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Configurar las directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md)
