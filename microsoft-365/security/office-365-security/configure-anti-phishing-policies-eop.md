---
title: Configuración de directivas contra phishing en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a crear, modificar y eliminar las directivas contra suplantación de identidad que están disponibles en las organizaciones de Exchange Online Protection (EOP) con o sin buzones de Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 612c7153f89a404cac736a9a46e8ca5f69e46f65
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406225"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="dc659-103">Configuración de directivas contra phishing en EOP</span><span class="sxs-lookup"><span data-stu-id="dc659-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dc659-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="dc659-104">**Applies to**</span></span>
- [<span data-ttu-id="dc659-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dc659-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="dc659-106">En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, hay una directiva contra la suplantación de identidad predeterminada que contiene un número limitado de características contra la suplantación de identidad habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc659-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="dc659-107">Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="dc659-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="dc659-108">Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc659-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="dc659-109">Para mayor granularidad, también puede crear directivas personalizadas contra la suplantación de identidad que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="dc659-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="dc659-110">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="dc659-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="dc659-111">Las organizaciones con buzones de Exchange Online pueden configurar directivas contra la suplantación de identidad en el Centro de seguridad & cumplimiento o en PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dc659-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="dc659-112">Las organizaciones EOP independientes solo pueden usar el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="dc659-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="dc659-113">Para obtener información sobre cómo crear y modificar las directivas contra suplantación de identidad más avanzadas en Microsoft Defender para Office 365 que están disponibles en Defender para Office 365, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dc659-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="dc659-114">Los elementos básicos de una directiva contra la suplantación de identidad son:</span><span class="sxs-lookup"><span data-stu-id="dc659-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="dc659-115">**La directiva contra suplantación de** identidad : especifica las protecciones de suplantación de identidad (phishing) que se habilitarán o deshabilitarán y las acciones que se aplicarán a las opciones.</span><span class="sxs-lookup"><span data-stu-id="dc659-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="dc659-116">**La regla contra suplantación de** identidad : especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva) para una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="dc659-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="dc659-117">La diferencia entre estos dos elementos no es obvia cuando se administran directivas contra suplantación de identidad en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="dc659-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="dc659-118">Al crear una directiva contra suplantación de identidad ( phishing), en realidad está creando una regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada al mismo tiempo que usa el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="dc659-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="dc659-119">Al modificar una directiva contra suplantación de identidad, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada, y los filtros de destinatarios modifican la regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="dc659-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="dc659-120">Todas las demás opciones modifican la directiva contra suplantación de identidad asociada.</span><span class="sxs-lookup"><span data-stu-id="dc659-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="dc659-121">Al quitar una directiva contra phishing, se quitan la regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada.</span><span class="sxs-lookup"><span data-stu-id="dc659-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="dc659-122">En Exchange Online PowerShell, administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="dc659-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="dc659-123">Para obtener más información, vea la sección [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="dc659-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="dc659-124">Cada organización tiene una directiva contra suplantación de identidad integrada denominada Office365 AntiPhish Default que tiene estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="dc659-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="dc659-125">La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla contra la suplantación de identidad (filtros de destinatarios) asociada a la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="dc659-126">La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="dc659-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="dc659-127">Las directivas personalizadas que cree siempre tendrán una prioridad mayor.</span><span class="sxs-lookup"><span data-stu-id="dc659-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="dc659-128">La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc659-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="dc659-129">Para aumentar la eficacia de la protección contra phishing, puede crear directivas personalizadas contra suplantación de identidad con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="dc659-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dc659-130">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="dc659-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dc659-131">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="dc659-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="dc659-132">Para ir directamente a la **página Anti-phishing,** use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="dc659-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="dc659-133">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="dc659-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="dc659-134">No puede administrar directivas contra suplantación de identidad (phishing) en PowerShell de EOP independiente.</span><span class="sxs-lookup"><span data-stu-id="dc659-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="dc659-135">Debe tener asignados permisos en **Exchange Online** para poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="dc659-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="dc659-136">Para agregar, modificar y eliminar directivas contra suplantación de identidad, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="dc659-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="dc659-137">Para obtener acceso de solo lectura a directivas contra suplantación de identidad, debe ser miembro de los grupos de roles Lector **global** o Lector **de** <sup>\*</sup> seguridad.</span><span class="sxs-lookup"><span data-stu-id="dc659-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="dc659-138">Para obtener más información, consulte los [permisos en Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="dc659-138">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="dc659-139">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="dc659-139">**Notes**:</span></span>

  - <span data-ttu-id="dc659-140">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos y permisos necesarios para _otras_ características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc659-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="dc659-141">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="dc659-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="dc659-142">El **grupo de roles Administración** de la organización de solo vista en Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="dc659-142">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="dc659-143"><sup>\*</sup> En el Centro de & seguridad, el acceso de solo lectura permite a los usuarios ver la configuración de las directivas personalizadas contra la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="dc659-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="dc659-144">Los usuarios de solo lectura no pueden ver la configuración en la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc659-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="dc659-145">Para crear y modificar directivas contra suplantación de identidad (phishing) en EOP independiente, debe hacer algo que requiera _hidratación_ para su inquilino.</span><span class="sxs-lookup"><span data-stu-id="dc659-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="dc659-146">Por ejemplo, en el Centro de administración de  Exchange (EAC), puede ir  a la pestaña Permisos, seleccionar un grupo de roles existente, hacer clic en Editar icono Editar y quitar un rol (que en última instancia ![ agregará). ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="dc659-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="dc659-147">Si el espacio empresarial nunca se ha hidratado, se obtiene un cuadro de diálogo denominado **Actualizar** configuración de la organización con una barra de progreso que debe completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc659-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="dc659-148">Para obtener más información acerca de la hidratación, vea el cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (que no está disponible en PowerShell EOP independiente o en el Centro de seguridad & cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="dc659-148">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="dc659-149">Para obtener la configuración recomendada para las directivas contra suplantación de identidad, consulte [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="dc659-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="dc659-150">Permitir hasta 30 minutos para que se aplique la directiva actualizada.</span><span class="sxs-lookup"><span data-stu-id="dc659-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="dc659-151">Para obtener información sobre dónde se aplican las directivas contra suplantación de identidad en la canalización de filtrado, vea [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="dc659-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="dc659-152">Usar el Centro de seguridad & cumplimiento para crear directivas contra la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="dc659-153">La creación de una directiva contra suplantación de identidad personalizada en el Centro de seguridad & Cumplimiento crea la regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="dc659-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="dc659-154">Al crear una directiva anti phishing, solo puede especificar el nombre de la directiva, la descripción y el filtro de destinatarios que identifica a quién se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="dc659-155">Después de crear la directiva, puede modificar la directiva para cambiar o revisar la configuración predeterminada contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="dc659-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="dc659-156">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="dc659-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="dc659-157">En la **página Anti-phishing,** haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="dc659-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="dc659-158">Se abrirá el Asistente para crear una nueva directiva **contra suplantación de** identidad.</span><span class="sxs-lookup"><span data-stu-id="dc659-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="dc659-159">En la **página Nombre de la directiva,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dc659-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="dc659-160">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="dc659-161">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="dc659-162">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dc659-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="dc659-163">En la **página Aplicada a** que aparece, identifique los destinatarios internos a los que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="dc659-164">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="dc659-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="dc659-165">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="dc659-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="dc659-166">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="dc659-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="dc659-167">Haga **clic en Agregar una condición**.</span><span class="sxs-lookup"><span data-stu-id="dc659-167">Click **Add a condition**.</span></span> <span data-ttu-id="dc659-168">En el desplegable que aparece, seleccione una condición en **Aplicada si**:</span><span class="sxs-lookup"><span data-stu-id="dc659-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="dc659-169">**El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="dc659-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="dc659-170">**El destinatario es miembro de**: Especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="dc659-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="dc659-171">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.</span><span class="sxs-lookup"><span data-stu-id="dc659-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="dc659-172">Después de seleccionar la condición, aparece un desplegable correspondiente con **un cuadro Cualquiera de estos.**</span><span class="sxs-lookup"><span data-stu-id="dc659-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="dc659-173">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="dc659-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="dc659-174">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="dc659-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="dc659-175">Para agregar valores adicionales, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="dc659-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="dc659-176">Para quitar entradas individuales, haga clic **en Quitar** ![ icono Quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="dc659-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="dc659-177">Para quitar toda la condición, haga clic **en Quitar** icono Quitar en ![ la ](../../media/scc-remove-icon.png) condición.</span><span class="sxs-lookup"><span data-stu-id="dc659-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="dc659-178">Para agregar una condición adicional, haga clic **en Agregar una condición** y seleccione un valor restante en Aplicado **si**.</span><span class="sxs-lookup"><span data-stu-id="dc659-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="dc659-179">Para agregar excepciones, haga clic **en Agregar una condición** y seleccione una excepción en Excepto **si**.</span><span class="sxs-lookup"><span data-stu-id="dc659-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="dc659-180">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="dc659-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="dc659-181">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dc659-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="dc659-182">En la **página Revisar la configuración** que aparece, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="dc659-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="dc659-183">Puede hacer clic **en Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="dc659-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="dc659-184">Cuando haya terminado, haga clic **en Crear esta directiva.**</span><span class="sxs-lookup"><span data-stu-id="dc659-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="dc659-185">Haga **clic en Aceptar** en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="dc659-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="dc659-186">Después de crear la directiva contra suplantación de identidad con esta configuración de directiva general, use las instrucciones de la sección siguiente para configurar las opciones de protección en la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="dc659-187">Usar el Centro de & seguridad para modificar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="dc659-188">Use los siguientes procedimientos para modificar las directivas contra suplantación de identidad: una nueva directiva que creó o directivas existentes que ya ha personalizado.</span><span class="sxs-lookup"><span data-stu-id="dc659-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="dc659-189">Si aún no está allí, abra el Centro de seguridad & cumplimiento y vaya a **Directiva** de administración de amenazas \>  \> **contra la suplantación** de identidad .</span><span class="sxs-lookup"><span data-stu-id="dc659-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="dc659-190">Seleccione la directiva contra suplantación de identidad personalizada que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="dc659-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="dc659-191">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="dc659-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="dc659-192">Aparece el control **desplegable \<name\>** Editar la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="dc659-193">Si **hace clic** en Editar en cualquier sección, podrá acceder a la configuración de esa sección.</span><span class="sxs-lookup"><span data-stu-id="dc659-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="dc659-194">Los pasos siguientes se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="dc659-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="dc659-195">Después de  hacer clic en Editar en una sección, la configuración disponible se presenta en un formato de asistente,  pero  puede saltar dentro de las páginas en cualquier orden y puede hacer clic en Guardar en cualquier página (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** cancelar o cerrar cerrar icono para volver a la página Editar la directiva (no es necesario visitar la última página del asistente para guardar o salir).</span><span class="sxs-lookup"><span data-stu-id="dc659-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="dc659-196">**Configuración de directiva:** haga clic **en Editar** para modificar la misma configuración que estaba disponible al [crear la directiva](#use-the-security--compliance-center-to-create-anti-phishing-policies) en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="dc659-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="dc659-197">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="dc659-197">**Name**</span></span>
   - <span data-ttu-id="dc659-198">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dc659-198">**Description**</span></span>
   - <span data-ttu-id="dc659-199">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="dc659-199">**Applied to**</span></span>
   - <span data-ttu-id="dc659-200">**Revisar la configuración**</span><span class="sxs-lookup"><span data-stu-id="dc659-200">**Review your settings**</span></span>

   <span data-ttu-id="dc659-201">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="dc659-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="dc659-202">**Suplantación:**  haga clic en Editar para activar o desactivar la inteligencia de suplantación de identidad, activar o desactivar la identificación de remitentes no autenticados en Outlook y configurar la acción para que se aplique a los mensajes de remitentes suplantados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="dc659-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="dc659-203">Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="dc659-203">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="dc659-204">Tenga en cuenta que esta misma configuración también está disponible en las directivas contra suplantación de identidad en Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc659-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="dc659-205">**Configuración del filtro de suplantación:** el valor predeterminado es **On** y le recomendamos que lo deje en.</span><span class="sxs-lookup"><span data-stu-id="dc659-205">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="dc659-206">Para desactivarlo, deslice el botón de alternancia a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="dc659-206">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="dc659-207">Para obtener más información, vea [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="dc659-207">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="dc659-208">No es necesario deshabilitar la protección contra la suplantación si el registro MX no apunta a Microsoft 365; habilitar el filtrado mejorado para conectores en su lugar.</span><span class="sxs-lookup"><span data-stu-id="dc659-208">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="dc659-209">Para obtener instrucciones, consulte [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="dc659-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="dc659-210">**Habilitar la característica Remitente no autenticado:** el valor predeterminado es **On**.</span><span class="sxs-lookup"><span data-stu-id="dc659-210">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="dc659-211">Para desactivarlo, deslice el botón de alternancia a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="dc659-211">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="dc659-212">**Acciones:** especifique la acción que se debe realizar en los mensajes que no puedan suplantar la inteligencia:</span><span class="sxs-lookup"><span data-stu-id="dc659-212">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="dc659-213">Si alguien que no tiene permiso para **suplantación** de dominio envía correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="dc659-213">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="dc659-214">**Mover el mensaje a las carpetas de correo no deseado de los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="dc659-214">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="dc659-215">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="dc659-215">**Quarantine the message**</span></span>

   - <span data-ttu-id="dc659-216">**Revise la configuración:** en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="dc659-216">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="dc659-217">Puede hacer clic **en Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="dc659-217">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="dc659-218">Puedes activar o desactivar la **siguiente** configuración **directamente** en esta página:</span><span class="sxs-lookup"><span data-stu-id="dc659-218">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="dc659-219">**Habilitar la protección contra la suplantación**</span><span class="sxs-lookup"><span data-stu-id="dc659-219">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="dc659-220">**Habilitar la característica Remitente no autenticado**</span><span class="sxs-lookup"><span data-stu-id="dc659-220">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="dc659-221">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="dc659-221">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="dc659-222">Vuelva a la **página Editar la \<Name\> directiva,** revise la configuración y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="dc659-222">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="dc659-223">Usar el Centro de seguridad & cumplimiento para modificar la directiva contra suplantación de identidad predeterminada</span><span class="sxs-lookup"><span data-stu-id="dc659-223">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="dc659-224">La directiva contra suplantación de identidad predeterminada se denomina Office365 AntiPhish Default y no aparece en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="dc659-224">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="dc659-225">Para modificar la directiva contra suplantación de identidad predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dc659-225">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="dc659-226">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="dc659-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="dc659-227">En la **página Anti-phishing,** haga clic en **Directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="dc659-227">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="dc659-228">Aparece **la página Editar la directiva Office365 AntiPhish Default.**</span><span class="sxs-lookup"><span data-stu-id="dc659-228">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="dc659-229">Las secciones siguientes están disponibles, que contienen una configuración idéntica para cuando [se modifica una directiva personalizada](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="dc659-229">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="dc659-230">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="dc659-230">**Impersonation**</span></span>
   - <span data-ttu-id="dc659-231">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="dc659-231">**Spoof**</span></span>
   - <span data-ttu-id="dc659-232">**Configuración avanzada**</span><span class="sxs-lookup"><span data-stu-id="dc659-232">**Advanced settings**</span></span>

   <span data-ttu-id="dc659-233">La siguiente configuración no está disponible al modificar la directiva predeterminada:</span><span class="sxs-lookup"><span data-stu-id="dc659-233">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="dc659-234">Puede ver  la sección Configuración de directiva y los valores, pero no hay ningún vínculo **Editar,** por lo que no puede modificar la configuración (nombre de directiva, descripción y a quién se aplica la directiva (se aplica a todos los destinatarios)).</span><span class="sxs-lookup"><span data-stu-id="dc659-234">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="dc659-235">No puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc659-235">You can't delete the default policy.</span></span>
   - <span data-ttu-id="dc659-236">No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="dc659-236">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="dc659-237">En la página Editar la directiva predeterminada de **Office365 AntiPhish,** revise la configuración y, a continuación, haga clic **en Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="dc659-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="dc659-238">Habilitar o deshabilitar directivas personalizadas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-238">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="dc659-239">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="dc659-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="dc659-240">Observe el valor de la **columna Estado:**</span><span class="sxs-lookup"><span data-stu-id="dc659-240">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="dc659-241">Deslice el botón de **alternancia a Desactivado** para deshabilitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-241">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="dc659-242">Deslice el botón de **alternancia a Activar** para habilitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-242">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="dc659-243">No puede deshabilitar la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc659-243">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="dc659-244">Establecer la prioridad de las directivas contra suplantación de identidad personalizadas</span><span class="sxs-lookup"><span data-stu-id="dc659-244">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="dc659-245">De forma predeterminada, las directivas contra suplantación de identidad tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="dc659-245">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="dc659-246">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="dc659-246">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="dc659-247">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-247">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="dc659-248">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="dc659-248">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="dc659-249">Las directivas contra suplantación de identidad personalizadas se muestran en el orden en que se procesan (la primera directiva tiene el **valor de prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="dc659-249">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="dc659-250">La directiva contra suplantación de identidad predeterminada denominada Office365 AntiPhish Default tiene el valor de prioridad personalizado **Lowest** y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="dc659-250">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="dc659-251">**Nota:** En el Centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la directiva contra suplantación de identidad después de crearla.</span><span class="sxs-lookup"><span data-stu-id="dc659-251">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="dc659-252">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla contra suplantación de identidad (lo que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="dc659-252">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="dc659-253">Para cambiar la prioridad de  una directiva, haga clic en Aumentar prioridad o Disminuir  prioridad en las propiedades de la directiva (no puede modificar directamente el número de prioridad en el Centro de seguridad & cumplimiento). </span><span class="sxs-lookup"><span data-stu-id="dc659-253">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="dc659-254">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="dc659-254">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="dc659-255">En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.</span><span class="sxs-lookup"><span data-stu-id="dc659-255">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="dc659-256">Seleccione la directiva que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="dc659-256">Select the policy that you want to modify.</span></span> <span data-ttu-id="dc659-257">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="dc659-257">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="dc659-258">Aparece el control **desplegable \<name\>** Editar la directiva.</span><span class="sxs-lookup"><span data-stu-id="dc659-258">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="dc659-259">La directiva contra suplantación de identidad personalizada con el valor **de prioridad** **0** solo tiene disponible el **botón Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="dc659-259">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="dc659-260">La directiva contra suplantación de identidad personalizada con el valor **priority** más bajo (por ejemplo, **3**) solo tiene disponible **el botón Aumentar** prioridad.</span><span class="sxs-lookup"><span data-stu-id="dc659-260">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="dc659-261">Si tiene tres o más directivas contra suplantación de identidad personalizadas, las  directivas entre los valores de prioridad más alta y más baja tienen disponibles los botones Aumentar prioridad y Disminuir prioridad. </span><span class="sxs-lookup"><span data-stu-id="dc659-261">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="dc659-262">Haga **clic en Aumentar prioridad** o Disminuir **prioridad** para cambiar el valor **De** prioridad.</span><span class="sxs-lookup"><span data-stu-id="dc659-262">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="dc659-263">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="dc659-263">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="dc659-264">Usar el Centro de seguridad & cumplimiento para ver directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-264">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="dc659-265">En el Centro de seguridad & cumplimiento y vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="dc659-265">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="dc659-266">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc659-266">Do one of the following steps:</span></span>

   - <span data-ttu-id="dc659-267">Seleccione una directiva contra suplantación de identidad personalizada que desee ver.</span><span class="sxs-lookup"><span data-stu-id="dc659-267">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="dc659-268">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="dc659-268">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="dc659-269">Haga **clic en Directiva predeterminada** para ver la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc659-269">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="dc659-270">Aparece **el \<name\> control desplegable** Editar la directiva, donde puede ver la configuración y los valores.</span><span class="sxs-lookup"><span data-stu-id="dc659-270">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="dc659-271">Usar el Centro de seguridad & cumplimiento para quitar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-271">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="dc659-272">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="dc659-272">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="dc659-273">Seleccione la directiva que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="dc659-273">Select the policy that you want to remove.</span></span> <span data-ttu-id="dc659-274">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="dc659-274">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="dc659-275">En el **control \<name\>** desplegable Editar la directiva que aparece, haga clic en **Eliminar** directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="dc659-275">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="dc659-276">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc659-276">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="dc659-277">Usar Exchange Online PowerShell para configurar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-277">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="dc659-278">Como se describió anteriormente, una directiva contra suplantación de identidad (phishing) consta de una directiva contra suplantación de identidad (phishing) y una regla contra suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="dc659-278">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="dc659-279">En Exchange Online PowerShell, la diferencia entre las directivas contra suplantación de identidad (phish) y las reglas contra suplantación de identidad (phishing) es aparente.</span><span class="sxs-lookup"><span data-stu-id="dc659-279">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="dc659-280">Las directivas contra suplantación de identidad se administran mediante los cmdlets **\* -AntiPhishPolicy** y se administran reglas contra suplantación de identidad mediante los cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="dc659-280">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="dc659-281">En PowerShell, primero se crea la directiva contra suplantación de identidad y, a continuación, se crea la regla contra suplantación de identidad que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="dc659-281">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="dc659-282">En PowerShell, se modifica la configuración de la directiva contra suplantación de identidad y la regla contra suplantación de identidad por separado.</span><span class="sxs-lookup"><span data-stu-id="dc659-282">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="dc659-283">Al quitar una directiva contra suplantación de identidad de PowerShell, la regla anti-phish correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="dc659-283">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="dc659-284">Los siguientes procedimientos de PowerShell no están disponibles en organizaciones EOP independientes con PowerShell de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="dc659-284">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="dc659-285">Usar PowerShell para crear directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-285">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="dc659-286">Crear una directiva contra la suplantación de identidad en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="dc659-286">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="dc659-287">Cree la directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="dc659-287">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="dc659-288">Cree la regla contra suplantación de identidad que especifica la directiva contra suplantación de identidad a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="dc659-288">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="dc659-289">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="dc659-289">**Notes**:</span></span>

- <span data-ttu-id="dc659-290">Puede crear una nueva regla contra suplantación de identidad (phish) y asignarle una directiva anti-phish existente y no asociada.</span><span class="sxs-lookup"><span data-stu-id="dc659-290">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="dc659-291">Una regla contra la suplantación de identidad no se puede asociar a más de una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="dc659-291">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="dc659-292">Puede configurar las siguientes opciones en las nuevas directivas contra suplantación de identidad en PowerShell que no están disponibles en el Centro de seguridad y cumplimiento de & hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="dc659-292">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="dc659-293">Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="dc659-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="dc659-294">Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="dc659-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="dc659-295">Una nueva directiva contra suplantación de identidad que cree en PowerShell no está visible en el Centro de seguridad y cumplimiento de & hasta que asigne la directiva a una regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="dc659-295">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="dc659-296">Paso 1: Usar PowerShell para crear una directiva contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-296">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="dc659-297">Para crear una directiva contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc659-297">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="dc659-298">En este ejemplo se crea una directiva contra phishing denominada Cuarentena de investigación con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="dc659-298">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="dc659-299">La descripción es: Directiva del departamento de investigación.</span><span class="sxs-lookup"><span data-stu-id="dc659-299">The description is: Research department policy.</span></span>
- <span data-ttu-id="dc659-300">Cambia la acción predeterminada de suplantación a Cuarentena.</span><span class="sxs-lookup"><span data-stu-id="dc659-300">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="dc659-301">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="dc659-301">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="dc659-302">Paso 2: Usar PowerShell para crear una regla contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-302">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="dc659-303">Para crear una regla contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc659-303">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="dc659-304">En este ejemplo se crea una regla contra suplantación de identidad (phish) denominada Departamento de investigación con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="dc659-304">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="dc659-305">La regla está asociada con la directiva contra phishing denominada Cuarentena de investigación.</span><span class="sxs-lookup"><span data-stu-id="dc659-305">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="dc659-306">La regla se aplica a los miembros del grupo denominado Research Department.</span><span class="sxs-lookup"><span data-stu-id="dc659-306">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="dc659-307">Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc659-307">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="dc659-308">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="dc659-308">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="dc659-309">Usar PowerShell para ver directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-309">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="dc659-310">Para ver las directivas anti phish existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc659-310">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="dc659-311">En este ejemplo se devuelve una lista resumida de todas las directivas contra phishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="dc659-311">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="dc659-312">En este ejemplo se devuelven todos los valores de propiedad de la directiva contra suplantación de identidad denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="dc659-312">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="dc659-313">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="dc659-313">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="dc659-314">Usar PowerShell para ver reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-314">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="dc659-315">Para ver las reglas anti phish existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc659-315">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="dc659-316">En este ejemplo se devuelve una lista resumida de todas las reglas contra phishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="dc659-316">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="dc659-317">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="dc659-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="dc659-318">En este ejemplo se devuelven todos los valores de propiedad de la regla contra suplantación de identidad denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="dc659-318">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="dc659-319">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="dc659-319">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="dc659-320">Usar PowerShell para modificar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-320">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="dc659-321">Aparte de los siguientes elementos, la misma configuración está disponible al modificar una directiva contra suplantación de identidad en PowerShell que al crear una directiva como se describe en Paso [1:](#step-1-use-powershell-to-create-an-anti-phish-policy) Usar PowerShell para crear una directiva contra suplantación de identidad anterior en este artículo.</span><span class="sxs-lookup"><span data-stu-id="dc659-321">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="dc659-322">El _modificador MakeDefault_ que convierte la directiva especificada en la directiva predeterminada (aplicada a todos, siempre **con** prioridad más baja y no puede eliminarla) solo está disponible cuando modifica una directiva contra suplantación de identidad en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc659-322">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="dc659-323">No puede cambiar el nombre de una directiva contra suplantación de identidad (el cmdlet **Set-AntiPhishPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="dc659-323">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="dc659-324">Al cambiar el nombre de una directiva contra suplantación de identidad en el Centro de seguridad & cumplimiento, solo se cambia el nombre de la regla contra _suplantación de identidad_.</span><span class="sxs-lookup"><span data-stu-id="dc659-324">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="dc659-325">Para modificar una directiva contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc659-325">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="dc659-326">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="dc659-326">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="dc659-327">Usar PowerShell para modificar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-327">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="dc659-328">La única configuración que no está disponible al modificar una regla contra suplantación de identidad en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="dc659-328">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="dc659-329">Para habilitar o deshabilitar las reglas antiphishing existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="dc659-329">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="dc659-330">De lo contrario, la misma configuración está disponible al crear una regla tal como se describe en el Paso [2: Usar PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) para crear una sección de regla contra suplantación de identidad anterior en este artículo.</span><span class="sxs-lookup"><span data-stu-id="dc659-330">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="dc659-331">Para modificar una regla contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc659-331">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="dc659-332">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="dc659-332">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="dc659-333">Usar PowerShell para habilitar o deshabilitar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-333">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="dc659-334">Habilitar o deshabilitar una regla contra suplantación de identidad en PowerShell habilita o deshabilita toda la directiva contra suplantación de identidad (la regla anti phishing y la directiva contra suplantación de identidad asignada).</span><span class="sxs-lookup"><span data-stu-id="dc659-334">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="dc659-335">No puede habilitar ni deshabilitar la directiva contra suplantación de identidad predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="dc659-335">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="dc659-336">Para habilitar o deshabilitar una regla contra phishing en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc659-336">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="dc659-337">En este ejemplo se deshabilita la regla contra suplantación de identidad (phish) denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="dc659-337">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="dc659-338">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="dc659-338">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="dc659-339">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) y [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="dc659-339">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="dc659-340">Usar PowerShell para establecer la prioridad de las reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-340">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="dc659-341">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="dc659-341">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="dc659-342">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="dc659-342">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="dc659-343">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="dc659-343">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="dc659-344">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="dc659-344">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="dc659-345">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="dc659-345">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="dc659-346">Para establecer la prioridad de una regla contra suplantación de identidad en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc659-346">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="dc659-347">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="dc659-347">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="dc659-348">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="dc659-348">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="dc659-349">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="dc659-349">**Notes**:</span></span>

- <span data-ttu-id="dc659-350">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="dc659-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="dc659-351">La directiva contra suplantación de identidad predeterminada no tiene una regla anti phish correspondiente y siempre tiene el valor de prioridad no modificable **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="dc659-351">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="dc659-352">Usar PowerShell para quitar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-352">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="dc659-353">Cuando se usa PowerShell para quitar una directiva contra suplantación de identidad, no se quita la regla contra suplantación de identidad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="dc659-353">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="dc659-354">Para quitar una directiva contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc659-354">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="dc659-355">En este ejemplo se quita la directiva contra suplantación de identidad denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="dc659-355">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="dc659-356">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="dc659-356">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="dc659-357">Usar PowerShell para quitar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="dc659-357">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="dc659-358">Cuando usa PowerShell para quitar una regla contra phishing, no se quita la directiva anti phish correspondiente.</span><span class="sxs-lookup"><span data-stu-id="dc659-358">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="dc659-359">Para quitar una regla contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc659-359">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="dc659-360">En este ejemplo se quita la regla contra suplantación de identidad (phish) denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="dc659-360">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="dc659-361">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="dc659-361">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="dc659-362">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="dc659-362">How do you know these procedures worked?</span></span>

<span data-ttu-id="dc659-363">Para comprobar que ha configurado correctamente directivas contra suplantación de identidad (phishing) en Microsoft Defender para Office 365, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dc659-363">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="dc659-364">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="dc659-364">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="dc659-365">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="dc659-365">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="dc659-366">Para ver más detalles, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dc659-366">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="dc659-367">Seleccione la directiva de la lista y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="dc659-367">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="dc659-368">Haga **clic en Directiva predeterminada** y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="dc659-368">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="dc659-369">En Exchange Online PowerShell, reemplace por el nombre de la directiva o \<Name\> regla, ejecute el siguiente comando y compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="dc659-369">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
