---
title: Administrar mensajes en cuarentena y archivos como administrador
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
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
description: Los administradores pueden obtener información sobre cómo ver y administrar los mensajes en cuarentena para todos los usuarios en Exchange Online Protection (EOP). Los administradores de organizaciones con Microsoft defender para Office 365 también pueden administrar los archivos en cuarentena en SharePoint Online, OneDrive para la empresa y Microsoft Teams.
ms.openlocfilehash: fed05ee202e4352200a80516e0ec1b62c8421178
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357138"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="9b831-104">Administración de mensajes en cuarentena y archivos como administrador en EOP</span><span class="sxs-lookup"><span data-stu-id="9b831-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9b831-105">En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados.</span><span class="sxs-lookup"><span data-stu-id="9b831-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="9b831-106">Para obtener más información, vea [mensajes de correo electrónico en cuarentena en EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9b831-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="9b831-107">Los administradores pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9b831-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="9b831-108">Solo los administradores pueden administrar los mensajes que se pusieron en cuarentena como malware, la suplantación de identidad de confianza alta o como resultado de las reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="9b831-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="9b831-109">Los administradores también pueden informar de falsos positivos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b831-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="9b831-110">Los administradores de organizaciones con Microsoft defender para Office 365 también pueden ver, descargar y eliminar archivos en cuarentena en SharePoint Online, OneDrive para la empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b831-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="9b831-111">Puede ver y administrar los mensajes en cuarentena en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones de correo en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de correo de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="9b831-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9b831-112">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="9b831-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9b831-113">Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="9b831-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="9b831-114">Para abrir directamente la página de Cuarentena, vaya a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="9b831-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="9b831-115">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9b831-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9b831-116">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="9b831-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9b831-117">Debe tener permisos asignados para poder administrar la cuarentena como administrador. Los permisos se controlan mediante el rol **cuarentena** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9b831-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="9b831-118">De forma predeterminada, este rol se asigna a los grupos de roles administración de la **organización** (administradores globales), **Administrador de cuarentena** y administrador de **seguridad** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9b831-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="9b831-119">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9b831-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="9b831-120">Los mensajes en cuarentena se conservan durante un período de tiempo predeterminado antes de que se eliminen automáticamente:</span><span class="sxs-lookup"><span data-stu-id="9b831-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="9b831-121">30 días para los mensajes puestos en cuarentena por las directivas contra correo no deseado (correo no deseado, phishing y correo electrónico masivo).</span><span class="sxs-lookup"><span data-stu-id="9b831-121">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="9b831-122">Este es el valor predeterminado y máximo.</span><span class="sxs-lookup"><span data-stu-id="9b831-122">This is the default and maximum value.</span></span> <span data-ttu-id="9b831-123">Para configurar (menos) este valor, vea [Configure anti-spam Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9b831-123">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="9b831-124">15 días para los mensajes que contienen malware.</span><span class="sxs-lookup"><span data-stu-id="9b831-124">15 days for messages that contain malware.</span></span>

  - <span data-ttu-id="9b831-125">15 días para los archivos en cuarentena por ATP para SharePoint, OneDrive y Microsoft Teams en defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="9b831-125">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="9b831-126">Cuando un mensaje expira de la cuarentena, no puede recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="9b831-126">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="9b831-127">Usar el centro de seguridad & cumplimiento para administrar los mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-127">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="9b831-128">Ver el correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-128">View quarantined email</span></span>

1. <span data-ttu-id="9b831-129">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="9b831-129">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="9b831-130">Compruebe que **vista en cuarentena** se haya establecido en el **correo** de valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9b831-130">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="9b831-131">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="9b831-131">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="9b831-132">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="9b831-132">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="9b831-133">Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="9b831-133">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="9b831-134">**Recibido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-134">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-135">**Remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-135">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-136">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-136">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-137">**Motivo de la cuarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-137">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-138">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-138">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-139">**Tipo de directiva**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-139">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-140">**Expires**</span><span class="sxs-lookup"><span data-stu-id="9b831-140">**Expires**</span></span>
   - <span data-ttu-id="9b831-141">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="9b831-141">**Recipient**</span></span>
   - <span data-ttu-id="9b831-142">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="9b831-142">**Message ID**</span></span>
   - <span data-ttu-id="9b831-143">**Nombre de la directiva**</span><span class="sxs-lookup"><span data-stu-id="9b831-143">**Policy name**</span></span>
   - <span data-ttu-id="9b831-144">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="9b831-144">**Size**</span></span>
   - <span data-ttu-id="9b831-145">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="9b831-145">**Direction**</span></span>

   <span data-ttu-id="9b831-146">Cuando haya terminado, haga clic en **Guardar** o en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="9b831-146">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="9b831-147">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="9b831-147">To filter the results, click **Filter**.</span></span> <span data-ttu-id="9b831-148">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="9b831-148">The available filters are:</span></span>

   - <span data-ttu-id="9b831-149">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="9b831-149">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="9b831-150">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="9b831-150">**Today**</span></span>
     - <span data-ttu-id="9b831-151">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="9b831-151">**Next 2 days**</span></span>
     - <span data-ttu-id="9b831-152">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="9b831-152">**Next 7 days**</span></span>
     - <span data-ttu-id="9b831-153">**Personalizado**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="9b831-153">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="9b831-154">**Hora de recepción**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="9b831-154">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="9b831-155">**Motivo de la cuarentena**:</span><span class="sxs-lookup"><span data-stu-id="9b831-155">**Quarantine reason**:</span></span>
     - <span data-ttu-id="9b831-156">**Directiva**: el mensaje coincide con las condiciones de una regla de flujo de correo (también denominada regla de transporte).</span><span class="sxs-lookup"><span data-stu-id="9b831-156">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="9b831-157">**Masivo**</span><span class="sxs-lookup"><span data-stu-id="9b831-157">**Bulk**</span></span>
     - <span data-ttu-id="9b831-158">**Phish**: el filtro de correo no deseado el veredicto fue **phishing email** o anti-phishing Protection en cuarentena del mensaje ([configuración de falsificación](set-up-anti-phishing-policies.md#spoof-settings) o [protección de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="9b831-158">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="9b831-159">**Malware**</span><span class="sxs-lookup"><span data-stu-id="9b831-159">**Malware**</span></span>
     - <span data-ttu-id="9b831-160">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="9b831-160">**Spam**</span></span>
     - <span data-ttu-id="9b831-161">**Phish de confianza alta**</span><span class="sxs-lookup"><span data-stu-id="9b831-161">**High Confidence Phish**</span></span>

   - <span data-ttu-id="9b831-162">**Tipo de directiva**: Filtrar mensajes por tipo de directiva:</span><span class="sxs-lookup"><span data-stu-id="9b831-162">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="9b831-163">**Directiva antimalware**</span><span class="sxs-lookup"><span data-stu-id="9b831-163">**Anti-malware policy**</span></span>
     - <span data-ttu-id="9b831-164">**Directiva de datos adjuntos seguros**</span><span class="sxs-lookup"><span data-stu-id="9b831-164">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="9b831-165">**Política Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="9b831-165">**Anti-phish policy**</span></span>
     - <span data-ttu-id="9b831-166">**Directiva de filtro de contenido alojado** (directiva anti-spam)</span><span class="sxs-lookup"><span data-stu-id="9b831-166">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="9b831-167">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="9b831-167">**Transport rule**</span></span>

   - <span data-ttu-id="9b831-168">**Destinatario de correo electrónico**: todos los usuarios o solo los mensajes que se le envíen.</span><span class="sxs-lookup"><span data-stu-id="9b831-168">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="9b831-169">Los usuarios finales solo pueden administrar los mensajes en cuarentena que se les envían.</span><span class="sxs-lookup"><span data-stu-id="9b831-169">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="9b831-170">Para borrar el filtro, haga clic en **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="9b831-170">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="9b831-171">Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="9b831-171">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="9b831-172">Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="9b831-172">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="9b831-173">No se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="9b831-173">Wildcards aren't supported.</span></span> <span data-ttu-id="9b831-174">Puede buscar según los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="9b831-174">You can search by the following values:</span></span>

   - <span data-ttu-id="9b831-175">**Id. de mensaje**: El identificador único global del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b831-175">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="9b831-176">Por ejemplo, usó el [seguimiento de mensajes](message-trace-scc.md) para buscar un mensaje que se envió a un usuario de su organización y usted determina que el mensaje se puso en cuarentena en lugar de entregarse.</span><span class="sxs-lookup"><span data-stu-id="9b831-176">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="9b831-177">Asegúrese de incluir el valor completo del identificador de mensaje, que puede incluir corchetes angulares ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="9b831-177">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="9b831-178">Por ejemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="9b831-178">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="9b831-179">**Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.</span><span class="sxs-lookup"><span data-stu-id="9b831-179">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="9b831-180">**Nombre de directiva**: Use el nombre de la Directiva completa del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b831-180">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="9b831-181">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9b831-181">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="9b831-182">**Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.</span><span class="sxs-lookup"><span data-stu-id="9b831-182">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="9b831-183">**Asunto**: Use el asunto completo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b831-183">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="9b831-184">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9b831-184">The search is not case-sensitive.</span></span>
  
   - <span data-ttu-id="9b831-185">**Nombre** de la Directiva: nombre de la Directiva que era responsable de poner en cuarentena el mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b831-185">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="9b831-186">Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="9b831-186">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="9b831-187">Cuando encuentre un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar una acción (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="9b831-187">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="9b831-188">Ver detalles de mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-188">View quarantined message details</span></span>

<span data-ttu-id="9b831-189">Cuando selecciona un mensaje de correo electrónico de la lista, aparecen los detalles de mensaje siguientes en el panel flotante **Detalles**:</span><span class="sxs-lookup"><span data-stu-id="9b831-189">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="9b831-190">**Id. de mensaje**: El identificador único global para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b831-190">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="9b831-191">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="9b831-191">**Sender address**</span></span>

- <span data-ttu-id="9b831-192">**Recibido**: La fecha/hora en que se ha recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b831-192">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="9b831-193">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="9b831-193">**Subject**</span></span>

- <span data-ttu-id="9b831-194">**Motivo de cuarentena**: muestra si un mensaje se ha identificado **como correo no deseado**, en **masa**, **phish**, coincide con una regla de flujo de correo (**regla de transporte**) o se identificó como **malware** que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="9b831-194">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="9b831-195">**Número de destinatarios**</span><span class="sxs-lookup"><span data-stu-id="9b831-195">**Recipient count**</span></span>

- <span data-ttu-id="9b831-196">**Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="9b831-196">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="9b831-197">**Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="9b831-197">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="9b831-198">**Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.</span><span class="sxs-lookup"><span data-stu-id="9b831-198">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="9b831-199">**Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.</span><span class="sxs-lookup"><span data-stu-id="9b831-199">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="9b831-200">Llevar a cabo una acción en un correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-200">Take action on quarantined email</span></span>

<span data-ttu-id="9b831-201">Después de seleccionar un mensaje, tiene varias opciones para qué hacer con los mensajes en el panel flotante **detalles** :</span><span class="sxs-lookup"><span data-stu-id="9b831-201">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="9b831-202">**Mensaje de liberación**: en el panel flotante que aparece, elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9b831-202">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="9b831-203">**Notificar mensajes a Microsoft para su análisis**: esta opción está seleccionada de forma predeterminada y notifica a Microsoft el mensaje con una cuarentena incorrecta como falso positivo.</span><span class="sxs-lookup"><span data-stu-id="9b831-203">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="9b831-204">Si el mensaje se puso en cuarentena como correo no deseado, en masa o con suplantación de identidad o con malware, el mensaje también se notifica al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b831-204">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="9b831-205">Según el análisis, las reglas de filtro de correo no deseado de todo el servicio podrían ajustarse para permitir el paso del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b831-205">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="9b831-206">Elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9b831-206">Choose one of the following options:</span></span>
    - <span data-ttu-id="9b831-207">**Liberar mensajes para todos los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="9b831-207">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="9b831-208">**Liberar mensajes a destinatarios específicos**</span><span class="sxs-lookup"><span data-stu-id="9b831-208">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="9b831-209">**Liberar mensajes para otros usuarios**: no se admite la liberación de mensajes de malware a otros usuarios que no sean destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="9b831-209">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span> 

  <span data-ttu-id="9b831-210">Cuando haya terminado, haga clic en **Liberar mensajes**.</span><span class="sxs-lookup"><span data-stu-id="9b831-210">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="9b831-211">Notas sobre la liberación de mensajes:</span><span class="sxs-lookup"><span data-stu-id="9b831-211">Notes about releasing messages:</span></span>

  - <span data-ttu-id="9b831-212">No puede publicar un mensaje en el mismo destinatario más de una vez.</span><span class="sxs-lookup"><span data-stu-id="9b831-212">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="9b831-213">Solo los destinatarios que no recibieron el mensaje aparecerán en la lista de posibles destinatarios.</span><span class="sxs-lookup"><span data-stu-id="9b831-213">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="9b831-214">**Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b831-214">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="9b831-215">Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Microsoft 365 complete esta tarea).</span><span class="sxs-lookup"><span data-stu-id="9b831-215">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="9b831-216">Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:</span><span class="sxs-lookup"><span data-stu-id="9b831-216">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="9b831-217">**Vista previa del mensaje**: En el panel flotante que aparece, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9b831-217">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="9b831-218">**Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.</span><span class="sxs-lookup"><span data-stu-id="9b831-218">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="9b831-219">**Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="9b831-219">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="9b831-220">**Quitar de cuarentena**: después de hacer clic en **sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="9b831-220">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="9b831-221">**Descargar mensaje**: En el panel de flotante que aparece, seleccione **Entiendo los riesgos de descargar este mensaje** para guardar una copia local del mensaje en formato .eml.</span><span class="sxs-lookup"><span data-stu-id="9b831-221">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="9b831-222">**Enviar mensaje**: en el panel flotante que aparece, elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9b831-222">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="9b831-223">**Tipo de objeto**: **email** (predeterminado), **URL** o **Attachment**.</span><span class="sxs-lookup"><span data-stu-id="9b831-223">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="9b831-224">**Formato de envío**: **identificador de mensaje de red** (predeterminado, con el valor correspondiente en el cuadro identificador de mensaje de **red** ) o **archivo** (busque un archivo. eml o. msg local).</span><span class="sxs-lookup"><span data-stu-id="9b831-224">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="9b831-225">Tenga en cuenta que si selecciona **archivo** y, a continuación, selecciona **identificador de mensaje de red**, el valor inicial desaparece.</span><span class="sxs-lookup"><span data-stu-id="9b831-225">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="9b831-226">**Destinatarios**: escriba la concesión un destinatario original del mensaje o haga clic en **seleccionar todo** para identificar todos los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="9b831-226">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="9b831-227">También puede hacer clic en **seleccionar todo** y quitar selectivamente destinatarios individuales.</span><span class="sxs-lookup"><span data-stu-id="9b831-227">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="9b831-228">**Motivo del envío**: **no se debe haber bloqueado** (predeterminado) o **debe haberse bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="9b831-228">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="9b831-229">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="9b831-229">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="9b831-230">Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9b831-230">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="9b831-231">Realice una acción en varios mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-231">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="9b831-232">Al seleccionar varios mensajes en cuarentena de la lista (hasta 100), se mostrará el panel de control flotante **Acciones en masa**, donde puede realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9b831-232">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="9b831-233">**Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar **Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.</span><span class="sxs-lookup"><span data-stu-id="9b831-233">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9b831-234">Considere el siguiente escenario: john@gmail.com envía un mensaje a faith@contoso.com y john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9b831-234">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="9b831-235">Gmail bifurca este mensaje en dos copias que se enrutan a la cuarentena como phishing en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b831-235">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="9b831-236">Un administrador libera ambos mensajes en admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9b831-236">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="9b831-237">El primer mensaje lanzado que llega al buzón de administración se entrega.</span><span class="sxs-lookup"><span data-stu-id="9b831-237">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="9b831-238">El segundo mensaje lanzado se identifica como entrega duplicada y se omite.</span><span class="sxs-lookup"><span data-stu-id="9b831-238">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="9b831-239">El mensaje se identifica como duplicados si tienen el mismo identificador de mensaje y la misma hora de recepción.</span><span class="sxs-lookup"><span data-stu-id="9b831-239">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="9b831-240">**Eliminar mensajes**: después de hacer clic en **sí** en la advertencia que aparece, los mensajes se eliminan inmediatamente sin que se envíen a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="9b831-240">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="9b831-241">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9b831-241">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="9b831-242">Solo Microsoft defender para Office 365: usar el centro de seguridad & cumplimiento para administrar los archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-242">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="9b831-243">Los procedimientos para los archivos en cuarentena en esta sección solo están disponibles para los suscriptores de Microsoft defender para Office 365, plan 1 y plan 2.</span><span class="sxs-lookup"><span data-stu-id="9b831-243">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="9b831-244">En las organizaciones con defender para Office 365, los administradores pueden administrar los archivos en cuarentena en SharePoint Online, OneDrive para la empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b831-244">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="9b831-245">Para habilitar la protección de estos archivos, consulte [Activar ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9b831-245">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="9b831-246">Ver archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-246">View quarantined files</span></span>

1. <span data-ttu-id="9b831-247">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="9b831-247">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="9b831-248">Cambiar **vista en cuarentena** en los **archivos** de valor.</span><span class="sxs-lookup"><span data-stu-id="9b831-248">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="9b831-249">Puede ordenar por un campo haciendo clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="9b831-249">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="9b831-250">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="9b831-250">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="9b831-251">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="9b831-251">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="9b831-252">Las columnas predeterminadas se marcan con un asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="9b831-252">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="9b831-253">**Usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-253">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-254">**Ubicaciones**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-254">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-255">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-255">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-256">**Dirección URL de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-256">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-257">**Tamaño de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-257">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-258">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-258">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-259">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b831-259">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="9b831-260">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="9b831-260">**Detected by**</span></span>
   - <span data-ttu-id="9b831-261">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="9b831-261">**Modified by time**</span></span>

4. <span data-ttu-id="9b831-262">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="9b831-262">To filter the results, click **Filter**.</span></span> <span data-ttu-id="9b831-263">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="9b831-263">The available filters are:</span></span>

   - <span data-ttu-id="9b831-264">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="9b831-264">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="9b831-265">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="9b831-265">**Today**</span></span>
     - <span data-ttu-id="9b831-266">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="9b831-266">**Next 2 days**</span></span>
     - <span data-ttu-id="9b831-267">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="9b831-267">**Next 7 days**</span></span>
     - <span data-ttu-id="9b831-268">Un intervalo de fecha y hora personalizado.</span><span class="sxs-lookup"><span data-stu-id="9b831-268">A custom date/time range.</span></span>
   - <span data-ttu-id="9b831-269">**Hora de recepción**</span><span class="sxs-lookup"><span data-stu-id="9b831-269">**Received time**</span></span>
   - <span data-ttu-id="9b831-270">**Motivo de cuarentena**: el único valor disponible es **malware**.</span><span class="sxs-lookup"><span data-stu-id="9b831-270">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="9b831-271">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="9b831-271">**Policy type**</span></span>

<span data-ttu-id="9b831-272">Una vez que haya encontrado un archivo en cuarentena específico, seleccione el archivo para ver los detalles del mismo y para realizar acciones en él (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="9b831-272">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="9b831-273">Ver detalles de archivo en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-273">View quarantined file details</span></span>

<span data-ttu-id="9b831-274">Al seleccionar un archivo de la lista, aparecen los siguientes detalles de archivo en el panel flotante de **detalles** :</span><span class="sxs-lookup"><span data-stu-id="9b831-274">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="9b831-275">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="9b831-275">**File Name**</span></span>
- <span data-ttu-id="9b831-276">**Dirección URL del archivo**: dirección URL que define la ubicación del archivo (por ejemplo, en SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="9b831-276">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="9b831-277">**Contenido malintencionado detectado en** La fecha y la hora en que se puso en cuarentena el archivo.</span><span class="sxs-lookup"><span data-stu-id="9b831-277">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="9b831-278">**Expires**: la fecha en la que se eliminará el archivo de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="9b831-278">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="9b831-279">**Detectado por**: defender para Office 365 o anti-malware Engine de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b831-279">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="9b831-280">**¿Liberado?**</span><span class="sxs-lookup"><span data-stu-id="9b831-280">**Released?**</span></span>
- <span data-ttu-id="9b831-281">**Nombre del malware**</span><span class="sxs-lookup"><span data-stu-id="9b831-281">**Malware Name**</span></span>
- <span data-ttu-id="9b831-282">**Identificador de documento**: un identificador único para el documento.</span><span class="sxs-lookup"><span data-stu-id="9b831-282">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="9b831-283">**Tamaño de archivo**: en kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="9b831-283">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="9b831-284">**Organización** El identificador único de su organización.</span><span class="sxs-lookup"><span data-stu-id="9b831-284">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="9b831-285">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="9b831-285">**Last modified**</span></span>
- <span data-ttu-id="9b831-286">**Modificado por**: el usuario que modificó el archivo por última vez.</span><span class="sxs-lookup"><span data-stu-id="9b831-286">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="9b831-287">**Algoritmo hash seguro 256-bit (SHA-256) valor**: puede usar este valor de hash para identificar el archivo en otros almacenes de reputación o en otras ubicaciones del entorno.</span><span class="sxs-lookup"><span data-stu-id="9b831-287">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="9b831-288">Realizar acciones en archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-288">Take action on quarantined files</span></span>

<span data-ttu-id="9b831-289">Al seleccionar un archivo de la lista, puede realizar las siguientes acciones en el archivo del panel flotante de **detalles** :</span><span class="sxs-lookup"><span data-stu-id="9b831-289">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="9b831-290">**Liberar archivos**: seleccione (predeterminado) o anule la selección **de archivos de informe a Microsoft para su análisis** y, a continuación, haga clic en **liberar archivos**.</span><span class="sxs-lookup"><span data-stu-id="9b831-290">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="9b831-291">**Descargar archivo**</span><span class="sxs-lookup"><span data-stu-id="9b831-291">**Download file**</span></span>
- <span data-ttu-id="9b831-292">**Quitar archivo de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="9b831-292">**Remove file from quarantine**</span></span>

<span data-ttu-id="9b831-293">Si no libera ni quita los archivos, se eliminarán después de que expire el período de retención de cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9b831-293">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="9b831-294">Acciones en varios archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-294">Actions on multiple quarantined files</span></span>

<span data-ttu-id="9b831-295">Al seleccionar varios archivos en cuarentena en la lista (hasta 100), aparece el panel flotante **acciones en masa** donde puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9b831-295">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="9b831-296">**Liberar archivos**</span><span class="sxs-lookup"><span data-stu-id="9b831-296">**Release files**</span></span>
- <span data-ttu-id="9b831-297">**Eliminar archivos**: después de hacer clic en **sí** en la advertencia que aparece, los archivos se eliminan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="9b831-297">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="9b831-298">Usar Exchange Online PowerShell o PowerShell independiente de EOP para ver y administrar los mensajes y archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b831-298">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="9b831-299">Los cmdlets que se usan para ver y administrar mensajes y archivos en cuarentena son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9b831-299">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="9b831-300">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="9b831-300">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="9b831-301">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="9b831-301">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="9b831-302">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="9b831-302">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="9b831-303">[Vista previa de QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): tenga en cuenta que este cmdlet solo es para los mensajes, no para los archivos de malware de ATP para SharePoint Online, OneDrive para la empresa o Teams.</span><span class="sxs-lookup"><span data-stu-id="9b831-303">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="9b831-304">Versión-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="9b831-304">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
