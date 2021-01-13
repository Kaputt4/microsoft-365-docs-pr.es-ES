---
title: Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft
description: Pasos importantes para asegurarse de que Azure AD puede comunicarse con AD local para proporcionar autenticación
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c1732dc17188427f9a181d1c47abe71bb8f39584
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841416"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft

En el Escritorio administrado de Microsoft, los dispositivos se unen automáticamente a Azure Active Directory (Azure AD). Por este motivo, si usa un Active Directory local, tendrá que comprobar algunas cosas para asegurarse de que los dispositivos unidos a Azure AD se puedan comunicar con su Active Directory local. 

> [!NOTE]  
> *Híbrido* La unión a Azure AD no es compatible con el Escritorio administrado de Microsoft.

Azure Active Directory permite a los usuarios aprovechar las ventajas del Sign-On único (SSO), lo que significa que normalmente no tendrán que proporcionar credenciales cada vez que usen recursos.

Para obtener información sobre cómo unirse a Azure Active Directory, consulte [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Para obtener información general sobre Sign-On de inicio de sesión único (SSO) en dispositivos unidos a Azure AD, vea cómo funciona el SSO en recursos locales en dispositivos unidos a [Azure AD.](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)


En este artículo se explican los aspectos que debe comprobar para asegurarse de que las aplicaciones y otros recursos que dependen de la conectividad local de Active Directory funcionarán sin problemas con el Escritorio administrado de Microsoft.


## <a name="single-sign-on-for-on-premises-resources"></a>Único Sign-On para recursos locales

Single Sign-On (SSO) by using UPN and password is enabled by default on Microsoft Managed Desktop Devices. Pero los usuarios también pueden usar Windows Hello para empresas, lo que requiere algunos pasos de configuración adicionales. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Configuración Sign-On con UPN y contraseña

En la mayoría de las organizaciones, los usuarios podrán usar SSO para autenticarse mediante UPN y contraseña en dispositivos de escritorio administrados de Microsoft. Sin embargo, para asegurarse de que esta función funcione, debe comprobar dos veces lo siguiente:

- Confirme que Azure AD Connect está configurado y usa un servidor de Active Directory local que ejecute Windows Server 2008 R2 o posterior.
- Confirma que Azure AD Connect ejecuta una versión compatible y está configurado para sincronizar estos tres atributos con Azure AD: 
    - Nombre de dominio DNS del Active Directory local (donde se encuentran los usuarios)
    - NetBIOS del Active Directory local (donde se encuentran los usuarios)
    - Nombre de cuenta SAM del usuario


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Single Sign-On by using Windows Hello for Business

Los dispositivos de Escritorio administrado de Microsoft también ofrecen a los usuarios una experiencia rápida y sin contraseñas mediante el uso de Windows Hello para empresas. Para asegurarte de que Windows Hello para empresas funcionará sin que los usuarios tengan que proporcionar el UPN y la contraseña respectivos, visita Configurar dispositivos unidos a Azure AD para Single-Sign En el uso de [Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) para empresas para comprobar los requisitos y, a continuación, sigue los pasos proporcionados allí.


## <a name="apps-and-resources-that-use-authentication"></a>Aplicaciones y recursos que usan la autenticación

Consulte Comprender [las consideraciones para aplicaciones y](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) recursos en el conjunto de contenido de Azure para obtener instrucciones detalladas sobre cómo configurar aplicaciones para que funcionen con Azure Active Directory. En resumen:


- Si **usas** aplicaciones basadas en la nube, como las que se agregan a la galería de aplicaciones de Azure AD, la mayoría no requieren ninguna preparación adicional para trabajar con escritorio administrado de Microsoft. Sin embargo, cualquier aplicación de Win32 que no use el Administrador de cuentas web (WAM) puede pedir autenticación a los usuarios.

- Para las aplicaciones **hospedadas localmente,** asegúrese de agregar esas aplicaciones a la lista de sitios de confianza en los exploradores. Este paso permitirá que la autenticación de Windows funcione sin problemas, sin que se pidan credenciales a los usuarios. Para agregar aplicaciones, consulte Sitios [de confianza en](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) la referencia de configuración [configurable.](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)

- Si usa servicios federados de Active Directory, compruebe que SSO esté habilitado mediante los pasos descritos en Comprobar y administrar el inicio de sesión único [con AD FS.](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)) 

- Para las aplicaciones que son locales y usan protocolos más **antiguos,** no se requiere ninguna configuración adicional, siempre y cuando los dispositivos tengan acceso a un controlador de dominio local para autenticarse. Sin embargo, para proporcionar acceso seguro a estas aplicaciones, debes implementar Azure AD Application Proxy. Para obtener más información, vea Acceso remoto a aplicaciones locales a través del Proxy de aplicación [de Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)

- Las aplicaciones que **se ejecutan localmente y dependen** de la autenticación del equipo no son compatibles, por lo que debes considerar reemplazarlas por versiones más recientes.

### <a name="network-shares-that-use-authentication"></a>Recursos compartidos de red que usan autenticación

No se requiere ninguna configuración adicional para que los usuarios tengan acceso a recursos compartidos de red, siempre y cuando los dispositivos tengan acceso a un controlador de dominio local mediante una ruta de acceso UNC.

### <a name="printers"></a>Impresoras

Los dispositivos de escritorio administrado de Microsoft no pueden conectarse a impresoras que se publican en active directory local a menos que haya configurado [la impresión en la nube híbrida.](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)

Aunque las impresoras no se pueden detectar automáticamente en un entorno de solo nube, los usuarios pueden usar impresoras locales mediante la ruta de impresora o la ruta de la cola de impresora, siempre y cuando los dispositivos tengan acceso a un controlador de dominio local.

<!--add fuller material on printers when available-->
