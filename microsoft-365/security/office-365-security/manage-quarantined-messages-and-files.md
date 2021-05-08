---
title: Administrar mensajes en cuarentena y archivos como administrador
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a ver y administrar mensajes en cuarentena para todos los usuarios de Exchange Online Protection (EOP). Los administradores de organizaciones con Microsoft Defender para Office 365 también pueden administrar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c5e2d6a3729a24766652d4c7c0973c63b1dcb207
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272209"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="8d563-104">Administración de mensajes en cuarentena y archivos como administrador en EOP</span><span class="sxs-lookup"><span data-stu-id="8d563-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8d563-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="8d563-105">**Applies to**</span></span>
- [<span data-ttu-id="8d563-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8d563-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8d563-107">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8d563-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8d563-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d563-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8d563-109">En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados.</span><span class="sxs-lookup"><span data-stu-id="8d563-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="8d563-110">Para obtener más información, vea [Quarantined email messages in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="8d563-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="8d563-111">Los administradores pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8d563-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="8d563-112">Solo los administradores pueden administrar mensajes que se han puesto en cuarentena como malware, phishing de elevada confianza o como resultado de reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="8d563-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="8d563-113">Los administradores también pueden notificar falsos positivos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d563-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="8d563-114">Los administradores de organizaciones con Microsoft Defender para Office 365 también pueden ver, descargar y eliminar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d563-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="8d563-115">Puede ver y administrar mensajes en cuarentena en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="8d563-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8d563-116">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="8d563-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8d563-117">Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="8d563-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="8d563-118">Para abrir directamente la página de Cuarentena, vaya a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="8d563-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="8d563-119">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8d563-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8d563-120">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="8d563-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8d563-121">Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="8d563-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8d563-122">Para realizar acciones en los mensajes en cuarentena para todos los usuarios, debe ser miembro de los grupos de roles Administración de la **organización,** Administrador de seguridad **o** Administrador <sup>\*</sup> de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="8d563-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="8d563-123">Para obtener acceso de solo lectura a mensajes en cuarentena para todos los usuarios, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="8d563-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="8d563-124">Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="8d563-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="8d563-125">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="8d563-125">**Notes**:</span></span>

  - <span data-ttu-id="8d563-126">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d563-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8d563-127">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8d563-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="8d563-128">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="8d563-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="8d563-129"><sup>\*</sup>Los miembros **del** grupo de roles Administrador de cuarentena también deben ser miembros del grupo de roles **Administración** de higiene en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) para realizar procedimientos de cuarentena en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d563-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="8d563-130">Los mensajes en cuarentena se conservan durante un período de tiempo predeterminado antes de que se eliminen automáticamente:</span><span class="sxs-lookup"><span data-stu-id="8d563-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="8d563-131">30 días para los mensajes en cuarentena por directivas contra correo no deseado (correo no deseado, suplantación de identidad y correo electrónico masivo).</span><span class="sxs-lookup"><span data-stu-id="8d563-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="8d563-132">Este es el valor predeterminado y máximo.</span><span class="sxs-lookup"><span data-stu-id="8d563-132">This is the default and maximum value.</span></span> <span data-ttu-id="8d563-133">Para configurar (inferior) este valor, vea [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8d563-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="8d563-134">15 días para los mensajes que contienen malware.</span><span class="sxs-lookup"><span data-stu-id="8d563-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="8d563-135">15 días para los archivos en cuarentena por Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams en Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="8d563-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="8d563-136">Cuando un mensaje expira de la cuarentena, no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="8d563-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="8d563-137">Usar el Centro de seguridad & cumplimiento para administrar mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="8d563-138">Ver correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-138">View quarantined email</span></span>

1. <span data-ttu-id="8d563-139">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="8d563-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="8d563-140">Compruebe que **Ver en cuarentena** esté configurado en el valor predeterminado **correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="8d563-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="8d563-141">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="8d563-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="8d563-142">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="8d563-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="8d563-143">Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="8d563-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="8d563-144">**Recibido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-145">**Remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-146">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-147">**Motivo de la cuarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-148">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-149">**Tipo de directiva**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-150">**Expires**</span><span class="sxs-lookup"><span data-stu-id="8d563-150">**Expires**</span></span>
   - <span data-ttu-id="8d563-151">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="8d563-151">**Recipient**</span></span>
   - <span data-ttu-id="8d563-152">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="8d563-152">**Message ID**</span></span>
   - <span data-ttu-id="8d563-153">**Nombre de la directiva**</span><span class="sxs-lookup"><span data-stu-id="8d563-153">**Policy name**</span></span>
   - <span data-ttu-id="8d563-154">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="8d563-154">**Size**</span></span>
   - <span data-ttu-id="8d563-155">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="8d563-155">**Direction**</span></span>

   <span data-ttu-id="8d563-156">Cuando haya terminado, haga clic en **Guardar** o en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="8d563-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="8d563-157">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="8d563-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="8d563-158">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="8d563-158">The available filters are:</span></span>

   - <span data-ttu-id="8d563-159">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="8d563-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="8d563-160">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="8d563-160">**Today**</span></span>
     - <span data-ttu-id="8d563-161">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="8d563-161">**Next 2 days**</span></span>
     - <span data-ttu-id="8d563-162">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="8d563-162">**Next 7 days**</span></span>
     - <span data-ttu-id="8d563-163">**Personalizado**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="8d563-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="8d563-164">**Hora de recepción**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="8d563-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="8d563-165">**Motivo de la cuarentena**:</span><span class="sxs-lookup"><span data-stu-id="8d563-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="8d563-166">**Directiva:** el mensaje coincide con las condiciones de una regla de flujo de correo (también conocida como regla de transporte).</span><span class="sxs-lookup"><span data-stu-id="8d563-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="8d563-167">**Masivo**</span><span class="sxs-lookup"><span data-stu-id="8d563-167">**Bulk**</span></span>
     - <span data-ttu-id="8d563-168">**Phish:** el veredicto de filtro de correo no deseado era **correo** electrónico de suplantación de identidad o protección contra suplantación de identidad en cuarentena el mensaje [(](set-up-anti-phishing-policies.md#spoof-settings) configuración de suplantación o protección [de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="8d563-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="8d563-169">**Malware**</span><span class="sxs-lookup"><span data-stu-id="8d563-169">**Malware**</span></span>
     - <span data-ttu-id="8d563-170">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="8d563-170">**Spam**</span></span>
     - <span data-ttu-id="8d563-171">**Phish de elevada confianza**</span><span class="sxs-lookup"><span data-stu-id="8d563-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="8d563-172">**Tipo de directiva**: Filtrar mensajes por tipo de directiva:</span><span class="sxs-lookup"><span data-stu-id="8d563-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="8d563-173">**Directiva antimalware**</span><span class="sxs-lookup"><span data-stu-id="8d563-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="8d563-174">**Caja fuerte Directiva de datos adjuntos**</span><span class="sxs-lookup"><span data-stu-id="8d563-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="8d563-175">**Política Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="8d563-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="8d563-176">**Directiva de filtro de contenido alojado** (directiva anti-spam)</span><span class="sxs-lookup"><span data-stu-id="8d563-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="8d563-177">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="8d563-177">**Transport rule**</span></span>

   - <span data-ttu-id="8d563-178">**Destinatario de correo** electrónico: todos los usuarios o solo los mensajes que se le envíen.</span><span class="sxs-lookup"><span data-stu-id="8d563-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="8d563-179">Los usuarios finales solo pueden administrar los mensajes en cuarentena que se les envíen.</span><span class="sxs-lookup"><span data-stu-id="8d563-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="8d563-180">Para borrar el filtro, haga clic en **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="8d563-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="8d563-181">Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="8d563-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="8d563-182">Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="8d563-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="8d563-183">No se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="8d563-183">Wildcards aren't supported.</span></span> <span data-ttu-id="8d563-184">Puede buscar según los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="8d563-184">You can search by the following values:</span></span>

   - <span data-ttu-id="8d563-185">**Id. de mensaje**: El identificador único global del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8d563-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="8d563-186">Por ejemplo, usó [el](message-trace-scc.md) seguimiento de mensajes para buscar un mensaje que se envió a un usuario de la organización y se determina que el mensaje se ha puesto en cuarentena en lugar de entregarse.</span><span class="sxs-lookup"><span data-stu-id="8d563-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="8d563-187">Asegúrese de incluir el valor de identificador de mensaje completo, que puede incluir corchetes angulares ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="8d563-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="8d563-188">Por ejemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="8d563-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="8d563-189">**Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.</span><span class="sxs-lookup"><span data-stu-id="8d563-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="8d563-190">**Nombre de directiva**: Use el nombre de la Directiva completa del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8d563-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="8d563-191">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8d563-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="8d563-192">**Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.</span><span class="sxs-lookup"><span data-stu-id="8d563-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="8d563-193">**Asunto**: Use el asunto completo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8d563-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="8d563-194">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8d563-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="8d563-195">**Nombre de** la directiva: el nombre de la directiva responsable de la anulación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8d563-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="8d563-196">Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="8d563-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="8d563-197">Cuando encuentre un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar una acción (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="8d563-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="8d563-198">Ver detalles de mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-198">View quarantined message details</span></span>

<span data-ttu-id="8d563-199">Cuando selecciona un mensaje de correo electrónico de la lista, aparecen los detalles de mensaje siguientes en el panel flotante **Detalles**:</span><span class="sxs-lookup"><span data-stu-id="8d563-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="8d563-200">**Id. de mensaje**: El identificador único global para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8d563-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="8d563-201">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="8d563-201">**Sender address**</span></span>

- <span data-ttu-id="8d563-202">**Recibido**: La fecha/hora en que se ha recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8d563-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="8d563-203">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="8d563-203">**Subject**</span></span>

- <span data-ttu-id="8d563-204">**Motivo de cuarentena:** muestra si un mensaje se ha identificado como **Correo** no deseado **,** Masivo , **Phish**, coincide con una regla de flujo de correo (**regla** de transporte ), o si se identificó como que contiene **malware**.</span><span class="sxs-lookup"><span data-stu-id="8d563-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="8d563-205">**Recuento de destinatarios**</span><span class="sxs-lookup"><span data-stu-id="8d563-205">**Recipient count**</span></span>

- <span data-ttu-id="8d563-206">**Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="8d563-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="8d563-207">**Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="8d563-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="8d563-208">**Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.</span><span class="sxs-lookup"><span data-stu-id="8d563-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="8d563-209">**Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.</span><span class="sxs-lookup"><span data-stu-id="8d563-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="8d563-210">Llevar a cabo una acción en un correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-210">Take action on quarantined email</span></span>

<span data-ttu-id="8d563-211">Después de seleccionar un mensaje, tiene varias opciones para qué hacer con los mensajes en el **panel** desplegable Detalles:</span><span class="sxs-lookup"><span data-stu-id="8d563-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="8d563-212">**Mensaje de versión:** en el panel desplegable que aparece, elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8d563-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="8d563-213">**Notificar mensajes a Microsoft para su** análisis: está seleccionado de forma predeterminada e informa el mensaje erróneamente en cuarentena a Microsoft como falso positivo.</span><span class="sxs-lookup"><span data-stu-id="8d563-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="8d563-214">Si el mensaje se ha puesto en cuarentena como correo no deseado, masivo, suplantación de identidad (phishing) o que contiene malware, el mensaje también se notifica al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d563-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="8d563-215">Según su análisis, las reglas de filtro de correo no deseado de todo el servicio podrían ajustarse para permitir la entrada del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8d563-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="8d563-216">Elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8d563-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="8d563-217">**Liberar mensajes a todos los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="8d563-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="8d563-218">**Liberar mensajes a destinatarios específicos**</span><span class="sxs-lookup"><span data-stu-id="8d563-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="8d563-219">**Liberar mensajes a otras personas:** tenga en cuenta que no se admite liberar mensajes de malware a personas que no son destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="8d563-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="8d563-220">Cuando haya terminado, haga clic en **Liberar mensajes**.</span><span class="sxs-lookup"><span data-stu-id="8d563-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="8d563-221">Notas sobre cómo liberar mensajes:</span><span class="sxs-lookup"><span data-stu-id="8d563-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="8d563-222">No puede liberar un mensaje al mismo destinatario más de una vez.</span><span class="sxs-lookup"><span data-stu-id="8d563-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="8d563-223">Solo los destinatarios que no hayan recibido el mensaje aparecerán en la lista de posibles destinatarios.</span><span class="sxs-lookup"><span data-stu-id="8d563-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="8d563-224">**Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8d563-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="8d563-225">Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Microsoft 365 complete esta tarea).</span><span class="sxs-lookup"><span data-stu-id="8d563-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="8d563-226">Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:</span><span class="sxs-lookup"><span data-stu-id="8d563-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="8d563-227">**Vista previa del mensaje**: En el panel flotante que aparece, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8d563-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="8d563-228">**Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.</span><span class="sxs-lookup"><span data-stu-id="8d563-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="8d563-229">**Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="8d563-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="8d563-230">**Quitar de la cuarentena:** después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="8d563-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="8d563-231">**Descargar mensaje**: En el panel de flotante que aparece, seleccione **Entiendo los riesgos de descargar este mensaje** para guardar una copia local del mensaje en formato .eml.</span><span class="sxs-lookup"><span data-stu-id="8d563-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="8d563-232">**Bloquear remitente:** agregue el remitente a la lista Remitentes bloqueados del buzón.</span><span class="sxs-lookup"><span data-stu-id="8d563-232">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="8d563-233">Para obtener más información, vea [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="8d563-233">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="8d563-234">**Enviar mensaje:** en el panel desplegable que aparece, elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8d563-234">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="8d563-235">**Tipo de objeto**: **Correo electrónico** (predeterminado), **DIRECCIÓN URL** o **Datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="8d563-235">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="8d563-236">**Formato de envío:** **Id.** de mensaje de red (predeterminado, con el valor correspondiente en el cuadro **Id.** de mensaje de red) o **Archivo** (vaya a un archivo .eml o .msg local).</span><span class="sxs-lookup"><span data-stu-id="8d563-236">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="8d563-237">Tenga en cuenta que si selecciona **Archivo** y, a continuación, selecciona **Id. de mensaje** de red, el valor inicial se ha ido.</span><span class="sxs-lookup"><span data-stu-id="8d563-237">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="8d563-238">**Destinatarios:** escriba en concesión un destinatario original del mensaje o haga clic en **Seleccionar** todo para identificar todos los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="8d563-238">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="8d563-239">También puede hacer clic en **Seleccionar todo y,** a continuación, quitar selectivamente los destinatarios individuales.</span><span class="sxs-lookup"><span data-stu-id="8d563-239">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="8d563-240">**Motivo del envío:** **no debería haber sido bloqueado** (predeterminado) o debería haber sido **bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="8d563-240">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="8d563-241">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="8d563-241">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="8d563-242">Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8d563-242">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="8d563-243">Realice una acción en varios mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-243">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="8d563-244">Al seleccionar varios mensajes en cuarentena de la lista (hasta 100), se mostrará el panel de control flotante **Acciones en masa**, donde puede realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d563-244">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="8d563-245">**Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar **Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.</span><span class="sxs-lookup"><span data-stu-id="8d563-245">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8d563-246">Tenga en cuenta el siguiente escenario: john@gmail.com envía un mensaje a faith@contoso.com y john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8d563-246">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="8d563-247">Gmail bifurca este mensaje en dos copias que se enrutan a la cuarentena como phishing en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d563-247">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="8d563-248">Un administrador libera ambos mensajes para admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8d563-248">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="8d563-249">Se entrega el primer mensaje publicado que llega al buzón de administración.</span><span class="sxs-lookup"><span data-stu-id="8d563-249">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="8d563-250">El segundo mensaje liberado se identifica como entrega duplicada y se omite.</span><span class="sxs-lookup"><span data-stu-id="8d563-250">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="8d563-251">Los mensajes se identifican como duplicados si tienen el mismo identificador de mensaje y el mismo tiempo recibido.</span><span class="sxs-lookup"><span data-stu-id="8d563-251">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="8d563-252">**Eliminar mensajes:** después de hacer clic en **Sí** en la advertencia que aparece, los mensajes se eliminan inmediatamente sin que se envíen a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="8d563-252">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="8d563-253">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="8d563-253">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="8d563-254">Solo Microsoft Defender para Office 365: Use el Centro de seguridad & cumplimiento para administrar archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-254">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="8d563-255">Los procedimientos para los archivos en cuarentena de esta sección solo están disponibles para suscriptores de Microsoft Defender para Office 365 Plan 1 y Plan 2.</span><span class="sxs-lookup"><span data-stu-id="8d563-255">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="8d563-256">En organizaciones con Defender para Office 365, los administradores pueden administrar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d563-256">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="8d563-257">Para habilitar la protección de estos archivos, vea Activar datos adjuntos seguros para [SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8d563-257">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="8d563-258">Ver archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-258">View quarantined files</span></span>

1. <span data-ttu-id="8d563-259">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="8d563-259">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="8d563-260">Cambiar **Vista en cuarentena a** los archivos de **valor**.</span><span class="sxs-lookup"><span data-stu-id="8d563-260">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="8d563-261">Puede ordenar un campo haciendo clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="8d563-261">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="8d563-262">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="8d563-262">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="8d563-263">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="8d563-263">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="8d563-264">Las columnas predeterminadas se marcan con un asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="8d563-264">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="8d563-265">**Usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-265">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-266">**Ubicación**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-266">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-267">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-267">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-268">**DIRECCIÓN URL de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-268">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-269">**Tamaño de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-269">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-270">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-270">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-271">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8d563-271">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="8d563-272">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="8d563-272">**Detected by**</span></span>
   - <span data-ttu-id="8d563-273">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="8d563-273">**Modified by time**</span></span>

4. <span data-ttu-id="8d563-274">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="8d563-274">To filter the results, click **Filter**.</span></span> <span data-ttu-id="8d563-275">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="8d563-275">The available filters are:</span></span>

   - <span data-ttu-id="8d563-276">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="8d563-276">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="8d563-277">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="8d563-277">**Today**</span></span>
     - <span data-ttu-id="8d563-278">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="8d563-278">**Next 2 days**</span></span>
     - <span data-ttu-id="8d563-279">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="8d563-279">**Next 7 days**</span></span>
     - <span data-ttu-id="8d563-280">Un intervalo de fecha y hora personalizado.</span><span class="sxs-lookup"><span data-stu-id="8d563-280">A custom date/time range.</span></span>
   - <span data-ttu-id="8d563-281">**Tiempo recibido**</span><span class="sxs-lookup"><span data-stu-id="8d563-281">**Received time**</span></span>
   - <span data-ttu-id="8d563-282">**Motivo de cuarentena:** el único valor disponible es **Malware**.</span><span class="sxs-lookup"><span data-stu-id="8d563-282">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="8d563-283">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="8d563-283">**Policy type**</span></span>

<span data-ttu-id="8d563-284">Después de encontrar un archivo en cuarentena específico, seleccione el archivo para ver detalles sobre él y para realizar acciones sobre él (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="8d563-284">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="8d563-285">Ver detalles del archivo en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-285">View quarantined file details</span></span>

<span data-ttu-id="8d563-286">Al seleccionar un archivo en la lista, los siguientes detalles de archivo aparecen en el **panel** desplegable Detalles:</span><span class="sxs-lookup"><span data-stu-id="8d563-286">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="8d563-287">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="8d563-287">**File Name**</span></span>
- <span data-ttu-id="8d563-288">**Dirección URL de** archivo: dirección URL que define la ubicación del archivo (por ejemplo, en SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="8d563-288">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="8d563-289">**Contenido malintencionado detectado en** La fecha y hora en que el archivo se ha puesto en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="8d563-289">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="8d563-290">**Expira:** la fecha en la que el archivo se eliminará de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="8d563-290">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="8d563-291">**Detectado por**: Defender para Office 365 o el motor antimalware de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d563-291">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="8d563-292">**¿Liberado?**</span><span class="sxs-lookup"><span data-stu-id="8d563-292">**Released?**</span></span>
- <span data-ttu-id="8d563-293">**Nombre de malware**</span><span class="sxs-lookup"><span data-stu-id="8d563-293">**Malware Name**</span></span>
- <span data-ttu-id="8d563-294">**Id. de** documento: identificador único del documento.</span><span class="sxs-lookup"><span data-stu-id="8d563-294">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="8d563-295">**Tamaño de archivo:** en kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="8d563-295">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="8d563-296">**Organización** Id. único de la organización.</span><span class="sxs-lookup"><span data-stu-id="8d563-296">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="8d563-297">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="8d563-297">**Last modified**</span></span>
- <span data-ttu-id="8d563-298">**Modified By:** el usuario que modificó por última vez el archivo.</span><span class="sxs-lookup"><span data-stu-id="8d563-298">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="8d563-299">Valor de algoritmo hash seguro de **256 bits (SHA-256):** puede usar este valor hash para identificar el archivo en otros almacenes de reputación o en otras ubicaciones del entorno.</span><span class="sxs-lookup"><span data-stu-id="8d563-299">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="8d563-300">Realizar acciones en archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-300">Take action on quarantined files</span></span>

<span data-ttu-id="8d563-301">Al seleccionar un archivo en la lista, puede realizar las siguientes acciones en el archivo en el panel **desplegable** Detalles:</span><span class="sxs-lookup"><span data-stu-id="8d563-301">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="8d563-302">**Liberar archivos:** seleccione (predeterminado) o anule la selección de Archivos de informe en **Microsoft** para su análisis y, a continuación, haga clic **en Liberar archivos**.</span><span class="sxs-lookup"><span data-stu-id="8d563-302">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="8d563-303">**Descargar archivo**</span><span class="sxs-lookup"><span data-stu-id="8d563-303">**Download file**</span></span>
- <span data-ttu-id="8d563-304">**Quitar archivo de cuarentena**</span><span class="sxs-lookup"><span data-stu-id="8d563-304">**Remove file from quarantine**</span></span>

<span data-ttu-id="8d563-305">Si no libera o quita los archivos, se eliminarán después de que expire el período de retención de cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8d563-305">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="8d563-306">Acciones en varios archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-306">Actions on multiple quarantined files</span></span>

<span data-ttu-id="8d563-307">Al seleccionar varios archivos en cuarentena en la lista (hasta 100), aparece el panel desplegable Acciones masivas donde puede realizar las siguientes acciones: </span><span class="sxs-lookup"><span data-stu-id="8d563-307">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="8d563-308">**Liberar archivos**</span><span class="sxs-lookup"><span data-stu-id="8d563-308">**Release files**</span></span>
- <span data-ttu-id="8d563-309">**Eliminar archivos:** después de hacer clic en **Sí** en la advertencia que aparece, los archivos se eliminan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="8d563-309">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="8d563-310">Usar Exchange Online PowerShell o PowerShell de EOP independiente para ver y administrar mensajes y archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8d563-310">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="8d563-311">Los cmdlets que usa para ver y administrar mensajes y archivos en cuarentena son:</span><span class="sxs-lookup"><span data-stu-id="8d563-311">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="8d563-312">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="8d563-312">Delete-QuarantineMessage</span></span>](/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="8d563-313">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="8d563-313">Export-QuarantineMessage</span></span>](/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="8d563-314">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="8d563-314">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="8d563-315">[Preview-QuarantineMessage:](/powershell/module/exchange/preview-quarantinemessage)tenga en cuenta que este cmdlet solo es para mensajes, no archivos en cuarentena de datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d563-315">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not quarantined files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="8d563-316">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="8d563-316">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)
