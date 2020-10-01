---
title: Administración de contraseñas de cuentas de usuario 365 de Microsoft
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
description: Obtenga información sobre cómo administrar las contraseñas de cuentas de usuario de Microsoft 365.
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328542"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Administración de contraseñas de cuentas de usuario 365 de Microsoft

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Puede administrar las contraseñas de cuentas de usuario de Microsoft 365 de varias maneras diferentes, según la configuración de su identidad. Puede administrar cuentas de usuario en el [centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), en servicios de dominio de Active Directory (AD DS), o en el centro de administración de Azure Active Directory (Azure ad).

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Planeación de dónde y cómo se va a administrar las contraseñas de la cuenta de usuario

Dónde y cómo puede administrar las cuentas de usuario depende del modelo de identidad que desee usar para el 365 de Microsoft. Los dos modelos son solo de nube e híbridos.
  
### <a name="cloud-only"></a>Solo de nube

Las contraseñas de cuentas de usuario se administran en:

- [Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- El centro de administración de Azure AD
    
### <a name="hybrid"></a>Híbrido

Con la identidad híbrida, las contraseñas se almacenan en AD DS, por lo que debe usar las herramientas de AD DS local para administrar las contraseñas de cuentas de usuario. Incluso cuando se usa la sincronización de hash de contraseña (PHS), en la que Azure AD almacena una versión hash de la versión ya con hash en AD DS, usted y los usuarios deben administrar sus contraseñas en AD DS.

Con la [escritura diferida de contraseñas](#pw_writeback), los usuarios pueden cambiar sus contraseñas de AD DS a través de Azure ad.

## <a name="prevent-bad-passwords"></a>Evite contraseñas no válidas

Todos los usuarios deben utilizar la [guía de contraseñas de Microsoft](https://www.microsoft.com/research/publication/password-guidance)para crear las contraseñas de sus cuentas de usuario.

Para evitar que los usuarios creen una contraseña que se pueda determinar con facilidad, utilice la protección de contraseña de Azure AD, que utiliza tanto una lista de contraseñas globalmente prohibidas como una lista opcional personalizada de contraseñas prohibidas que usted especifique. Por ejemplo, puede especificar términos que sean específicos de su organización, como:

- Nombres de marcas
- Nombres de productos
- Ubicaciones (por ejemplo, como la oficina central de la empresa)
- Términos internos específicos de la empresa
- Abreviaturas que tienen un significado específico en la empresa

Puede prohibir las contraseñas incorrectas [en la nube](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) y en [AD DS local](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

## <a name="simplify-user-sign-in"></a>Simplificar el inicio de sesión de usuario

El inicio de sesión único de perfectas de Azure AD (SSO de acceso directo de Azure AD) funciona con PHS y autenticación de paso a través (PTA), para permitir que los usuarios inicien sesión en servicios que usan cuentas de usuario de Azure AD sin tener que escribir sus contraseñas y, en muchos casos, sus nombres de usuario. Esto ofrece facilita a los usuarios el acceso a aplicaciones en la nube, como Office 365, sin necesidad de componentes locales adicionales, como los servidores de federación de identidades.

Configure el SSO de conexión directa de Azure AD con la herramienta Azure AD Connect. Vea las [instrucciones para configurar el SSO de conexión directa de Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Simplificar las actualizaciones de contraseñas en AD DS

Con la escritura diferida de contraseña, puede permitir a los usuarios restablecer sus contraseñas mediante Azure AD, que se replican a AD DS. Los usuarios no necesitan tener acceso a su AD DS local para actualizar sus contraseñas. Esto resulta útil para los usuarios móviles o remotos que no disponen de una conexión de acceso remoto a la red local.

La escritura diferida de contraseñas es necesaria para utilizar por completo las capacidades de Azure AD Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando se haya detectado un alto riesgo de que la cuenta se haya visto comprometida.

Para obtener más información e instrucciones de configuración, vea [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) (SSPR de Azure AD con escritura diferida de contraseñas).

>[!Note]
>Actualice a la última versión de Azure AD Connect para garantizar que tiene la mejor experiencia posible y nuevas características cuando se publican. Para obtener más información, vea [Instalación personalizada de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

## <a name="simplify-password-resets"></a>Simplificar los restablecimientos de contraseña

Self-Service password reset (SSPR) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas. Para alertarle acerca de abusos o usos indebidos, el sistema incluye informes detallados del seguimiento de acceso de los usuarios al sistema, además de notificaciones. Debe habilitar la [escritura diferida de contraseñas](#pw_writeback) para poder implementar restablecimientos de contraseña.

Consulte las [instrucciones para habilitar el restablecimiento de contraseña](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

