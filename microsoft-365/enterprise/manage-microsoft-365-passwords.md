---
title: Administrar Microsoft 365 contraseñas de cuenta de usuario
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Obtenga información sobre cómo administrar las contraseñas Microsoft 365 cuenta de usuario.
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905097"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Administrar Microsoft 365 contraseñas de cuenta de usuario

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede administrar las contraseñas Microsoft 365 cuenta de usuario de varias maneras diferentes, según la configuración de la identidad. Puede administrar cuentas de usuario en el Centro de administración de [Microsoft 365](../admin/add-users/index.yml), en Servicios de dominio de Active Directory (AD DS) o en el Centro de administración de Azure Active Directory (Azure AD).

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Planear dónde y cómo administrará las contraseñas de la cuenta de usuario

Dónde y cómo puede administrar sus cuentas de usuario depende del modelo de identidad que desee usar para su Microsoft 365. Los dos modelos son híbridos y solo en la nube.
  
### <a name="cloud-only"></a>Solo de nube

Las contraseñas de cuentas de usuario se administran en:

- [Centro de administración de Microsoft 365](../admin/add-users/index.yml)
- Centro de administración de Azure AD
    
### <a name="hybrid"></a>Híbrido

Con la identidad híbrida, las contraseñas se almacenan en AD DS, por lo que debes usar las herramientas locales de AD DS para administrar las contraseñas de cuentas de usuario. Incluso cuando se usa la sincronización de hash de contraseña (PHS), en la que Azure AD almacena una versión hash de la versión ya hash en AD DS, usted y los usuarios deben administrar sus contraseñas en AD DS.

Con [la reescribición de](#pw_writeback)contraseñas, los usuarios pueden cambiar sus contraseñas de AD DS a través de Azure AD.

## <a name="prevent-bad-passwords"></a>Evite contraseñas no válidas

Todos los usuarios deben utilizar la [guía de contraseñas de Microsoft](https://www.microsoft.com/research/publication/password-guidance)para crear las contraseñas de sus cuentas de usuario.

Para evitar que los usuarios creen una contraseña que se pueda determinar con facilidad, utilice la protección de contraseña de Azure AD, que utiliza tanto una lista de contraseñas globalmente prohibidas como una lista opcional personalizada de contraseñas prohibidas que usted especifique. Por ejemplo, puede especificar términos que sean específicos de su organización, como:

- Nombres de marcas
- Nombres de productos
- Ubicaciones (por ejemplo, como la oficina central de la empresa)
- Términos internos específicos de la empresa
- Abreviaturas que tienen un significado específico en la empresa

Puede prohibir las contraseñas [incorrectas en la nube](/azure/active-directory/authentication/concept-password-ban-bad) y para su [AD DS local.](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)

## <a name="simplify-user-sign-in"></a>Simplificar el inicio de sesión de usuario

Azure AD Seamless Single Sign-On (SSO de conexión directa de Azure AD) funciona con PHS y autenticación Pass-Through (PTA), para permitir que los usuarios inicien sesión en los servicios que usan cuentas de usuario de Azure AD sin tener que escribir sus contraseñas y, en muchos casos, sus nombres de usuario. Esto ofrece facilita a los usuarios el acceso a aplicaciones en la nube, como Office 365, sin necesidad de componentes locales adicionales, como los servidores de federación de identidades.

Configure el SSO de conexión directa de Azure AD con la herramienta Azure AD Connect. Vea las [instrucciones para configurar el SSO de conexión directa de Azure AD](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Simplificar las actualizaciones de contraseñas en AD DS

Con la reescribición de contraseñas, puede permitir que los usuarios restablezcan sus contraseñas a través de Azure AD, que luego se replica en AD DS. Los usuarios no necesitan tener acceso a su AD DS local para actualizar sus contraseñas. Esto resulta útil para los usuarios móviles o remotos que no disponen de una conexión de acceso remoto a la red local.

La escritura diferida de contraseñas es necesaria para utilizar por completo las capacidades de Azure AD Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando se haya detectado un alto riesgo de que la cuenta se haya visto comprometida.

Para obtener más información e instrucciones de configuración, vea [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback) (SSPR de Azure AD con escritura diferida de contraseñas).

>[!Note]
>Actualice a la última versión de Azure AD Connect para garantizar que tiene la mejor experiencia posible y nuevas características cuando se publican. Para obtener más información, vea [Instalación personalizada de Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

## <a name="simplify-password-resets"></a>Simplificar los restablecimientos de contraseña

El restablecimiento de contraseñas de autoservicio (SSPR) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas. Para alertarle acerca de abusos o usos indebidos, el sistema incluye informes detallados del seguimiento de acceso de los usuarios al sistema, además de notificaciones. Debe habilitar la [reescribición de contraseñas](#pw_writeback) para poder implementar restablecimientos de contraseña.

Consulte las [instrucciones para habilitar el restablecimiento de contraseña](/azure/active-directory/authentication/howto-sspr-deployment).