---
title: 'Trabajo de requisitos previos para implementar directivas de acceso a dispositivos e identidades: Microsoft 365 para empresas | Microsoft Docs'
description: En este artículo se describen los requisitos previos que debe cumplir para usar las directivas y configuraciones de acceso a dispositivos e identidades de confianza cero.
ms.author: dansimp
author: dansimp
manager: dansimp
ms.service: microsoft-365-security
ms.topic: conceptual
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- m365-security
- m365solution-identitydevice
- m365solution-scenario
- zerotrust-solution
- highpri
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 17f605e368f523d40aacaf7a5d301aadb7c3e27d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68624981"
---
# <a name="prerequisite-work-for-implementing-zero-trust-identity-and-device-access-policies"></a>Trabajo de requisitos previos para implementar directivas de acceso a dispositivos e identidad de confianza cero

En este artículo se describen los requisitos previos que deben cumplir los administradores para usar las directivas recomendadas de acceso a dispositivos e identidad de confianza cero, y para usar el acceso condicional. También se describen los valores predeterminados recomendados para configurar plataformas cliente para la mejor experiencia de inicio de sesión único (SSO).

## <a name="prerequisites"></a>Requisitos previos

Antes de usar las directivas de acceso a dispositivos e identidad de confianza cero que se recomiendan, la organización debe cumplir los requisitos previos. Los requisitos son diferentes para los distintos modelos de identidad y autenticación enumerados:

- Solo de nube
- Autenticación híbrida con sincronización de hash de contraseña (PHS)
- Híbrido con autenticación de paso a través (PTA)
- Federados

En la tabla siguiente se detallan las características de requisitos previos y su configuración que se aplican a todos los modelos de identidad, excepto donde se indique.

|Configuración|Excepciones|Licencias|
|---|:---:|---|
|[Configure PHS](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).  Debe estar habilitado para detectar credenciales filtradas y actuar sobre ellas para el acceso condicional basado en riesgos. **Nota:** Esto es necesario independientemente de si la organización usa la autenticación federada.|Solo de nube|Microsoft 365 E3 o E5|
|[Habilite el inicio de sesión único sin problemas](/azure/active-directory/connect/active-directory-aadconnect-sso) para que los usuarios inicien sesión automáticamente cuando estén en los dispositivos de su organización conectados a la red de la organización.|Solo en la nube y federado|Microsoft 365 E3 o E5|
|[Configurar ubicaciones con nombre](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations). Azure AD Identity Protection recopila y analiza todos los datos de sesión disponibles para generar una puntuación de riesgo. Se recomienda especificar los intervalos IP públicos de la organización para la red en la configuración de ubicaciones con nombre de Azure AD. Al tráfico procedente de estos intervalos se le asigna una puntuación de riesgo reducida y al tráfico desde fuera del entorno de la organización se le proporciona una puntuación de riesgo más alta.||Microsoft 365 E3 o E5|
|[Registre todos los usuarios para el autoservicio de restablecimiento de contraseña (SSPR) y la autenticación multifactor (MFA).](/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) Se recomienda registrar usuarios para la autenticación multifactor de Azure AD con antelación. Azure AD Identity Protection usa la autenticación multifactor de Azure AD para realizar una comprobación de seguridad adicional. Además, para obtener la mejor experiencia de inicio de sesión, se recomienda que los usuarios instalen la [aplicación Microsoft Authenticator](/azure/active-directory/user-help/microsoft-authenticator-app-how-to) y la aplicación Microsoft Portal de empresa en sus dispositivos. Se pueden instalar desde la tienda de aplicaciones para cada plataforma.||Microsoft 365 E3 o E5|
|[Habilite el registro automático de dispositivos de equipos Windows unidos a un dominio](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). El acceso condicional garantizará que los dispositivos que se conectan a las aplicaciones estén unidos a un dominio o sean compatibles. Para permitir esto en equipos Windows, el dispositivo debe estar registrado con Azure AD.  En este artículo se explica cómo configurar el registro automático de dispositivos.|Solo de nube|Microsoft 365 E3 o E5|
|**Preparar el equipo de soporte técnico**. Tenga preparado un plan para los usuarios que no puedan completar MFA. Esto podría ser agregarlos a un grupo de exclusión de directivas o registrar nueva información de MFA para ellos. Antes de realizar cualquiera de estos cambios sensibles a la seguridad, debe asegurarse de que el usuario real realiza la solicitud. Un paso eficaz es exigir a los administradores de los usuarios que ayuden con la aprobación.||Microsoft 365 E3 o E5|
|[Configurar la escritura diferida de contraseñas en AD local](/azure/active-directory/active-directory-passwords-getting-started). La escritura diferida de contraseñas permite que Azure AD requiera que los usuarios cambien sus contraseñas locales cuando se detecta un riesgo de cuenta de alto riesgo. Puede habilitar esta característica mediante Azure AD Connect de dos maneras: habilitar la **escritura diferida de contraseñas** en la pantalla de características opcionales del programa de instalación de Azure AD Connect o habilitarla a través de Windows PowerShell.|Solo de nube|Microsoft 365 E3 o E5|
|[Configuración de la protección con contraseña de Azure AD](/azure/active-directory/authentication/concept-password-ban-bad). La protección de contraseñas de Azure AD detecta y bloquea las contraseñas que son conocidas por ser vulnerables y sus variantes. Además, también puede bloquear los términos vulnerables adicionales que sean específicos de su organización. Las listas de contraseñas desvetadas global predeterminada se aplican automáticamente a todos los usuarios de un inquilino de Azure AD. Se puede definir entradas adicionales en una lista personalizada de contraseñas prohibidas. Cuando los usuarios cambien o restablezcan sus contraseñas, estas listas de contraseñas prohibidas se comprueban para exigir el uso de contraseñas seguras.||Microsoft 365 E3 o E5|
|[Habilite Azure Active Directory Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection). Azure AD Identity Protection le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización y configurar una directiva de corrección automatizada en riesgo de inicio de sesión bajo, medio y alto y riesgo de usuario.||Microsoft 365 E5 o Microsoft 365 E3 con el complemento de seguridad E5|
|**Habilite la autenticación moderna** para [Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) y para [Skype Empresarial Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). La autenticación moderna es un requisito previo para usar MFA. La autenticación moderna está habilitada de forma predeterminada para los clientes de Office 2016 y 2019, SharePoint y OneDrive para la Empresa.||Microsoft 365 E3 o E5|
|[Habilite la evaluación de acceso continuo](microsoft-365-continuous-access-evaluation.md) para Azure AD. La evaluación de acceso continua finaliza proactivamente las sesiones de usuario activas y aplica los cambios de directiva de inquilino casi en tiempo real.||Microsoft 365 E3 o E5|

## <a name="recommended-client-configurations"></a>Configuraciones de cliente recomendadas

En esta sección se describen las configuraciones de cliente de plataforma predeterminadas que se recomiendan para proporcionar la mejor experiencia de SSO a los usuarios, así como los requisitos previos técnicos para el acceso condicional.

### <a name="windows-devices"></a>Dispositivos Windows

Se recomienda Windows 11 o Windows 10 (versión 2004 o posterior), ya que Azure está diseñado para proporcionar la experiencia de SSO más fluida posible tanto en el entorno local como en Azure AD. Los dispositivos emitidos por el trabajo o la escuela deben configurarse para unirse a Azure AD directamente o si la organización usa la unión a un dominio de AD local, esos dispositivos deben [configurarse para registrarse automáticamente y de forma silenciosa en Azure AD](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

En el caso de los dispositivos Windows BYOD, los usuarios pueden usar **Agregar cuenta profesional o educativa**. Tenga en cuenta que los usuarios del explorador Google Chrome en dispositivos Windows 11 o Windows 10 necesitan [instalar una extensión](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) para obtener la misma experiencia de inicio de sesión fluida que los usuarios de Microsoft Edge. Además, si su organización tiene dispositivos Windows 8 o 8.1 unidos a un dominio, puede instalar Microsoft Workplace Join para equipos que no sean Windows 10. [Descargue el paquete para registrar](https://www.microsoft.com/download/details.aspx?id=53554) los dispositivos con Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS

Se recomienda instalar la [aplicación Microsoft Authenticator](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) en dispositivos de usuario antes de implementar directivas de MFA o acceso condicional. Como mínimo, la aplicación debe instalarse cuando se pida a los usuarios que registren su dispositivo en Azure AD agregando una cuenta profesional o educativa, o cuando instalen la aplicación del portal de empresa Intune para inscribir su dispositivo en la administración. Esto depende de la directiva de acceso condicional configurada.

### <a name="android-devices"></a>dispositivos Android

Se recomienda que los usuarios instalen la [aplicación Portal de empresa de Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) y la [aplicación Microsoft Authenticator](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de implementar las directivas de acceso condicional o cuando sea necesario durante determinados intentos de autenticación. Después de la instalación de la aplicación, se puede pedir a los usuarios que se registren con Azure AD o que inscriban su dispositivo con Intune. Esto depende de la directiva de acceso condicional configurada.

También se recomienda que los dispositivos propiedad de la organización estén estandarizados en oemes y versiones compatibles con Android for Work o Samsung Knox para permitir cuentas de correo, administrarse y protegerse mediante Intune directiva MDM.

### <a name="recommended-email-clients"></a>Clientes de correo electrónico recomendados

Los siguientes clientes de correo electrónico admiten la autenticación moderna y el acceso condicional.

|Plataforma|Cliente|Versión/Notas|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Habilitación de la autenticación moderna](../../admin/security-and-compliance/enable-modern-authentication.md) <p> [Actualizaciones necesarias](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook para iOS|[Más reciente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook para Android|[Más reciente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 y 2016|
|**Linux**|No compatible||

### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas para proteger documentos

Se recomiendan los siguientes clientes cuando se ha aplicado una directiva de documentos seguros.

|Plataforma|Word/Excel/PowerPoint|OneNote|Aplicación OneDrive|Aplicación SharePoint|[Cliente de sincronización de OneDrive](/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 11 o Windows 10|Compatible|Compatible.|No aplicable|N/D|Compatible|
|Windows 8.1|Compatible.|Compatible.|No aplicable|N/D|Compatible|
|Android|Compatible.|Compatible|Compatible|Compatible.|No aplicable|
|iOS|Compatible.|Compatible|Compatible|Compatible.|No aplicable|
|macOS|Compatible|Compatible.|No aplicable|No aplicable|No compatible|
|Linux|No compatible|No compatible|No compatible|No compatible|No compatible|

### <a name="microsoft-365-client-support"></a>Soporte técnico para el cliente de Microsoft 365

Para obtener más información sobre la compatibilidad con clientes en Microsoft 365, consulte los artículos siguientes:

- [Compatibilidad con aplicaciones cliente de Microsoft 365: acceso condicional](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Compatibilidad con aplicaciones cliente de Microsoft 365: autenticación multifactor](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>Protección de cuentas de administrador

Para Microsoft 365 E3 o E5 o con licencias de Azure AD Premium P1 o P2 independientes, puede requerir MFA para las cuentas de administrador con una directiva de acceso condicional creada manualmente. Consulte [Acceso condicional: Requerir MFA para los administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) para obtener los detalles.

Para las ediciones de Microsoft 365 o Office 365 que no admiten el acceso condicional, puede habilitar [los valores predeterminados de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) para requerir MFA para todas las cuentas.

Estas son algunas recomendaciones adicionales:

- Use [Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-getting-started) para reducir el número de cuentas administrativas persistentes.
- [Use la administración de acceso con privilegios](../../compliance/privileged-access-management-overview.md) para proteger su organización frente a infracciones que pueden usar cuentas de administrador con privilegios existentes con acceso permanente a datos confidenciales o acceso a configuraciones críticas.
- Cree y use cuentas independientes a las que se asignen [roles de administrador de Microsoft 365](../../admin/add-users/about-admin-roles.md) *solo para la administración*. Los administradores deben tener su propia cuenta de usuario para un uso no administrativo normal y solo usar una cuenta administrativa cuando sea necesario para completar una tarea asociada a su rol o función de trabajo.
- Siga [los procedimientos recomendados](/azure/active-directory/admin-roles-best-practices) para proteger cuentas con privilegios en Azure AD.

## <a name="next-step"></a>Paso siguiente

[![Paso 2: Configurar las directivas comunes de acceso condicional de identidad y acceso de confianza cero.](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png#lightbox)](identity-access-policies.md)

[Configuración de las directivas comunes de acceso a dispositivos e identidad de confianza cero](identity-access-policies.md)
