---
title: Buscar y liberar mensajes en cuarentena como usuario de Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: Como usuario de Office 365, puede ver, liberar y eliminar los mensajes puestos en cuarentena (mensajes de los que es destinatario y que el filtrado de correo no deseado puso en cuarentena como correo no deseado o correo electrónico masivo). Puede ver y administrar los mensajes en cuarentena en el Centro de seguridad y cumplimiento.
ms.openlocfilehash: e74358d57b96c8655fbf6a3f7f0b6eedb5e65ede
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857338"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="e4c20-104">Buscar y liberar mensajes en cuarentena como usuario de Office 365</span><span class="sxs-lookup"><span data-stu-id="e4c20-104">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="e4c20-105">La cuarentena retiene los mensajes que pueden ser peligrosos o no deseados en las organizaciones de Office 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e4c20-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="e4c20-106">Para obtener más información, consulte [Cuarentena en Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e4c20-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e4c20-107">Como usuario, puede ver, liberar y eliminar mensajes puestos en cuarentena de los que es destinatario y que fueron puestos en cuarentena como correo no deseado, correo electrónico masivo o (a partir de abril de 2020) de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e4c20-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="e4c20-108">También puede notificar falsos positivos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4c20-108">You can also report false positives to Microsoft.</span></span>

<span data-ttu-id="e4c20-109">Puede ver y administrar los mensajes en cuarentena en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e4c20-109">You view and manage your quarantined messages in the Security & Compliance Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e4c20-110">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="e4c20-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e4c20-111">Para abrir el Centro de seguridad y cumplimiento de Office 365, vaya a <https://protection.office.com></span><span class="sxs-lookup"><span data-stu-id="e4c20-111">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="e4c20-112">Para abrir directamente la página de Cuarentena, vaya a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="e4c20-112">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="e4c20-113">Los administradores pueden configurar cuánto tiempo se conservan los mensajes en cuarentena antes de que se eliminen de forma permanente (directivas contra correo electrónico no deseado).</span><span class="sxs-lookup"><span data-stu-id="e4c20-113">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="e4c20-114">Los mensajes que han expirado de la cuarentena no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="e4c20-114">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="e4c20-115">Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e4c20-115">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="e4c20-116">Los administradores también pueden [configurar notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md) en directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="e4c20-116">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md) in anti-spam policies.</span></span> <span data-ttu-id="e4c20-117">A partir de octubre de 2019, ya no podrá liberar mensajes en cuarentena directamente desde estas notificaciones.</span><span class="sxs-lookup"><span data-stu-id="e4c20-117">As of October 2019, you can no longer release quarantined messages directly from these notifications.</span></span> <span data-ttu-id="e4c20-118">Puede hacer clic en **Revisar** en la notificación, que le redireccionará a Cuarentena en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e4c20-118">You can click **Review** in the notification, which will take you to Quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="e4c20-119">Para obtener más información, consulte [Notificaciones de correo no deseado para el usuario final en Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e4c20-119">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="e4c20-120">Los mensajes puestos en cuarentena por suplantación de identidad de alta confianza, malware o por reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores.</span><span class="sxs-lookup"><span data-stu-id="e4c20-120">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="e4c20-121">Para más información, consulte [Buscar y liberar mensajes en cuarentena como administrador de Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span><span class="sxs-lookup"><span data-stu-id="e4c20-121">For more information, see [Find and release quarantined messages as an admin in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

- <span data-ttu-id="e4c20-122">Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.</span><span class="sxs-lookup"><span data-stu-id="e4c20-122">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="e4c20-123">Ver los mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e4c20-123">View your quarantined messages</span></span>

1. <span data-ttu-id="e4c20-124">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-124">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e4c20-125">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="e4c20-125">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e4c20-126">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="e4c20-126">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e4c20-127">Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="e4c20-127">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e4c20-128">**Recibido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4c20-128">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="e4c20-129">**Remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4c20-129">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="e4c20-130">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4c20-130">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="e4c20-131">**Motivo de la cuarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4c20-131">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="e4c20-132">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4c20-132">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="e4c20-133">**Tipo de directiva**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4c20-133">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="e4c20-134">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4c20-134">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="e4c20-135">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="e4c20-135">**Recipient**</span></span>

   - <span data-ttu-id="e4c20-136">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="e4c20-136">**Message ID**</span></span>

   - <span data-ttu-id="e4c20-137">**Nombre de la directiva**</span><span class="sxs-lookup"><span data-stu-id="e4c20-137">**Policy name**</span></span>

   - <span data-ttu-id="e4c20-138">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="e4c20-138">**Size**</span></span>

   - <span data-ttu-id="e4c20-139">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="e4c20-139">**Direction**</span></span>

   <span data-ttu-id="e4c20-140">Cuando haya terminado, haga clic en **Guardar** o en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-140">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="e4c20-141">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-141">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e4c20-142">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="e4c20-142">The available filters are:</span></span>

   - <span data-ttu-id="e4c20-143">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="e4c20-143">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="e4c20-144">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="e4c20-144">**Today**</span></span>

     - <span data-ttu-id="e4c20-145">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="e4c20-145">**Next 2 days**</span></span>

     - <span data-ttu-id="e4c20-146">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="e4c20-146">**Next 7 days**</span></span>

     - <span data-ttu-id="e4c20-147">**Personalizado**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-147">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e4c20-148">**Hora de recepción**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-148">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e4c20-149">**Motivo de la cuarentena**:</span><span class="sxs-lookup"><span data-stu-id="e4c20-149">**Quarantine reason**:</span></span>

     - <span data-ttu-id="e4c20-150">**Masivo**</span><span class="sxs-lookup"><span data-stu-id="e4c20-150">**Bulk**</span></span>

     - <span data-ttu-id="e4c20-151">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="e4c20-151">**Spam**</span></span>

     - <span data-ttu-id="e4c20-152">**Suplantación de identidad** (a partir de abril de 2020)</span><span class="sxs-lookup"><span data-stu-id="e4c20-152">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="e4c20-153">Para borrar el filtro, haga clic en **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-153">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="e4c20-154">Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-154">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="e4c20-155">Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="e4c20-155">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="e4c20-156">No se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="e4c20-156">Wildcards aren't supported.</span></span> <span data-ttu-id="e4c20-157">Puede buscar según los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e4c20-157">You can search by the following values:</span></span>

   - <span data-ttu-id="e4c20-158">**Id. de mensaje**: El identificador único global del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4c20-158">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="e4c20-159">Si selecciona un mensaje de la lista, el valor **Id. de mensaje** aparece en el panel flotante **Detalles** que aparece.</span><span class="sxs-lookup"><span data-stu-id="e4c20-159">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="e4c20-160">Los administradores pueden usar [seguimiento de mensajes](message-trace-scc.md) para buscar mensajes y los valores de Id. de mensaje correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e4c20-160">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="e4c20-161">**Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.</span><span class="sxs-lookup"><span data-stu-id="e4c20-161">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="e4c20-162">**Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.</span><span class="sxs-lookup"><span data-stu-id="e4c20-162">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="e4c20-163">**Asunto**: Use el asunto completo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4c20-163">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="e4c20-164">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e4c20-164">The search is not case-sensitive.</span></span>

   <span data-ttu-id="e4c20-165">Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="e4c20-165">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="e4c20-166">Cuando encuentre un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar una acción (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="e4c20-166">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="e4c20-167">Exportar los resultados de los mensajes</span><span class="sxs-lookup"><span data-stu-id="e4c20-167">Export message results</span></span>

1. <span data-ttu-id="e4c20-168">Seleccione los mensajes que le interesan y haga clic en **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-168">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="e4c20-169">Haga clic en **Sí** en el mensaje de confirmación que le advierte de que debe mantener abierta la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="e4c20-169">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="e4c20-170">Cuando la exportación esté lista, puede elegir el nombre y la ubicación de descarga del archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="e4c20-170">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="e4c20-171">Ver detalles de mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e4c20-171">View quarantined message details</span></span>

<span data-ttu-id="e4c20-172">Cuando selecciona un mensaje de correo electrónico de la lista, aparecen los detalles de mensaje siguientes en el panel flotante **Detalles**:</span><span class="sxs-lookup"><span data-stu-id="e4c20-172">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e4c20-173">**Id. de mensaje**: El identificador único global para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4c20-173">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="e4c20-174">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="e4c20-174">**Sender address**</span></span>

- <span data-ttu-id="e4c20-175">**Recibido**: La fecha/hora en que se ha recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4c20-175">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="e4c20-176">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="e4c20-176">**Subject**</span></span>

- <span data-ttu-id="e4c20-177">**Motivo de la cuarentena**: Muestra si un mensaje se ha identificado como **Correo no deseado**, **Masivo** o (a partir de abril de 2020) **Suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-177">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="e4c20-178">**Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="e4c20-178">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="e4c20-179">**Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="e4c20-179">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="e4c20-180">**Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.</span><span class="sxs-lookup"><span data-stu-id="e4c20-180">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="e4c20-181">**Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.</span><span class="sxs-lookup"><span data-stu-id="e4c20-181">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="e4c20-182">Llevar a cabo una acción en un correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e4c20-182">Take action on quarantined email</span></span>

<span data-ttu-id="e4c20-183">Después de seleccionar un mensaje, dispone opciones con respecto a qué hacer con los mensajes en el panel flotante **Detalles**:</span><span class="sxs-lookup"><span data-stu-id="e4c20-183">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e4c20-184">**Liberar mensaje**: En el panel flotante que aparece, elija si desea **Informar de los mensajes a Microsoft para su análisis**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-184">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="e4c20-185">Esta opción está seleccionada de forma predeterminada y comunica a Microsoft el mensaje puesto en cuarentena por error como falso positivo.</span><span class="sxs-lookup"><span data-stu-id="e4c20-185">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="e4c20-186">Cuando haya terminado, haga clic en **Liberar mensajes**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-186">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="e4c20-187">**Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4c20-187">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="e4c20-188">Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Office 365 complete esta tarea).</span><span class="sxs-lookup"><span data-stu-id="e4c20-188">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="e4c20-189">Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:</span><span class="sxs-lookup"><span data-stu-id="e4c20-189">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="e4c20-190">**Vista previa del mensaje**: En el panel flotante que aparece, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e4c20-190">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="e4c20-191">**Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.</span><span class="sxs-lookup"><span data-stu-id="e4c20-191">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="e4c20-192">**Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="e4c20-192">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="e4c20-193">**Descargar mensaje**: En el panel de flotante que aparece, seleccione **Entiendo los riesgos de descargar este mensaje** para guardar una copia local del mensaje en formato .eml.</span><span class="sxs-lookup"><span data-stu-id="e4c20-193">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="e4c20-194">**Eliminar de cuarentena**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="e4c20-194">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="e4c20-195">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-195">When you're finished, click **Close**.</span></span>

<span data-ttu-id="e4c20-196">Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e4c20-196">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="e4c20-197">Realice una acción en varios mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e4c20-197">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="e4c20-198">Al seleccionar varios mensajes en cuarentena de la lista (hasta 100), se mostrará el panel de control flotante**Acciones en masa**, donde puede realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4c20-198">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e4c20-199">**Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar**Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-199">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="e4c20-200">**Eliminar mensajes**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="e4c20-200">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="e4c20-201">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e4c20-201">When you're finished, click **Close**.</span></span>
