---
title: Administrar mensajes en cuarentena y archivos como administrador
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
description: Los administradores pueden obtener información sobre cómo ver y administrar los mensajes en cuarentena para todos los usuarios en Exchange Online Protection (EOP). Los administradores de organizaciones con Office 365 Advanced Threat Protection (Office 365 ATP) también pueden administrar los archivos en cuarentena en SharePoint Online, OneDrive para la empresa y Microsoft Teams.
ms.openlocfilehash: 472a5258c112db7e8b8017e5d2ff19dc4741e93c
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213333"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="2e921-104">Administrar archivos y mensajes en cuarentena como un administrador en EOP</span><span class="sxs-lookup"><span data-stu-id="2e921-104">Manage quarantined messages and files as an admin in EOP</span></span>

<span data-ttu-id="2e921-105">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, la cuarentena contiene mensajes potencialmente peligrosos o no deseados.</span><span class="sxs-lookup"><span data-stu-id="2e921-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="2e921-106">Para obtener más información, vea [mensajes de correo electrónico en cuarentena en EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="2e921-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="2e921-107">Los administradores pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2e921-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="2e921-108">Solo los administradores pueden administrar los mensajes que se pusieron en cuarentena como malware, la suplantación de identidad de confianza alta o como resultado de las reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="2e921-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="2e921-109">Los administradores también pueden informar de falsos positivos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e921-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="2e921-110">Los administradores de organizaciones con Office 365 Advance Threat Protection (Office 365 ATP) también pueden ver, descargar y eliminar archivos en cuarentena en SharePoint Online, OneDrive para la empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2e921-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="2e921-111">Puede ver y administrar los mensajes en cuarentena en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones de correo en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de correo de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="2e921-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2e921-112">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="2e921-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2e921-113">Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="2e921-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="2e921-114">Para abrir directamente la página de Cuarentena, vaya a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="2e921-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="2e921-115">Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2e921-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2e921-116">Para conectarse a PowerShell de EOP independiente, vea [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2e921-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2e921-117">Debe tener permisos asignados para poder administrar la cuarentena como administrador. Los permisos se controlan mediante el rol **cuarentena** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2e921-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="2e921-118">De forma predeterminada, este rol se asigna a los grupos de roles administración de la **organización** (administradores globales), **Administrador de cuarentena**y administrador de **seguridad** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2e921-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="2e921-119">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2e921-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="2e921-120">Los mensajes en cuarentena se conservan durante un período de tiempo predeterminado antes de que se eliminen automáticamente:</span><span class="sxs-lookup"><span data-stu-id="2e921-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="2e921-121">Mensajes puestos en cuarentena por directivas contra correo no deseado (correo no deseado, phishing y correo electrónico masivo): 30 días.</span><span class="sxs-lookup"><span data-stu-id="2e921-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="2e921-122">Este es el valor predeterminado y máximo.</span><span class="sxs-lookup"><span data-stu-id="2e921-122">This is the default and maximum value.</span></span> <span data-ttu-id="2e921-123">Para configurar este valor, consulte [configurar directivas contra correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2e921-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="2e921-124">Mensajes que contienen malware: 15 días.</span><span class="sxs-lookup"><span data-stu-id="2e921-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="2e921-125">Cuando un mensaje expira de la cuarentena, no puede recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="2e921-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="2e921-126">Usar el centro de seguridad & cumplimiento para administrar los mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="2e921-127">Ver el correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-127">View quarantined email</span></span>

1. <span data-ttu-id="2e921-128">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="2e921-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="2e921-129">Compruebe que **vista en cuarentena** se haya establecido en el **correo**de valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2e921-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="2e921-130">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="2e921-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="2e921-131">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="2e921-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="2e921-132">Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="2e921-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="2e921-133">**Recibido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-134">**Remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-135">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-136">**Motivo de la cuarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-137">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-138">**Tipo de directiva**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-139">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="2e921-139">**Recipient**</span></span>

   - <span data-ttu-id="2e921-140">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="2e921-140">**Message ID**</span></span>

   - <span data-ttu-id="2e921-141">**Nombre de la directiva**</span><span class="sxs-lookup"><span data-stu-id="2e921-141">**Policy name**</span></span>

   - <span data-ttu-id="2e921-142">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="2e921-142">**Size**</span></span>

   - <span data-ttu-id="2e921-143">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="2e921-143">**Direction**</span></span>

   <span data-ttu-id="2e921-144">Cuando haya terminado, haga clic en **Guardar** o en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="2e921-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="2e921-145">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="2e921-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="2e921-146">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="2e921-146">The available filters are:</span></span>

   - <span data-ttu-id="2e921-147">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="2e921-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="2e921-148">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="2e921-148">**Today**</span></span>

     - <span data-ttu-id="2e921-149">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="2e921-149">**Next 2 days**</span></span>

     - <span data-ttu-id="2e921-150">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="2e921-150">**Next 7 days**</span></span>

     - <span data-ttu-id="2e921-151">**Personalizado**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="2e921-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="2e921-152">**Hora de recepción**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="2e921-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="2e921-153">**Motivo de la cuarentena**:</span><span class="sxs-lookup"><span data-stu-id="2e921-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="2e921-154">**Directiva**: el mensaje coincide con las condiciones de una regla de flujo de correo (también denominada regla de transporte).</span><span class="sxs-lookup"><span data-stu-id="2e921-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="2e921-155">**Masivo**</span><span class="sxs-lookup"><span data-stu-id="2e921-155">**Bulk**</span></span>

     - <span data-ttu-id="2e921-156">**Conseguir**</span><span class="sxs-lookup"><span data-stu-id="2e921-156">**Phish**</span></span>

     - <span data-ttu-id="2e921-157">**Malware**</span><span class="sxs-lookup"><span data-stu-id="2e921-157">**Malware**</span></span>

     - <span data-ttu-id="2e921-158">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="2e921-158">**Spam**</span></span>

     - <span data-ttu-id="2e921-159">**Phish de confianza alta**</span><span class="sxs-lookup"><span data-stu-id="2e921-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="2e921-160">**Destinatario de correo electrónico**: todos los usuarios o solo los mensajes que se le envíen.</span><span class="sxs-lookup"><span data-stu-id="2e921-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="2e921-161">Los usuarios finales solo pueden administrar los mensajes en cuarentena que se les envían.</span><span class="sxs-lookup"><span data-stu-id="2e921-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="2e921-162">Para borrar el filtro, haga clic en **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="2e921-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="2e921-163">Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="2e921-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="2e921-164">Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="2e921-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="2e921-165">No se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="2e921-165">Wildcards aren't supported.</span></span> <span data-ttu-id="2e921-166">Puede buscar según los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="2e921-166">You can search by the following values:</span></span>

   - <span data-ttu-id="2e921-167">**Id. de mensaje**: El identificador único global del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2e921-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="2e921-168">Por ejemplo, usó el [seguimiento de mensajes](message-trace-scc.md) para buscar un mensaje que se envió a un usuario de su organización y usted determina que el mensaje se puso en cuarentena en lugar de entregarse.</span><span class="sxs-lookup"><span data-stu-id="2e921-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="2e921-169">Asegúrese de incluir el valor completo del identificador de mensaje, que puede incluir corchetes angulares ( \< \> ).</span><span class="sxs-lookup"><span data-stu-id="2e921-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="2e921-170">Por ejemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="2e921-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="2e921-171">**Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.</span><span class="sxs-lookup"><span data-stu-id="2e921-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="2e921-172">**Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.</span><span class="sxs-lookup"><span data-stu-id="2e921-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="2e921-173">**Asunto**: Use el asunto completo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2e921-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="2e921-174">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2e921-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="2e921-175">Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="2e921-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="2e921-176">Cuando encuentre un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar una acción (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="2e921-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="2e921-177">Exportar los resultados de los mensajes</span><span class="sxs-lookup"><span data-stu-id="2e921-177">Export message results</span></span>

1. <span data-ttu-id="2e921-178">Seleccione los mensajes que le interesan y haga clic en **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="2e921-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="2e921-179">Haga clic en **Sí** en el mensaje de confirmación que le advierte de que debe mantener abierta la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="2e921-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="2e921-180">Cuando la exportación esté lista, puede elegir el nombre y la ubicación de descarga del archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="2e921-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="2e921-181">Ver detalles de mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-181">View quarantined message details</span></span>

<span data-ttu-id="2e921-182">Cuando selecciona un mensaje de correo electrónico de la lista, aparecen los detalles de mensaje siguientes en el panel flotante **Detalles**:</span><span class="sxs-lookup"><span data-stu-id="2e921-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="2e921-183">**Id. de mensaje**: El identificador único global para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2e921-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="2e921-184">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="2e921-184">**Sender address**</span></span>

- <span data-ttu-id="2e921-185">**Recibido**: La fecha/hora en que se ha recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2e921-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="2e921-186">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="2e921-186">**Subject**</span></span>

- <span data-ttu-id="2e921-187">**Motivo de cuarentena**: muestra si un mensaje se ha identificado **como correo no deseado**, en **masa**, **phish**, coincide con una regla de flujo de correo (**regla de transporte**) o se identificó como **malware**que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="2e921-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="2e921-188">**Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="2e921-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="2e921-189">**Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2e921-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="2e921-190">**Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.</span><span class="sxs-lookup"><span data-stu-id="2e921-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="2e921-191">**Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.</span><span class="sxs-lookup"><span data-stu-id="2e921-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="2e921-192">Llevar a cabo una acción en un correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-192">Take action on quarantined email</span></span>

<span data-ttu-id="2e921-193">Después de seleccionar un mensaje, tiene varias opciones para qué hacer con los mensajes en el panel flotante **detalles** :</span><span class="sxs-lookup"><span data-stu-id="2e921-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="2e921-194">**Mensaje de liberación**: en el panel flotante que aparece, elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2e921-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="2e921-195">**Notificar mensajes a Microsoft para su análisis**: esta opción está seleccionada de forma predeterminada y notifica a Microsoft el mensaje con una cuarentena incorrecta como falso positivo.</span><span class="sxs-lookup"><span data-stu-id="2e921-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="2e921-196">Si el mensaje se puso en cuarentena como correo no deseado, en masa o con suplantación de identidad o con malware, el mensaje también se notifica al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e921-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="2e921-197">Según el análisis, las reglas de filtro de correo no deseado de todo el servicio pueden ajustarse para permitir el paso del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2e921-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="2e921-198">Elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2e921-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="2e921-199">**Liberar mensajes para todos los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="2e921-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="2e921-200">**Liberar mensajes a destinatarios específicos**</span><span class="sxs-lookup"><span data-stu-id="2e921-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="2e921-201">**Liberar mensajes para otros usuarios**</span><span class="sxs-lookup"><span data-stu-id="2e921-201">**Release messages to other people**</span></span>

  <span data-ttu-id="2e921-202">Cuando haya terminado, haga clic en **Liberar mensajes**.</span><span class="sxs-lookup"><span data-stu-id="2e921-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="2e921-203">Notas sobre la liberación de mensajes:</span><span class="sxs-lookup"><span data-stu-id="2e921-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="2e921-204">No puede publicar un mensaje en el mismo destinatario más de una vez.</span><span class="sxs-lookup"><span data-stu-id="2e921-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="2e921-205">Solo los destinatarios que no recibieron el mensaje aparecerán en la lista de posibles destinatarios.</span><span class="sxs-lookup"><span data-stu-id="2e921-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="2e921-206">**Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2e921-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="2e921-207">Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Microsoft 365 complete esta tarea).</span><span class="sxs-lookup"><span data-stu-id="2e921-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="2e921-208">Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:</span><span class="sxs-lookup"><span data-stu-id="2e921-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="2e921-209">**Vista previa del mensaje**: En el panel flotante que aparece, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2e921-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="2e921-210">**Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.</span><span class="sxs-lookup"><span data-stu-id="2e921-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="2e921-211">**Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="2e921-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="2e921-212">**Quitar de cuarentena**: después de hacer clic en **sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="2e921-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="2e921-213">**Descargar mensaje**: En el panel de flotante que aparece, seleccione **Entiendo los riesgos de descargar este mensaje** para guardar una copia local del mensaje en formato .eml.</span><span class="sxs-lookup"><span data-stu-id="2e921-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="2e921-214">**Enviar mensaje**: en el panel flotante que aparece, elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2e921-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="2e921-215">**Tipo de objeto**: **email** (predeterminado), **URL**o **Attachment**.</span><span class="sxs-lookup"><span data-stu-id="2e921-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="2e921-216">**Formato de envío**: **identificador de mensaje de red** (predeterminado, con el valor correspondiente en el cuadro identificador de mensaje de **red** ) o **archivo** (busque un archivo. eml o. msg local).</span><span class="sxs-lookup"><span data-stu-id="2e921-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="2e921-217">Tenga en cuenta que si selecciona **archivo** y, a continuación, selecciona **identificador de mensaje de red**, el valor inicial desaparece.</span><span class="sxs-lookup"><span data-stu-id="2e921-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="2e921-218">**Destinatarios**: escriba la concesión un destinatario original del mensaje o haga clic en **seleccionar todo** para identificar todos los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="2e921-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="2e921-219">También puede hacer clic en **seleccionar todo** y quitar selectivamente destinatarios individuales.</span><span class="sxs-lookup"><span data-stu-id="2e921-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="2e921-220">**Motivo del envío**: **no se debe haber bloqueado** (predeterminado) o **debe haberse bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="2e921-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="2e921-221">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2e921-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="2e921-222">Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2e921-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="2e921-223">Realice una acción en varios mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="2e921-224">Al seleccionar varios mensajes en cuarentena de la lista (hasta 100), se mostrará el panel de control flotante**Acciones en masa**, donde puede realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2e921-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="2e921-225">**Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar**Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.</span><span class="sxs-lookup"><span data-stu-id="2e921-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="2e921-226">**Eliminar mensajes**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="2e921-226">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="2e921-227">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2e921-227">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="2e921-228">Solo ATP: usar el centro de seguridad & cumplimiento para administrar los archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-228">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="2e921-229">Los procedimientos para los archivos en cuarentena de esta sección solo están disponibles para los suscriptores de ATP plan 1 y plan 2.</span><span class="sxs-lookup"><span data-stu-id="2e921-229">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="2e921-230">En las organizaciones con ATP, los administradores pueden administrar los archivos en cuarentena en SharePoint Online, OneDrive para la empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2e921-230">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="2e921-231">Ver archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-231">View quarantined files</span></span>

1. <span data-ttu-id="2e921-232">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="2e921-232">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="2e921-233">Cambiar **vista en cuarentena** en los **archivos**de valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2e921-233">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="2e921-234">Puede ordenar por un campo haciendo clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="2e921-234">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="2e921-235">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="2e921-235">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="2e921-236">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="2e921-236">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="2e921-237">Las columnas predeterminadas se marcan con un asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="2e921-237">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="2e921-238">**Usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-238">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-239">**Ubicaciones**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-239">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-240">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-240">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-241">**Dirección URL de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-241">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-242">**Tamaño de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-242">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-243">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-243">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-244">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2e921-244">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="2e921-245">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="2e921-245">**Detected by**</span></span>

   - <span data-ttu-id="2e921-246">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="2e921-246">**Modified by time**</span></span>

4. <span data-ttu-id="2e921-247">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="2e921-247">To filter the results, click **Filter**.</span></span> <span data-ttu-id="2e921-248">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="2e921-248">The available filters are:</span></span>

   - <span data-ttu-id="2e921-249">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="2e921-249">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="2e921-250">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="2e921-250">**Today**</span></span>

     - <span data-ttu-id="2e921-251">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="2e921-251">**Next 2 days**</span></span>

     - <span data-ttu-id="2e921-252">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="2e921-252">**Next 7 days**</span></span>

     - <span data-ttu-id="2e921-253">Un intervalo de fecha y hora personalizado.</span><span class="sxs-lookup"><span data-stu-id="2e921-253">A custom date/time range.</span></span>

   - <span data-ttu-id="2e921-254">**Hora de recepción**</span><span class="sxs-lookup"><span data-stu-id="2e921-254">**Received time**</span></span>

   - <span data-ttu-id="2e921-255">**Motivo de cuarentena**: el único valor disponible es **malware**.</span><span class="sxs-lookup"><span data-stu-id="2e921-255">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="2e921-256">Una vez que haya encontrado un archivo en cuarentena específico, seleccione el archivo para ver los detalles del mismo y para realizar acciones en él (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="2e921-256">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="2e921-257">Resultados de la exportación de archivos</span><span class="sxs-lookup"><span data-stu-id="2e921-257">Export file results</span></span>

1. <span data-ttu-id="2e921-258">Seleccione los archivos que le interesan y haga clic en **exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="2e921-258">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="2e921-259">Haga clic en **Sí** en el mensaje de confirmación que le advierte de que debe mantener abierta la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="2e921-259">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="2e921-260">Cuando la exportación esté lista, puede elegir el nombre y la ubicación de descarga del archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="2e921-260">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="2e921-261">Ver detalles de archivo en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-261">View quarantined file details</span></span>

<span data-ttu-id="2e921-262">Al seleccionar un archivo de la lista, aparecen los siguientes detalles de archivo en el panel flotante de **detalles** :</span><span class="sxs-lookup"><span data-stu-id="2e921-262">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="2e921-263">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="2e921-263">**File Name**</span></span>

- <span data-ttu-id="2e921-264">**Dirección URL del archivo**: dirección URL que define la ubicación del archivo (por ejemplo, en SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="2e921-264">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="2e921-265">**Contenido malintencionado detectado en** La fecha y la hora en que se puso en cuarentena el archivo.</span><span class="sxs-lookup"><span data-stu-id="2e921-265">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="2e921-266">**Expires**: la fecha en la que se eliminará el archivo de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2e921-266">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="2e921-267">**Detectado por**: ATP (protección contra amenazas avanzada) o motor antimalware de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e921-267">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="2e921-268">**¿Liberado?**</span><span class="sxs-lookup"><span data-stu-id="2e921-268">**Released?**</span></span>

- <span data-ttu-id="2e921-269">**Nombre del malware**</span><span class="sxs-lookup"><span data-stu-id="2e921-269">**Malware Name**</span></span>

- <span data-ttu-id="2e921-270">**Identificador de documento**: un identificador único para el documento.</span><span class="sxs-lookup"><span data-stu-id="2e921-270">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="2e921-271">**Tamaño de archivo**: en kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="2e921-271">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="2e921-272">**Organización** El identificador único de su organización.</span><span class="sxs-lookup"><span data-stu-id="2e921-272">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="2e921-273">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="2e921-273">**Last modified**</span></span>

- <span data-ttu-id="2e921-274">**Modificado por**: el usuario que modificó el archivo por última vez.</span><span class="sxs-lookup"><span data-stu-id="2e921-274">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="2e921-275">**Algoritmo hash seguro 256-bit (SHA-256) valor**: puede usar este valor de hash para identificar el archivo en otros almacenes de reputación o en otras ubicaciones del entorno.</span><span class="sxs-lookup"><span data-stu-id="2e921-275">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="2e921-276">Realizar acciones en archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-276">Take action on quarantined files</span></span>

<span data-ttu-id="2e921-277">Al seleccionar un archivo de la lista, puede realizar las siguientes acciones en el archivo del panel flotante de **detalles** :</span><span class="sxs-lookup"><span data-stu-id="2e921-277">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="2e921-278">**Liberar archivos**: seleccione (predeterminado) o anule la selección **de archivos de informe a Microsoft para su análisis**y, a continuación, haga clic en **liberar archivos**.</span><span class="sxs-lookup"><span data-stu-id="2e921-278">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="2e921-279">**Descargar archivo**</span><span class="sxs-lookup"><span data-stu-id="2e921-279">**Download file**</span></span>

- <span data-ttu-id="2e921-280">**Quitar archivo de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="2e921-280">**Remove file from quarantine**</span></span>

<span data-ttu-id="2e921-281">Si no libera ni quita los archivos, se eliminarán después de que expire el período de retención de cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2e921-281">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="2e921-282">Acciones en varios archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-282">Actions on multiple quarantined files</span></span>

<span data-ttu-id="2e921-283">Al seleccionar varios archivos en cuarentena en la lista (hasta 100), aparece el panel flotante **acciones en masa** donde puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2e921-283">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="2e921-284">**Liberar archivos**</span><span class="sxs-lookup"><span data-stu-id="2e921-284">**Release files**</span></span>

- <span data-ttu-id="2e921-285">**Eliminar archivos**: después de hacer clic en **sí** en la advertencia que aparece, los archivos se eliminan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="2e921-285">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="2e921-286">Con una cuenta profesional o educativa con privilegios de administrador global (o roles de seguridad & cumplimiento del centro de cumplimiento) en su organización, inicie sesión y [vaya al centro de seguridad & cumplimiento](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2e921-286">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="2e921-287">Usar Exchange Online PowerShell o PowerShell independiente de EOP para ver y administrar los mensajes y archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="2e921-287">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="2e921-288">Los cmdlets que se usan para ver y administrar mensajes y archivos en cuarentena son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2e921-288">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="2e921-289">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="2e921-289">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="2e921-290">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="2e921-290">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="2e921-291">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="2e921-291">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="2e921-292">[Vista previa de QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): tenga en cuenta que este cmdlet solo es para los mensajes, no para los archivos de malware de ATP para SharePoint Online, OneDrive para la empresa o Teams.</span><span class="sxs-lookup"><span data-stu-id="2e921-292">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="2e921-293">Versión-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="2e921-293">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
