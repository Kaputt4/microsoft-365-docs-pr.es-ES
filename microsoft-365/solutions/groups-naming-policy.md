---
title: Microsoft 365 de nomenclatura de grupos
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
recommendations: false
description: Obtenga información sobre cómo crear una directiva de nomenclatura para Microsoft 365 grupos.
ms.openlocfilehash: 5ab5f252e2b81470413b4efea17b131613aabc18
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538176"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="5c9bb-103">Microsoft 365 de nomenclatura de grupos</span><span class="sxs-lookup"><span data-stu-id="5c9bb-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="5c9bb-104">Puede usar una directiva de nomenclatura de grupo para aplicar una estrategia de nomenclatura coherente para los grupos creados por usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="5c9bb-105">Una directiva de nomenclatura puede ayudarle a usted y a los usuarios a identificar la función del grupo, la pertenencia, la región geográfica o quién creó el grupo.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="5c9bb-106">La directiva de nomenclatura también puede ayudar a clasificar grupos en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="5c9bb-107">Puede usar la directiva para impedir que se usen palabras específicas en nombres de grupo y alias.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="5c9bb-108">La directiva de nomenclatura se aplica a los grupos que se crean en todas las cargas de trabajo de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span><span class="sxs-lookup"><span data-stu-id="5c9bb-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="5c9bb-109">Se aplica tanto al nombre del grupo como al alias de grupo.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="5c9bb-110">También se aplica cuando un usuario crea un grupo y cuando se edita el nombre, el alias, la descripción o el avatar del grupo para un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-110">It also gets applied when a user creates a group and when the group name, alias, description, or avatar is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="5c9bb-111">Una Microsoft 365 de nomenclatura de grupos solo se aplica a Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="5c9bb-112">No se aplica a los grupos de distribución creados en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="5c9bb-113">Para crear una directiva de nomenclatura para grupos de distribución, vea [Create a distribution group naming policy](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="5c9bb-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="5c9bb-114">La directiva de nomenclatura de grupo consta de las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="5c9bb-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="5c9bb-115">**Directiva de nomenclatura prefix-suffix:** puede usar prefijos o sufijos para definir la convención de nomenclatura de grupos (por ejemplo: "Ingeniería de mi grupo de ESTADOS \_ \_ UNIDOS").</span><span class="sxs-lookup"><span data-stu-id="5c9bb-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="5c9bb-116">Los prefijos o sufijos pueden ser cadenas fijas o atributos de usuario como [Department] que se sustituirán en función del usuario que está creando el grupo.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="5c9bb-117">**Palabras bloqueadas** personalizadas: puede cargar un conjunto de palabras bloqueadas específicas de su organización que se bloquearían en grupos creados por usuarios.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="5c9bb-118">(Por ejemplo: "CEO, Payroll, HR").</span><span class="sxs-lookup"><span data-stu-id="5c9bb-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="5c9bb-119">Requisitos de licencias</span><span class="sxs-lookup"><span data-stu-id="5c9bb-119">Licensing requirements</span></span>

<span data-ttu-id="5c9bb-120">El uso de la directiva de nomenclatura de Azure AD para grupos de Microsoft 365 requiere que posea una licencia de Azure Active Directory Premium P1 o una licencia EDU básica de Azure AD para cada usuario único (incluidos los invitados) que sea miembro de uno o más grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="5c9bb-121">Esto también es necesario para el administrador que crea la directiva de nomenclatura de grupos.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="5c9bb-122">Prefix-Suffix de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="5c9bb-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="5c9bb-123">Los prefijos y sufijos pueden ser cadenas fijas o atributos de usuario.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="5c9bb-124">Cadenas fijas</span><span class="sxs-lookup"><span data-stu-id="5c9bb-124">Fixed strings</span></span>

<span data-ttu-id="5c9bb-125">Puede usar cadenas cortas que pueden ayudarle a diferenciar los grupos de la GAL y la navegación izquierda de las cargas de trabajo de grupo.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="5c9bb-126">Algunos de los sufijos de prefijo comunes son palabras clave como 'Grp \_ Name', ' \# Name', ' \_ Name'</span><span class="sxs-lookup"><span data-stu-id="5c9bb-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="5c9bb-127">Atributos</span><span class="sxs-lookup"><span data-stu-id="5c9bb-127">Attributes</span></span>

<span data-ttu-id="5c9bb-128">Puede usar atributos que pueden ayudar a identificar quién creó el grupo como [Departamento] y dónde se creó desde [País].</span><span class="sxs-lookup"><span data-stu-id="5c9bb-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="5c9bb-129">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="5c9bb-129">Examples:</span></span>

- <span data-ttu-id="5c9bb-130">Policy = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="5c9bb-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="5c9bb-131">Departamento del usuario = Ingeniería</span><span class="sxs-lookup"><span data-stu-id="5c9bb-131">User's department = Engineering</span></span>
- <span data-ttu-id="5c9bb-132">Nombre de grupo creado = "GRP Mi ingeniería de grupo"</span><span class="sxs-lookup"><span data-stu-id="5c9bb-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="5c9bb-133">Los atributos Azure Active Directory (Azure AD) son [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] y [Title].</span><span class="sxs-lookup"><span data-stu-id="5c9bb-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="5c9bb-134">Los atributos de usuario no admitidos se consideran cadenas fijas, por ejemplo [postalCode].</span><span class="sxs-lookup"><span data-stu-id="5c9bb-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="5c9bb-135">No se admiten atributos de extensión ni atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="5c9bb-136">Se recomienda usar atributos que tengan valores rellenados para todos los usuarios de la organización y que no usen atributos con valores más largos.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="5c9bb-137">Aspectos a tener en cuenta</span><span class="sxs-lookup"><span data-stu-id="5c9bb-137">Things to look out for</span></span>

- <span data-ttu-id="5c9bb-138">Durante la creación de directivas, la longitud total de la cadena de prefijos y sufijos está restringida a 53 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="5c9bb-139">Los prefijos y sufijos pueden contener caracteres especiales admitidos en el nombre del grupo y el alias de grupo.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="5c9bb-140">Cuando los prefijos y sufijos contienen caracteres especiales que no están permitidos en el alias de grupo, solo se aplican al nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="5c9bb-141">Por lo tanto, en este caso, los prefijos y sufijos aplicados al nombre de grupo serían diferentes de los que se aplican al alias de grupo.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5c9bb-142">Se permite un punto (.) o un guión (-) en cualquier lugar del nombre del grupo, excepto al principio o al final del nombre.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="5c9bb-143">Se permite un carácter de subrayado (_) en cualquier lugar del nombre del grupo, incluso al principio o al final del nombre.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="5c9bb-144">Si usa grupos Yammer Office 365 conectados, evite usar los siguientes caracteres en la directiva de nomenclatura: @, \# , \[ , , \] \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="5c9bb-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="5c9bb-145">Si estos caracteres están en la directiva de nomenclatura, los usuarios Yammer no podrán crear grupos.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="5c9bb-146">Use cadenas cortas como sufijo.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="5c9bb-147">Use atributos con valores.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-147">Use attributes with values.</span></span>
> - <span data-ttu-id="5c9bb-148">No seas demasiado creativo, la longitud total del nombre tiene un máximo de 264 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="5c9bb-149">Upload palabras bloqueadas específicas de la organización para restringir el uso.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="5c9bb-150">Palabras bloqueadas personalizadas</span><span class="sxs-lookup"><span data-stu-id="5c9bb-150">Custom blocked words</span></span>

<span data-ttu-id="5c9bb-151">Puede escribir una lista separada por comas de palabras bloqueadas que se bloquearán en nombres de grupo y alias.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="5c9bb-152">No se llevan a cabo búsquedas de subcadena; Específicamente, se requiere una coincidencia exacta entre el nombre especificado por el usuario y las palabras bloqueadas personalizadas para desencadenar un error.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="5c9bb-153">**Aspectos que debe tener en cuenta:**</span><span class="sxs-lookup"><span data-stu-id="5c9bb-153">**Things to look out for**:</span></span>

- <span data-ttu-id="5c9bb-154">Las palabras bloqueadas no tienen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="5c9bb-155">Cuando un usuario escribe una palabra bloqueada, el cliente de grupo mostrará un mensaje de error con la palabra bloqueada.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="5c9bb-156">No hay restricciones de caracteres en las palabras bloqueadas usadas.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="5c9bb-157">Hay un límite de 5000 palabras que se pueden establecer como palabras bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="5c9bb-158">Reemplazo de administrador</span><span class="sxs-lookup"><span data-stu-id="5c9bb-158">Admin override</span></span>

<span data-ttu-id="5c9bb-159">Algunos administradores están exentos de estas directivas, en todas las cargas de trabajo de grupo y puntos de conexión, para que puedan crear grupos con estas palabras bloqueadas y con sus convenciones de nomenclatura deseadas.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="5c9bb-160">A continuación se muestra la lista de roles de administrador exentos de la directiva de nomenclatura de grupo.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="5c9bb-161">Administrador global</span><span class="sxs-lookup"><span data-stu-id="5c9bb-161">Global admin</span></span>

- <span data-ttu-id="5c9bb-162">Soporte técnico de nivel 1 de partner</span><span class="sxs-lookup"><span data-stu-id="5c9bb-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="5c9bb-163">Soporte técnico de nivel 2 de partner</span><span class="sxs-lookup"><span data-stu-id="5c9bb-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="5c9bb-164">Administrador de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="5c9bb-164">User account admin</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="5c9bb-165">Cómo configurar la directiva de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="5c9bb-165">How to set up the naming policy</span></span>

<span data-ttu-id="5c9bb-166">Para configurar una directiva de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="5c9bb-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="5c9bb-167">En [Azure Active Directory](https://aad.portal.azure.com), en **Administrar**, haga clic en **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="5c9bb-168">En **Configuración**, haga clic **en Directiva de nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="5c9bb-169">Elija la **pestaña Directiva de nomenclatura de** grupo.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="5c9bb-170">En **Directiva actual,** elija si desea requerir un prefijo o sufijo o ambos, y active las casillas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="5c9bb-171">Elija entre **Atributo** y **Cadena** para cada línea y, a continuación, especifique el atributo o cadena.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="5c9bb-172">Cuando haya agregado los prefijos y sufijos que necesita, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5c9bb-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Captura de pantalla de la configuración de directiva de nomenclatura de grupos en Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="5c9bb-174">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5c9bb-174">Related topics</span></span>

[<span data-ttu-id="5c9bb-175">Planeación paso a paso de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="5c9bb-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="5c9bb-176">Crear el plan de gobierno de colaboración</span><span class="sxs-lookup"><span data-stu-id="5c9bb-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="5c9bb-177">Cmdlets de Azure Active Directory para configurar configuraciones de grupo</span><span class="sxs-lookup"><span data-stu-id="5c9bb-177">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/enterprise-users/groups-settings-cmdlets)