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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Obtenga información sobre cómo configurar la autenticación multifactor para su organización.
monikerRange: o365-worldwide
ms.openlocfilehash: b0fd16fc74319c88a6f91bf56ac96346915c35ac
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049765"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="60132-103">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="60132-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="60132-104">En función de sus conocimientos de [multi-factor Authentication (MFA) y su compatibilidad en Microsoft 365](multi-factor-authentication-microsoft-365.md), es el momento de configurarlo y distribuirlo en su organización.</span><span class="sxs-lookup"><span data-stu-id="60132-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="60132-105">Antes de comenzar, determine si estas condiciones especiales se aplican a usted y realice las acciones adecuadas:</span><span class="sxs-lookup"><span data-stu-id="60132-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="60132-106">Si tiene clientes de Office 2013 en dispositivos Windows, [habilite la autenticación moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="60132-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="60132-107">Si tiene servicios de directorio de terceros con los servicios de Federación de Active Directory (AD FS), configure el servidor de Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="60132-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="60132-108">Para obtener más información [, vea escenarios avanzados con la autenticación multifactor de Azure y soluciones de VPN de otros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) fabricantes.</span><span class="sxs-lookup"><span data-stu-id="60132-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="60132-109">Se pedirá a todos los demás usuarios una autenticación adicional cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="60132-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="60132-110">Para obtener más información, visite [la configuración y el método de verificación de dos factores](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span><span class="sxs-lookup"><span data-stu-id="60132-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="60132-111">Paso 1: decidir el método de exigir a los usuarios que usen la MFA</span><span class="sxs-lookup"><span data-stu-id="60132-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="60132-112">Debe ser un administrador global para configurar o modificar la MFA.</span><span class="sxs-lookup"><span data-stu-id="60132-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="60132-113">Hay tres formas de requerir que los usuarios usen MFA para iniciar sesión. Consulte [compatibilidad con MFA en Microsoft 365](multi-factor-authentication-microsoft-365.md) para obtener información detallada.</span><span class="sxs-lookup"><span data-stu-id="60132-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="60132-114">Valores predeterminados de seguridad (recomendado para pequeñas empresas)</span><span class="sxs-lookup"><span data-stu-id="60132-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="60132-115">Si compró la suscripción o la versión de prueba después del 21 de octubre de 2019 y se le solicita inesperadamente la MFA, los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="60132-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="60132-116">Todas las nuevas suscripciones de Microsoft 365 tendrán habilitada la seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="60132-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="60132-117">Esto significa que todos los usuarios tendrán que configurar MFA e instalar la aplicación Microsoft Authenticator en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="60132-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="60132-118">Todos los usuarios deben usar la aplicación Microsoft Authenticator como método de comprobación adicional y la autenticación heredada está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="60132-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="60132-119">Directivas de acceso condicional (recomendado para empresas)</span><span class="sxs-lookup"><span data-stu-id="60132-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="60132-120">Los usuarios eligen el método de verificación adicional durante el registro de MFA.</span><span class="sxs-lookup"><span data-stu-id="60132-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="60132-121">Cuenta por usuario (no recomendado)</span><span class="sxs-lookup"><span data-stu-id="60132-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="60132-122">Los usuarios eligen el método de verificación adicional durante el registro de MFA.</span><span class="sxs-lookup"><span data-stu-id="60132-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="60132-123">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="60132-123">Step 2.</span></span> <span data-ttu-id="60132-124">Probar la MFA en los usuarios piloto</span><span class="sxs-lookup"><span data-stu-id="60132-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="60132-125">Si usa directivas de acceso condicional o MFA por usuario (no recomendado), seleccione usuarios piloto de la empresa u organización para probar el registro de MFA y los inicios de sesión. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60132-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="60132-126">Para las directivas de acceso condicional, cree un grupo de usuarios piloto y una directiva que requiera MFA para los miembros del grupo y para todas las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="60132-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="60132-127">A continuación, agregue las cuentas del usuario piloto al grupo.</span><span class="sxs-lookup"><span data-stu-id="60132-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="60132-128">Para la MFA por usuario, habilite MFA para las cuentas de usuario de los usuarios piloto una vez.</span><span class="sxs-lookup"><span data-stu-id="60132-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="60132-129">Trabaje con los usuarios de la prueba piloto para resolver las preguntas y los problemas que se deben cumplir para preparar una implementación fluida en su organización.</span><span class="sxs-lookup"><span data-stu-id="60132-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="60132-130">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="60132-130">Step 3.</span></span> <span data-ttu-id="60132-131">Informar a su organización de que se va a provenir MFA</span><span class="sxs-lookup"><span data-stu-id="60132-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="60132-132">Use notificaciones de correo electrónico, pósters de vestíbulos, reuniones de equipo o entrenamiento formal para asegurarse de que sus empleados entienden:</span><span class="sxs-lookup"><span data-stu-id="60132-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="60132-133">Por qué se necesita MFA para iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="60132-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="60132-134">Cómo registrar el método de verificación adicional</span><span class="sxs-lookup"><span data-stu-id="60132-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="60132-135">Cómo iniciar sesión después del registro</span><span class="sxs-lookup"><span data-stu-id="60132-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="60132-136">Cómo cambiar el método de verificación adicional</span><span class="sxs-lookup"><span data-stu-id="60132-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="60132-137">Cómo tratar con situaciones como un nuevo teléfono inteligente</span><span class="sxs-lookup"><span data-stu-id="60132-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="60132-138">Y, lo que es más importante, asegúrese de que sus empleados entienden ***Cuándo se va a imponer el requisito de MFA*** para que no les sorprende.</span><span class="sxs-lookup"><span data-stu-id="60132-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="60132-139">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="60132-139">Step 4.</span></span> <span data-ttu-id="60132-140">Implementar el requisito de MFA en la organización o los usuarios</span><span class="sxs-lookup"><span data-stu-id="60132-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="60132-141">Basándose en el método de requisito de MFA elegido, implemente la autenticación MFA a los empleados más allá de los evaluadores piloto.</span><span class="sxs-lookup"><span data-stu-id="60132-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="60132-142">Valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="60132-142">Security defaults</span></span>

<span data-ttu-id="60132-143">Los valores predeterminados de seguridad se habilitan o deshabilitan en el panel de **propiedades** de Azure Active Directory (Azure ad) en Azure portal.</span><span class="sxs-lookup"><span data-stu-id="60132-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="60132-144">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="60132-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="60132-145">Vaya a la [Página de propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="60132-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="60132-146">En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="60132-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="60132-147">Elija **sí** para habilitar los valores predeterminados de seguridad y **no** para deshabilitar los valores predeterminados de seguridad y, después, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="60132-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="60132-148">Si ha estado usando [directivas de acceso condicional de línea base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), le mostramos cómo pasar a usar los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="60132-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="60132-149">Vaya a la [Página acceso condicional-directivas](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="60132-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="60132-150">Elija cada directiva de línea base que esté **activada** y establezca la **Directiva de habilitación** en **desactivada**.</span><span class="sxs-lookup"><span data-stu-id="60132-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="60132-151">Vaya a la [Página de propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="60132-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="60132-152">En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="60132-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="60132-153">Elija **sí** para habilitar los valores predeterminados de seguridad y **no** para deshabilitar los valores predeterminados de seguridad y, después, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="60132-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="60132-154">Directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="60132-154">Conditional Access policies</span></span>

<span data-ttu-id="60132-155">Crear, configurar y habilitar las directivas adecuadas que incluyen el grupo de usuarios que requieren MFA para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="60132-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="60132-156">MFA por usuario (no recomendado)</span><span class="sxs-lookup"><span data-stu-id="60132-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="60132-157">Habilitar cuentas de usuario para MFA correspondiente a su implementación.</span><span class="sxs-lookup"><span data-stu-id="60132-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="60132-158">Dar soporte a sus empleados</span><span class="sxs-lookup"><span data-stu-id="60132-158">Supporting your employees</span></span>

<span data-ttu-id="60132-159">Como los empleados se registran y comienzan a iniciar sesión con MFA, asegúrese de que los especialistas de ti, el Departamento de ti o el Departamento de soporte puedan responder a preguntas y solucionar problemas rápidamente.</span><span class="sxs-lookup"><span data-stu-id="60132-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="60132-160">Consulte este artículo para obtener [información acerca de la solución de problemas de inicios de sesión de MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="60132-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


