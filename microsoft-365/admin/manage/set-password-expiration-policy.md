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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Aprenda a establecer la directiva de expiración de contraseñas para su organización en el Centro de administración de Microsoft 365. '
ms.openlocfilehash: eec6231d2c6b5d51b25f42c401e367743fdb19ea
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560876"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="a4c64-103">Cambiar la directiva de expiración de las contraseñas de la organización</span><span class="sxs-lookup"><span data-stu-id="a4c64-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a4c64-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="a4c64-104">The admin center is changing.</span></span> <span data-ttu-id="a4c64-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a4c64-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="a4c64-106">Este artículo va dirigido a los usuarios que deben establecer una directiva de expiración de contraseñas para una empresa, un centro educativo o una ONG.</span><span class="sxs-lookup"><span data-stu-id="a4c64-106">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="a4c64-107">En caso de ser un usuario, no posee los permisos para establecer una contraseña que no expire nunca.</span><span class="sxs-lookup"><span data-stu-id="a4c64-107">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="a4c64-108">Pídale al soporte técnico de su trabajo o escuela que siga los pasos de este artículo por usted.</span><span class="sxs-lookup"><span data-stu-id="a4c64-108">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="a4c64-109">Como administrador, puede hacer que las contraseñas de usuario expiren al cabo de un número determinado de días, o establecer que las contraseñas nunca expiren.</span><span class="sxs-lookup"><span data-stu-id="a4c64-109">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="a4c64-110">De forma predeterminada, las contraseñas se configuran para que expiren en 90 días.</span><span class="sxs-lookup"><span data-stu-id="a4c64-110">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="a4c64-111">Según estudios recientes, los cambios de contraseña obligatorios causan más daño que beneficio.</span><span class="sxs-lookup"><span data-stu-id="a4c64-111">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="a4c64-112">Esto conduce a los usuarios a elegir contraseñas menos seguras, a volver a utilizar contraseñas anteriores o actualizarlas de manera que sean fáciles de adivinar por los piratas informáticos.</span><span class="sxs-lookup"><span data-stu-id="a4c64-112">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="a4c64-113">Si el establecimiento de su contraseña nunca expira, le recomendamos que habilite la [autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a4c64-113">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="a4c64-114">Siga los siguientes pasos cuando quiera configurar las contraseñas de los usuarios para que expiren después que haya transcurrido cierto tiempo.</span><span class="sxs-lookup"><span data-stu-id="a4c64-114">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a4c64-115">Solo los [administradores globales](../add-users/about-admin-roles.md) pueden realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a4c64-115">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="a4c64-116">En el centro de administración, vaya a **configuración** \> **ajustes**.</span><span class="sxs-lookup"><span data-stu-id="a4c64-116">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="a4c64-117">Vaya a la página de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">seguridad y privacidad</a>.</span><span class="sxs-lookup"><span data-stu-id="a4c64-117">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="a4c64-118">Si no es administrador global, no verá la opción de seguridad y privacidad.</span><span class="sxs-lookup"><span data-stu-id="a4c64-118">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="a4c64-119">Establecer la **directiva de expiración de contraseña**</span><span class="sxs-lookup"><span data-stu-id="a4c64-119">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="a4c64-120">Cuando no desee que los usuarios tengan que cambiar de contraseña, seleccione la casilla de verificación situada junto a **establecer que las contraseñas de usuario nunca expiren tras un cierto número de días**.</span><span class="sxs-lookup"><span data-stu-id="a4c64-120">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="a4c64-121">Escriba la frecuencia en la que deben expirar las contraseñas.</span><span class="sxs-lookup"><span data-stu-id="a4c64-121">Type how often passwords should expire.</span></span> <span data-ttu-id="a4c64-122">Elija un número de días entre 14 y 730.</span><span class="sxs-lookup"><span data-stu-id="a4c64-122">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="a4c64-123">Escriba en la segunda casilla cuándo se debe informar a los usuarios sobre la expiración de su contraseña y luego seleccione **guardar**.</span><span class="sxs-lookup"><span data-stu-id="a4c64-123">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="a4c64-124">Elija una cantidad de días entre 1 y 30.</span><span class="sxs-lookup"><span data-stu-id="a4c64-124">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="a4c64-125">Cuando la contraseña del usuario expira, recibirá una notificación que aparece en la esquina inferior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="a4c64-125">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="a4c64-126">Aspectos importantes que debe conocer sobre la función de expiración de contraseña</span><span class="sxs-lookup"><span data-stu-id="a4c64-126">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="a4c64-127">Estos son algunos aspectos que debe conocer acerca del funcionamiento de esta función a partir de enero de 2018:</span><span class="sxs-lookup"><span data-stu-id="a4c64-127">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="a4c64-p107">Los usuarios que solo usen la aplicación de Outlook no tendrán que restablecer su contraseña de Microsoft 365 hasta que expire en la caché. Esto puede ser varios días después de la fecha de expiración real. No hay ninguna solución para este problema en el nivel de administrador.</span><span class="sxs-lookup"><span data-stu-id="a4c64-p107">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="a4c64-p108">Los usuarios no reciben una notificación por correo electrónico de que su contraseña va a expirar en X número de días. ¿Quiere esta característica? **[Vote aquí.](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="a4c64-p108">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="a4c64-134">Impedir la reutilización de la última contraseña</span><span class="sxs-lookup"><span data-stu-id="a4c64-134">Prevent last password from being used again</span></span>

<span data-ttu-id="a4c64-135">Si desea impedir que los usuarios reutilicen contraseñas anteriores, puede implementar el historial de contraseñas en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a4c64-135">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in Azure AD.</span></span> <span data-ttu-id="a4c64-136">Consulte [Crear una directiva de contraseñas personalizada](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="a4c64-136">See [Create a custom password policy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="a4c64-137">Sincronice las contraseñas de usuario de los hash de un Active Directory local con Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="a4c64-137">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="a4c64-138">Este artículo aborda la manera de configurar la directiva de expiración para los usuarios solo de la nube (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a4c64-138">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="a4c64-139">No se aplica a los usuarios de identidad híbrida que usan la sincronización hash de contraseña, autenticación de acceso directo o federación local como ADFS.</span><span class="sxs-lookup"><span data-stu-id="a4c64-139">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="a4c64-140">Para obtener información sobre cómo sincronizar los hash de contraseña de usuario desde el AD local a Azure AD, vea [implementar la sincronización hash de contraseña con la](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)de sincronización de Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="a4c64-140">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>


## <a name="update-password-policy"></a><span data-ttu-id="a4c64-141">Actualizar la directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="a4c64-141">Update password Policy</span></span>

<span data-ttu-id="a4c64-142">El cmdlet Set-MsolPasswordPolicy actualiza la directiva de contraseñas de un inquilino o un dominio específico.</span><span class="sxs-lookup"><span data-stu-id="a4c64-142">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="a4c64-143">Se requieren dos opciones de configuración. La primera es indicar el período de tiempo en el que una contraseña sigue siendo válida antes de que se cambie, y la segunda es indicar el número de días antes de la fecha de expiración de la contraseña que se activará cuando los usuarios reciban la primera notificación de que la contraseña va a expirar pronto.</span><span class="sxs-lookup"><span data-stu-id="a4c64-143">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="a4c64-144">Para obtener información sobre cómo actualizar la directiva de contraseñas para un dominio o un inquilino específico, consulte [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="a4c64-144">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>
