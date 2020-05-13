---
title: Configuración de autenticación multifactor para usuarios
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Obtenga información sobre cómo usar los valores predeterminados de seguridad para configurar la autenticación multifactor para los usuarios.
monikerRange: o365-worldwide
ms.openlocfilehash: 4c0df9198db8154c1aa748a68eff29dd9bf3bca1
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213015"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="e1e7d-103">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="e1e7d-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e1e7d-104">Si compró la suscripción o la versión de prueba después del 21 de octubre de 2019 y se le solicita inesperadamente la autenticación multifactor (MFA), los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="e1e7d-105">Todas las nuevas suscripciones de Microsoft 365 tendrán habilitada la [seguridad predeterminada](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) .</span><span class="sxs-lookup"><span data-stu-id="e1e7d-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="e1e7d-106">Esto significa que todos los usuarios tendrán que configurar la autenticación multifactor (MFA) e instalar la aplicación Microsoft Authenticator en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="e1e7d-107">Para obtener más información, consulte [configurar la MFA para una cuenta de Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="e1e7d-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="e1e7d-108">Los nueve roles de administrador que se indican a continuación serán necesarios para realizar una autenticación adicional cada vez que inicien sesión:</span><span class="sxs-lookup"><span data-stu-id="e1e7d-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="e1e7d-109">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e1e7d-109">Global administrator</span></span>
- <span data-ttu-id="e1e7d-110">Administrador de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e1e7d-110">SharePoint administrator</span></span>
- <span data-ttu-id="e1e7d-111">Administrador de Exchange</span><span class="sxs-lookup"><span data-stu-id="e1e7d-111">Exchange administrator</span></span>
- <span data-ttu-id="e1e7d-112">Administrador de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="e1e7d-112">Conditional Access administrator</span></span>
- <span data-ttu-id="e1e7d-113">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="e1e7d-113">Security administrator</span></span>
- <span data-ttu-id="e1e7d-114">Administrador de contraseñas o administrador del departamento de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="e1e7d-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="e1e7d-115">Administrador de facturación</span><span class="sxs-lookup"><span data-stu-id="e1e7d-115">Billing administrator</span></span>
- <span data-ttu-id="e1e7d-116">Administrador de usuarios</span><span class="sxs-lookup"><span data-stu-id="e1e7d-116">User administrator</span></span>
- <span data-ttu-id="e1e7d-117">Administrador de autenticación</span><span class="sxs-lookup"><span data-stu-id="e1e7d-117">Authentication administrator</span></span>

<span data-ttu-id="e1e7d-118">Se pedirá a todos los demás usuarios una autenticación adicional cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="e1e7d-119">Debe ser un administrador global para configurar o modificar la MFA</span><span class="sxs-lookup"><span data-stu-id="e1e7d-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="e1e7d-120">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="e1e7d-121">Si ha configurado previamente MFA con directivas de línea base, debe desactivarlas [para activar los valores predeterminados de seguridad](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="e1e7d-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="e1e7d-122">Sin embargo, si tiene Microsoft 365 Business o su suscripción incluye [Azure Active Directory Premium P1 o Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), también puede configurar directivas de [acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) .</span><span class="sxs-lookup"><span data-stu-id="e1e7d-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="e1e7d-123">Para usar directivas de acceso condicional, debe asegurarse de que los valores predeterminados de seguridad están deshabilitados y la [autenticación moderna](#enable-modern-authentication-for-your-organization) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="e1e7d-124">Para explicar a los usuarios cómo configurar la aplicación Microsoft Authenticator, vea [usar Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span><span class="sxs-lookup"><span data-stu-id="e1e7d-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="e1e7d-125">Administrar los valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="e1e7d-125">Manage security defaults</span></span>

1. <span data-ttu-id="e1e7d-126">Inicie sesión en el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822) con credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="e1e7d-127">Vaya a la [Página de propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="e1e7d-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="e1e7d-128">En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="e1e7d-129">Elija **sí** para habilitar los valores predeterminados de seguridad y **no** para deshabilitar los valores predeterminados de seguridad y, después, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="e1e7d-130">Cambie de las directivas de línea base a los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="e1e7d-131">Vaya a la [Página acceso condicional-directivas](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="e1e7d-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="e1e7d-132">Elija cada directiva de línea base que esté **activada** y establezca la **Directiva de habilitación** en **desactivada**.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="e1e7d-133">Vaya a la [Página de propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="e1e7d-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="e1e7d-134">En la parte inferior de la página, **Elija administrar los valores predeterminados de seguridad**y, en el panel **Habilitar valores** predeterminados de seguridad, establezca la alternancia **Habilitar valores predeterminados de seguridad** en **sí**y, después, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="e1e7d-135">Habilitar la autenticación moderna para la organización</span><span class="sxs-lookup"><span data-stu-id="e1e7d-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="e1e7d-136">Todas las aplicaciones de cliente de Office 2016 admiten la MFA mediante el uso de la Biblioteca de autenticación de Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="e1e7d-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="e1e7d-137">Esto significa que las contraseñas de aplicaciones no son necesarias para los clientes de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="e1e7d-138">Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-138">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>

<span data-ttu-id="e1e7d-139">Sin embargo, debe asegurarse de que la suscripción a Microsoft 365 está habilitada para ADAL o para la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-139">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="e1e7d-140">Para habilitar la autenticación moderna, en el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822), seleccione **Configuración** \>\*\*Configuración \*\*y después, en la pestaña **Servicios** elija **Autenticación moderna** en la lista.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="e1e7d-141">Active la casilla **Habilitar autenticación moderna (recomendada)** en el panel de **autenticación moderna** y, a continuación, elija **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-141">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![En el Panel de autenticación moderna la casilla de verificación está marcada en habilitar](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="e1e7d-143">A partir de agosto de 2017, todas las suscripciones de Microsoft 365 nuevas que incluyen Skype empresarial online y Exchange Online tienen habilitada de forma predeterminada la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-143">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="e1e7d-144">Para comprobar el estado de su autenticación moderna para Skype Empresarial online, puede utilizar el PowerShell de Skype Empresarial online con credenciales de Administrador Global.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-144">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="e1e7d-145">Ejecute Get-CsOAuthConfiguration para comprobar la salida de -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-145">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="e1e7d-146">Si -ClientADALAuthOverride está en la opción "Permitir", significa que la autenticación moderna está activada.</span><span class="sxs-lookup"><span data-stu-id="e1e7d-146">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="e1e7d-147">Para comprobar el estado de su MA para Exchange Online, visite [habilite la autenticación moderna en Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="e1e7d-147">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="e1e7d-148">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="e1e7d-148">Related articles</span></span>

[<span data-ttu-id="e1e7d-149">Las diez formas principales de proteger los planes de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e1e7d-149">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="e1e7d-150">Habilitar la autenticación moderna para Office 2013 en dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="e1e7d-150">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
