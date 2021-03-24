---
title: 'Directivas de acceso a dispositivos y identidades para permitir el acceso B2B de usuarios invitados y externos: Microsoft 365 para empresas | Microsoft Docs'
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
ms.openlocfilehash: 9d3a47752efc86c8ced32905bda851b7d8157f82
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071387"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="77d81-103">Directivas para permitir el acceso de invitado y el acceso de usuarios externos B2B</span><span class="sxs-lookup"><span data-stu-id="77d81-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="77d81-104">En este artículo se describe cómo ajustar las directivas recomendadas de acceso a identidades y dispositivos para permitir el acceso a invitados y usuarios externos que tienen una cuenta de Azure Active Directory (Azure AD) empresa a empresa (B2B).</span><span class="sxs-lookup"><span data-stu-id="77d81-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="77d81-105">Esta guía se basa en las directivas [comunes de acceso a dispositivos y identidades.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="77d81-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="77d81-106">Estas recomendaciones están diseñadas para aplicarse al nivel **de protección** de línea base.</span><span class="sxs-lookup"><span data-stu-id="77d81-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="77d81-107">Pero también puede ajustar las recomendaciones en función de sus necesidades específicas de protección **confidencial** **y altamente** regulada.</span><span class="sxs-lookup"><span data-stu-id="77d81-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="77d81-108">Proporcionar una ruta de acceso para que las cuentas B2B se autentiquen con el inquilino de Azure AD no proporciona a estas cuentas acceso a todo el entorno.</span><span class="sxs-lookup"><span data-stu-id="77d81-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="77d81-109">Los usuarios B2B y sus cuentas tienen acceso a servicios y recursos, como archivos, compartidos con ellos mediante la directiva de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="77d81-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="77d81-110">Actualizar las directivas comunes para permitir y proteger el acceso de invitados y usuarios externos</span><span class="sxs-lookup"><span data-stu-id="77d81-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="77d81-111">En este diagrama se muestran las directivas que se agregarán o actualizarán entre las directivas comunes de acceso a dispositivos y identidades, para el acceso de invitado b2B y de usuario externo.</span><span class="sxs-lookup"><span data-stu-id="77d81-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="77d81-112">[![Resumen de las actualizaciones de directivas para proteger el acceso de invitados](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="77d81-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

<span data-ttu-id="77d81-113">En la tabla siguiente se enumeran las directivas que debe crear y actualizar.</span><span class="sxs-lookup"><span data-stu-id="77d81-113">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="77d81-114">Las directivas comunes se vinculan a las instrucciones de configuración asociadas en [el artículo Identidad común y directivas de acceso a dispositivos.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="77d81-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="77d81-115">Nivel de protección</span><span class="sxs-lookup"><span data-stu-id="77d81-115">Protection level</span></span>|<span data-ttu-id="77d81-116">Directivas</span><span class="sxs-lookup"><span data-stu-id="77d81-116">Policies</span></span>|<span data-ttu-id="77d81-117">Más información</span><span class="sxs-lookup"><span data-stu-id="77d81-117">More information</span></span>|
|---|---|---|
|<span data-ttu-id="77d81-118">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="77d81-118">**Baseline**</span></span>|[<span data-ttu-id="77d81-119">Requerir MFA siempre para invitados y usuarios externos</span><span class="sxs-lookup"><span data-stu-id="77d81-119">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="77d81-120">Cree esta nueva directiva y configure:</span><span class="sxs-lookup"><span data-stu-id="77d81-120">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="77d81-121">Para **Asignaciones > Usuarios** y grupos > Incluir , elija **Seleccionar** usuarios y grupos y, a continuación, seleccione Todos los usuarios **invitados y externos.**</span><span class="sxs-lookup"><span data-stu-id="77d81-121">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="77d81-122">Para **las asignaciones > condiciones > inicio** de sesión, deje todas las opciones desactivadas para aplicar siempre la autenticación multifactor (MFA).</span><span class="sxs-lookup"><span data-stu-id="77d81-122">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="77d81-123">Requerir MFA cuando el riesgo de inicio de sesión *es medio* o *alto*</span><span class="sxs-lookup"><span data-stu-id="77d81-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="77d81-124">Modifique esta directiva para excluir invitados y usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="77d81-124">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="77d81-125">Exigir equipos PC compatibles</span><span class="sxs-lookup"><span data-stu-id="77d81-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="77d81-126">Modifique esta directiva para excluir invitados y usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="77d81-126">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="77d81-127">Para incluir o excluir **invitados** y usuarios externos en directivas de acceso condicional, para Asignaciones > Usuarios y grupos > Incluir o **Excluir**, compruebe Todos los usuarios invitados **y externos**.</span><span class="sxs-lookup"><span data-stu-id="77d81-127">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![captura de pantalla de controles para excluir invitados y usuarios externos](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="77d81-129">Más información</span><span class="sxs-lookup"><span data-stu-id="77d81-129">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="77d81-130">Acceso de invitados y usuarios externos con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77d81-130">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="77d81-131">Microsoft Teams define los siguientes usuarios:</span><span class="sxs-lookup"><span data-stu-id="77d81-131">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="77d81-132">**El acceso** de invitado usa una cuenta B2B de Azure AD que se puede agregar como miembro de un equipo y tener acceso a las comunicaciones y recursos del equipo.</span><span class="sxs-lookup"><span data-stu-id="77d81-132">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="77d81-133">**El acceso** externo es para un usuario externo que no tiene una cuenta B2B.</span><span class="sxs-lookup"><span data-stu-id="77d81-133">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="77d81-134">El acceso de usuarios externos incluye invitaciones, llamadas, chats y reuniones, pero no incluye la pertenencia al equipo ni el acceso a los recursos del equipo.</span><span class="sxs-lookup"><span data-stu-id="77d81-134">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="77d81-135">Para obtener más información, vea la [comparación entre invitados y el acceso de usuarios externos para teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="77d81-135">For more information, see the [comparison between guests and external user access for teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="77d81-136">Para obtener más información sobre cómo proteger las directivas de acceso a dispositivos y identidades para Teams, consulta Recomendaciones de directivas para proteger [chats,](teams-access-policies.md)grupos y archivos de Teams.</span><span class="sxs-lookup"><span data-stu-id="77d81-136">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="77d81-137">Requerir MFA siempre para usuarios invitados y externos</span><span class="sxs-lookup"><span data-stu-id="77d81-137">Require MFA always for guest and external users</span></span>

<span data-ttu-id="77d81-138">Esta directiva solicita a los invitados que se registren en MFA en el inquilino, independientemente de si están registrados para MFA en su inquilino principal.</span><span class="sxs-lookup"><span data-stu-id="77d81-138">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="77d81-139">Al obtener acceso a recursos en el inquilino, los invitados y los usuarios externos deben usar MFA para cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="77d81-139">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="77d81-140">Excluir invitados y usuarios externos de MFA basada en riesgos</span><span class="sxs-lookup"><span data-stu-id="77d81-140">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="77d81-141">Aunque las organizaciones pueden aplicar directivas basadas en riesgos para usuarios B2B con Azure AD Identity Protection, existen limitaciones en la implementación de Azure AD Identity Protection para usuarios de colaboración B2B en un directorio de recursos debido a su identidad existente en su directorio principal.</span><span class="sxs-lookup"><span data-stu-id="77d81-141">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="77d81-142">Debido a estas limitaciones, Microsoft recomienda excluir invitados de las directivas de MFA basadas en riesgos y requerir que estos usuarios usen siempre MFA.</span><span class="sxs-lookup"><span data-stu-id="77d81-142">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="77d81-143">Para obtener más información, vea [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span><span class="sxs-lookup"><span data-stu-id="77d81-143">For more information, see [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="77d81-144">Excluir invitados y usuarios externos de la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="77d81-144">Excluding guests and external users from device management</span></span>

<span data-ttu-id="77d81-145">Solo una organización puede administrar un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77d81-145">Only one organization can manage a device.</span></span> <span data-ttu-id="77d81-146">Si no excluyes a los invitados ni a los usuarios externos de las directivas que requieren el cumplimiento de dispositivos, estas directivas bloquearán a estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="77d81-146">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="77d81-147">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="77d81-147">Next step</span></span>

![Paso 4: Directivas para aplicaciones en la nube de Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="77d81-149">Configurar directivas de acceso condicional para:</span><span class="sxs-lookup"><span data-stu-id="77d81-149">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="77d81-150">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77d81-150">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="77d81-151">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="77d81-151">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="77d81-152">SharePoint</span><span class="sxs-lookup"><span data-stu-id="77d81-152">SharePoint</span></span>](sharepoint-file-access-policies.md)