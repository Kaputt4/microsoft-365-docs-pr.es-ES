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
description: Aprenda a establecer la directiva de expiración de contraseñas para su organización en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 74b23b4a1b67ecd5c9199388985e8e38c3231239
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221828"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Cambiar la directiva de expiración de las contraseñas de la organización

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](../microsoft-365-admin-center-preview.md?view=o365-worldwide).

::: moniker-end

## <a name="before-you-begin"></a>Antes de empezar

Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).

Para poder realizar estos pasos, debe ser [Administrador global](../add-users/about-admin-roles.md).

En caso de ser un usuario, no posee los permisos para establecer una contraseña que no expire nunca. Pídale al soporte técnico de su trabajo o escuela que siga los pasos de este artículo por usted.

Como administrador, puede hacer que las contraseñas de usuario expiren al cabo de un número determinado de días, o establecer que las contraseñas nunca expiren.

## <a name="set-password-expiration-policy"></a>Establecer directiva de expiración de contraseña

> [!Tip]
> De forma predeterminada, las contraseñas se configuran para que expiren en 90 días. Según estudios recientes, los cambios de contraseña obligatorios causan más daño que beneficio. Esto conduce a los usuarios a elegir contraseñas menos seguras, a volver a utilizar contraseñas anteriores o actualizarlas de manera que sean fáciles de adivinar por los piratas informáticos. Si el establecimiento de su contraseña nunca expira, le recomendamos que habilite la [autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md).

Siga los siguientes pasos cuando quiera configurar las contraseñas de los usuarios para que expiren después que haya transcurrido cierto tiempo.

1. En el centro de administración, vaya a **Configuración** \> **Ajustes de organización**.

2. Vaya a la página de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">seguridad y privacidad</a>.
 Si no es administrador global, no verá la opción de seguridad y privacidad.
  
3. Establecer la **directiva de expiración de contraseña**
  
4. Si no desea que los usuarios tengan que cambiar de contraseña, anule la selección de la casilla situada junto a **Establecer que las contraseñas de usuario nunca expiren tras un cierto número de días**.
  
5. Escriba la frecuencia en la que deben expirar las contraseñas. Elija un número de días entre 14 y 730.
  
6. Escriba en la segunda casilla cuándo se debe informar a los usuarios sobre la expiración de su contraseña y luego seleccione **guardar**. Elija una cantidad de días entre 1 y 30.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Aspectos importantes que debe conocer sobre la función de expiración de contraseña
  
- Los usuarios que solo usen la aplicación de Outlook no tendrán que restablecer su contraseña de Microsoft 365 hasta que expire en la caché. Esto puede ser varios días después de la fecha de expiración real. No hay ninguna solución para este problema en el nivel de administrador.

## <a name="prevent-last-password-from-being-used-again"></a>Impedir la reutilización de la última contraseña

Si desea impedir que los usuarios reutilicen contraseñas anteriores, puede implementar el historial de contraseñas en Active Directory (AD) local. Consulte [Crear una directiva de contraseñas personalizada](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).

En Azure AD, la última contraseña no se puede volver a usar cuando el usuario cambia una contraseña. La directiva de contraseñas se aplica a todas las cuentas de usuario que se crean y administran directamente en Azure AD. Esta directiva de contraseñas no se puede modificar. Consulte [Directivas de contraseñas de Azure AD](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>Sincronice las contraseñas de usuario de los hash de un Active Directory local con Azure AD (Microsoft 365)

Este artículo aborda la manera de configurar la directiva de expiración para los usuarios solo de la nube (Azure AD). No se aplica a los usuarios de identidad híbrida que usan la sincronización hash de contraseña, autenticación de acceso directo o federación local como ADFS.
  
Para obtener información sobre cómo sincronizar los hash de contraseña de usuario desde el AD local a Azure AD, vea [implementar la sincronización hash de contraseña con la](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)de sincronización de Azure AD Connect.

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Vea las directivas y restricciones de contraseñas en Azure Active Directory.

Puede establecer más directivas y restricciones de contraseñas en Azure Active Directory. Para obtener más información, vea las [directivas de contraseñas y las restricciones de la cuenta de Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy).

## <a name="update-password-policy"></a>Actualizar la directiva de contraseñas

El cmdlet Set-MsolPasswordPolicy actualiza la directiva de contraseñas de un inquilino o un dominio específico. Se requieren dos opciones de configuración. La primera es indicar el período de tiempo en el que una contraseña sigue siendo válida antes de que se cambie, y la segunda es indicar el número de días antes de la fecha de expiración de la contraseña que se activará cuando los usuarios reciban la primera notificación de que la contraseña va a expirar pronto.

Para obtener información sobre cómo actualizar la directiva de contraseñas para un dominio o un inquilino específico, consulte [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).

## <a name="related-content"></a>Contenido relacionado

[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md)

[Restablecer contraseñas](../add-users/reset-passwords.md)