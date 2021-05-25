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
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="2023a-103">Cambiar la directiva de expiración de las contraseñas de la organización</span><span class="sxs-lookup"><span data-stu-id="2023a-103">Set the password expiration policy for your organization</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2023a-104">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="2023a-104">Before you begin</span></span>

<span data-ttu-id="2023a-105">Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro.</span><span class="sxs-lookup"><span data-stu-id="2023a-105">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="2023a-106">Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2023a-106">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="2023a-107">[¿Qué es una cuenta de administrador?](../../business-video/admin-center-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2023a-107">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span>

<span data-ttu-id="2023a-p102">Como administrador, puede hacer que las contraseñas de usuario expiren al cabo de un número determinado de días, o establecer que las contraseñas nunca expiren. De forma predeterminada, está establecido que no expiren nuncapara su organización.</span><span class="sxs-lookup"><span data-stu-id="2023a-p102">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire. By default, passwords are set to never expire for your organization.</span></span>

<span data-ttu-id="2023a-110">Según estudios recientes, los cambios de contraseña obligatorios causan más daño que beneficio.</span><span class="sxs-lookup"><span data-stu-id="2023a-110">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="2023a-111">Esto conduce a los usuarios a elegir contraseñas menos seguras, a volver a utilizar contraseñas anteriores o actualizarlas de manera que sean fáciles de adivinar por los piratas informáticos.</span><span class="sxs-lookup"><span data-stu-id="2023a-111">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="2023a-112">Se recomienda habilitar la [autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2023a-112">We recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span> <span data-ttu-id="2023a-113">Para más información sobre la directiva de contraseñas, consulte [Recomendaciones sobre la directiva de contraseñas](../misc/password-policy-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="2023a-113">To learn more about password policy, check out [Password policy recommendations](../misc/password-policy-recommendations.md).</span></span>

<span data-ttu-id="2023a-114">Para poder realizar estos pasos, debe ser [Administrador global](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2023a-114">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="2023a-p104">Si es un usuario, no tiene los permisos necesarios para configurar que la contraseña no expire nunca. Solicite al soporte técnico de su institución educativa o de su trabajo que siga los pasos de este artículo por usted.</span><span class="sxs-lookup"><span data-stu-id="2023a-p104">If you're a user, you don't have the permissions to set your password to never expire. Ask your work or school technical support to do the steps in this article for you.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="2023a-117">Establecer directiva de expiración de contraseña</span><span class="sxs-lookup"><span data-stu-id="2023a-117">Set password expiration policy</span></span>

<span data-ttu-id="2023a-118">Siga los siguientes pasos cuando quiera configurar las contraseñas de los usuarios para que expiren después que haya transcurrido cierto tiempo.</span><span class="sxs-lookup"><span data-stu-id="2023a-118">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="2023a-119">En el centro de administración, vaya a **Configuración** \> **Ajustes de organización**.</span><span class="sxs-lookup"><span data-stu-id="2023a-119">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="2023a-120">Vaya a la página de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">seguridad y privacidad</a>.</span><span class="sxs-lookup"><span data-stu-id="2023a-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="2023a-121">Si no es administrador global, no verá la opción de seguridad y privacidad.</span><span class="sxs-lookup"><span data-stu-id="2023a-121">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="2023a-122">Establecer la **directiva de expiración de contraseña**</span><span class="sxs-lookup"><span data-stu-id="2023a-122">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="2023a-123">Si no desea que los usuarios tengan que cambiar de contraseña, anule la selección de la casilla situada junto a **Establecer que las contraseñas de usuario nunca expiren tras un cierto número de días**.</span><span class="sxs-lookup"><span data-stu-id="2023a-123">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="2023a-p106">Escriba la frecuencia con la que deben expirar las contraseñas. Elija un número de días de 14 a 730.</span><span class="sxs-lookup"><span data-stu-id="2023a-p106">Type how often passwords should expire. Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="2023a-126">Escriba en la segunda casilla cuándo se debe informar a los usuarios sobre la expiración de su contraseña y luego seleccione **guardar**.</span><span class="sxs-lookup"><span data-stu-id="2023a-126">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="2023a-127">Elija una cantidad de días entre 1 y 30.</span><span class="sxs-lookup"><span data-stu-id="2023a-127">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="2023a-128">Aspectos importantes que debe conocer sobre la función de expiración de contraseña</span><span class="sxs-lookup"><span data-stu-id="2023a-128">Important things you need to know about the password expiration feature</span></span>
  
<span data-ttu-id="2023a-p108">Los usuarios que solo usen la aplicación de Outlook no tendrán que restablecer su contraseña de Microsoft 365 hasta que expire en la caché. Esto puede ser varios días después de la fecha de expiración real. No hay ninguna solución para este problema en el nivel de administrador.</span><span class="sxs-lookup"><span data-stu-id="2023a-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="2023a-132">Impedir la reutilización de la última contraseña</span><span class="sxs-lookup"><span data-stu-id="2023a-132">Prevent last password from being used again</span></span>

<span data-ttu-id="2023a-133">Si desea impedir que los usuarios reutilicen contraseñas anteriores, puede implementar el historial de contraseñas en Active Directory (AD) local.</span><span class="sxs-lookup"><span data-stu-id="2023a-133">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="2023a-134">Consulte [Crear una directiva de contraseñas personalizada](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="2023a-134">See [Create a custom password policy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="2023a-135">En Azure AD, la última contraseña no se puede volver a usar cuando el usuario cambia una contraseña.</span><span class="sxs-lookup"><span data-stu-id="2023a-135">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="2023a-136">La directiva de contraseñas se aplica a todas las cuentas de usuario que se crean y administran directamente en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2023a-136">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="2023a-137">Esta directiva de contraseñas no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="2023a-137">This password policy can't be modified.</span></span> <span data-ttu-id="2023a-138">Consulte [Directivas de contraseñas de Azure AD](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="2023a-138">See [Azure AD password policies](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="2023a-139">Sincronice las contraseñas de usuario de los hash de un Active Directory local con Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="2023a-139">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="2023a-140">Este artículo aborda la manera de configurar la directiva de expiración para los usuarios solo de la nube (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="2023a-140">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="2023a-141">No se aplica a los usuarios de identidad híbrida que usan la sincronización hash de contraseña, autenticación de acceso directo o federación local como ADFS.</span><span class="sxs-lookup"><span data-stu-id="2023a-141">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="2023a-142">Para obtener información sobre cómo sincronizar los hash de contraseña de usuario desde el AD local a Azure AD, vea [implementar la sincronización hash de contraseña con la](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)de sincronización de Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="2023a-142">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="2023a-143">Vea las directivas y restricciones de contraseñas en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2023a-143">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="2023a-144">Puede establecer más directivas y restricciones de contraseñas en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2023a-144">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="2023a-145">Para obtener más información, vea las [directivas de contraseñas y las restricciones de la cuenta de Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy).</span><span class="sxs-lookup"><span data-stu-id="2023a-145">Check out [Password policies and account restrictions in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="2023a-146">Actualizar la directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="2023a-146">Update password Policy</span></span>

<span data-ttu-id="2023a-p113">El cmdlet Set-MsolPasswordPolicy actualiza la directiva de contraseñas de un espacio empresarial o un dominio específico. Se requieren dos opciones de configuración. La primera es indicar el período de tiempo en el que una contraseña sigue siendo válida antes de que se cambie, y la segunda es indicar el número de días antes de la fecha de expiración de la contraseña en que se activará la primera notificación para los usuarios de que la contraseña va a expirar pronto.</span><span class="sxs-lookup"><span data-stu-id="2023a-p113">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant. Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="2023a-149">Para obtener información sobre cómo actualizar la directiva de contraseñas para un dominio o un inquilino específico, consulte [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="2023a-149">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="2023a-150">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="2023a-150">Related content</span></span>

<span data-ttu-id="2023a-151">[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="2023a-151">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="2023a-152">[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="2023a-152">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>