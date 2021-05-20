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
description: Los administradores pueden aprender a crear, modificar y eliminar las directivas contra suplantación de identidad que están disponibles en organizaciones de Exchange Online Protection (EOP) con o sin buzones Exchange Online correo.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bc3c15d2a652e9acd3407ecb91fc99b7ef295c7e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537924"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="6477f-103">Configuración de directivas contra phishing en EOP</span><span class="sxs-lookup"><span data-stu-id="6477f-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6477f-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="6477f-104">**Applies to**</span></span>
- [<span data-ttu-id="6477f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6477f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="6477f-106">En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo de Exchange Online, hay una directiva contra la suplantación de identidad predeterminada que contiene un número limitado de características contra la suplantación de identidad que están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6477f-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="6477f-107">Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="6477f-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="6477f-108">Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6477f-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="6477f-109">Para mayor granularidad, también puede crear directivas personalizadas contra la suplantación de identidad que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="6477f-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="6477f-110">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="6477f-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="6477f-111">Las organizaciones con Exchange Online buzones de correo pueden configurar directivas contra la suplantación de identidad en el Centro de seguridad y & cumplimiento o Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6477f-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="6477f-112">Las organizaciones EOP independientes solo pueden usar el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6477f-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="6477f-113">Para obtener información sobre cómo crear y modificar las directivas contra suplantación de identidad más avanzadas en Microsoft Defender para Office 365 que están disponibles en Defender para Office 365, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6477f-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="6477f-114">Los elementos básicos de una directiva contra la suplantación de identidad son:</span><span class="sxs-lookup"><span data-stu-id="6477f-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="6477f-115">**La directiva contra suplantación de** identidad : especifica las protecciones de suplantación de identidad (phishing) que se habilitarán o deshabilitarán y las acciones que se aplicarán a las opciones.</span><span class="sxs-lookup"><span data-stu-id="6477f-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="6477f-116">**La regla contra suplantación de** identidad : especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva) para una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6477f-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="6477f-117">La diferencia entre estos dos elementos no es obvia cuando se administran directivas contra suplantación de identidad en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="6477f-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="6477f-118">Al crear una directiva contra suplantación de identidad ( phishing), en realidad está creando una regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada al mismo tiempo que usa el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="6477f-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="6477f-119">Al modificar una directiva contra suplantación de identidad, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada, y los filtros de destinatarios modifican la regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6477f-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="6477f-120">Todas las demás opciones modifican la directiva contra suplantación de identidad asociada.</span><span class="sxs-lookup"><span data-stu-id="6477f-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="6477f-121">Al quitar una directiva contra phishing, se quitan la regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada.</span><span class="sxs-lookup"><span data-stu-id="6477f-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="6477f-122">En Exchange Online PowerShell, administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="6477f-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="6477f-123">Para obtener más información, vea la sección [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="6477f-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="6477f-124">Cada organización tiene una directiva contra suplantación de identidad integrada denominada Office365 AntiPhish Default que tiene estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="6477f-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="6477f-125">La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla contra la suplantación de identidad (filtros de destinatarios) asociada a la directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="6477f-126">La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="6477f-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="6477f-127">Las directivas personalizadas que cree siempre tendrán una prioridad mayor.</span><span class="sxs-lookup"><span data-stu-id="6477f-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="6477f-128">La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6477f-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="6477f-129">Para aumentar la eficacia de la protección contra phishing, puede crear directivas personalizadas contra suplantación de identidad con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="6477f-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6477f-130">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="6477f-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6477f-131">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6477f-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6477f-132">Para ir directamente a la **página Anti-phishing,** use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="6477f-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="6477f-133">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6477f-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="6477f-134">No puede administrar directivas contra suplantación de identidad (phishing) en PowerShell de EOP independiente.</span><span class="sxs-lookup"><span data-stu-id="6477f-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="6477f-135">Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="6477f-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6477f-136">Para agregar, modificar y eliminar directivas contra suplantación de identidad, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="6477f-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="6477f-137">Para obtener acceso de solo lectura a directivas contra suplantación de identidad, debe ser miembro de los grupos de roles Lector **global** o Lector **de** <sup>\*</sup> seguridad.</span><span class="sxs-lookup"><span data-stu-id="6477f-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="6477f-138">Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="6477f-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="6477f-139">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="6477f-139">**Notes**:</span></span>

  - <span data-ttu-id="6477f-140">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6477f-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6477f-141">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6477f-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="6477f-142">El **grupo de roles Administración** de la organización de solo vista [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="6477f-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="6477f-143"><sup>\*</sup> En el Centro de & seguridad, el acceso de solo lectura permite a los usuarios ver la configuración de las directivas personalizadas contra la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6477f-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="6477f-144">Los usuarios de solo lectura no pueden ver la configuración en la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6477f-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="6477f-145">Para crear y modificar directivas contra suplantación de identidad (phishing) en EOP independiente, debe hacer algo que requiera _hidratación_ para su inquilino.</span><span class="sxs-lookup"><span data-stu-id="6477f-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="6477f-146">Por ejemplo, en el Centro de administración de Exchange  (EAC), puede ir a  la pestaña Permisos, seleccionar un grupo de roles existente, hacer clic en Editar icono editar y quitar un rol (que en última instancia ![ agregará). ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="6477f-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="6477f-147">Si el espacio empresarial nunca se ha hidratado, se obtiene un cuadro de diálogo denominado Actualizar organización **Configuración** con una barra de progreso que debe completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="6477f-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="6477f-148">Para obtener más información acerca de la hidratación, vea el cmdlet [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) (que no está disponible en PowerShell EOP independiente o en el Centro de seguridad & cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="6477f-148">For more information about hydration, see the [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="6477f-149">Para obtener la configuración recomendada para las directivas contra suplantación de identidad, consulte [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="6477f-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="6477f-150">Permitir hasta 30 minutos para que se aplique la directiva actualizada.</span><span class="sxs-lookup"><span data-stu-id="6477f-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="6477f-151">Para obtener información sobre dónde se aplican las directivas contra suplantación de identidad en la canalización de filtrado, vea [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="6477f-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="6477f-152">Usar el Centro de seguridad & cumplimiento para crear directivas contra la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="6477f-153">La creación de una directiva contra suplantación de identidad personalizada en el Centro de seguridad & Cumplimiento crea la regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="6477f-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="6477f-154">Al crear una directiva anti phishing, solo puede especificar el nombre de la directiva, la descripción y el filtro de destinatarios que identifica a quién se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="6477f-155">Después de crear la directiva, puede modificar la directiva para cambiar o revisar la configuración predeterminada contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6477f-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="6477f-156">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="6477f-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="6477f-157">En la **página Anti-phishing,** haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="6477f-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="6477f-158">Se abrirá el Asistente para crear una nueva directiva **contra suplantación de** identidad.</span><span class="sxs-lookup"><span data-stu-id="6477f-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="6477f-159">En la **página Nombre de la directiva,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6477f-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="6477f-160">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="6477f-161">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="6477f-162">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6477f-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6477f-163">En la **página Aplicada a** que aparece, identifique los destinatarios internos a los que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="6477f-164">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="6477f-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="6477f-165">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="6477f-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="6477f-166">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="6477f-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="6477f-167">Haga **clic en Agregar una condición**.</span><span class="sxs-lookup"><span data-stu-id="6477f-167">Click **Add a condition**.</span></span> <span data-ttu-id="6477f-168">En el desplegable que aparece, seleccione una condición en **Aplicada si**:</span><span class="sxs-lookup"><span data-stu-id="6477f-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="6477f-169">**El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="6477f-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="6477f-170">**El destinatario es miembro de**: Especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="6477f-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="6477f-171">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.</span><span class="sxs-lookup"><span data-stu-id="6477f-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="6477f-172">Después de seleccionar la condición, aparece un desplegable correspondiente con **un cuadro Cualquiera de estos.**</span><span class="sxs-lookup"><span data-stu-id="6477f-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="6477f-173">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="6477f-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="6477f-174">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="6477f-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="6477f-175">Para agregar valores adicionales, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="6477f-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="6477f-176">Para quitar entradas individuales, haga clic **en Quitar** ![ icono Quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="6477f-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="6477f-177">Para quitar toda la condición, haga clic **en Quitar** icono Quitar en ![ la ](../../media/scc-remove-icon.png) condición.</span><span class="sxs-lookup"><span data-stu-id="6477f-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="6477f-178">Para agregar una condición adicional, haga clic **en Agregar una condición** y seleccione un valor restante en Aplicado **si**.</span><span class="sxs-lookup"><span data-stu-id="6477f-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="6477f-179">Para agregar excepciones, haga clic **en Agregar una condición** y seleccione una excepción en Excepto **si**.</span><span class="sxs-lookup"><span data-stu-id="6477f-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="6477f-180">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="6477f-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="6477f-181">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6477f-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6477f-182">En la **página Revisar la configuración** que aparece, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="6477f-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="6477f-183">Puede hacer clic **en Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="6477f-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="6477f-184">Cuando haya terminado, haga clic **en Crear esta directiva.**</span><span class="sxs-lookup"><span data-stu-id="6477f-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="6477f-185">Haga **clic en Aceptar** en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="6477f-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="6477f-186">Después de crear la directiva contra suplantación de identidad con esta configuración de directiva general, use las instrucciones de la sección siguiente para configurar las opciones de protección en la directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="6477f-187">Usar el Centro de & seguridad para modificar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="6477f-188">Use los siguientes procedimientos para modificar las directivas contra suplantación de identidad: una nueva directiva que creó o directivas existentes que ya ha personalizado.</span><span class="sxs-lookup"><span data-stu-id="6477f-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="6477f-189">Si aún no está allí, abra el Centro de seguridad & cumplimiento y vaya a **Directiva** de administración de amenazas \>  \> **contra la suplantación** de identidad .</span><span class="sxs-lookup"><span data-stu-id="6477f-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="6477f-190">Seleccione la directiva contra suplantación de identidad personalizada que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="6477f-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="6477f-191">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="6477f-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="6477f-192">Aparece el control **desplegable \<name\>** Editar la directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="6477f-193">Si **hace clic** en Editar en cualquier sección, podrá acceder a la configuración de esa sección.</span><span class="sxs-lookup"><span data-stu-id="6477f-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="6477f-194">Los pasos siguientes se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="6477f-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="6477f-195">Después de  hacer clic en Editar en una sección, la configuración disponible se presenta en un formato de asistente,  pero  puede saltar dentro de las páginas en cualquier orden y puede hacer clic en Guardar en cualquier página (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** cancelar o cerrar cerrar icono para volver a la página Editar la directiva (no es necesario visitar la última página del asistente para guardar o salir).</span><span class="sxs-lookup"><span data-stu-id="6477f-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="6477f-196">**Configuración de directiva:** haga clic **en Editar** para modificar la misma configuración que estaba disponible al [crear la directiva](#use-the-security--compliance-center-to-create-anti-phishing-policies) en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="6477f-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="6477f-197">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6477f-197">**Name**</span></span>
   - <span data-ttu-id="6477f-198">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6477f-198">**Description**</span></span>
   - <span data-ttu-id="6477f-199">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="6477f-199">**Applied to**</span></span>
   - <span data-ttu-id="6477f-200">**Revisión de la configuración**</span><span class="sxs-lookup"><span data-stu-id="6477f-200">**Review your settings**</span></span>

   <span data-ttu-id="6477f-201">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="6477f-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="6477f-202">**Suplantación:**  haga clic en Editar para activar o desactivar la inteligencia de suplantación de identidad, activar o desactivar la identificación del remitente no autenticado en Outlook y configurar la acción para que se aplique a los mensajes de remitentes suplantados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="6477f-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="6477f-203">Para obtener más información acerca de esta configuración, vea [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="6477f-203">For more information about these settings, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="6477f-204">Ten en cuenta que esta misma configuración también está disponible en las directivas contra suplantación de identidad en Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="6477f-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="6477f-205">**Configuración de filtro de** suplantación: Use la opción Habilitar la inteligencia de suplantación de seguridad **para** activar o desactivar la inteligencia de suplantación.</span><span class="sxs-lookup"><span data-stu-id="6477f-205">**Spoofing filter settings**: Use the **Enable spoof intelligence?** setting to turn spoof intelligence on or off.</span></span> <span data-ttu-id="6477f-206">El valor predeterminado es **On** y le recomendamos que lo deje en.</span><span class="sxs-lookup"><span data-stu-id="6477f-206">The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="6477f-207">Para desactivarlo, deslice el botón de alternancia **a Desactivar** ![ desactivar ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="6477f-207">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     > [!NOTE]
     > <span data-ttu-id="6477f-208">No es necesario desactivar la protección contra la suplantación si el registro MX no apunta a Microsoft 365; habilitar el filtrado mejorado para conectores en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6477f-208">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="6477f-209">Para obtener instrucciones, consulte [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="6477f-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="6477f-210">**Configuración del remitente no autenticado:** puede configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6477f-210">**Unauthenticated sender settings**: You can configure the following settings:</span></span>
     - <span data-ttu-id="6477f-211">Habilitar el símbolo de interrogación del remitente no autenticado **(?):** esta configuración agrega signo de interrogación a la foto del remitente  en el cuadro De de Outlook si el mensaje no pasa comprobaciones SPF o DKIM y el mensaje no pasa dmarc ni autenticación compuesta [.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="6477f-211">**Enable unauthenticated sender question mark (?) symbol?**: This settings adds question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="6477f-212">El valor predeterminado es **Activada**.</span><span class="sxs-lookup"><span data-stu-id="6477f-212">The default value is **On**.</span></span> <span data-ttu-id="6477f-213">Para desactivarlo, deslice el botón de alternancia **a Desactivar** ![ desactivar ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="6477f-213">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>
     - <span data-ttu-id="6477f-214">**Habilitar la etiqueta "via":** esta configuración agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) es diferente del dominio en la firma DKIM o la dirección **MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="6477f-214">**Enable "via" tag?**: This setting adds a via tag (chris@contoso.com via fabrikam.com) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="6477f-215">El valor predeterminado es **Activada**.</span><span class="sxs-lookup"><span data-stu-id="6477f-215">The default value is **On**.</span></span> <span data-ttu-id="6477f-216">Para desactivarlo, deslice el botón de alternancia **a Desactivar** ![ desactivar ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="6477f-216">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="6477f-217">**Acciones:** especifique la acción que se debe realizar en los mensajes de remitentes suplantados bloqueados:</span><span class="sxs-lookup"><span data-stu-id="6477f-217">**Actions**: Specify the action to take on messages from blocked spoofed senders:</span></span>

     <span data-ttu-id="6477f-218">Si alguien que no tiene permiso para **suplantación** de dominio envía correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="6477f-218">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="6477f-219">**Mover el mensaje a las carpetas de correo no deseado de los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="6477f-219">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="6477f-220">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="6477f-220">**Quarantine the message**</span></span>

   - <span data-ttu-id="6477f-221">**Revise la configuración:** en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="6477f-221">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="6477f-222">Puede hacer clic **en Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6477f-222">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="6477f-223">Puedes activar o desactivar la **siguiente** configuración **directamente** en esta página:</span><span class="sxs-lookup"><span data-stu-id="6477f-223">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="6477f-224">**Configuración de filtro de suplantación**</span><span class="sxs-lookup"><span data-stu-id="6477f-224">**Spoof filter settings**</span></span>
       - <span data-ttu-id="6477f-225">**Configuración del remitente no autenticado**</span><span class="sxs-lookup"><span data-stu-id="6477f-225">**Unauthenticated sender settings**</span></span>
       - <span data-ttu-id="6477f-226">**Actions**</span><span class="sxs-lookup"><span data-stu-id="6477f-226">**Actions**</span></span>

   <span data-ttu-id="6477f-227">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="6477f-227">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="6477f-228">Vuelva a la **página Editar la \<Name\> directiva,** revise la configuración y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6477f-228">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="6477f-229">Usar el Centro de seguridad & cumplimiento para modificar la directiva contra suplantación de identidad predeterminada</span><span class="sxs-lookup"><span data-stu-id="6477f-229">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="6477f-230">La directiva contra suplantación de identidad predeterminada se denomina Office365 AntiPhish Default y no aparece en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="6477f-230">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="6477f-231">Para modificar la directiva contra suplantación de identidad predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6477f-231">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="6477f-232">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="6477f-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="6477f-233">En la **página Anti-phishing,** haga clic en **Directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="6477f-233">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="6477f-234">Aparece **la página Editar la directiva Office365 AntiPhish Default.**</span><span class="sxs-lookup"><span data-stu-id="6477f-234">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="6477f-235">Solo está **disponible la sección** Suplantación, que contiene una configuración idéntica para cuando se modifica una directiva [personalizada.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="6477f-235">Only the **Spoof** section is available, which contains identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   <span data-ttu-id="6477f-236">La siguiente configuración no está disponible al modificar la directiva predeterminada:</span><span class="sxs-lookup"><span data-stu-id="6477f-236">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="6477f-237">Puede ver  la sección Configuración de directiva y los valores, pero no hay ningún vínculo **Editar,** por lo que no puede modificar la configuración (nombre de directiva, descripción y a quién se aplica la directiva (se aplica a todos los destinatarios)).</span><span class="sxs-lookup"><span data-stu-id="6477f-237">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="6477f-238">No puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6477f-238">You can't delete the default policy.</span></span>
   - <span data-ttu-id="6477f-239">No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="6477f-239">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="6477f-240">En la página Editar la directiva predeterminada de **Office365 AntiPhish,** revise la configuración y, a continuación, haga clic **en Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6477f-240">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="6477f-241">Habilitar o deshabilitar directivas personalizadas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-241">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="6477f-242">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="6477f-242">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="6477f-243">Observe el valor de la **columna Estado:**</span><span class="sxs-lookup"><span data-stu-id="6477f-243">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="6477f-244">Deslice el botón de alternancia **a Desactivar** desactivar para deshabilitar ![ la ](../../media/scc-toggle-off.png) directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-244">Slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png) to disable the policy.</span></span>

   - <span data-ttu-id="6477f-245">Deslice el botón de **alternancia** a Activar ![ para habilitar la ](../../media/scc-toggle-on.png) directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-245">Slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png) to enable the policy.</span></span>

<span data-ttu-id="6477f-246">No puede deshabilitar la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6477f-246">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="6477f-247">Establecer la prioridad de las directivas contra suplantación de identidad personalizadas</span><span class="sxs-lookup"><span data-stu-id="6477f-247">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="6477f-248">De forma predeterminada, las directivas contra suplantación de identidad tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="6477f-248">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="6477f-249">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="6477f-249">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="6477f-250">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-250">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="6477f-251">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="6477f-251">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="6477f-252">Las directivas contra suplantación de identidad personalizadas se muestran en el orden en que se procesan (la primera directiva tiene el **valor de prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="6477f-252">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="6477f-253">La directiva contra suplantación de identidad predeterminada denominada Office365 AntiPhish Default tiene el valor de prioridad personalizado **Lowest** y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="6477f-253">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="6477f-254">**Nota:** En el Centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la directiva contra suplantación de identidad después de crearla.</span><span class="sxs-lookup"><span data-stu-id="6477f-254">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="6477f-255">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla contra suplantación de identidad (lo que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="6477f-255">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="6477f-256">Para cambiar la prioridad de  una directiva, haga clic en Aumentar prioridad o Disminuir  prioridad en las propiedades de la directiva (no puede modificar directamente el número de prioridad en el Centro de seguridad & cumplimiento). </span><span class="sxs-lookup"><span data-stu-id="6477f-256">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="6477f-257">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="6477f-257">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="6477f-258">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="6477f-258">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="6477f-259">Seleccione la directiva que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="6477f-259">Select the policy that you want to modify.</span></span> <span data-ttu-id="6477f-260">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="6477f-260">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="6477f-261">Aparece el control **desplegable \<name\>** Editar la directiva.</span><span class="sxs-lookup"><span data-stu-id="6477f-261">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="6477f-262">La directiva contra suplantación de identidad personalizada con el valor **de prioridad** **0** solo tiene disponible el **botón Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="6477f-262">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="6477f-263">La directiva contra suplantación de identidad personalizada con el valor **priority** más bajo (por ejemplo, **3**) solo tiene disponible **el botón Aumentar** prioridad.</span><span class="sxs-lookup"><span data-stu-id="6477f-263">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="6477f-264">Si tiene tres o más directivas contra suplantación de identidad personalizadas, las  directivas entre los valores de prioridad más alta y más baja tienen disponibles los botones Aumentar prioridad y Disminuir prioridad. </span><span class="sxs-lookup"><span data-stu-id="6477f-264">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="6477f-265">Haga **clic en Aumentar prioridad** o Disminuir **prioridad** para cambiar el valor **De** prioridad.</span><span class="sxs-lookup"><span data-stu-id="6477f-265">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="6477f-266">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6477f-266">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="6477f-267">Usar el Centro de seguridad & cumplimiento para ver directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-267">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="6477f-268">En el Centro de seguridad & cumplimiento y vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="6477f-268">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="6477f-269">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6477f-269">Do one of the following steps:</span></span>

   - <span data-ttu-id="6477f-270">Seleccione una directiva contra suplantación de identidad personalizada que desee ver.</span><span class="sxs-lookup"><span data-stu-id="6477f-270">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="6477f-271">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="6477f-271">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="6477f-272">Haga **clic en Directiva predeterminada** para ver la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6477f-272">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="6477f-273">Aparece **el \<name\> control desplegable** Editar la directiva, donde puede ver la configuración y los valores.</span><span class="sxs-lookup"><span data-stu-id="6477f-273">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="6477f-274">Usar el Centro de seguridad & cumplimiento para quitar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-274">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="6477f-275">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="6477f-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="6477f-276">Seleccione la directiva que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="6477f-276">Select the policy that you want to remove.</span></span> <span data-ttu-id="6477f-277">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="6477f-277">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="6477f-278">En el **control \<name\>** desplegable Editar la directiva que aparece, haga clic en **Eliminar** directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="6477f-278">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="6477f-279">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6477f-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="6477f-280">Usar Exchange Online PowerShell para configurar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-280">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="6477f-281">Como se describió anteriormente, una directiva contra suplantación de identidad (phishing) consta de una directiva contra suplantación de identidad (phishing) y una regla contra suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="6477f-281">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="6477f-282">En Exchange Online PowerShell, la diferencia entre las directivas contra suplantación de identidad y las reglas contra suplantación de identidad es aparente.</span><span class="sxs-lookup"><span data-stu-id="6477f-282">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="6477f-283">Las directivas contra suplantación de identidad se administran mediante los cmdlets **\* -AntiPhishPolicy** y se administran reglas contra suplantación de identidad mediante los cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="6477f-283">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="6477f-284">En PowerShell, primero se crea la directiva contra suplantación de identidad y, a continuación, se crea la regla contra suplantación de identidad que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="6477f-284">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="6477f-285">En PowerShell, se modifica la configuración de la directiva contra suplantación de identidad y la regla contra suplantación de identidad por separado.</span><span class="sxs-lookup"><span data-stu-id="6477f-285">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="6477f-286">Al quitar una directiva contra suplantación de identidad de PowerShell, la regla anti-phish correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="6477f-286">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="6477f-287">Los siguientes procedimientos de PowerShell no están disponibles en organizaciones EOP independientes que usan Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6477f-287">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="6477f-288">Usar PowerShell para crear directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-288">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="6477f-289">Crear una directiva contra la suplantación de identidad en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="6477f-289">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="6477f-290">Cree la directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6477f-290">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="6477f-291">Cree la regla contra suplantación de identidad que especifica la directiva contra suplantación de identidad a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="6477f-291">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="6477f-292">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="6477f-292">**Notes**:</span></span>

- <span data-ttu-id="6477f-293">Puede crear una nueva regla contra suplantación de identidad (phish) y asignarle una directiva anti-phish existente y no asociada.</span><span class="sxs-lookup"><span data-stu-id="6477f-293">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="6477f-294">Una regla contra la suplantación de identidad no se puede asociar a más de una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6477f-294">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="6477f-295">Puede configurar las siguientes opciones en las nuevas directivas contra suplantación de identidad en PowerShell que no están disponibles en el Centro de seguridad y cumplimiento de & hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="6477f-295">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="6477f-296">Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="6477f-296">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="6477f-297">Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="6477f-297">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="6477f-298">Una nueva directiva contra suplantación de identidad que cree en PowerShell no está visible en el Centro de seguridad y cumplimiento de & hasta que asigne la directiva a una regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6477f-298">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="6477f-299">Paso 1: Usar PowerShell para crear una directiva contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-299">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="6477f-300">Para crear una directiva contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6477f-300">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="6477f-301">En este ejemplo se crea una directiva contra phishing denominada Cuarentena de investigación con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="6477f-301">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="6477f-302">La descripción es: Directiva del departamento de investigación.</span><span class="sxs-lookup"><span data-stu-id="6477f-302">The description is: Research department policy.</span></span>
- <span data-ttu-id="6477f-303">Cambia la acción predeterminada de suplantación a Cuarentena.</span><span class="sxs-lookup"><span data-stu-id="6477f-303">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="6477f-304">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="6477f-304">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="6477f-305">Paso 2: Usar PowerShell para crear una regla contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-305">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="6477f-306">Para crear una regla contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6477f-306">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="6477f-307">En este ejemplo se crea una regla contra suplantación de identidad (phish) denominada Departamento de investigación con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="6477f-307">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="6477f-308">La regla está asociada con la directiva contra phishing denominada Cuarentena de investigación.</span><span class="sxs-lookup"><span data-stu-id="6477f-308">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="6477f-309">La regla se aplica a los miembros del grupo denominado Research Department.</span><span class="sxs-lookup"><span data-stu-id="6477f-309">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="6477f-310">Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6477f-310">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="6477f-311">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="6477f-311">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="6477f-312">Usar PowerShell para ver directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-312">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="6477f-313">Para ver las directivas anti phish existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6477f-313">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6477f-314">En este ejemplo se devuelve una lista resumida de todas las directivas contra phishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="6477f-314">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="6477f-315">En este ejemplo se devuelven todos los valores de propiedad de la directiva contra suplantación de identidad denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="6477f-315">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="6477f-316">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="6477f-316">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="6477f-317">Usar PowerShell para ver reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-317">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="6477f-318">Para ver las reglas anti phish existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6477f-318">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6477f-319">En este ejemplo se devuelve una lista resumida de todas las reglas contra phishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="6477f-319">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="6477f-320">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="6477f-320">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="6477f-321">En este ejemplo se devuelven todos los valores de propiedad de la regla contra suplantación de identidad denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="6477f-321">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="6477f-322">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="6477f-322">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="6477f-323">Usar PowerShell para modificar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-323">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="6477f-324">Aparte de los siguientes elementos, la misma configuración está disponible al modificar una directiva contra suplantación de identidad en PowerShell que al crear una directiva como se describe en Paso [1:](#step-1-use-powershell-to-create-an-anti-phish-policy) Usar PowerShell para crear una directiva contra suplantación de identidad anterior en este artículo.</span><span class="sxs-lookup"><span data-stu-id="6477f-324">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="6477f-325">El _modificador MakeDefault_ que convierte la directiva especificada en la directiva predeterminada (aplicada a todos, siempre **con** prioridad más baja y no puede eliminarla) solo está disponible cuando modifica una directiva contra suplantación de identidad en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6477f-325">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="6477f-326">No puede cambiar el nombre de una directiva contra suplantación de identidad (el cmdlet **Set-AntiPhishPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="6477f-326">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="6477f-327">Al cambiar el nombre de una directiva contra suplantación de identidad en el Centro de seguridad & cumplimiento, solo se cambia el nombre de la regla contra _suplantación de identidad_.</span><span class="sxs-lookup"><span data-stu-id="6477f-327">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="6477f-328">Para modificar una directiva contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6477f-328">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="6477f-329">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="6477f-329">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="6477f-330">Usar PowerShell para modificar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-330">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="6477f-331">La única configuración que no está disponible al modificar una regla contra suplantación de identidad en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="6477f-331">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="6477f-332">Para habilitar o deshabilitar las reglas antiphishing existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="6477f-332">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="6477f-333">De lo contrario, la misma configuración está disponible al crear una regla tal como se describe en el Paso [2: Usar PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) para crear una sección de regla contra suplantación de identidad anterior en este artículo.</span><span class="sxs-lookup"><span data-stu-id="6477f-333">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="6477f-334">Para modificar una regla contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6477f-334">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="6477f-335">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="6477f-335">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="6477f-336">Usar PowerShell para habilitar o deshabilitar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-336">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="6477f-337">Habilitar o deshabilitar una regla contra suplantación de identidad en PowerShell habilita o deshabilita toda la directiva contra suplantación de identidad (la regla anti phishing y la directiva contra suplantación de identidad asignada).</span><span class="sxs-lookup"><span data-stu-id="6477f-337">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="6477f-338">No puede habilitar ni deshabilitar la directiva contra suplantación de identidad predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="6477f-338">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="6477f-339">Para habilitar o deshabilitar una regla contra phishing en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6477f-339">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="6477f-340">En este ejemplo se deshabilita la regla contra suplantación de identidad (phish) denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="6477f-340">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="6477f-341">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="6477f-341">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="6477f-342">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) y [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="6477f-342">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="6477f-343">Usar PowerShell para establecer la prioridad de las reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-343">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="6477f-344">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="6477f-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="6477f-345">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="6477f-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="6477f-346">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="6477f-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="6477f-347">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="6477f-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="6477f-348">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="6477f-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="6477f-349">Para establecer la prioridad de una regla contra suplantación de identidad en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6477f-349">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="6477f-350">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="6477f-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="6477f-351">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="6477f-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="6477f-352">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="6477f-352">**Notes**:</span></span>

- <span data-ttu-id="6477f-353">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6477f-353">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="6477f-354">La directiva contra suplantación de identidad predeterminada no tiene una regla anti phish correspondiente y siempre tiene el valor de prioridad no modificable **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="6477f-354">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="6477f-355">Usar PowerShell para quitar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-355">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="6477f-356">Cuando se usa PowerShell para quitar una directiva contra suplantación de identidad, no se quita la regla contra suplantación de identidad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6477f-356">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="6477f-357">Para quitar una directiva contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6477f-357">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="6477f-358">En este ejemplo se quita la directiva contra suplantación de identidad denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="6477f-358">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="6477f-359">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="6477f-359">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="6477f-360">Usar PowerShell para quitar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6477f-360">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="6477f-361">Cuando usa PowerShell para quitar una regla contra phishing, no se quita la directiva anti phish correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6477f-361">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="6477f-362">Para quitar una regla contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="6477f-362">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="6477f-363">En este ejemplo se quita la regla contra suplantación de identidad (phish) denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="6477f-363">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="6477f-364">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="6477f-364">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6477f-365">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="6477f-365">How do you know these procedures worked?</span></span>

<span data-ttu-id="6477f-366">Para comprobar que ha configurado correctamente directivas contra suplantación de identidad (phishing) en Microsoft Defender para Office 365, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6477f-366">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="6477f-367">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas Contra la \>  \> **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="6477f-367">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="6477f-368">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="6477f-368">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="6477f-369">Para ver más detalles, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6477f-369">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="6477f-370">Seleccione la directiva de la lista y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="6477f-370">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="6477f-371">Haga **clic en Directiva predeterminada** y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="6477f-371">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="6477f-372">En Exchange Online PowerShell, reemplace por el nombre de la directiva o regla, ejecute el \<Name\> siguiente comando y compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="6477f-372">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```