---
title: Configurar directivas de acceso condicional
f1.keywords:
- NOCSH
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo requerir MFA y configurar directivas de acceso condicional para Microsoft 365 para empresas.
ms.openlocfilehash: b13ba9f8c948d9a1209655c44871ca62cb5354dd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044505"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="3baa1-103">Requerir la autenticación multifactor y configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="3baa1-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="3baa1-104">El acceso a los datos se protege con la autenticación multifactor y las directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="3baa1-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="3baa1-105">Esto agrega una seguridad adicional considerable.</span><span class="sxs-lookup"><span data-stu-id="3baa1-105">These add substantial additional security.</span></span> <span data-ttu-id="3baa1-106">Microsoft proporciona un conjunto de directivas de acceso condicional de línea base que se recomiendan para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="3baa1-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="3baa1-107">Las directivas de línea base son un conjunto de directivas predefinidas que ayudan a proteger a las organizaciones contra muchos ataques comunes.</span><span class="sxs-lookup"><span data-stu-id="3baa1-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="3baa1-108">Estos ataques comunes pueden incluir la protección contra contraseñas, la reproducción y la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="3baa1-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="3baa1-109">Estas directivas requieren que los administradores y los usuarios escriban una segunda forma de autenticación (denominada autenticación multifactor o MFA) en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="3baa1-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="3baa1-110">Por ejemplo, si un usuario de su organización intenta iniciar sesión en Microsoft 365 desde un país diferente o desde un dispositivo desconocido, el inicio de sesión puede considerarse arriesgado.</span><span class="sxs-lookup"><span data-stu-id="3baa1-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="3baa1-111">El usuario debe proporcionar una forma adicional de autenticación (como una huella digital o un código) para demostrar su identidad.</span><span class="sxs-lookup"><span data-stu-id="3baa1-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="3baa1-112">Actualmente, las directivas de línea base incluyen las siguientes directivas:</span><span class="sxs-lookup"><span data-stu-id="3baa1-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="3baa1-113">Configurar en el Centro de administración de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="3baa1-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="3baa1-114">**Requerir MFA para administradores:** requiere autenticación multifactor para los roles de administrador con más privilegios, incluido el administrador global.</span><span class="sxs-lookup"><span data-stu-id="3baa1-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="3baa1-115">**Protección del usuario final:** requiere autenticación multifactor para los usuarios solo cuando un inicio de sesión es arriesgado.</span><span class="sxs-lookup"><span data-stu-id="3baa1-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="3baa1-116">Configurar en el portal de Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="3baa1-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="3baa1-117">**Bloquear la autenticación heredada:** las aplicaciones cliente más antiguas y algunas aplicaciones nuevas no usan protocolos de autenticación más recientes y seguros.</span><span class="sxs-lookup"><span data-stu-id="3baa1-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="3baa1-118">Estas aplicaciones anteriores pueden omitir las directivas de acceso condicional y obtener acceso no autorizado a su entorno.</span><span class="sxs-lookup"><span data-stu-id="3baa1-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="3baa1-119">Esta directiva bloquea el acceso de clientes que no admiten el acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="3baa1-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="3baa1-120">**Requerir MFA para la administración de** servicios: requiere autenticación multifactor para obtener acceso a las herramientas de administración, incluido Azure Portal (donde se configuran las directivas de línea base).</span><span class="sxs-lookup"><span data-stu-id="3baa1-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="3baa1-121">Se recomienda habilitar todas estas directivas de línea base.</span><span class="sxs-lookup"><span data-stu-id="3baa1-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="3baa1-122">Una vez habilitadas estas directivas, se pedirá a los administradores y usuarios que se registren para la autenticación multifactor de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3baa1-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="3baa1-123">Para obtener más información acerca de estas directivas, vea [¿Qué son las directivas de línea base?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="3baa1-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="3baa1-124">Requerimiento de la MFA</span><span class="sxs-lookup"><span data-stu-id="3baa1-124">Require MFA</span></span>

<span data-ttu-id="3baa1-125">Para requerir que todos los usuarios inicien sesión con una segunda forma de identificador:</span><span class="sxs-lookup"><span data-stu-id="3baa1-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="3baa1-126">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> y elija **Configurar.**</span><span class="sxs-lookup"><span data-stu-id="3baa1-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="3baa1-127">En la página de instalación, elija **Ver** en la tarjeta de inicio de **sesión más** segura.</span><span class="sxs-lookup"><span data-stu-id="3baa1-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![Haga que el inicio de sesión sea más seguro.](../media/setupmfa.png)
3. <span data-ttu-id="3baa1-129">On the Make sign-in more secure page, choose **Get started**.</span><span class="sxs-lookup"><span data-stu-id="3baa1-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="3baa1-130">En el panel Reforzar la seguridad de inicio de sesión, active las **casillas situadas** junto a Requerir autenticación multifactor para los administradores y Requerir que los usuarios se registren para la autenticación multifactor y bloquee el acceso si se detecta un **riesgo.**</span><span class="sxs-lookup"><span data-stu-id="3baa1-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="3baa1-131">Asegúrese de excluir la cuenta de [administrador](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) de emergencia o "break-glass" del requisito de MFA en **el** cuadro Buscar usuarios.</span><span class="sxs-lookup"><span data-stu-id="3baa1-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![Reforzar la página de seguridad de inicio de sesión.](../media/requiremfa.png)

5. <span data-ttu-id="3baa1-133">Elija **Crear directiva** en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="3baa1-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="3baa1-134">Configurar directivas de línea base</span><span class="sxs-lookup"><span data-stu-id="3baa1-134">Set up baseline policies</span></span>

1. <span data-ttu-id="3baa1-135">Vaya a [Azure Portal y,](https://portal.azure.com)a continuación, vaya a Acceso condicional de **Azure Active Directory** para crear una nueva \>  **directiva.**</span><span class="sxs-lookup"><span data-stu-id="3baa1-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="3baa1-136">Vea las siguientes instrucciones específicas para cada directiva:</span><span class="sxs-lookup"><span data-stu-id="3baa1-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="3baa1-137">Requerir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="3baa1-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="3baa1-138">Requerir MFA para los usuarios</span><span class="sxs-lookup"><span data-stu-id="3baa1-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="3baa1-139">Bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="3baa1-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="3baa1-140">Requerir MFA para la administración de servicios</span><span class="sxs-lookup"><span data-stu-id="3baa1-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="3baa1-141">Las directivas de vista previa ya no existen y los usuarios tendrán que crear sus propias directivas.</span><span class="sxs-lookup"><span data-stu-id="3baa1-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="3baa1-142">Puedes configurar directivas adicionales, como requerir aplicaciones cliente aprobadas.</span><span class="sxs-lookup"><span data-stu-id="3baa1-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="3baa1-143">Para obtener más información, consulte la [documentación de acceso condicional.](https://docs.microsoft.com/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="3baa1-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
