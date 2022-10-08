---
title: Administración de contraseñas de cuenta de usuario de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- scotvorg
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Obtenga información sobre cómo administrar contraseñas de cuenta de usuario de Microsoft 365.
ms.openlocfilehash: 3c6683fb916ac066d9fff3b168299c50391cbe63
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68163149"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Administración de contraseñas de cuenta de usuario de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede administrar las contraseñas de cuenta de usuario de Microsoft 365 de varias maneras diferentes, en función de la configuración de su identidad. Puede administrar cuentas de usuario en el [Centro de administración de Microsoft 365](/admin), en Servicios de dominio de Active Directory (AD DS) o en el Centro de administración de Azure Active Directory (Azure AD).

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Planear dónde y cómo administrará las contraseñas de la cuenta de usuario

Dónde y cómo puede administrar las cuentas de usuario depende del modelo de identidad que quiera usar para Microsoft 365. Los dos modelos son solo en la nube e híbridos.
  
### <a name="cloud-only"></a>Solo de nube

Las contraseñas de cuenta de usuario se administran en:

- [El Centro de administración de Microsoft 365](/admin)
- Centro de administración de Azure AD
    
### <a name="hybrid"></a>Híbrido

Con la identidad híbrida, las contraseñas se almacenan en AD DS, por lo que debe usar herramientas de AD DS locales para administrar las contraseñas de cuenta de usuario. Incluso cuando se usa la sincronización de hash de contraseñas (PHS), en la que Azure AD almacena una versión con hash de la versión ya con hash en AD DS, usted y los usuarios deben administrar sus contraseñas en AD DS.

Con la [escritura diferida de contraseñas](#pw_writeback), los usuarios pueden cambiar sus contraseñas de AD DS a través de Azure AD.

## <a name="prevent-bad-passwords"></a>Evite contraseñas no válidas

Todos los usuarios deben utilizar la [guía de contraseñas de Microsoft](https://www.microsoft.com/research/publication/password-guidance)para crear las contraseñas de sus cuentas de usuario.

Para evitar que los usuarios creen una contraseña que se pueda determinar con facilidad, utilice la protección de contraseña de Azure AD, que utiliza tanto una lista de contraseñas globalmente prohibidas como una lista opcional personalizada de contraseñas prohibidas que usted especifique. Por ejemplo, puede especificar términos que sean específicos de su organización, como:

- Nombres de marcas
- Nombres de productos
- Ubicaciones (por ejemplo, como la oficina central de la empresa)
- Términos internos específicos de la empresa
- Abreviaturas que tienen un significado específico en la empresa

Puede prohibir las contraseñas incorrectas [en la nube](/azure/active-directory/authentication/concept-password-ban-bad) y [en AD DS local](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

## <a name="simplify-user-sign-in"></a>Simplificar el inicio de sesión de usuario

Azure AD Seamless Single Sign-On (Sso de conexión directa de Azure AD) funciona con PHS y Pass-Through Authentication (PTA), para permitir que los usuarios inicien sesión en servicios que usan cuentas de usuario de Azure AD sin tener que escribir sus contraseñas y, en muchos casos, sus nombres de usuario. Esto ofrece facilita a los usuarios el acceso a aplicaciones en la nube, como Office 365, sin necesidad de componentes locales adicionales, como los servidores de federación de identidades.

Configure el SSO de conexión directa de Azure AD con la herramienta Azure AD Connect. Vea las [instrucciones para configurar el SSO de conexión directa de Azure AD](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Simplificación de las actualizaciones de contraseñas en AD DS

Con la escritura diferida de contraseñas, puede permitir que los usuarios restablezcan sus contraseñas a través de Azure AD, que luego se replica en AD DS. Los usuarios no necesitan acceder a su AD DS local para actualizar sus contraseñas. Esto resulta útil para los usuarios móviles o remotos que no disponen de una conexión de acceso remoto a la red local.

La escritura diferida de contraseñas es necesaria para utilizar por completo las capacidades de Azure AD Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando se haya detectado un alto riesgo de que la cuenta se haya visto comprometida.

Para obtener más información e instrucciones de configuración, vea [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback) (SSPR de Azure AD con escritura diferida de contraseñas).

>[!Note]
>Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

## <a name="simplify-password-resets"></a>Simplificar los restablecimientos de contraseña

El autoservicio de restablecimiento de contraseña (SSPR) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas. Para alertarle acerca de abusos o usos indebidos, el sistema incluye informes detallados del seguimiento de acceso de los usuarios al sistema, además de notificaciones. Debe habilitar la [escritura diferida de contraseñas](#pw_writeback) para poder implementar los restablecimientos de contraseña.

Consulte las [instrucciones para habilitar el restablecimiento de contraseña](/azure/active-directory/authentication/howto-sspr-deployment).