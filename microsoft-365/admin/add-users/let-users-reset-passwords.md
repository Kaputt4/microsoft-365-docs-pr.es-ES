---
title: Permitir que los usuarios puedan restablecer sus propias contraseñas
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Obtén información sobre cómo puedes restablecer las contraseñas con la herramienta de restablecimiento de contraseñas de autoservicio.
ms.openlocfilehash: f43c409e98aa98e942bd7c7cbb15302422df241d
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222128"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="85d6c-103">Permitir que los usuarios puedan restablecer sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="85d6c-103">Let users reset their own passwords</span></span>

<span data-ttu-id="85d6c-104">Como administrador de Microsoft 365, puede [](https://go.microsoft.com/fwlink/p/?LinkId=522677) permitir que los usuarios usen la herramienta de restablecimiento de contraseñas sin servicio para que no tenga que restablecer contraseñas para ellas.</span><span class="sxs-lookup"><span data-stu-id="85d6c-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="85d6c-105">Así no tendrá tanto trabajo.</span><span class="sxs-lookup"><span data-stu-id="85d6c-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="85d6c-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="85d6c-106">Before you begin</span></span>
  
- <span data-ttu-id="85d6c-107">El restablecimiento de contraseñas  sin ánimo de lucro para los usuarios de la nube es gratuito con cualquier plan de pago para empresas, educación o ong de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="85d6c-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="85d6c-108">No funciona con la versión de prueba de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="85d6c-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="85d6c-p103">Usa Azure. Recibirá esta característica automáticamente en Azure **gratis** cuando realice estos pasos. No le costará nada activar el autoservicio de restablecimiento de contraseñas si no usa otras características de Azure.</span><span class="sxs-lookup"><span data-stu-id="85d6c-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="85d6c-112">**Si usa un Active Directory local,** no se aplican los dos puntos anteriores.</span><span class="sxs-lookup"><span data-stu-id="85d6c-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="85d6c-113">En su lugar, puede configurar esto, pero requiere una suscripción **de pago a Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="85d6c-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="85d6c-114">Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro.</span><span class="sxs-lookup"><span data-stu-id="85d6c-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="85d6c-115">Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="85d6c-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="85d6c-116">¿Qué es una cuenta de administrador?</span><span class="sxs-lookup"><span data-stu-id="85d6c-116">What's an admin account?</span></span>](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

<span data-ttu-id="85d6c-117">Debe ser administrador global o administrador [de contraseñas](about-admin-roles.md) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="85d6c-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="85d6c-118">Ver: permitir que los usuarios restablezcan sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="85d6c-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="85d6c-119">Si este vídeo le ha sido de ayuda, vea la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="85d6c-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="85d6c-120">Pasos: permitir que los usuarios restablezcan sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="85d6c-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="85d6c-121">Siga estos pasos para activar el restablecimiento de contraseña de autoservicio para todos los usuarios de su empresa.</span><span class="sxs-lookup"><span data-stu-id="85d6c-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="85d6c-122">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración,</a>vaya a la **página Configuración** de > **la organización.**</span><span class="sxs-lookup"><span data-stu-id="85d6c-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="85d6c-123">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración,</a>vaya a la **página Configuración** Seguridad de \> **&amp; privacidad.**</span><span class="sxs-lookup"><span data-stu-id="85d6c-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="85d6c-124">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración,</a>vaya a la página **Configuración** \>  \> **seguridad &amp; privacidad.**</span><span class="sxs-lookup"><span data-stu-id="85d6c-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="85d6c-125">En la parte superior de la **página Configuración de la** organización, seleccione la pestaña Seguridad & **Privacidad.**</span><span class="sxs-lookup"><span data-stu-id="85d6c-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="85d6c-126">Seleccione **Autoservicio Restablecimiento de contraseña**.</span><span class="sxs-lookup"><span data-stu-id="85d6c-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="85d6c-127">En **Autoservicio de restablecimiento de contraseña,** seleccione Ir a Azure Portal para activar el restablecimiento **de contraseñas sin servicio.**</span><span class="sxs-lookup"><span data-stu-id="85d6c-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="85d6c-128">En el panel de navegación izquierdo, seleccione **Usuarios** y, a continuación, en el **panel Usuarios | Todos los usuarios** página, seleccione **Restablecimiento de contraseña**.</span><span class="sxs-lookup"><span data-stu-id="85d6c-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="85d6c-129">En la **página Propiedades,** seleccione **Todo** para habilitarlo para todos los usuarios de su empresa y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="85d6c-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="85d6c-130">Cuando los usuarios inicien sesión, se les pedirá que escriban información de contacto adicional que les ayudará a restablecer su contraseña en el futuro.</span><span class="sxs-lookup"><span data-stu-id="85d6c-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="85d6c-131">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="85d6c-131">Related content</span></span>

[<span data-ttu-id="85d6c-132">Cambiar la directiva de expiración de las contraseñas de la organización</span><span class="sxs-lookup"><span data-stu-id="85d6c-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="85d6c-133">Establecer la contraseña de un usuario individual que nunca caduque</span><span class="sxs-lookup"><span data-stu-id="85d6c-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="85d6c-134">Vídeos de aprendizaje de Microsoft 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="85d6c-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
