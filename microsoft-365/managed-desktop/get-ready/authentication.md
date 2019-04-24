---
title: Preparar el acceso a los recursos locales para el escritorio administrado por Microsoft
description: Pasos importantes para asegurarse de que Azure AD pueda comunicarse con AD local para proporcionar autenticación
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c4ebe0c7ad3d1e197cf90cc975366df61d3b0cb5
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276921"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Preparar el acceso a los recursos locales para el escritorio administrado por Microsoft

En el escritorio administrado de Microsoft, los dispositivos se unen automáticamente a Azure Active Directory (Azure AD). Esto significa que si usa un Active Directory local, tendrá que comprobar algunas cosas para asegurarse de que los dispositivos Unidos a Azure AD puedan comunicarse con su Active Directory local. 

> [!NOTE]  
> *Entorno híbrido* El escritorio administrado de Microsoft no admite Azure AD join.

Azure Active Directory permite a los usuarios aprovechar el inicio de sesión único (SSO), lo que significa que, por lo general, no tendrá que proporcionar credenciales cada vez que usen recursos.

Para obtener información sobre cómo unirse a Azure Active Directory, consulte [How to: Plan Your Azure ad join Implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Para obtener información general sobre el inicio de sesión único (SSO) en dispositivos Unidos a Azure AD, vea [Cómo SSO a los recursos locales funciona en dispositivos Unidos a Azure ad](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


En este tema se explican las cosas que debe comprobar para asegurarse de que las aplicaciones y otros recursos que dependen de la conectividad local de Active Directory funcionarán sin problemas con el escritorio administrado de Microsoft.


## <a name="single-sign-on-for-on-premises-resources"></a>Inicio de sesión único para recursos locales

El inicio de sesión único (SSO) mediante UPN y la contraseña están habilitados de forma predeterminada en los dispositivos de escritorio administrados por Microsoft. Pero los usuarios también pueden usar Windows Hello para empresas, que requiere algunos pasos de configuración adicionales. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Inicio de sesión único con UPN y contraseña

En la mayoría de las organizaciones, los usuarios podrán usar SSO para autenticar por UPN y contraseña en dispositivos de escritorio administrados por Microsoft. Sin embargo, para asegurarse de que funcione correctamente, debe comprobar lo siguiente:

- Confirme que Azure AD Connect está configurado y usa un servidor local de Active Directory que ejecuta Windows Server 2008 R2 o versiones posteriores.
- Confirme que Azure AD Connect se ejecuta en una versión compatible y está configurado para sincronizar estos tres atributos con Azure AD: 
    - Nombre de dominio DNS de Active Directory local (donde se encuentran los usuarios finales)
    - NetBIOS de su Active Directory local (donde se encuentran los usuarios finales)
    - Nombre de cuenta SAM del usuario


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Inicio de sesión único con Windows Hello para empresas

Los dispositivos de escritorio administrados por Microsoft también ofrecen a los usuarios una experiencia rápida y no con contraseñas al usar Windows Hello para empresas. Para garantizar que Windows Hello para empresas funcione sin que los usuarios tengan que proporcionar el UPN y la contraseña respectivos, visita [configurar los dispositivos Unidos a Azure ad para el inicio de sesión único local con Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) para comprobar los requisitos y, a continuación, Siga los pasos que se indican allí.


## <a name="apps-and-resources-that-use-authentication"></a>Aplicaciones y recursos que usan la autenticación

Consulte [comprender las consideraciones de aplicaciones y recursos](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) en el conjunto de contenido de Azure para obtener instrucciones completas sobre cómo configurar las aplicaciones para que funcionen con Azure Active Directory. En Resumen:


- Si usa **aplicaciones basadas en la nube**, como las que se agregan a la galería de aplicaciones de Azure ad, la mayoría no necesitará más preparación para trabajar con el escritorio administrado de Microsoft. Sin embargo, cualquier aplicación Win32 que no use el administrador de cuentas web (WAM) podría seguir solicitando a los usuarios la autenticación.

- Para las aplicaciones **hospedadas localmente**, asegúrese de agregar esas aplicaciones a la lista de sitios de confianza en sus exploradores. Esto permitirá que la autenticación de Windows funcione sin problemas, sin que se soliciten las credenciales a los usuarios. Para ello, consulte sitios de [confianza](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) en la [referencia configurable Settings](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).

- Si usa los servicios federados de Active Directory, compruebe que el SSO esté habilitado mediante los pasos de [Verify and Manage Single Sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Para las aplicaciones que son **locales y usan protocolos más antiguos**, no se necesita ninguna configuración adicional, siempre y cuando los dispositivos tengan acceso a un controlador de dominio local para autenticarse. Sin embargo, para proporcionar acceso seguro a estas aplicaciones, debe implementar el proxy de aplicación de Azure AD. Para obtener más información, vea [acceso remoto a aplicaciones locales a través del proxy de aplicación de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Las aplicaciones que se ejecutan **de forma local y dependen de la autenticación del equipo** no son compatibles, por lo que se recomienda reemplazarlas por versiones más recientes.

### <a name="network-shares-that-use-authentication"></a>Recursos compartidos de red que usan autenticación

No es necesario realizar ninguna configuración adicional para que los usuarios tengan acceso a recursos compartidos de red, siempre que los dispositivos tengan acceso a un controlador de dominio local mediante una ruta UNC.

### <a name="printers"></a>Impresoras

Los dispositivos de escritorio administrados por Microsoft no se pueden conectar a impresoras publicadas en Active Directory local a menos que haya configurado [la nube híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).

Aunque las impresoras no se detectan automáticamente en un entorno solo de nube, los usuarios pueden usar las impresoras locales con la ruta de la impresora o la ruta de la cola de impresión, siempre que los dispositivos tengan acceso a un controlador de dominio local.

<!--add fuller material on printers when available-->
