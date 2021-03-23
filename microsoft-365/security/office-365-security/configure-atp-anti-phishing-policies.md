---
title: Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365
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
description: Los administradores pueden aprender a crear, modificar y eliminar las directivas avanzadas contra la suplantación de identidad que están disponibles en organizaciones con Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9f9fe04b2c3b6db3681212d678c8e827f6a83f41
ms.sourcegitcommit: 3d3c446d5e2e90369be1339dd0a33e71432fbc36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2021
ms.locfileid: "50994575"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="899a0-103">Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="899a0-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="899a0-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="899a0-104">**Applies to**</span></span>
- [<span data-ttu-id="899a0-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="899a0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="899a0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="899a0-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="899a0-107">Las directivas contra suplantación de identidad en [Microsoft Defender para Office 365](office-365-atp.md) pueden ayudar a proteger su organización de ataques de suplantación de identidad malintencionados y otros tipos de ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="899a0-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="899a0-108">Para obtener más información acerca de las diferencias entre las directivas contra suplantación de identidad (phishing) en Exchange Online Protection (EOP) y las directivas contra suplantación de identidad en Microsoft Defender para Office 365, vea [Anti-phishing protection](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="899a0-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="899a0-109">Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="899a0-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="899a0-110">Para mayor granularidad, también puede crear directivas personalizadas contra la suplantación de identidad que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="899a0-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="899a0-111">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="899a0-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="899a0-112">Puede configurar directivas contra la suplantación de identidad en el Centro de seguridad & cumplimiento o en PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="899a0-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="899a0-113">Para obtener información sobre cómo configurar las directivas contra suplantación de identidad más limitadas que están disponibles en las organizaciones de Exchange Online Protection (es decir, organizaciones sin Microsoft Defender para Office 365), vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="899a0-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="899a0-114">Los elementos básicos de una directiva contra la suplantación de identidad son:</span><span class="sxs-lookup"><span data-stu-id="899a0-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="899a0-115">**La directiva contra suplantación de** identidad : especifica las protecciones de suplantación de identidad (phishing) que se habilitarán o deshabilitarán y las acciones que se aplicarán a las opciones.</span><span class="sxs-lookup"><span data-stu-id="899a0-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="899a0-116">**La regla contra suplantación de** identidad : especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva) para una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="899a0-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="899a0-117">La diferencia entre estos dos elementos no es obvia cuando se administran directivas contra suplantación de identidad en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="899a0-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="899a0-118">Al crear una directiva, está creando una regla contra suplantación de identidad (phish) y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="899a0-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="899a0-119">Al modificar una directiva, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada y los filtros de destinatarios modifican la regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="899a0-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="899a0-120">Todas las demás opciones modifican la directiva contra suplantación de identidad asociada.</span><span class="sxs-lookup"><span data-stu-id="899a0-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="899a0-121">Al quitar una directiva, se quitan la regla contra phishing y la directiva contra suplantación de identidad asociada.</span><span class="sxs-lookup"><span data-stu-id="899a0-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="899a0-122">En Exchange Online PowerShell, administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="899a0-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="899a0-123">Para obtener más información, vea la sección [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="899a0-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="899a0-124">Cada organización de Microsoft Defender para Office 365 tiene una directiva contra suplantación de identidad integrada denominada Office365 AntiPhish Default que tiene estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="899a0-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="899a0-125">La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla contra la suplantación de identidad (filtros de destinatarios) asociada a la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="899a0-126">La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="899a0-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="899a0-127">Las directivas personalizadas que cree siempre tendrán una prioridad mayor.</span><span class="sxs-lookup"><span data-stu-id="899a0-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="899a0-128">La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="899a0-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="899a0-129">Para aumentar la eficacia de la protección contra suplantación de identidad (phishing) en Microsoft Defender para Office 365, puede crear directivas anti phishing personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="899a0-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="899a0-130">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="899a0-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="899a0-131">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="899a0-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="899a0-132">Para ir directamente a la **página contra suplantación** de identidad atp, use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="899a0-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="899a0-133">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="899a0-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="899a0-134">Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="899a0-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="899a0-135">Para agregar, modificar y eliminar directivas contra suplantación de identidad, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="899a0-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="899a0-136">Para obtener acceso de solo lectura a directivas contra suplantación de identidad, debe ser miembro de los grupos de roles Lector **global** o Lector **de** <sup>\*</sup> seguridad.</span><span class="sxs-lookup"><span data-stu-id="899a0-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="899a0-137">Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="899a0-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="899a0-138">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="899a0-138">**Notes**:</span></span>

  - <span data-ttu-id="899a0-139">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="899a0-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="899a0-140">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="899a0-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="899a0-141">El **grupo de roles Administración** de la organización de solo vista en Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="899a0-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="899a0-142"><sup>\*</sup> En el Centro de & seguridad, el acceso de solo lectura permite a los usuarios ver la configuración de las directivas personalizadas contra la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="899a0-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="899a0-143">Los usuarios de solo lectura no pueden ver la configuración en la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="899a0-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="899a0-144">Para obtener información sobre la configuración recomendada para las directivas contra suplantación de identidad en Microsoft Defender para Office 365, vea [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="899a0-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="899a0-145">Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="899a0-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="899a0-146">Para obtener información sobre dónde se aplican las directivas contra suplantación de identidad en la canalización de filtrado, vea [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="899a0-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="899a0-147">Usar el Centro de seguridad & cumplimiento para crear directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="899a0-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="899a0-148">La creación de una directiva contra suplantación de identidad personalizada en el Centro de seguridad & Cumplimiento crea la regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="899a0-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="899a0-149">Al crear una directiva anti phishing, solo puede especificar el nombre de la directiva, la descripción y el filtro de destinatarios que identifica a quién se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="899a0-150">Después de crear la directiva, puede modificar la directiva para cambiar o revisar la configuración predeterminada contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="899a0-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="899a0-151">En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.</span><span class="sxs-lookup"><span data-stu-id="899a0-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="899a0-152">En la **página Anti-phishing,** haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="899a0-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="899a0-153">Se abrirá el Asistente para crear una nueva directiva **contra suplantación de** identidad.</span><span class="sxs-lookup"><span data-stu-id="899a0-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="899a0-154">En la **página Nombre de la directiva,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="899a0-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="899a0-155">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="899a0-156">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="899a0-157">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="899a0-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="899a0-158">En la **página Aplicada a** que aparece, identifique los destinatarios internos a los que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="899a0-159">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="899a0-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="899a0-160">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="899a0-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="899a0-161">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="899a0-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="899a0-162">Haga **clic en Agregar una condición**.</span><span class="sxs-lookup"><span data-stu-id="899a0-162">Click **Add a condition**.</span></span> <span data-ttu-id="899a0-163">En el desplegable que aparece, seleccione una condición en **Aplicada si**:</span><span class="sxs-lookup"><span data-stu-id="899a0-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="899a0-164">**El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="899a0-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="899a0-165">**El destinatario es miembro de**: Especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="899a0-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="899a0-166">**El dominio de destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="899a0-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="899a0-167">Después de seleccionar la condición, aparece un desplegable correspondiente con **un cuadro Cualquiera de estos.**</span><span class="sxs-lookup"><span data-stu-id="899a0-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="899a0-168">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="899a0-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="899a0-169">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="899a0-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="899a0-170">Para agregar valores adicionales, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="899a0-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="899a0-171">Para quitar entradas individuales, haga clic **en Quitar** ![ icono Quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="899a0-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="899a0-172">Para quitar toda la condición, haga clic **en Quitar** icono Quitar en ![ la ](../../media/scc-remove-icon.png) condición.</span><span class="sxs-lookup"><span data-stu-id="899a0-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="899a0-173">Para agregar una condición adicional, haga clic **en Agregar una condición** y seleccione un valor restante en Aplicado **si**.</span><span class="sxs-lookup"><span data-stu-id="899a0-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="899a0-174">Para agregar excepciones, haga clic **en Agregar una condición** y seleccione una excepción en Excepto **si**.</span><span class="sxs-lookup"><span data-stu-id="899a0-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="899a0-175">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="899a0-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="899a0-176">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="899a0-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="899a0-177">En la **página Revisar la configuración** que aparece, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="899a0-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="899a0-178">Puede hacer clic **en Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="899a0-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="899a0-179">Cuando haya terminado, haga clic **en Crear esta directiva.**</span><span class="sxs-lookup"><span data-stu-id="899a0-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="899a0-180">Haga **clic en Aceptar** en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="899a0-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="899a0-181">Después de crear la directiva contra suplantación de identidad con esta configuración general, use las instrucciones de la sección siguiente para configurar las opciones de protección en la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="899a0-182">Usar el Centro de & seguridad para modificar directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="899a0-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="899a0-183">Use los siguientes procedimientos para modificar las directivas contra suplantación de identidad: una nueva directiva que creó o directivas existentes que ya ha personalizado.</span><span class="sxs-lookup"><span data-stu-id="899a0-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="899a0-184">Si aún no está allí, abra el Centro de seguridad & cumplimiento y vaya a **Directiva** de administración de amenazas \>  \> **contra la suplantación** de identidad atp .</span><span class="sxs-lookup"><span data-stu-id="899a0-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="899a0-185">Seleccione la directiva contra suplantación de identidad personalizada que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="899a0-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="899a0-186">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="899a0-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="899a0-187">Aparece el control **desplegable \<name\>** Editar la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="899a0-188">Si **hace clic** en Editar en cualquier sección, podrá acceder a la configuración de esa sección.</span><span class="sxs-lookup"><span data-stu-id="899a0-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="899a0-189">Los pasos siguientes se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="899a0-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="899a0-190">Después de  hacer clic en Editar en una sección, la configuración disponible se presenta en un formato de asistente,  pero  puede saltar dentro de las páginas en cualquier orden y puede hacer clic en Guardar en cualquier página (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** cancelar o cerrar cerrar icono para volver a la página Editar la directiva (no es necesario visitar la última página del asistente para guardar o salir).</span><span class="sxs-lookup"><span data-stu-id="899a0-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="899a0-191">**Configuración de directiva:** haga clic **en Editar** para modificar la misma configuración que estaba disponible al [crear la directiva](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="899a0-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="899a0-192">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="899a0-192">**Name**</span></span>
   - <span data-ttu-id="899a0-193">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="899a0-193">**Description**</span></span>
   - <span data-ttu-id="899a0-194">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="899a0-194">**Applied to**</span></span>
   - <span data-ttu-id="899a0-195">**Revisar la configuración**</span><span class="sxs-lookup"><span data-stu-id="899a0-195">**Review your settings**</span></span>

   <span data-ttu-id="899a0-196">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="899a0-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="899a0-197">**Suplantación:** haga clic **en Editar** para modificar los remitentes protegidos y los dominios protegidos de la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="899a0-198">Esta configuración es una condición para la directiva que identifica remitentes suplantados para buscar (individualmente o por dominio) en la dirección De de los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="899a0-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="899a0-199">Para obtener más información, vea Configuración de suplantación en directivas contra suplantación de identidad en [Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="899a0-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="899a0-200">**Agregar usuarios para proteger**: El valor predeterminado es **Off**.</span><span class="sxs-lookup"><span data-stu-id="899a0-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="899a0-201">Para activarlo, deslice el botón de alternancia a **On** y, a continuación, haga clic en **el botón Agregar usuario** que aparece.</span><span class="sxs-lookup"><span data-stu-id="899a0-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="899a0-202">En el **control desplegable Agregar** usuario que aparece, configure los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="899a0-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="899a0-203">**Dirección de correo** electrónico :</span><span class="sxs-lookup"><span data-stu-id="899a0-203">**Email address**:</span></span>

       - <span data-ttu-id="899a0-204">Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="899a0-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="899a0-205">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.</span><span class="sxs-lookup"><span data-stu-id="899a0-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="899a0-206">Para quitar una entrada, haga clic **en Quitar** icono Quitar ![ del ](../../media/scc-remove-icon.png) usuario.</span><span class="sxs-lookup"><span data-stu-id="899a0-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="899a0-207">**Nombre:** este valor se rellena en función de la dirección de correo electrónico seleccionada, pero puede cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="899a0-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="899a0-208">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="899a0-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="899a0-209">Para editar una entrada existente, seleccione el usuario protegido en la lista.</span><span class="sxs-lookup"><span data-stu-id="899a0-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="899a0-210">En cada directiva contra phishing, puede especificar un máximo de 60 usuarios protegidos (direcciones de correo electrónico del remitente).</span><span class="sxs-lookup"><span data-stu-id="899a0-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="899a0-211">No puede especificar el mismo usuario protegido en varias directivas.</span><span class="sxs-lookup"><span data-stu-id="899a0-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="899a0-212">La protección de suplantación de usuario no funciona si el remitente y el destinatario se han comunicado previamente por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="899a0-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="899a0-213">Si el remitente y el destinatario nunca se han comunicado por correo electrónico, el mensaje se identificará como un intento de suplantación.</span><span class="sxs-lookup"><span data-stu-id="899a0-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="899a0-214">**Agregar dominios para proteger:** Configure una o ambas opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="899a0-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="899a0-215">**Incluya automáticamente los dominios que tengo:** El valor predeterminado es **Off**.</span><span class="sxs-lookup"><span data-stu-id="899a0-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="899a0-216">Para activarlo, deslice el botón de alternancia a **On**.</span><span class="sxs-lookup"><span data-stu-id="899a0-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="899a0-217">**Incluir dominios personalizados:** el valor predeterminado es **Off**.</span><span class="sxs-lookup"><span data-stu-id="899a0-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="899a0-218">Para activarlo, deslice el botón de  alternancia en **On** y, en el cuadro Agregar dominios, escriba el nombre de dominio (por ejemplo, contoso.com), presione ENTRAR y repita según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="899a0-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="899a0-219">Puede tener un máximo de 50 dominios en todas las directivas contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="899a0-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="899a0-220">**Acciones:** haga clic en **Editar**</span><span class="sxs-lookup"><span data-stu-id="899a0-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="899a0-221">**Si** un usuario suplantado envía correo electrónico: configure una de las siguientes acciones para los mensajes en los que el remitente suplantado sea uno de los usuarios protegidos que especificó en Agregar usuarios para **proteger**:</span><span class="sxs-lookup"><span data-stu-id="899a0-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="899a0-222">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="899a0-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="899a0-223">**Redirigir el mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="899a0-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="899a0-224">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="899a0-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="899a0-225">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="899a0-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="899a0-226">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="899a0-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="899a0-227">**Eliminar el mensaje antes de entregarlo**</span><span class="sxs-lookup"><span data-stu-id="899a0-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="899a0-228">**Si** un dominio suplantado envía correo electrónico: configure una de las siguientes acciones para los mensajes en los que el remitente suplantado se encuentra en uno de los dominios protegidos que especificó en Agregar dominios para **proteger**:</span><span class="sxs-lookup"><span data-stu-id="899a0-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="899a0-229">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="899a0-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="899a0-230">**Redirigir el mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="899a0-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="899a0-231">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="899a0-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="899a0-232">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="899a0-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="899a0-233">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="899a0-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="899a0-234">**Eliminar el mensaje antes de entregarlo**</span><span class="sxs-lookup"><span data-stu-id="899a0-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="899a0-235">Haga clic en Activar sugerencias de seguridad **de suplantación** y configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="899a0-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="899a0-236">**Sugerencia para usuarios suplantados:** el valor predeterminado es **Off**.</span><span class="sxs-lookup"><span data-stu-id="899a0-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="899a0-237">Para activarlo, deslice el botón de alternancia a **On**.</span><span class="sxs-lookup"><span data-stu-id="899a0-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="899a0-238">**Sugerencia para dominios suplantados:** el valor predeterminado es **Off**.</span><span class="sxs-lookup"><span data-stu-id="899a0-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="899a0-239">Para activarlo, deslice el botón de alternancia a **On**.</span><span class="sxs-lookup"><span data-stu-id="899a0-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="899a0-240">**Sugerencia para mostrar caracteres inusuales:** el valor predeterminado es **Off**.</span><span class="sxs-lookup"><span data-stu-id="899a0-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="899a0-241">Para activarlo, deslice el botón de alternancia a **On**.</span><span class="sxs-lookup"><span data-stu-id="899a0-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="899a0-242">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="899a0-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="899a0-243">**Inteligencia de buzones**:</span><span class="sxs-lookup"><span data-stu-id="899a0-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="899a0-244">**Habilitar la inteligencia de buzones de correo:** el valor predeterminado es **On**.</span><span class="sxs-lookup"><span data-stu-id="899a0-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="899a0-245">Para desactivarlo, deslice el botón de alternancia a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="899a0-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="899a0-246">**Habilitar la protección de suplantación basada** en inteligencia de buzones de correo: esta configuración solo está disponible si Habilitar inteligencia **de buzones de correo es** **On**.</span><span class="sxs-lookup"><span data-stu-id="899a0-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="899a0-247">Active esta configuración para especificar la acción que se debe realizar en los mensajes para las detecciones de suplantación de los resultados de inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="899a0-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="899a0-248">En **Si un usuario** suplantado envía correo electrónico, puede especificar una de las siguientes acciones (las mismas acciones que están disponibles para usuarios protegidos y dominios protegidos):</span><span class="sxs-lookup"><span data-stu-id="899a0-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="899a0-249">**No aplique ninguna** acción: tenga en cuenta que este valor tiene el mismo resultado que activar Habilitar inteligencia de buzones **de correo,** pero desactivar Habilitar la protección de suplantación basada en inteligencia de **buzones.**</span><span class="sxs-lookup"><span data-stu-id="899a0-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="899a0-250">**Redirigir el mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="899a0-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="899a0-251">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="899a0-251">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="899a0-252">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="899a0-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="899a0-253">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="899a0-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="899a0-254">**Eliminar el mensaje antes de entregarlo**</span><span class="sxs-lookup"><span data-stu-id="899a0-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="899a0-255">**Agregar remitentes y dominios de confianza:** especifique excepciones para la directiva:</span><span class="sxs-lookup"><span data-stu-id="899a0-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="899a0-256">**Remitentes de confianza:**</span><span class="sxs-lookup"><span data-stu-id="899a0-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="899a0-257">Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="899a0-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="899a0-258">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.</span><span class="sxs-lookup"><span data-stu-id="899a0-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="899a0-259">Para quitar una entrada, haga clic **en Quitar** icono Quitar ![ del ](../../media/scc-remove-icon.png) usuario.</span><span class="sxs-lookup"><span data-stu-id="899a0-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="899a0-260">**Dominios de** confianza: escriba el nombre de dominio (por ejemplo, contoso.com), presione ENTRAR y repita según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="899a0-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="899a0-261">**Revise la configuración:** en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="899a0-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="899a0-262">Puede hacer clic **en Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="899a0-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="899a0-263">Puedes activar o desactivar la **siguiente** configuración **directamente** en esta página:</span><span class="sxs-lookup"><span data-stu-id="899a0-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="899a0-264">**Usuarios protegidos**</span><span class="sxs-lookup"><span data-stu-id="899a0-264">**Protected users**</span></span>
       - <span data-ttu-id="899a0-265">**Dominios protegidos** \> **Incluir dominios de mi propiedad**</span><span class="sxs-lookup"><span data-stu-id="899a0-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="899a0-266">**Dominios protegidos** \> **Dominios protegidos** (dominios personalizados)</span><span class="sxs-lookup"><span data-stu-id="899a0-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="899a0-267">**Inteligencia de buzones**</span><span class="sxs-lookup"><span data-stu-id="899a0-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="899a0-268">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="899a0-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="899a0-269">**Suplantación:**  haga clic en Editar para activar o desactivar la inteligencia de suplantación de identidad, activar o desactivar la identificación de remitentes no autenticados en Outlook y configurar la acción para que se aplique a los mensajes de remitentes suplantados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="899a0-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="899a0-270">Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="899a0-270">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="899a0-271">Tenga en cuenta que esta misma configuración también está disponible en las directivas contra suplantación de identidad en EOP.</span><span class="sxs-lookup"><span data-stu-id="899a0-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="899a0-272">**Configuración del filtro de suplantación:** el valor predeterminado es **On** y le recomendamos que lo deje en.</span><span class="sxs-lookup"><span data-stu-id="899a0-272">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="899a0-273">Para desactivarlo, deslice el botón de alternancia a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="899a0-273">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="899a0-274">Para obtener más información, vea [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="899a0-274">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="899a0-275">No es necesario deshabilitar la protección contra la suplantación si el registro MX no apunta a Microsoft 365; habilitar el filtrado mejorado para conectores en su lugar.</span><span class="sxs-lookup"><span data-stu-id="899a0-275">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="899a0-276">Para obtener instrucciones, consulte [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="899a0-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="899a0-277">**Habilitar la característica Remitente no autenticado:** el valor predeterminado es **On**.</span><span class="sxs-lookup"><span data-stu-id="899a0-277">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="899a0-278">Para desactivarlo, deslice el botón de alternancia a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="899a0-278">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="899a0-279">**Acciones:** especifique la acción que se debe realizar en los mensajes que no puedan suplantar la inteligencia:</span><span class="sxs-lookup"><span data-stu-id="899a0-279">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="899a0-280">Si alguien que no tiene permiso para **suplantación** de dominio envía correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="899a0-280">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="899a0-281">**Mover el mensaje a las carpetas de correo no deseado de los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="899a0-281">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="899a0-282">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="899a0-282">**Quarantine the message**</span></span>

   - <span data-ttu-id="899a0-283">**Revise la configuración:** en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="899a0-283">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="899a0-284">Puede hacer clic **en Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="899a0-284">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="899a0-285">Puedes activar o desactivar la **siguiente** configuración **directamente** en esta página:</span><span class="sxs-lookup"><span data-stu-id="899a0-285">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="899a0-286">**Habilitar la protección contra la suplantación**</span><span class="sxs-lookup"><span data-stu-id="899a0-286">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="899a0-287">**Habilitar la característica Remitente no autenticado**</span><span class="sxs-lookup"><span data-stu-id="899a0-287">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="899a0-288">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="899a0-288">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="899a0-289">**Configuración avanzada:** haga clic **en Editar** para configurar los umbrales de suplantación de identidad avanzados.</span><span class="sxs-lookup"><span data-stu-id="899a0-289">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="899a0-290">Para obtener más información, vea [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="899a0-290">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="899a0-291">**Umbrales de suplantación de identidad avanzados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="899a0-291">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="899a0-292">**1- Estándar** (este es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="899a0-292">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="899a0-293">**2 : agresivo**</span><span class="sxs-lookup"><span data-stu-id="899a0-293">**2 - Aggressive**</span></span>
   - <span data-ttu-id="899a0-294">**3: más agresivo**</span><span class="sxs-lookup"><span data-stu-id="899a0-294">**3 - More aggressive**</span></span>
   - <span data-ttu-id="899a0-295">**4: más agresivo**</span><span class="sxs-lookup"><span data-stu-id="899a0-295">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="899a0-296">**Revisa la configuración:** haz clic **en Editar** para volver a la **página Umbrales de suplantación de** identidad avanzada.</span><span class="sxs-lookup"><span data-stu-id="899a0-296">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="899a0-297">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="899a0-297">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="899a0-298">Vuelva a la **página Editar la \<Name\> directiva,** revise la configuración y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="899a0-298">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="899a0-299">Usar el Centro de & seguridad para modificar la directiva contra suplantación de identidad predeterminada en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="899a0-299">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="899a0-300">La directiva contra suplantación de identidad predeterminada en Microsoft Defender para Office 365 se denomina Office365 AntiPhish Default y no aparece en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="899a0-300">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="899a0-301">Para modificar la directiva contra suplantación de identidad predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="899a0-301">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="899a0-302">En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.</span><span class="sxs-lookup"><span data-stu-id="899a0-302">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="899a0-303">En la **página Anti-phishing,** haga clic en **Directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="899a0-303">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="899a0-304">Aparece **la página Editar la directiva Office365 AntiPhish Default.**</span><span class="sxs-lookup"><span data-stu-id="899a0-304">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="899a0-305">Las siguientes secciones están disponibles, que contienen una configuración idéntica para cuando [se modifica una directiva personalizada:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="899a0-305">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="899a0-306">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="899a0-306">**Impersonation**</span></span>
   - <span data-ttu-id="899a0-307">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="899a0-307">**Spoof**</span></span>
   - <span data-ttu-id="899a0-308">**Configuración avanzada**</span><span class="sxs-lookup"><span data-stu-id="899a0-308">**Advanced settings**</span></span>

   <span data-ttu-id="899a0-309">La siguiente configuración no está disponible al modificar la directiva predeterminada:</span><span class="sxs-lookup"><span data-stu-id="899a0-309">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="899a0-310">Puede ver  la sección Configuración de directiva y los valores, pero no hay ningún vínculo **Editar,** por lo que no puede modificar la configuración (nombre de directiva, descripción y a quién se aplica la directiva (se aplica a todos los destinatarios)).</span><span class="sxs-lookup"><span data-stu-id="899a0-310">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="899a0-311">No puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="899a0-311">You can't delete the default policy.</span></span>
   - <span data-ttu-id="899a0-312">No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="899a0-312">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="899a0-313">En la página Editar la directiva predeterminada de **Office365 AntiPhish,** revise la configuración y, a continuación, haga clic **en Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="899a0-313">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="899a0-314">Habilitar o deshabilitar directivas anti phishing personalizadas en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="899a0-314">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="899a0-315">En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.</span><span class="sxs-lookup"><span data-stu-id="899a0-315">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="899a0-316">Observe el valor de la **columna Estado:**</span><span class="sxs-lookup"><span data-stu-id="899a0-316">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="899a0-317">Deslice el botón de **alternancia a Desactivado** para deshabilitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-317">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="899a0-318">Deslice el botón de **alternancia a Activar** para habilitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-318">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="899a0-319">No puede deshabilitar la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="899a0-319">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="899a0-320">Establecer la prioridad de las directivas anti phishing personalizadas en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="899a0-320">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="899a0-321">De forma predeterminada, las directivas contra suplantación de identidad tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="899a0-321">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="899a0-322">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="899a0-322">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="899a0-323">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-323">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="899a0-324">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="899a0-324">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="899a0-325">Las directivas contra suplantación de identidad personalizadas se muestran en el orden en que se procesan (la primera directiva tiene el **valor de prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="899a0-325">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="899a0-326">La directiva contra suplantación de identidad predeterminada denominada Office365 AntiPhish Default tiene el valor de prioridad personalizado **Lowest** y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="899a0-326">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="899a0-327">**Nota:** En el Centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la directiva contra suplantación de identidad después de crearla.</span><span class="sxs-lookup"><span data-stu-id="899a0-327">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="899a0-328">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla contra suplantación de identidad (lo que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="899a0-328">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="899a0-329">Para cambiar la prioridad de  una directiva, haga clic en Aumentar prioridad o Disminuir  prioridad en las propiedades de la directiva (no puede modificar directamente el número de prioridad en el Centro de seguridad & cumplimiento). </span><span class="sxs-lookup"><span data-stu-id="899a0-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="899a0-330">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="899a0-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="899a0-331">En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.</span><span class="sxs-lookup"><span data-stu-id="899a0-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="899a0-332">Seleccione la directiva que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="899a0-332">Select the policy that you want to modify.</span></span> <span data-ttu-id="899a0-333">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="899a0-333">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="899a0-334">Aparece el control **desplegable \<name\>** Editar la directiva.</span><span class="sxs-lookup"><span data-stu-id="899a0-334">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="899a0-335">La directiva contra suplantación de identidad personalizada con el valor **de prioridad** **0** solo tiene disponible el **botón Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="899a0-335">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="899a0-336">La directiva contra suplantación de identidad personalizada con el valor **priority** más bajo (por ejemplo, **3**) solo tiene disponible **el botón Aumentar** prioridad.</span><span class="sxs-lookup"><span data-stu-id="899a0-336">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="899a0-337">Si tiene tres o más directivas contra suplantación de identidad personalizadas, las  directivas entre los valores de prioridad más alta y más baja tienen disponibles los botones Aumentar prioridad y Disminuir prioridad. </span><span class="sxs-lookup"><span data-stu-id="899a0-337">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="899a0-338">Haga **clic en Aumentar prioridad** o Disminuir **prioridad** para cambiar el valor **De** prioridad.</span><span class="sxs-lookup"><span data-stu-id="899a0-338">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="899a0-339">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="899a0-339">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="899a0-340">Usar el Centro de seguridad & cumplimiento para ver directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="899a0-340">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="899a0-341">En el Centro de seguridad & cumplimiento y vaya a **Directiva de administración** de amenazas ATP contra \>  \> **suplantación** de identidad .</span><span class="sxs-lookup"><span data-stu-id="899a0-341">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="899a0-342">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="899a0-342">Do one of the following steps:</span></span>

   - <span data-ttu-id="899a0-343">Seleccione una directiva contra suplantación de identidad personalizada que desee ver.</span><span class="sxs-lookup"><span data-stu-id="899a0-343">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="899a0-344">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="899a0-344">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="899a0-345">Haga **clic en Directiva predeterminada** para ver la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="899a0-345">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="899a0-346">Aparece **el \<name\> control desplegable** Editar la directiva, donde puede ver la configuración y los valores.</span><span class="sxs-lookup"><span data-stu-id="899a0-346">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="899a0-347">Usar el Centro de & seguridad para quitar directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="899a0-347">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="899a0-348">En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.</span><span class="sxs-lookup"><span data-stu-id="899a0-348">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="899a0-349">Seleccione la directiva que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="899a0-349">Select the policy that you want to remove.</span></span> <span data-ttu-id="899a0-350">Si ya está seleccionado, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="899a0-350">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="899a0-351">En el **control \<name\>** desplegable Editar la directiva que aparece, haga clic en **Eliminar** directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="899a0-351">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="899a0-352">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="899a0-352">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="899a0-353">Usar Exchange Online PowerShell para configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="899a0-353">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="899a0-354">Como se describió anteriormente, una directiva contra correo no deseado consta de una directiva contra suplantación de identidad (phish) y una regla contra suplantación de identidad (phish).</span><span class="sxs-lookup"><span data-stu-id="899a0-354">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="899a0-355">En Exchange Online PowerShell, la diferencia entre las directivas contra suplantación de identidad (phish) y las reglas contra suplantación de identidad (phishing) es aparente.</span><span class="sxs-lookup"><span data-stu-id="899a0-355">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="899a0-356">Las directivas contra suplantación de identidad se administran mediante los cmdlets **\* -AntiPhishPolicy** y se administran reglas contra suplantación de identidad mediante los cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="899a0-356">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="899a0-357">En PowerShell, primero se crea la directiva contra suplantación de identidad y, a continuación, se crea la regla contra suplantación de identidad que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="899a0-357">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="899a0-358">En PowerShell, se modifica la configuración de la directiva contra suplantación de identidad y la regla contra suplantación de identidad por separado.</span><span class="sxs-lookup"><span data-stu-id="899a0-358">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="899a0-359">Al quitar una directiva contra suplantación de identidad de PowerShell, la regla anti-phish correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="899a0-359">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="899a0-360">Usar PowerShell para crear directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-360">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="899a0-361">Crear una directiva contra la suplantación de identidad en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="899a0-361">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="899a0-362">Cree la directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="899a0-362">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="899a0-363">Cree la regla contra suplantación de identidad que especifica la directiva contra suplantación de identidad a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="899a0-363">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="899a0-364">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="899a0-364">**Notes**:</span></span>

- <span data-ttu-id="899a0-365">Puede crear una nueva regla contra suplantación de identidad (phish) y asignarle una directiva anti-phish existente y no asociada.</span><span class="sxs-lookup"><span data-stu-id="899a0-365">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="899a0-366">Una regla contra la suplantación de identidad no se puede asociar a más de una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="899a0-366">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="899a0-367">Puede configurar las siguientes opciones en las nuevas directivas contra suplantación de identidad en PowerShell que no están disponibles en el Centro de seguridad y cumplimiento de & hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="899a0-367">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="899a0-368">Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="899a0-368">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="899a0-369">Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="899a0-369">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="899a0-370">Una nueva directiva contra suplantación de identidad que cree en PowerShell no está visible en el Centro de seguridad y cumplimiento de & hasta que asigne la directiva a una regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="899a0-370">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="899a0-371">Paso 1: Usar PowerShell para crear una directiva contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-371">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="899a0-372">Para crear una directiva contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="899a0-372">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="899a0-373">En este ejemplo se crea una directiva contra phishing denominada Cuarentena de investigación con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="899a0-373">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="899a0-374">La directiva está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="899a0-374">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="899a0-375">La descripción es: Directiva del departamento de investigación.</span><span class="sxs-lookup"><span data-stu-id="899a0-375">The description is: Research department policy.</span></span>
- <span data-ttu-id="899a0-376">Habilita la protección de dominios de la organización para todos los dominios aceptados y la protección de dominios de destino para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="899a0-376">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="899a0-377">Especifica Mai Fujito (mfujito@fabrikam.com) como el usuario que se debe proteger de la suplantación.</span><span class="sxs-lookup"><span data-stu-id="899a0-377">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="899a0-378">Habilita la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="899a0-378">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="899a0-379">Habilita la protección de inteligencia de buzones de correo y especifica la acción de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="899a0-379">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="899a0-380">Habilita las sugerencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="899a0-380">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="899a0-381">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="899a0-381">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="899a0-382">Paso 2: Usar PowerShell para crear una regla contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-382">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="899a0-383">Para crear una regla contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="899a0-383">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="899a0-384">En este ejemplo se crea una regla contra suplantación de identidad (phish) denominada Departamento de investigación con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="899a0-384">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="899a0-385">La regla está asociada con la directiva contra phishing denominada Cuarentena de investigación.</span><span class="sxs-lookup"><span data-stu-id="899a0-385">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="899a0-386">La regla se aplica a los miembros del grupo denominado Research Department.</span><span class="sxs-lookup"><span data-stu-id="899a0-386">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="899a0-387">Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="899a0-387">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="899a0-388">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="899a0-388">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="899a0-389">Usar PowerShell para ver directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-389">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="899a0-390">Para ver las directivas anti phish existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="899a0-390">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="899a0-391">En este ejemplo se devuelve una lista resumida de todas las directivas contra phishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="899a0-391">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="899a0-392">En este ejemplo se devuelven todos los valores de propiedad de la directiva contra suplantación de identidad denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="899a0-392">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="899a0-393">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="899a0-393">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="899a0-394">Usar PowerShell para ver reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-394">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="899a0-395">Para ver las reglas anti phish existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="899a0-395">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="899a0-396">En este ejemplo se devuelve una lista resumida de todas las reglas contra phishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="899a0-396">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="899a0-397">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="899a0-397">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="899a0-398">En este ejemplo se devuelven todos los valores de propiedad de la regla contra suplantación de identidad denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="899a0-398">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="899a0-399">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="899a0-399">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="899a0-400">Usar PowerShell para modificar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-400">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="899a0-401">Aparte de los siguientes elementos, la misma configuración está disponible al modificar una directiva contra suplantación de identidad en PowerShell que al crear la directiva, tal como se describe en el Paso 1: Usar PowerShell para crear una sección de directiva contra suplantación de identidad [(phish policy)](#step-1-use-powershell-to-create-an-anti-phish-policy) anterior en este artículo.</span><span class="sxs-lookup"><span data-stu-id="899a0-401">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="899a0-402">El _modificador MakeDefault_ que convierte la directiva especificada en la directiva predeterminada (aplicada a todos, siempre **con** prioridad más baja y no puede eliminarla) solo está disponible cuando modifica una directiva contra suplantación de identidad en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="899a0-402">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="899a0-403">No puede cambiar el nombre de una directiva contra suplantación de identidad (el cmdlet **Set-AntiPhishPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="899a0-403">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="899a0-404">Al cambiar el nombre de una directiva contra suplantación de identidad en el Centro de seguridad & cumplimiento, solo se cambia el nombre de la regla contra _suplantación de identidad_.</span><span class="sxs-lookup"><span data-stu-id="899a0-404">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="899a0-405">Para modificar una directiva contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="899a0-405">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="899a0-406">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="899a0-406">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="899a0-407">Usar PowerShell para modificar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-407">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="899a0-408">La única configuración que no está disponible al modificar una regla contra suplantación de identidad en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="899a0-408">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="899a0-409">Para habilitar o deshabilitar las reglas antiphishing existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="899a0-409">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="899a0-410">De lo contrario, no hay ninguna configuración adicional disponible al modificar una regla contra suplantación de identidad en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="899a0-410">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="899a0-411">La misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) para crear una regla contra suplantación de identidad anterior en este artículo.</span><span class="sxs-lookup"><span data-stu-id="899a0-411">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="899a0-412">Para modificar una regla contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="899a0-412">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="899a0-413">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="899a0-413">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="899a0-414">Usar PowerShell para habilitar o deshabilitar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-414">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="899a0-415">Habilitar o deshabilitar una regla contra suplantación de identidad en PowerShell habilita o deshabilita toda la directiva contra suplantación de identidad (la regla anti phishing y la directiva contra suplantación de identidad asignada).</span><span class="sxs-lookup"><span data-stu-id="899a0-415">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="899a0-416">No puede habilitar ni deshabilitar la directiva contra suplantación de identidad predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="899a0-416">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="899a0-417">Para habilitar o deshabilitar una regla contra phishing en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="899a0-417">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="899a0-418">En este ejemplo se deshabilita la regla contra suplantación de identidad (phish) denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="899a0-418">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="899a0-419">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="899a0-419">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="899a0-420">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) y [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="899a0-420">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="899a0-421">Usar PowerShell para establecer la prioridad de las reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-421">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="899a0-422">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="899a0-422">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="899a0-423">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="899a0-423">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="899a0-424">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="899a0-424">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="899a0-425">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="899a0-425">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="899a0-426">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="899a0-426">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="899a0-427">Para establecer la prioridad de una regla contra suplantación de identidad en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="899a0-427">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="899a0-428">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="899a0-428">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="899a0-429">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="899a0-429">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="899a0-430">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="899a0-430">**Notes**:</span></span>

- <span data-ttu-id="899a0-431">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="899a0-431">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="899a0-432">La directiva contra suplantación de identidad predeterminada no tiene una regla anti phish correspondiente y siempre tiene el valor de prioridad no modificable **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="899a0-432">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="899a0-433">Usar PowerShell para quitar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-433">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="899a0-434">Cuando se usa PowerShell para quitar una directiva contra suplantación de identidad, no se quita la regla contra suplantación de identidad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="899a0-434">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="899a0-435">Para quitar una directiva contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="899a0-435">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="899a0-436">En este ejemplo se quita la directiva contra suplantación de identidad denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="899a0-436">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="899a0-437">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="899a0-437">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="899a0-438">Usar PowerShell para quitar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="899a0-438">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="899a0-439">Cuando usa PowerShell para quitar una regla contra phishing, no se quita la directiva anti phish correspondiente.</span><span class="sxs-lookup"><span data-stu-id="899a0-439">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="899a0-440">Para quitar una regla contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="899a0-440">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="899a0-441">En este ejemplo se quita la regla contra suplantación de identidad (phish) denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="899a0-441">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="899a0-442">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="899a0-442">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="899a0-443">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="899a0-443">How do you know these procedures worked?</span></span>

<span data-ttu-id="899a0-444">Para comprobar que ha configurado correctamente directivas contra suplantación de identidad (phishing) en Microsoft Defender para Office 365, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="899a0-444">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="899a0-445">En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.</span><span class="sxs-lookup"><span data-stu-id="899a0-445">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="899a0-446">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="899a0-446">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="899a0-447">Para ver más detalles, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="899a0-447">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="899a0-448">Seleccione la directiva de la lista y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="899a0-448">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="899a0-449">Haga **clic en Directiva predeterminada** y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="899a0-449">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="899a0-450">En Exchange Online PowerShell, reemplace por el nombre de la directiva o \<Name\> regla y ejecute el siguiente comando y compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="899a0-450">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```