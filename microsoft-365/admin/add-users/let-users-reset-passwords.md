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
description: Descubra cómo puede establecer una directiva para permitir a los usuarios restablecer sus propias contraseñas mediante la herramienta de restablecimiento de contraseña de autoservicio.
ms.openlocfilehash: 2c79d5611ab2db00f4de5f227b0ec2f411955558
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571858"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="21e41-103">Permitir que los usuarios puedan restablecer sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="21e41-103">Let users reset their own passwords</span></span>

<span data-ttu-id="21e41-104">Como administrador de Microsoft 365, puede permitir que las personas usen la [herramienta de restablecimiento de contraseña de autoservicio](https://go.microsoft.com/fwlink/p/?LinkId=522677) para que no tenga que restablecer las contraseñas para ellas.</span><span class="sxs-lookup"><span data-stu-id="21e41-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="21e41-105">Así no tendrá tanto trabajo.</span><span class="sxs-lookup"><span data-stu-id="21e41-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="21e41-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="21e41-106">Before you begin</span></span>
  
- <span data-ttu-id="21e41-107">Obtiene restablecimiento de contraseña de autoservicio para usuarios en la nube **de forma gratuita** con cualquier Microsoft 365 plan de pago empresarial, educativo o sin fines de lucro.</span><span class="sxs-lookup"><span data-stu-id="21e41-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="21e41-108">No funciona con Microsoft 365 juicio.</span><span class="sxs-lookup"><span data-stu-id="21e41-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="21e41-p103">Usa Azure. Recibirá esta característica automáticamente en Azure **gratis** cuando realice estos pasos. No le costará nada activar el autoservicio de restablecimiento de contraseñas si no usa otras características de Azure.</span><span class="sxs-lookup"><span data-stu-id="21e41-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="21e41-112">**Si usa un Active Directory local,** no se aplican los dos puntos anteriores.</span><span class="sxs-lookup"><span data-stu-id="21e41-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="21e41-113">En su lugar, puede configurarlo, pero **requiere una suscripción de pago a Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="21e41-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="21e41-114">Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro.</span><span class="sxs-lookup"><span data-stu-id="21e41-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="21e41-115">Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21e41-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="21e41-116">¿Qué es una cuenta de administrador?</span><span class="sxs-lookup"><span data-stu-id="21e41-116">What's an admin account?</span></span>](../../business-video/admin-center-overview.md)

<span data-ttu-id="21e41-117">Debe ser [administrador global o administrador de contraseñas](about-admin-roles.md) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="21e41-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="21e41-118">Vea: Permita que los usuarios restablezcan sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="21e41-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="21e41-119">Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="21e41-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="21e41-120">Pasos: Deje que las personas restablezcan sus propias contraseñas</span><span class="sxs-lookup"><span data-stu-id="21e41-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="21e41-121">Siga estos pasos para activar el restablecimiento de contraseña de autoservicio para todos los usuarios de su empresa.</span><span class="sxs-lookup"><span data-stu-id="21e41-121">These steps turn on self-service password reset for everyone in your business.</span></span>

1. <span data-ttu-id="21e41-122">En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración,</a>vaya a la página de configuración **de Configuración**  >  **Org.**</span><span class="sxs-lookup"><span data-stu-id="21e41-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

2. <span data-ttu-id="21e41-123">En la parte superior de la página **Configuración de la organización,** seleccione la pestaña **Seguridad & Privacidad.**</span><span class="sxs-lookup"><span data-stu-id="21e41-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="21e41-124">Seleccione **Autoservicio Restablecimiento de contraseña**.</span><span class="sxs-lookup"><span data-stu-id="21e41-124">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="21e41-125">En **Autoservicio de restablecimiento de contraseña,** seleccione **Ir a Azure Portal para activar el restablecimiento de contraseña de autoservicio.**</span><span class="sxs-lookup"><span data-stu-id="21e41-125">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="21e41-126">En el panel de navegación izquierdo, seleccione **Usuarios** y, a continuación, en **los usuarios | Todos los usuarios** página, seleccione **Restablecimiento de contraseña**.</span><span class="sxs-lookup"><span data-stu-id="21e41-126">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="21e41-127">En la página **Propiedades,** seleccione **Todo** para habilitarlo para todos los miembros de su empresa y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="21e41-127">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="21e41-128">Cuando los usuarios inicien sesión, se les pedirá que introduzcan información de contacto adicional que les ayudará a restablecer su contraseña en el futuro.</span><span class="sxs-lookup"><span data-stu-id="21e41-128">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="21e41-129">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="21e41-129">Related content</span></span>

<span data-ttu-id="21e41-130">[Establezca la directiva de expiración de contraseñas para su organización](../manage/set-password-expiration-policy.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="21e41-130">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>

<span data-ttu-id="21e41-131">[Establecer la contraseña de un usuario individual para que nunca expire](set-password-to-never-expire.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="21e41-131">[Set an individual user's password to never expire](set-password-to-never-expire.md) (article)</span></span>

<span data-ttu-id="21e41-132">[Microsoft 365 Empresa vídeos de formación](../../business-video/index.yml) (página de enlace)</span><span class="sxs-lookup"><span data-stu-id="21e41-132">[Microsoft 365 Business training videos](../../business-video/index.yml) (link page)</span></span>
