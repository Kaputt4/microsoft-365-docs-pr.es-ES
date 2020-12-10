---
title: Configurar el filtrado de spam de salida
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre cómo ver, crear, modificar y eliminar directivas de correo no deseado salientes en Exchange Online Protection (EOP).
ms.openlocfilehash: 237703d9ad6ed652a3feb4dda57a7af0e99240f7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614945"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="a29b6-103">Configurar el filtrado de correo no deseado saliente en EOP</span><span class="sxs-lookup"><span data-stu-id="a29b6-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a29b6-104">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes de correo electrónico salientes que se envían a través de EOP se comprueban automáticamente en busca de correo no deseado y actividad de envío inusual.</span><span class="sxs-lookup"><span data-stu-id="a29b6-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="a29b6-105">Normalmente, el correo no deseado saliente de un usuario de la organización indica una cuenta en peligro.</span><span class="sxs-lookup"><span data-stu-id="a29b6-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="a29b6-106">Los mensajes sospechosos se marcan como correo no deseado (independientemente del nivel de confianza de correo no deseado o de SCL) y se enrutan a través del [grupo de entrega de alto riesgo](high-risk-delivery-pool-for-outbound-messages.md) para ayudar a proteger la reputación del servicio (es decir, mantenga los servidores de correo electrónico de origen de Microsoft 365 en las listas de direcciones IP bloqueadas).</span><span class="sxs-lookup"><span data-stu-id="a29b6-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="a29b6-107">Los administradores reciben automáticamente una notificación de la actividad de correo electrónico saliente y de los usuarios bloqueados mediante [directivas de alerta](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a29b6-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="a29b6-108">EOP usa directivas de correo no deseado salientes como parte de la defensa general de la organización contra el correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a29b6-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="a29b6-109">Para obtener más información, consulte [Protección contra correo no deseado](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="a29b6-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="a29b6-110">Los administradores pueden ver, editar y configurar (pero no eliminar) la Directiva de correo no deseado saliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a29b6-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="a29b6-111">Para una mayor granularidad, también puede crear directivas de correo no deseado saliente personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="a29b6-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="a29b6-112">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="a29b6-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="a29b6-113">Puede configurar directivas de correo no deseado salientes en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones en Exchange Online; independiente de EOP para organizaciones sin buzones de correo de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="a29b6-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="a29b6-114">Los elementos básicos de una directiva de correo no deseado saliente en EOP son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a29b6-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="a29b6-115">**La Directiva de filtro de correo no deseado saliente**: especifica las acciones para los veredictos de filtrado de correo no deseado saliente y las opciones de notificación.</span><span class="sxs-lookup"><span data-stu-id="a29b6-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="a29b6-116">**La regla de filtro de correo no deseado saliente**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva) para una directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="a29b6-117">La diferencia entre estos dos elementos no es obvia cuando se administran las directivas de correo no deseado saliente en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="a29b6-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a29b6-118">Al crear una directiva, en realidad está creando una regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado de salida asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="a29b6-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a29b6-119">Cuando se modifica una directiva, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado y destinatario modifica la regla de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="a29b6-120">Todas las demás opciones modifican la Directiva de filtro de correo no deseado saliente asociada.</span><span class="sxs-lookup"><span data-stu-id="a29b6-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="a29b6-121">Al quitar una directiva, se quita la regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asociada.</span><span class="sxs-lookup"><span data-stu-id="a29b6-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="a29b6-122">En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="a29b6-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a29b6-123">Para obtener más información, consulte la sección [usar Exchange Online PowerShell o Standalone EOP PowerShell para configurar directivas de correo no deseado saliente](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="a29b6-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="a29b6-124">Cada organización tiene integrada una directiva de correo no deseado saliente denominada predeterminada que tiene estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="a29b6-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="a29b6-125">La Directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla de filtro de correo no deseado saliente (filtros de destinatario) asociada a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="a29b6-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="a29b6-126">La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="a29b6-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="a29b6-127">Las directivas personalizadas que cree siempre tendrán una prioridad mayor que la directiva denominada Predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a29b6-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="a29b6-128">La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a29b6-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="a29b6-129">Para aumentar la eficacia del filtrado de correo no deseado saliente, puede crear directivas de correo no deseado saliente personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="a29b6-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a29b6-130">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="a29b6-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a29b6-131">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a29b6-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a29b6-132">Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="a29b6-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="a29b6-133">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a29b6-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a29b6-134">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="a29b6-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a29b6-135">Debe tener asignados permisos en el centro de seguridad & cumplimiento antes de poder llevar a cabo los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="a29b6-135">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a29b6-136">Para agregar, modificar y eliminar directivas de correo no deseado saliente, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="a29b6-136">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a29b6-137">Para el acceso de solo lectura a las directivas de correo no deseado saliente, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="a29b6-137">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a29b6-138">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a29b6-138">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="a29b6-139">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="a29b6-139">**Notes**:</span></span>

  - <span data-ttu-id="a29b6-140">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a29b6-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a29b6-141">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="a29b6-141">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="a29b6-142">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="a29b6-142">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a29b6-143">Para conocer la configuración recomendada para las directivas de correo no deseado saliente, consulte [EOP Outbound Spam Filter Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="a29b6-143">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="a29b6-144">Las [directivas de alerta](../../compliance/alert-policies.md) predeterminadas denominadas límite de envío de **correo electrónico superado**, los **patrones de envío de correo electrónico sospechoso detectados** y el **usuario restringido del envío de correo electrónico** ya envían notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**global Admins**) sobre la actividad de correo electrónico saliente y los usuarios bloqueados debido a correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-144">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="a29b6-145">Para obtener más información, consulte [Verify The Alert Settings for Restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="a29b6-145">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="a29b6-146">Se recomienda usar estas directivas de alerta en lugar de las opciones de notificación en las directivas de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-146">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="a29b6-147">Usar el centro de seguridad & cumplimiento para crear directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-147">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="a29b6-148">La creación de una directiva personalizada de correo no deseado saliente en el centro de seguridad & cumplimiento crea la regla de filtro de correo no deseado y la Directiva de filtro de correo no deseado asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="a29b6-148">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="a29b6-149">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a29b6-150">En la página **configuración contra correo no deseado** , haga clic en **crear una directiva de salida**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-150">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="a29b6-151">En la **Directiva de filtro de correo no deseado saliente** , vaya hacia fuera que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a29b6-151">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="a29b6-152">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="a29b6-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="a29b6-153">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="a29b6-153">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="a29b6-154">Opcional Expanda la sección **notificaciones** para configurar usuarios adicionales que deben recibir copias y notificaciones de mensajes de correo electrónico salientes sospechosos:</span><span class="sxs-lookup"><span data-stu-id="a29b6-154">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="a29b6-155">**Enviar una copia de los mensajes de correo electrónico saliente sospechosos a personas específicas**: esta opción agrega los usuarios especificados como destinatarios en copia oculta a los mensajes sospechosos de salida.</span><span class="sxs-lookup"><span data-stu-id="a29b6-155">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a29b6-156">Esta configuración solo funciona en la directiva predeterminada de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-156">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="a29b6-157">No funciona en las directivas de correo no deseado saliente personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="a29b6-157">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="a29b6-158">Para habilitar esta opción:</span><span class="sxs-lookup"><span data-stu-id="a29b6-158">To enable this setting:</span></span>

     1. <span data-ttu-id="a29b6-159">Active la casilla para habilitar la configuración.</span><span class="sxs-lookup"><span data-stu-id="a29b6-159">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="a29b6-160">Haga clic en **Agregar personas**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-160">Click **Add people**.</span></span> <span data-ttu-id="a29b6-161">En el control flotante **Agregar o quitar destinatarios** que aparece:</span><span class="sxs-lookup"><span data-stu-id="a29b6-161">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="a29b6-162">Escriba la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-162">Enter the sender's email address.</span></span> <span data-ttu-id="a29b6-163">Puede especificar varias direcciones de correo electrónico separadas por punto y coma (;) o un destinatario por línea.</span><span class="sxs-lookup"><span data-stu-id="a29b6-163">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="a29b6-164">Haga clic en</span><span class="sxs-lookup"><span data-stu-id="a29b6-164">Click</span></span> ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="a29b6-166">para agregar los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="a29b6-166">to add the recipients.</span></span>

        <span data-ttu-id="a29b6-167">Repita estos pasos tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a29b6-167">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="a29b6-168">Los destinatarios que ha agregado aparecen en la sección **lista de destinatarios** en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="a29b6-168">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="a29b6-169">Para eliminar un destinatario, haga clic en el ![ botón quitar ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="a29b6-169">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="a29b6-170">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-170">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="a29b6-171">Para deshabilitar esta opción, desactive la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="a29b6-171">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="a29b6-172">**Notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado saliente**:</span><span class="sxs-lookup"><span data-stu-id="a29b6-172">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="a29b6-173">Esta configuración está en desuso de las directivas de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-173">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="a29b6-174">La [Directiva de alerta](../../compliance/alert-policies.md) predeterminada denominada **usuario restringido del envío de correo electrónico** ya envía notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**administradores globales**) cuando los usuarios se bloquean debido a que superan los límites de la sección **límites de destinatarios** .</span><span class="sxs-lookup"><span data-stu-id="a29b6-174">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="a29b6-175">Se **recomienda encarecidamente usar la Directiva de alertas en lugar de esta opción en la Directiva de correo no deseado saliente para notificar a los administradores y a otros usuarios**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-175">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="a29b6-176">Para obtener instrucciones, consulte [Verify The Alert Settings for Restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="a29b6-176">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="a29b6-177">Opcional Expanda la sección **límites de destinatarios** para configurar los límites y las acciones de los mensajes de correo electrónico saliente sospechosos:</span><span class="sxs-lookup"><span data-stu-id="a29b6-177">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="a29b6-178">Esta configuración solo se aplica a los buzones basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="a29b6-178">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="a29b6-179">**Número máximo de destinatarios por usuario**</span><span class="sxs-lookup"><span data-stu-id="a29b6-179">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="a29b6-180">Un valor válido es de 0 a 10000.</span><span class="sxs-lookup"><span data-stu-id="a29b6-180">A valid value is 0 to 10000.</span></span> <span data-ttu-id="a29b6-181">El valor predeterminado es 0, lo que significa que se usan los valores predeterminados del servicio.</span><span class="sxs-lookup"><span data-stu-id="a29b6-181">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="a29b6-182">Para obtener más información, consulte [límites de envío](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="a29b6-182">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="a29b6-183">**Límite horario externo**: el número máximo de destinatarios externos por hora.</span><span class="sxs-lookup"><span data-stu-id="a29b6-183">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="a29b6-184">**Límite horario interno**: el número máximo de destinatarios internos por hora.</span><span class="sxs-lookup"><span data-stu-id="a29b6-184">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="a29b6-185">**Límite diario**: número máximo total de destinatarios por día.</span><span class="sxs-lookup"><span data-stu-id="a29b6-185">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="a29b6-186">**Acción cuando un usuario supera los límites anteriores**: configure la acción que se llevará a cabo cuando se supere alguno de los **límites de destinatarios** .</span><span class="sxs-lookup"><span data-stu-id="a29b6-186">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="a29b6-187">Para todas las acciones, los destinatarios especificados en el **usuario restringió el envío de la Directiva de alerta de correo electrónico** (y en el ahora la Directiva de notificación de correo no deseado **se bloquea al enviar un remitente porque al enviar la configuración de correo no deseado saliente** en la Directiva de correo no deseado de salida recibe notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a29b6-187">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="a29b6-188">**Restringir al usuario el envío de correo hasta el siguiente día**: este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a29b6-188">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="a29b6-189">Se envían notificaciones por correo electrónico y el usuario no podrá enviar más mensajes hasta el día siguiente, en función de la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="a29b6-189">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="a29b6-190">El administrador no tiene forma de reemplazar este bloque.</span><span class="sxs-lookup"><span data-stu-id="a29b6-190">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="a29b6-191">La alerta de actividad denominada **usuario restringido del envío de correo electrónico** notifica a los administradores (por correo electrónico y en la página **Ver alertas** ).</span><span class="sxs-lookup"><span data-stu-id="a29b6-191">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="a29b6-192">También se notifica a los destinatarios especificados en la directiva **notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado saliente** en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="a29b6-192">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="a29b6-193">El usuario no podrá enviar más mensajes hasta el día siguiente, en función de la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="a29b6-193">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="a29b6-194">El administrador no tiene forma de reemplazar este bloque.</span><span class="sxs-lookup"><span data-stu-id="a29b6-194">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="a29b6-195">**Restringir al usuario el envío de correo**: se envían notificaciones por correo electrónico, el usuario se agrega al portal **[Restricted users] <https://sip.protection.office.com/restrictedusers>** en el centro de seguridad & cumplimiento y el usuario no puede enviar correo electrónico hasta que un administrador lo elimine del portal de **usuarios restringidos** . Una vez que un administrador quita al usuario de la lista, el usuario no volverá a estar restringido para ese día.</span><span class="sxs-lookup"><span data-stu-id="a29b6-195">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="a29b6-196">Para obtener instrucciones, consulte [quitar un usuario del portal de usuarios restringidos después de enviar correo no deseado](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="a29b6-196">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="a29b6-197">**No se realiza ninguna acción, solo alerta**: se envían notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a29b6-197">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="a29b6-198">Opcional Expanda la sección **desvío automático** para controlar el reenvío automático de correo electrónico de los usuarios a remitentes externos.</span><span class="sxs-lookup"><span data-stu-id="a29b6-198">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="a29b6-199">Para obtener más información acerca del reenvío automático, consulte [configurar el reenvío de correo electrónico](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="a29b6-199">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="a29b6-200">Antes de septiembre de 2020, estas opciones están disponibles pero no se aplican.</span><span class="sxs-lookup"><span data-stu-id="a29b6-200">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="a29b6-201">Esta configuración solo se aplica a los buzones basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="a29b6-201">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="a29b6-202">Cuando el reenvío automático está deshabilitado, el destinatario recibirá un informe de no entrega (también conocido como un mensaje NDR o de devolución) si los remitentes externos envían correo electrónico a un buzón que se ha reenviado en su ubicación.</span><span class="sxs-lookup"><span data-stu-id="a29b6-202">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="a29b6-203">Si un remitente interno envía el correo electrónico, el remitente recibirá el NDR.</span><span class="sxs-lookup"><span data-stu-id="a29b6-203">If the email is sent by an internal sender, the sender will get the NDR.</span></span>

   <span data-ttu-id="a29b6-204">Los valores disponibles son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a29b6-204">The available values are:</span></span>

   - <span data-ttu-id="a29b6-205">**Sistema automático controlado**: permite el filtrado de correo no deseado saliente para controlar el reenvío automático de correo electrónico externo.</span><span class="sxs-lookup"><span data-stu-id="a29b6-205">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="a29b6-206">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a29b6-206">This is the default value.</span></span>
   - <span data-ttu-id="a29b6-207">**On**: la Directiva no deshabilita el reenvío de correo electrónico externo automático.</span><span class="sxs-lookup"><span data-stu-id="a29b6-207">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="a29b6-208">**Desactivado**: la Directiva deshabilita todo el reenvío de correo electrónico externo automático.</span><span class="sxs-lookup"><span data-stu-id="a29b6-208">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="a29b6-209">Necesarios Expanda la sección **aplicado a** para identificar los remitentes internos a los que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="a29b6-209">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="a29b6-210">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="a29b6-210">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="a29b6-211">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<sender1\>_ o _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="a29b6-211">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="a29b6-212">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<sender1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="a29b6-212">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="a29b6-213">Es más fácil hacer clic en **Agregar una condición** tres veces para ver todas las condiciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="a29b6-213">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="a29b6-214">Puede hacer clic en el ![botón Quitar](../../media/scc-remove-icon.png) para quitar condiciones que no quiera configurar.</span><span class="sxs-lookup"><span data-stu-id="a29b6-214">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="a29b6-215">**El dominio del remitente es**: especifica los remitentes en uno o varios de los dominios aceptados configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="a29b6-215">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="a29b6-216">Haga clic en el cuadro **Agregar una etiqueta** para ver y seleccionar un dominio.</span><span class="sxs-lookup"><span data-stu-id="a29b6-216">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="a29b6-217">Haga clic de nuevo en el cuadro **Agregar una etiqueta** para seleccionar dominios adicionales si hay más de un dominio disponible.</span><span class="sxs-lookup"><span data-stu-id="a29b6-217">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="a29b6-218">**Sender es**: especifica uno o más usuarios en la organización.</span><span class="sxs-lookup"><span data-stu-id="a29b6-218">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="a29b6-219">Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista.</span><span class="sxs-lookup"><span data-stu-id="a29b6-219">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="a29b6-220">Vuelva a hacer clic en el cuadro **Agregar una etiqueta** para seleccionar remitentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="a29b6-220">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="a29b6-221">**Sender es un miembro de**: especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="a29b6-221">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="a29b6-222">Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista.</span><span class="sxs-lookup"><span data-stu-id="a29b6-222">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="a29b6-223">Vuelva a hacer clic en el cuadro **Agregar una etiqueta** para seleccionar remitentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="a29b6-223">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="a29b6-224">**Excepto si**: para agregar excepciones para la regla, haga clic en **Agregar una condición** tres veces para ver todas las excepciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="a29b6-224">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="a29b6-225">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="a29b6-225">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="a29b6-226">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-226">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="a29b6-227">Usar el centro de seguridad & cumplimiento para ver las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-227">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="a29b6-228">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-228">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a29b6-229">En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir una directiva de correo no deseado saliente:</span><span class="sxs-lookup"><span data-stu-id="a29b6-229">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="a29b6-230">La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-230">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="a29b6-231">Una directiva personalizada creada donde el valor de la columna **tipo** es Directiva de **correo no deseado saliente personalizada**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-231">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="a29b6-232">La configuración de la Directiva se muestra en los detalles de la Directiva ampliada que aparecen, o bien puede hacer clic en **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-232">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="a29b6-233">Usar el centro de seguridad & cumplimiento para modificar las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-233">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="a29b6-234">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-234">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a29b6-235">En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir una directiva de correo no deseado saliente:</span><span class="sxs-lookup"><span data-stu-id="a29b6-235">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="a29b6-236">La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-236">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="a29b6-237">Una directiva personalizada creada donde el valor de la columna **tipo** es Directiva de **correo no deseado saliente personalizada**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-237">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="a29b6-238">Haga clic en **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-238">Click **Edit policy**.</span></span>

<span data-ttu-id="a29b6-239">Para directivas de correo no deseado personalizadas personalizadas, la configuración disponible en el control flotante que aparece es idéntica a la descrita en el [centro de seguridad & cumplimiento para crear directivas de correo no deseado saliente](#use-the-security--compliance-center-to-create-outbound-spam-policies) .</span><span class="sxs-lookup"><span data-stu-id="a29b6-239">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="a29b6-240">Para la Directiva de correo no deseado saliente predeterminada denominada **Directiva de filtro de correo no deseado saliente**, la sección **aplicado a** no está disponible (la Directiva se aplica a todos los usuarios) y no puede cambiar el nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="a29b6-240">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="a29b6-241">Vea las secciones siguientes para habilitar o deshabilitar una directiva, establecer el orden de prioridad de la directiva o configurar las notificaciones en cuarentena para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="a29b6-241">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="a29b6-242">Habilitar o deshabilitar las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-242">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="a29b6-243">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-243">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a29b6-244">En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir una directiva personalizada que haya creado (el valor en la columna **tipo** es **Directiva de correo no deseado saliente personalizada**).</span><span class="sxs-lookup"><span data-stu-id="a29b6-244">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="a29b6-245">En los detalles de la directiva expandida que aparecen, observe el valor de la columna **Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-245">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="a29b6-246">Mueva el botón de alternancia a la izquierda para deshabilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="a29b6-246">Move the toggle to the left to disable the policy:</span></span> ![Deshabilitar](../../media/scc-toggle-off.png)

   <span data-ttu-id="a29b6-248">Mueva el botón de alternancia a la derecha para habilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="a29b6-248">Move the toggle to the right to enable the policy:</span></span> ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="a29b6-250">No se puede deshabilitar la Directiva de correo no deseado saliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a29b6-250">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="a29b6-251">Establecer la prioridad de las directivas de correo no deseado saliente personalizadas</span><span class="sxs-lookup"><span data-stu-id="a29b6-251">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="a29b6-252">De forma predeterminada, las directivas de correo no deseado saliente tienen una prioridad que se basa en el orden en que se crearon (las nuevas directivas tienen una prioridad más baja que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="a29b6-252">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="a29b6-253">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="a29b6-253">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a29b6-254">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="a29b6-254">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a29b6-255">Las directivas de correo no deseado de salida personalizadas se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="a29b6-255">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="a29b6-256">La Directiva de correo no deseado saliente predeterminada denominada **Directiva de filtro de correo no deseado saliente** tiene el valor de prioridad **más bajo** y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="a29b6-256">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="a29b6-257">Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="a29b6-257">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="a29b6-258">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-258">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a29b6-259">En la página **configuración contra correo no deseado** , busque las directivas en las que el valor de la columna **tipo** es **Directiva de correo no deseado saliente personalizada**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-259">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="a29b6-260">Observe los valores de la columna **Prioridad**:</span><span class="sxs-lookup"><span data-stu-id="a29b6-260">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="a29b6-261">La directiva personalizada de correo no deseado saliente con la prioridad más alta tiene el ![ icono de flecha abajo de valor ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-261">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="a29b6-262">La directiva personalizada de correo no deseado saliente con la prioridad más baja tiene el ![ icono de flecha arriba de valor ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por ejemplo, ![ icono de flecha arriba ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="a29b6-262">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="a29b6-263">Si tiene tres o más directivas de correo no deseado saliente personalizadas, las directivas entre la prioridad más alta y la más baja tienen ![ un ](../../media/ITPro-EAC-UpArrowIcon.png)![ icono de flecha abajo hacia arriba ](../../media/ITPro-EAC-DownArrowIcon.png) (por ejemplo, **icono flecha** arriba en el icono ![ de ](../../media/ITPro-EAC-UpArrowIcon.png)![ flecha arriba ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="a29b6-263">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="a29b6-264">Haga clic en</span><span class="sxs-lookup"><span data-stu-id="a29b6-264">Click</span></span> ![Icono flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="a29b6-266">o</span><span class="sxs-lookup"><span data-stu-id="a29b6-266">or</span></span> ![Icono flecha abajo](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="a29b6-268">para mover la Directiva de correo no deseado saliente personalizada hacia arriba o hacia abajo en la lista de prioridades.</span><span class="sxs-lookup"><span data-stu-id="a29b6-268">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="a29b6-269">Usar el centro de seguridad & cumplimiento para eliminar directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-269">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="a29b6-270">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a29b6-271">En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir la directiva personalizada que desea eliminar (la columna **tipo** es **Directiva de correo no deseado saliente personalizada**).</span><span class="sxs-lookup"><span data-stu-id="a29b6-271">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="a29b6-272">En los detalles de la directiva expandida que aparecen, haga clic en **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-272">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="a29b6-273">Haga clic en **Sí** en el mensaje de advertencia que se muestra.</span><span class="sxs-lookup"><span data-stu-id="a29b6-273">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="a29b6-274">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a29b6-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="a29b6-275">Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-275">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="a29b6-276">Como se ha descrito anteriormente, una directiva de correo no deseado saliente consta de una directiva de filtro de correo no deseado saliente y una regla de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-276">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="a29b6-277">En Exchange Online PowerShell o en PowerShell independiente de EOP, la diferencia entre las directivas de filtro de correo no deseado saliente y las reglas de filtro de correo no deseado saliente es evidente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-277">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="a29b6-278">Puede administrar las directivas de filtro de correo no deseado saliente con los cmdlets **\* -HostedOutboundSpamFilterPolicy** y administrar las reglas de filtro de correo no deseado saliente con los cmdlets **\* -HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="a29b6-278">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="a29b6-279">En PowerShell, se crea la Directiva de filtro de correo no deseado saliente en primer lugar y, a continuación, se crea la regla de filtro de correo no deseado saliente que identifica la Directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="a29b6-279">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a29b6-280">En PowerShell, se modifica la configuración de la Directiva de filtro de correo no deseado saliente y de la regla de filtro de correo no deseado saliente por separado.</span><span class="sxs-lookup"><span data-stu-id="a29b6-280">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="a29b6-281">Cuando quita una directiva de filtro de correo no deseado saliente de PowerShell, la regla de filtro de correo no deseado saliente correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="a29b6-281">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="a29b6-282">Usar PowerShell para crear directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-282">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="a29b6-283">La creación de una directiva de correo no deseado saliente en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="a29b6-283">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a29b6-284">Crear la Directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-284">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="a29b6-285">Cree la regla de filtro de correo no deseado saliente que especifica la Directiva de filtro de correo no deseado saliente a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="a29b6-285">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="a29b6-286">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="a29b6-286">**Notes**:</span></span>

- <span data-ttu-id="a29b6-287">Puede crear una nueva regla de filtro de correo no deseado saliente y asignar una directiva de filtro de correo no deseado saliente existente que no esté asociada.</span><span class="sxs-lookup"><span data-stu-id="a29b6-287">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="a29b6-288">Una regla de filtro de correo no deseado saliente no se puede asociar con más de una directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-288">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="a29b6-289">Puede configurar las siguientes opciones en nuevas directivas de filtro de correo no deseado saliente en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:</span><span class="sxs-lookup"><span data-stu-id="a29b6-289">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="a29b6-290">Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="a29b6-290">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="a29b6-291">Establezca la prioridad de la Directiva durante la creación (_prioridad_ _\<Number\>_ ) en el cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="a29b6-291">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="a29b6-292">Una nueva Directiva de filtro de correo no deseado saliente que se crea en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que se asigna la Directiva a una regla de filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a29b6-292">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="a29b6-293">Paso 1: usar PowerShell para crear una directiva de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-293">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="a29b6-294">Para crear una directiva de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-294">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="a29b6-295">En este ejemplo se crea una nueva Directiva de filtro de correo no deseado saliente denominada ejecutivos de Contoso con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="a29b6-295">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="a29b6-296">Los límites de frecuencia de destinatarios están restringidos a valores más bajos que los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a29b6-296">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="a29b6-297">Para obtener más información, consulte [límites de envío en las opciones de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="a29b6-297">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="a29b6-298">Una vez que se alcanza uno de los límites, se impide el envío de mensajes al usuario.</span><span class="sxs-lookup"><span data-stu-id="a29b6-298">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="a29b6-299">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a29b6-299">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="a29b6-300">Paso 2: usar PowerShell para crear una regla de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-300">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="a29b6-301">Para crear una regla de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-301">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="a29b6-302">En este ejemplo se crea una nueva regla de filtro de correo no deseado saliente denominada ejecutivos de Contoso con esta configuración:</span><span class="sxs-lookup"><span data-stu-id="a29b6-302">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="a29b6-303">La Directiva de filtro de correo no deseado saliente denominada ejecutivos de Contoso está asociada a la regla.</span><span class="sxs-lookup"><span data-stu-id="a29b6-303">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="a29b6-304">La regla se aplica a los miembros del grupo denominado Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="a29b6-304">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="a29b6-305">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="a29b6-305">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="a29b6-306">Usar PowerShell para ver las directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-306">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="a29b6-307">Para obtener una lista resumida de todas las directivas de filtro de correo no deseado salientes, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="a29b6-307">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="a29b6-308">Para obtener información detallada sobre una directiva de filtro de correo no deseado específica, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-308">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="a29b6-309">En este ejemplo se devuelven todos los valores de propiedad de la Directiva de filtro de correo no deseado saliente denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="a29b6-309">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="a29b6-310">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a29b6-310">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="a29b6-311">Usar PowerShell para ver las reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-311">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="a29b6-312">Para ver las reglas de filtro de correo no deseado saliente existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-312">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="a29b6-313">Para obtener una lista resumida de todas las reglas de filtro de correo no deseado salientes, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="a29b6-313">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="a29b6-314">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="a29b6-314">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="a29b6-315">Para obtener información detallada sobre una regla de filtrado de correo no deseado específica, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-315">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="a29b6-316">En este ejemplo se devuelven todos los valores de propiedad de la regla de filtro de correo no deseado saliente denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="a29b6-316">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="a29b6-317">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="a29b6-317">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="a29b6-318">Usar PowerShell para modificar las directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-318">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="a29b6-319">La misma configuración está disponible cuando modifica una directiva de filtro de malware en PowerShell como cuando crea la Directiva tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva de filtro de correo no deseado saliente](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="a29b6-319">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="a29b6-320">No se puede cambiar el nombre de una directiva de filtro de correo no deseado saliente (el cmdlet **set-HostedOutboundSpamFilterPolicy** no tiene ningún parámetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="a29b6-320">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a29b6-321">Al cambiar el nombre de una directiva de correo no deseado saliente en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_ de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-321">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="a29b6-322">Para modificar una directiva de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-322">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a29b6-323">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a29b6-323">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="a29b6-324">Usar PowerShell para modificar las reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-324">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="a29b6-325">El único valor que no está disponible cuando se modifica una regla de filtro de correo no deseado saliente en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a29b6-325">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a29b6-326">Para habilitar o deshabilitar las reglas de filtro de correo no deseado saliente existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="a29b6-326">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="a29b6-327">De lo contrario, no hay opciones de configuración adicionales disponibles cuando se modifica una regla de filtro de correo no deseado saliente en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a29b6-327">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="a29b6-328">La misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla de filtro de correo no deseado saliente](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="a29b6-328">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="a29b6-329">Para modificar una regla de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-329">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a29b6-330">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="a29b6-330">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="a29b6-331">Usar PowerShell para habilitar o deshabilitar reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-331">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="a29b6-332">La habilitación o deshabilitación de una regla de filtro de correo no deseado saliente en PowerShell habilita o deshabilita toda la Directiva de correo no deseado saliente (la regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asignada).</span><span class="sxs-lookup"><span data-stu-id="a29b6-332">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="a29b6-333">No se puede habilitar o deshabilitar la Directiva de correo no deseado saliente predeterminada (siempre se aplica siempre a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="a29b6-333">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="a29b6-334">Para habilitar o deshabilitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-334">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="a29b6-335">En este ejemplo se deshabilita la regla de filtro de correo no deseado saliente denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="a29b6-335">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="a29b6-336">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="a29b6-336">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="a29b6-337">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) y [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="a29b6-337">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="a29b6-338">Usar PowerShell para establecer la prioridad de las reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-338">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="a29b6-339">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="a29b6-339">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="a29b6-340">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="a29b6-340">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="a29b6-341">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="a29b6-341">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="a29b6-342">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="a29b6-342">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="a29b6-343">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="a29b6-343">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a29b6-344">Para establecer la prioridad de una regla de filtro de correo no deseado saliente en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-344">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a29b6-345">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="a29b6-345">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="a29b6-346">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="a29b6-346">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="a29b6-347">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-HostedOutboundSpamFilterRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a29b6-347">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="a29b6-348">La Directiva de filtro de correo no deseado predeterminado saliente no tiene una regla de filtro de correo no deseado correspondiente y siempre tiene el valor de prioridad no modificable **más bajo**.</span><span class="sxs-lookup"><span data-stu-id="a29b6-348">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="a29b6-349">Usar PowerShell para quitar las directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-349">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="a29b6-350">Cuando se usa PowerShell para quitar una directiva de filtro de correo no deseado saliente, no se quita la regla de filtro de correo no deseado saliente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-350">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="a29b6-351">Para quitar una directiva de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-351">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a29b6-352">En este ejemplo se quita la Directiva de filtro de correo no deseado saliente denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="a29b6-352">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a29b6-353">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a29b6-353">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="a29b6-354">Usar PowerShell para quitar reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="a29b6-354">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="a29b6-355">Cuando se usa PowerShell para quitar una regla de filtro de correo no deseado saliente, no se elimina la Directiva de filtro de correo no deseado saliente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a29b6-355">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="a29b6-356">Para quitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a29b6-356">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="a29b6-357">En este ejemplo se quita la regla de filtro de correo no deseado saliente denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="a29b6-357">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="a29b6-358">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="a29b6-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a29b6-359">Más información</span><span class="sxs-lookup"><span data-stu-id="a29b6-359">For more information</span></span>

[<span data-ttu-id="a29b6-360">Quitar usuarios bloqueados del portal de Usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="a29b6-360">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="a29b6-361">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="a29b6-361">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="a29b6-362">Preguntas más frecuentes sobre la protección contra correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="a29b6-362">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="a29b6-363">Informe de mensajes reenviados automáticamente</span><span class="sxs-lookup"><span data-stu-id="a29b6-363">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
