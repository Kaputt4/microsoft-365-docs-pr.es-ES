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
description: Obtenga información sobre cómo configurar la autenticación multifactor para su organización.
monikerRange: o365-worldwide
ms.openlocfilehash: 893a4ae535dfb781a4f77ee57c0ead40fda8454f
ms.sourcegitcommit: 185d62f41f6b173894ba6e3e87b11b2b5d02db58
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "44340779"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="02dc4-103">Configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="02dc4-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="02dc4-104">En función de sus conocimientos de [multi-factor Authentication (MFA) y su compatibilidad en Microsoft 365](multi-factor-authentication-microsoft-365.md), es el momento de configurarlo y distribuirlo en su organización.</span><span class="sxs-lookup"><span data-stu-id="02dc4-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="02dc4-105">Antes de comenzar, determine si estas condiciones especiales se aplican a usted y realice las acciones adecuadas:</span><span class="sxs-lookup"><span data-stu-id="02dc4-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="02dc4-106">Si tiene clientes de Office 2013 en dispositivos Windows, [habilite la autenticación moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="02dc4-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="02dc4-107">Si tiene servicios de directorio de terceros con los servicios de Federación de Active Directory (AD FS), configure el servidor de Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="02dc4-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="02dc4-108">Para obtener más información [, vea escenarios avanzados con la autenticación multifactor de Azure y soluciones de VPN de otros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) fabricantes.</span><span class="sxs-lookup"><span data-stu-id="02dc4-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="02dc4-109">Paso 1: decidir el método de exigir a los usuarios que usen la MFA</span><span class="sxs-lookup"><span data-stu-id="02dc4-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

<span data-ttu-id="02dc4-110">Hay tres formas de requerir que los usuarios usen MFA para iniciar sesión. Consulte [compatibilidad con MFA en Microsoft 365](multi-factor-authentication-microsoft-365.md) para obtener información detallada.</span><span class="sxs-lookup"><span data-stu-id="02dc4-110">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="02dc4-111">Valores predeterminados de seguridad (recomendado para pequeñas empresas)</span><span class="sxs-lookup"><span data-stu-id="02dc4-111">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="02dc4-112">Si compró la suscripción o la versión de prueba después del 21 de octubre de 2019 y se le solicita inesperadamente la MFA, los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="02dc4-112">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="02dc4-113">Todas las nuevas suscripciones de Microsoft 365 tendrán habilitada la seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="02dc4-113">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="02dc4-114">Esto significa que todos los usuarios tendrán que configurar MFA e instalar la aplicación Microsoft Authenticator en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="02dc4-114">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="02dc4-115">Todos los usuarios deben usar la aplicación Microsoft Authenticator como método de comprobación adicional y la autenticación heredada está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="02dc4-115">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="02dc4-116">Directivas de acceso condicional (recomendado para empresas)</span><span class="sxs-lookup"><span data-stu-id="02dc4-116">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="02dc4-117">Los usuarios eligen el método de verificación adicional durante el registro de MFA.</span><span class="sxs-lookup"><span data-stu-id="02dc4-117">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="02dc4-118">Cuenta por usuario (no recomendado)</span><span class="sxs-lookup"><span data-stu-id="02dc4-118">Per-user account (not recommended)</span></span>

  <span data-ttu-id="02dc4-119">Los usuarios eligen el método de verificación adicional durante el registro de MFA.</span><span class="sxs-lookup"><span data-stu-id="02dc4-119">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="02dc4-120">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="02dc4-120">Step 2.</span></span> <span data-ttu-id="02dc4-121">Probar la MFA en los usuarios piloto</span><span class="sxs-lookup"><span data-stu-id="02dc4-121">Test MFA on your pilot users</span></span>

<span data-ttu-id="02dc4-122">Si usa directivas de acceso condicional o MFA por usuario (no recomendado), seleccione usuarios piloto de la empresa u organización para probar el registro de MFA y los inicios de sesión. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02dc4-122">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="02dc4-123">Para las directivas de acceso condicional, cree un grupo de usuarios piloto y una directiva que requiera MFA para los miembros del grupo y para todas las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="02dc4-123">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="02dc4-124">A continuación, agregue las cuentas del usuario piloto al grupo.</span><span class="sxs-lookup"><span data-stu-id="02dc4-124">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="02dc4-125">Para la MFA por usuario, habilite MFA para las cuentas de usuario de los usuarios piloto una vez.</span><span class="sxs-lookup"><span data-stu-id="02dc4-125">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="02dc4-126">Trabaje con los usuarios de la prueba piloto para resolver las preguntas y los problemas que se deben cumplir para preparar una implementación fluida en su organización.</span><span class="sxs-lookup"><span data-stu-id="02dc4-126">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="02dc4-127">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="02dc4-127">Step 3.</span></span> <span data-ttu-id="02dc4-128">Informar a su organización de que se va a provenir MFA</span><span class="sxs-lookup"><span data-stu-id="02dc4-128">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="02dc4-129">Use notificaciones de correo electrónico, pósters de vestíbulos, reuniones de equipo o entrenamiento formal para asegurarse de que sus empleados entienden:</span><span class="sxs-lookup"><span data-stu-id="02dc4-129">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="02dc4-130">Por qué se necesita MFA para iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="02dc4-130">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="02dc4-131">Cómo registrar el método de verificación adicional</span><span class="sxs-lookup"><span data-stu-id="02dc4-131">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="02dc4-132">Cómo iniciar sesión después del registro</span><span class="sxs-lookup"><span data-stu-id="02dc4-132">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="02dc4-133">Cómo cambiar el método de verificación adicional</span><span class="sxs-lookup"><span data-stu-id="02dc4-133">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="02dc4-134">Cómo tratar con situaciones como un nuevo teléfono inteligente</span><span class="sxs-lookup"><span data-stu-id="02dc4-134">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="02dc4-135">Y, lo que es más importante, asegúrese de que sus empleados entienden ***Cuándo se va a imponer el requisito de MFA*** para que no les sorprende.</span><span class="sxs-lookup"><span data-stu-id="02dc4-135">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="02dc4-136">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="02dc4-136">Step 4.</span></span> <span data-ttu-id="02dc4-137">Implementar el requisito de MFA en la organización o los usuarios</span><span class="sxs-lookup"><span data-stu-id="02dc4-137">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="02dc4-138">Basándose en el método de requisito de MFA elegido, implemente la autenticación MFA a los empleados más allá de los evaluadores piloto.</span><span class="sxs-lookup"><span data-stu-id="02dc4-138">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="02dc4-139">Valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="02dc4-139">Security defaults</span></span>

<span data-ttu-id="02dc4-140">Los valores predeterminados de seguridad se habilitan o deshabilitan en el panel de **propiedades** de Azure Active Directory (Azure ad) en Azure portal.</span><span class="sxs-lookup"><span data-stu-id="02dc4-140">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="02dc4-141">Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="02dc4-141">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="02dc4-142">Vaya a la [Página de propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="02dc4-142">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="02dc4-143">En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="02dc4-143">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="02dc4-144">Elija **sí** para habilitar los valores predeterminados de seguridad y **no** para deshabilitar los valores predeterminados de seguridad y, después, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="02dc4-144">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="02dc4-145">Si ha estado usando [directivas de acceso condicional de línea base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), le mostramos cómo pasar a usar los valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="02dc4-145">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="02dc4-146">Vaya a la [Página acceso condicional-directivas](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="02dc4-146">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="02dc4-147">Elija cada directiva de línea base que esté **activada** y establezca la **Directiva de habilitación** en **desactivada**.</span><span class="sxs-lookup"><span data-stu-id="02dc4-147">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="02dc4-148">Vaya a la [Página de propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="02dc4-148">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="02dc4-149">En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="02dc4-149">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="02dc4-150">Elija **sí** para habilitar los valores predeterminados de seguridad y **no** para deshabilitar los valores predeterminados de seguridad y, después, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="02dc4-150">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="02dc4-151">Directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="02dc4-151">Conditional Access policies</span></span>

<span data-ttu-id="02dc4-152">Crear, configurar o habilitar las directivas adecuadas que incluyen el grupo de usuarios que requieren MFA para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="02dc4-152">Create, configure, or enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="02dc4-153">MFA por usuario (no recomendado)</span><span class="sxs-lookup"><span data-stu-id="02dc4-153">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="02dc4-154">Habilitar cuentas de usuario para MFA correspondiente a su implementación.</span><span class="sxs-lookup"><span data-stu-id="02dc4-154">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="02dc4-155">Dar soporte a sus empleados</span><span class="sxs-lookup"><span data-stu-id="02dc4-155">Supporting your employees</span></span>

<span data-ttu-id="02dc4-156">Como los empleados se registran y comienzan a iniciar sesión con MFA, asegúrese de que los especialistas de ti, el Departamento de ti o el Departamento de soporte puedan responder a preguntas y solucionar problemas rápidamente.</span><span class="sxs-lookup"><span data-stu-id="02dc4-156">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="02dc4-157">Consulte este artículo para obtener [información acerca de la solución de problemas de inicios de sesión de MFA](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="02dc4-157">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


