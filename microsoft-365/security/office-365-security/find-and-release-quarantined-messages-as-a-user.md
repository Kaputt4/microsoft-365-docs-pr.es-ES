---
title: Buscar y liberar mensajes en cuarentena como usuario
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los usuarios pueden obtener información sobre cómo ver y administrar los mensajes en cuarentena en Exchange Online Protection (EOP) que deberían haberles entregado.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 60b319b81362b9d88afcd734021db227969b04d0
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877877"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="87ef2-103">Búsqueda y liberación de mensajes en cuarentena como usuario en EOP</span><span class="sxs-lookup"><span data-stu-id="87ef2-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="87ef2-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="87ef2-104">**Applies to**</span></span>
- [<span data-ttu-id="87ef2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="87ef2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="87ef2-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="87ef2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="87ef2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87ef2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="87ef2-108">En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados.</span><span class="sxs-lookup"><span data-stu-id="87ef2-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="87ef2-109">Para más información, consulte [Cuarentena en EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="87ef2-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="87ef2-110">En tanto que destinatario de un mensaje en cuarentena, lo que puede hacer con el mensaje como usuario normal se describe en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="87ef2-110">As a recipient of a quarantined message, what you can do to the message as a regular user is described in the following table:</span></span>

<br>

****

|<span data-ttu-id="87ef2-111">Motivo de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="87ef2-111">Quarantine reason</span></span>|<span data-ttu-id="87ef2-112">Ver</span><span class="sxs-lookup"><span data-stu-id="87ef2-112">View</span></span>|<span data-ttu-id="87ef2-113">Liberar</span><span class="sxs-lookup"><span data-stu-id="87ef2-113">Release</span></span>|<span data-ttu-id="87ef2-114">Eliminar</span><span class="sxs-lookup"><span data-stu-id="87ef2-114">Delete</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="87ef2-115">Masivo</span><span class="sxs-lookup"><span data-stu-id="87ef2-115">Bulk</span></span>|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="87ef2-119">Correo no deseado</span><span class="sxs-lookup"><span data-stu-id="87ef2-119">Spam</span></span>|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="87ef2-123">Suplantación de identidad (suplantación de identidad no de alta confianza)</span><span class="sxs-lookup"><span data-stu-id="87ef2-123">Phishing (not high confidence phishing)</span></span>|![Marca de verificación](../../media/checkmark.png)||![Marca de verificación](../../media/checkmark.png)|
|

<span data-ttu-id="87ef2-126">Puede ver y administrar los mensajes en cuarentena en el portal de Microsoft 365 Defender o, si un administrador lo ha configurado, en [notificaciones de correo no deseado para el usuario](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="87ef2-126">You view and manage your quarantined messages in the Microsoft 365 Defender portal or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="87ef2-127">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="87ef2-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="87ef2-128">Para abrir el portal de Microsoft 365 Defender, vaya a <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="87ef2-128">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="87ef2-129">Para abrir directamente la página de cuarentena, vaya a <https://security.microsoft.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="87ef2-129">To open the Quarantine page directly, go to <https://security.microsoft.com/quarantine>.</span></span>

- <span data-ttu-id="87ef2-130">Los administradores pueden configurar cuánto tiempo se conservan los mensajes en cuarentena antes de que se eliminen de forma permanente (directivas contra correo electrónico no deseado).</span><span class="sxs-lookup"><span data-stu-id="87ef2-130">Admins can configure how long messages are kept in quarantine before they're permanently deleted in anti-spam policies.</span></span> <span data-ttu-id="87ef2-131">Los mensajes que han expirado de la cuarentena no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="87ef2-131">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="87ef2-132">Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="87ef2-132">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="87ef2-133">Los administradores también pueden [configurar notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) en directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="87ef2-133">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="87ef2-134">Los usuarios pueden eliminar mensajes de correo no deseado en cuarentena directamente desde estas notificaciones.</span><span class="sxs-lookup"><span data-stu-id="87ef2-134">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="87ef2-135">Los usuarios pueden revisar mensajes de suplantación de identidad (phishing) en cuarentena (no se trata de mensajes fraudulentos de alta confianza) directamente desde estas notificaciones.</span><span class="sxs-lookup"><span data-stu-id="87ef2-135">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="87ef2-136">Para obtener más información, consulte [Notificaciones de correo no deseado para el usuario final en EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="87ef2-136">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="87ef2-137">Los mensajes puestos en cuarentena por suplantación de identidad de alta confianza, malware o por reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores y no son visibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="87ef2-137">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="87ef2-138">Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="87ef2-138">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="87ef2-139">Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.</span><span class="sxs-lookup"><span data-stu-id="87ef2-139">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="87ef2-140">Ver los mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="87ef2-140">View your quarantined messages</span></span>

1. <span data-ttu-id="87ef2-141">En el portal de Microsoft 365 Defender, vaya a **Colaboración y correos electrónicos** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-141">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="87ef2-142">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="87ef2-142">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="87ef2-143">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="87ef2-143">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="87ef2-144">Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="87ef2-144">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="87ef2-145">**Recibido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="87ef2-145">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="87ef2-146">**Remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="87ef2-146">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="87ef2-147">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="87ef2-147">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="87ef2-148">**Motivo de la cuarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="87ef2-148">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="87ef2-149">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="87ef2-149">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="87ef2-150">**Tipo de directiva**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="87ef2-150">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="87ef2-151">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="87ef2-151">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="87ef2-152">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="87ef2-152">**Recipient**</span></span>
   - <span data-ttu-id="87ef2-153">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="87ef2-153">**Message ID**</span></span>
   - <span data-ttu-id="87ef2-154">**Nombre de la directiva**</span><span class="sxs-lookup"><span data-stu-id="87ef2-154">**Policy name**</span></span>
   - <span data-ttu-id="87ef2-155">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="87ef2-155">**Size**</span></span>
   - <span data-ttu-id="87ef2-156">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="87ef2-156">**Direction**</span></span>

   <span data-ttu-id="87ef2-157">Cuando haya terminado, haga clic en **Guardar** o en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-157">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="87ef2-158">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-158">To filter the results, click **Filter**.</span></span> <span data-ttu-id="87ef2-159">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="87ef2-159">The available filters are:</span></span>

   - <span data-ttu-id="87ef2-160">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="87ef2-160">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="87ef2-161">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="87ef2-161">**Today**</span></span>
     - <span data-ttu-id="87ef2-162">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="87ef2-162">**Next 2 days**</span></span>
     - <span data-ttu-id="87ef2-163">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="87ef2-163">**Next 7 days**</span></span>
     - <span data-ttu-id="87ef2-164">**Personalizado**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-164">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="87ef2-165">**Hora de recepción**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-165">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="87ef2-166">**Motivo de la cuarentena**:</span><span class="sxs-lookup"><span data-stu-id="87ef2-166">**Quarantine reason**:</span></span>
     - <span data-ttu-id="87ef2-167">**Masivo**</span><span class="sxs-lookup"><span data-stu-id="87ef2-167">**Bulk**</span></span>
     - <span data-ttu-id="87ef2-168">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="87ef2-168">**Spam**</span></span>
     - <span data-ttu-id="87ef2-169">**Suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="87ef2-169">**Phish**</span></span>

   - <span data-ttu-id="87ef2-170">**Tipo de directiva**: Filtrar mensajes por tipo de directiva:</span><span class="sxs-lookup"><span data-stu-id="87ef2-170">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="87ef2-171">**directiva antimalware**</span><span class="sxs-lookup"><span data-stu-id="87ef2-171">**Anti-malware policy**</span></span>
     - <span data-ttu-id="87ef2-172">**Directiva de datos adjuntos seguros** (Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="87ef2-172">**Safe Attachments policy** (Defender for Office 365)</span></span>
     - <span data-ttu-id="87ef2-173">**Política Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="87ef2-173">**Anti-phish policy**</span></span>
     - <span data-ttu-id="87ef2-174">**Directiva de filtro de contenido alojado** (directiva anti-spam)</span><span class="sxs-lookup"><span data-stu-id="87ef2-174">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="87ef2-175">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="87ef2-175">**Transport rule**</span></span>

     <sup>\*</sup>

   <span data-ttu-id="87ef2-176">Para borrar el filtro, haga clic en **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="87ef2-177">Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-177">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="87ef2-178">Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="87ef2-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="87ef2-179">No se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="87ef2-179">Wildcards aren't supported.</span></span> <span data-ttu-id="87ef2-180">Puede buscar según los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="87ef2-180">You can search by the following values:</span></span>

   - <span data-ttu-id="87ef2-181">**Id. de mensaje**: El identificador único global del mensaje.</span><span class="sxs-lookup"><span data-stu-id="87ef2-181">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="87ef2-182">Si selecciona un mensaje de la lista, el valor **Id. de mensaje** aparece en el panel flotante **Detalles** que aparece.</span><span class="sxs-lookup"><span data-stu-id="87ef2-182">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="87ef2-183">Los administradores pueden usar [seguimiento de mensajes](message-trace-scc.md) para buscar mensajes y los valores de Id. de mensaje correspondientes.</span><span class="sxs-lookup"><span data-stu-id="87ef2-183">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>
   - <span data-ttu-id="87ef2-184">**Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.</span><span class="sxs-lookup"><span data-stu-id="87ef2-184">**Sender email address**: A single sender's email address.</span></span>
   - <span data-ttu-id="87ef2-185">**Nombre de directiva**: Use el nombre de la Directiva completa del mensaje.</span><span class="sxs-lookup"><span data-stu-id="87ef2-185">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="87ef2-186">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="87ef2-186">The search is not case-sensitive.</span></span>
   - <span data-ttu-id="87ef2-187">**Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.</span><span class="sxs-lookup"><span data-stu-id="87ef2-187">**Recipient email address**: A single recipient's email address.</span></span>
   - <span data-ttu-id="87ef2-188">**Asunto**: Use el asunto completo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="87ef2-188">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="87ef2-189">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="87ef2-189">The search is not case-sensitive.</span></span>

   <span data-ttu-id="87ef2-190">Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="87ef2-190">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="87ef2-191">Cuando encuentre un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar una acción (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="87ef2-191">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="87ef2-192">Exportar los resultados de los mensajes</span><span class="sxs-lookup"><span data-stu-id="87ef2-192">Export message results</span></span>

1. <span data-ttu-id="87ef2-193">Seleccione los mensajes que le interesan y haga clic en **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-193">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="87ef2-194">Haga clic en **Sí** en el mensaje de confirmación que le advierte de que debe mantener abierta la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="87ef2-194">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="87ef2-195">Cuando la exportación esté lista, puede elegir el nombre y la ubicación de descarga del archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="87ef2-195">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="87ef2-196">Ver detalles de mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="87ef2-196">View quarantined message details</span></span>

<span data-ttu-id="87ef2-197">Cuando selecciona un mensaje de correo electrónico de la lista, aparecen los detalles de mensaje siguientes en el panel flotante **Detalles**:</span><span class="sxs-lookup"><span data-stu-id="87ef2-197">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="87ef2-198">**Id. de mensaje**: El identificador único global para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="87ef2-198">**Message ID**: The globally unique identifier for the message.</span></span>
- <span data-ttu-id="87ef2-199">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="87ef2-199">**Sender address**</span></span>
- <span data-ttu-id="87ef2-200">**Recibido**: La fecha/hora en que se ha recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="87ef2-200">**Received**: The date/time when the message was received.</span></span>
- <span data-ttu-id="87ef2-201">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="87ef2-201">**Subject**</span></span>
- <span data-ttu-id="87ef2-202">**Motivo de la cuarentena**: Muestra si un mensaje se ha identificado como **Correo no deseado**, **Masivo** o **Suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-202">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>
- <span data-ttu-id="87ef2-203">**Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="87ef2-203">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>
- <span data-ttu-id="87ef2-204">**Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="87ef2-204">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>
- <span data-ttu-id="87ef2-205">**Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.</span><span class="sxs-lookup"><span data-stu-id="87ef2-205">**Released to**: All email addresses (if any) to which the message has been released.</span></span>
- <span data-ttu-id="87ef2-206">**Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.</span><span class="sxs-lookup"><span data-stu-id="87ef2-206">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="87ef2-207">Llevar a cabo una acción en un correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="87ef2-207">Take action on quarantined email</span></span>

<span data-ttu-id="87ef2-208">Después de seleccionar un mensaje, dispone opciones con respecto a qué hacer con los mensajes en el panel flotante **Detalles**:</span><span class="sxs-lookup"><span data-stu-id="87ef2-208">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="87ef2-209">**Liberar mensaje**: En el panel flotante que aparece, elija si desea **Informar de los mensajes a Microsoft para su análisis**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-209">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="87ef2-210">Esta opción está seleccionada de forma predeterminada y comunica a Microsoft el mensaje puesto en cuarentena por error como falso positivo.</span><span class="sxs-lookup"><span data-stu-id="87ef2-210">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="87ef2-211">Cuando haya terminado, haga clic en **Liberar mensajes**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-211">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="87ef2-212">**Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="87ef2-212">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="87ef2-213">Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Microsoft 365 complete esta tarea).</span><span class="sxs-lookup"><span data-stu-id="87ef2-213">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="87ef2-214">Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:</span><span class="sxs-lookup"><span data-stu-id="87ef2-214">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="87ef2-215">**Vista previa del mensaje**: En el panel flotante que aparece, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="87ef2-215">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="87ef2-216">**Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.</span><span class="sxs-lookup"><span data-stu-id="87ef2-216">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="87ef2-217">**Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="87ef2-217">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="87ef2-218">**Eliminar de cuarentena**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="87ef2-218">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="87ef2-219">**Bloquear remitente**: Agregue el remitente a la lista Remitentes bloqueados del buzón.</span><span class="sxs-lookup"><span data-stu-id="87ef2-219">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="87ef2-220">Para más información, consulte [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="87ef2-220">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="87ef2-221">Agregue el remitente a la lista de remitentes bloqueados del buzón.</span><span class="sxs-lookup"><span data-stu-id="87ef2-221">Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="87ef2-222">Para más información, consulte [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="87ef2-222">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="87ef2-223">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-223">When you're finished, click **Close**.</span></span>

<span data-ttu-id="87ef2-224">Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="87ef2-224">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="87ef2-225">Realice una acción en varios mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="87ef2-225">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="87ef2-226">Al seleccionar varios mensajes en cuarentena de la lista (hasta 100), se mostrará el panel de control flotante **Acciones en masa**, donde puede realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="87ef2-226">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="87ef2-227">**Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar **Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-227">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>
- <span data-ttu-id="87ef2-228">**Eliminar mensajes**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="87ef2-228">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="87ef2-229">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="87ef2-229">When you're finished, click **Close**.</span></span>
