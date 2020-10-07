---
title: Directiva de nomenclatura de grupos de 365 de Microsoft
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
description: Obtenga información sobre cómo crear una directiva de nomenclatura para grupos de Microsoft 365.
ms.openlocfilehash: 55faf5c61d577b35b34923efc7b65457fe46de29
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377610"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="ba386-103">Directiva de nomenclatura de grupos de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba386-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="ba386-104">Puede usar una directiva de nomenclatura de grupos para aplicar una estrategia de nomenclatura coherente para los grupos creados por los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="ba386-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="ba386-105">Una directiva de nomenclatura puede ayudarle a usted y a sus usuarios a identificar la función del grupo, la pertenencia, la región geográfica o el usuario que creó el grupo.</span><span class="sxs-lookup"><span data-stu-id="ba386-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="ba386-106">La Directiva de nomenclatura también puede ayudar a clasificar los grupos de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="ba386-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="ba386-107">Puede usar la Directiva para bloquear palabras específicas para que no se usen en nombres de grupo y alias.</span><span class="sxs-lookup"><span data-stu-id="ba386-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="ba386-108">La Directiva de nomenclatura se aplica a los grupos que se crean en todas las cargas de trabajo de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span><span class="sxs-lookup"><span data-stu-id="ba386-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="ba386-109">Se aplica al nombre del grupo y al alias del grupo.</span><span class="sxs-lookup"><span data-stu-id="ba386-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="ba386-110">Se aplica cuando un usuario crea un grupo y cuando se modifica el nombre o el alias del grupo para un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="ba386-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="ba386-111">Una directiva de nomenclatura de grupo de Microsoft 365 solo se aplica a los grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba386-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="ba386-112">No se aplica a los grupos de distribución creados en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ba386-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="ba386-113">Para crear una directiva de nomenclatura para los grupos de distribución, consulte [Create a Distribution Group naming Policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="ba386-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="ba386-114">La Directiva de nomenclatura de grupos consta de las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="ba386-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="ba386-115">**Directiva de nomenclatura de prefijo-sufijo**: puede usar prefijos o sufijos para definir la Convención de nomenclatura de grupos (por ejemplo: "US \_ My Group \_ Engineering").</span><span class="sxs-lookup"><span data-stu-id="ba386-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="ba386-116">Los prefijos/sufijos pueden ser cadenas fijas o atributos de usuario, como [Departamento], que se sustituirán según el usuario que cree el grupo.</span><span class="sxs-lookup"><span data-stu-id="ba386-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="ba386-117">**Palabras bloqueadas personalizadas**: puede cargar un conjunto de palabras bloqueadas específicas de su organización que podrían bloquearse en grupos creados por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ba386-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="ba386-118">(Por ejemplo: "CEO, nóminas, h").</span><span class="sxs-lookup"><span data-stu-id="ba386-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="ba386-119">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="ba386-119">Licensing requirements</span></span>

<span data-ttu-id="ba386-120">El uso de la Directiva de nomenclatura de Azure AD para los grupos de Microsoft 365 requiere tener que poseer, pero no necesariamente, una licencia de Azure Active Directory Premium P1 o la licencia de Azure AD Basic EDU para cada usuario único (incluidos los invitados) que pertenezca a uno o varios grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba386-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="ba386-121">Esto también es necesario para el administrador que crea la Directiva de nomenclatura de grupos.</span><span class="sxs-lookup"><span data-stu-id="ba386-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="ba386-122">Directiva de nomenclatura prefix-Suffix</span><span class="sxs-lookup"><span data-stu-id="ba386-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="ba386-123">Los prefijos y los sufijos pueden ser cadenas fijas o atributos de usuario.</span><span class="sxs-lookup"><span data-stu-id="ba386-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="ba386-124">Cadenas fijas</span><span class="sxs-lookup"><span data-stu-id="ba386-124">Fixed strings</span></span>

<span data-ttu-id="ba386-125">Puede usar cadenas cortas que pueden ayudarle a diferenciar los grupos de la GAL y la navegación izquierda de las cargas de trabajo de grupo.</span><span class="sxs-lookup"><span data-stu-id="ba386-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="ba386-126">Algunos de los sufijos comunes son palabras clave como "nombre del GRP \_ ", " \# nombre", " \_ nombre".</span><span class="sxs-lookup"><span data-stu-id="ba386-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="ba386-127">Atributos</span><span class="sxs-lookup"><span data-stu-id="ba386-127">Attributes</span></span>

<span data-ttu-id="ba386-128">Puede usar atributos que ayuden a identificar quién ha creado el grupo como [Departamento] y dónde se ha creado desde like [país].</span><span class="sxs-lookup"><span data-stu-id="ba386-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="ba386-129">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="ba386-129">Examples:</span></span>

- <span data-ttu-id="ba386-130">Policy = "GRP [Nombredegrupo] [Departamento]"</span><span class="sxs-lookup"><span data-stu-id="ba386-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="ba386-131">Departamento del usuario = ingeniería</span><span class="sxs-lookup"><span data-stu-id="ba386-131">User's department = Engineering</span></span>
- <span data-ttu-id="ba386-132">Nombre de grupo creado = "grupo de ingeniería de mi grupo"</span><span class="sxs-lookup"><span data-stu-id="ba386-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="ba386-133">Los atributos compatibles de Azure Active Directory (Azure AD) son [Departamento], [compañía], [Office], [StateOrProvince], [CountryOrRegion] y [cargo].</span><span class="sxs-lookup"><span data-stu-id="ba386-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="ba386-134">Los atributos de usuario no admitidos se consideran cadenas fijas, por ejemplo [CódigoPostal].</span><span class="sxs-lookup"><span data-stu-id="ba386-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="ba386-135">Los atributos de extensión y los atributos personalizados no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="ba386-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="ba386-136">Se recomienda usar atributos que tengan valores rellenados para todos los usuarios de la organización y que no usen atributos que tengan valores más largos.</span><span class="sxs-lookup"><span data-stu-id="ba386-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="ba386-137">Aspectos que se deben tener en cuentan</span><span class="sxs-lookup"><span data-stu-id="ba386-137">Things to look out for</span></span>

- <span data-ttu-id="ba386-138">Durante la creación de la Directiva, la longitud total de las cadenas de prefijos y sufijos se limita a 53 caracteres.</span><span class="sxs-lookup"><span data-stu-id="ba386-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="ba386-139">Los prefijos y los sufijos pueden contener caracteres especiales que se admiten en nombre de grupo y alias de grupo.</span><span class="sxs-lookup"><span data-stu-id="ba386-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="ba386-140">Cuando los prefijos y los sufijos contienen caracteres especiales que no se permiten en el alias de grupo, solo se aplican al nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="ba386-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="ba386-141">Por lo tanto, en este caso, los prefijos y los sufijos aplicados al nombre del grupo serían distintos de los que se aplican al alias del grupo.</span><span class="sxs-lookup"><span data-stu-id="ba386-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ba386-142">Se permite un punto (.) o un guión (-) en cualquier lugar del nombre del grupo, excepto al principio o al final del nombre.</span><span class="sxs-lookup"><span data-stu-id="ba386-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="ba386-143">Un carácter de subrayado (_) se permite en cualquier lugar del nombre del grupo, incluido al principio o al final del nombre.</span><span class="sxs-lookup"><span data-stu-id="ba386-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="ba386-144">Si usa los grupos conectados de Yammer Office 365, evite usar los siguientes caracteres en su Directiva de nomenclatura: @, \# , \[ , \] , \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="ba386-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="ba386-145">Si estos caracteres están en la Directiva de nomenclatura, los usuarios normales de Yammer no podrán crear grupos.</span><span class="sxs-lookup"><span data-stu-id="ba386-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="ba386-146">Use cadenas cortas como sufijo.</span><span class="sxs-lookup"><span data-stu-id="ba386-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="ba386-147">Use atributos con valores.</span><span class="sxs-lookup"><span data-stu-id="ba386-147">Use attributes with values.</span></span>
> - <span data-ttu-id="ba386-148">No ser demasiado creativo, la longitud total del nombre tiene un máximo de 264 caracteres.</span><span class="sxs-lookup"><span data-stu-id="ba386-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="ba386-149">Cargar las palabras bloqueadas específicas de la organización para restringir el uso.</span><span class="sxs-lookup"><span data-stu-id="ba386-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="ba386-150">Palabras bloqueadas personalizadas</span><span class="sxs-lookup"><span data-stu-id="ba386-150">Custom blocked words</span></span>

<span data-ttu-id="ba386-151">Puede escribir una lista separada por comas de palabras bloqueadas que se bloquearán en nombres de grupo y alias.</span><span class="sxs-lookup"><span data-stu-id="ba386-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="ba386-152">No se realizan búsquedas de subcadenas; concretamente, se necesita una coincidencia exacta entre el nombre del usuario especificado y las palabras bloqueadas personalizadas para desencadenar un error.</span><span class="sxs-lookup"><span data-stu-id="ba386-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="ba386-153">**Aspectos que se deben tener en**cuentan:</span><span class="sxs-lookup"><span data-stu-id="ba386-153">**Things to look out for**:</span></span>

- <span data-ttu-id="ba386-154">Las palabras bloqueadas no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ba386-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="ba386-155">Cuando un usuario escribe una palabra bloqueada, el cliente del grupo mostrará un mensaje de error con la palabra bloqueada.</span><span class="sxs-lookup"><span data-stu-id="ba386-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="ba386-156">No hay restricciones de caracteres en las palabras bloqueadas que se usan.</span><span class="sxs-lookup"><span data-stu-id="ba386-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="ba386-157">Hay un límite de 5000 palabras que se pueden establecer como palabras bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="ba386-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="ba386-158">Invalidación de administrador</span><span class="sxs-lookup"><span data-stu-id="ba386-158">Admin override</span></span>

<span data-ttu-id="ba386-159">Algunos administradores están exentos de estas directivas, en todas las cargas de trabajo y extremos de grupo, para que puedan crear grupos con estas palabras bloqueadas y con sus convenciones de nomenclatura deseadas.</span><span class="sxs-lookup"><span data-stu-id="ba386-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="ba386-160">A continuación se muestra la lista de roles de administrador exentos de la Directiva de nomenclatura de grupos.</span><span class="sxs-lookup"><span data-stu-id="ba386-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="ba386-161">Administrador global</span><span class="sxs-lookup"><span data-stu-id="ba386-161">Global admin</span></span>

- <span data-ttu-id="ba386-162">Soporte técnico de nivel 1 de asociado</span><span class="sxs-lookup"><span data-stu-id="ba386-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="ba386-163">Soporte técnico de nivel 2 del asociado</span><span class="sxs-lookup"><span data-stu-id="ba386-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="ba386-164">Administrador de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="ba386-164">User account admin</span></span>

- <span data-ttu-id="ba386-165">Escritores de directorios</span><span class="sxs-lookup"><span data-stu-id="ba386-165">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="ba386-166">Cómo configurar la Directiva de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="ba386-166">How to set up the naming policy</span></span>

<span data-ttu-id="ba386-167">Para configurar una directiva de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="ba386-167">To set up a naming policy:</span></span>

1. <span data-ttu-id="ba386-168">En [Azure Active Directory](https://aad.portal.azure.com), en **administrar**, haga clic en **grupos**.</span><span class="sxs-lookup"><span data-stu-id="ba386-168">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="ba386-169">En **configuración**, haga clic en **Directiva de nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="ba386-169">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="ba386-170">Seleccione la pestaña **Directiva de nomenclatura de grupos** .</span><span class="sxs-lookup"><span data-stu-id="ba386-170">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="ba386-171">En **Directiva actual**, elija si desea requerir un prefijo o un sufijo o ambos y active las casillas de verificación adecuadas.</span><span class="sxs-lookup"><span data-stu-id="ba386-171">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="ba386-172">Elija entre **atributo** y **cadena** para cada línea y, a continuación, especifique el atributo o la cadena.</span><span class="sxs-lookup"><span data-stu-id="ba386-172">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="ba386-173">Cuando haya agregado los prefijos y los sufijos que necesita, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ba386-173">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Captura de pantalla de la configuración de la Directiva de nomenclatura de grupos en Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="ba386-175">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ba386-175">Related topics</span></span>

[<span data-ttu-id="ba386-176">Cmdlets de Azure Active Directory para configurar configuraciones de grupo</span><span class="sxs-lookup"><span data-stu-id="ba386-176">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
