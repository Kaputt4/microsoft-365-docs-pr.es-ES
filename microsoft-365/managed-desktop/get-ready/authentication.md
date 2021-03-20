---
title: Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft
description: Pasos importantes para asegurarse de que Azure AD se puede comunicar con AD local para proporcionar autenticación
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f6b1e257fd767fa112fddb41d773065b8002a2a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909195"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft

En Microsoft Managed Desktop, los dispositivos se unen automáticamente a Azure Active Directory (Azure AD). Por este motivo, si usa un Active Directory local, tendrá que comprobar algunas cosas para asegurarse de que los dispositivos unidos a Azure AD puedan comunicarse con su Active Directory local. 

> [!NOTE]  
> *Híbrido* La unión a Azure AD no es compatible con Microsoft Managed Desktop.

Azure Active Directory permite a los usuarios aprovechar el single Sign-On (SSO), lo que significa que normalmente no tendrán que proporcionar credenciales cada vez que usen recursos.

Para obtener información sobre cómo unirse a Azure Active Directory, consulte [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan). Para obtener información en segundo plano sobre single Sign-On (SSO) en dispositivos unidos a Azure AD, consulte [How SSO to on-premises resources works on Azure AD joined devices](/azure/active-directory/devices/azuread-join-sso#how-it-works).


En este artículo se explican las cosas que debe comprobar para asegurarse de que las aplicaciones y otros recursos que dependen de la conectividad local de Active Directory funcionarán sin problemas con El escritorio administrado de Microsoft.


## <a name="single-sign-on-for-on-premises-resources"></a>Single Sign-On para recursos locales

El Sign-On (SSO) mediante UPN y contraseña está habilitado de forma predeterminada en dispositivos de escritorio administrados de Microsoft. Pero los usuarios también pueden usar Windows Hello para empresas, lo que requiere algunos pasos de configuración adicionales. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Single Sign-On mediante UPN y contraseña

En la mayoría de las organizaciones, los usuarios podrán usar SSO para autenticarse mediante UPN y contraseña en dispositivos de escritorio administrados de Microsoft. Sin embargo, para asegurarse de que esta función funcionará, debe comprobar dos veces lo siguiente:

- Confirme que Azure AD Connect está configurado y usa un servidor de Active Directory local que ejecute Windows Server 2008 R2 o posterior.
- Confirme que Azure AD Connect ejecuta una versión compatible y está configurado para sincronizar estos tres atributos con Azure AD: 
    - Nombre de dominio DNS del Active Directory local (donde se encuentran los usuarios)
    - NetBIOS de su Active Directory local (donde se encuentran los usuarios)
    - Nombre de cuenta SAM del usuario


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Single Sign-On mediante Windows Hello para empresas

Los dispositivos de Escritorio administrado de Microsoft también ofrecen a los usuarios una experiencia rápida y sin contraseña al usar Windows Hello para empresas. Para asegurarse de que Windows Hello para empresas funcionará sin que los usuarios tengan que proporcionar el UPN y la contraseña correspondientes, visite Configurar dispositivos unidos a Azure AD para el Single-Sign Local Al usar [Windows Hello para](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) empresas para comprobar los requisitos y, a continuación, siga los pasos proporcionados allí.


## <a name="apps-and-resources-that-use-authentication"></a>Aplicaciones y recursos que usan la autenticación

Consulte [Understand considerations for applications and resources](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set para obtener instrucciones detalladas sobre cómo configurar aplicaciones para que funcionen con Azure Active Directory. En resumen:


- Si usa aplicaciones **basadas** en la nube, como las agregadas a la galería de aplicaciones de Azure AD, la mayoría no requiere ninguna preparación adicional para trabajar con Microsoft Managed Desktop. Sin embargo, las aplicaciones de Win32 que no usen el Administrador de cuentas web (WAM) podrían pedir autenticación a los usuarios.

- Para las aplicaciones **hospedadas localmente,** asegúrese de agregar esas aplicaciones a la lista de sitios de confianza en los exploradores. Este paso permitirá que la autenticación de Windows funcione sin problemas, sin que se pidan credenciales a los usuarios. Para agregar aplicaciones, consulte [Sitios de confianza en](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) la referencia configuración [configurable](../working-with-managed-desktop/config-setting-ref.md).

- Si usa Servicios federados de Active Directory, compruebe que SSO está habilitado mediante los pasos descritos en Comprobar y administrar el inicio de sesión único [con AD FS](/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Para las aplicaciones que son locales y usan **protocolos antiguos,** no se requiere ninguna configuración adicional, siempre que los dispositivos tengan acceso a un controlador de dominio local para autenticarse. Sin embargo, para proporcionar acceso seguro a estas aplicaciones, debe implementar el proxy de aplicación de Azure AD. Para obtener más información, vea Acceso remoto a aplicaciones locales a través del proxy de [aplicación de Azure Active Directory](/azure/active-directory/manage-apps/application-proxy).

- Las aplicaciones que se **ejecutan localmente y dependen** de la autenticación de máquina no son compatibles, por lo que deberías considerar reemplazarlas por versiones más recientes.

### <a name="network-shares-that-use-authentication"></a>Recursos compartidos de red que usan autenticación

No se requiere ninguna configuración adicional para que los usuarios tengan acceso a recursos compartidos de red, siempre y cuando los dispositivos tengan acceso a un controlador de dominio local mediante una ruta de acceso UNC.

### <a name="printers"></a>Impresoras

Los dispositivos de Escritorio administrado de Microsoft no pueden conectarse a impresoras que se publican en su Active Directory local a menos que haya configurado [Hybrid Cloud Print](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).

Aunque las impresoras no se pueden detectar automáticamente en un entorno de solo nube, los usuarios pueden usar impresoras locales mediante la ruta de acceso de la impresora o la ruta de cola de la impresora, siempre que los dispositivos tengan acceso a un controlador de dominio local.

<!--add fuller material on printers when available-->