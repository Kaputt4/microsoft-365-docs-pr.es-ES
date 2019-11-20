---
title: Configurar directivas de acceso condicional
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo requerir MFA y cómo configurar directivas de acceso condicional para Microsoft 365 Business.
ms.openlocfilehash: 0279fff8dd4143c883b2f1633907ac197c65f04a
ms.sourcegitcommit: b535fe233234fd25146cfe15478e20d954f71e03
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "38748291"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="0a587-103">Requerir la autenticación multifactor y configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="0a587-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="0a587-104">Proteja el acceso a sus datos con la autenticación multifactor y las directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="0a587-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="0a587-105">Estos agregan una seguridad adicional importante.</span><span class="sxs-lookup"><span data-stu-id="0a587-105">These add substantial additional security.</span></span> <span data-ttu-id="0a587-106">Microsoft proporciona un conjunto de directivas de acceso condicional de línea base que se recomiendan para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="0a587-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="0a587-107">Las directivas de línea base son un conjunto de directivas predefinidas que ayudan a proteger a las organizaciones frente a muchos ataques comunes.</span><span class="sxs-lookup"><span data-stu-id="0a587-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="0a587-108">Estos ataques comunes pueden incluir aerosol, reproducción y suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="0a587-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="0a587-109">Estas directivas requieren que los administradores y los usuarios escriban una segunda forma de autenticación (denominada autenticación multifactor o MFA) cuando se cumplan ciertas condiciones.</span><span class="sxs-lookup"><span data-stu-id="0a587-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="0a587-110">Por ejemplo, si un usuario de su organización intenta iniciar sesión en Microsoft 365 desde otro país o desde un dispositivo desconocido, es posible que el inicio de sesión se considere arriesgado.</span><span class="sxs-lookup"><span data-stu-id="0a587-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="0a587-111">El usuario debe proporcionar una forma adicional de autenticación (como una huella digital o un código) para demostrar su identidad.</span><span class="sxs-lookup"><span data-stu-id="0a587-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="0a587-112">Actualmente, las directivas de línea base son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="0a587-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="0a587-113">Se configura en el centro de administración de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="0a587-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="0a587-114">**Requerir MFA para los administradores** : requiere multi-factor Authentication para los roles de administrador con más privilegios, incluido el administrador global.</span><span class="sxs-lookup"><span data-stu-id="0a587-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="0a587-115">**Protección del usuario final** : requiere la autenticación multifactor para los usuarios solo cuando un inicio de sesión es arriesgado.</span><span class="sxs-lookup"><span data-stu-id="0a587-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="0a587-116">Configure en el portal de Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="0a587-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="0a587-117">**Bloquear la autenticación heredada** : las aplicaciones cliente antiguas y algunas nuevas aplicaciones no usan protocolos de autenticación más recientes, más seguros.</span><span class="sxs-lookup"><span data-stu-id="0a587-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="0a587-118">Estas aplicaciones antiguas pueden omitir las directivas de acceso condicional y obtener acceso no autorizado a su entorno.</span><span class="sxs-lookup"><span data-stu-id="0a587-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="0a587-119">Esta directiva bloquea el acceso de los clientes que no admiten el acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="0a587-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="0a587-120">**Requerir MFA para la administración de servicios** : requiere multi-factor Authentication para el acceso a las herramientas de administración, incluido Azure portal (donde se configuran las directivas de línea base).</span><span class="sxs-lookup"><span data-stu-id="0a587-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="0a587-121">Microsoft recomienda habilitar todas estas directivas de línea base.</span><span class="sxs-lookup"><span data-stu-id="0a587-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="0a587-122">Una vez habilitadas estas directivas, se pedirá a los administradores y usuarios que se registren para la autenticación multifactor de Azure.</span><span class="sxs-lookup"><span data-stu-id="0a587-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="0a587-123">Para obtener más información acerca de estas directivas, vea [¿Qué son las directivas de línea base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="0a587-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="0a587-124">Exigir MFA</span><span class="sxs-lookup"><span data-stu-id="0a587-124">Require MFA</span></span>

<span data-ttu-id="0a587-125">Para requerir que todos los usuarios inicien sesión con un segundo formulario de identificador:</span><span class="sxs-lookup"><span data-stu-id="0a587-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="0a587-126">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> y elija **configurar**.</span><span class="sxs-lookup"><span data-stu-id="0a587-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="0a587-127">En la página Configuración, elija **Ver** en la tarjeta para **crear un inicio de sesión más seguro** .</span><span class="sxs-lookup"><span data-stu-id="0a587-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![Haga que el inicio de sesión sea una tarjeta más segura.](media/setupmfa.png)
3. <span data-ttu-id="0a587-129">En la página hacer que **el inicio de**sesión sea más seguro, elija introducción.</span><span class="sxs-lookup"><span data-stu-id="0a587-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="0a587-130">En el panel reforzar la seguridad de inicio de sesión, active las casillas situadas junto a **requerir autenticación multifactor para administradores** y **requerir que los usuarios se registren para la autenticación multifactor y bloquear el acceso si se detecta un riesgo**.</span><span class="sxs-lookup"><span data-stu-id="0a587-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="0a587-131">Asegúrese de excluir la cuenta de administrador de [emergencia](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) o "ruptura de cristal" del requisito de MFA en el cuadro **Buscar usuarios** .</span><span class="sxs-lookup"><span data-stu-id="0a587-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![Página de seguridad de complementos de refuerzo.](media/requiremfa.png)

5. <span data-ttu-id="0a587-133">Elija **crear Directiva** en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="0a587-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="0a587-134">Configurar directivas de línea base</span><span class="sxs-lookup"><span data-stu-id="0a587-134">Set up baseline policies</span></span>

1. <span data-ttu-id="0a587-135">Vaya a [Azure portal](https://portal.azure.com)y navegue a **Azure Active Directory** \> **Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="0a587-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="0a587-136">Las directivas de línea base se enumeran en la página y puede ver que **requieren MFA para los administradores** y la **protección del usuario final** ya están habilitados después de completar los pasos de [requerir MFA](#require-mfa).</span><span class="sxs-lookup"><span data-stu-id="0a587-136">The baseline policies are listed on the page, and you can see that **Require MFA for admins** and **End user protection** are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![Página donde se enumeran las directivas de línea base para el acceso condicional.](media/casettings.png)
2. <span data-ttu-id="0a587-138">Consulte las siguientes instrucciones específicas para cada directiva:</span><span class="sxs-lookup"><span data-stu-id="0a587-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="0a587-139">Requerir MFA para los administradores</span><span class="sxs-lookup"><span data-stu-id="0a587-139">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [<span data-ttu-id="0a587-140">Requerir MFA para los usuarios</span><span class="sxs-lookup"><span data-stu-id="0a587-140">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="0a587-141">Bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="0a587-141">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="0a587-142">Requerir MFA para la administración de servicios</span><span class="sxs-lookup"><span data-stu-id="0a587-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="0a587-143">Puede configurar directivas adicionales, como requerir aplicaciones cliente aprobadas.</span><span class="sxs-lookup"><span data-stu-id="0a587-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="0a587-144">Para obtener más información, consulte la [documentación de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="0a587-144">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
