---
title: Configuración de autenticación multifactor para usuarios
f1.keywords:
- NOCSH
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
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Obtenga información acerca de cómo configurar la autenticación multifactor para su organización.
monikerRange: o365-worldwide
ms.openlocfilehash: 480e09e42ea53cc78cd738a6e0650feae7a9f8c8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635955"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="faa96-103">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="faa96-103">Set up multi-factor authentication</span></span>

<span data-ttu-id="faa96-104">Basándose en su conocimiento de la [autenticación multifactor (MFA) y su compatibilidad con Microsoft 365](multi-factor-authentication-microsoft-365.md), es hora de configurarla e implementarla en la organización.</span><span class="sxs-lookup"><span data-stu-id="faa96-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="faa96-105">Si ha comprado la suscripción o la versión de evaluación después del 21 de octubre de 2019, y se le solicita la MFA al iniciar sesión, los [valores predeterminados de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="faa96-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="faa96-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="faa96-106">Before you begin</span></span>

- <span data-ttu-id="faa96-107">Para poder gestionar la MFA, debe ser administrador global.</span><span class="sxs-lookup"><span data-stu-id="faa96-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="faa96-108">Para obtener más información, vea [Sobre los roles de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="faa96-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="faa96-109">Si tiene activada la MFA heredada por usuario, [Desactive la MFA heredada por usuario](#turn-off-legacy-per-user-mfa).</span><span class="sxs-lookup"><span data-stu-id="faa96-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="faa96-110">Si tiene clientes de Office 2013 en dispositivos Windows, [habilite la autenticación moderna para clientes de Office 2013](./enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="faa96-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](./enable-modern-authentication.md).</span></span>
- <span data-ttu-id="faa96-111">Configuración avanzada: si tiene servicios de directorio de terceros con Servicios de federación de Active Directory (AD FS), configure el Servidor Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="faa96-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="faa96-112">Para más información, consulte [Escenarios avanzados con la autenticación multifactor de Microsoft Azure AD y soluciones VPN de terceros](/azure/active-directory/authentication/howto-mfaserver-nps-vpn).</span><span class="sxs-lookup"><span data-stu-id="faa96-112">See [advanced scenarios with Azure AD Multi-Factor Authentication and third-party VPN solutions](/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="faa96-113">Activar o desactivar las opciones predeterminadas de seguridad</span><span class="sxs-lookup"><span data-stu-id="faa96-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="faa96-114">En la mayoría de las organizaciones, los valores predeterminados de seguridad ofrecen un buen nivel de seguridad adicional de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="faa96-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="faa96-115">Para obtener más información, vea [¿Qué son los valores predeterminados de seguridad?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="faa96-115">For more information, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="faa96-116">Si la suscripción es nueva, es posible que los valores predeterminados de seguridad ya estén activados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="faa96-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="faa96-117">Puede habilitar o deshabilitar los valores predeterminados de seguridad en el panel **Propiedades** de Azure Active Directory (Azure AD) en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="faa96-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="faa96-118">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="faa96-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="faa96-119">En el panel de navegación izquierdo, elija **Mostrar todo** y, en **Centros de administración**, elija **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="faa96-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="faa96-120">En el **Centro de administración de Azure Active Directory** elija **Azure Active Directory** \> **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="faa96-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="faa96-121">En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="faa96-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="faa96-122">Elija **Sí** para habilitar los valores predeterminados de seguridad y **No** para deshabilitar los valores predeterminados de seguridad; a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="faa96-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="faa96-123">Si ha estado usando [directivas de acceso condicional de línea base](/azure/active-directory/conditional-access/concept-baseline-protection), se le pedirá que las desactive antes de pasar a usar los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="faa96-123">If you have been using [baseline Conditional Access policies](/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="faa96-124">Vaya a la página [Directivas: Acceso condicional](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="faa96-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="faa96-125">Elija cada directiva de línea base que esté **Activada** y establezca **Activar directiva** en **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="faa96-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="faa96-126">Vaya a la página [Propiedades en Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="faa96-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="faa96-127">En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="faa96-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="faa96-128">Elija **Sí** para habilitar los valores predeterminados de seguridad y **No** para deshabilitar los valores predeterminados de seguridad, después, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="faa96-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="faa96-129">Usar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="faa96-129">Use Conditional Access policies</span></span>

<span data-ttu-id="faa96-130">Si su organización tiene necesidades de seguridad de inicio de sesión más pormenorizadas, las directivas de acceso condicional le ofrecen más control.</span><span class="sxs-lookup"><span data-stu-id="faa96-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="faa96-131">El acceso condicional le permite crear y definir directivas que reaccionan a eventos de inicio de sesión y solicitan acciones adicionales antes de otorgar acceso a un usuario a una aplicación o a un servicio.</span><span class="sxs-lookup"><span data-stu-id="faa96-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="faa96-132">Desactive la MFA por usuario y los valores predeterminados de seguridad antes de habilitar las directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="faa96-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="faa96-133">El acceso condicional está disponible para los clientes que han adquirido Azure AD Premium P1 o licencias que lo incluyen, como Microsoft 365 Empresa Premium y Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="faa96-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="faa96-134">Para obtener más información, vea [creación de una directiva de acceso condicional](/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span><span class="sxs-lookup"><span data-stu-id="faa96-134">For more information, see [create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="faa96-135">El acceso condicional basado en el riesgo está disponible con la licencia de Azure AD Premium P2 o las licencias que lo incluyen, como Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="faa96-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="faa96-136">Para más información, vea [Acceso condicional basado en el riesgo](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span><span class="sxs-lookup"><span data-stu-id="faa96-136">For more information, see [risk-based Conditional Access](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="faa96-137">Para obtener más información sobre Azure AD P1 y P2, vea [Precios de Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="faa96-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="faa96-138">Activar la autenticación moderna para su organización</span><span class="sxs-lookup"><span data-stu-id="faa96-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="faa96-139">Para la mayoría de las suscripciones, la autenticación moderna se activa automáticamente, pero si compró la suscripción antes de agosto de 2017, es probable que deba activar la autenticación moderna para que características como la autenticación multifactor funcionen en clientes de Windows como Outlook.</span><span class="sxs-lookup"><span data-stu-id="faa96-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription before August 2017, it is likely that you will need to turn on Modern Authentication in order to get features like Multi-Factor Authentication to work in Windows clients like Outlook.</span></span>


1. <span data-ttu-id="faa96-140">En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, elija **Configuración** \> **Configuración de la organización**.</span><span class="sxs-lookup"><span data-stu-id="faa96-140">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
2. <span data-ttu-id="faa96-141">En la pestaña **Servicios**, elija **Autenticación moderna** y, en el panel **Autenticación moderna**, asegúrese de que **Habilitar autenticación moderna** esté seleccionado.</span><span class="sxs-lookup"><span data-stu-id="faa96-141">Under the **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="faa96-142">Elija **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="faa96-142">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="faa96-143">Desactivar la MFA heredada por usuario</span><span class="sxs-lookup"><span data-stu-id="faa96-143">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="faa96-144">Si ha activado previamente la MFA por usuario, debe desactivarla antes de habilitar los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="faa96-144">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="faa96-145">En el centro de administración de Microsoft 365, en el panel de navegación izquierdo, elija **Usuarios** \> **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="faa96-145">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="faa96-146">En la página **Usuarios activos**, elija **Autenticación multifactor**.</span><span class="sxs-lookup"><span data-stu-id="faa96-146">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="faa96-147">En la página de autenticación multifactor, seleccione cada usuario y establezca el estado de la autenticación multifactor en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="faa96-147">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="faa96-148">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="faa96-148">Next steps</span></span>

- [<span data-ttu-id="faa96-149">Cómo registrarse para el método de verificación adicional</span><span class="sxs-lookup"><span data-stu-id="faa96-149">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="faa96-150">Qué es: la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="faa96-150">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="faa96-151">Cómo iniciar sesión después del registro</span><span class="sxs-lookup"><span data-stu-id="faa96-151">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="faa96-152">Cómo cambiar el método de verificación adicional</span><span class="sxs-lookup"><span data-stu-id="faa96-152">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-content"></a><span data-ttu-id="faa96-153">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="faa96-153">Related content</span></span>

<span data-ttu-id="faa96-154">[Activar la autenticación multifactor](../../business-video/turn-on-mfa.md) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="faa96-154">[Turn on multi-factor authentication](../../business-video/turn-on-mfa.md) (video)</span></span>\
<span data-ttu-id="faa96-155">[Activar la autenticación multifactor para su teléfono (Vídeo)](../../business-video/set-up-mfa.md)</span><span class="sxs-lookup"><span data-stu-id="faa96-155">[Turn on multi-factor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>