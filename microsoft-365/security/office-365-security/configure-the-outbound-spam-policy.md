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
description: Los administradores pueden obtener información sobre cómo ver, crear, modificar y eliminar directivas de correo no deseado salientes en Exchange Online Protection (EOP).
ms.openlocfilehash: 7102f858e0293f2a55fe68a55d4dc2cf3ab38a33
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024587"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="b2606-103">Configurar el filtrado de correo no deseado saliente en EOP</span><span class="sxs-lookup"><span data-stu-id="b2606-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="b2606-104">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes de correo electrónico salientes que se envían a través de EOP se comprueban automáticamente en busca de correo no deseado y actividad de envío inusual.</span><span class="sxs-lookup"><span data-stu-id="b2606-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="b2606-105">Normalmente, el correo no deseado saliente de un usuario de la organización indica una cuenta en peligro.</span><span class="sxs-lookup"><span data-stu-id="b2606-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="b2606-106">Los mensajes sospechosos se marcan como correo no deseado (independientemente del nivel de confianza de correo no deseado o de SCL) y se enrutan a través del [grupo de entrega de alto riesgo](high-risk-delivery-pool-for-outbound-messages.md) para ayudar a proteger la reputación del servicio (es decir, mantenga los servidores de correo electrónico de origen de Microsoft 365 en las listas de direcciones IP bloqueadas).</span><span class="sxs-lookup"><span data-stu-id="b2606-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="b2606-107">Los administradores reciben automáticamente una notificación de la actividad de correo electrónico saliente y de los usuarios bloqueados mediante [directivas de alerta](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b2606-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="b2606-108">EOP usa directivas de correo no deseado salientes como parte de la defensa general de la organización contra el correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b2606-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="b2606-109">Para obtener más información, consulte [Protección contra correo no deseado](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b2606-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="b2606-110">Los administradores pueden ver, editar y configurar (pero no eliminar) la Directiva de correo no deseado saliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b2606-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="b2606-111">Para una mayor granularidad, también puede crear directivas de correo no deseado saliente personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="b2606-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="b2606-112">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="b2606-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="b2606-113">Puede configurar directivas de correo no deseado salientes en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones en Exchange Online; independiente de EOP para organizaciones sin buzones de correo de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="b2606-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="b2606-114">Directivas de correo no deseado salientes en el centro de seguridad & cumplimiento vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2606-114">Outbound spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="b2606-115">Los elementos básicos de una directiva de correo no deseado saliente en EOP son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2606-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="b2606-116">**La Directiva de filtro de correo no deseado saliente**: especifica las acciones para los veredictos de filtrado de correo no deseado saliente y las opciones de notificación.</span><span class="sxs-lookup"><span data-stu-id="b2606-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="b2606-117">**La regla de filtro de correo no deseado saliente**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva) para una directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b2606-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="b2606-118">La diferencia entre estos dos elementos no es obvia cuando se administran las directivas de correo no deseado saliente en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="b2606-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b2606-119">Cuando se crea una directiva de correo no deseado saliente en el centro de seguridad & cumplimiento, en realidad se crea una regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="b2606-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="b2606-120">Cuando se modifica una directiva de correo no deseado saliente en el centro de seguridad & cumplimiento, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado y destinatarios modifica la regla de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b2606-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="b2606-121">Todas las demás opciones modifican la Directiva de filtro de correo no deseado saliente asociada.</span><span class="sxs-lookup"><span data-stu-id="b2606-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="b2606-122">Cuando quita una directiva de correo no deseado saliente del centro de seguridad & cumplimiento, se quita la regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asociada.</span><span class="sxs-lookup"><span data-stu-id="b2606-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="b2606-123">En Exchange Online PowerShell o en PowerShell independiente de EOP, la diferencia entre las directivas de filtro de correo no deseado saliente y las reglas de filtro de correo no deseado saliente es evidente.</span><span class="sxs-lookup"><span data-stu-id="b2606-123">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="b2606-124">Puede administrar las directivas de filtro de correo no deseado saliente con los cmdlets \*\* \* -HostedOutboundSpamFilterPolicy\*\* y administrar las reglas de filtro de correo no deseado saliente con los cmdlets \*\* \* -HostedOutboundSpamFilterRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="b2606-124">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="b2606-125">En PowerShell, se crea la Directiva de filtro de correo no deseado saliente en primer lugar y, a continuación, se crea la regla de filtro de correo no deseado saliente que identifica la Directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="b2606-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="b2606-126">En PowerShell, se modifica la configuración de la Directiva de filtro de correo no deseado saliente y de la regla de filtro de correo no deseado saliente por separado.</span><span class="sxs-lookup"><span data-stu-id="b2606-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="b2606-127">Cuando quita una directiva de filtro de correo no deseado saliente de PowerShell, la regla de filtro de correo no deseado saliente correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="b2606-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="b2606-128">Directiva de correo no deseado saliente predeterminada</span><span class="sxs-lookup"><span data-stu-id="b2606-128">Default outbound spam policy</span></span>

<span data-ttu-id="b2606-129">Cada organización tiene integrada una directiva de correo no deseado saliente denominada predeterminada que tiene estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="b2606-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="b2606-130">La Directiva de filtro de correo no deseado saliente denominada predeterminada se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla de filtro de correo no deseado saliente (filtros de destinatario) asociada a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="b2606-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="b2606-131">La directiva denominada Predeterminada tiene un valor de prioridad personalizado **Inferior** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="b2606-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="b2606-132">Las directivas personalizadas que cree siempre tendrán una prioridad mayor que la directiva denominada Predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b2606-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="b2606-133">La directiva denominada Predeterminada es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b2606-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="b2606-134">Para aumentar la eficacia del filtrado de correo no deseado saliente, puede crear directivas de correo no deseado saliente personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="b2606-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b2606-135">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="b2606-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b2606-136">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b2606-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b2606-137">Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="b2606-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="b2606-138">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b2606-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b2606-139">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="b2606-139">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b2606-140">Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:</span><span class="sxs-lookup"><span data-stu-id="b2606-140">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="b2606-141">Para agregar, modificar y eliminar directivas de correo no deseado saliente, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="b2606-141">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b2606-142">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b2606-142">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b2606-143">**Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b2606-143">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="b2606-144">Para el acceso de solo lectura a las directivas de correo no deseado saliente, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="b2606-144">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b2606-145">**Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b2606-145">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b2606-146">**Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b2606-146">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="b2606-147">Para conocer la configuración recomendada para las directivas de correo no deseado saliente, consulte [EOP Outbound Spam Filter Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="b2606-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="b2606-148">Las [directivas de alerta](../../compliance/alert-policies.md) predeterminadas denominadas límite de envío de **correo electrónico superado**, los **patrones de envío de correo electrónico sospechoso detectados**y el **usuario restringido del envío de correo electrónico** ya envían notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**global Admins**) sobre la actividad de correo electrónico saliente y los usuarios bloqueados debido a correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b2606-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="b2606-149">Para obtener más información, consulte [Verify The Alert Settings for Restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="b2606-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="b2606-150">Se recomienda usar estas directivas de alerta en lugar de las opciones de notificación en las directivas de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b2606-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="b2606-151">Usar el centro de seguridad & cumplimiento para crear directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="b2606-152">La creación de una directiva personalizada de correo no deseado saliente en el centro de seguridad & cumplimiento crea la regla de filtro de correo no deseado y la Directiva de filtro de correo no deseado asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="b2606-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="b2606-153">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b2606-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b2606-154">En la página **configuración contra correo no deseado** , haga clic en **crear una directiva de salida**.</span><span class="sxs-lookup"><span data-stu-id="b2606-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="b2606-155">En la **Directiva de filtro de correo no deseado saliente** , vaya hacia fuera que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b2606-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="b2606-156">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="b2606-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="b2606-157">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="b2606-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="b2606-158">Opcional Expanda la sección **notificaciones** para configurar usuarios adicionales que deben recibir copias y notificaciones de mensajes de correo electrónico salientes sospechosos:</span><span class="sxs-lookup"><span data-stu-id="b2606-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="b2606-159">**Enviar una copia de los mensajes de correo electrónico saliente sospechosos a personas específicas**: esta opción agrega los usuarios especificados como destinatarios en copia oculta a los mensajes sospechosos de salida.</span><span class="sxs-lookup"><span data-stu-id="b2606-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="b2606-160">Esta configuración solo funciona en la directiva predeterminada de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b2606-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="b2606-161">No funciona en las directivas de correo no deseado saliente personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="b2606-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="b2606-162">Para habilitar esta opción:</span><span class="sxs-lookup"><span data-stu-id="b2606-162">To enable this setting:</span></span>

     1. <span data-ttu-id="b2606-163">Active la casilla para habilitar la configuración.</span><span class="sxs-lookup"><span data-stu-id="b2606-163">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="b2606-164">Haga clic en **Agregar personas**.</span><span class="sxs-lookup"><span data-stu-id="b2606-164">Click **Add people**.</span></span> <span data-ttu-id="b2606-165">En el control flotante **Agregar o quitar destinatarios** que aparece:</span><span class="sxs-lookup"><span data-stu-id="b2606-165">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="b2606-166">Escriba la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="b2606-166">Enter the sender's email address.</span></span> <span data-ttu-id="b2606-167">Puede especificar varias direcciones de correo electrónico separadas por punto y coma (;) o un destinatario por línea.</span><span class="sxs-lookup"><span data-stu-id="b2606-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="b2606-168">Haga clic en</span><span class="sxs-lookup"><span data-stu-id="b2606-168">Click</span></span> ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="b2606-170">para agregar los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="b2606-170">to add the recipients.</span></span>

        <span data-ttu-id="b2606-171">Repita estos pasos tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b2606-171">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="b2606-172">Los destinatarios que ha agregado aparecen en la sección **lista de destinatarios** en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="b2606-172">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="b2606-173">Para eliminar un destinatario, haga clic en el ![ botón quitar ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="b2606-173">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="b2606-174">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b2606-174">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="b2606-175">Para deshabilitar esta opción, desactive la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="b2606-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="b2606-176">**Notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado saliente**:</span><span class="sxs-lookup"><span data-stu-id="b2606-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="b2606-177">La [Directiva de alerta](../../compliance/alert-policies.md) predeterminada denominada **usuario restringido del envío de correo electrónico** ya envía notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**administradores globales**) cuando los usuarios se bloquean debido a que superan los límites de la sección **límites de destinatarios** .</span><span class="sxs-lookup"><span data-stu-id="b2606-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="b2606-178">Le recomendamos que use la Directiva de alertas en lugar de esta opción en la Directiva de correo no deseado saliente para notificar a los administradores y a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="b2606-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="b2606-179">Para obtener instrucciones, consulte [Verify The Alert Settings for Restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="b2606-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <br/><br/> <span data-ttu-id="b2606-180">Esta configuración solo funciona en la directiva predeterminada de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b2606-180">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="b2606-181">No funciona en las directivas de correo no deseado saliente personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="b2606-181">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="b2606-182">Para habilitar esta opción:</span><span class="sxs-lookup"><span data-stu-id="b2606-182">To enable this setting:</span></span>

     <span data-ttu-id="b2606-183">a.</span><span class="sxs-lookup"><span data-stu-id="b2606-183">a.</span></span> <span data-ttu-id="b2606-184">Active la casilla para habilitar la configuración.</span><span class="sxs-lookup"><span data-stu-id="b2606-184">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="b2606-185">b.</span><span class="sxs-lookup"><span data-stu-id="b2606-185">b.</span></span> <span data-ttu-id="b2606-186">Haga clic en **Agregar personas**.</span><span class="sxs-lookup"><span data-stu-id="b2606-186">Click **Add people**.</span></span> <span data-ttu-id="b2606-187">En el control flotante **Agregar o quitar destinatarios** que aparece:</span><span class="sxs-lookup"><span data-stu-id="b2606-187">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="b2606-188">c.</span><span class="sxs-lookup"><span data-stu-id="b2606-188">c.</span></span> <span data-ttu-id="b2606-189">Escriba la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="b2606-189">Enter the sender's email address.</span></span> <span data-ttu-id="b2606-190">Puede especificar varias direcciones de correo electrónico separadas por punto y coma (;) o un destinatario por línea.</span><span class="sxs-lookup"><span data-stu-id="b2606-190">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="b2606-191">d.</span><span class="sxs-lookup"><span data-stu-id="b2606-191">d.</span></span> <span data-ttu-id="b2606-192">Haga clic en</span><span class="sxs-lookup"><span data-stu-id="b2606-192">Click</span></span> ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="b2606-194">para agregar los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="b2606-194">to add the recipients.</span></span>

        <span data-ttu-id="b2606-195">Repita estos pasos tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b2606-195">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="b2606-196">Los destinatarios que ha agregado aparecen en la sección **lista de destinatarios** en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="b2606-196">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="b2606-197">Para eliminar un destinatario, haga clic en el ![ botón quitar ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="b2606-197">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="b2606-198">e.</span><span class="sxs-lookup"><span data-stu-id="b2606-198">e.</span></span> <span data-ttu-id="b2606-199">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b2606-199">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="b2606-200">Para deshabilitar esta opción, desactive la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="b2606-200">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="b2606-201">Opcional Expanda la sección **límites de destinatarios** para configurar los límites y las acciones de los mensajes de correo electrónico saliente sospechosos:</span><span class="sxs-lookup"><span data-stu-id="b2606-201">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="b2606-202">Esta configuración solo se aplica a los buzones basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="b2606-202">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="b2606-203">**Número máximo de destinatarios por usuario**</span><span class="sxs-lookup"><span data-stu-id="b2606-203">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="b2606-204">Un valor válido es de 0 a 10000.</span><span class="sxs-lookup"><span data-stu-id="b2606-204">A valid value is 0 to 10000.</span></span> <span data-ttu-id="b2606-205">El valor predeterminado es 0, lo que significa que se usan los valores predeterminados del servicio.</span><span class="sxs-lookup"><span data-stu-id="b2606-205">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="b2606-206">Para obtener más información, consulte [límites de envío](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="b2606-206">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="b2606-207">**Límite horario externo**: el número máximo de destinatarios externos por hora.</span><span class="sxs-lookup"><span data-stu-id="b2606-207">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="b2606-208">**Límite horario interno**: el número máximo de destinatarios internos por hora.</span><span class="sxs-lookup"><span data-stu-id="b2606-208">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="b2606-209">**Límite diario**: número máximo total de destinatarios por día.</span><span class="sxs-lookup"><span data-stu-id="b2606-209">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="b2606-210">**Acción cuando un usuario supera los límites anteriores**: configure la acción que se llevará a cabo cuando se supere alguno de los **límites de destinatarios** .</span><span class="sxs-lookup"><span data-stu-id="b2606-210">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="b2606-211">Para todas las acciones, los destinatarios especificados en el **usuario restringió el envío de la Directiva de alerta de correo electrónico** (y en el ahora la Directiva de notificación de correo no deseado **se bloquea al enviar un remitente porque al enviar la configuración de correo no deseado saliente** en la Directiva de correo no deseado de salida recibe notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b2606-211">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="b2606-212">**Restringir al usuario el envío de correo hasta el siguiente día**: este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b2606-212">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="b2606-213">Se envían notificaciones por correo electrónico y el usuario no podrá enviar más mensajes hasta el día siguiente, en función de la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="b2606-213">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="b2606-214">El administrador no tiene forma de reemplazar este bloque.</span><span class="sxs-lookup"><span data-stu-id="b2606-214">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="b2606-215">La alerta de actividad denominada **usuario restringido del envío de correo electrónico** notifica a los administradores (por correo electrónico y en la página **Ver alertas** ).</span><span class="sxs-lookup"><span data-stu-id="b2606-215">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="b2606-216">También se notifica a los destinatarios especificados en la directiva **notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado saliente** en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="b2606-216">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="b2606-217">El usuario no podrá enviar más mensajes hasta el día siguiente, en función de la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="b2606-217">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="b2606-218">El administrador no tiene forma de reemplazar este bloque.</span><span class="sxs-lookup"><span data-stu-id="b2606-218">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="b2606-219">**Restringir al usuario el envío de correo**: se envían notificaciones por correo electrónico, el usuario se agrega al portal \*\*[Restricted users] <https://sip.protection.office.com/restrictedusers> \*\* en el centro de seguridad & cumplimiento y el usuario no puede enviar correo electrónico hasta que un administrador lo elimine del portal de **usuarios restringidos** . Una vez que un administrador quita al usuario de la lista, el usuario no volverá a estar restringido para ese día.</span><span class="sxs-lookup"><span data-stu-id="b2606-219">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="b2606-220">Para obtener instrucciones, consulte [quitar un usuario del portal de usuarios restringidos después de enviar correo no deseado](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="b2606-220">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="b2606-221">**No se realiza ninguna acción, solo alerta**: se envían notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b2606-221">**No action, alert only**: Email notifications are sent.</span></span>
6. <span data-ttu-id="b2606-222">Opcional Expanda la sección **desvío automático** para configurar los controles sobre cómo se controla el reenvío automático por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b2606-222">(Optional) Expand **Automatic Forwarding** section to configure controls over how automatic forwarding by users is controlled.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b2606-223">Esta configuración solo se aplica a los buzones basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="b2606-223">These settings are only applicable to cloud-based mailboxes.</span></span>
   
   - <span data-ttu-id="b2606-224">**Reenvío automático**</span><span class="sxs-lookup"><span data-stu-id="b2606-224">**Automatic Forwarding**</span></span>
  
      <span data-ttu-id="b2606-225">Seleccione una de las opciones para controlar cómo se controla el reenvío automático.</span><span class="sxs-lookup"><span data-stu-id="b2606-225">Select one of the options to control how automatic forwarding is handled.</span></span>
    
      - <span data-ttu-id="b2606-226">**Automático**: configuración predeterminada que permite al sistema controlar el reenvío automático con el reenvío automático deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b2606-226">**Automatic**: Default setting that allows the system to control automatic forwarding with automatic forwarding disabled by default.</span></span>
      - <span data-ttu-id="b2606-227">**On**: el reenvío externo está habilitado en la Directiva sin restricción.</span><span class="sxs-lookup"><span data-stu-id="b2606-227">**On**: External forwarding is enabled within the policy without restriction.</span></span>
      - <span data-ttu-id="b2606-228">**Desactivado**: el reenvío externo está deshabilitado y se bloqueará</span><span class="sxs-lookup"><span data-stu-id="b2606-228">**Off**: External forwarding is disabled and will be blocked</span></span>

7. <span data-ttu-id="b2606-229">Necesarios Expanda la sección **aplicado a** para identificar los remitentes internos a los que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="b2606-229">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="b2606-230">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="b2606-230">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b2606-231">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<sender1\>_ o _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="b2606-231">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="b2606-232">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<sender1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="b2606-232">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="b2606-233">Es más fácil hacer clic en **Agregar una condición** tres veces para ver todas las condiciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="b2606-233">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="b2606-234">Puede hacer clic en el ![botón Quitar](../../media/scc-remove-icon.png) para quitar condiciones que no quiera configurar.</span><span class="sxs-lookup"><span data-stu-id="b2606-234">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="b2606-235">**El dominio del remitente es**: especifica los remitentes en uno o varios de los dominios aceptados configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="b2606-235">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="b2606-236">Haga clic en el cuadro **Agregar una etiqueta** para ver y seleccionar un dominio.</span><span class="sxs-lookup"><span data-stu-id="b2606-236">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="b2606-237">Haga clic de nuevo en el cuadro **Agregar una etiqueta** para seleccionar dominios adicionales si hay más de un dominio disponible.</span><span class="sxs-lookup"><span data-stu-id="b2606-237">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="b2606-238">**Sender es**: especifica uno o más usuarios en la organización.</span><span class="sxs-lookup"><span data-stu-id="b2606-238">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="b2606-239">Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista.</span><span class="sxs-lookup"><span data-stu-id="b2606-239">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="b2606-240">Vuelva a hacer clic en el cuadro **Agregar una etiqueta** para seleccionar remitentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="b2606-240">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="b2606-241">**Sender es un miembro de**: especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="b2606-241">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="b2606-242">Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista.</span><span class="sxs-lookup"><span data-stu-id="b2606-242">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="b2606-243">Vuelva a hacer clic en el cuadro **Agregar una etiqueta** para seleccionar remitentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="b2606-243">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="b2606-244">**Excepto si**: para agregar excepciones para la regla, haga clic en **Agregar una condición** tres veces para ver todas las excepciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="b2606-244">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="b2606-245">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="b2606-245">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="b2606-246">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b2606-246">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="b2606-247">Usar el centro de seguridad & cumplimiento para ver las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-247">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="b2606-248">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b2606-248">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b2606-249">En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir una directiva de correo no deseado saliente:</span><span class="sxs-lookup"><span data-stu-id="b2606-249">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="b2606-250">La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.</span><span class="sxs-lookup"><span data-stu-id="b2606-250">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="b2606-251">Una directiva personalizada creada donde el valor de la columna **tipo** es Directiva de **correo no deseado saliente personalizada**.</span><span class="sxs-lookup"><span data-stu-id="b2606-251">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="b2606-252">La configuración de la Directiva se muestra en los detalles de la Directiva ampliada que aparecen, o bien puede hacer clic en **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="b2606-252">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="b2606-253">Usar el centro de seguridad & cumplimiento para modificar las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-253">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="b2606-254">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b2606-254">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b2606-255">En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir una directiva de correo no deseado saliente:</span><span class="sxs-lookup"><span data-stu-id="b2606-255">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="b2606-256">La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.</span><span class="sxs-lookup"><span data-stu-id="b2606-256">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="b2606-257">Una directiva personalizada creada donde el valor de la columna **tipo** es Directiva de **correo no deseado saliente personalizada**.</span><span class="sxs-lookup"><span data-stu-id="b2606-257">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="b2606-258">Haga clic en **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="b2606-258">Click **Edit policy**.</span></span>

<span data-ttu-id="b2606-259">Para directivas de correo no deseado personalizadas personalizadas, la configuración disponible en el control flotante que aparece es idéntica a la descrita en el [centro de seguridad & cumplimiento para crear directivas de correo no deseado saliente](#use-the-security--compliance-center-to-create-outbound-spam-policies) .</span><span class="sxs-lookup"><span data-stu-id="b2606-259">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="b2606-260">Para la Directiva de correo no deseado saliente predeterminada denominada **Directiva de filtro de correo no deseado saliente**, la sección **aplicado a** no está disponible (la Directiva se aplica a todos los usuarios) y no puede cambiar el nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="b2606-260">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="b2606-261">Vea las secciones siguientes para habilitar o deshabilitar una directiva, establecer el orden de prioridad de la directiva o configurar las notificaciones en cuarentena para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="b2606-261">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="b2606-262">Habilitar o deshabilitar las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-262">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="b2606-263">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b2606-263">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b2606-264">En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir una directiva personalizada que haya creado (el valor en la columna **tipo** es **Directiva de correo no deseado saliente personalizada**).</span><span class="sxs-lookup"><span data-stu-id="b2606-264">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="b2606-265">En los detalles de la directiva expandida que aparecen, observe el valor de la columna **Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="b2606-265">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="b2606-266">Mueva el botón de alternancia a la izquierda para deshabilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="b2606-266">Move the toggle to the left to disable the policy:</span></span> ![Deshabilitar](../../media/scc-toggle-off.png)

   <span data-ttu-id="b2606-268">Mueva el botón de alternancia a la derecha para habilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="b2606-268">Move the toggle to the right to enable the policy:</span></span> ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="b2606-270">No se puede deshabilitar la Directiva de correo no deseado saliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b2606-270">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="b2606-271">Establecer la prioridad de las directivas de correo no deseado saliente personalizadas</span><span class="sxs-lookup"><span data-stu-id="b2606-271">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="b2606-272">De forma predeterminada, las directivas de correo no deseado saliente tienen una prioridad que se basa en el orden en que se crearon (las nuevas directivas tienen una prioridad más baja que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="b2606-272">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="b2606-273">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="b2606-273">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b2606-274">Dos directivas no pueden tener la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="b2606-274">No two policies can have the same priority.</span></span>

<span data-ttu-id="b2606-275">Las directivas de correo no deseado de salida personalizadas se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="b2606-275">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="b2606-276">La Directiva de correo no deseado saliente predeterminada denominada **Directiva de filtro de correo no deseado saliente** tiene el valor de prioridad **más bajo**y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="b2606-276">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="b2606-277">Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="b2606-277">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="b2606-278">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b2606-278">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b2606-279">En la página **configuración contra correo no deseado** , busque las directivas en las que el valor de la columna **tipo** es **Directiva de correo no deseado saliente personalizada**.</span><span class="sxs-lookup"><span data-stu-id="b2606-279">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="b2606-280">Observe los valores de la columna **Prioridad**:</span><span class="sxs-lookup"><span data-stu-id="b2606-280">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="b2606-281">La directiva personalizada de correo no deseado saliente con la prioridad más alta tiene el ![ icono de flecha abajo de valor ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="b2606-281">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="b2606-282">La directiva personalizada de correo no deseado saliente con la prioridad más baja tiene el ![ icono de flecha arriba de valor ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por ejemplo, ![ icono de flecha arriba ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="b2606-282">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="b2606-283">Si tiene tres o más directivas de correo no deseado saliente personalizadas, las directivas entre la prioridad más alta y la más baja tienen ![ un ](../../media/ITPro-EAC-UpArrowIcon.png)![ icono de flecha abajo hacia arriba ](../../media/ITPro-EAC-DownArrowIcon.png) (por ejemplo, **icono flecha** arriba en el icono ![ de ](../../media/ITPro-EAC-UpArrowIcon.png)![ flecha arriba ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="b2606-283">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="b2606-284">Haga clic en</span><span class="sxs-lookup"><span data-stu-id="b2606-284">Click</span></span> ![Icono flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="b2606-286">o</span><span class="sxs-lookup"><span data-stu-id="b2606-286">or</span></span> ![Icono flecha abajo](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="b2606-288">para mover la Directiva de correo no deseado saliente personalizada hacia arriba o hacia abajo en la lista de prioridades.</span><span class="sxs-lookup"><span data-stu-id="b2606-288">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="b2606-289">Usar el centro de seguridad & cumplimiento para eliminar directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-289">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="b2606-290">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b2606-290">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b2606-291">En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir la directiva personalizada que desea eliminar (la columna **tipo** es **Directiva de correo no deseado saliente personalizada**).</span><span class="sxs-lookup"><span data-stu-id="b2606-291">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="b2606-292">En los detalles de la directiva expandida que aparecen, haga clic en **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="b2606-292">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="b2606-293">Haga clic en **Sí** en el mensaje de advertencia que se muestra.</span><span class="sxs-lookup"><span data-stu-id="b2606-293">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="b2606-294">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b2606-294">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="b2606-295">Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar las directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-295">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="b2606-296">Usar PowerShell para crear directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-296">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="b2606-297">La creación de una directiva de correo no deseado saliente en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="b2606-297">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b2606-298">Crear la Directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b2606-298">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="b2606-299">Cree la regla de filtro de correo no deseado saliente que especifica la Directiva de filtro de correo no deseado saliente a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="b2606-299">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="b2606-300">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="b2606-300">**Notes**:</span></span>

- <span data-ttu-id="b2606-301">Puede crear una nueva regla de filtro de correo no deseado saliente y asignar una directiva de filtro de correo no deseado saliente existente que no esté asociada.</span><span class="sxs-lookup"><span data-stu-id="b2606-301">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="b2606-302">Una regla de filtro de correo no deseado saliente no se puede asociar con más de una directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b2606-302">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="b2606-303">Puede configurar las siguientes opciones en nuevas directivas de filtro de correo no deseado saliente en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:</span><span class="sxs-lookup"><span data-stu-id="b2606-303">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="b2606-304">Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="b2606-304">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="b2606-305">Establezca la prioridad de la Directiva durante la creación (_prioridad_ _\<Number\>_ ) en el cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="b2606-305">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="b2606-306">Una nueva Directiva de filtro de correo no deseado saliente que se crea en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que se asigna la Directiva a una regla de filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b2606-306">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="b2606-307">Paso 1: usar PowerShell para crear una directiva de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-307">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="b2606-308">Para crear una directiva de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-308">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="b2606-309">En este ejemplo se crea una nueva Directiva de filtro de correo no deseado saliente denominada ejecutivos de Contoso con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="b2606-309">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="b2606-310">Los límites de frecuencia de destinatarios están restringidos a valores más bajos que los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b2606-310">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="b2606-311">Para obtener más información, consulte [límites de envío en las opciones de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="b2606-311">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="b2606-312">Una vez que se alcanza uno de los límites, se impide el envío de mensajes al usuario.</span><span class="sxs-lookup"><span data-stu-id="b2606-312">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="b2606-313">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b2606-313">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="b2606-314">Paso 2: usar PowerShell para crear una regla de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-314">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="b2606-315">Para crear una regla de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-315">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="b2606-316">En este ejemplo se crea una nueva regla de filtro de correo no deseado saliente denominada ejecutivos de Contoso con esta configuración:</span><span class="sxs-lookup"><span data-stu-id="b2606-316">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="b2606-317">La Directiva de filtro de correo no deseado saliente denominada ejecutivos de Contoso está asociada a la regla.</span><span class="sxs-lookup"><span data-stu-id="b2606-317">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="b2606-318">La regla se aplica a los miembros del grupo denominado Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="b2606-318">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="b2606-319">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b2606-319">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="b2606-320">Usar PowerShell para ver las directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-320">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="b2606-321">Para obtener una lista resumida de todas las directivas de filtro de correo no deseado salientes, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="b2606-321">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="b2606-322">Para obtener información detallada sobre una directiva de filtro de correo no deseado específica, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-322">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="b2606-323">En este ejemplo se devuelven todos los valores de propiedad de la Directiva de filtro de correo no deseado saliente denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="b2606-323">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="b2606-324">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b2606-324">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="b2606-325">Usar PowerShell para ver las reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-325">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="b2606-326">Para ver las reglas de filtro de correo no deseado saliente existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-326">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="b2606-327">Para obtener una lista resumida de todas las reglas de filtro de correo no deseado salientes, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="b2606-327">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="b2606-328">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="b2606-328">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="b2606-329">Para obtener información detallada sobre una regla de filtrado de correo no deseado específica, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-329">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="b2606-330">En este ejemplo se devuelven todos los valores de propiedad de la regla de filtro de correo no deseado saliente denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="b2606-330">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="b2606-331">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b2606-331">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="b2606-332">Usar PowerShell para modificar las directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-332">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="b2606-333">La misma configuración está disponible cuando modifica una directiva de filtro de malware en PowerShell como cuando crea la Directiva tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva de filtro de correo no deseado saliente](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="b2606-333">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="b2606-334">No se puede cambiar el nombre de una directiva de filtro de correo no deseado saliente (el cmdlet **set-HostedOutboundSpamFilterPolicy** no tiene ningún parámetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="b2606-334">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b2606-335">Al cambiar el nombre de una directiva de correo no deseado saliente en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b2606-335">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="b2606-336">Para modificar una directiva de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-336">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b2606-337">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b2606-337">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="b2606-338">Usar PowerShell para modificar las reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-338">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="b2606-339">El único valor que no está disponible cuando se modifica una regla de filtro de correo no deseado saliente en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="b2606-339">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b2606-340">Para habilitar o deshabilitar las reglas de filtro de correo no deseado saliente existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="b2606-340">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="b2606-341">De lo contrario, no hay opciones de configuración adicionales disponibles cuando se modifica una regla de filtro de correo no deseado saliente en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2606-341">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="b2606-342">La misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla de filtro de correo no deseado saliente](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="b2606-342">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="b2606-343">Para modificar una regla de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-343">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b2606-344">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b2606-344">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="b2606-345">Usar PowerShell para habilitar o deshabilitar reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-345">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="b2606-346">La habilitación o deshabilitación de una regla de filtro de correo no deseado saliente en PowerShell habilita o deshabilita toda la Directiva de correo no deseado saliente (la regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asignada).</span><span class="sxs-lookup"><span data-stu-id="b2606-346">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="b2606-347">No se puede habilitar o deshabilitar la Directiva de correo no deseado saliente predeterminada (siempre se aplica siempre a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="b2606-347">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="b2606-348">Para habilitar o deshabilitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-348">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="b2606-349">En este ejemplo se deshabilita la regla de filtro de correo no deseado saliente denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b2606-349">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="b2606-350">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="b2606-350">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="b2606-351">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) y [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b2606-351">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="b2606-352">Usar PowerShell para establecer la prioridad de las reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-352">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="b2606-353">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="b2606-353">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="b2606-354">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="b2606-354">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="b2606-355">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="b2606-355">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="b2606-356">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="b2606-356">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="b2606-357">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="b2606-357">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b2606-358">Para establecer la prioridad de una regla de filtro de correo no deseado saliente en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-358">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b2606-359">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="b2606-359">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="b2606-360">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="b2606-360">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> 
> - <span data-ttu-id="b2606-361">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-HostedOutboundSpamFilterRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b2606-361">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="b2606-362">La Directiva de filtro de correo no deseado predeterminado saliente no tiene una regla de filtro de correo no deseado correspondiente y siempre tiene el valor de prioridad no modificable **más bajo**.</span><span class="sxs-lookup"><span data-stu-id="b2606-362">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="b2606-363">Usar PowerShell para quitar las directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-363">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="b2606-364">Cuando se usa PowerShell para quitar una directiva de filtro de correo no deseado saliente, no se quita la regla de filtro de correo no deseado saliente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b2606-364">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="b2606-365">Para quitar una directiva de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-365">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b2606-366">En este ejemplo se quita la Directiva de filtro de correo no deseado saliente denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b2606-366">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b2606-367">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b2606-367">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="b2606-368">Usar PowerShell para quitar reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b2606-368">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="b2606-369">Cuando se usa PowerShell para quitar una regla de filtro de correo no deseado saliente, no se elimina la Directiva de filtro de correo no deseado saliente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b2606-369">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="b2606-370">Para quitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2606-370">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="b2606-371">En este ejemplo se quita la regla de filtro de correo no deseado saliente denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b2606-371">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="b2606-372">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b2606-372">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b2606-373">Más información</span><span class="sxs-lookup"><span data-stu-id="b2606-373">For more information</span></span>

[<span data-ttu-id="b2606-374">Quitar usuarios bloqueados del portal de Usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="b2606-374">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="b2606-375">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="b2606-375">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="b2606-376">Preguntas más frecuentes sobre la protección contra correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="b2606-376">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="b2606-377">Informe de mensajes reenviados automáticamente</span><span class="sxs-lookup"><span data-stu-id="b2606-377">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
