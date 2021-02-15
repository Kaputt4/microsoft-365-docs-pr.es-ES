---
title: 'Directivas de acceso a dispositivos e identidades para permitir el acceso B2B de usuarios invitados y externos: Microsoft 365 para empresas | Microsoft Docs'
description: Describe el acceso condicional recomendado y las directivas relacionadas para proteger el acceso de invitados y usuarios externos.
ms.prod: m365-security
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932615"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="fcfd1-103">Directivas para permitir el acceso de invitado y el acceso de usuarios externos B2B</span><span class="sxs-lookup"><span data-stu-id="fcfd1-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="fcfd1-104">En este artículo se describe cómo ajustar las directivas recomendadas de acceso a identidades y dispositivos para permitir el acceso a invitados y usuarios externos que tienen una cuenta de Azure Active Directory (Azure AD) De empresa a empresa (B2B).</span><span class="sxs-lookup"><span data-stu-id="fcfd1-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="fcfd1-105">Esta guía se basa en las directivas comunes [de acceso a dispositivos e identidades.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fcfd1-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="fcfd1-106">Estas recomendaciones están diseñadas para aplicarse al nivel **de línea base** de protección.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="fcfd1-107">Pero también puede ajustar las recomendaciones en función de sus necesidades específicas de protección **confidencial** **y altamente** regulada.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="fcfd1-108">Proporcionar una ruta de acceso para que las cuentas B2B se autentiquen con el inquilino de Azure AD no proporciona a estas cuentas acceso a todo el entorno.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="fcfd1-109">Los usuarios B2B y sus cuentas tienen acceso a servicios y recursos, como archivos, compartidos con ellos mediante la directiva de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="fcfd1-110">Actualización de las directivas comunes para permitir y proteger el acceso de invitados y usuarios externos</span><span class="sxs-lookup"><span data-stu-id="fcfd1-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="fcfd1-111">En este diagrama se muestran las directivas que se agregarán o actualizarán entre las directivas comunes de acceso a dispositivos e identidades, para el acceso de usuarios externos y invitados B2B.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="fcfd1-112">[![Resumen de las actualizaciones de directivas para proteger el acceso de invitados](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="fcfd1-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="fcfd1-113">Ver una versión más grande de esta imagen</span><span class="sxs-lookup"><span data-stu-id="fcfd1-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="fcfd1-114">En la tabla siguiente se enumeran las directivas que debe crear y actualizar.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="fcfd1-115">Las directivas comunes se vinculan a las instrucciones de configuración asociadas en el artículo Directivas comunes de acceso a [dispositivos](identity-access-policies.md) e identidades.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="fcfd1-116">Nivel de protección</span><span class="sxs-lookup"><span data-stu-id="fcfd1-116">Protection level</span></span>|<span data-ttu-id="fcfd1-117">Directivas</span><span class="sxs-lookup"><span data-stu-id="fcfd1-117">Policies</span></span>|<span data-ttu-id="fcfd1-118">Más información</span><span class="sxs-lookup"><span data-stu-id="fcfd1-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="fcfd1-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="fcfd1-119">**Baseline**</span></span>|[<span data-ttu-id="fcfd1-120">Requerir MFA siempre para invitados y usuarios externos</span><span class="sxs-lookup"><span data-stu-id="fcfd1-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="fcfd1-121">Cree esta nueva directiva y configure:</span><span class="sxs-lookup"><span data-stu-id="fcfd1-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="fcfd1-122">Para **Tareas > Usuarios** y grupos > Incluir , elija Seleccionar usuarios y grupos y, a continuación, seleccione Todos los usuarios invitados y **externos.** </span><span class="sxs-lookup"><span data-stu-id="fcfd1-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="fcfd1-123">Para las > de > inicio de sesión, deje todas las opciones **desactivadas** para aplicar siempre la autenticación multifactor (MFA).</span><span class="sxs-lookup"><span data-stu-id="fcfd1-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="fcfd1-124">Requerir MFA cuando el riesgo de inicio de sesión *es medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="fcfd1-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="fcfd1-125">Modifique esta directiva para excluir invitados y usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="fcfd1-126">Exigir equipos PC compatibles</span><span class="sxs-lookup"><span data-stu-id="fcfd1-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="fcfd1-127">Modifique esta directiva para excluir invitados y usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="fcfd1-128">Para incluir o excluir invitados y usuarios externos en las directivas de acceso condicional, para Asignaciones > Usuarios y grupos > Incluir o excluir **,** active Todos los usuarios **invitados** y **externos.**</span><span class="sxs-lookup"><span data-stu-id="fcfd1-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![captura de pantalla de controles para excluir invitados y usuarios externos](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="fcfd1-130">Más información</span><span class="sxs-lookup"><span data-stu-id="fcfd1-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="fcfd1-131">Acceso de invitados y usuarios externos con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fcfd1-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="fcfd1-132">Microsoft Teams define los siguientes usuarios:</span><span class="sxs-lookup"><span data-stu-id="fcfd1-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="fcfd1-133">**El acceso** de invitado usa una cuenta B2B de Azure AD que se puede agregar como miembro de un equipo y tener acceso a las comunicaciones y los recursos del equipo.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="fcfd1-134">**El acceso** externo es para un usuario externo que no tiene una cuenta B2B.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="fcfd1-135">El acceso de usuarios externos incluye invitaciones, llamadas, chats y reuniones, pero no incluye la pertenencia al equipo ni el acceso a los recursos del equipo.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="fcfd1-136">Para obtener más información, vea [la comparación entre invitados y el acceso de usuarios externos para equipos.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="fcfd1-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="fcfd1-137">Para obtener más información sobre cómo proteger las directivas de acceso a dispositivos e identidades para Teams, vea recomendaciones de directivas para proteger [los chats,](teams-access-policies.md)grupos y archivos de Teams.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="fcfd1-138">Requerir MFA siempre para usuarios invitados y externos</span><span class="sxs-lookup"><span data-stu-id="fcfd1-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="fcfd1-139">Esta directiva solicita a los invitados que se registren para MFA en el inquilino, independientemente de si están registrados para MFA en su inquilino principal.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="fcfd1-140">Al obtener acceso a los recursos del espacio empresarial, los invitados y los usuarios externos deben usar MFA para cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="fcfd1-141">Exclusión de invitados y usuarios externos de MFA basada en riesgos</span><span class="sxs-lookup"><span data-stu-id="fcfd1-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="fcfd1-142">Aunque las organizaciones pueden aplicar directivas basadas en riesgos para los usuarios de B2B mediante Azure AD Identity Protection, existen limitaciones en la implementación de Azure AD Identity Protection para usuarios de colaboración B2B en un directorio de recursos debido a su identidad existente en su directorio principal.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="fcfd1-143">Debido a estas limitaciones, Microsoft recomienda excluir a los invitados de las directivas de MFA basadas en riesgos y exigir que estos usuarios siempre usen MFA.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="fcfd1-144">Para obtener más información, vea [Limitaciones de Identity Protection para usuarios de colaboración B2B.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="fcfd1-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="fcfd1-145">Exclusión de invitados y usuarios externos de la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="fcfd1-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="fcfd1-146">Solo una organización puede administrar un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-146">Only one organization can manage a device.</span></span> <span data-ttu-id="fcfd1-147">Si no excluye invitados y usuarios externos de las directivas que requieren el cumplimiento del dispositivo, estas directivas bloquearán estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="fcfd1-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="fcfd1-148">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="fcfd1-148">Next step</span></span>

![Paso 4: Directivas para aplicaciones en la nube de Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="fcfd1-150">Configure las directivas de acceso condicional para:</span><span class="sxs-lookup"><span data-stu-id="fcfd1-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="fcfd1-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fcfd1-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="fcfd1-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fcfd1-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="fcfd1-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fcfd1-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
