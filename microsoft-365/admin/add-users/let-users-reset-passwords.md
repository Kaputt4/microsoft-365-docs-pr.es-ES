---
title: Permitir que los usuarios puedan restablecer sus propias contraseñas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Obtenga información sobre cómo restablecer las contraseñas con la herramienta de restablecimiento de contraseña de autoservicio.
ms.openlocfilehash: 01099f6f678bbaa3b163ac59e0417614352e0e97
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173535"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="e0d67-103">Permitir que los usuarios puedan restablecer sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="e0d67-103">Let users reset their own passwords</span></span>

<span data-ttu-id="e0d67-104">¿No cesan de pedirle que restablezca contraseñas?</span><span class="sxs-lookup"><span data-stu-id="e0d67-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="e0d67-105">Como administrador de Microsoft 365, puede permitir que los usuarios usen la [herramienta de restablecimiento de contraseñas de autoservicio](https://go.microsoft.com/fwlink/p/?LinkId=522677) para no tener que restablecer sus contraseñas.</span><span class="sxs-lookup"><span data-stu-id="e0d67-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="e0d67-106">Así no tendrá tanto trabajo.</span><span class="sxs-lookup"><span data-stu-id="e0d67-106">Less work for you!</span></span> 
  
<span data-ttu-id="e0d67-107">Algunas cuestiones que debería conocer:</span><span class="sxs-lookup"><span data-stu-id="e0d67-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="e0d67-108">Obtiene el restablecimiento de contraseñas de autoservicio para los usuarios en la nube de forma gratuita con cualquier plan pagado de Microsoft 365 Business, Education o **sin** ánimo de lucro.</span><span class="sxs-lookup"><span data-stu-id="e0d67-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="e0d67-109">No funciona con la versión de prueba de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0d67-109">It doesn't work with Microsoft 365 trial.</span></span> 
    
- <span data-ttu-id="e0d67-p103">Usa Azure. Recibirá esta característica automáticamente en Azure **gratis** cuando realice estos pasos. No le costará nada activar el autoservicio de restablecimiento de contraseñas si no usa otras características de Azure.</span><span class="sxs-lookup"><span data-stu-id="e0d67-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="e0d67-113">**Si está usando un Active Directory local**, no se aplican los dos puntos anteriores.</span><span class="sxs-lookup"><span data-stu-id="e0d67-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="e0d67-114">En su lugar, puede configurar esto pero **requiere una suscripción de pago a Azure ad Premium**.</span><span class="sxs-lookup"><span data-stu-id="e0d67-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="e0d67-115">Vea un breve vídeo sobre cómo permitir que los usuarios restablezcan sus propias contraseñas.</span><span class="sxs-lookup"><span data-stu-id="e0d67-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="e0d67-116">Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="e0d67-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="e0d67-117">Permitir que los usuarios restablezcan sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="e0d67-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="e0d67-118">Siga estos pasos para activar el restablecimiento de contraseña de autoservicio para todos los usuarios de su empresa.</span><span class="sxs-lookup"><span data-stu-id="e0d67-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1. <span data-ttu-id="e0d67-119">En el centro de administración, vaya a **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">la página de configuración de</a> configuración.</span><span class="sxs-lookup"><span data-stu-id="e0d67-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e0d67-120">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **configuración** \> de \*\*privacidad de seguridad &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="e0d67-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e0d67-121">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a **la** \> **Settings** \> página Configuración de configuración de \*\*privacidad de seguridad &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="e0d67-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="e0d67-122">En la parte superior de la página Configuración, seleccione **seguridad & privacidad**.</span><span class="sxs-lookup"><span data-stu-id="e0d67-122">At the top of the Settings page select **Security & Privacy**.</span></span>
  
3. <span data-ttu-id="e0d67-123">Seleccione **autoservicio de restablecimiento de contraseña**.</span><span class="sxs-lookup"><span data-stu-id="e0d67-123">Select **Self Service Password Reset**.</span></span>
  
4. <span data-ttu-id="e0d67-124">En la página de propiedades, seleccione **todos** para habilitarlo para todos los usuarios de su empresa y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e0d67-124">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="e0d67-125">Cuando los usuarios inicien sesión, se les pedirá que escriban información de contacto adicional que les ayude a restablecer la contraseña en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e0d67-125">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e0d67-126">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="e0d67-126">Related articles</span></span>

[<span data-ttu-id="e0d67-127">Cambiar la directiva de expiración de las contraseñas de la organización</span><span class="sxs-lookup"><span data-stu-id="e0d67-127">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="e0d67-128">Establecer la contraseña de un usuario individual que nunca caduque</span><span class="sxs-lookup"><span data-stu-id="e0d67-128">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="e0d67-129">Vídeos de aprendizaje de Microsoft 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="e0d67-129">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
