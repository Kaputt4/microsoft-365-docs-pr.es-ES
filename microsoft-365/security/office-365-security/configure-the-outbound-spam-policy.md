---
title: Configurar el filtrado de spam de salida
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a configurar directivas de correo no deseado saliente que se aplican a usuarios, grupos o dominios específicos de la organización.
ms.openlocfilehash: efd3fecc2447435f40e4e20fd958e8f3b2d8e48f
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173445"
---
# <a name="configure-outbound-spam-filtering"></a><span data-ttu-id="3f827-103">Configurar el filtrado de spam de salida</span><span class="sxs-lookup"><span data-stu-id="3f827-103">Configure outbound spam filtering</span></span>

<span data-ttu-id="3f827-104">Si es un cliente de Microsoft 365 con buzones en Exchange online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes de correo electrónico salientes que se envían a través de EOP se comprueban automáticamente en busca de correo no deseado y actividad de envío inusual.</span><span class="sxs-lookup"><span data-stu-id="3f827-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="3f827-105">Normalmente, el correo no deseado saliente de un usuario de la organización indica una cuenta en peligro.</span><span class="sxs-lookup"><span data-stu-id="3f827-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="3f827-106">Los mensajes sospechosos se marcan como correo no deseado (independientemente del nivel de confianza de correo no deseado o de SCL) y se enrutan a través del [grupo de entrega de alto riesgo](high-risk-delivery-pool-for-outbound-messages.md) para ayudar a proteger la reputación del servicio (es decir, mantenga los servidores de correo electrónico de origen de Microsoft 365 en las listas de direcciones IP bloqueadas).</span><span class="sxs-lookup"><span data-stu-id="3f827-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="3f827-107">Los administradores reciben automáticamente una notificación de la actividad de correo electrónico saliente y de los usuarios bloqueados mediante [directivas de alerta](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3f827-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="3f827-108">EOP usa directivas de correo no deseado salientes como parte de la defensa general de la organización contra el correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="3f827-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="3f827-109">Para obtener más información, consulte [Protección contra correo no deseado](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="3f827-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="3f827-110">Los administradores pueden ver, editar y configurar (pero no eliminar) la Directiva de correo no deseado saliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f827-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="3f827-111">Para una mayor granularidad, también puede crear directivas de correo no deseado saliente personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="3f827-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="3f827-112">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="3f827-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="3f827-113">Puede configurar directivas de correo no deseado salientes en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para los clientes de Microsoft 365; Exchange Online Protection PowerShell para clientes independientes de EOP).</span><span class="sxs-lookup"><span data-stu-id="3f827-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="3f827-114">Directivas de correo no deseado salientes en el centro de seguridad & cumplimiento vs Exchange Online PowerShell o Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f827-114">Outbound spam policies in the Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="3f827-115">Los elementos básicos de una directiva de correo no deseado saliente en EOP son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f827-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="3f827-116">**La Directiva de filtro de correo no deseado saliente**: especifica las acciones para los veredictos de filtrado de correo no deseado saliente y las opciones de notificación.</span><span class="sxs-lookup"><span data-stu-id="3f827-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="3f827-117">**La regla de filtro de correo no deseado saliente**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva) para una directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="3f827-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="3f827-118">La diferencia entre estos dos elementos no es obvia cuando se administran las directivas de correo no deseado saliente en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="3f827-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="3f827-119">Cuando se crea una directiva de correo no deseado saliente en el centro de seguridad & cumplimiento, en realidad se crea una regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="3f827-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="3f827-120">Cuando se modifica una directiva de correo no deseado saliente en el centro de seguridad & cumplimiento, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado y destinatarios modifica la regla de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="3f827-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="3f827-121">Todas las demás opciones modifican la Directiva de filtro de correo no deseado saliente asociada.</span><span class="sxs-lookup"><span data-stu-id="3f827-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="3f827-122">Cuando quita una directiva de correo no deseado saliente del centro de seguridad & cumplimiento, se quita la regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asociada.</span><span class="sxs-lookup"><span data-stu-id="3f827-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="3f827-123">En Exchange Online PowerShell o PowerShell independiente de Exchange Online Protection, la diferencia entre las directivas de filtro de correo no deseado saliente y las reglas de filtro de correo no deseado saliente es evidente.</span><span class="sxs-lookup"><span data-stu-id="3f827-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="3f827-124">Puede administrar las directivas \*\* \*de filtro de\*\* correo no deseado saliente con los cmdlets-HostedOutboundSpamFilterPolicy y administrar las reglas de filtro de correo no deseado saliente con los \*\* \*cmdlets-HostedOutboundSpamFilterRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="3f827-124">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="3f827-125">En PowerShell, se crea la Directiva de filtro de correo no deseado saliente en primer lugar y, a continuación, se crea la regla de filtro de correo no deseado saliente que identifica la Directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="3f827-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="3f827-126">En PowerShell, se modifica la configuración de la Directiva de filtro de correo no deseado saliente y de la regla de filtro de correo no deseado saliente por separado.</span><span class="sxs-lookup"><span data-stu-id="3f827-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="3f827-127">Cuando quita una directiva de filtro de correo no deseado saliente de PowerShell, la regla de filtro de correo no deseado saliente correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="3f827-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="3f827-128">Directiva de correo no deseado saliente predeterminada</span><span class="sxs-lookup"><span data-stu-id="3f827-128">Default outbound spam policy</span></span>

<span data-ttu-id="3f827-129">Cada organización tiene integrada una directiva de correo no deseado saliente denominada predeterminada que tiene estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="3f827-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="3f827-130">La Directiva de filtro de correo no deseado saliente denominada predeterminada se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla de filtro de correo no deseado saliente (filtros de destinatario) asociada a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="3f827-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="3f827-131">La directiva denominada Predeterminada tiene un valor de prioridad personalizado **Inferior** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="3f827-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="3f827-132">Las directivas personalizadas que cree siempre tendrán una prioridad mayor que la directiva denominada Predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f827-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="3f827-133">La directiva denominada Predeterminada es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f827-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="3f827-134">Para aumentar la eficacia del filtrado de correo no deseado saliente, puede crear directivas de correo no deseado saliente personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="3f827-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3f827-135">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="3f827-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3f827-136">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3f827-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3f827-137">Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="3f827-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="3f827-138">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3f827-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3f827-139">Para conectarse a Exchange Online Protection PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="3f827-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3f827-140">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="3f827-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="3f827-141">Para agregar, modificar y eliminar directivas de correo no deseado saliente, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="3f827-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="3f827-142">Para el acceso de solo lectura a las directivas de correo no deseado saliente, debe ser miembro del grupo de roles **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="3f827-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="3f827-143">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3f827-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="3f827-144">Para conocer la configuración recomendada para las directivas de correo no deseado saliente, consulte [EOP Outbound Spam Filter Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="3f827-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="3f827-145">Las [directivas de alerta](../../compliance/alert-policies.md) predeterminadas denominadas límite de envío de **correo electrónico superado**, los **patrones de envío de correo electrónico sospechoso detectados**y el **usuario restringido del envío de correo electrónico** ya envían notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**global Admins**) sobre la actividad de correo electrónico saliente y los usuarios bloqueados debido a correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="3f827-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="3f827-146">Para obtener más información, consulte [Verify The Alert Settings for Restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="3f827-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="3f827-147">Se recomienda usar estas directivas de alerta en lugar de las opciones de notificación en las directivas de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="3f827-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="3f827-148">Usar el centro de seguridad & cumplimiento para crear directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="3f827-149">La creación de una directiva personalizada de correo no deseado saliente en el centro de seguridad & cumplimiento crea la regla de filtro de correo no deseado y la Directiva de filtro de correo no deseado asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="3f827-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="3f827-150">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="3f827-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3f827-151">En la página **configuración contra correo no deseado** , haga clic en **crear una directiva de salida**.</span><span class="sxs-lookup"><span data-stu-id="3f827-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="3f827-152">En la **Directiva de filtro de correo no deseado saliente** , vaya hacia fuera que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3f827-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="3f827-153">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="3f827-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="3f827-154">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="3f827-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="3f827-155">Opcional Expanda la sección **notificaciones** para configurar usuarios adicionales que deben recibir copias y notificaciones de mensajes de correo electrónico salientes sospechosos:</span><span class="sxs-lookup"><span data-stu-id="3f827-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="3f827-156">**Enviar una copia de los mensajes de correo electrónico saliente sospechosos a personas específicas**: esta opción agrega los usuarios especificados como destinatarios en copia oculta a los mensajes sospechosos de salida.</span><span class="sxs-lookup"><span data-stu-id="3f827-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="3f827-157">Para habilitar esta opción:</span><span class="sxs-lookup"><span data-stu-id="3f827-157">To enable this setting:</span></span>

     <span data-ttu-id="3f827-158">a.</span><span class="sxs-lookup"><span data-stu-id="3f827-158">a.</span></span> <span data-ttu-id="3f827-159">Active la casilla para habilitar la configuración.</span><span class="sxs-lookup"><span data-stu-id="3f827-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="3f827-160">b.</span><span class="sxs-lookup"><span data-stu-id="3f827-160">b.</span></span> <span data-ttu-id="3f827-161">Haga clic en **Agregar personas**.</span><span class="sxs-lookup"><span data-stu-id="3f827-161">Click **Add people**.</span></span> <span data-ttu-id="3f827-162">En el control flotante **Agregar o quitar destinatarios** que aparece:</span><span class="sxs-lookup"><span data-stu-id="3f827-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="3f827-163">c.</span><span class="sxs-lookup"><span data-stu-id="3f827-163">c.</span></span> <span data-ttu-id="3f827-164">Escriba la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="3f827-164">Enter the sender's email address.</span></span> <span data-ttu-id="3f827-165">Puede especificar varias direcciones de correo electrónico separadas por punto y coma (;) o un destinatario por línea.</span><span class="sxs-lookup"><span data-stu-id="3f827-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="3f827-166">d.</span><span class="sxs-lookup"><span data-stu-id="3f827-166">d.</span></span> <span data-ttu-id="3f827-167">Haga clic en</span><span class="sxs-lookup"><span data-stu-id="3f827-167">Click</span></span> ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="3f827-169">para agregar los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="3f827-169">to add the recipients.</span></span>

        <span data-ttu-id="3f827-170">Repita estos pasos tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3f827-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="3f827-171">Los destinatarios que ha agregado aparecen en la sección **lista de destinatarios** en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="3f827-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="3f827-172">Para eliminar un destinatario, haga ![clic en](../../media/scc-remove-icon.png)el botón Quitar.</span><span class="sxs-lookup"><span data-stu-id="3f827-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="3f827-173">e.</span><span class="sxs-lookup"><span data-stu-id="3f827-173">e.</span></span> <span data-ttu-id="3f827-174">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f827-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="3f827-175">Para deshabilitar esta opción, desactive la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="3f827-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="3f827-176">**Notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado saliente**:</span><span class="sxs-lookup"><span data-stu-id="3f827-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="3f827-177">La [Directiva de alerta](../../compliance/alert-policies.md) predeterminada denominada **usuario restringido del envío de correo electrónico** ya envía notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**administradores globales**) cuando los usuarios se bloquean debido a que superan los límites de la sección **límites de destinatarios** .</span><span class="sxs-lookup"><span data-stu-id="3f827-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="3f827-178">Le recomendamos que use la Directiva de alertas en lugar de esta opción en la Directiva de correo no deseado saliente para notificar a los administradores y a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="3f827-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="3f827-179">Para obtener instrucciones, consulte [Verify The Alert Settings for Restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="3f827-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="3f827-180">Para habilitar esta opción:</span><span class="sxs-lookup"><span data-stu-id="3f827-180">To enable this setting:</span></span>

     <span data-ttu-id="3f827-181">a.</span><span class="sxs-lookup"><span data-stu-id="3f827-181">a.</span></span> <span data-ttu-id="3f827-182">Active la casilla para habilitar la configuración.</span><span class="sxs-lookup"><span data-stu-id="3f827-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="3f827-183">b.</span><span class="sxs-lookup"><span data-stu-id="3f827-183">b.</span></span> <span data-ttu-id="3f827-184">Haga clic en **Agregar personas**.</span><span class="sxs-lookup"><span data-stu-id="3f827-184">Click **Add people**.</span></span> <span data-ttu-id="3f827-185">En el control flotante **Agregar o quitar destinatarios** que aparece:</span><span class="sxs-lookup"><span data-stu-id="3f827-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="3f827-186">c.</span><span class="sxs-lookup"><span data-stu-id="3f827-186">c.</span></span> <span data-ttu-id="3f827-187">Escriba la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="3f827-187">Enter the sender's email address.</span></span> <span data-ttu-id="3f827-188">Puede especificar varias direcciones de correo electrónico separadas por punto y coma (;) o un destinatario por línea.</span><span class="sxs-lookup"><span data-stu-id="3f827-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="3f827-189">d.</span><span class="sxs-lookup"><span data-stu-id="3f827-189">d.</span></span> <span data-ttu-id="3f827-190">Haga clic en</span><span class="sxs-lookup"><span data-stu-id="3f827-190">Click</span></span> ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="3f827-192">para agregar los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="3f827-192">to add the recipients.</span></span>

        <span data-ttu-id="3f827-193">Repita estos pasos tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3f827-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="3f827-194">Los destinatarios que ha agregado aparecen en la sección **lista de destinatarios** en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="3f827-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="3f827-195">Para eliminar un destinatario, haga ![clic en](../../media/scc-remove-icon.png)el botón Quitar.</span><span class="sxs-lookup"><span data-stu-id="3f827-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="3f827-196">e.</span><span class="sxs-lookup"><span data-stu-id="3f827-196">e.</span></span> <span data-ttu-id="3f827-197">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f827-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="3f827-198">Para deshabilitar esta opción, desactive la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="3f827-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="3f827-199">Opcional Expanda la sección **límites de destinatarios** para configurar los límites y las acciones de los mensajes de correo electrónico saliente sospechosos:</span><span class="sxs-lookup"><span data-stu-id="3f827-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="3f827-200">Esta configuración solo se aplica a los buzones basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="3f827-200">These settings are only applicable to cloud-based mailboxes.</span></span>
     
   - <span data-ttu-id="3f827-201">**Número máximo de destinatarios por usuario**</span><span class="sxs-lookup"><span data-stu-id="3f827-201">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="3f827-202">Un valor válido es de 0 a 10000.</span><span class="sxs-lookup"><span data-stu-id="3f827-202">A valid value is 0 to 10000.</span></span> <span data-ttu-id="3f827-203">El valor predeterminado es 0, lo que significa que se usan los valores predeterminados del servicio.</span><span class="sxs-lookup"><span data-stu-id="3f827-203">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="3f827-204">Para obtener más información, consulte [límites de envío en las opciones de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="3f827-204">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="3f827-205">**Límite horario externo**: el número máximo de destinatarios externos por hora.</span><span class="sxs-lookup"><span data-stu-id="3f827-205">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="3f827-206">**Límite horario interno**: el número máximo de destinatarios internos por hora.</span><span class="sxs-lookup"><span data-stu-id="3f827-206">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="3f827-207">**Límite diario**: número máximo total de destinatarios por día.</span><span class="sxs-lookup"><span data-stu-id="3f827-207">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="3f827-208">**Acción cuando un usuario supera los límites anteriores**: configure la acción que se llevará a cabo cuando se supere alguno de los **límites de destinatarios** .</span><span class="sxs-lookup"><span data-stu-id="3f827-208">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="3f827-209">Para todas las acciones, los destinatarios especificados en el **usuario restringió el envío de la Directiva de alerta de correo electrónico** (y en el ahora la Directiva de notificación de correo no deseado **se bloquea al enviar un remitente porque al enviar la configuración de correo no deseado saliente** en la Directiva de correo no deseado de salida recibe notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3f827-209">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="3f827-210">**Restringir al usuario el envío de correo hasta el siguiente día**: este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3f827-210">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="3f827-211">Se envían notificaciones por correo electrónico y el usuario no podrá enviar más mensajes hasta el día siguiente, en función de la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="3f827-211">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="3f827-212">El administrador no tiene forma de reemplazar este bloque.</span><span class="sxs-lookup"><span data-stu-id="3f827-212">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="3f827-213">La alerta de actividad denominada **usuario restringido del envío de correo electrónico** notifica a los administradores (por correo electrónico y en la página **Ver alertas** ).</span><span class="sxs-lookup"><span data-stu-id="3f827-213">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="3f827-214">También se notifica a los destinatarios especificados en la directiva **notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado saliente** en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="3f827-214">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="3f827-215">El usuario no podrá enviar más mensajes hasta el día siguiente, en función de la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="3f827-215">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="3f827-216">El administrador no tiene forma de reemplazar este bloque.</span><span class="sxs-lookup"><span data-stu-id="3f827-216">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="3f827-217">**Restringir al usuario el envío de correo**: se envían notificaciones por correo electrónico, el usuario se agrega al portal \*\*[Restricted users]<https://sip.protection.office.com/restrictedusers> \*\* en el centro de seguridad & cumplimiento y el usuario no puede enviar correo electrónico hasta que un administrador lo elimine del portal de **usuarios restringidos** . Una vez que un administrador quita al usuario de la lista, el usuario no volverá a estar restringido para ese día.</span><span class="sxs-lookup"><span data-stu-id="3f827-217">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="3f827-218">Para obtener instrucciones, consulte [quitar un usuario del portal de usuarios restringidos después de enviar correo no deseado](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="3f827-218">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="3f827-219">**No se realiza ninguna acción, solo alerta**: se envían notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3f827-219">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="3f827-220">Necesarios Expanda la sección **aplicado a** para identificar los remitentes internos a los que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="3f827-220">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="3f827-221">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="3f827-221">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="3f827-222">Varios valores de la misma condición o del uso o la lógica de la excepción (por ejemplo, _ \<sender1\> _ o _ \<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="3f827-222">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="3f827-223">Las diferentes condiciones o excepciones usan la lógica (por ejemplo _ \<,\> sender1_ y _ \<el miembro del\>Grupo 1_).</span><span class="sxs-lookup"><span data-stu-id="3f827-223">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="3f827-224">Es más fácil hacer clic en **Agregar una condición** tres veces para ver todas las condiciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="3f827-224">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="3f827-225">Puede hacer clic en el ![botón Quitar](../../media/scc-remove-icon.png) para quitar condiciones que no quiera configurar.</span><span class="sxs-lookup"><span data-stu-id="3f827-225">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="3f827-226">**El dominio del remitente es**: especifica los remitentes en uno o varios de los dominios aceptados configurados en Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f827-226">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="3f827-227">Haga clic en el cuadro **Agregar una etiqueta** para ver y seleccionar un dominio.</span><span class="sxs-lookup"><span data-stu-id="3f827-227">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="3f827-228">Haga clic de nuevo en el cuadro **Agregar una etiqueta** para seleccionar dominios adicionales si hay más de un dominio disponible.</span><span class="sxs-lookup"><span data-stu-id="3f827-228">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="3f827-229">**Sender es**: especifica uno o más usuarios en la organización.</span><span class="sxs-lookup"><span data-stu-id="3f827-229">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="3f827-230">Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista.</span><span class="sxs-lookup"><span data-stu-id="3f827-230">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="3f827-231">Vuelva a hacer clic en el cuadro **Agregar una etiqueta** para seleccionar remitentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="3f827-231">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="3f827-232">**Sender es un miembro de**: especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="3f827-232">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="3f827-233">Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista.</span><span class="sxs-lookup"><span data-stu-id="3f827-233">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="3f827-234">Vuelva a hacer clic en el cuadro **Agregar una etiqueta** para seleccionar remitentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="3f827-234">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="3f827-235">**Excepto si**: para agregar excepciones para la regla, haga clic en **Agregar una condición** tres veces para ver todas las excepciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="3f827-235">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="3f827-236">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="3f827-236">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="3f827-237">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f827-237">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="3f827-238">Usar el centro de seguridad & cumplimiento para ver las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-238">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="3f827-239">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="3f827-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3f827-240">En la página **configuración contra correo no deseado** , ![haga clic](../../media/scc-expand-icon.png) en expandir icono para expandir una directiva de correo no deseado saliente:</span><span class="sxs-lookup"><span data-stu-id="3f827-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="3f827-241">La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.</span><span class="sxs-lookup"><span data-stu-id="3f827-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="3f827-242">Una directiva personalizada creada donde el valor de la columna **tipo** es Directiva de **correo no deseado saliente personalizada**.</span><span class="sxs-lookup"><span data-stu-id="3f827-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="3f827-243">La configuración de la Directiva se muestra en los detalles de la Directiva ampliada que aparecen, o bien puede hacer clic en **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="3f827-243">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="3f827-244">Usar el centro de seguridad & cumplimiento para modificar las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-244">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="3f827-245">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="3f827-245">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3f827-246">En la página **configuración contra correo no deseado** , ![haga clic](../../media/scc-expand-icon.png) en expandir icono para expandir una directiva de correo no deseado saliente:</span><span class="sxs-lookup"><span data-stu-id="3f827-246">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="3f827-247">La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.</span><span class="sxs-lookup"><span data-stu-id="3f827-247">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="3f827-248">Una directiva personalizada creada donde el valor de la columna **tipo** es Directiva de **correo no deseado saliente personalizada**.</span><span class="sxs-lookup"><span data-stu-id="3f827-248">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="3f827-249">Haga clic en **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="3f827-249">Click **Edit policy**.</span></span>

<span data-ttu-id="3f827-250">Para directivas de correo no deseado personalizadas personalizadas, la configuración disponible en el control flotante que aparece es idéntica a la descrita en el [centro de seguridad & cumplimiento para crear directivas de correo no deseado saliente](#use-the-security--compliance-center-to-create-outbound-spam-policies) .</span><span class="sxs-lookup"><span data-stu-id="3f827-250">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="3f827-251">Para la Directiva de correo no deseado saliente predeterminada denominada **Directiva de filtro de correo no deseado saliente**, la sección **aplicado a** no está disponible (la Directiva se aplica a todos los usuarios) y no puede cambiar el nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="3f827-251">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="3f827-252">Vea las secciones siguientes para habilitar o deshabilitar una directiva, establecer el orden de prioridad de la directiva o configurar las notificaciones en cuarentena para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="3f827-252">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="3f827-253">Habilitar o deshabilitar las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-253">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="3f827-254">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="3f827-254">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3f827-255">En la **página Configuración contra correo no deseado** , ![haga clic](../../media/scc-expand-icon.png) en expandir icono para expandir una directiva personalizada que haya creado (el valor en la columna **tipo** es **Directiva de correo no deseado saliente personalizada**).</span><span class="sxs-lookup"><span data-stu-id="3f827-255">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="3f827-256">En los detalles de la directiva expandida que aparecen, observe el valor de la columna **Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="3f827-256">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="3f827-257">Mueva el botón de alternancia a la izquierda para deshabilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="3f827-257">Move the toggle to the left to disable the policy:</span></span> ![Deshabilitar](../../media/scc-toggle-off.png)

   <span data-ttu-id="3f827-259">Mueva el botón de alternancia a la derecha para habilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="3f827-259">Move the toggle to the right to enable the policy:</span></span> ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="3f827-261">No se puede deshabilitar la Directiva de correo no deseado saliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f827-261">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="3f827-262">Establecer la prioridad de las directivas de correo no deseado saliente personalizadas</span><span class="sxs-lookup"><span data-stu-id="3f827-262">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="3f827-263">De forma predeterminada, las directivas de correo no deseado saliente tienen una prioridad que se basa en el orden en que se crearon (las nuevas directivas tienen una prioridad más baja que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="3f827-263">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="3f827-264">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="3f827-264">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="3f827-265">Dos directivas no pueden tener la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="3f827-265">No two policies can have the same priority.</span></span>

<span data-ttu-id="3f827-266">Las directivas de correo no deseado de salida personalizadas se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="3f827-266">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="3f827-267">La Directiva de correo no deseado saliente predeterminada denominada **Directiva de filtro de correo no deseado saliente** tiene el valor de prioridad **más bajo**y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="3f827-267">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="3f827-268">Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="3f827-268">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="3f827-269">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="3f827-269">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3f827-270">En la página **configuración contra correo no deseado** , busque las directivas en las que el valor de la columna **tipo** es **Directiva de correo no deseado saliente personalizada**.</span><span class="sxs-lookup"><span data-stu-id="3f827-270">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="3f827-271">Observe los valores de la columna **Prioridad**:</span><span class="sxs-lookup"><span data-stu-id="3f827-271">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="3f827-272">La directiva personalizada de correo no deseado saliente con la prioridad más alta ![tiene el icono](../../media/ITPro-EAC-DownArrowIcon.png) de flecha abajo de valor **0**.</span><span class="sxs-lookup"><span data-stu-id="3f827-272">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="3f827-273">La directiva personalizada de correo no deseado saliente con la prioridad más baja ![tiene el icono](../../media/ITPro-EAC-UpArrowIcon.png) de flecha arriba de valor ![ **n** (por](../../media/ITPro-EAC-UpArrowIcon.png) ejemplo, icono de flecha arriba **3**).</span><span class="sxs-lookup"><span data-stu-id="3f827-273">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="3f827-274">Si tiene tres o más directivas de correo no deseado saliente personalizadas, las directivas entre la prioridad más alta y la ![más baja tienen](../../media/ITPro-EAC-UpArrowIcon.png)![un icono](../../media/ITPro-EAC-DownArrowIcon.png) de flecha abajo hacia arriba ( ![por ejemplo,](../../media/ITPro-EAC-UpArrowIcon.png)![icono flecha arriba](../../media/ITPro-EAC-DownArrowIcon.png) en el icono de flecha arriba **2**). **n**</span><span class="sxs-lookup"><span data-stu-id="3f827-274">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="3f827-275">Haga clic en</span><span class="sxs-lookup"><span data-stu-id="3f827-275">Click</span></span> ![Icono flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="3f827-277">o</span><span class="sxs-lookup"><span data-stu-id="3f827-277">or</span></span> ![Icono flecha abajo](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="3f827-279">para mover la Directiva de correo no deseado saliente personalizada hacia arriba o hacia abajo en la lista de prioridades.</span><span class="sxs-lookup"><span data-stu-id="3f827-279">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="3f827-280">Usar el centro de seguridad & cumplimiento para eliminar directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-280">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="3f827-281">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="3f827-281">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3f827-282">En la **página Configuración contra correo no deseado** , ![haga clic](../../media/scc-expand-icon.png) en expandir icono para expandir la directiva personalizada que desea eliminar (la columna **tipo** es **Directiva de correo no deseado saliente personalizada**).</span><span class="sxs-lookup"><span data-stu-id="3f827-282">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="3f827-283">En los detalles de la directiva expandida que aparecen, haga clic en **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="3f827-283">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="3f827-284">Haga clic en **Sí** en el mensaje de advertencia que se muestra.</span><span class="sxs-lookup"><span data-stu-id="3f827-284">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="3f827-285">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f827-285">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="3f827-286">Usar Exchange Online PowerShell o Exchange Online Protection PowerShell para configurar las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-286">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="3f827-287">Usar PowerShell para crear directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="3f827-288">La creación de una directiva de correo no deseado saliente en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="3f827-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="3f827-289">Crear la Directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="3f827-289">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="3f827-290">Cree la regla de filtro de correo no deseado saliente que especifica la Directiva de filtro de correo no deseado saliente a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="3f827-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="3f827-291">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="3f827-291">**Notes**:</span></span>

- <span data-ttu-id="3f827-292">Puede crear una nueva regla de filtro de correo no deseado saliente y asignar una directiva de filtro de correo no deseado saliente existente que no esté asociada.</span><span class="sxs-lookup"><span data-stu-id="3f827-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="3f827-293">Una regla de filtro de correo no deseado saliente no se puede asociar con más de una directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="3f827-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="3f827-294">Puede configurar las siguientes opciones en nuevas directivas de filtro de correo no deseado saliente en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:</span><span class="sxs-lookup"><span data-stu-id="3f827-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="3f827-295">Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="3f827-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="3f827-296">Establezca la prioridad de la Directiva durante la creación ( _ \<número\>_ de_prioridad_ ) en el cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="3f827-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="3f827-297">Una nueva Directiva de filtro de correo no deseado saliente que se crea en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que se asigna la Directiva a una regla de filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="3f827-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="3f827-298">Paso 1: usar PowerShell para crear una directiva de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="3f827-299">Para crear una directiva de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="3f827-300">En este ejemplo se crea una nueva Directiva de filtro de correo no deseado saliente denominada ejecutivos de Contoso con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="3f827-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="3f827-301">Los límites de frecuencia de destinatarios están restringidos a valores más bajos que los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3f827-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="3f827-302">Para obtener más información, consulte [límites de envío en las opciones de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="3f827-302">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="3f827-303">Una vez que se alcanza uno de los límites, se impide el envío de mensajes al usuario.</span><span class="sxs-lookup"><span data-stu-id="3f827-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="3f827-304">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3f827-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="3f827-305">Paso 2: usar PowerShell para crear una regla de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="3f827-306">Para crear una regla de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="3f827-307">En este ejemplo se crea una nueva regla de filtro de correo no deseado saliente denominada ejecutivos de Contoso con esta configuración:</span><span class="sxs-lookup"><span data-stu-id="3f827-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="3f827-308">La Directiva de filtro de correo no deseado saliente denominada ejecutivos de Contoso está asociada a la regla.</span><span class="sxs-lookup"><span data-stu-id="3f827-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="3f827-309">La regla se aplica a los miembros del grupo denominado Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="3f827-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="3f827-310">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3f827-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="3f827-311">Usar PowerShell para ver las directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="3f827-312">Para obtener una lista resumida de todas las directivas de filtro de correo no deseado salientes, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="3f827-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="3f827-313">Para obtener información detallada sobre una directiva de filtro de correo no deseado específica, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="3f827-314">En este ejemplo se devuelven todos los valores de propiedad de la Directiva de filtro de correo no deseado saliente denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="3f827-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="3f827-315">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3f827-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="3f827-316">Usar PowerShell para ver las reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="3f827-317">Para ver las reglas de filtro de correo no deseado saliente existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="3f827-318">Para obtener una lista resumida de todas las reglas de filtro de correo no deseado salientes, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="3f827-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="3f827-319">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="3f827-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="3f827-320">Para obtener información detallada sobre una regla de filtrado de correo no deseado específica, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="3f827-321">En este ejemplo se devuelven todos los valores de propiedad de la regla de filtro de correo no deseado saliente denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="3f827-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="3f827-322">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3f827-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="3f827-323">Usar PowerShell para modificar las directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="3f827-324">La misma configuración está disponible cuando modifica una directiva de filtro de malware en PowerShell como cuando crea la Directiva tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva de filtro de correo no deseado saliente](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="3f827-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="3f827-325">**Nota**: no puede cambiar el nombre de una directiva de filtro de correo no deseado saliente (el cmdlet **set-HostedOutboundSpamFilterPolicy** no tiene ningún parámetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="3f827-325">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="3f827-326">Al cambiar el nombre de una directiva de correo no deseado saliente en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="3f827-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="3f827-327">Para modificar una directiva de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="3f827-328">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3f827-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="3f827-329">Usar PowerShell para modificar las reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="3f827-330">El único valor que no está disponible cuando se modifica una regla de filtro de correo no deseado saliente en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="3f827-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="3f827-331">Para habilitar o deshabilitar las reglas de filtro de correo no deseado saliente existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="3f827-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="3f827-332">De lo contrario, no hay opciones de configuración adicionales disponibles cuando se modifica una regla de filtro de correo no deseado saliente en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f827-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="3f827-333">La misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla de filtro de correo no deseado saliente](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="3f827-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="3f827-334">Para modificar una regla de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="3f827-335">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3f827-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="3f827-336">Usar PowerShell para habilitar o deshabilitar reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="3f827-337">La habilitación o deshabilitación de una regla de filtro de correo no deseado saliente en PowerShell habilita o deshabilita toda la Directiva de correo no deseado saliente (la regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asignada).</span><span class="sxs-lookup"><span data-stu-id="3f827-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="3f827-338">No se puede habilitar o deshabilitar la Directiva de correo no deseado saliente predeterminada (siempre se aplica siempre a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="3f827-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="3f827-339">Para habilitar o deshabilitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="3f827-340">En este ejemplo se deshabilita la regla de filtro de correo no deseado saliente denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3f827-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="3f827-341">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="3f827-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="3f827-342">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) y [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3f827-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="3f827-343">Usar PowerShell para establecer la prioridad de las reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="3f827-344">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="3f827-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="3f827-345">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="3f827-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="3f827-346">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="3f827-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="3f827-347">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="3f827-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="3f827-348">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="3f827-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="3f827-349">Para establecer la prioridad de una regla de filtro de correo no deseado saliente en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="3f827-350">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="3f827-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="3f827-351">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="3f827-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="3f827-352">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="3f827-352">**Notes**:</span></span>

- <span data-ttu-id="3f827-353">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-HostedOutboundSpamFilterRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3f827-353">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="3f827-354">La Directiva de filtro de correo no deseado predeterminado saliente no tiene una regla de filtro de correo no deseado correspondiente y siempre tiene el valor de prioridad no modificable **más bajo**.</span><span class="sxs-lookup"><span data-stu-id="3f827-354">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="3f827-355">Usar PowerShell para quitar las directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-355">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="3f827-356">Cuando se usa PowerShell para quitar una directiva de filtro de correo no deseado saliente, no se quita la regla de filtro de correo no deseado saliente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3f827-356">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="3f827-357">Para quitar una directiva de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-357">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="3f827-358">En este ejemplo se quita la Directiva de filtro de correo no deseado saliente denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3f827-358">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="3f827-359">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3f827-359">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="3f827-360">Usar PowerShell para quitar reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="3f827-360">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="3f827-361">Cuando se usa PowerShell para quitar una regla de filtro de correo no deseado saliente, no se elimina la Directiva de filtro de correo no deseado saliente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3f827-361">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="3f827-362">Para quitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3f827-362">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="3f827-363">En este ejemplo se quita la regla de filtro de correo no deseado saliente denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3f827-363">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="3f827-364">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3f827-364">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="3f827-365">Más información</span><span class="sxs-lookup"><span data-stu-id="3f827-365">For more information</span></span>

[<span data-ttu-id="3f827-366">Quitar usuarios bloqueados del portal de Usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="3f827-366">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="3f827-367">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="3f827-367">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="3f827-368">Preguntas más frecuentes sobre la protección contra correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="3f827-368">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
