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
ms.openlocfilehash: 4a7b544b6eded6f0cd6441ad7f6b02de790e5e44
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50603989"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="4c826-103">Cambiar la directiva de expiración de las contraseñas de la organización</span><span class="sxs-lookup"><span data-stu-id="4c826-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4c826-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="4c826-104">The admin center is changing.</span></span> <span data-ttu-id="4c826-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="4c826-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide).</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="4c826-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="4c826-106">Before you begin</span></span>

<span data-ttu-id="4c826-107">Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro.</span><span class="sxs-lookup"><span data-stu-id="4c826-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="4c826-108">Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c826-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="4c826-109">[¿Qué es una cuenta de administrador?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4c826-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span>

<span data-ttu-id="4c826-110">Para poder realizar estos pasos, debe ser [Administrador global](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="4c826-110">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="4c826-111">En caso de ser un usuario, no posee los permisos para establecer una contraseña que no expire nunca.</span><span class="sxs-lookup"><span data-stu-id="4c826-111">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="4c826-112">Pídale al soporte técnico de su trabajo o escuela que siga los pasos de este artículo por usted.</span><span class="sxs-lookup"><span data-stu-id="4c826-112">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="4c826-113">Como administrador, puede hacer que las contraseñas de usuario expiren al cabo de un número determinado de días, o establecer que las contraseñas nunca expiren.</span><span class="sxs-lookup"><span data-stu-id="4c826-113">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="4c826-114">Establecer directiva de expiración de contraseña</span><span class="sxs-lookup"><span data-stu-id="4c826-114">Set password expiration policy</span></span>

> [!Tip]
> <span data-ttu-id="4c826-115">De forma predeterminada, las contraseñas se configuran para que expiren en 90 días.</span><span class="sxs-lookup"><span data-stu-id="4c826-115">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="4c826-116">Según estudios recientes, los cambios de contraseña obligatorios causan más daño que beneficio.</span><span class="sxs-lookup"><span data-stu-id="4c826-116">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="4c826-117">Esto conduce a los usuarios a elegir contraseñas menos seguras, a volver a utilizar contraseñas anteriores o actualizarlas de manera que sean fáciles de adivinar por los piratas informáticos.</span><span class="sxs-lookup"><span data-stu-id="4c826-117">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="4c826-118">Si el establecimiento de su contraseña nunca expira, le recomendamos que habilite la [autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="4c826-118">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="4c826-119">Siga los siguientes pasos cuando quiera configurar las contraseñas de los usuarios para que expiren después que haya transcurrido cierto tiempo.</span><span class="sxs-lookup"><span data-stu-id="4c826-119">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="4c826-120">En el centro de administración, vaya a **Configuración** \> **Ajustes de organización**.</span><span class="sxs-lookup"><span data-stu-id="4c826-120">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="4c826-121">Vaya a la página de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">seguridad y privacidad</a>.</span><span class="sxs-lookup"><span data-stu-id="4c826-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="4c826-122">Si no es administrador global, no verá la opción de seguridad y privacidad.</span><span class="sxs-lookup"><span data-stu-id="4c826-122">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="4c826-123">Establecer la **directiva de expiración de contraseña**</span><span class="sxs-lookup"><span data-stu-id="4c826-123">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="4c826-124">Si no desea que los usuarios tengan que cambiar de contraseña, anule la selección de la casilla situada junto a **Establecer que las contraseñas de usuario nunca expiren tras un cierto número de días**.</span><span class="sxs-lookup"><span data-stu-id="4c826-124">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="4c826-125">Escriba la frecuencia en la que deben expirar las contraseñas.</span><span class="sxs-lookup"><span data-stu-id="4c826-125">Type how often passwords should expire.</span></span> <span data-ttu-id="4c826-126">Elija un número de días entre 14 y 730.</span><span class="sxs-lookup"><span data-stu-id="4c826-126">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="4c826-127">Escriba en la segunda casilla cuándo se debe informar a los usuarios sobre la expiración de su contraseña y luego seleccione **guardar**.</span><span class="sxs-lookup"><span data-stu-id="4c826-127">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="4c826-128">Elija una cantidad de días entre 1 y 30.</span><span class="sxs-lookup"><span data-stu-id="4c826-128">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="4c826-129">Aspectos importantes que debe conocer sobre la función de expiración de contraseña</span><span class="sxs-lookup"><span data-stu-id="4c826-129">Important things you need to know about the password expiration feature</span></span>
  
- <span data-ttu-id="4c826-p108">Los usuarios que solo usen la aplicación de Outlook no tendrán que restablecer su contraseña de Microsoft 365 hasta que expire en la caché. Esto puede ser varios días después de la fecha de expiración real. No hay ninguna solución para este problema en el nivel de administrador.</span><span class="sxs-lookup"><span data-stu-id="4c826-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="4c826-133">Impedir la reutilización de la última contraseña</span><span class="sxs-lookup"><span data-stu-id="4c826-133">Prevent last password from being used again</span></span>

<span data-ttu-id="4c826-134">Si desea impedir que los usuarios reutilicen contraseñas anteriores, puede implementar el historial de contraseñas en Active Directory (AD) local.</span><span class="sxs-lookup"><span data-stu-id="4c826-134">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="4c826-135">Consulte [Crear una directiva de contraseñas personalizada](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="4c826-135">See [Create a custom password policy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="4c826-136">En Azure AD, la última contraseña no se puede volver a usar cuando el usuario cambia una contraseña.</span><span class="sxs-lookup"><span data-stu-id="4c826-136">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="4c826-137">La directiva de contraseñas se aplica a todas las cuentas de usuario que se crean y administran directamente en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4c826-137">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="4c826-138">Esta directiva de contraseñas no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="4c826-138">This password policy can't be modified.</span></span> <span data-ttu-id="4c826-139">Consulte [Directivas de contraseñas de Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="4c826-139">See [Azure AD password policies](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="4c826-140">Sincronice las contraseñas de usuario de los hash de un Active Directory local con Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="4c826-140">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="4c826-141">Este artículo aborda la manera de configurar la directiva de expiración para los usuarios solo de la nube (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="4c826-141">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="4c826-142">No se aplica a los usuarios de identidad híbrida que usan la sincronización hash de contraseña, autenticación de acceso directo o federación local como ADFS.</span><span class="sxs-lookup"><span data-stu-id="4c826-142">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="4c826-143">Para obtener información sobre cómo sincronizar los hash de contraseña de usuario desde el AD local a Azure AD, vea [implementar la sincronización hash de contraseña con la](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)de sincronización de Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="4c826-143">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="4c826-144">Vea las directivas y restricciones de contraseñas en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4c826-144">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="4c826-145">Puede establecer más directivas y restricciones de contraseñas en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4c826-145">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="4c826-146">Para obtener más información, vea las [directivas de contraseñas y las restricciones de la cuenta de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy).</span><span class="sxs-lookup"><span data-stu-id="4c826-146">Check out [Password policies and account restrictions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="4c826-147">Actualizar la directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="4c826-147">Update password Policy</span></span>

<span data-ttu-id="4c826-148">El cmdlet Set-MsolPasswordPolicy actualiza la directiva de contraseñas de un inquilino o un dominio específico.</span><span class="sxs-lookup"><span data-stu-id="4c826-148">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="4c826-149">Se requieren dos opciones de configuración. La primera es indicar el período de tiempo en el que una contraseña sigue siendo válida antes de que se cambie, y la segunda es indicar el número de días antes de la fecha de expiración de la contraseña que se activará cuando los usuarios reciban la primera notificación de que la contraseña va a expirar pronto.</span><span class="sxs-lookup"><span data-stu-id="4c826-149">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="4c826-150">Para obtener información sobre cómo actualizar la directiva de contraseñas para un dominio o un inquilino específico, consulte [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="4c826-150">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="4c826-151">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="4c826-151">Related content</span></span>

[<span data-ttu-id="4c826-152">Permitir que los usuarios puedan restablecer sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="4c826-152">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="4c826-153">Restablecer contraseñas</span><span class="sxs-lookup"><span data-stu-id="4c826-153">Reset passwords</span></span>](../add-users/reset-passwords.md)
