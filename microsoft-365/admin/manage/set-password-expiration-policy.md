---
title: Cambiar la directiva de expiración de las contraseñas de la organización
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Obtenga información sobre cómo un administrador puede establecer una directiva de expiración de contraseñas para su empresa, escuela u ONG en el Centro de administración de Microsoft 365.
ms.openlocfilehash: d94073121eab1979b02883b359de2b75604c8c50
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2022
ms.locfileid: "68564968"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Cambiar la directiva de expiración de las contraseñas de la organización

## <a name="before-you-begin"></a>Antes de empezar

Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](/microsoft-365/admin/add-users/about-admin-roles).

As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire. By default, passwords are set to never expire for your organization.

Según estudios recientes, los cambios de contraseña obligatorios causan más daño que beneficio. Esto conduce a los usuarios a elegir contraseñas menos seguras, a volver a utilizar contraseñas anteriores o actualizarlas de manera que sean fáciles de adivinar por los piratas informáticos. Se recomienda habilitar la [autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md). Para más información sobre la directiva de contraseñas, consulte [Recomendaciones sobre la directiva de contraseñas](../misc/password-policy-recommendations.md).

Para poder realizar estos pasos, debe ser [Administrador global](../add-users/about-admin-roles.md).

If you're a user, you don't have the permissions to set your password to never expire. Ask your work or school technical support to do the steps in this article for you.

> [!TIP]
> Si necesita ayuda con los pasos que se describen en este tema, considere la posibilidad de [trabajar con un especialista en pequeñas empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="set-password-expiration-policy"></a>Establecer directiva de expiración de contraseña

Siga los siguientes pasos cuando quiera configurar las contraseñas de los usuarios para que expiren después que haya transcurrido cierto tiempo.

1. En el Centro de administración de Microsoft 365, vaya a la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**Seguridad y privacidad**</a>.

    Si no es administrador global o administrador de seguridad, no verá la opción Seguridad y privacidad.
  
1. Establecer la **directiva de expiración de contraseña**
  
1. Si no quiere que los usuarios tengan que cambiar las contraseñas, desactive la casilla situada junto a **Establecer contraseñas para que nunca expiren**.

1. Escriba la frecuencia en la que deben expirar las contraseñas. Elija un número de días entre 14 y 730.
 
> [!IMPORTANT]
> Las notificaciones de expiración de contraseñas ya no se admiten en la Centro de administración de Microsoft 365 ni en las aplicaciones de Office ni en las aplicaciones web de Office.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Aspectos importantes que debe conocer sobre la función de expiración de contraseña
  
People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.

## <a name="prevent-last-password-from-being-used-again"></a>Impedir la reutilización de la última contraseña

If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD). See [Create a custom password policy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).

En Azure AD, la última contraseña no se puede volver a usar cuando el usuario cambia una contraseña. La directiva de contraseñas se aplica a todas las cuentas de usuario que se crean y administran directamente en Azure AD. Esta directiva de contraseñas no se puede modificar. Consulte [Directivas de contraseñas de Azure AD](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>Sincronice las contraseñas de usuario de los hash de un Active Directory local con Azure AD (Microsoft 365)

Este artículo aborda la manera de configurar la directiva de expiración para los usuarios solo de la nube (Azure AD). No se aplica a los usuarios de identidad híbrida que usan la sincronización hash de contraseña, autenticación de acceso directo o federación local como ADFS.
  
Para obtener información sobre cómo sincronizar los hash de contraseña de usuario desde el AD local a Azure AD, vea [implementar la sincronización hash de contraseña con la](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)de sincronización de Azure AD Connect.

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Vea las directivas y restricciones de contraseñas en Azure Active Directory.

Puede establecer más directivas y restricciones de contraseñas en Azure Active Directory. Para obtener más información, vea las [directivas de contraseñas y las restricciones de la cuenta de Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy).

## <a name="update-password-policy"></a>Actualizar la directiva de contraseñas

El cmdlet Set-MsolPasswordPolicy actualiza la directiva de contraseñas de un dominio o inquilino especificado e indica el tiempo que una contraseña permanece válida antes de que se deba cambiar.

Para obtener información sobre cómo actualizar la directiva de contraseñas para un dominio o un inquilino específico, consulte [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy).

## <a name="related-content"></a>Contenido relacionado

[Permitir que los usuarios restablezcan sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)/

[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)
