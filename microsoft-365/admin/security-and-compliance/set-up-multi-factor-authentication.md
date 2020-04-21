---
title: Configurar multi-factor Authentication para los usuarios
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
ms.openlocfilehash: 4a829aa597596564b9c2f468e72f3a766b198372
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627685"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="71113-103">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="71113-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="71113-104">Si compró la suscripción o la versión de prueba después del 21 de octubre de 2019 y se le solicita inesperadamente la MFA, los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="71113-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="71113-105">Todas las nuevas suscripciones de Microsoft 365 tendrán habilitada la seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="71113-105">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="71113-106">Esto significa que todos los usuarios tendrán que configurar la autenticación multifactor (MFA) y, a continuación, instalar la aplicación de autenticación en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="71113-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="71113-107">Para obtener más información, consulte [configurar la verificación en dos pasos para Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="71113-107">For more information, see [Set up 2-step verification for Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="71113-108">Los nueve roles de administrador que se indican a continuación serán necesarios para realizar una autenticación adicional cada vez que inicien sesión:</span><span class="sxs-lookup"><span data-stu-id="71113-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="71113-109">Administrador global</span><span class="sxs-lookup"><span data-stu-id="71113-109">Global administrator</span></span>
- <span data-ttu-id="71113-110">Administrador de SharePoint</span><span class="sxs-lookup"><span data-stu-id="71113-110">SharePoint administrator</span></span>
- <span data-ttu-id="71113-111">Administrador de Exchange</span><span class="sxs-lookup"><span data-stu-id="71113-111">Exchange administrator</span></span>
- <span data-ttu-id="71113-112">Administrador de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="71113-112">Conditional Access administrator</span></span>
- <span data-ttu-id="71113-113">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="71113-113">Security administrator</span></span>
- <span data-ttu-id="71113-114">Administrador de contraseñas o administrador del departamento de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="71113-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="71113-115">Administrador de facturación</span><span class="sxs-lookup"><span data-stu-id="71113-115">Billing administrator</span></span>
- <span data-ttu-id="71113-116">Administrador de usuarios</span><span class="sxs-lookup"><span data-stu-id="71113-116">User administrator</span></span>
- <span data-ttu-id="71113-117">Administrador de autenticación</span><span class="sxs-lookup"><span data-stu-id="71113-117">Authentication administrator</span></span>

<span data-ttu-id="71113-118">Se pedirá a todos los demás usuarios una autenticación adicional cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="71113-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="71113-119">Para más información, vea [¿Qué son los valores predeterminados de seguridad?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="71113-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="71113-120">Debe ser un administrador global para configurar o modificar la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="71113-120">You must be a global admin to set up or modify multi-factor authentication.</span></span> <br><br>
> <span data-ttu-id="71113-121">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="71113-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="71113-122">Si ha configurado previamente MFA con directivas de línea base, [debe desactivarlas y activar los valores predeterminados de seguridad](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="71113-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="71113-123">Sin embargo, si tiene Microsoft 365 Empresa o su suscripción incluye [Azure Active Directory Premium 1 o Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), también puede configurar directivas de [acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="71113-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="71113-124">Para usar directivas de acceso condicional, debe asegurarse de que la [autenticación moderna](#enable-modern-authentication-for-your-organization) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="71113-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="71113-125">Para explicar a los usuarios cómo configurar la aplicación Authenticator, visite [Usar Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="71113-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="71113-126">Administrar los valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="71113-126">Manage security defaults</span></span>

1. <span data-ttu-id="71113-127">Inicie sesión en el [Centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822) con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="71113-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="71113-128">Vaya a [Propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="71113-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="71113-129">En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="71113-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="71113-130">Elija **Sí** para habilitar los valores predeterminados de seguridad y **No** para deshabilitar los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71113-130">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="71113-131">Cambie de las directivas de línea base a los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71113-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="71113-132">En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822), seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="71113-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="71113-133">Junto a **inicio de sesión y seguridad**, por debajo de **un inicio de sesión más seguro**, seleccione **ver**.</span><span class="sxs-lookup"><span data-stu-id="71113-133">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="71113-134">Por debajo de **Un inicio de sesión más seguro**, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="71113-134">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="71113-135">En la página **acceso condicional-directivas** , elija cada directiva de línea base que esté **activada**y, a continuación, establezca el valor en **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="71113-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="71113-136">Vaya a la página [Propiedades en Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="71113-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="71113-137">En la parte inferior de la página, **Elija administrar los valores predeterminados de seguridad**y, en el panel **Habilitar valores** predeterminados de seguridad, establezca la alternancia **Habilitar valores predeterminados de seguridad** en **sí**y, después, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="71113-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="71113-138">Habilitar la autenticación moderna para la organización</span><span class="sxs-lookup"><span data-stu-id="71113-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="71113-139">Todas las aplicaciones de cliente de Office 2016 admiten la MFA mediante el uso de la Biblioteca de autenticación de Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="71113-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="71113-140">Esto significa que las contraseñas de aplicaciones no son necesarias para los clientes de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="71113-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="71113-141">Sin embargo, debe asegurarse de que la suscripción a Microsoft 365 está habilitada para ADAL o para la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="71113-141">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="71113-142">Para habilitar la autenticación moderna, en el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822), seleccione **Configuración** \>\*\*Configuración \*\*y después, en la pestaña **Servicios** elija **Autenticación moderna** en la lista.</span><span class="sxs-lookup"><span data-stu-id="71113-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="71113-143">Active la casilla **Habilitar autenticación moderna (recomendada)** en el panel de **autenticación moderna** y, a continuación, elija **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="71113-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![En el Panel de autenticación moderna la casilla de verificación está marcada en habilitar](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="71113-145">A partir de agosto de 2017, todas las suscripciones de Microsoft 365 nuevas que incluyen Skype empresarial online y Exchange Online tienen habilitada de forma predeterminada la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="71113-145">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="71113-146">Para comprobar el estado de su autenticación moderna para Skype Empresarial online, puede utilizar el PowerShell de Skype Empresarial online con credenciales de Administrador Global.</span><span class="sxs-lookup"><span data-stu-id="71113-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="71113-147">Ejecute Get-CsOAuthConfiguration para comprobar la salida de -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="71113-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="71113-148">Si -ClientADALAuthOverride está en la opción "Permitir", significa que la autenticación moderna está activada.</span><span class="sxs-lookup"><span data-stu-id="71113-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="71113-149">Para comprobar el estado de su MA para Exchange Online, visite [habilite la autenticación moderna en Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="71113-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="71113-150">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="71113-150">Related articles</span></span>

[<span data-ttu-id="71113-151">Las diez formas principales de proteger los planes de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="71113-151">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="71113-152">Habilitar la autenticación moderna para Office 2013 en dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="71113-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
