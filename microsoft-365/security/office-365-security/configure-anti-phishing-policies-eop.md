---
title: Configurar directivas contra la suplantación de identidad (phishing) en EOP
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
description: Los administradores pueden aprender a crear, modificar y eliminar las directivas antiphishing que están disponibles en las organizaciones de Exchange Online Protection (EOP) con o sin buzones de correo de Exchange Online.
ms.openlocfilehash: 69ab17263ab8c0cc03d3bc4aed6bdf39b251b9fb
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572530"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="e471a-103">Configurar directivas contra la suplantación de identidad (phishing) en EOP</span><span class="sxs-lookup"><span data-stu-id="e471a-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e471a-104">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, hay una directiva antiphishing predeterminada que contiene un número limitado de características de protección contra la suplantación de identidad habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e471a-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="e471a-105">Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="e471a-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="e471a-106">Los administradores pueden ver, editar y configurar (pero no eliminar) la Directiva de suplantación de identidad (phishing) predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e471a-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="e471a-107">Para una mayor granularidad, también puede crear directivas antiphishing personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="e471a-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="e471a-108">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="e471a-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="e471a-109">Las organizaciones con buzones de correo de Exchange online pueden configurar directivas antiphishing en el centro de seguridad & cumplimiento o en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e471a-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="e471a-110">Las organizaciones de EOP independientes solo pueden usar el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e471a-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="e471a-111">Para obtener información sobre cómo crear y modificar las directivas antiphishing más avanzadas en Microsoft defender para Office 365 que están disponibles en defender para Office 365, vea [Configure anti-phishing policies in Microsoft defender for office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e471a-111">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="e471a-112">Los elementos básicos de una directiva contra la suplantación de identidad (phishing) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e471a-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="e471a-113">**La Directiva ANTIPHISH**: especifica las protecciones de suplantación de identidad (phishing) que se deben habilitar o deshabilitar y las acciones para aplicar opciones.</span><span class="sxs-lookup"><span data-stu-id="e471a-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="e471a-114">**La regla anti-phish**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva) para una directiva antiphishing.</span><span class="sxs-lookup"><span data-stu-id="e471a-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="e471a-115">La diferencia entre estos dos elementos no es obvia cuando administra directivas antiphishing en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="e471a-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e471a-116">Al crear una directiva antiphishing, en realidad está creando una regla antiphishing y la Directiva ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="e471a-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="e471a-117">Cuando se modifica una directiva antiphishing, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado, y los filtros de destinatarios modifican la regla antiphishing.</span><span class="sxs-lookup"><span data-stu-id="e471a-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="e471a-118">Todas las demás opciones modifican la Directiva ANTIPHISH asociada.</span><span class="sxs-lookup"><span data-stu-id="e471a-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="e471a-119">Cuando se elimina una directiva antiphishing, se quita la regla antiphishing y la Directiva antiphishing asociada.</span><span class="sxs-lookup"><span data-stu-id="e471a-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="e471a-120">En Exchange Online PowerShell, puede administrar la Directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="e471a-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="e471a-121">Para obtener más información, vea la sección [usar Exchange Online PowerShell para configurar directivas de suplantación de identidad (phishing)](#use-exchange-online-powershell-to-configure-anti-phishing-policies) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="e471a-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="e471a-122">Cada organización tiene una directiva antiphishing integrada denominada Office365 ANTIPHISH predeterminada con estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="e471a-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="e471a-123">La Directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla antiphishing (filtros de destinatario) asociada a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="e471a-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="e471a-124">La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="e471a-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="e471a-125">Las directivas personalizadas que cree siempre tendrán una prioridad mayor.</span><span class="sxs-lookup"><span data-stu-id="e471a-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="e471a-126">La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e471a-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="e471a-127">Para aumentar la eficacia de la protección contra suplantación de identidad (phishing), puede crear directivas antiphishing personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="e471a-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e471a-128">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="e471a-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e471a-129">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e471a-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e471a-130">Para ir directamente a la página de **contra la suplantación de identidad (phishing** ), use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="e471a-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="e471a-131">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e471a-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="e471a-132">No puede administrar las directivas antiphishing en PowerShell de EOP independiente.</span><span class="sxs-lookup"><span data-stu-id="e471a-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="e471a-133">Debe tener asignados permisos en el centro de seguridad & cumplimiento antes de poder llevar a cabo los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="e471a-133">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e471a-134">Para agregar, modificar y eliminar directivas antiphishing, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="e471a-134">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e471a-135">Para el acceso de solo lectura a las directivas antiphishing, debe ser miembro de los grupos de roles **lector global** o **lector** de seguridad <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="e471a-135">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="e471a-136">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e471a-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="e471a-137">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="e471a-137">**Notes**:</span></span>

  - <span data-ttu-id="e471a-138">La adición de usuarios al rol correspondiente de Azure Active Directory en el centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el centro de seguridad & cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e471a-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e471a-139">Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="e471a-139">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="e471a-140">El grupo de roles administración de la **organización de solo vista** de [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="e471a-140">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="e471a-141"><sup>\*</sup> En el centro de seguridad & cumplimiento, el acceso de solo lectura permite a los usuarios ver la configuración de las directivas antiphishing personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e471a-141"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="e471a-142">Solo lectura los usuarios no pueden ver la configuración de la Directiva de suplantación de identidad (phishing) predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e471a-142">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="e471a-143">Para crear y modificar directivas antiphishing en EOP independiente, debe hacer algo que requiera la _hidratación_ de su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="e471a-143">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="e471a-144">Por ejemplo, en el centro de administración de Exchange (EAC), puede ir a la pestaña **permisos** , seleccionar un grupo de roles existente, hacer clic en **Editar** ![ icono de edición ](../../media/ITPro-EAC-EditIcon.png) y quitar una función (que, más adelante, se agregará).</span><span class="sxs-lookup"><span data-stu-id="e471a-144">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="e471a-145">Si nunca se ha hidratado el espacio empresarial, se obtiene un cuadro de diálogo denominado configuración de la **organización de actualización** con una barra de progreso que debería completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="e471a-145">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="e471a-146">Para obtener más información sobre la hidratación, consulte el cmdlet [enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (que no está disponible en POWERSHELL de EOP independiente ni en el centro de seguridad & cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="e471a-146">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="e471a-147">Para conocer la configuración recomendada para las directivas antiphishing, consulte [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="e471a-147">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="e471a-148">Espere hasta 30 minutos para que se aplique la directiva actualizada.</span><span class="sxs-lookup"><span data-stu-id="e471a-148">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="e471a-149">Para obtener información acerca de dónde se aplican las directivas contra la suplantación de identidad (phishing) en la canalización de filtros, consulte [Order and Precedence of email Protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="e471a-149">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="e471a-150">Usar el centro de seguridad & cumplimiento para crear directivas contra la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="e471a-150">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="e471a-151">La creación de una directiva antiphishing personalizada en el centro de seguridad & cumplimiento crea la regla antiphishing y la Directiva ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="e471a-151">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="e471a-152">Cuando se crea una directiva antiphishing, solo se puede especificar el nombre de la Directiva, la descripción y el filtro de destinatarios que identifican a quién se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="e471a-152">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="e471a-153">Después de crear la Directiva, puede modificar la Directiva para cambiar o revisar la configuración predeterminada de la suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="e471a-153">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="e471a-154">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="e471a-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e471a-155">En la página **contra la suplantación de identidad** , haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="e471a-155">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="e471a-156">Se abrirá el Asistente para **crear una nueva Directiva antiphishing** .</span><span class="sxs-lookup"><span data-stu-id="e471a-156">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="e471a-157">En la página **asigne un nombre a la Directiva** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e471a-157">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="e471a-158">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="e471a-158">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="e471a-159">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="e471a-159">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="e471a-160">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e471a-160">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e471a-161">En la página **aplicado a** que aparece, identifique los destinatarios internos a los que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="e471a-161">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="e471a-162">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="e471a-162">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="e471a-163">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="e471a-163">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="e471a-164">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="e471a-164">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="e471a-165">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="e471a-165">Click **Add a condition**.</span></span> <span data-ttu-id="e471a-166">En la lista desplegable que aparece, seleccione una condición en **aplicado si**:</span><span class="sxs-lookup"><span data-stu-id="e471a-166">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="e471a-167">**El destinatario es**: especifica uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="e471a-167">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="e471a-168">**El destinatario es un miembro de**: especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="e471a-168">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="e471a-169">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.</span><span class="sxs-lookup"><span data-stu-id="e471a-169">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="e471a-170">Después de seleccionar la condición, aparece la lista desplegable correspondiente con una **de estas** casillas.</span><span class="sxs-lookup"><span data-stu-id="e471a-170">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="e471a-171">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="e471a-171">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="e471a-172">Haga clic en el cuadro y comience a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="e471a-172">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="e471a-173">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="e471a-173">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="e471a-174">Para quitar entradas individuales, haga **Remove** clic en ![ el icono quitar quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="e471a-174">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="e471a-175">Para quitar toda la condición, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en la condición.</span><span class="sxs-lookup"><span data-stu-id="e471a-175">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="e471a-176">Para agregar una condición adicional, haga clic en **Agregar condición** y seleccione un valor restante en **aplicado si**.</span><span class="sxs-lookup"><span data-stu-id="e471a-176">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="e471a-177">Para agregar excepciones, haga clic en **Agregar una condición** y seleccione una excepción en **excepto si**.</span><span class="sxs-lookup"><span data-stu-id="e471a-177">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="e471a-178">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="e471a-178">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="e471a-179">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e471a-179">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e471a-180">En la página **Revise la configuración** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="e471a-180">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="e471a-181">Puede hacer clic en **Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="e471a-181">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="e471a-182">Cuando haya terminado, haga clic en **crear esta directiva**.</span><span class="sxs-lookup"><span data-stu-id="e471a-182">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="e471a-183">Haga clic en **Aceptar** en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="e471a-183">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="e471a-184">Después de crear la Directiva antiphishing con estas opciones de directiva generales, siga las instrucciones de la siguiente sección para establecer la configuración de protección en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="e471a-184">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="e471a-185">Usar el centro de seguridad & cumplimiento para modificar las directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="e471a-185">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="e471a-186">Use los siguientes procedimientos para modificar las directivas antiphishing: una nueva directiva que ha creado o las directivas existentes que ya ha personalizado.</span><span class="sxs-lookup"><span data-stu-id="e471a-186">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="e471a-187">Si aún no está ahí, abra el centro de seguridad & cumplimiento y vaya a la Directiva de **Administración de amenazas** \> **Policy** \> **contra la suplantación de identidad (phishing)**.</span><span class="sxs-lookup"><span data-stu-id="e471a-187">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e471a-188">Seleccione la Directiva antiphishing personalizada que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="e471a-188">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="e471a-189">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="e471a-189">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="e471a-190">Aparece el control flotante **editar la directiva \<name\>** .</span><span class="sxs-lookup"><span data-stu-id="e471a-190">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="e471a-191">Al hacer clic en **Editar** en cualquier sección, obtendrá acceso a la configuración de esa sección.</span><span class="sxs-lookup"><span data-stu-id="e471a-191">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="e471a-192">Los pasos siguientes se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="e471a-192">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="e471a-193">Después de hacer clic en **Editar** en una sección, la configuración disponible se presenta en un formato de asistente, pero puede saltar dentro de las páginas en cualquier orden y puede hacer clic en **Guardar** en cualquier página (o en **Cancelar** o **cerrar** el ![ icono cerrar ](../../media/scc-remove-icon.png) para volver a la página **editar la directiva \<name\>** ) (no es necesario visitar la última página del Asistente para guardarla o dejarla).</span><span class="sxs-lookup"><span data-stu-id="e471a-193">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="e471a-194">**Configuración de directiva**: haga clic en **Editar** para modificar la misma configuración que estaba disponible cuando [creó la Directiva](#use-the-security--compliance-center-to-create-anti-phishing-policies) en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="e471a-194">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="e471a-195">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e471a-195">**Name**</span></span>
   - <span data-ttu-id="e471a-196">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e471a-196">**Description**</span></span>
   - <span data-ttu-id="e471a-197">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="e471a-197">**Applied to**</span></span>
   - <span data-ttu-id="e471a-198">**Revisar la configuración**</span><span class="sxs-lookup"><span data-stu-id="e471a-198">**Review your settings**</span></span>

   <span data-ttu-id="e471a-199">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="e471a-199">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="e471a-200">**Suplantación de identidad**: haga clic en **Editar** para activar o desactivar la inteligencia de suplantación, activar o desactivar la identificación del remitente sin autenticar en Outlook y configurar la acción para aplicar a los mensajes de los remitentes suplantados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="e471a-200">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="e471a-201">Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="e471a-201">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="e471a-202">Tenga en cuenta que esta misma configuración también está disponible en directivas antiphishing en defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e471a-202">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="e471a-203">**Configuración del filtro de suplantación de identidad**: el valor predeterminado es **activado** y se recomienda que lo deje activado.</span><span class="sxs-lookup"><span data-stu-id="e471a-203">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="e471a-204">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="e471a-204">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="e471a-205">Para obtener más información, vea [Configure outsimulate Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="e471a-205">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="e471a-206">No es necesario deshabilitar la protección contra la suplantación de identidad si el registro MX no apunta a Microsoft 365; en su lugar, se habilita el filtrado mejorado para los conectores.</span><span class="sxs-lookup"><span data-stu-id="e471a-206">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="e471a-207">Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="e471a-207">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="e471a-208">**Habilitar la característica de remitente sin autenticar**: el valor predeterminado es **activado**.</span><span class="sxs-lookup"><span data-stu-id="e471a-208">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="e471a-209">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="e471a-209">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="e471a-210">**Acciones**: especificar la acción que se realizará en los mensajes que no superen la inteligencia de identidad:</span><span class="sxs-lookup"><span data-stu-id="e471a-210">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="e471a-211">**Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio**:</span><span class="sxs-lookup"><span data-stu-id="e471a-211">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="e471a-212">**Mover mensaje a las carpetas de correo no deseado de los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="e471a-212">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="e471a-213">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="e471a-213">**Quarantine the message**</span></span>

   - <span data-ttu-id="e471a-214">**Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="e471a-214">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="e471a-215">Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e471a-215">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="e471a-216">Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:</span><span class="sxs-lookup"><span data-stu-id="e471a-216">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="e471a-217">**Habilitar la protección contra la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="e471a-217">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="e471a-218">**Habilitar la característica de remitente sin autenticar**</span><span class="sxs-lookup"><span data-stu-id="e471a-218">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="e471a-219">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="e471a-219">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="e471a-220">De nuevo en la página **Editar \<Name\> la Directiva** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e471a-220">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="e471a-221">Usar el centro de seguridad & cumplimiento para modificar la Directiva contra suplantación de identidad (phishing) predeterminada</span><span class="sxs-lookup"><span data-stu-id="e471a-221">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="e471a-222">La Directiva antiphishing predeterminada se denomina Office365 ANTIPHISH predeterminada y no aparece en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="e471a-222">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="e471a-223">Para modificar la Directiva de suplantación de identidad (phishing) predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e471a-223">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="e471a-224">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="e471a-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e471a-225">En la página **contra la suplantación de identidad** , haga clic en **directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="e471a-225">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="e471a-226">Aparecerá la página **editar la Directiva de ANTIPHISH predeterminada de Office365** .</span><span class="sxs-lookup"><span data-stu-id="e471a-226">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="e471a-227">Las siguientes secciones están disponibles, que contienen ajustes idénticos para cuando se [modifica una directiva personalizada](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="e471a-227">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="e471a-228">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="e471a-228">**Impersonation**</span></span>
   - <span data-ttu-id="e471a-229">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="e471a-229">**Spoof**</span></span>
   - <span data-ttu-id="e471a-230">**Configuración avanzada**</span><span class="sxs-lookup"><span data-stu-id="e471a-230">**Advanced settings**</span></span>

   <span data-ttu-id="e471a-231">Las siguientes opciones de configuración no están disponibles cuando se modifica la directiva predeterminada:</span><span class="sxs-lookup"><span data-stu-id="e471a-231">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="e471a-232">Puede ver la sección y los valores de configuración de la **Directiva** , pero no hay ningún vínculo **Editar** , por lo que no puede modificar la configuración (nombre de Directiva, Descripción y a quién se aplica la Directiva (se aplica a todos los destinatarios)).</span><span class="sxs-lookup"><span data-stu-id="e471a-232">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="e471a-233">No puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e471a-233">You can't delete the default policy.</span></span>
   - <span data-ttu-id="e471a-234">No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="e471a-234">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="e471a-235">En la página **editar la Directiva de ANTIPHISH predeterminada de Office365** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e471a-235">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="e471a-236">Habilitar o deshabilitar las directivas antiphishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="e471a-236">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="e471a-237">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="e471a-237">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e471a-238">Observe el valor de la columna **Estado** :</span><span class="sxs-lookup"><span data-stu-id="e471a-238">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="e471a-239">Deslice el botón de alternancia a **desactivado** para deshabilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="e471a-239">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="e471a-240">Deslice el botón de alternancia a **activado** para habilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="e471a-240">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="e471a-241">No se puede deshabilitar la Directiva antiphishing predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e471a-241">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="e471a-242">Establecer la prioridad de las directivas antiphishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="e471a-242">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="e471a-243">De forma predeterminada, las directivas antiphishing reciben una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen prioridad más baja que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="e471a-243">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="e471a-244">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="e471a-244">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="e471a-245">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="e471a-245">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="e471a-246">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="e471a-246">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="e471a-247">Las directivas de suplantación de identidad personalizadas se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="e471a-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="e471a-248">La Directiva antiphishing predeterminada denominada Office365 ANTIPHISH predeterminada tiene el valor de prioridad personalizado **más bajo** y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="e471a-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="e471a-249">**Nota**: en el centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la Directiva contra el suplantación de identidad (phishing) después de crearla.</span><span class="sxs-lookup"><span data-stu-id="e471a-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="e471a-250">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla antiphishing (que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="e471a-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="e471a-251">Para cambiar la prioridad de una directiva, haga clic en **aumentar prioridad** o **disminuir prioridad** en las propiedades de la Directiva (no puede modificar directamente el número de **prioridad** en el centro de seguridad & cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="e471a-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="e471a-252">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="e471a-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="e471a-253">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="e471a-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="e471a-254">Seleccione la Directiva que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="e471a-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="e471a-255">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="e471a-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="e471a-256">Aparece el control flotante **editar la directiva \<name\>** .</span><span class="sxs-lookup"><span data-stu-id="e471a-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="e471a-257">La Directiva antiphishing personalizada con el valor **Priority** de prioridad **0** solo tiene el botón **disminuir prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="e471a-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="e471a-258">La Directiva antiphishing personalizada con el valor de **prioridad** más bajo (por ejemplo, **3**) solo tiene el botón **aumentar prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="e471a-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="e471a-259">Si tiene tres o más directivas de suplantación de identidad personalizadas, las directivas entre los valores de prioridad mayor y menor tienen los botones **aumentar prioridad** y **disminuir prioridad** disponibles.</span><span class="sxs-lookup"><span data-stu-id="e471a-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="e471a-260">Haga clic en **aumentar prioridad** o **disminuir prioridad** para cambiar el valor de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="e471a-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="e471a-261">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e471a-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="e471a-262">Usar el centro de seguridad & cumplimiento para ver las directivas de protección contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="e471a-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="e471a-263">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="e471a-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e471a-264">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e471a-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="e471a-265">Seleccione una directiva de antiphishing personalizada que quiera ver.</span><span class="sxs-lookup"><span data-stu-id="e471a-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="e471a-266">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="e471a-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="e471a-267">Haga clic en **directiva predeterminada** para ver la Directiva contra la suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e471a-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="e471a-268">Aparece el control flotante **editar la directiva \<name\>** , donde puede ver la configuración y los valores.</span><span class="sxs-lookup"><span data-stu-id="e471a-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="e471a-269">Usar el centro de seguridad & cumplimiento para eliminar las directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="e471a-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="e471a-270">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="e471a-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e471a-271">Seleccione la Directiva que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="e471a-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="e471a-272">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="e471a-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="e471a-273">En el control flotante **Editar \<name\> la Directiva** que aparece, haga clic en **eliminar Directiva** y, a continuación, haga clic en **sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="e471a-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="e471a-274">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e471a-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="e471a-275">Usar Exchange Online PowerShell para configurar las directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="e471a-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="e471a-276">Como se ha descrito anteriormente, una directiva antiphishing consta de una directiva antiphishing y una regla antiphishing.</span><span class="sxs-lookup"><span data-stu-id="e471a-276">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="e471a-277">En Exchange Online PowerShell, la diferencia entre las directivas antiphishing y las reglas antiphishing es evidente.</span><span class="sxs-lookup"><span data-stu-id="e471a-277">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="e471a-278">Las directivas antiphishing se administran mediante los cmdlets **\* -AntiPhishPolicy** y se administran las reglas antiphishing mediante los cmdlets **\* -AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="e471a-278">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="e471a-279">En PowerShell, se crea la Directiva ANTIPHISH en primer lugar y, a continuación, se crea la regla ANTIPHISH que identifica la Directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="e471a-279">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="e471a-280">En PowerShell, la configuración de la Directiva antiphishing y la regla antiphishing se modifican por separado.</span><span class="sxs-lookup"><span data-stu-id="e471a-280">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="e471a-281">Cuando se quita una directiva ANTIPHISH de PowerShell, la regla antiphishing correspondiente no se elimina automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="e471a-281">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="e471a-282">Los siguientes procedimientos de PowerShell no están disponibles en organizaciones de EOP independientes con Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e471a-282">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="e471a-283">Usar PowerShell para crear directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="e471a-283">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="e471a-284">La creación de una directiva contra la suplantación de identidad (phishing) en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="e471a-284">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="e471a-285">Cree la Directiva contra phish.</span><span class="sxs-lookup"><span data-stu-id="e471a-285">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="e471a-286">Cree la regla ANTIPHISH que especifica la Directiva antiphishing a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="e471a-286">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="e471a-287">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="e471a-287">**Notes**:</span></span>

- <span data-ttu-id="e471a-288">Puede crear una nueva regla antiphishing y asignarle una directiva ANTIPHISH existente no asociada.</span><span class="sxs-lookup"><span data-stu-id="e471a-288">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="e471a-289">Una regla antiphishing no puede asociarse con más de una directiva antiphishing.</span><span class="sxs-lookup"><span data-stu-id="e471a-289">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="e471a-290">Puede configurar las siguientes opciones en nuevas directivas antiphishing en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:</span><span class="sxs-lookup"><span data-stu-id="e471a-290">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="e471a-291">Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="e471a-291">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="e471a-292">Establezca la prioridad de la Directiva durante la creación (_prioridad_ _\<Number\>_ ) en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="e471a-292">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="e471a-293">Una nueva Directiva antiphishing que cree en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que asigna la Directiva a una regla antiphishing.</span><span class="sxs-lookup"><span data-stu-id="e471a-293">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="e471a-294">Paso 1: usar PowerShell para crear una directiva ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="e471a-294">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="e471a-295">Para crear una directiva contra phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e471a-295">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="e471a-296">En este ejemplo se crea una directiva contra phish denominada Research Quarantine con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="e471a-296">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="e471a-297">La descripción es: Research Department Policy.</span><span class="sxs-lookup"><span data-stu-id="e471a-297">The description is: Research department policy.</span></span>
- <span data-ttu-id="e471a-298">Cambia la acción predeterminada para la suplantación de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="e471a-298">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="e471a-299">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="e471a-299">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="e471a-300">Paso 2: usar PowerShell para crear una regla contra el phish</span><span class="sxs-lookup"><span data-stu-id="e471a-300">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="e471a-301">Para crear una regla contra el phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e471a-301">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="e471a-302">En este ejemplo se crea una regla ANTIPHISH denominada Research Department con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="e471a-302">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="e471a-303">La regla está asociada a la Directiva ANTIPHISH denominada Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="e471a-303">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="e471a-304">La regla se aplica a los miembros del grupo denominado Research Department.</span><span class="sxs-lookup"><span data-stu-id="e471a-304">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="e471a-305">Como no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e471a-305">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="e471a-306">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="e471a-306">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="e471a-307">Usar PowerShell para ver las directivas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="e471a-307">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="e471a-308">Para ver las directivas ANTIPHISH existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e471a-308">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e471a-309">En este ejemplo se devuelve una lista resumida de todas las directivas contra phish junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="e471a-309">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="e471a-310">En este ejemplo se devuelven todos los valores de propiedad de la Directiva ANTIPHISH denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="e471a-310">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="e471a-311">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="e471a-311">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="e471a-312">Usar PowerShell para ver las reglas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="e471a-312">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="e471a-313">Para ver las reglas ANTIPHISH existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e471a-313">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e471a-314">En este ejemplo se devuelve una lista resumida de todas las reglas antiphishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="e471a-314">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="e471a-315">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="e471a-315">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="e471a-316">En este ejemplo se devuelven todos los valores de propiedad de la regla antiphishing denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="e471a-316">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="e471a-317">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="e471a-317">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="e471a-318">Usar PowerShell para modificar las directivas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="e471a-318">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="e471a-319">Aparte de los siguientes elementos, la misma configuración está disponible cuando se modifica una directiva ANTIPHISH en PowerShell como cuando se crea una directiva como se describe en [paso 1: usar PowerShell para crear una directiva ANTIPHISH](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="e471a-319">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="e471a-320">El modificador _MakeDefault_ que convierte la Directiva especificada en la directiva predeterminada (aplicado a todos, siempre la prioridad **más baja** y no puede eliminarla) solo está disponible cuando se modifica una directiva ANTIPHISH en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e471a-320">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="e471a-321">No se puede cambiar el nombre de una directiva antiphishing (el cmdlet **set-AntiPhishPolicy** no tiene un parámetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="e471a-321">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="e471a-322">Al cambiar el nombre de una directiva antiphishing en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_ antiphishing.</span><span class="sxs-lookup"><span data-stu-id="e471a-322">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="e471a-323">Para modificar una directiva contra phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e471a-323">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="e471a-324">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="e471a-324">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="e471a-325">Usar PowerShell para modificar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="e471a-325">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="e471a-326">La única opción que no está disponible cuando se modifica una regla antiphishing en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="e471a-326">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="e471a-327">Para habilitar o deshabilitar las reglas de ANTIPHISH existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="e471a-327">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="e471a-328">De lo contrario, la misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla ANTIPHISH](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="e471a-328">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="e471a-329">Para modificar una regla antiphishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e471a-329">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="e471a-330">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="e471a-330">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="e471a-331">Usar PowerShell para habilitar o deshabilitar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="e471a-331">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="e471a-332">La habilitación o deshabilitación de una regla antiphishing en PowerShell habilita o deshabilita toda la Directiva antiphishing (la regla ANTIPHISH y la Directiva de ANTIPHISH asignada).</span><span class="sxs-lookup"><span data-stu-id="e471a-332">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="e471a-333">No se puede habilitar o deshabilitar la Directiva de suplantación de identidad (phishing) predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="e471a-333">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="e471a-334">Para habilitar o deshabilitar una regla antiphishing en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e471a-334">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="e471a-335">En este ejemplo se deshabilita la regla antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e471a-335">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e471a-336">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="e471a-336">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e471a-337">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) y [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="e471a-337">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="e471a-338">Usar PowerShell para establecer la prioridad de las reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="e471a-338">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="e471a-339">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="e471a-339">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="e471a-340">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="e471a-340">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="e471a-341">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="e471a-341">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="e471a-342">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="e471a-342">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="e471a-343">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="e471a-343">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="e471a-344">Para establecer la prioridad de una regla anti-phish en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e471a-344">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="e471a-345">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="e471a-345">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="e471a-346">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="e471a-346">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="e471a-347">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="e471a-347">**Notes**:</span></span>

- <span data-ttu-id="e471a-348">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e471a-348">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="e471a-349">La Directiva ANTIPHISH predeterminada no tiene una regla ANTIPHISH correspondiente y siempre tiene el valor de prioridad no modificable **más bajo**.</span><span class="sxs-lookup"><span data-stu-id="e471a-349">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="e471a-350">Usar PowerShell para quitar directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="e471a-350">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="e471a-351">Cuando se usa PowerShell para quitar una directiva antiphishing, no se elimina la regla antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e471a-351">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="e471a-352">Para quitar una directiva ANTIPHISH en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e471a-352">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="e471a-353">En este ejemplo se quita la Directiva antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e471a-353">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="e471a-354">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="e471a-354">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="e471a-355">Usar PowerShell para eliminar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="e471a-355">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="e471a-356">Cuando se usa PowerShell para quitar una regla antiphishing, no se elimina la Directiva antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e471a-356">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="e471a-357">Para quitar una regla contra el phish en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e471a-357">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="e471a-358">En este ejemplo se quita la regla antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e471a-358">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="e471a-359">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="e471a-359">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e471a-360">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="e471a-360">How do you know these procedures worked?</span></span>

<span data-ttu-id="e471a-361">Para comprobar que ha configurado correctamente las directivas antiphishing en Microsoft defender para Office 365, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e471a-361">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="e471a-362">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="e471a-362">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="e471a-363">Compruebe la lista de directivas, sus valores de **Estado** y sus valores de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="e471a-363">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="e471a-364">Para ver más detalles, realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e471a-364">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="e471a-365">Seleccione la Directiva de la lista y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="e471a-365">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="e471a-366">Haga clic en **directiva predeterminada** y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="e471a-366">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="e471a-367">En Exchange Online PowerShell, reemplace \<Name\> por el nombre de la Directiva o regla, ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="e471a-367">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
