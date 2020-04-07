---
title: Configurar la autenticación multifactor para los usuarios de Office 365
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
description: Aprenda a usar valores predeterminados para configurar la autenticación multifactor para los usuarios de Office 365.
monikerRange: o365-worldwide
ms.openlocfilehash: 331552a4de21198fe7fbc9980e89bfcd87449ffa
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153561"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="e7b16-103">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="e7b16-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e7b16-104">Si compró la suscripción o la versión de prueba después del 21 de octubre de 2019 y se le solicita inesperadamente la autenticación multifactor (MFA), los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="e7b16-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="e7b16-105">Todas las nuevas suscripciones de Office 365 Empresa o Microsoft 365 Empresa tendrán activados automáticamente los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e7b16-105">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="e7b16-106">Esto significa que todos los usuarios tendrán que configurar MFA e instalar la aplicación Microsoft Authenticator en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="e7b16-106">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="e7b16-107">Para obtener más información, vea [Configurar la verificación en dos pasos de Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="e7b16-107">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="e7b16-108">Los nueve roles de administrador que se indican a continuación serán necesarios para realizar una autenticación adicional cada vez que inicien sesión:</span><span class="sxs-lookup"><span data-stu-id="e7b16-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="e7b16-109">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e7b16-109">Global administrator</span></span>
- <span data-ttu-id="e7b16-110">Administrador de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e7b16-110">SharePoint administrator</span></span>
- <span data-ttu-id="e7b16-111">Administrador de Exchange</span><span class="sxs-lookup"><span data-stu-id="e7b16-111">Exchange administrator</span></span>
- <span data-ttu-id="e7b16-112">Administrador de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="e7b16-112">Conditional Access administrator</span></span>
- <span data-ttu-id="e7b16-113">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="e7b16-113">Security administrator</span></span>
- <span data-ttu-id="e7b16-114">Administrador de contraseñas o administrador del departamento de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="e7b16-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="e7b16-115">Administrador de facturación</span><span class="sxs-lookup"><span data-stu-id="e7b16-115">Billing administrator</span></span>
- <span data-ttu-id="e7b16-116">Administrador de usuarios</span><span class="sxs-lookup"><span data-stu-id="e7b16-116">User administrator</span></span>
- <span data-ttu-id="e7b16-117">Administrador de autenticación</span><span class="sxs-lookup"><span data-stu-id="e7b16-117">Authentication administrator</span></span>

<span data-ttu-id="e7b16-118">Se pedirá a todos los demás usuarios una autenticación adicional cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e7b16-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="e7b16-119">Para obtener más información, vea [¿Qué son los valores predeterminados de seguridad?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="e7b16-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="e7b16-120">Debe ser un administrador global de Office 365 para configurar o modificar la MFA.</span><span class="sxs-lookup"><span data-stu-id="e7b16-120">You must be an Office 365 global admin to set up or modify MFA.</span></span> <br><br>
> <span data-ttu-id="e7b16-121">Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="e7b16-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="e7b16-122">Si ha configurado previamente MFA con directivas de línea base, [debe desactivarlas y activar los valores predeterminados de seguridad](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="e7b16-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="e7b16-123">Sin embargo, si tiene Microsoft 365 Business o su suscripción incluye [Azure Active Directory Premium P1 o Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), también puede configurar directivas de [acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) .</span><span class="sxs-lookup"><span data-stu-id="e7b16-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="e7b16-124">Para usar directivas de acceso condicional, debe asegurarse de que la [autenticación moderna](#enable-modern-authentication-for-your-organization) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="e7b16-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="e7b16-125">Para explicar a los usuarios cómo configurar la aplicación Authenticator, visite [Usar Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="e7b16-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="e7b16-126">Administrar los valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="e7b16-126">Manage security defaults</span></span>

1. <span data-ttu-id="e7b16-127">Inicie sesión en el [Centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822) con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e7b16-127">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="e7b16-128">Vaya a [Propiedades en Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="e7b16-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="e7b16-129">En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e7b16-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="e7b16-130">Elija **sí** para habilitar los valores predeterminados de seguridad o **no** para deshabilitar los valores predeterminados de seguridad y, después, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e7b16-130">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="e7b16-131">Cambie de las directivas de línea base a los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e7b16-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="e7b16-132">En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822), seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="e7b16-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="e7b16-133">Junto a **inicio de sesión y seguridad**, por debajo de **un inicio de sesión más seguro**, seleccione **ver**.</span><span class="sxs-lookup"><span data-stu-id="e7b16-133">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="e7b16-134">Por debajo de **Un inicio de sesión más seguro**, seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="e7b16-134">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="e7b16-135">En la página **Directivas de acceso condicional de Azure Portal:**, elija cada directiva de línea base que esté **Activada** y establézcala como **Desactivada**.</span><span class="sxs-lookup"><span data-stu-id="e7b16-135">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="e7b16-136">Vaya a la página [Propiedades en Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="e7b16-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="e7b16-137">En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad** y en el panel **Habilitar valores predeterminados de seguridad**, establezca **Habilitar valores predeterminados de seguridad** como **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e7b16-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="e7b16-138">Habilitar la autenticación moderna para la organización</span><span class="sxs-lookup"><span data-stu-id="e7b16-138">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="e7b16-139">Todas las aplicaciones de cliente de Office 2016 admiten la MFA mediante el uso de la Biblioteca de autenticación de Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="e7b16-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="e7b16-140">Esto significa que las contraseñas de aplicaciones no son necesarias para los clientes de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="e7b16-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="e7b16-141">Sin embargo, debe asegurarse de que su suscripción a Office 365 está habilitada para ADAL, o autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="e7b16-141">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="e7b16-142">Para habilitar la autenticación moderna, en el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822), seleccione **Configuración** \>\*\*Configuración \*\*y después, en la pestaña **Servicios** elija **Autenticación moderna** en la lista.</span><span class="sxs-lookup"><span data-stu-id="e7b16-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="e7b16-143">Marque la casilla **habilitar autenticación moderna** en el panel de **autenticación moderna**.</span><span class="sxs-lookup"><span data-stu-id="e7b16-143">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![En el Panel de autenticación moderna la casilla de verificación está marcada en habilitar](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="e7b16-145">A partir de agosto de 2017, todos los nuevos inquilinos de Office 365 que incluyen Skype Empresarial online y Exchange online tienen la autenticación moderna habilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e7b16-145">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="e7b16-146">Para comprobar el estado de su autenticación moderna para Skype Empresarial online, puede utilizar el PowerShell de Skype Empresarial online con credenciales de Administrador Global.</span><span class="sxs-lookup"><span data-stu-id="e7b16-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="e7b16-147">Ejecute Get-CsOAuthConfiguration para comprobar la salida de -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="e7b16-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="e7b16-148">Si -ClientADALAuthOverride está en la opción "Permitir", significa que la autenticación moderna está activada.</span><span class="sxs-lookup"><span data-stu-id="e7b16-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="e7b16-149">Para comprobar el estado de su MA para Exchange Online, visite [habilite la autenticación moderna en Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="e7b16-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="e7b16-150">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="e7b16-150">Related articles</span></span>

[<span data-ttu-id="e7b16-151">Las 10 mejores formas de proteger los planes de Office 365 y Microsoft 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="e7b16-151">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="e7b16-152">Habilitar la autenticación moderna para Office 2013 en dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="e7b16-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
