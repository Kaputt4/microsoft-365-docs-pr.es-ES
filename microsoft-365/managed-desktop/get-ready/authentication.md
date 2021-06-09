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
audience: Admin
ms.openlocfilehash: 6df23e0d7e3ea0ecd7ebacd96f00cb47b9e0aa84
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574600"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft

En Escritorio administrado de Microsoft, los dispositivos se unen automáticamente a Azure Active Directory (Azure AD). Por este motivo, si usa un Active Directory local, tendrá que comprobar algunas cosas para asegurarse de que los dispositivos unidos a Azure AD puedan comunicarse con su Active Directory local. 

> [!NOTE]  
> *Híbrido* La combinación de Azure AD no es compatible con Escritorio administrado de Microsoft.

Azure Active Directory permite a los usuarios aprovechar las ventajas de Single Sign-On (SSO), lo que significa que normalmente no tendrán que proporcionar credenciales cada vez que usen recursos.

Para obtener información acerca de Azure Active Directory, consulte [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan). Para obtener información en segundo plano sobre single Sign-On (SSO) en dispositivos unidos a Azure AD, consulte [How SSO to on-premises resources works on Azure AD joined devices](/azure/active-directory/devices/azuread-join-sso#how-it-works).


En este artículo se explican las cosas que debe comprobar para asegurarse de que las aplicaciones y otros recursos que dependen de la conectividad local de Active Directory funcionarán sin problemas con Escritorio administrado de Microsoft.


## <a name="single-sign-on-for-on-premises-resources"></a>Single Sign-On para recursos locales

El Sign-On (SSO) mediante UPN y contraseña está habilitado de forma predeterminada en Escritorio administrado de Microsoft dispositivos. Pero los usuarios también pueden usar Windows Hello para empresas, lo que requiere algunos pasos de configuración adicionales. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Single Sign-On mediante UPN y contraseña

En la mayoría de las organizaciones, los usuarios podrán usar SSO para autenticarse mediante UPN y contraseña en Escritorio administrado de Microsoft dispositivos. Sin embargo, para asegurarse de que esta función funcionará, debe comprobar dos veces lo siguiente:

- Confirme que Azure AD Conectar está configurado y usa un servidor de Active Directory local que ejecuta Windows Server 2008 R2 o posterior.
- Confirme que Azure AD Conectar está ejecutando una versión compatible y está configurado para sincronizar estos tres atributos con Azure AD: 
    - Nombre de dominio DNS del Active Directory local (donde se encuentran los usuarios)
    - NetBIOS de su Active Directory local (donde se encuentran los usuarios)
    - Nombre de cuenta SAM del usuario


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Single Sign-On by using Windows Hello for Business

Escritorio administrado de Microsoft dispositivos también ofrecen a los usuarios una experiencia rápida y sin contraseña mediante el Windows Hello para empresas. Para asegurarse de que Windows Hello para empresas funcionará sin que los usuarios tengan que proporcionar el UPN y la contraseña correspondientes, visite Configure [Azure AD joined devices for On Single-Sign on using Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) para comprobar los requisitos y, a continuación, siga los pasos proporcionados allí.


## <a name="apps-and-resources-that-use-authentication"></a>Aplicaciones y recursos que usan la autenticación

Consulte [Understand considerations for applications and resources](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set para obtener instrucciones detalladas sobre cómo configurar aplicaciones para que funcionen con Azure Active Directory. En resumen:


- Si usa aplicaciones **basadas** en la nube, como las agregadas a la galería de aplicaciones de Azure AD, la mayoría no requiere ninguna preparación adicional para trabajar con Escritorio administrado de Microsoft. Sin embargo, las aplicaciones de Win32 que no usen el Administrador de cuentas web (WAM) podrían pedir autenticación a los usuarios.

- Para las aplicaciones **hospedadas localmente,** asegúrese de agregar esas aplicaciones a la lista de sitios de confianza en los exploradores. Este paso permitirá que Windows autenticación funcione sin problemas, sin que se pidan credenciales a los usuarios. Para agregar aplicaciones, consulte [Sitios de confianza en](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) la referencia configuración [configurable](../working-with-managed-desktop/config-setting-ref.md).

- Si usa Servicios federados de Active Directory, compruebe que SSO está habilitado mediante los pasos descritos en Comprobar y administrar el inicio de sesión único [con AD FS](/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Para las aplicaciones que son locales y usan **protocolos antiguos,** no se requiere ninguna configuración adicional, siempre que los dispositivos tengan acceso a un controlador de dominio local para autenticarse. Sin embargo, para proporcionar acceso seguro a estas aplicaciones, debe implementar el proxy de aplicación de Azure AD. Para obtener más información, vea Acceso remoto a aplicaciones locales a través del proxy de aplicación de [Azure Active Directory.](/azure/active-directory/manage-apps/application-proxy)

- Las aplicaciones que se **ejecutan localmente y dependen** de la autenticación de máquina no son compatibles, por lo que deberías considerar reemplazarlas por versiones más recientes.

### <a name="network-shares-that-use-authentication"></a>Recursos compartidos de red que usan autenticación

No se requiere ninguna configuración adicional para que los usuarios tengan acceso a recursos compartidos de red, siempre y cuando los dispositivos tengan acceso a un controlador de dominio local mediante una ruta de acceso UNC.

### <a name="printers"></a>Impresoras

Escritorio administrado de Microsoft dispositivos no se pueden conectar a impresoras que se publican en su Active Directory local a menos que haya configurado [Hybrid Cloud Print](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).

Aunque las impresoras no se pueden detectar automáticamente en un entorno de solo nube, los usuarios pueden usar impresoras locales mediante la ruta de acceso de la impresora o la ruta de cola de la impresora, siempre que los dispositivos tengan acceso a un controlador de dominio local.

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready"></a>Pasos para prepararse

1. Revisar [Requisitos previos para Escritorio administrado de Microsoft](prerequisites.md).
2. Usar [herramientas de evaluación de preparación](readiness-assessment-tool.md).
3. [Requisitos previos para las cuentas de invitado](guest-accounts.md)
4. [Configuración de red para el Escritorio administrado de Microsoft](network.md)
5. [Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft](certs-wifi-lan.md)
6. [Preparar el acceso a recursos locales para Escritorio administrado de Microsoft](authentication.md) (este artículo)
7. [Aplicaciones en el Escritorio administrado de Microsoft](apps.md)
8. [Preparar unidades asignadas para el Escritorio administrado de Microsoft](mapped-drives.md)
9. [Preparar recursos de impresión para el Escritorio administrado de Microsoft](printing.md)
