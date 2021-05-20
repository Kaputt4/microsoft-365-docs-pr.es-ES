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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a ver, crear, modificar y eliminar directivas de correo no deseado saliente en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ead8aa75c0218dd2c4cad96e50e37ed3ddc12815
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583213"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="b14cf-103">Configurar el filtrado de correo no deseado saliente en EOP</span><span class="sxs-lookup"><span data-stu-id="b14cf-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b14cf-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="b14cf-104">**Applies to**</span></span>
- [<span data-ttu-id="b14cf-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b14cf-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b14cf-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b14cf-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b14cf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b14cf-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b14cf-108">En Microsoft 365 organizaciones con buzones de correo en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, los mensajes de correo electrónico salientes que se envían a través de EOP se comprueban automáticamente en busca de correo no deseado y actividad de envío inusual.</span><span class="sxs-lookup"><span data-stu-id="b14cf-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="b14cf-109">El correo no deseado saliente de un usuario de la organización suele indicar una cuenta comprometida.</span><span class="sxs-lookup"><span data-stu-id="b14cf-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="b14cf-110">Los mensajes salientes sospechosos se marcan como correo no deseado (independientemente del nivel de confianza de correo no deseado o SCL) y se enruta a través del grupo de entrega de alto riesgo para ayudar a proteger la reputación del servicio (es decir, mantener Microsoft 365 los servidores de correo electrónico de origen fuera de las listas de direcciones IP bloqueados). [](high-risk-delivery-pool-for-outbound-messages.md)</span><span class="sxs-lookup"><span data-stu-id="b14cf-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="b14cf-111">A los administradores se les notifica automáticamente sobre la actividad de correo electrónico saliente sospechosa y se bloquean los usuarios mediante directivas [de alerta.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b14cf-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="b14cf-112">EOP usa directivas de correo no deseado salientes como parte de la defensa general de su organización contra el correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b14cf-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="b14cf-113">Para obtener más información, consulte [Protección contra correo no deseado](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b14cf-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="b14cf-114">Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva de correo no deseado saliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b14cf-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="b14cf-115">Para mayor granularidad, también puede crear directivas de correo no deseado saliente personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="b14cf-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="b14cf-116">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="b14cf-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="b14cf-117">Puede configurar directivas de correo no deseado salientes en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin buzones Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="b14cf-117">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="b14cf-118">Los elementos básicos de una directiva de correo no deseado saliente en EOP son:</span><span class="sxs-lookup"><span data-stu-id="b14cf-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="b14cf-119">**La directiva de filtro de correo no** deseado saliente: especifica las acciones para los veredictos de filtrado de correo no deseado saliente y las opciones de notificación.</span><span class="sxs-lookup"><span data-stu-id="b14cf-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="b14cf-120">**La regla de filtro de correo** no deseado saliente: especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva) para una directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="b14cf-121">La diferencia entre estos dos elementos no es obvia cuando se administran directivas de correo no deseado salientes en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="b14cf-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b14cf-122">Al crear una directiva, está creando una regla de filtro de correo no deseado saliente y la directiva de filtro de correo no deseado saliente asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="b14cf-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="b14cf-123">Al modificar una directiva, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada, y los filtros de destinatarios modifican la regla de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="b14cf-124">Todas las demás opciones modifican la directiva de filtro de correo no deseado saliente asociada.</span><span class="sxs-lookup"><span data-stu-id="b14cf-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="b14cf-125">Al quitar una directiva, se quitan la regla de filtro de correo no deseado saliente y la directiva de filtro de correo no deseado saliente asociada.</span><span class="sxs-lookup"><span data-stu-id="b14cf-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="b14cf-126">En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="b14cf-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="b14cf-127">Para obtener más información, vea la sección Usar Exchange Online PowerShell o [PowerShell de EOP](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) independiente para configurar directivas de correo no deseado salientes más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b14cf-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="b14cf-128">Cada organización tiene una directiva de correo no deseado de salida integrada denominada Default que tiene estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="b14cf-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="b14cf-129">La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla de filtro de correo no deseado saliente (filtros de destinatarios) asociada a la directiva.</span><span class="sxs-lookup"><span data-stu-id="b14cf-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="b14cf-130">La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="b14cf-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="b14cf-131">Las directivas personalizadas que cree siempre tendrán una prioridad mayor que la directiva denominada Predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b14cf-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="b14cf-132">La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b14cf-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="b14cf-133">Para aumentar la eficacia del filtrado de correo no deseado saliente, puede crear directivas de correo no deseado saliente personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="b14cf-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b14cf-134">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="b14cf-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b14cf-135">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b14cf-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b14cf-136">Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="b14cf-136">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="b14cf-137">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b14cf-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b14cf-138">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="b14cf-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b14cf-139">Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="b14cf-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b14cf-140">Para agregar, modificar y eliminar directivas de correo no deseado salientes, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="b14cf-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b14cf-141">Para obtener acceso de solo lectura a las directivas de correo no deseado saliente, debe ser miembro de los grupos de roles **Lector global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="b14cf-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b14cf-142">Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="b14cf-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > - <span data-ttu-id="b14cf-143">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b14cf-143">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b14cf-144">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b14cf-144">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > 
  > - <span data-ttu-id="b14cf-145">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="b14cf-145">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="b14cf-146">Para obtener la configuración recomendada para las directivas de correo no deseado saliente, vea [Configuración de la directiva de filtro de correo no deseado saliente de EOP](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="b14cf-146">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="b14cf-147">Se [](../../compliance/alert-policies.md) superaron las directivas de alerta predeterminadas denominadas  Límite de envío de correo **electrónico,** patrones de envío de correo electrónico sospechosos **detectados** y Usuarios restringidos para enviar correo electrónico ya enviar notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** ( Administradores globales ) sobre la actividad de correo electrónico saliente inusual y los usuarios **bloqueados** debido al correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-147">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="b14cf-148">Para obtener más información, vea [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="b14cf-148">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="b14cf-149">Se recomienda usar estas directivas de alerta en lugar de las opciones de notificación en las directivas de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-149">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="b14cf-150">Usar el Centro de seguridad & cumplimiento para crear directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-150">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="b14cf-151">La creación de una directiva de correo no deseado saliente personalizada en el Centro de seguridad y cumplimiento de & crea la regla de filtro de correo no deseado y la directiva de filtro de correo no deseado asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="b14cf-151">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="b14cf-152">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-152">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b14cf-153">En la **página Configuración contra correo** no deseado, haga clic en Crear una directiva de **salida.**</span><span class="sxs-lookup"><span data-stu-id="b14cf-153">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="b14cf-154">En la **directiva de filtro de correo no** deseado saliente que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b14cf-154">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="b14cf-155">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="b14cf-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="b14cf-156">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="b14cf-156">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="b14cf-157">(Opcional) Expanda la **sección Notificaciones para** configurar usuarios adicionales que deben recibir copias y notificaciones de mensajes de correo electrónico saliente sospechosos:</span><span class="sxs-lookup"><span data-stu-id="b14cf-157">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="b14cf-158">**Enviar una copia de mensajes de** correo electrónico saliente sospechosos a personas específicas: esta configuración agrega los usuarios especificados como destinatarios CCO a los mensajes salientes sospechosos.</span><span class="sxs-lookup"><span data-stu-id="b14cf-158">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="b14cf-159">Esta configuración solo funciona en la directiva de correo no deseado saliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b14cf-159">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="b14cf-160">No funciona en las directivas de correo no deseado saliente personalizadas que cree.</span><span class="sxs-lookup"><span data-stu-id="b14cf-160">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="b14cf-161">Para habilitar esta configuración:</span><span class="sxs-lookup"><span data-stu-id="b14cf-161">To enable this setting:</span></span>

     1. <span data-ttu-id="b14cf-162">Active la casilla para habilitar la configuración.</span><span class="sxs-lookup"><span data-stu-id="b14cf-162">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="b14cf-163">Haga clic **en Agregar personas**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-163">Click **Add people**.</span></span> <span data-ttu-id="b14cf-164">En el **menú desplegable Agregar o quitar** destinatarios que aparece:</span><span class="sxs-lookup"><span data-stu-id="b14cf-164">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="b14cf-165">Escriba la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-165">Enter the sender's email address.</span></span> <span data-ttu-id="b14cf-166">Puede especificar varias direcciones de correo electrónico separadas por punto y coma (;) o un destinatario por línea.</span><span class="sxs-lookup"><span data-stu-id="b14cf-166">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="b14cf-167">Haga clic en</span><span class="sxs-lookup"><span data-stu-id="b14cf-167">Click</span></span> ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="b14cf-169">para agregar los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="b14cf-169">to add the recipients.</span></span>

        <span data-ttu-id="b14cf-170">Repita estos pasos tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b14cf-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="b14cf-171">Los destinatarios que agregó aparecen en la sección **Lista de destinatarios** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="b14cf-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="b14cf-172">Para eliminar un destinatario, haga clic ![ en El botón Quitar ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="b14cf-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="b14cf-173">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-173">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="b14cf-174">Para deshabilitar esta configuración, desactive la casilla.</span><span class="sxs-lookup"><span data-stu-id="b14cf-174">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="b14cf-175">**Notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado saliente:**</span><span class="sxs-lookup"><span data-stu-id="b14cf-175">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="b14cf-176">Esta configuración está en proceso de desuso de las directivas de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-176">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="b14cf-177">La [](../../compliance/alert-policies.md) directiva de  alerta predeterminada denominada Usuario restringido para enviar correo electrónico ya envía notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** ( Administradores globales ) cuando los usuarios se bloquean debido a que superan los límites de la sección **Límites** de destinatarios. </span><span class="sxs-lookup"><span data-stu-id="b14cf-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="b14cf-178">**Se recomienda encarecidamente que use la** directiva de alertas en lugar de esta configuración en la directiva de correo no deseado saliente para notificar a los administradores y otros usuarios .</span><span class="sxs-lookup"><span data-stu-id="b14cf-178">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="b14cf-179">Para obtener instrucciones, consulte [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="b14cf-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="b14cf-180">(Opcional) Expanda la **sección Límites de** destinatarios para configurar los límites y acciones de los mensajes de correo electrónico saliente sospechosos:</span><span class="sxs-lookup"><span data-stu-id="b14cf-180">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="b14cf-181">Esta configuración solo se aplica a los buzones basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="b14cf-181">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="b14cf-182">**Número máximo de destinatarios por usuario**</span><span class="sxs-lookup"><span data-stu-id="b14cf-182">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="b14cf-183">Un valor válido es de 0 a 10000.</span><span class="sxs-lookup"><span data-stu-id="b14cf-183">A valid value is 0 to 10000.</span></span> <span data-ttu-id="b14cf-184">El valor predeterminado es 0, lo que significa que se usan los valores predeterminados del servicio.</span><span class="sxs-lookup"><span data-stu-id="b14cf-184">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="b14cf-185">Para obtener más información, vea [Límites de envío](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="b14cf-185">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="b14cf-186">**Límite por hora externo:** el número máximo de destinatarios externos por hora.</span><span class="sxs-lookup"><span data-stu-id="b14cf-186">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="b14cf-187">**Límite por hora interno:** el número máximo de destinatarios internos por hora.</span><span class="sxs-lookup"><span data-stu-id="b14cf-187">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="b14cf-188">**Límite diario:** el número total máximo de destinatarios por día.</span><span class="sxs-lookup"><span data-stu-id="b14cf-188">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="b14cf-189">**Acción cuando un usuario supera los límites** anteriores: Configure la acción que debe realizarse cuando se supere **alguno** de los límites de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="b14cf-189">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="b14cf-190">Para todas las acciones, los  destinatarios especificados en la directiva de alerta de correo electrónico restringido por el usuario (y en la ahora redundante Notificar a personas específicas si un remitente está bloqueado debido **al** envío de correo no deseado saliente en la directiva de correo no deseado saliente reciben notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b14cf-190">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="b14cf-191">**Restringir al usuario el envío de correo hasta el día siguiente:** este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b14cf-191">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="b14cf-192">Se envían notificaciones por correo electrónico y el usuario no podrá enviar más mensajes hasta el día siguiente, en función de la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="b14cf-192">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="b14cf-193">No hay forma de que el administrador invalide este bloque.</span><span class="sxs-lookup"><span data-stu-id="b14cf-193">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="b14cf-194">La alerta de actividad denominada **Usuario restringido para enviar correo** electrónico notifica a los administradores (por correo electrónico y en la página Ver **alertas).**</span><span class="sxs-lookup"><span data-stu-id="b14cf-194">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="b14cf-195">También se notificará a los destinatarios especificados en la configuración Notificar a personas específicas si un remitente está bloqueado debido al envío de **correo** no deseado saliente en la directiva.</span><span class="sxs-lookup"><span data-stu-id="b14cf-195">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="b14cf-196">El usuario no podrá enviar más mensajes hasta el día siguiente, según la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="b14cf-196">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="b14cf-197">No hay forma de que el administrador invalide este bloque.</span><span class="sxs-lookup"><span data-stu-id="b14cf-197">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="b14cf-198">**Restringir** al usuario el envío de correo: se envían notificaciones de correo electrónico, el usuario se agrega al portal **[Usuarios restringidos] <https://sip.protection.office.com/restrictedusers>** en el Centro de seguridad & Cumplimiento y el usuario no puede enviar correo electrónico hasta que un administrador no las quite del **portal** de usuarios restringidos. Después de que un administrador quite el usuario de la lista, no se restringirá de nuevo para ese día.</span><span class="sxs-lookup"><span data-stu-id="b14cf-198">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="b14cf-199">Para obtener instrucciones, consulte [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="b14cf-199">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="b14cf-200">**Sin acción, solo alerta:** se envían notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b14cf-200">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="b14cf-201">(Opcional) Expanda **Sección Reenvío automático para** controlar el reenvío automático de correo electrónico por parte de los usuarios a remitentes externos.</span><span class="sxs-lookup"><span data-stu-id="b14cf-201">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="b14cf-202">Para obtener más información, consulte [Controlar el reenvío automático de correo electrónico externo en Microsoft 365](external-email-forwarding.md).</span><span class="sxs-lookup"><span data-stu-id="b14cf-202">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="b14cf-203">Antes de septiembre de 2020, esta configuración está disponible pero no se aplica.</span><span class="sxs-lookup"><span data-stu-id="b14cf-203">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="b14cf-204">Esta configuración solo se aplica a los buzones basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="b14cf-204">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="b14cf-205">Cuando se deshabilita el reenvío automático, el destinatario recibirá un informe de no entrega (también conocido como NDR o mensaje de desenviamiento) si los remitentes externos envían correo electrónico a un buzón que tiene el reenvío en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b14cf-205">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="b14cf-206">Si un remitente interno envía  el mensaje y el método de reenvío es el reenvío de buzones [(también](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) conocido como reenvío _SMTP),_ el remitente interno recibirá el NDR.</span><span class="sxs-lookup"><span data-stu-id="b14cf-206">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="b14cf-207">El remitente interno no obtiene un NDR si el reenvío se produjo debido a una regla de bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="b14cf-207">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="b14cf-208">Los valores disponibles son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b14cf-208">The available values are:</span></span>

   - <span data-ttu-id="b14cf-209">**Automático: controlado por el sistema:** permite el filtrado de correo no deseado saliente para controlar el reenvío automático de correo electrónico externo.</span><span class="sxs-lookup"><span data-stu-id="b14cf-209">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="b14cf-210">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b14cf-210">This is the default value.</span></span>
   - <span data-ttu-id="b14cf-211">**On**: La directiva no deshabilita el reenvío automático de correo electrónico externo.</span><span class="sxs-lookup"><span data-stu-id="b14cf-211">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="b14cf-212">**Desactivado:** la directiva deshabilita todo el reenvío automático de correo electrónico externo.</span><span class="sxs-lookup"><span data-stu-id="b14cf-212">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="b14cf-213">(Obligatorio) Expanda la **sección Aplicado a** para identificar los remitentes internos a los que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="b14cf-213">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="b14cf-214">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="b14cf-214">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b14cf-215">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<sender1\>_ o _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="b14cf-215">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="b14cf-216">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<sender1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="b14cf-216">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="b14cf-217">Es más fácil hacer clic en **Agregar una condición** tres veces para ver todas las condiciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="b14cf-217">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="b14cf-218">Puede hacer clic en el ![botón Quitar](../../media/scc-remove-icon.png) para quitar condiciones que no quiera configurar.</span><span class="sxs-lookup"><span data-stu-id="b14cf-218">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="b14cf-219">**El dominio del remitente es**: especifica remitentes en uno o varios de los dominios aceptados configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="b14cf-219">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="b14cf-220">Haga clic en el cuadro **Agregar una etiqueta** para ver y seleccionar un dominio.</span><span class="sxs-lookup"><span data-stu-id="b14cf-220">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="b14cf-221">Haga clic de nuevo en el cuadro **Agregar una etiqueta** para seleccionar dominios adicionales si hay más de un dominio disponible.</span><span class="sxs-lookup"><span data-stu-id="b14cf-221">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="b14cf-222">**Sender es**: especifica uno o varios usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="b14cf-222">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="b14cf-223">Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista.</span><span class="sxs-lookup"><span data-stu-id="b14cf-223">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="b14cf-224">Haga clic de nuevo **en el cuadro Agregar una etiqueta** para seleccionar remitentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="b14cf-224">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="b14cf-225">**El remitente es miembro de**: Especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="b14cf-225">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="b14cf-226">Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista.</span><span class="sxs-lookup"><span data-stu-id="b14cf-226">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="b14cf-227">Haga clic de nuevo **en el cuadro Agregar una etiqueta** para seleccionar remitentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="b14cf-227">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="b14cf-228">**Excepto si**: para agregar excepciones para la regla, haga clic en **Agregar una condición** tres veces para ver todas las excepciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="b14cf-228">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="b14cf-229">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="b14cf-229">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="b14cf-230">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-230">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="b14cf-231">Usar el Centro de seguridad & cumplimiento para ver directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-231">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="b14cf-232">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b14cf-233">En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir una directiva de correo no deseado ![ ](../../media/scc-expand-icon.png) saliente:</span><span class="sxs-lookup"><span data-stu-id="b14cf-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="b14cf-234">La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="b14cf-235">Una directiva personalizada que creó donde el valor de la columna **Tipo** es **Directiva de correo no deseado de salida personalizada.**</span><span class="sxs-lookup"><span data-stu-id="b14cf-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="b14cf-236">La configuración de directiva se muestra en los detalles de directiva expandido que aparecen o puede hacer clic en **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-236">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="b14cf-237">Usar el Centro de seguridad & cumplimiento para modificar directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-237">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="b14cf-238">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b14cf-239">En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir una directiva de correo no deseado ![ ](../../media/scc-expand-icon.png) saliente:</span><span class="sxs-lookup"><span data-stu-id="b14cf-239">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="b14cf-240">La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-240">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="b14cf-241">Una directiva personalizada que creó donde el valor de la columna **Tipo** es **Directiva de correo no deseado de salida personalizada.**</span><span class="sxs-lookup"><span data-stu-id="b14cf-241">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="b14cf-242">Haga clic en **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-242">Click **Edit policy**.</span></span>

<span data-ttu-id="b14cf-243">Para las directivas de correo no deseado saliente personalizadas, la configuración disponible en el control desplegable que aparece es idéntica a la descrita en la sección Usar el Centro de seguridad [& cumplimiento](#use-the-security--compliance-center-to-create-outbound-spam-policies) para crear directivas de correo no deseado salientes.</span><span class="sxs-lookup"><span data-stu-id="b14cf-243">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="b14cf-244">Para la directiva de correo no deseado  saliente predeterminada denominada Directiva de filtro de **correo** no deseado saliente, la sección Aplicado a no está disponible (la directiva se aplica a todos) y no se puede cambiar el nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="b14cf-244">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="b14cf-245">Vea las secciones siguientes para habilitar o deshabilitar una directiva, establecer el orden de prioridad de la directiva o configurar las notificaciones en cuarentena para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="b14cf-245">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="b14cf-246">Habilitar o deshabilitar directivas de correo no deseado salientes</span><span class="sxs-lookup"><span data-stu-id="b14cf-246">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="b14cf-247">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-247">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b14cf-248">En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir una directiva personalizada que haya creado (el valor de la columna Tipo es Directiva de correo no deseado de salida ![ ](../../media/scc-expand-icon.png) **personalizada).** </span><span class="sxs-lookup"><span data-stu-id="b14cf-248">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="b14cf-249">En los detalles de la directiva expandida que aparecen, observe el valor de la columna **Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-249">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="b14cf-250">Mueva el botón de alternancia a la izquierda para deshabilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="b14cf-250">Move the toggle to the left to disable the policy:</span></span> ![Deshabilitar](../../media/scc-toggle-off.png)

   <span data-ttu-id="b14cf-252">Mueva el botón de alternancia a la derecha para habilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="b14cf-252">Move the toggle to the right to enable the policy:</span></span> ![Habilitar](../../media/scc-toggle-on.png)

<span data-ttu-id="b14cf-254">No puede deshabilitar la directiva de correo no deseado saliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b14cf-254">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="b14cf-255">Establecer la prioridad de las directivas de correo no deseado saliente personalizadas</span><span class="sxs-lookup"><span data-stu-id="b14cf-255">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="b14cf-256">De forma predeterminada, las directivas de correo no deseado saliente tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="b14cf-256">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="b14cf-257">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="b14cf-257">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b14cf-258">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="b14cf-258">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="b14cf-259">Las directivas de correo no deseado saliente personalizadas se muestran en el orden en que se procesan (la primera directiva tiene el **valor de** prioridad 0).</span><span class="sxs-lookup"><span data-stu-id="b14cf-259">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="b14cf-260">La directiva de correo no deseado saliente predeterminada denominada Directiva de filtro de **correo** no deseado saliente tiene el valor de prioridad **Lowest** y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="b14cf-260">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="b14cf-261">Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="b14cf-261">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="b14cf-262">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b14cf-263">En la **página Configuración contra correo** no deseado,  busque las directivas donde el valor de la columna Tipo es Directiva de correo no deseado de **salida personalizada.**</span><span class="sxs-lookup"><span data-stu-id="b14cf-263">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="b14cf-264">Observe los valores de la columna **Prioridad**:</span><span class="sxs-lookup"><span data-stu-id="b14cf-264">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="b14cf-265">La directiva de correo no deseado saliente personalizada con la prioridad más alta tiene el valor ![ Flecha abajo icono ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-265">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="b14cf-266">La directiva de correo no deseado saliente personalizada con la prioridad más baja tiene el valor Flecha arriba ![ icono ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por ejemplo, ![ icono flecha arriba ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="b14cf-266">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="b14cf-267">Si tiene tres o más directivas de correo no deseado saliente personalizadas, las directivas entre la prioridad más alta y la más baja tienen valores Icono flecha arriba icono flecha ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ abajo ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (por ejemplo, icono flecha arriba icono flecha abajo ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ icono ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="b14cf-267">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="b14cf-268">Haga clic en</span><span class="sxs-lookup"><span data-stu-id="b14cf-268">Click</span></span> ![Icono flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="b14cf-270">o</span><span class="sxs-lookup"><span data-stu-id="b14cf-270">or</span></span> ![Icono flecha abajo](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="b14cf-272">para mover la directiva de correo no deseado saliente personalizada hacia arriba o hacia abajo en la lista de prioridad.</span><span class="sxs-lookup"><span data-stu-id="b14cf-272">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="b14cf-273">Usar el Centro de seguridad & cumplimiento para quitar directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-273">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="b14cf-274">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-274">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b14cf-275">En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir la directiva personalizada que desea eliminar (la columna Tipo es Directiva de correo no deseado de salida ![ ](../../media/scc-expand-icon.png) **personalizada).** </span><span class="sxs-lookup"><span data-stu-id="b14cf-275">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="b14cf-276">En los detalles de la directiva expandida que aparecen, haga clic en **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-276">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="b14cf-277">Haga clic en **Sí** en el mensaje de advertencia que se muestra.</span><span class="sxs-lookup"><span data-stu-id="b14cf-277">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="b14cf-278">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b14cf-278">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="b14cf-279">Usar Exchange Online PowerShell o PowerShell de EOP independiente para configurar directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-279">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="b14cf-280">Como se describió anteriormente, una directiva de correo no deseado saliente consta de una directiva de filtro de correo no deseado saliente y una regla de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-280">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="b14cf-281">En Exchange Online PowerShell o PowerShell independiente de EOP, la diferencia entre las directivas de filtro de correo no deseado saliente y las reglas de filtro de correo no deseado saliente es evidente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-281">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="b14cf-282">Las directivas de filtro de correo no deseado saliente se administran mediante los cmdlets **\* -HostedOutboundSpamFilterPolicy** y se administran las reglas de filtro de correo no deseado saliente mediante los cmdlets **\* -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="b14cf-282">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="b14cf-283">En PowerShell, primero se crea la directiva de filtro de correo no deseado saliente y, a continuación, se crea la regla de filtro de correo no deseado saliente que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="b14cf-283">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="b14cf-284">En PowerShell, modifica la configuración de la directiva de filtro de correo no deseado saliente y la regla de filtro de correo no deseado saliente por separado.</span><span class="sxs-lookup"><span data-stu-id="b14cf-284">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="b14cf-285">Al quitar una directiva de filtro de correo no deseado saliente de PowerShell, la regla de filtro de correo no deseado saliente correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="b14cf-285">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="b14cf-286">Usar PowerShell para crear directivas de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-286">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="b14cf-287">Crear una directiva de correo no deseado saliente en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="b14cf-287">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b14cf-288">Cree la directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-288">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="b14cf-289">Cree la regla de filtro de correo no deseado saliente que especifique la directiva de filtro de correo no deseado saliente a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="b14cf-289">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

> [!NOTE]
> - <span data-ttu-id="b14cf-290">Puede crear una nueva regla de filtro de correo no deseado saliente y asignarle una directiva de filtro de correo no deseado saliente existente y sin asociar.</span><span class="sxs-lookup"><span data-stu-id="b14cf-290">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="b14cf-291">Una regla de filtro de correo no deseado saliente no se puede asociar a más de una directiva de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-291">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
> 
> - <span data-ttu-id="b14cf-292">Puede configurar las siguientes opciones en las nuevas directivas de filtro de correo no deseado saliente en PowerShell que no están disponibles en el Centro de seguridad y cumplimiento de & hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="b14cf-292">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="b14cf-293">Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="b14cf-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
>   - <span data-ttu-id="b14cf-294">Establezca la prioridad de la directiva durante la creación (_Prioridad_ ) en _\<Number\>_ el cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="b14cf-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="b14cf-295">Una nueva directiva de filtro de correo no deseado saliente que cree en PowerShell no está visible en el Centro de seguridad y cumplimiento de & hasta que asigne la directiva a una regla de filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b14cf-295">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="b14cf-296">Paso 1: Usar PowerShell para crear una directiva de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-296">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="b14cf-297">Para crear una directiva de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b14cf-297">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="b14cf-298">En este ejemplo se crea una nueva directiva de filtro de correo no deseado saliente denominada Ejecutivos de Contoso con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="b14cf-298">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="b14cf-299">Los límites de velocidad de destinatarios están restringidos a valores más pequeños que los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b14cf-299">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="b14cf-300">Para obtener más información, vea [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="b14cf-300">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="b14cf-301">Una vez alcanzado uno de los límites, se impide que el usuario envíe mensajes.</span><span class="sxs-lookup"><span data-stu-id="b14cf-301">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="b14cf-302">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b14cf-302">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="b14cf-303">Paso 2: Usar PowerShell para crear una regla de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-303">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="b14cf-304">Para crear una regla de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b14cf-304">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="b14cf-305">En este ejemplo se crea una nueva regla de filtro de correo no deseado saliente denominada Ejecutivos de Contoso con esta configuración:</span><span class="sxs-lookup"><span data-stu-id="b14cf-305">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="b14cf-306">La directiva de filtro de correo no deseado saliente denominada Ejecutivos de Contoso está asociada a la regla.</span><span class="sxs-lookup"><span data-stu-id="b14cf-306">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="b14cf-307">La regla se aplica a los miembros del grupo denominado Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="b14cf-307">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="b14cf-308">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b14cf-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="b14cf-309">Usar PowerShell para ver directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-309">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="b14cf-310">Para devolver una lista resumida de todas las directivas de filtro de correo no deseado saliente, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="b14cf-310">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="b14cf-311">Para devolver información detallada sobre una directiva de filtro de correo no deseado saliente específica, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="b14cf-311">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="b14cf-312">En este ejemplo se devuelven todos los valores de propiedad de la directiva de filtro de correo no deseado saliente denominada Ejecutivos.</span><span class="sxs-lookup"><span data-stu-id="b14cf-312">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="b14cf-313">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b14cf-313">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="b14cf-314">Usar PowerShell para ver reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-314">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="b14cf-315">Para ver las reglas de filtro de correo no deseado saliente existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b14cf-315">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="b14cf-316">Para devolver una lista resumida de todas las reglas de filtro de correo no deseado saliente, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="b14cf-316">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="b14cf-317">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="b14cf-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="b14cf-318">Para devolver información detallada sobre una regla de filtro de correo no deseado saliente específica, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b14cf-318">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="b14cf-319">En este ejemplo se devuelven todos los valores de propiedad de la regla de filtro de correo no deseado saliente denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="b14cf-319">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="b14cf-320">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b14cf-320">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="b14cf-321">Usar PowerShell para modificar directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-321">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="b14cf-322">La misma configuración está disponible cuando se modifica una directiva de filtro de malware en PowerShell que cuando se crea la directiva como se describe en el paso [1:](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) Usar PowerShell para crear una directiva de filtro de correo no deseado saliente anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b14cf-322">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="b14cf-323">No puede cambiar el nombre de una directiva de filtro de correo no deseado saliente (el cmdlet **Set-HostedOutboundSpamFilterPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="b14cf-323">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b14cf-324">Al cambiar el nombre de una directiva de correo no deseado saliente en el Centro de seguridad & cumplimiento, solo se cambia el nombre de la regla de filtro de correo no _deseado saliente._</span><span class="sxs-lookup"><span data-stu-id="b14cf-324">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="b14cf-325">Para modificar una directiva de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b14cf-325">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b14cf-326">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b14cf-326">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="b14cf-327">Usar PowerShell para modificar reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-327">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="b14cf-328">La única configuración que no está disponible al modificar una regla de filtro de correo no deseado saliente en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="b14cf-328">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b14cf-329">Para habilitar o deshabilitar las reglas de filtro de correo no deseado saliente existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="b14cf-329">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="b14cf-330">De lo contrario, no hay ninguna configuración adicional disponible al modificar una regla de filtro de correo no deseado saliente en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b14cf-330">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="b14cf-331">La misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) para crear una regla de filtro de correo no deseado saliente anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b14cf-331">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="b14cf-332">Para modificar una regla de filtro de correo no deseado saliente, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b14cf-332">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b14cf-333">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b14cf-333">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="b14cf-334">Usar PowerShell para habilitar o deshabilitar reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-334">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="b14cf-335">Habilitar o deshabilitar una regla de filtro de correo no deseado saliente en PowerShell habilita o deshabilita toda la directiva de correo no deseado saliente (la regla de filtro de correo no deseado saliente y la directiva de filtro de correo no deseado saliente asignada).</span><span class="sxs-lookup"><span data-stu-id="b14cf-335">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="b14cf-336">No puede habilitar ni deshabilitar la directiva de correo no deseado saliente predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="b14cf-336">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="b14cf-337">Para habilitar o deshabilitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b14cf-337">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="b14cf-338">En este ejemplo se deshabilita la regla de filtro de correo no deseado saliente denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="b14cf-338">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="b14cf-339">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="b14cf-339">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="b14cf-340">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) y [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b14cf-340">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="b14cf-341">Usar PowerShell para establecer la prioridad de las reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-341">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="b14cf-342">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="b14cf-342">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="b14cf-343">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="b14cf-343">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="b14cf-344">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="b14cf-344">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="b14cf-345">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="b14cf-345">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="b14cf-346">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="b14cf-346">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b14cf-347">Para establecer la prioridad de una regla de filtro de correo no deseado saliente en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b14cf-347">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b14cf-348">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="b14cf-348">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="b14cf-349">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="b14cf-349">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="b14cf-350">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-HostedOutboundSpamFilterRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b14cf-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="b14cf-351">La directiva de filtro de correo no deseado predeterminada saliente no tiene una regla de filtro de correo no deseado correspondiente y siempre tiene el valor de prioridad no modificable **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="b14cf-351">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="b14cf-352">Usar PowerShell para quitar directivas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-352">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="b14cf-353">Cuando usa PowerShell para quitar una directiva de filtro de correo no deseado saliente, no se quita la regla de filtro de correo no deseado saliente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-353">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="b14cf-354">Para quitar una directiva de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b14cf-354">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b14cf-355">En este ejemplo se quita la directiva de filtro de correo no deseado saliente denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="b14cf-355">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b14cf-356">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b14cf-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="b14cf-357">Usar PowerShell para quitar reglas de filtro de correo no deseado saliente</span><span class="sxs-lookup"><span data-stu-id="b14cf-357">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="b14cf-358">Cuando usa PowerShell para quitar una regla de filtro de correo no deseado saliente, no se quita la directiva de filtro de correo no deseado saliente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b14cf-358">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="b14cf-359">Para quitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b14cf-359">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="b14cf-360">En este ejemplo se quita la regla de filtro de correo no deseado saliente denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="b14cf-360">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="b14cf-361">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="b14cf-361">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b14cf-362">Más información</span><span class="sxs-lookup"><span data-stu-id="b14cf-362">For more information</span></span>

[<span data-ttu-id="b14cf-363">Quitar usuarios bloqueados del portal de Usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="b14cf-363">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="b14cf-364">Grupo de entrega de alto riesgo para mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="b14cf-364">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="b14cf-365">Preguntas más frecuentes sobre la protección contra correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="b14cf-365">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="b14cf-366">Informe de mensajes reenviados automáticamente</span><span class="sxs-lookup"><span data-stu-id="b14cf-366">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)