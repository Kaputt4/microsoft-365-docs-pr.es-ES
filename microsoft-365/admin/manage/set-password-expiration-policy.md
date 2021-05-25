---
title: Cambiar la directiva de expiración de las contraseñas de la organización
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Obtenga información sobre cómo un administrador puede establecer una directiva de expiración de contraseñas para su empresa, escuela u ONG en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 7f12918211718b91313c0c89b11eaeb0a8cc3181
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635827"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Cambiar la directiva de expiración de las contraseñas de la organización

## <a name="before-you-begin"></a>Antes de empezar

Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](../../business-video/admin-center-overview.md).

Como administrador, puede hacer que las contraseñas de usuario expiren al cabo de un número determinado de días, o establecer que las contraseñas nunca expiren. De forma predeterminada, está establecido que no expiren nuncapara su organización.

Según estudios recientes, los cambios de contraseña obligatorios causan más daño que beneficio. Esto conduce a los usuarios a elegir contraseñas menos seguras, a volver a utilizar contraseñas anteriores o actualizarlas de manera que sean fáciles de adivinar por los piratas informáticos. Se recomienda habilitar la [autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md). Para más información sobre la directiva de contraseñas, consulte [Recomendaciones sobre la directiva de contraseñas](../misc/password-policy-recommendations.md).

Para poder realizar estos pasos, debe ser [Administrador global](../add-users/about-admin-roles.md).

Si es un usuario, no tiene los permisos necesarios para configurar que la contraseña no expire nunca. Solicite al soporte técnico de su institución educativa o de su trabajo que siga los pasos de este artículo por usted.

## <a name="set-password-expiration-policy"></a>Establecer directiva de expiración de contraseña

Siga los siguientes pasos cuando quiera configurar las contraseñas de los usuarios para que expiren después que haya transcurrido cierto tiempo.

1. En el centro de administración, vaya a **Configuración** \> **Ajustes de organización**.

2. Vaya a la página de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">seguridad y privacidad</a>.
 Si no es administrador global, no verá la opción de seguridad y privacidad.
  
3. Establecer la **directiva de expiración de contraseña**
  
4. Si no desea que los usuarios tengan que cambiar de contraseña, anule la selección de la casilla situada junto a **Establecer que las contraseñas de usuario nunca expiren tras un cierto número de días**.
  
5. Escriba la frecuencia con la que deben expirar las contraseñas. Elija un número de días de 14 a 730.
  
6. Escriba en la segunda casilla cuándo se debe informar a los usuarios sobre la expiración de su contraseña y luego seleccione **guardar**. Elija una cantidad de días entre 1 y 30.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Aspectos importantes que debe conocer sobre la función de expiración de contraseña
  
Los usuarios que solo usen la aplicación de Outlook no tendrán que restablecer su contraseña de Microsoft 365 hasta que expire en la caché. Esto puede ser varios días después de la fecha de expiración real. No hay ninguna solución para este problema en el nivel de administrador.

## <a name="prevent-last-password-from-being-used-again"></a>Impedir la reutilización de la última contraseña

Si desea impedir que los usuarios reutilicen contraseñas anteriores, puede implementar el historial de contraseñas en Active Directory (AD) local. Consulte [Crear una directiva de contraseñas personalizada](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).

En Azure AD, la última contraseña no se puede volver a usar cuando el usuario cambia una contraseña. La directiva de contraseñas se aplica a todas las cuentas de usuario que se crean y administran directamente en Azure AD. Esta directiva de contraseñas no se puede modificar. Consulte [Directivas de contraseñas de Azure AD](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>Sincronice las contraseñas de usuario de los hash de un Active Directory local con Azure AD (Microsoft 365)

Este artículo aborda la manera de configurar la directiva de expiración para los usuarios solo de la nube (Azure AD). No se aplica a los usuarios de identidad híbrida que usan la sincronización hash de contraseña, autenticación de acceso directo o federación local como ADFS.
  
Para obtener información sobre cómo sincronizar los hash de contraseña de usuario desde el AD local a Azure AD, vea [implementar la sincronización hash de contraseña con la](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)de sincronización de Azure AD Connect.

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Vea las directivas y restricciones de contraseñas en Azure Active Directory.

Puede establecer más directivas y restricciones de contraseñas en Azure Active Directory. Para obtener más información, vea las [directivas de contraseñas y las restricciones de la cuenta de Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy).

## <a name="update-password-policy"></a>Actualizar la directiva de contraseñas

El cmdlet Set-MsolPasswordPolicy actualiza la directiva de contraseñas de un espacio empresarial o un dominio específico. Se requieren dos opciones de configuración. La primera es indicar el período de tiempo en el que una contraseña sigue siendo válida antes de que se cambie, y la segunda es indicar el número de días antes de la fecha de expiración de la contraseña en que se activará la primera notificación para los usuarios de que la contraseña va a expirar pronto.

Para obtener información sobre cómo actualizar la directiva de contraseñas para un dominio o un inquilino específico, consulte [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).

## <a name="related-content"></a>Contenido relacionado

[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)\
[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)