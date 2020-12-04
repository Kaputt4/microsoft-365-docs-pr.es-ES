---
title: Configurar directivas contra la suplantación de identidad en Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a crear, modificar y eliminar las Directivas avanzadas de suplantación de identidad (phishing) que están disponibles en las organizaciones con Microsoft defender para Office 365.
ms.openlocfilehash: ae8c87a0bfb7f975328d8283f0b62aa12c1d5e2b
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572410"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="368da-103">Configurar directivas contra la suplantación de identidad en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="368da-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="368da-104">Las directivas antiphishing de [Microsoft defender para Office 365](office-365-atp.md) pueden ayudar a proteger a su organización de ataques de suplantación de identidad (phishing) malintencionados y otros tipos de ataques de suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="368da-104">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="368da-105">Para obtener más información acerca de las diferencias entre las directivas antiphishing en Exchange Online Protection (EOP) y las directivas antiphishing en Microsoft defender para Office 365, consulte [protección contra suplantación de identidad (phishing](anti-phishing-protection.md)).</span><span class="sxs-lookup"><span data-stu-id="368da-105">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="368da-106">Los administradores pueden ver, editar y configurar (pero no eliminar) la Directiva de suplantación de identidad (phishing) predeterminada.</span><span class="sxs-lookup"><span data-stu-id="368da-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="368da-107">Para una mayor granularidad, también puede crear directivas antiphishing personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="368da-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="368da-108">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="368da-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="368da-109">Puede configurar directivas contra la suplantación de identidad en el centro de seguridad & cumplimiento o en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="368da-109">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="368da-110">Para obtener información acerca de la configuración de las directivas antiphishing más limitadas que están disponibles en las organizaciones de Exchange Online Protection (es decir, organizaciones sin Microsoft defender para Office 365), vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="368da-110">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="368da-111">Los elementos básicos de una directiva contra la suplantación de identidad (phishing) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="368da-111">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="368da-112">**La Directiva ANTIPHISH**: especifica las protecciones de suplantación de identidad (phishing) que se deben habilitar o deshabilitar y las acciones para aplicar opciones.</span><span class="sxs-lookup"><span data-stu-id="368da-112">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="368da-113">**La regla anti-phish**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva) para una directiva antiphishing.</span><span class="sxs-lookup"><span data-stu-id="368da-113">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="368da-114">La diferencia entre estos dos elementos no es obvia cuando administra directivas antiphishing en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="368da-114">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="368da-115">Al crear una directiva, en realidad está creando una regla ANTIPHISH y la Directiva ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="368da-115">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="368da-116">Cuando modifica una directiva, la configuración relacionada con el nombre, la prioridad, habilitada o deshabilitada y los filtros de destinatarios modifican la regla antiphishing.</span><span class="sxs-lookup"><span data-stu-id="368da-116">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="368da-117">Todas las demás opciones modifican la Directiva ANTIPHISH asociada.</span><span class="sxs-lookup"><span data-stu-id="368da-117">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="368da-118">Al quitar una directiva, se quita la regla antiphishing y la Directiva antiphishing asociada.</span><span class="sxs-lookup"><span data-stu-id="368da-118">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="368da-119">En Exchange Online PowerShell, puede administrar la Directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="368da-119">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="368da-120">Para obtener más información, consulte la sección [usar Exchange Online PowerShell para configurar directivas antiphishing en Microsoft defender para Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) , más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="368da-120">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this topic.</span></span>

<span data-ttu-id="368da-121">Cada organización de Microsoft defender para Office 365 tiene una directiva antiphishing integrada denominada Office365 ANTIPHISH predeterminada que tiene estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="368da-121">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="368da-122">La Directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla antiphishing (filtros de destinatario) asociada a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="368da-122">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="368da-123">La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="368da-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="368da-124">Las directivas personalizadas que cree siempre tendrán una prioridad mayor.</span><span class="sxs-lookup"><span data-stu-id="368da-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="368da-125">La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="368da-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="368da-126">Para aumentar la eficacia de la protección contra la suplantación de identidad en Microsoft defender para Office 365, puede crear directivas antiphishing personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="368da-126">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="368da-127">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="368da-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="368da-128">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="368da-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="368da-129">Para ir directamente a la página **contra la suplantación de identidad ATP** , use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="368da-129">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="368da-130">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="368da-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="368da-131">Debe tener asignados permisos en el centro de seguridad & cumplimiento antes de poder llevar a cabo los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="368da-131">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="368da-132">Para agregar, modificar y eliminar directivas antiphishing, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="368da-132">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="368da-133">Para el acceso de solo lectura a las directivas antiphishing, debe ser miembro de los grupos de roles **lector global** o **lector** de seguridad <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="368da-133">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="368da-134">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="368da-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="368da-135">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="368da-135">**Notes**:</span></span>

  - <span data-ttu-id="368da-136">La adición de usuarios al rol correspondiente de Azure Active Directory en el centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el centro de seguridad & cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="368da-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="368da-137">Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="368da-137">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="368da-138">El grupo de roles administración de la **organización de solo vista** de [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="368da-138">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="368da-139"><sup>\*</sup> En el centro de seguridad & cumplimiento, el acceso de solo lectura permite a los usuarios ver la configuración de las directivas antiphishing personalizadas.</span><span class="sxs-lookup"><span data-stu-id="368da-139"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="368da-140">Solo lectura los usuarios no pueden ver la configuración de la Directiva de suplantación de identidad (phishing) predeterminada.</span><span class="sxs-lookup"><span data-stu-id="368da-140">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="368da-141">Para conocer la configuración recomendada para las directivas antiphishing en Microsoft defender para Office 365, consulte [anti-phishing Policy in defender for office 365 Settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="368da-141">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="368da-142">Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="368da-142">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="368da-143">Para obtener información acerca de dónde se aplican las directivas contra la suplantación de identidad (phishing) en la canalización de filtros, consulte [Order and Precedence of email Protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="368da-143">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="368da-144">Usar el centro de seguridad & cumplimiento para crear directivas contra la suplantación de identidad en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="368da-144">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="368da-145">La creación de una directiva antiphishing personalizada en el centro de seguridad & cumplimiento crea la regla antiphishing y la Directiva ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="368da-145">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="368da-146">Cuando se crea una directiva antiphishing, solo se puede especificar el nombre de la Directiva, la descripción y el filtro de destinatarios que identifican a quién se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="368da-146">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="368da-147">Después de crear la Directiva, puede modificar la Directiva para cambiar o revisar la configuración predeterminada de la suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="368da-147">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="368da-148">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="368da-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="368da-149">En la página **contra la suplantación de identidad** , haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="368da-149">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="368da-150">Se abrirá el Asistente para **crear una nueva Directiva antiphishing** .</span><span class="sxs-lookup"><span data-stu-id="368da-150">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="368da-151">En la página **asigne un nombre a la Directiva** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="368da-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="368da-152">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="368da-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="368da-153">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="368da-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="368da-154">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="368da-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="368da-155">En la página **aplicado a** que aparece, identifique los destinatarios internos a los que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="368da-155">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="368da-156">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="368da-156">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="368da-157">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="368da-157">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="368da-158">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="368da-158">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="368da-159">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="368da-159">Click **Add a condition**.</span></span> <span data-ttu-id="368da-160">En la lista desplegable que aparece, seleccione una condición en **aplicado si**:</span><span class="sxs-lookup"><span data-stu-id="368da-160">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="368da-161">**El destinatario es**: especifica uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="368da-161">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="368da-162">**El destinatario es un miembro de**: especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="368da-162">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="368da-163">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="368da-163">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="368da-164">Después de seleccionar la condición, aparece la lista desplegable correspondiente con una **de estas** casillas.</span><span class="sxs-lookup"><span data-stu-id="368da-164">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="368da-165">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="368da-165">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="368da-166">Haga clic en el cuadro y comience a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="368da-166">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="368da-167">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="368da-167">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="368da-168">Para quitar entradas individuales, haga **Remove** clic en ![ el icono quitar quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="368da-168">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="368da-169">Para quitar toda la condición, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en la condición.</span><span class="sxs-lookup"><span data-stu-id="368da-169">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="368da-170">Para agregar una condición adicional, haga clic en **Agregar condición** y seleccione un valor restante en **aplicado si**.</span><span class="sxs-lookup"><span data-stu-id="368da-170">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="368da-171">Para agregar excepciones, haga clic en **Agregar una condición** y seleccione una excepción en **excepto si**.</span><span class="sxs-lookup"><span data-stu-id="368da-171">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="368da-172">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="368da-172">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="368da-173">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="368da-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="368da-174">En la página **Revise la configuración** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="368da-174">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="368da-175">Puede hacer clic en **Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="368da-175">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="368da-176">Cuando haya terminado, haga clic en **crear esta directiva**.</span><span class="sxs-lookup"><span data-stu-id="368da-176">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="368da-177">Haga clic en **Aceptar** en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="368da-177">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="368da-178">Después de crear la Directiva antiphishing con esta configuración general, siga las instrucciones de la siguiente sección para establecer la configuración de protección en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="368da-178">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="368da-179">Usar el centro de seguridad & cumplimiento para modificar las directivas antiphishing en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="368da-179">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="368da-180">Use los siguientes procedimientos para modificar las directivas antiphishing: una nueva directiva que ha creado o las directivas existentes que ya ha personalizado.</span><span class="sxs-lookup"><span data-stu-id="368da-180">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="368da-181">Si aún no está ahí, abra el centro de seguridad & cumplimiento y vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="368da-181">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="368da-182">Seleccione la Directiva antiphishing personalizada que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="368da-182">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="368da-183">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="368da-183">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="368da-184">Aparece el control flotante **editar la directiva \<name\>** .</span><span class="sxs-lookup"><span data-stu-id="368da-184">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="368da-185">Al hacer clic en **Editar** en cualquier sección, obtendrá acceso a la configuración de esa sección.</span><span class="sxs-lookup"><span data-stu-id="368da-185">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="368da-186">Los pasos siguientes se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="368da-186">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="368da-187">Después de hacer clic en **Editar** en una sección, la configuración disponible se presenta en un formato de asistente, pero puede saltar dentro de las páginas en cualquier orden y puede hacer clic en **Guardar** en cualquier página (o en **Cancelar** o **cerrar** el ![ icono cerrar ](../../media/scc-remove-icon.png) para volver a la página **editar la directiva \<name\>** ) (no es necesario visitar la última página del Asistente para guardarla o dejarla).</span><span class="sxs-lookup"><span data-stu-id="368da-187">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="368da-188">**Configuración de directiva**: haga clic en **Editar** para modificar la misma configuración que estaba disponible cuando [creó la Directiva](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="368da-188">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="368da-189">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="368da-189">**Name**</span></span>
   - <span data-ttu-id="368da-190">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="368da-190">**Description**</span></span>
   - <span data-ttu-id="368da-191">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="368da-191">**Applied to**</span></span>
   - <span data-ttu-id="368da-192">**Revisar la configuración**</span><span class="sxs-lookup"><span data-stu-id="368da-192">**Review your settings**</span></span>

   <span data-ttu-id="368da-193">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="368da-193">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="368da-194">**Suplantación**: haga clic en **Editar** para modificar los remitentes protegidos y los dominios protegidos en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="368da-194">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="368da-195">Esta configuración es una condición para la Directiva que identifica a los remitentes suplantados para que busquen (de forma individual o por dominio) en la dirección de de los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="368da-195">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="368da-196">Para obtener más información, vea [configuración de suplantación en directivas antiphishing en Microsoft defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="368da-196">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="368da-197">**Agregar usuarios para proteger**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="368da-197">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="368da-198">Para activarla, deslice el botón de alternancia a **activado** y, a continuación, haga clic en el botón **Agregar usuario** que aparece.</span><span class="sxs-lookup"><span data-stu-id="368da-198">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="368da-199">En el control flotante **Agregar usuario** que aparece, configure los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="368da-199">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="368da-200">**Dirección de correo electrónico**:</span><span class="sxs-lookup"><span data-stu-id="368da-200">**Email address**:</span></span>

       - <span data-ttu-id="368da-201">Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="368da-201">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="368da-202">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.</span><span class="sxs-lookup"><span data-stu-id="368da-202">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="368da-203">Para quitar una entrada, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en el usuario.</span><span class="sxs-lookup"><span data-stu-id="368da-203">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="368da-204">**Nombre**: este valor se rellena en función de la dirección de correo electrónico que haya seleccionado, pero puede cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="368da-204">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="368da-205">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="368da-205">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="368da-206">Para editar una entrada existente, seleccione el usuario protegido en la lista.</span><span class="sxs-lookup"><span data-stu-id="368da-206">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="368da-207">En cada Directiva contra la suplantación de identidad (phishing), puede especificar un máximo de 60 usuarios protegidos (direcciones de correo electrónico del remitente).</span><span class="sxs-lookup"><span data-stu-id="368da-207">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="368da-208">No puede especificar el mismo usuario protegido en varias directivas.</span><span class="sxs-lookup"><span data-stu-id="368da-208">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="368da-209">La protección de suplantación del usuario no funciona si el remitente y el destinatario se comunicaron previamente mediante correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="368da-209">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="368da-210">Si el remitente y el destinatario nunca se han comunicado a través del correo electrónico, el mensaje se identificará como un intento de suplantación.</span><span class="sxs-lookup"><span data-stu-id="368da-210">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="368da-211">**Agregar dominios para proteger**: configure una o ambas de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="368da-211">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="368da-212">**Incluir automáticamente los dominios que tengo**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="368da-212">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="368da-213">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="368da-213">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="368da-214">**Incluir dominios personalizados**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="368da-214">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="368da-215">Para activarla, deslice el botón de alternancia a **activado** y, en el cuadro **Agregar dominios** , escriba el nombre de dominio (por ejemplo, contoso.com), presione entrar y repita lo mismo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="368da-215">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="368da-216">Puede tener un máximo de 50 dominios en todas las directivas contra la suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="368da-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="368da-217">**Acciones**: haga clic en **Editar**</span><span class="sxs-lookup"><span data-stu-id="368da-217">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="368da-218">**Si un usuario suplantado envía un correo electrónico**: configure una de las siguientes acciones para los mensajes en los que el remitente falso sea uno de los usuarios protegidos que ha especificado en **Agregar usuarios para proteger**:</span><span class="sxs-lookup"><span data-stu-id="368da-218">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="368da-219">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="368da-219">**Don't apply any action**</span></span>
       - <span data-ttu-id="368da-220">**Redirigir un mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="368da-220">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="368da-221">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="368da-221">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="368da-222">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="368da-222">**Quarantine the message**</span></span>
       - <span data-ttu-id="368da-223">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="368da-223">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="368da-224">**Eliminar el mensaje antes de su entrega**</span><span class="sxs-lookup"><span data-stu-id="368da-224">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="368da-225">**Si un dominio suplantado envía un correo electrónico**: configure una de las siguientes acciones para los mensajes en los que el remitente falso esté en uno de los dominios protegidos que ha especificado en **Agregar dominios para proteger**:</span><span class="sxs-lookup"><span data-stu-id="368da-225">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="368da-226">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="368da-226">**Don't apply any action**</span></span>
       - <span data-ttu-id="368da-227">**Redirigir un mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="368da-227">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="368da-228">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="368da-228">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="368da-229">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="368da-229">**Quarantine the message**</span></span>
       - <span data-ttu-id="368da-230">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="368da-230">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="368da-231">**Eliminar el mensaje antes de su entrega**</span><span class="sxs-lookup"><span data-stu-id="368da-231">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="368da-232">Haga clic en **Activar sugerencias de seguridad de suplantación** y configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="368da-232">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="368da-233">**Mostrar sugerencia para usuarios suplantados**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="368da-233">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="368da-234">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="368da-234">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="368da-235">**Mostrar sugerencia para dominios suplantados**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="368da-235">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="368da-236">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="368da-236">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="368da-237">**Mostrar sugerencia para caracteres inusuales**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="368da-237">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="368da-238">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="368da-238">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="368da-239">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="368da-239">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="368da-240">**Inteligencia de buzones de correo**:</span><span class="sxs-lookup"><span data-stu-id="368da-240">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="368da-241">**¿Habilitar la inteligencia de buzones?**: el valor predeterminado es **activado**.</span><span class="sxs-lookup"><span data-stu-id="368da-241">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="368da-242">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="368da-242">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="368da-243">**¿Habilitar la protección de suplantación basada en buzones de correo?**: esta opción solo está disponible si **Habilitar inteligencia de buzones de correo?** es **activado**.</span><span class="sxs-lookup"><span data-stu-id="368da-243">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="368da-244">En **si un usuario suplantado envía un correo electrónico**, puede especificar una de las siguientes acciones para que se realicen en los mensajes que no superen la inteligencia del buzón (las mismas acciones que están disponibles para los usuarios protegidos y los dominios protegidos):</span><span class="sxs-lookup"><span data-stu-id="368da-244">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="368da-245">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="368da-245">**Don't apply any action**</span></span>
       - <span data-ttu-id="368da-246">**Redirigir un mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="368da-246">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="368da-247">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="368da-247">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="368da-248">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="368da-248">**Quarantine the message**</span></span>
       - <span data-ttu-id="368da-249">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="368da-249">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="368da-250">**Eliminar el mensaje antes de su entrega**</span><span class="sxs-lookup"><span data-stu-id="368da-250">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="368da-251">**Agregue los remitentes y dominios de confianza**: especifique las excepciones de la Directiva:</span><span class="sxs-lookup"><span data-stu-id="368da-251">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="368da-252">**Remitentes de confianza**:</span><span class="sxs-lookup"><span data-stu-id="368da-252">**Trusted senders**:</span></span>

       - <span data-ttu-id="368da-253">Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="368da-253">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="368da-254">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.</span><span class="sxs-lookup"><span data-stu-id="368da-254">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="368da-255">Para quitar una entrada, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en el usuario.</span><span class="sxs-lookup"><span data-stu-id="368da-255">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="368da-256">**Dominios de confianza**: escriba el nombre del dominio (por ejemplo, contoso.com), presione entrar y repita el procedimiento según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="368da-256">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="368da-257">**Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="368da-257">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="368da-258">Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="368da-258">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="368da-259">Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:</span><span class="sxs-lookup"><span data-stu-id="368da-259">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="368da-260">**Usuarios protegidos**</span><span class="sxs-lookup"><span data-stu-id="368da-260">**Protected users**</span></span>
       - <span data-ttu-id="368da-261">**Dominios protegidos** \> **Incluir dominios de su propiedad**</span><span class="sxs-lookup"><span data-stu-id="368da-261">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="368da-262">**Dominios protegidos** \> **Dominios protegidos** (dominios personalizados)</span><span class="sxs-lookup"><span data-stu-id="368da-262">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="368da-263">**Inteligencia de buzones**</span><span class="sxs-lookup"><span data-stu-id="368da-263">**Mailbox intelligence**</span></span>

   <span data-ttu-id="368da-264">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="368da-264">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="368da-265">**Suplantación de identidad**: haga clic en **Editar** para activar o desactivar la inteligencia de suplantación, activar o desactivar la identificación del remitente sin autenticar en Outlook y configurar la acción para aplicar a los mensajes de los remitentes suplantados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="368da-265">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="368da-266">Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="368da-266">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="368da-267">Tenga en cuenta que esta misma configuración también está disponible en las directivas antiphishing en EOP.</span><span class="sxs-lookup"><span data-stu-id="368da-267">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="368da-268">**Configuración del filtro de suplantación de identidad**: el valor predeterminado es **activado** y se recomienda que lo deje activado.</span><span class="sxs-lookup"><span data-stu-id="368da-268">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="368da-269">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="368da-269">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="368da-270">Para obtener más información, vea [Configure outsimulate Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="368da-270">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="368da-271">No es necesario deshabilitar la protección contra la suplantación de identidad si el registro MX no apunta a Microsoft 365; en su lugar, se habilita el filtrado mejorado para los conectores.</span><span class="sxs-lookup"><span data-stu-id="368da-271">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="368da-272">Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="368da-272">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="368da-273">**Habilitar la característica de remitente sin autenticar**: el valor predeterminado es **activado**.</span><span class="sxs-lookup"><span data-stu-id="368da-273">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="368da-274">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="368da-274">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="368da-275">**Acciones**: especificar la acción que se realizará en los mensajes que no superen la inteligencia de identidad:</span><span class="sxs-lookup"><span data-stu-id="368da-275">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="368da-276">**Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio**:</span><span class="sxs-lookup"><span data-stu-id="368da-276">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="368da-277">**Mover mensaje a las carpetas de correo no deseado de los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="368da-277">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="368da-278">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="368da-278">**Quarantine the message**</span></span>

   - <span data-ttu-id="368da-279">**Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="368da-279">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="368da-280">Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="368da-280">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="368da-281">Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:</span><span class="sxs-lookup"><span data-stu-id="368da-281">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="368da-282">**Habilitar la protección contra la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="368da-282">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="368da-283">**Habilitar la característica de remitente sin autenticar**</span><span class="sxs-lookup"><span data-stu-id="368da-283">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="368da-284">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="368da-284">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="368da-285">**Configuración avanzada**: haga clic en **Editar** para configurar los umbrales de suplantación de identidad avanzada.</span><span class="sxs-lookup"><span data-stu-id="368da-285">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="368da-286">Para obtener más información, consulte [umbrales de suplantación de identidad avanzada en directivas antiphishing en Microsoft defender para Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="368da-286">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="368da-287">**Umbrales de suplantación de identidad avanzada**: Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="368da-287">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="368da-288">**1-estándar** (este es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="368da-288">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="368da-289">**2-agresivo**</span><span class="sxs-lookup"><span data-stu-id="368da-289">**2 - Aggressive**</span></span>
   - <span data-ttu-id="368da-290">**3-más agresivo**</span><span class="sxs-lookup"><span data-stu-id="368da-290">**3 - More aggressive**</span></span>
   - <span data-ttu-id="368da-291">**4: más agresivo**</span><span class="sxs-lookup"><span data-stu-id="368da-291">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="368da-292">**Revise la configuración**: haga clic en **Editar** para volver a la página **umbrales de suplantación de identidad avanzada** .</span><span class="sxs-lookup"><span data-stu-id="368da-292">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="368da-293">Cuando haya terminado, haga clic en **Guardar** en cualquiera de las páginas.</span><span class="sxs-lookup"><span data-stu-id="368da-293">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="368da-294">De nuevo en la página **Editar \<Name\> la Directiva** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="368da-294">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="368da-295">Usar el centro de seguridad & cumplimiento para modificar la Directiva antiphishing predeterminada en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="368da-295">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="368da-296">La Directiva antiphishing predeterminada de Microsoft defender para Office 365 se denomina Office365 ANTIPHISH predeterminada y no aparece en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="368da-296">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="368da-297">Para modificar la Directiva de suplantación de identidad (phishing) predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="368da-297">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="368da-298">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="368da-298">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="368da-299">En la página **contra la suplantación de identidad** , haga clic en **directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="368da-299">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="368da-300">Aparecerá la página **editar la Directiva de ANTIPHISH predeterminada de Office365** .</span><span class="sxs-lookup"><span data-stu-id="368da-300">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="368da-301">Las siguientes secciones están disponibles, que contienen ajustes idénticos para cuando se [modifica una directiva personalizada](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span><span class="sxs-lookup"><span data-stu-id="368da-301">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="368da-302">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="368da-302">**Impersonation**</span></span>
   - <span data-ttu-id="368da-303">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="368da-303">**Spoof**</span></span>
   - <span data-ttu-id="368da-304">**Configuración avanzada**</span><span class="sxs-lookup"><span data-stu-id="368da-304">**Advanced settings**</span></span>

   <span data-ttu-id="368da-305">Las siguientes opciones de configuración no están disponibles cuando se modifica la directiva predeterminada:</span><span class="sxs-lookup"><span data-stu-id="368da-305">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="368da-306">Puede ver la sección y los valores de configuración de la **Directiva** , pero no hay ningún vínculo **Editar** , por lo que no puede modificar la configuración (nombre de Directiva, Descripción y a quién se aplica la Directiva (se aplica a todos los destinatarios)).</span><span class="sxs-lookup"><span data-stu-id="368da-306">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="368da-307">No puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="368da-307">You can't delete the default policy.</span></span>
   - <span data-ttu-id="368da-308">No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="368da-308">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="368da-309">En la página **editar la Directiva de ANTIPHISH predeterminada de Office365** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="368da-309">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="368da-310">Habilitar o deshabilitar las directivas antiphishing personalizadas en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="368da-310">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="368da-311">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="368da-311">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="368da-312">Observe el valor de la columna **Estado** :</span><span class="sxs-lookup"><span data-stu-id="368da-312">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="368da-313">Deslice el botón de alternancia a **desactivado** para deshabilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="368da-313">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="368da-314">Deslice el botón de alternancia a **activado** para habilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="368da-314">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="368da-315">No se puede deshabilitar la Directiva antiphishing predeterminada.</span><span class="sxs-lookup"><span data-stu-id="368da-315">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="368da-316">Establecer la prioridad de las directivas antiphishing personalizadas en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="368da-316">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="368da-317">De forma predeterminada, las directivas antiphishing reciben una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen prioridad más baja que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="368da-317">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="368da-318">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="368da-318">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="368da-319">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="368da-319">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="368da-320">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="368da-320">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="368da-321">Las directivas de suplantación de identidad personalizadas se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="368da-321">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="368da-322">La Directiva antiphishing predeterminada denominada Office365 ANTIPHISH predeterminada tiene el valor de prioridad personalizado **más bajo** y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="368da-322">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="368da-323">**Nota**: en el centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la Directiva contra el suplantación de identidad (phishing) después de crearla.</span><span class="sxs-lookup"><span data-stu-id="368da-323">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="368da-324">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla antiphishing (que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="368da-324">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="368da-325">Para cambiar la prioridad de una directiva, haga clic en **aumentar prioridad** o **disminuir prioridad** en las propiedades de la Directiva (no puede modificar directamente el número de **prioridad** en el centro de seguridad & cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="368da-325">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="368da-326">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="368da-326">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="368da-327">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="368da-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="368da-328">Seleccione la Directiva que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="368da-328">Select the policy that you want to modify.</span></span> <span data-ttu-id="368da-329">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="368da-329">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="368da-330">Aparece el control flotante **editar la directiva \<name\>** .</span><span class="sxs-lookup"><span data-stu-id="368da-330">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="368da-331">La Directiva antiphishing personalizada con el valor **Priority** de prioridad **0** solo tiene el botón **disminuir prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="368da-331">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="368da-332">La Directiva antiphishing personalizada con el valor de **prioridad** más bajo (por ejemplo, **3**) solo tiene el botón **aumentar prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="368da-332">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="368da-333">Si tiene tres o más directivas de suplantación de identidad personalizadas, las directivas entre los valores de prioridad mayor y menor tienen los botones **aumentar prioridad** y **disminuir prioridad** disponibles.</span><span class="sxs-lookup"><span data-stu-id="368da-333">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="368da-334">Haga clic en **aumentar prioridad** o **disminuir prioridad** para cambiar el valor de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="368da-334">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="368da-335">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="368da-335">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="368da-336">Usar el centro de seguridad & cumplimiento para ver las directivas antiphishing en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="368da-336">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="368da-337">En el centro de seguridad & cumplimiento y vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="368da-337">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="368da-338">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="368da-338">Do one of the following steps:</span></span>

   - <span data-ttu-id="368da-339">Seleccione una directiva de antiphishing personalizada que quiera ver.</span><span class="sxs-lookup"><span data-stu-id="368da-339">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="368da-340">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="368da-340">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="368da-341">Haga clic en **directiva predeterminada** para ver la Directiva contra la suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="368da-341">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="368da-342">Aparece el control flotante **editar la directiva \<name\>** , donde puede ver la configuración y los valores.</span><span class="sxs-lookup"><span data-stu-id="368da-342">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="368da-343">Usar el centro de seguridad & cumplimiento para quitar directivas antiphishing en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="368da-343">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="368da-344">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="368da-344">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="368da-345">Seleccione la Directiva que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="368da-345">Select the policy that you want to remove.</span></span> <span data-ttu-id="368da-346">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="368da-346">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="368da-347">En el control flotante **Editar \<name\> la Directiva** que aparece, haga clic en **eliminar Directiva** y, a continuación, haga clic en **sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="368da-347">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="368da-348">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="368da-348">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="368da-349">Usar Exchange Online PowerShell para configurar directivas antiphishing en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="368da-349">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="368da-350">Como se ha descrito anteriormente, una directiva contra el correo no deseado consiste en una directiva ANTIPHISH y una regla antiphishing.</span><span class="sxs-lookup"><span data-stu-id="368da-350">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="368da-351">En Exchange Online PowerShell, la diferencia entre las directivas antiphishing y las reglas antiphishing es evidente.</span><span class="sxs-lookup"><span data-stu-id="368da-351">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="368da-352">Las directivas antiphishing se administran mediante los cmdlets **\* -AntiPhishPolicy** y se administran las reglas antiphishing mediante los cmdlets **\* -AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="368da-352">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="368da-353">En PowerShell, se crea la Directiva ANTIPHISH en primer lugar y, a continuación, se crea la regla ANTIPHISH que identifica la Directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="368da-353">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="368da-354">En PowerShell, la configuración de la Directiva antiphishing y la regla antiphishing se modifican por separado.</span><span class="sxs-lookup"><span data-stu-id="368da-354">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="368da-355">Cuando se quita una directiva ANTIPHISH de PowerShell, la regla antiphishing correspondiente no se elimina automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="368da-355">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="368da-356">Usar PowerShell para crear directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="368da-356">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="368da-357">La creación de una directiva contra la suplantación de identidad (phishing) en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="368da-357">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="368da-358">Cree la Directiva contra phish.</span><span class="sxs-lookup"><span data-stu-id="368da-358">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="368da-359">Cree la regla ANTIPHISH que especifica la Directiva antiphishing a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="368da-359">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="368da-360">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="368da-360">**Notes**:</span></span>

- <span data-ttu-id="368da-361">Puede crear una nueva regla antiphishing y asignarle una directiva ANTIPHISH existente no asociada.</span><span class="sxs-lookup"><span data-stu-id="368da-361">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="368da-362">Una regla antiphishing no puede asociarse con más de una directiva antiphishing.</span><span class="sxs-lookup"><span data-stu-id="368da-362">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="368da-363">Puede configurar las siguientes opciones en nuevas directivas antiphishing en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:</span><span class="sxs-lookup"><span data-stu-id="368da-363">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="368da-364">Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="368da-364">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="368da-365">Establezca la prioridad de la Directiva durante la creación (_prioridad_ _\<Number\>_ ) en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="368da-365">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="368da-366">Una nueva Directiva antiphishing que cree en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que asigna la Directiva a una regla antiphishing.</span><span class="sxs-lookup"><span data-stu-id="368da-366">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="368da-367">Paso 1: usar PowerShell para crear una directiva ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="368da-367">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="368da-368">Para crear una directiva contra phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="368da-368">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="368da-369">En este ejemplo se crea una directiva contra phish denominada Research Quarantine con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="368da-369">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="368da-370">La Directiva está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="368da-370">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="368da-371">La descripción es: Research Department Policy.</span><span class="sxs-lookup"><span data-stu-id="368da-371">The description is: Research department policy.</span></span>
- <span data-ttu-id="368da-372">Habilita la protección de dominios de organización para todos los dominios aceptados y la protección de dominios de destino para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="368da-372">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="368da-373">Especifica el Mai Fuji (mfujito@fabrikam.com) como el usuario que se va a proteger de la suplantación.</span><span class="sxs-lookup"><span data-stu-id="368da-373">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="368da-374">Habilita la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="368da-374">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="368da-375">Habilita la protección de inteligencia de buzones de correo y especifica la acción de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="368da-375">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="368da-376">Habilita las sugerencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="368da-376">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="368da-377">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="368da-377">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="368da-378">Paso 2: usar PowerShell para crear una regla contra el phish</span><span class="sxs-lookup"><span data-stu-id="368da-378">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="368da-379">Para crear una regla contra el phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="368da-379">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="368da-380">En este ejemplo se crea una regla ANTIPHISH denominada Research Department con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="368da-380">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="368da-381">La regla está asociada a la Directiva ANTIPHISH denominada Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="368da-381">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="368da-382">La regla se aplica a los miembros del grupo denominado Research Department.</span><span class="sxs-lookup"><span data-stu-id="368da-382">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="368da-383">Como no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="368da-383">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="368da-384">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="368da-384">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="368da-385">Usar PowerShell para ver las directivas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="368da-385">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="368da-386">Para ver las directivas ANTIPHISH existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="368da-386">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="368da-387">En este ejemplo se devuelve una lista resumida de todas las directivas contra phish junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="368da-387">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="368da-388">En este ejemplo se devuelven todos los valores de propiedad de la Directiva ANTIPHISH denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="368da-388">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="368da-389">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="368da-389">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="368da-390">Usar PowerShell para ver las reglas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="368da-390">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="368da-391">Para ver las reglas ANTIPHISH existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="368da-391">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="368da-392">En este ejemplo se devuelve una lista resumida de todas las reglas antiphishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="368da-392">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="368da-393">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="368da-393">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="368da-394">En este ejemplo se devuelven todos los valores de propiedad de la regla antiphishing denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="368da-394">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="368da-395">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="368da-395">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="368da-396">Usar PowerShell para modificar las directivas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="368da-396">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="368da-397">Aparte de los siguientes elementos, la misma configuración está disponible cuando se modifica una directiva ANTIPHISH en PowerShell como cuando se crea la Directiva tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva ANTIPHISH](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="368da-397">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="368da-398">El modificador _MakeDefault_ que convierte la Directiva especificada en la directiva predeterminada (aplicado a todos, siempre la prioridad **más baja** y no puede eliminarla) solo está disponible cuando se modifica una directiva ANTIPHISH en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="368da-398">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="368da-399">No se puede cambiar el nombre de una directiva antiphishing (el cmdlet **set-AntiPhishPolicy** no tiene un parámetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="368da-399">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="368da-400">Al cambiar el nombre de una directiva antiphishing en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_ antiphishing.</span><span class="sxs-lookup"><span data-stu-id="368da-400">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="368da-401">Para modificar una directiva contra phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="368da-401">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="368da-402">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="368da-402">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="368da-403">Usar PowerShell para modificar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="368da-403">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="368da-404">La única opción que no está disponible cuando se modifica una regla antiphishing en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="368da-404">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="368da-405">Para habilitar o deshabilitar las reglas de ANTIPHISH existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="368da-405">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="368da-406">De lo contrario, no hay opciones de configuración adicionales disponibles cuando se modifica una regla antiphishing en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="368da-406">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="368da-407">La misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla ANTIPHISH](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="368da-407">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="368da-408">Para modificar una regla antiphishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="368da-408">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="368da-409">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="368da-409">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="368da-410">Usar PowerShell para habilitar o deshabilitar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="368da-410">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="368da-411">La habilitación o deshabilitación de una regla antiphishing en PowerShell habilita o deshabilita toda la Directiva antiphishing (la regla ANTIPHISH y la Directiva de ANTIPHISH asignada).</span><span class="sxs-lookup"><span data-stu-id="368da-411">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="368da-412">No se puede habilitar o deshabilitar la Directiva de suplantación de identidad (phishing) predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="368da-412">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="368da-413">Para habilitar o deshabilitar una regla antiphishing en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="368da-413">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="368da-414">En este ejemplo se deshabilita la regla antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="368da-414">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="368da-415">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="368da-415">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="368da-416">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) y [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="368da-416">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="368da-417">Usar PowerShell para establecer la prioridad de las reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="368da-417">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="368da-418">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="368da-418">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="368da-419">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="368da-419">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="368da-420">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="368da-420">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="368da-421">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="368da-421">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="368da-422">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="368da-422">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="368da-423">Para establecer la prioridad de una regla anti-phish en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="368da-423">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="368da-424">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="368da-424">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="368da-425">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="368da-425">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="368da-426">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="368da-426">**Notes**:</span></span>

- <span data-ttu-id="368da-427">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="368da-427">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="368da-428">La Directiva ANTIPHISH predeterminada no tiene una regla ANTIPHISH correspondiente y siempre tiene el valor de prioridad no modificable **más bajo**.</span><span class="sxs-lookup"><span data-stu-id="368da-428">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="368da-429">Usar PowerShell para quitar directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="368da-429">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="368da-430">Cuando se usa PowerShell para quitar una directiva antiphishing, no se elimina la regla antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="368da-430">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="368da-431">Para quitar una directiva ANTIPHISH en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="368da-431">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="368da-432">En este ejemplo se quita la Directiva antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="368da-432">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="368da-433">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="368da-433">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="368da-434">Usar PowerShell para eliminar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="368da-434">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="368da-435">Cuando se usa PowerShell para quitar una regla antiphishing, no se elimina la Directiva antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="368da-435">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="368da-436">Para quitar una regla contra el phish en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="368da-436">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="368da-437">En este ejemplo se quita la regla antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="368da-437">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="368da-438">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="368da-438">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="368da-439">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="368da-439">How do you know these procedures worked?</span></span>

<span data-ttu-id="368da-440">Para comprobar que ha configurado correctamente las directivas antiphishing en Microsoft defender para Office 365, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="368da-440">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="368da-441">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="368da-441">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="368da-442">Compruebe la lista de directivas, sus valores de **Estado** y sus valores de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="368da-442">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="368da-443">Para ver más detalles, realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="368da-443">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="368da-444">Seleccione la Directiva de la lista y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="368da-444">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="368da-445">Haga clic en **directiva predeterminada** y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="368da-445">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="368da-446">En Exchange Online PowerShell, reemplace \<Name\> por el nombre de la Directiva o regla y ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="368da-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
