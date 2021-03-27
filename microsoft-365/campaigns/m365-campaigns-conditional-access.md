---
title: Activar valores predeterminados de seguridad
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
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
description: Obtenga información sobre cómo los valores predeterminados de seguridad pueden ayudar a proteger su organización de ataques relacionados con la identidad proporcionando una configuración de seguridad preconfigurada.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398301"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="15cb8-103">Activar valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="15cb8-103">Turn on security defaults</span></span>

<span data-ttu-id="15cb8-104">Los valores predeterminados de seguridad ayudan a proteger su organización de ataques relacionados con la identidad proporcionando una configuración de seguridad preconfigurada que Microsoft administra en nombre de su organización.</span><span class="sxs-lookup"><span data-stu-id="15cb8-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="15cb8-105">Estas opciones incluyen habilitar la autenticación multifactor (MFA) para todos los administradores y cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="15cb8-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="15cb8-106">Para la mayoría de las organizaciones, los valores predeterminados de seguridad ofrecen un buen nivel de seguridad de inicio de sesión adicional.</span><span class="sxs-lookup"><span data-stu-id="15cb8-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="15cb8-107">Para obtener más información acerca de los valores predeterminados de seguridad y las directivas que aplican, vea [¿Cuáles son los valores predeterminados de seguridad?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="15cb8-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="15cb8-108">Si la suscripción se creó el 22 de octubre de 2019 o después, es posible que los valores predeterminados de seguridad se hayan habilitado automáticamente para que compruebe la configuración para &mdash; confirmarla.</span><span class="sxs-lookup"><span data-stu-id="15cb8-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="15cb8-109">Para habilitar los valores predeterminados de seguridad en Azure Active Directory (Azure AD) o para comprobar si ya están habilitados:</span><span class="sxs-lookup"><span data-stu-id="15cb8-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="15cb8-110">Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> con credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="15cb8-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="15cb8-111">En el panel izquierdo, seleccione **Mostrar todo y, a continuación,** en Centros de **administración,** **seleccione Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="15cb8-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="15cb8-112">En el panel izquierdo del Centro de **administración de Azure Active Directory,** seleccione Azure Active **Directory**.</span><span class="sxs-lookup"><span data-stu-id="15cb8-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="15cb8-113">En el menú izquierdo del panel, en la **sección Administrar,** seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="15cb8-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Captura de pantalla del Centro de administración de Azure Active Directory que muestra la ubicación del elemento de menú Propiedades.":::

5. <span data-ttu-id="15cb8-115">En la parte inferior de la **página Propiedades,** seleccione **Administrar valores predeterminados de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="15cb8-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="15cb8-116">En el panel derecho, verá la configuración Habilitar **valores predeterminados de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="15cb8-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="15cb8-117">Si **se** selecciona Sí, los valores predeterminados de seguridad ya están habilitados y no se requiere ninguna acción adicional.</span><span class="sxs-lookup"><span data-stu-id="15cb8-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="15cb8-118">Si los valores predeterminados de seguridad no están habilitados actualmente, seleccione **Sí** para habilitarlos y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="15cb8-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="15cb8-119">Si ha estado usando directivas de acceso condicional, deberá desactivarlas antes de usar valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="15cb8-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="15cb8-120">Puede usar los valores predeterminados de seguridad o las directivas de acceso condicional, pero no puede usar ambas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="15cb8-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="15cb8-121">Considere la posibilidad de usar el acceso condicional</span><span class="sxs-lookup"><span data-stu-id="15cb8-121">Consider using Conditional Access</span></span>

<span data-ttu-id="15cb8-122">Si su organización tiene requisitos de seguridad complejos o necesita un control más detallado sobre las directivas de seguridad, debe considerar el uso del acceso condicional en lugar de los valores predeterminados de seguridad para lograr una posición de seguridad similar o superior.</span><span class="sxs-lookup"><span data-stu-id="15cb8-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="15cb8-123">El acceso condicional le permite crear y definir directivas que reaccionan a eventos de inicio de sesión y solicitan acciones adicionales antes de que un usuario obtenga acceso a una aplicación o servicio.</span><span class="sxs-lookup"><span data-stu-id="15cb8-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="15cb8-124">Las directivas de acceso condicional pueden ser granulares y específicas, lo que permite a los usuarios ser productivos donde y cuando sea, pero también proteger su organización.</span><span class="sxs-lookup"><span data-stu-id="15cb8-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="15cb8-125">Los valores predeterminados de seguridad están disponibles para todos los clientes, mientras que el acceso condicional requiere una licencia para uno de los siguientes planes:</span><span class="sxs-lookup"><span data-stu-id="15cb8-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="15cb8-126">Azure Active Directory Premium P1 o P2</span><span class="sxs-lookup"><span data-stu-id="15cb8-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="15cb8-127">Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="15cb8-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="15cb8-128">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="15cb8-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="15cb8-129">Enterprise Mobility & Security E3 o E5</span><span class="sxs-lookup"><span data-stu-id="15cb8-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="15cb8-130">Si desea usar el acceso condicional para configurar directivas equivalentes a las habilitadas por los valores predeterminados de seguridad, consulte las siguientes guías paso a paso:</span><span class="sxs-lookup"><span data-stu-id="15cb8-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="15cb8-131">Requerir MFA para los administradores</span><span class="sxs-lookup"><span data-stu-id="15cb8-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="15cb8-132">Requerir MFA para la administración de Azure</span><span class="sxs-lookup"><span data-stu-id="15cb8-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="15cb8-133">Bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="15cb8-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="15cb8-134">Requerir MFA para todos los usuarios</span><span class="sxs-lookup"><span data-stu-id="15cb8-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="15cb8-135">[Requerir el registro de MFA de Azure AD:](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) requiere Azure AD Identity Protection, que forma parte de Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="15cb8-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="15cb8-136">Para obtener más información sobre el acceso condicional, vea [¿Qué es el acceso condicional?](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="15cb8-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="15cb8-137">Para obtener más información acerca de cómo crear directivas de acceso condicional, [vea Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span><span class="sxs-lookup"><span data-stu-id="15cb8-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="15cb8-138">Si tiene un plan o una licencia que proporciona acceso condicional pero aún no ha creado ninguna directiva de acceso condicional, puede usar valores predeterminados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="15cb8-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="15cb8-139">Sin embargo, deberá desactivar los valores predeterminados de seguridad antes de poder usar directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="15cb8-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>
