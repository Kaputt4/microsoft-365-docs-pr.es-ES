---
title: Configurar directivas contra la suplantación de identidad en Microsoft Defender para Office 365
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
description: Los administradores pueden aprender a crear, modificar y eliminar las directivas avanzadas contra la suplantación de identidad que están disponibles en las organizaciones con Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 89b931b37119d7c8c689d0f3c044fcd550db67ab
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287502"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="37d30-103">Configurar directivas contra la suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="37d30-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="37d30-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="37d30-104">**Applies to**</span></span>
- [<span data-ttu-id="37d30-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="37d30-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="37d30-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37d30-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="37d30-107">Las directivas contra suplantación de identidad en Microsoft Defender para [Office 365](office-365-atp.md) pueden ayudar a proteger su organización contra ataques de suplantación de identidad malintencionados y otros tipos de ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="37d30-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="37d30-108">Para obtener más información sobre las diferencias entre las directivas contra suplantación de identidad en Exchange Online Protection (EOP) y las directivas contra suplantación de identidad en Microsoft Defender para Office 365, vea [Protección](anti-phishing-protection.md)contra la suplantación de identidad .</span><span class="sxs-lookup"><span data-stu-id="37d30-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="37d30-109">Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37d30-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="37d30-110">Para mayor granularidad, también puede crear directivas contra suplantación de identidad personalizadas que se apliquen a usuarios, grupos o dominios específicos de su organización.</span><span class="sxs-lookup"><span data-stu-id="37d30-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="37d30-111">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="37d30-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="37d30-112">Puede configurar directivas contra suplantación de identidad en el Centro de seguridad y & cumplimiento o en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37d30-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="37d30-113">Para obtener información sobre cómo configurar las directivas contra suplantación de identidad más limitadas que están disponibles en las organizaciones de Exchange Online Protection (es decir, las organizaciones sin Microsoft Defender para Office 365), vea Configurar directivas contra suplantación de identidad en [EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="37d30-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="37d30-114">Los elementos básicos de una directiva contra suplantación de identidad son:</span><span class="sxs-lookup"><span data-stu-id="37d30-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="37d30-115">**La directiva contra suplantación de** identidad : especifica las protecciones de suplantación de identidad que se habilitarán o deshabilitarán, y las acciones para aplicar opciones.</span><span class="sxs-lookup"><span data-stu-id="37d30-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="37d30-116">**La regla contra suplantación de** identidad: especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva) para una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="37d30-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="37d30-117">La diferencia entre estos dos elementos no es obvia al administrar directivas contra la suplantación de identidad en el Centro de & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="37d30-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="37d30-118">Cuando crea una directiva, realmente está creando una regla contra suplantación de identidad y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="37d30-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="37d30-119">Al modificar una directiva, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada, y los filtros de destinatarios modifican la regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="37d30-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="37d30-120">Todas las demás opciones modifican la directiva contra suplantación de identidad asociada.</span><span class="sxs-lookup"><span data-stu-id="37d30-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="37d30-121">Al quitar una directiva, se quitan la regla contra suplantación de identidad y la directiva contra suplantación de identidad asociada.</span><span class="sxs-lookup"><span data-stu-id="37d30-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="37d30-122">En Exchange Online PowerShell, la directiva y la regla se administran por separado.</span><span class="sxs-lookup"><span data-stu-id="37d30-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="37d30-123">Para obtener más información, vea la sección Usar Exchange Online PowerShell para configurar directivas contra suplantación de identidad en Microsoft Defender para [Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="37d30-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="37d30-124">Cada organización de Microsoft Defender para Office 365 tiene una directiva contra suplantación de identidad integrada denominada Office365 AntiPhish Default que tiene estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="37d30-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="37d30-125">La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla contra suplantación de identidad (filtros de destinatarios) asociada a la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="37d30-126">La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="37d30-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="37d30-127">Las directivas personalizadas que cree siempre tendrán una prioridad mayor.</span><span class="sxs-lookup"><span data-stu-id="37d30-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="37d30-128">La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37d30-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="37d30-129">Para aumentar la eficacia de la protección contra suplantación de identidad en Microsoft Defender para Office 365, puede crear directivas contra suplantación de identidad personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="37d30-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="37d30-130">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="37d30-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="37d30-131">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="37d30-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="37d30-132">Para ir directamente a la **página de protección contra suplantación** de identidad de ATP, use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="37d30-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="37d30-133">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="37d30-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="37d30-134">Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="37d30-134">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="37d30-135">Para agregar, modificar y eliminar directivas contra suplantación de  identidad, debe ser miembro de los grupos de roles Administración de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="37d30-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="37d30-136">Para obtener acceso de solo lectura a las directivas contra suplantación de identidad, debe ser miembro de los grupos de roles Lector **global** o **Lector de** <sup>\*</sup> seguridad.</span><span class="sxs-lookup"><span data-stu-id="37d30-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="37d30-137">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="37d30-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="37d30-138">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="37d30-138">**Notes**:</span></span>

  - <span data-ttu-id="37d30-139">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37d30-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="37d30-140">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="37d30-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="37d30-141">El **grupo de roles Administración de** la organización de solo vista en Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la <sup>\*</sup> característica.</span><span class="sxs-lookup"><span data-stu-id="37d30-141">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="37d30-142"><sup>\*</sup> En el Centro de & cumplimiento, el acceso de solo lectura permite a los usuarios ver la configuración de las directivas contra suplantación de identidad personalizadas.</span><span class="sxs-lookup"><span data-stu-id="37d30-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="37d30-143">Los usuarios de solo lectura no pueden ver la configuración de la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37d30-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="37d30-144">Para obtener la configuración recomendada para las directivas contra suplantación de identidad en Microsoft Defender para Office 365, vea la directiva contra suplantación de identidad en la configuración de Defender para [Office 365.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="37d30-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="37d30-145">Espere hasta 30 minutos para que se aplique una directiva nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="37d30-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="37d30-146">Para obtener información sobre dónde se aplican las directivas contra la suplantación de identidad en la canalización de filtrado, vea Orden y [prioridad de la protección de correo electrónico.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="37d30-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="37d30-147">Usar el Centro de & cumplimiento para crear directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="37d30-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="37d30-148">La creación de una directiva contra suplantación de identidad personalizada en el Centro de seguridad y cumplimiento de & crea la regla contra suplantación de identidad y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="37d30-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="37d30-149">Al crear una directiva contra suplantación de identidad, solo puede especificar el nombre de la directiva, la descripción y el filtro de destinatarios que identifica a quién se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="37d30-150">Después de crear la directiva, puede modificarla para cambiar o revisar la configuración contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37d30-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="37d30-151">En el Centro de & cumplimiento, vaya a Directiva **de administración** de amenazas contra \>  \> **la suplantación de identidad de ATP.**</span><span class="sxs-lookup"><span data-stu-id="37d30-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="37d30-152">En la **página Contra la suplantación** de identidad, haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="37d30-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="37d30-153">Se abrirá el Asistente para crear una **nueva directiva contra suplantación** de identidad.</span><span class="sxs-lookup"><span data-stu-id="37d30-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="37d30-154">En la **página Nombre de la directiva,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="37d30-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="37d30-155">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="37d30-156">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="37d30-157">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="37d30-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="37d30-158">En la **página Aplicada a** que aparece, identifique los destinatarios internos a los que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="37d30-159">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="37d30-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="37d30-160">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="37d30-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="37d30-161">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="37d30-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="37d30-162">Haga **clic en Agregar una condición.**</span><span class="sxs-lookup"><span data-stu-id="37d30-162">Click **Add a condition**.</span></span> <span data-ttu-id="37d30-163">En la lista desplegable que aparece, seleccione una condición en **Aplicada si:**</span><span class="sxs-lookup"><span data-stu-id="37d30-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="37d30-164">**El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="37d30-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="37d30-165">**El destinatario es miembro de**: Especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="37d30-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="37d30-166">**El dominio del destinatario es:** especifica los destinatarios de uno o varios de los dominios aceptados configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="37d30-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="37d30-167">Después de seleccionar la condición, aparece una lista desplegable correspondiente con **uno de estos** cuadros.</span><span class="sxs-lookup"><span data-stu-id="37d30-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="37d30-168">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="37d30-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="37d30-169">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="37d30-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="37d30-170">Para agregar valores adicionales, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="37d30-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="37d30-171">Para quitar entradas individuales, haga clic **en el** ![ icono Quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="37d30-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="37d30-172">Para quitar toda la condición, haga clic **en el** icono Quitar de ![ la ](../../media/scc-remove-icon.png) condición.</span><span class="sxs-lookup"><span data-stu-id="37d30-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="37d30-173">Para agregar una condición adicional, haga clic **en Agregar una condición** y seleccione un valor restante en Aplicado **si**.</span><span class="sxs-lookup"><span data-stu-id="37d30-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="37d30-174">Para agregar excepciones, haga clic **en Agregar una condición** y seleccione una excepción en Excepto **si**.</span><span class="sxs-lookup"><span data-stu-id="37d30-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="37d30-175">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="37d30-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="37d30-176">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="37d30-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="37d30-177">En la **página Revisar la configuración** que aparece, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="37d30-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="37d30-178">Puedes hacer clic **en Editar** en cada opción para modificarla.</span><span class="sxs-lookup"><span data-stu-id="37d30-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="37d30-179">Cuando haya terminado, haga clic **en Crear esta directiva.**</span><span class="sxs-lookup"><span data-stu-id="37d30-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="37d30-180">Haga **clic en Aceptar** en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="37d30-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="37d30-181">Después de crear la directiva contra la suplantación de identidad con esta configuración general, siga las instrucciones de la sección siguiente para configurar las opciones de protección en la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="37d30-182">Usar el Centro de seguridad & cumplimiento para modificar directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="37d30-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="37d30-183">Use los siguientes procedimientos para modificar directivas contra la suplantación de identidad: una nueva directiva creada o directivas existentes que ya ha personalizado.</span><span class="sxs-lookup"><span data-stu-id="37d30-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="37d30-184">Si aún no está, abra el Centro de seguridad &  cumplimiento y vaya a Directiva de administración de amenazas contra la suplantación de identidad \>  \> **de ATP.**</span><span class="sxs-lookup"><span data-stu-id="37d30-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="37d30-185">Seleccione la directiva contra suplantación de identidad personalizada que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="37d30-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="37d30-186">Si ya está seleccionada, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="37d30-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="37d30-187">Aparece **el \<name\> control desplegable Editar** la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="37d30-188">Al **hacer clic** en Editar en cualquier sección se proporciona acceso a la configuración de esa sección.</span><span class="sxs-lookup"><span data-stu-id="37d30-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="37d30-189">Los siguientes pasos se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="37d30-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="37d30-190">Después de  hacer clic en Editar en una sección, la configuración disponible se presenta en un formato de asistente,  pero  puede saltar dentro de las páginas en cualquier orden y puede hacer clic en Guardar en cualquier página (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** en el icono Cancelar o cerrar cerrar para volver a la página Editar la directiva (no es necesario que visite la última página del asistente para guardar o salir).</span><span class="sxs-lookup"><span data-stu-id="37d30-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="37d30-191">**Configuración de directiva:** haga **clic en Editar** para modificar la misma configuración que estaba disponible cuando [creó](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) la directiva en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="37d30-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="37d30-192">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="37d30-192">**Name**</span></span>
   - <span data-ttu-id="37d30-193">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="37d30-193">**Description**</span></span>
   - <span data-ttu-id="37d30-194">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="37d30-194">**Applied to**</span></span>
   - <span data-ttu-id="37d30-195">**Revisar la configuración**</span><span class="sxs-lookup"><span data-stu-id="37d30-195">**Review your settings**</span></span>

   <span data-ttu-id="37d30-196">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="37d30-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="37d30-197">**Suplantación:** haga clic **en Editar** para modificar los remitentes protegidos y los dominios protegidos en la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="37d30-198">Esta configuración es una condición para la directiva que identifica a los remitentes suplantados para buscar (individualmente o por dominio) en la dirección De de los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="37d30-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="37d30-199">Para obtener más información, vea la configuración de suplantación en las directivas contra suplantación de identidad en [Microsoft Defender para Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="37d30-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="37d30-200">**Agregar usuarios para proteger**: El valor predeterminado es **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="37d30-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="37d30-201">Para activarlo, deslice el botón de alternancia a **Activar** y, a continuación, haga clic en el botón Agregar **usuario** que aparece.</span><span class="sxs-lookup"><span data-stu-id="37d30-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="37d30-202">En el **control desplegable Agregar** usuario que aparece, configure los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="37d30-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="37d30-203">**Dirección de correo electrónico:**</span><span class="sxs-lookup"><span data-stu-id="37d30-203">**Email address**:</span></span>

       - <span data-ttu-id="37d30-204">Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="37d30-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="37d30-205">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.</span><span class="sxs-lookup"><span data-stu-id="37d30-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="37d30-206">Para quitar una entrada, haga clic **en el** icono Quitar ![ del ](../../media/scc-remove-icon.png) usuario.</span><span class="sxs-lookup"><span data-stu-id="37d30-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="37d30-207">**Nombre:** este valor se rellena en función de la dirección de correo electrónico seleccionada, pero puede cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="37d30-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="37d30-208">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="37d30-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="37d30-209">Para editar una entrada existente, seleccione el usuario protegido en la lista.</span><span class="sxs-lookup"><span data-stu-id="37d30-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="37d30-210">En cada directiva contra la suplantación de identidad, puede especificar un máximo de 60 usuarios protegidos (direcciones de correo electrónico del remitente).</span><span class="sxs-lookup"><span data-stu-id="37d30-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="37d30-211">No puede especificar el mismo usuario protegido en varias directivas.</span><span class="sxs-lookup"><span data-stu-id="37d30-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="37d30-212">La protección de suplantación de usuario no funciona si el remitente y el destinatario se han comunicado previamente por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="37d30-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="37d30-213">Si el remitente y el destinatario nunca se han comunicado por correo electrónico, el mensaje se identificará como un intento de suplantación.</span><span class="sxs-lookup"><span data-stu-id="37d30-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="37d30-214">**Agregar dominios para proteger:** configure una o ambas de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="37d30-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="37d30-215">**Incluya automáticamente los dominios que tengo:** el valor predeterminado es **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="37d30-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="37d30-216">Para activarlo, deslice el botón de alternancia a **On**.</span><span class="sxs-lookup"><span data-stu-id="37d30-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="37d30-217">**Incluir dominios personalizados:** el valor predeterminado es **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="37d30-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="37d30-218">Para activarlo, deslice el botón de  alternancia en Activar y, en el cuadro Agregar dominios, escriba el nombre de dominio (por ejemplo, contoso.com), presione ENTRAR y repita el proceso según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="37d30-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="37d30-219">Puede tener un máximo de 50 dominios en todas las directivas contra la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="37d30-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="37d30-220">**Acciones:** Haga clic en **Editar**</span><span class="sxs-lookup"><span data-stu-id="37d30-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="37d30-221">**Si** un usuario suplantado envía un correo electrónico: configure una de las siguientes acciones para los mensajes en los que el remitente suplantado sea uno de los usuarios protegidos que especificó en Agregar usuarios para **proteger:**</span><span class="sxs-lookup"><span data-stu-id="37d30-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="37d30-222">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="37d30-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="37d30-223">**Redirigir el mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="37d30-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="37d30-224">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="37d30-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="37d30-225">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="37d30-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="37d30-226">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="37d30-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="37d30-227">**Eliminar el mensaje antes de entregarlo**</span><span class="sxs-lookup"><span data-stu-id="37d30-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="37d30-228">**Si** un dominio suplantado envía correo electrónico: configure una de las siguientes acciones para los mensajes en los que el remitente suplantado se encuentra en uno de los dominios protegidos que especificó en Agregar dominios para **proteger:**</span><span class="sxs-lookup"><span data-stu-id="37d30-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="37d30-229">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="37d30-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="37d30-230">**Redirigir el mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="37d30-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="37d30-231">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="37d30-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="37d30-232">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="37d30-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="37d30-233">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="37d30-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="37d30-234">**Eliminar el mensaje antes de entregarlo**</span><span class="sxs-lookup"><span data-stu-id="37d30-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="37d30-235">Haz **clic en activar las sugerencias de seguridad de suplantación** y configura cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="37d30-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="37d30-236">**Mostrar sugerencia para usuarios suplantados:** El valor predeterminado es **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="37d30-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="37d30-237">Para activarlo, deslice el botón de alternancia a **On**.</span><span class="sxs-lookup"><span data-stu-id="37d30-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="37d30-238">**Mostrar sugerencia para dominios suplantados**: El valor predeterminado es **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="37d30-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="37d30-239">Para activarlo, deslice el botón de alternancia a **On**.</span><span class="sxs-lookup"><span data-stu-id="37d30-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="37d30-240">**Mostrar sugerencia para caracteres inusuales:** El valor predeterminado es **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="37d30-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="37d30-241">Para activarlo, deslice el botón de alternancia a **On**.</span><span class="sxs-lookup"><span data-stu-id="37d30-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="37d30-242">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="37d30-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="37d30-243">**Inteligencia de buzones** de correo:</span><span class="sxs-lookup"><span data-stu-id="37d30-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="37d30-244">**¿Habilitar la inteligencia de buzones?**: El valor predeterminado es **On**.</span><span class="sxs-lookup"><span data-stu-id="37d30-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="37d30-245">Para desactivarlo, deslice el botón de alternancia a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="37d30-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="37d30-246">**Habilitar la protección de suplantación** basada en inteligencia de buzones: ¿esta configuración solo está disponible si habilitar la inteligencia de buzones? está **activa.** </span><span class="sxs-lookup"><span data-stu-id="37d30-246">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="37d30-247">In **If email is sent by an suersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span><span class="sxs-lookup"><span data-stu-id="37d30-247">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="37d30-248">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="37d30-248">**Don't apply any action**</span></span>
       - <span data-ttu-id="37d30-249">**Redirigir el mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="37d30-249">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="37d30-250">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="37d30-250">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="37d30-251">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="37d30-251">**Quarantine the message**</span></span>
       - <span data-ttu-id="37d30-252">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="37d30-252">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="37d30-253">**Eliminar el mensaje antes de entregarlo**</span><span class="sxs-lookup"><span data-stu-id="37d30-253">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="37d30-254">**Agregar remitentes y dominios de confianza:** especifique excepciones para la directiva:</span><span class="sxs-lookup"><span data-stu-id="37d30-254">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="37d30-255">**Remitentes de confianza:**</span><span class="sxs-lookup"><span data-stu-id="37d30-255">**Trusted senders**:</span></span>

       - <span data-ttu-id="37d30-256">Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="37d30-256">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="37d30-257">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.</span><span class="sxs-lookup"><span data-stu-id="37d30-257">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="37d30-258">Para quitar una entrada, haga clic **en el** icono Quitar ![ del ](../../media/scc-remove-icon.png) usuario.</span><span class="sxs-lookup"><span data-stu-id="37d30-258">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="37d30-259">**Dominios de** confianza: escriba el nombre de dominio (por ejemplo, contoso.com), presione ENTRAR y repita según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="37d30-259">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="37d30-260">**Revise la configuración:** en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="37d30-260">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="37d30-261">Puede hacer clic **en Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="37d30-261">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="37d30-262">Puedes activar o desactivar la **siguiente** configuración **directamente** en esta página:</span><span class="sxs-lookup"><span data-stu-id="37d30-262">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="37d30-263">**Usuarios protegidos**</span><span class="sxs-lookup"><span data-stu-id="37d30-263">**Protected users**</span></span>
       - <span data-ttu-id="37d30-264">**Dominios protegidos** \> **Incluir dominios de mi propiedad**</span><span class="sxs-lookup"><span data-stu-id="37d30-264">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="37d30-265">**Dominios protegidos** \> **Dominios protegidos** (dominios personalizados)</span><span class="sxs-lookup"><span data-stu-id="37d30-265">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="37d30-266">**Inteligencia de buzones**</span><span class="sxs-lookup"><span data-stu-id="37d30-266">**Mailbox intelligence**</span></span>

   <span data-ttu-id="37d30-267">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="37d30-267">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="37d30-268">**Suplantación** de  identidad: haga clic en Editar para activar o desactivar la inteligencia de suplantación de identidad, activar o desactivar la identificación de remitentes no autenticados en Outlook y configurar la acción que se aplicará a los mensajes de remitentes suplantados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="37d30-268">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="37d30-269">Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="37d30-269">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="37d30-270">Tenga en cuenta que esta misma configuración también está disponible en las directivas contra suplantación de identidad en EOP.</span><span class="sxs-lookup"><span data-stu-id="37d30-270">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="37d30-271">**Configuración del filtro de suplantación:** el valor predeterminado es **On** y le recomendamos que lo deje en.</span><span class="sxs-lookup"><span data-stu-id="37d30-271">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="37d30-272">Para desactivarlo, deslice el botón de alternancia a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="37d30-272">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="37d30-273">Para obtener más información, vea [Configurar la inteligencia de suplantación de seguridad en EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="37d30-273">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="37d30-274">No es necesario deshabilitar la protección contra la suplantación si el registro MX no apunta a Microsoft 365; En su lugar, habilite el filtrado mejorado para conectores.</span><span class="sxs-lookup"><span data-stu-id="37d30-274">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="37d30-275">Para obtener instrucciones, consulte [Filtrado mejorado para conectores en Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="37d30-275">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="37d30-276">**Habilitar la característica Remitente no autenticado:** el valor predeterminado es **On**.</span><span class="sxs-lookup"><span data-stu-id="37d30-276">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="37d30-277">Para desactivarlo, deslice el botón de alternancia a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="37d30-277">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="37d30-278">**Acciones:** especifique la acción que se llevará a cabo en los mensajes que no son de inteligencia de suplantación de seguridad:</span><span class="sxs-lookup"><span data-stu-id="37d30-278">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="37d30-279">Si alguien que no tiene permiso para **suplantación** de su dominio envía un correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="37d30-279">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="37d30-280">**Mover el mensaje a las carpetas de correo no deseado de los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="37d30-280">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="37d30-281">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="37d30-281">**Quarantine the message**</span></span>

   - <span data-ttu-id="37d30-282">**Revise la configuración:** en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="37d30-282">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="37d30-283">Puede hacer clic **en Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="37d30-283">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="37d30-284">Puedes activar o desactivar la **siguiente** configuración **directamente** en esta página:</span><span class="sxs-lookup"><span data-stu-id="37d30-284">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="37d30-285">**Habilitar la protección contra la suplantación**</span><span class="sxs-lookup"><span data-stu-id="37d30-285">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="37d30-286">**Habilitar la característica Remitente no autenticado**</span><span class="sxs-lookup"><span data-stu-id="37d30-286">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="37d30-287">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="37d30-287">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="37d30-288">**Configuración avanzada:** haga **clic en Editar** para configurar los umbrales de suplantación de identidad avanzados.</span><span class="sxs-lookup"><span data-stu-id="37d30-288">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="37d30-289">Para obtener más información, vea Umbrales avanzados de suplantación de identidad en las directivas contra suplantación de identidad en [Microsoft Defender para Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="37d30-289">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="37d30-290">**Umbrales de suplantación de identidad avanzados:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="37d30-290">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="37d30-291">**1- Estándar** (este es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="37d30-291">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="37d30-292">**2: agresivo**</span><span class="sxs-lookup"><span data-stu-id="37d30-292">**2 - Aggressive**</span></span>
   - <span data-ttu-id="37d30-293">**3- Más agresivo**</span><span class="sxs-lookup"><span data-stu-id="37d30-293">**3 - More aggressive**</span></span>
   - <span data-ttu-id="37d30-294">**4- Más agresivo**</span><span class="sxs-lookup"><span data-stu-id="37d30-294">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="37d30-295">**Revisa la configuración:** haz clic **en Editar** para volver a la **página umbrales de suplantación de** identidad avanzada.</span><span class="sxs-lookup"><span data-stu-id="37d30-295">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="37d30-296">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="37d30-296">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="37d30-297">De nuevo en la **página Editar la \<Name\> directiva,** revise la configuración y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="37d30-297">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="37d30-298">Usar el Centro de & cumplimiento para modificar la directiva contra suplantación de identidad predeterminada en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="37d30-298">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="37d30-299">La directiva contra suplantación de identidad predeterminada en Microsoft Defender para Office 365 se denomina Office365 AntiPhish Default y no aparece en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="37d30-299">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="37d30-300">Para modificar la directiva contra suplantación de identidad predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="37d30-300">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="37d30-301">En el Centro de & cumplimiento, vaya a Directiva **de administración** de amenazas contra \>  \> **la suplantación de identidad de ATP.**</span><span class="sxs-lookup"><span data-stu-id="37d30-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="37d30-302">En la **página Contra la suplantación** de identidad, haga clic **en Directiva predeterminada.**</span><span class="sxs-lookup"><span data-stu-id="37d30-302">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="37d30-303">Aparece la página Editar la directiva predeterminada contra el **antiphish de Office 365.**</span><span class="sxs-lookup"><span data-stu-id="37d30-303">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="37d30-304">Están disponibles las secciones siguientes, que contienen configuraciones idénticas para cuando [se modifica una directiva personalizada:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="37d30-304">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="37d30-305">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="37d30-305">**Impersonation**</span></span>
   - <span data-ttu-id="37d30-306">**Suplantación de seguridad**</span><span class="sxs-lookup"><span data-stu-id="37d30-306">**Spoof**</span></span>
   - <span data-ttu-id="37d30-307">**Configuración avanzada**</span><span class="sxs-lookup"><span data-stu-id="37d30-307">**Advanced settings**</span></span>

   <span data-ttu-id="37d30-308">La siguiente configuración no está disponible al modificar la directiva predeterminada:</span><span class="sxs-lookup"><span data-stu-id="37d30-308">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="37d30-309">Puede ver  la sección y los valores de configuración de directiva, pero **no** hay ningún vínculo Editar, por lo que no puede modificar la configuración (nombre de directiva, descripción y a quién se aplica la directiva (se aplica a todos los destinatarios)).</span><span class="sxs-lookup"><span data-stu-id="37d30-309">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="37d30-310">No puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37d30-310">You can't delete the default policy.</span></span>
   - <span data-ttu-id="37d30-311">No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="37d30-311">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="37d30-312">En la **página Editar directiva de Office365 Antiphish Default,** revise la configuración y, a continuación, haga clic en **Cerrar.**</span><span class="sxs-lookup"><span data-stu-id="37d30-312">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="37d30-313">Habilitar o deshabilitar directivas contra suplantación de identidad personalizadas en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="37d30-313">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="37d30-314">En el Centro de & cumplimiento, vaya a Directiva **de administración** de amenazas contra \>  \> **la suplantación de identidad de ATP.**</span><span class="sxs-lookup"><span data-stu-id="37d30-314">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="37d30-315">Observe el valor de la columna **Estado:**</span><span class="sxs-lookup"><span data-stu-id="37d30-315">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="37d30-316">Desliza el botón de **alternancia a Desactivado** para deshabilitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-316">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="37d30-317">Desliza el botón de **alternancia a Activar** para habilitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-317">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="37d30-318">No puede deshabilitar la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37d30-318">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="37d30-319">Establecer la prioridad de las directivas contra suplantación de identidad personalizadas en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="37d30-319">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="37d30-320">De forma predeterminada, las directivas contra suplantación de identidad tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="37d30-320">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="37d30-321">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="37d30-321">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="37d30-322">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-322">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="37d30-323">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="37d30-323">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="37d30-324">Las directivas contra suplantación de identidad personalizadas se muestran en el orden en que se procesan (la primera directiva tiene el **valor de prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="37d30-324">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="37d30-325">La directiva contra suplantación de identidad predeterminada denominada Office365 AntiPhish Default tiene el valor de prioridad personalizado **Lowest** y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="37d30-325">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="37d30-326">**Nota:** En el Centro de & cumplimiento, solo puede cambiar la prioridad de la directiva contra suplantación de identidad después de crearla.</span><span class="sxs-lookup"><span data-stu-id="37d30-326">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="37d30-327">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla contra suplantación de identidad (que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="37d30-327">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="37d30-328">Para cambiar la prioridad de  una directiva, haga clic en Aumentar prioridad o Disminuir  prioridad en las propiedades de la directiva (no puede modificar directamente el número de prioridad en el Centro de seguridad & cumplimiento). </span><span class="sxs-lookup"><span data-stu-id="37d30-328">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="37d30-329">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="37d30-329">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="37d30-330">En el Centro de & cumplimiento, vaya a Directiva **de administración** de amenazas contra \>  \> **la suplantación de identidad de ATP.**</span><span class="sxs-lookup"><span data-stu-id="37d30-330">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="37d30-331">Seleccione la directiva que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="37d30-331">Select the policy that you want to modify.</span></span> <span data-ttu-id="37d30-332">Si ya está seleccionada, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="37d30-332">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="37d30-333">Aparece **el \<name\> control desplegable Editar** la directiva.</span><span class="sxs-lookup"><span data-stu-id="37d30-333">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="37d30-334">La directiva contra suplantación de identidad personalizada con el valor **de prioridad** **0** solo tiene disponible el **botón** Disminuir prioridad.</span><span class="sxs-lookup"><span data-stu-id="37d30-334">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="37d30-335">La directiva contra suplantación de identidad personalizada con el valor **de prioridad** más bajo (por ejemplo, **3)** solo tiene el **botón** Aumentar prioridad disponible.</span><span class="sxs-lookup"><span data-stu-id="37d30-335">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="37d30-336">Si tiene tres o más directivas contra suplantación de identidad personalizadas, las  directivas entre los valores de prioridad más alta y baja tienen los botones Aumentar prioridad y Disminuir prioridad disponibles. </span><span class="sxs-lookup"><span data-stu-id="37d30-336">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="37d30-337">Haga **clic en Aumentar prioridad** o **Disminuir** prioridad para cambiar el valor **de Prioridad.**</span><span class="sxs-lookup"><span data-stu-id="37d30-337">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="37d30-338">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="37d30-338">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="37d30-339">Usar el Centro de & cumplimiento para ver directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="37d30-339">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="37d30-340">En el Centro de & cumplimiento y vaya a Directiva **de** administración de amenazas contra la suplantación de \>  \> **identidad de ATP.**</span><span class="sxs-lookup"><span data-stu-id="37d30-340">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="37d30-341">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="37d30-341">Do one of the following steps:</span></span>

   - <span data-ttu-id="37d30-342">Seleccione una directiva contra suplantación de identidad personalizada que desee ver.</span><span class="sxs-lookup"><span data-stu-id="37d30-342">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="37d30-343">Si ya está seleccionada, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="37d30-343">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="37d30-344">Haga **clic en Directiva predeterminada** para ver la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37d30-344">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="37d30-345">Aparece **el \<name\> control desplegable Editar** la directiva, donde puedes ver la configuración y los valores.</span><span class="sxs-lookup"><span data-stu-id="37d30-345">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="37d30-346">Usar el Centro de seguridad & cumplimiento para quitar directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="37d30-346">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="37d30-347">En el Centro de & cumplimiento, vaya a Directiva **de administración** de amenazas contra \>  \> **la suplantación de identidad de ATP.**</span><span class="sxs-lookup"><span data-stu-id="37d30-347">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="37d30-348">Seleccione la directiva que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="37d30-348">Select the policy that you want to remove.</span></span> <span data-ttu-id="37d30-349">Si ya está seleccionada, anule la selección y selecciónelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="37d30-349">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="37d30-350">En el **control \<name\> desplegable Editar** la directiva que aparece, haga clic en Eliminar directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="37d30-350">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="37d30-351">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37d30-351">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="37d30-352">Usar Exchange Online PowerShell para configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="37d30-352">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="37d30-353">Como se describió anteriormente, una directiva contra correo no deseado consta de una directiva contra suplantación de identidad y una regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="37d30-353">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="37d30-354">En Exchange Online PowerShell, la diferencia entre las directivas contra suplantación de identidad y las reglas contra suplantación de identidad es aparente.</span><span class="sxs-lookup"><span data-stu-id="37d30-354">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="37d30-355">Las directivas contra suplantación de identidad se administran con los cmdlets **\* -AntiPhishPolicy** y se administran mediante los cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="37d30-355">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="37d30-356">En PowerShell, primero se crea la directiva contra suplantación de identidad y, a continuación, se crea la regla contra suplantación de identidad que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="37d30-356">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="37d30-357">En PowerShell, puede modificar la configuración de la directiva contra suplantación de identidad y la regla contra suplantación de identidad por separado.</span><span class="sxs-lookup"><span data-stu-id="37d30-357">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="37d30-358">Al quitar una directiva contra suplantación de identidad de PowerShell, la regla contra suplantación de identidad correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="37d30-358">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="37d30-359">Usar PowerShell para crear directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-359">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="37d30-360">Crear una directiva contra suplantación de identidad en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="37d30-360">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="37d30-361">Cree la directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="37d30-361">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="37d30-362">Cree la regla contra suplantación de identidad que especifica la directiva contra suplantación de identidad a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="37d30-362">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="37d30-363">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="37d30-363">**Notes**:</span></span>

- <span data-ttu-id="37d30-364">Puede crear una nueva regla contra suplantación de identidad y asignarle una directiva anti-phish existente y sin asociar.</span><span class="sxs-lookup"><span data-stu-id="37d30-364">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="37d30-365">Una regla contra suplantación de identidad no se puede asociar a más de una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="37d30-365">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="37d30-366">Puede configurar las siguientes opciones en las nuevas directivas contra suplantación de identidad en PowerShell que no estén disponibles en el Centro de seguridad & Cumplimiento hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="37d30-366">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="37d30-367">Cree la nueva directiva como deshabilitada _(habilitada en_ `$false` el cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="37d30-367">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="37d30-368">Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="37d30-368">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="37d30-369">Una nueva directiva contra suplantación de identidad que cree en PowerShell no será visible en el Centro de seguridad & Cumplimiento hasta que asigne la directiva a una regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="37d30-369">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="37d30-370">Paso 1: Usar PowerShell para crear una directiva contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-370">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="37d30-371">Para crear una directiva contra suplantación de identidad, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="37d30-371">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="37d30-372">En este ejemplo se crea una directiva contra suplantación de identidad denominada Research Quarantine con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="37d30-372">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="37d30-373">La directiva está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="37d30-373">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="37d30-374">La descripción es: Directiva del departamento de investigación.</span><span class="sxs-lookup"><span data-stu-id="37d30-374">The description is: Research department policy.</span></span>
- <span data-ttu-id="37d30-375">Habilita la protección de dominios de la organización para todos los dominios aceptados y la protección de dominios de destino para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="37d30-375">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="37d30-376">Especifica Mai Fujito (mfujito@fabrikam.com) como el usuario para protegerse de la suplantación.</span><span class="sxs-lookup"><span data-stu-id="37d30-376">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="37d30-377">Habilita la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="37d30-377">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="37d30-378">Habilita la protección de inteligencia de buzones de correo y especifica la acción de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="37d30-378">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="37d30-379">Permite sugerencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="37d30-379">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="37d30-380">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="37d30-380">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="37d30-381">Paso 2: Usar PowerShell para crear una regla contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-381">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="37d30-382">Para crear una regla contra suplantación de identidad, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="37d30-382">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="37d30-383">En este ejemplo se crea una regla contra suplantación de identidad denominada Research Department con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="37d30-383">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="37d30-384">La regla está asociada a la directiva contra suplantación de identidad denominada Cuarentena de investigación.</span><span class="sxs-lookup"><span data-stu-id="37d30-384">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="37d30-385">La regla se aplica a los miembros del grupo denominado Research Department.</span><span class="sxs-lookup"><span data-stu-id="37d30-385">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="37d30-386">Como no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37d30-386">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="37d30-387">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="37d30-387">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="37d30-388">Usar PowerShell para ver directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-388">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="37d30-389">Para ver las directivas contra suplantación de identidad existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="37d30-389">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="37d30-390">En este ejemplo se devuelve una lista resumida de todas las directivas contra suplantación de identidad junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="37d30-390">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="37d30-391">En este ejemplo se devuelven todos los valores de propiedad de la directiva contra suplantación de identidad denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="37d30-391">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="37d30-392">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="37d30-392">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="37d30-393">Usar PowerShell para ver reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-393">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="37d30-394">Para ver las reglas contra suplantación de identidad existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="37d30-394">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="37d30-395">En este ejemplo se devuelve una lista resumida de todas las reglas contra suplantación de identidad junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="37d30-395">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="37d30-396">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="37d30-396">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="37d30-397">En este ejemplo se devuelven todos los valores de propiedad de la regla contra suplantación de identidad denominada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="37d30-397">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="37d30-398">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="37d30-398">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="37d30-399">Usar PowerShell para modificar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-399">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="37d30-400">Aparte de los siguientes elementos, la misma configuración está disponible cuando se modifica una directiva contra suplantación de identidad en PowerShell que cuando se crea la directiva como se describe en el paso [1: Usar PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) para crear una sección de directiva contra suplantación de identidad anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="37d30-400">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="37d30-401">El modificador _MakeDefault_ que convierte la directiva especificada en la  directiva predeterminada (se aplica a todos, siempre con la prioridad más baja y no se puede eliminar) solo está disponible cuando se modifica una directiva contra suplantación de identidad en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37d30-401">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="37d30-402">No puede cambiar el nombre de una directiva contra suplantación de identidad (el cmdlet **Set-AntiPhishPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="37d30-402">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="37d30-403">Cuando cambia el nombre de una directiva contra suplantación de identidad en el Centro de seguridad & Cumplimiento, solo cambia el nombre de la regla contra _suplantación de identidad_.</span><span class="sxs-lookup"><span data-stu-id="37d30-403">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="37d30-404">Para modificar una directiva contra suplantación de identidad, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="37d30-404">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="37d30-405">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="37d30-405">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="37d30-406">Usar PowerShell para modificar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-406">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="37d30-407">La única configuración que no está disponible al modificar una regla contra suplantación de identidad en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="37d30-407">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="37d30-408">Para habilitar o deshabilitar reglas contra suplantación de identidad existentes, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="37d30-408">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="37d30-409">De lo contrario, no hay opciones de configuración adicionales disponibles al modificar una regla contra suplantación de identidad en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37d30-409">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="37d30-410">La misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) para crear una sección de regla contra suplantación de identidad anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="37d30-410">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="37d30-411">Para modificar una regla contra suplantación de identidad, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="37d30-411">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="37d30-412">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="37d30-412">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="37d30-413">Usar PowerShell para habilitar o deshabilitar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-413">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="37d30-414">Habilitar o deshabilitar una regla contra suplantación de identidad en PowerShell habilita o deshabilita toda la directiva contra suplantación de identidad (la regla contra suplantación de identidad y la directiva contra suplantación de identidad asignada).</span><span class="sxs-lookup"><span data-stu-id="37d30-414">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="37d30-415">No puede habilitar ni deshabilitar la directiva contra suplantación de identidad predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="37d30-415">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="37d30-416">Para habilitar o deshabilitar una regla contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="37d30-416">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="37d30-417">En este ejemplo se deshabilita la regla contra suplantación de identidad denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="37d30-417">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="37d30-418">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="37d30-418">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="37d30-419">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) y [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="37d30-419">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="37d30-420">Usar PowerShell para establecer la prioridad de las reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-420">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="37d30-421">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="37d30-421">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="37d30-422">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="37d30-422">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="37d30-423">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="37d30-423">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="37d30-424">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="37d30-424">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="37d30-425">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="37d30-425">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="37d30-426">Para establecer la prioridad de una regla contra suplantación de identidad en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="37d30-426">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="37d30-427">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="37d30-427">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="37d30-428">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="37d30-428">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="37d30-429">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="37d30-429">**Notes**:</span></span>

- <span data-ttu-id="37d30-430">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="37d30-430">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="37d30-431">La directiva contra suplantación de identidad predeterminada no tiene una regla contra suplantación de identidad correspondiente y siempre tiene el valor de prioridad no modificable **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="37d30-431">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="37d30-432">Usar PowerShell para quitar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-432">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="37d30-433">Al usar PowerShell para quitar una directiva contra suplantación de identidad, no se quita la regla antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="37d30-433">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="37d30-434">Para quitar una directiva contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="37d30-434">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="37d30-435">En este ejemplo se quita la directiva contra suplantación de identidad denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="37d30-435">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="37d30-436">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="37d30-436">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="37d30-437">Usar PowerShell para quitar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37d30-437">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="37d30-438">Cuando usa PowerShell para quitar una regla contra suplantación de identidad, no se quita la directiva contra suplantación de identidad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="37d30-438">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="37d30-439">Para quitar una regla contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="37d30-439">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="37d30-440">En este ejemplo se quita la regla contra suplantación de identidad denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="37d30-440">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="37d30-441">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="37d30-441">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="37d30-442">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="37d30-442">How do you know these procedures worked?</span></span>

<span data-ttu-id="37d30-443">Para comprobar que ha configurado correctamente directivas contra suplantación de identidad en Microsoft Defender para Office 365, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="37d30-443">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="37d30-444">En el Centro de & cumplimiento, vaya a Directiva **de administración** de amenazas contra \>  \> **la suplantación de identidad de ATP.**</span><span class="sxs-lookup"><span data-stu-id="37d30-444">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="37d30-445">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="37d30-445">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="37d30-446">Para ver más detalles, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="37d30-446">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="37d30-447">Seleccione la directiva de la lista y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="37d30-447">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="37d30-448">Haga **clic en Directiva** predeterminada y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="37d30-448">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="37d30-449">En Exchange Online PowerShell, reemplace por el nombre de la directiva o regla, ejecute \<Name\> el siguiente comando y compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="37d30-449">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
