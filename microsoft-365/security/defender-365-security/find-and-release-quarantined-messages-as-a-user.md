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
ms.openlocfilehash: 961912427f9c343f8235f0ed8e990431669ff9e5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071419"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="8b24b-103">Búsqueda y liberación de mensajes en cuarentena como usuario en EOP</span><span class="sxs-lookup"><span data-stu-id="8b24b-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8b24b-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="8b24b-104">**Applies to**</span></span>
- [<span data-ttu-id="8b24b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8b24b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8b24b-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8b24b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8b24b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b24b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8b24b-108">En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados.</span><span class="sxs-lookup"><span data-stu-id="8b24b-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="8b24b-109">Para más información, consulte [Cuarentena en EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="8b24b-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="8b24b-110">Como usuario, puede ver, liberar y eliminar mensajes puestos en cuarentena de los que es destinatario y que fueron puestos en cuarentena como correo no deseado o correo electrónico masivo.</span><span class="sxs-lookup"><span data-stu-id="8b24b-110">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="8b24b-111">A partir de abril de 2020, puede ver o eliminar mensajes de phishing en cuarentena (no phishing de alta confianza) en los casos en que es un destinatario.</span><span class="sxs-lookup"><span data-stu-id="8b24b-111">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="8b24b-112">Puede ver y administrar los mensajes en cuarentena en el Centro de seguridad y cumplimiento o (si el administrador ha configurado esto) en [notificaciones de correo no deseado para el usuario final](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="8b24b-112">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8b24b-113">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="8b24b-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8b24b-114">Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="8b24b-114">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="8b24b-115">Para abrir directamente la página de Cuarentena, vaya a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="8b24b-115">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="8b24b-116">Los administradores pueden configurar cuánto tiempo se conservan los mensajes en cuarentena antes de que se eliminen de forma permanente (directivas contra correo electrónico no deseado).</span><span class="sxs-lookup"><span data-stu-id="8b24b-116">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="8b24b-117">Los mensajes que han expirado de la cuarentena no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="8b24b-117">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="8b24b-118">Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8b24b-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="8b24b-119">Los administradores también pueden [configurar notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) en directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="8b24b-119">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="8b24b-120">Los usuarios pueden eliminar mensajes de correo no deseado en cuarentena directamente desde estas notificaciones.</span><span class="sxs-lookup"><span data-stu-id="8b24b-120">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="8b24b-121">Los usuarios pueden revisar mensajes de suplantación de identidad (phishing) en cuarentena (no se trata de mensajes fraudulentos de alta confianza) directamente desde estas notificaciones.</span><span class="sxs-lookup"><span data-stu-id="8b24b-121">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="8b24b-122">Para obtener más información, consulte [Notificaciones de correo no deseado para el usuario final en EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="8b24b-122">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="8b24b-123">Los mensajes puestos en cuarentena por suplantación de identidad de alta confianza, malware o por reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores y no son visibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8b24b-123">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="8b24b-124">Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="8b24b-124">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="8b24b-125">Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.</span><span class="sxs-lookup"><span data-stu-id="8b24b-125">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="8b24b-126">Ver los mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8b24b-126">View your quarantined messages</span></span>

1. <span data-ttu-id="8b24b-127">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-127">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="8b24b-128">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="8b24b-128">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="8b24b-129">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="8b24b-129">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="8b24b-130">Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="8b24b-130">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="8b24b-131">**Recibido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b24b-131">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="8b24b-132">**Remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b24b-132">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="8b24b-133">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b24b-133">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="8b24b-134">**Motivo de la cuarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b24b-134">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="8b24b-135">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b24b-135">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="8b24b-136">**Tipo de directiva**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b24b-136">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="8b24b-137">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8b24b-137">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="8b24b-138">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="8b24b-138">**Recipient**</span></span>
   - <span data-ttu-id="8b24b-139">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="8b24b-139">**Message ID**</span></span>
   - <span data-ttu-id="8b24b-140">**Nombre de la directiva**</span><span class="sxs-lookup"><span data-stu-id="8b24b-140">**Policy name**</span></span>
   - <span data-ttu-id="8b24b-141">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="8b24b-141">**Size**</span></span>
   - <span data-ttu-id="8b24b-142">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="8b24b-142">**Direction**</span></span>

   <span data-ttu-id="8b24b-143">Cuando haya terminado, haga clic en **Guardar** o en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-143">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="8b24b-144">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-144">To filter the results, click **Filter**.</span></span> <span data-ttu-id="8b24b-145">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="8b24b-145">The available filters are:</span></span>

   - <span data-ttu-id="8b24b-146">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="8b24b-146">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="8b24b-147">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="8b24b-147">**Today**</span></span>
     - <span data-ttu-id="8b24b-148">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="8b24b-148">**Next 2 days**</span></span>
     - <span data-ttu-id="8b24b-149">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="8b24b-149">**Next 7 days**</span></span>
     - <span data-ttu-id="8b24b-150">**Personalizado**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-150">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="8b24b-151">**Hora de recepción**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-151">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="8b24b-152">**Motivo de la cuarentena**:</span><span class="sxs-lookup"><span data-stu-id="8b24b-152">**Quarantine reason**:</span></span>
     - <span data-ttu-id="8b24b-153">**Masivo**</span><span class="sxs-lookup"><span data-stu-id="8b24b-153">**Bulk**</span></span>
     - <span data-ttu-id="8b24b-154">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="8b24b-154">**Spam**</span></span>
     - <span data-ttu-id="8b24b-155">**Suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="8b24b-155">**Phish**</span></span>

   - <span data-ttu-id="8b24b-156">**Tipo de directiva**: Filtrar mensajes por tipo de directiva:</span><span class="sxs-lookup"><span data-stu-id="8b24b-156">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="8b24b-157">**Política Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="8b24b-157">**Anti-phish policy**</span></span>
     - <span data-ttu-id="8b24b-158">**Directiva de filtro de contenido alojado** (directiva anti-spam)</span><span class="sxs-lookup"><span data-stu-id="8b24b-158">**Hosted content filter policy** (anti-spam policy)</span></span>

   <span data-ttu-id="8b24b-159">Para borrar el filtro, haga clic en **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-159">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="8b24b-160">Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-160">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="8b24b-161">Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="8b24b-161">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="8b24b-162">No se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="8b24b-162">Wildcards aren't supported.</span></span> <span data-ttu-id="8b24b-163">Puede buscar según los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="8b24b-163">You can search by the following values:</span></span>

   - <span data-ttu-id="8b24b-164">**Id. de mensaje**: El identificador único global del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8b24b-164">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="8b24b-165">Si selecciona un mensaje de la lista, el valor **Id. de mensaje** aparece en el panel flotante **Detalles** que aparece.</span><span class="sxs-lookup"><span data-stu-id="8b24b-165">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="8b24b-166">Los administradores pueden usar [seguimiento de mensajes](message-trace-scc.md) para buscar mensajes y los valores de Id. de mensaje correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8b24b-166">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="8b24b-167">**Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.</span><span class="sxs-lookup"><span data-stu-id="8b24b-167">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="8b24b-168">**Nombre de directiva**: Use el nombre de la Directiva completa del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8b24b-168">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="8b24b-169">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8b24b-169">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="8b24b-170">**Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.</span><span class="sxs-lookup"><span data-stu-id="8b24b-170">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="8b24b-171">**Asunto**: Use el asunto completo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8b24b-171">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="8b24b-172">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8b24b-172">The search is not case-sensitive.</span></span>

   <span data-ttu-id="8b24b-173">Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="8b24b-173">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="8b24b-174">Cuando encuentre un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar una acción (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="8b24b-174">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="8b24b-175">Exportar los resultados de los mensajes</span><span class="sxs-lookup"><span data-stu-id="8b24b-175">Export message results</span></span>

1. <span data-ttu-id="8b24b-176">Seleccione los mensajes que le interesan y haga clic en **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-176">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="8b24b-177">Haga clic en **Sí** en el mensaje de confirmación que le advierte de que debe mantener abierta la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="8b24b-177">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="8b24b-178">Cuando la exportación esté lista, puede elegir el nombre y la ubicación de descarga del archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="8b24b-178">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="8b24b-179">Ver detalles de mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8b24b-179">View quarantined message details</span></span>

<span data-ttu-id="8b24b-180">Cuando selecciona un mensaje de correo electrónico de la lista, aparecen los detalles de mensaje siguientes en el panel flotante **Detalles**:</span><span class="sxs-lookup"><span data-stu-id="8b24b-180">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="8b24b-181">**Id. de mensaje**: El identificador único global para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8b24b-181">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="8b24b-182">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="8b24b-182">**Sender address**</span></span>

- <span data-ttu-id="8b24b-183">**Recibido**: La fecha/hora en que se ha recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8b24b-183">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="8b24b-184">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="8b24b-184">**Subject**</span></span>

- <span data-ttu-id="8b24b-185">**Motivo de la cuarentena**: Muestra si un mensaje se ha identificado como **Correo no deseado**, **Masivo** o **Suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-185">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="8b24b-186">**Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="8b24b-186">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="8b24b-187">**Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="8b24b-187">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="8b24b-188">**Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.</span><span class="sxs-lookup"><span data-stu-id="8b24b-188">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="8b24b-189">**Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.</span><span class="sxs-lookup"><span data-stu-id="8b24b-189">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="8b24b-190">Llevar a cabo una acción en un correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8b24b-190">Take action on quarantined email</span></span>

<span data-ttu-id="8b24b-191">Después de seleccionar un mensaje, dispone opciones con respecto a qué hacer con los mensajes en el panel flotante **Detalles**:</span><span class="sxs-lookup"><span data-stu-id="8b24b-191">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="8b24b-192">**Liberar mensaje**: En el panel flotante que aparece, elija si desea **Informar de los mensajes a Microsoft para su análisis**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-192">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="8b24b-193">Esta opción está seleccionada de forma predeterminada y comunica a Microsoft el mensaje puesto en cuarentena por error como falso positivo.</span><span class="sxs-lookup"><span data-stu-id="8b24b-193">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="8b24b-194">Cuando haya terminado, haga clic en **Liberar mensajes**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-194">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="8b24b-195">**Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8b24b-195">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="8b24b-196">Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Microsoft 365 complete esta tarea).</span><span class="sxs-lookup"><span data-stu-id="8b24b-196">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="8b24b-197">Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:</span><span class="sxs-lookup"><span data-stu-id="8b24b-197">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="8b24b-198">**Vista previa del mensaje**: En el panel flotante que aparece, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8b24b-198">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="8b24b-199">**Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.</span><span class="sxs-lookup"><span data-stu-id="8b24b-199">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="8b24b-200">**Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="8b24b-200">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="8b24b-201">**Eliminar de cuarentena**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="8b24b-201">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="8b24b-202">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-202">When you're finished, click **Close**.</span></span>

<span data-ttu-id="8b24b-203">Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8b24b-203">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="8b24b-204">Realice una acción en varios mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8b24b-204">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="8b24b-205">Al seleccionar varios mensajes en cuarentena de la lista (hasta 100), se mostrará el panel de control flotante **Acciones en masa**, donde puede realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8b24b-205">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="8b24b-206">**Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar **Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-206">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="8b24b-207">**Eliminar mensajes**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="8b24b-207">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="8b24b-208">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="8b24b-208">When you're finished, click **Close**.</span></span>
