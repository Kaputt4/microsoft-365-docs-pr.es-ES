---
title: Preparar el acceso a los recursos locales para el escritorio administrado por Microsoft
description: Pasos importantes para asegurarse de que Azure AD pueda comunicarse con AD local para proporcionar autenticación
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0f9cbe6712b8d16f435cfdf5fd84875656fa9c2e
ms.sourcegitcommit: ef589025820ddf6edb5f454826b1c12c9bcb8e49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "31824470"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Preparar el acceso a los recursos locales para el escritorio administrado por Microsoft

En el escritorio administrado de Microsoft, los dispositivos se unen automáticamente a Azure Active Directory. Esto significa que si usa un Active Directory local, tendrá que comprobar algunas cosas para asegurarse de que los dispositivos Unidos a Azure AD puedan comunicarse con su Active Directory local. 

> [!NOTE]  
> *Entorno híbrido* El escritorio administrado de Microsoft no admite Azure AD join.

Azure Active Directory permite a los usuarios aprovechar el inicio de sesión único (SSO), lo que significa que, por lo general, no tendrá que proporcionar credenciales cada vez que quieran hacer algo. Si no está completamente familiarizado con Azure Active Directory, consulte [How to: Plan Your Azure ad join](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan), sin embargo, a medida que haga referencia a la documentación de Azure Active Directory, tenga en cuenta que Microsoft Azure ad join *híbrido* no es compatible con Microsoft Escritorio administrado.


En este tema se explican las cosas que debe comprobar para asegurarse de que las aplicaciones y otros recursos que dependen de la conectividad local de Active Directory funcionarán sin problemas con el escritorio administrado de Microsoft.


> [!IMPORTANT]  
> Para que los usuarios puedan registrar dispositivos en Azure Active Directory e inscribirse en Intune (necesario para el escritorio administrado de Microsoft), siga los pasos de [configurar la configuración del dispositivo](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) antes de continuar con el resto de este tema.


## <a name="single-sign-on-for-on-premises-resources"></a>Inicio de sesión único para recursos locales

El inicio de sesión único (SSO) para los dispositivos mediante el uso de UPN o contraseñas (el método predeterminado) ya debe funcionar de forma predeterminada. Pero también puede usar Windows Hello para empresas, que requiere algunos pasos de configuración adicionales. Para obtener información general sobre SSO, vea [Cómo funciona SSO con los recursos locales en dispositivos Unidos a Azure ad](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


### <a name="single-sign-on-by-using-upn-and-passwords"></a>Inicio de sesión único con UPN y contraseñas

No es necesario realizar ninguna configuración especial para que los usuarios se autentiquen por UPN y contraseña, ya que esto se obtiene de forma predeterminada desde Azure. Sin embargo, para asegurarse de que funcione correctamente, debe comprobar lo siguiente:

- Confirme que Azure Active Directory (AAD) Connect se configura con un servidor local de Active Directory que ejecuta Windows Server 2008 R2 o versiones posteriores.
- AAD Connect se está ejecutando en una versión compatible y está configurada para sincronizar estos tres atributos clave con Azure AD: 
    - Nombre de dominio DNS en el que el usuario está presente en su implementación local de Active Directory
    - Nombre de dominio NetBIOS donde el usuario está presente en su Active Directory local
    - Nombre de cuenta SAM del usuario


### <a name="sso-by-using-windows-hello-for-business"></a>SSO mediante Windows Hello para empresas

Como alternativa, puede ofrecer a los usuarios una experiencia rápida y no con contraseñas si emplea Windows Hello para empresas. Para configurar esto, visite [configurar los dispositivos Unidos de Azure ad para el inicio de sesión único local con Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) para comprobar los requisitos y, a continuación, siga los pasos que se indican.


## <a name="apps-and-resources-that-use-authentication"></a>Aplicaciones y recursos que usan la autenticación

Consulte [comprender las consideraciones de aplicaciones y recursos](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) en el conjunto de contenido de Azure para obtener instrucciones completas sobre cómo configurar las aplicaciones para que funcionen con Azure Active Directory. En Resumen:


- Si usa **aplicaciones basadas en la nube**, como las que se agregan a la galería de aplicaciones de Azure ad, la mayoría no necesitará más preparación para trabajar con el escritorio administrado de Microsoft. Sin embargo, cualquier aplicación Win32 que no use el administrador de cuentas web (WAM) {Compruebe este acrónimo} podría seguir solicitando a los usuarios la autenticación.

- Para las aplicaciones **hospedadas localmente**, asegúrese de agregar esas aplicaciones a la lista de sitios de confianza en sus exploradores. Esto permitirá que la autenticación de Windows funcione sin problemas, sin que se soliciten las credenciales a los usuarios.

- Si usa los servicios federados de Active Directory, siga los pasos descritos en [Verify and Manage Single Sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Para las aplicaciones que son **locales y usan protocolos más antiguos**, no se necesita ninguna configuración adicional, siempre y cuando los dispositivos tengan acceso a un controlador de dominio local. Sin embargo, para proporcionar acceso seguro a estas aplicaciones, debe implementar el proxy de aplicación de Azure AD. Para obtener más información, vea [acceso remoto a aplicaciones locales a través del proxy de aplicación de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Las aplicaciones que se ejecutan **de forma local y dependen de la autenticación del equipo** no son compatibles, por lo que se recomienda reemplazarlas por versiones más recientes.

## <a name="network-shares-that-use-authentication"></a>Recursos compartidos de red que usan autenticación

No es necesario realizar ninguna configuración adicional para que los usuarios tengan acceso a recursos compartidos de red, siempre que los dispositivos tengan acceso a un controlador de dominio local mediante una ruta UNC.

## <a name="printers"></a>Impresoras

Aunque las impresoras no se detectan automáticamente en un entorno solo de nube, los usuarios también pueden usar la ruta UNC de la impresora para agregarlas directamente.

<!--add fuller material on printers when available-->