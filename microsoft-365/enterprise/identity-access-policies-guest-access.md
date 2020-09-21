---
title: 'Directivas de acceso a dispositivos e identidades para permitir el acceso de B2B a invitado y externo: Microsoft 365 para Enterprise | Microsoft docs'
description: Describe el acceso condicional recomendado y las directivas relacionadas para proteger el acceso de invitados y usuarios externos.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 6d6562f528b36acdfbc28da9647d3356a0f585af
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132163"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="908c4-103">Directivas para permitir el acceso de B2B y de invitado externo</span><span class="sxs-lookup"><span data-stu-id="908c4-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="908c4-104">En este artículo se describe cómo ajustar las directivas de identidad y acceso de dispositivos comunes recomendadas para permitir el acceso de usuarios externos y invitados que tienen una cuenta de Azure Active Directory (Azure AD) negocio a negocio (B2B).</span><span class="sxs-lookup"><span data-stu-id="908c4-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="908c4-105">Esta guía se basa en las [directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="908c4-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="908c4-106">Estas recomendaciones están diseñadas para aplicarse al nivel de **línea base** de protección.</span><span class="sxs-lookup"><span data-stu-id="908c4-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="908c4-107">Sin embargo, también puede ajustar las recomendaciones en función de la granularidad de sus necesidades de protección **sensible** y **altamente regulada** .</span><span class="sxs-lookup"><span data-stu-id="908c4-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="908c4-108">Al proporcionar una ruta de acceso para las cuentas B2B para autenticarse con el inquilino de Azure AD, no se concede a estas cuentas acceso a todo el entorno.</span><span class="sxs-lookup"><span data-stu-id="908c4-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="908c4-109">Los usuarios de B2B y sus cuentas solo tienen acceso a los recursos compartidos con ellos (como archivos) dentro de los servicios concedidos en las directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="908c4-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="908c4-110">Actualización de las directivas comunes para permitir y proteger el acceso de invitados y externos</span><span class="sxs-lookup"><span data-stu-id="908c4-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="908c4-111">Para proteger el acceso de invitados y externos con cuentas B2B de Azure AD, en el siguiente diagrama se ilustran las directivas que se deben agregar o actualizar desde las directivas comunes de identidad y acceso a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="908c4-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span> 

<span data-ttu-id="908c4-112">[![Resumen de las actualizaciones de directivas para proteger el acceso de invitado](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="908c4-112">[![Summary of policy updates for protecting guest access](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="908c4-113">Ver una versión más grande de esta imagen</span><span class="sxs-lookup"><span data-stu-id="908c4-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="908c4-114">En la siguiente tabla se enumeran las directivas que es necesario crear y actualizar.</span><span class="sxs-lookup"><span data-stu-id="908c4-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="908c4-115">Las directivas comunes vinculan a las instrucciones de configuración asociadas en el artículo [Common Identity and Device Access Policies](identity-access-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="908c4-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="908c4-116">Nivel de protección</span><span class="sxs-lookup"><span data-stu-id="908c4-116">Protection level</span></span>|<span data-ttu-id="908c4-117">Directivas</span><span class="sxs-lookup"><span data-stu-id="908c4-117">Policies</span></span>|<span data-ttu-id="908c4-118">Más información</span><span class="sxs-lookup"><span data-stu-id="908c4-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="908c4-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="908c4-119">**Baseline**</span></span>|[<span data-ttu-id="908c4-120">Requerir MFA siempre para los usuarios externos y invitados</span><span class="sxs-lookup"><span data-stu-id="908c4-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="908c4-121">Crear esta nueva Directiva y configurar:</span><span class="sxs-lookup"><span data-stu-id="908c4-121">Create this new policy and configure:</span></span> <ul><li> <span data-ttu-id="908c4-122">Para las **asignaciones > usuarios y grupos > incluir**, elija **Seleccionar usuarios y grupos**y, a continuación, seleccione **todos los usuarios externos y invitados**.</span><span class="sxs-lookup"><span data-stu-id="908c4-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span> </li><li> <span data-ttu-id="908c4-123">Para **las asignaciones > condiciones > inicio de sesión**, deje todas las opciones desactivadas para exigir siempre la autenticación multifactor (MFA).</span><span class="sxs-lookup"><span data-stu-id="908c4-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li>|
|        |[<span data-ttu-id="908c4-124">Requerir MFA cuando el riesgo de inicio de sesión sea *medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="908c4-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="908c4-125">Modifique esta directiva para excluir usuarios externos y invitados.</span><span class="sxs-lookup"><span data-stu-id="908c4-125">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="908c4-126">Exigir equipos PC compatibles</span><span class="sxs-lookup"><span data-stu-id="908c4-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="908c4-127">Modifique esta directiva para excluir usuarios externos y invitados.</span><span class="sxs-lookup"><span data-stu-id="908c4-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="908c4-128">Para incluir o excluir usuarios de invitado y externos en directivas de acceso condicional, para **asignaciones > usuarios y grupos > incluir** o **excluir**, compruebe **todos los usuarios externos y de invitado**.</span><span class="sxs-lookup"><span data-stu-id="908c4-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![captura de pantalla de controles para excluir usuarios externos y invitados](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="908c4-130">Más información</span><span class="sxs-lookup"><span data-stu-id="908c4-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="908c4-131">Invitado y acceso externo con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="908c4-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="908c4-132">Microsoft Teams define lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="908c4-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="908c4-133">El **acceso de invitado** usa una cuenta B2B de Azure ad que puede agregarse como miembro de un equipo y tener todo el acceso con permisos a las comunicaciones y recursos del equipo.</span><span class="sxs-lookup"><span data-stu-id="908c4-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="908c4-134">El **acceso externo** es para un usuario externo que no tiene una cuenta B2B.</span><span class="sxs-lookup"><span data-stu-id="908c4-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="908c4-135">El acceso externo puede incluir invitaciones y participación en las llamadas, chats y reuniones, pero no incluye la pertenencia al equipo ni el acceso a los recursos del equipo.</span><span class="sxs-lookup"><span data-stu-id="908c4-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="908c4-136">Para obtener más información, consulte [esta comparación entre Guest y external Access for Teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="908c4-136">For more information, see [this comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="908c4-137">Las directivas de acceso condicional solo se aplican al acceso de invitado en Microsoft Teams porque hay una cuenta B2B de Azure AD correspondiente.</span><span class="sxs-lookup"><span data-stu-id="908c4-137">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<span data-ttu-id="908c4-138">Consulte [recomendaciones de directivas para proteger los equipos chats, grupos y archivos](teams-access-policies.md) para obtener más información sobre cómo proteger las directivas de acceso a dispositivos e identidades para Teams.</span><span class="sxs-lookup"><span data-stu-id="908c4-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

<!--
ount treats guest and external users that have an Azure AD B2B account differently than external access  .


to a meeting, call, or chat with


differentiates between guest users and external users within the app. Guest users have Azure AD B2B accounts and can be added to teams. External users can only participate in calls, chats, and meetings. 
--> 

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="908c4-139">Requerir MFA siempre para los usuarios externos y invitados</span><span class="sxs-lookup"><span data-stu-id="908c4-139">Require MFA always for guest and external users</span></span>
<span data-ttu-id="908c4-140">Esta directiva solicita a los invitados que se registren en MFA en su espacio empresarial, independientemente de si están registrados para MFA en su inquilino de inicio.</span><span class="sxs-lookup"><span data-stu-id="908c4-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="908c4-141">Al obtener acceso a los recursos de su espacio empresarial, los usuarios externos y invitados deben usar MFA para cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="908c4-141">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="908c4-142">Exclusión de invitados y usuarios externos de la MFA basada en riesgos</span><span class="sxs-lookup"><span data-stu-id="908c4-142">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="908c4-143">Si bien las organizaciones pueden aplicar directivas basadas en riesgos para los usuarios de B2B mediante Azure AD Identity Protection, hay limitaciones en la implementación de la protección de identidad de Azure AD para los usuarios de colaboración B2B en un directorio de recursos debido a la identidad existente en su directorio principal.</span><span class="sxs-lookup"><span data-stu-id="908c4-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="908c4-144">Debido a estas limitaciones, Microsoft recomienda excluir a los usuarios invitados de las directivas de MFA basadas en riesgos y requerir que estos usuarios usen siempre la MFA.</span><span class="sxs-lookup"><span data-stu-id="908c4-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="908c4-145">Para obtener más información, vea [limitaciones de la protección de identidad para usuarios de colaboración B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="908c4-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="908c4-146">Excluir usuarios externos y invitados de la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="908c4-146">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="908c4-147">Solo una organización puede administrar un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="908c4-147">Only one organization can manage a device.</span></span> <span data-ttu-id="908c4-148">Si no excluye a los usuarios externos y invitados de las directivas que requieran el cumplimiento de dispositivos, estas directivas bloquearán a estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="908c4-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="908c4-149">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="908c4-149">Next step</span></span>

![Paso 4: directivas para las aplicaciones en la nube de Microsoft 365](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="908c4-151">Configure las directivas de acceso condicional para:</span><span class="sxs-lookup"><span data-stu-id="908c4-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="908c4-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="908c4-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="908c4-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="908c4-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="908c4-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="908c4-154">SharePoint</span></span>](secure-email-recommended-policies.md)

