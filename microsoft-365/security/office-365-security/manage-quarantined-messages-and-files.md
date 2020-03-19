---
title: Administrar archivos y mensajes en cuarentena como un administrador en Office 365
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
description: Los administradores pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios. Solo los administradores pueden administrar los mensajes que se pusieron en cuarentena como malware, la suplantación de identidad de confianza alta o como resultado de las reglas de flujo de correo (reglas de transporte).
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857083"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="e96c9-104">Administrar archivos y mensajes en cuarentena como un administrador en Office 365</span><span class="sxs-lookup"><span data-stu-id="e96c9-104">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="e96c9-105">Quarantine contiene mensajes potencialmente peligrosos o no deseados en las organizaciones de Office 365 con buzones en Exchange online o organizaciones independientes de Exchange Online (EOP) sin buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e96c9-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="e96c9-106">Para obtener más información, consulte [Quarantine in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e96c9-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e96c9-107">Los administradores pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e96c9-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="e96c9-108">Solo los administradores pueden administrar los mensajes que se pusieron en cuarentena como malware, la suplantación de identidad de confianza alta o como resultado de las reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="e96c9-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e96c9-109">Los administradores también pueden informar de falsos positivos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e96c9-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="e96c9-110">Los administradores de organizaciones con la protección contra amenazas avanzada (ATP) de Office 365 también pueden ver, descargar y eliminar archivos en cuarentena en SharePoint Online, OneDrive para la empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e96c9-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="e96c9-111">Puede ver y administrar los mensajes en cuarentena en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Office 365 clientes; Exchange Online Protection PowerShell para clientes independientes de EOP).</span><span class="sxs-lookup"><span data-stu-id="e96c9-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e96c9-112">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="e96c9-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e96c9-113">Para abrir el centro de cumplimiento de & de seguridad de Office <https://protection.office.com>365, vaya a.</span><span class="sxs-lookup"><span data-stu-id="e96c9-113">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="e96c9-114">Para abrir la página de cuarentena directamente, vaya <https://protection.office.com/quarantine>a.</span><span class="sxs-lookup"><span data-stu-id="e96c9-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="e96c9-115">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e96c9-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e96c9-116">Para conectarse a PowerShell de Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e96c9-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e96c9-117">Debe tener permisos asignados para poder administrar la cuarentena como administrador. Los permisos se controlan mediante el rol **cuarentena** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e96c9-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="e96c9-118">De forma predeterminada, este rol se asigna a los grupos de roles administración de la **organización** (administradores globales), **Administrador de cuarentena**y administrador de **seguridad** en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e96c9-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="e96c9-119">Para obtener más información, consulte [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e96c9-119">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e96c9-120">Los mensajes en cuarentena se conservan durante un período de tiempo predeterminado antes de que se eliminen automáticamente:</span><span class="sxs-lookup"><span data-stu-id="e96c9-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="e96c9-121">Mensajes puestos en cuarentena por directivas contra correo no deseado (correo no deseado, phishing y correo electrónico masivo): 30 días.</span><span class="sxs-lookup"><span data-stu-id="e96c9-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="e96c9-122">Este es el valor predeterminado y máximo.</span><span class="sxs-lookup"><span data-stu-id="e96c9-122">This is the default and maximum value.</span></span> <span data-ttu-id="e96c9-123">Para configurar este valor, consulte [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e96c9-123">To configure this value, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="e96c9-124">Mensajes puestos en cuarentena por las reglas de flujo de correo (la acción de regla es **entregar el mensaje a la cuarentena hospedada**): 30 días.</span><span class="sxs-lookup"><span data-stu-id="e96c9-124">Messages quarantined by mail flow rules (the rule action is **Deliver the message to the hosted quarantine**): 30 days.</span></span> <span data-ttu-id="e96c9-125">No puede cambiar este valor.</span><span class="sxs-lookup"><span data-stu-id="e96c9-125">You can't change this value.</span></span>

  - <span data-ttu-id="e96c9-126">Mensajes que contienen malware: 15 días.</span><span class="sxs-lookup"><span data-stu-id="e96c9-126">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="e96c9-127">Cuando un mensaje expira de la cuarentena, no puede recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="e96c9-127">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="e96c9-128">Usar el centro de seguridad & cumplimiento para administrar los mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-128">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="e96c9-129">Ver el correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-129">View quarantined email</span></span>

1. <span data-ttu-id="e96c9-130">En el centro de seguridad y cumplimiento, vaya a **Threat Management** \> **Review** \> **Quarantine**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-130">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e96c9-131">Compruebe que **vista en cuarentena** se haya establecido en el **correo**de valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e96c9-131">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="e96c9-132">Puede ordenar los resultados haciendo clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="e96c9-132">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e96c9-133">Haga clic en **modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="e96c9-133">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e96c9-134">Los valores predeterminados están marcados con<sup>\*</sup>un asterisco ():</span><span class="sxs-lookup"><span data-stu-id="e96c9-134">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e96c9-135">**Obtenido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-135">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-136">**Remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-136">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-137">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-137">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-138">**Motivo de cuarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-138">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-139">**Exento?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-139">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-140">**Tipo de Directiva**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-140">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-141">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-141">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-142">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="e96c9-142">**Recipient**</span></span>

   - <span data-ttu-id="e96c9-143">**Id. del mensaje**</span><span class="sxs-lookup"><span data-stu-id="e96c9-143">**Message ID**</span></span>

   - <span data-ttu-id="e96c9-144">**Nombre de la directiva**</span><span class="sxs-lookup"><span data-stu-id="e96c9-144">**Policy name**</span></span>

   - <span data-ttu-id="e96c9-145">**Size**</span><span class="sxs-lookup"><span data-stu-id="e96c9-145">**Size**</span></span>

   - <span data-ttu-id="e96c9-146">**Direction**</span><span class="sxs-lookup"><span data-stu-id="e96c9-146">**Direction**</span></span>

   <span data-ttu-id="e96c9-147">Cuando haya terminado, haga clic en **Guardar**o haga clic en **establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-147">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="e96c9-148">Para filtrar los resultados, haga clic en **filtro**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-148">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e96c9-149">Los filtros disponibles son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e96c9-149">The available filters are:</span></span>

   - <span data-ttu-id="e96c9-150">**Expira el tiempo**: filtrar los mensajes cuando expiren de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="e96c9-150">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="e96c9-151">**Toda**</span><span class="sxs-lookup"><span data-stu-id="e96c9-151">**Today**</span></span>

     - <span data-ttu-id="e96c9-152">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="e96c9-152">**Next 2 days**</span></span>

     - <span data-ttu-id="e96c9-153">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="e96c9-153">**Next 7 days**</span></span>

     - <span data-ttu-id="e96c9-154">**Personalizado**: especifique una **fecha de inicio** y una **fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-154">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e96c9-155">**Hora de recepción**: especifique una **fecha de inicio** y una fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-155">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e96c9-156">**Motivo de cuarentena**:</span><span class="sxs-lookup"><span data-stu-id="e96c9-156">**Quarantine reason**:</span></span>

     - <span data-ttu-id="e96c9-157">**Directiva**: el mensaje coincide con las condiciones de una regla de flujo de correo (también denominada regla de transporte).</span><span class="sxs-lookup"><span data-stu-id="e96c9-157">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="e96c9-158">**Masivo**</span><span class="sxs-lookup"><span data-stu-id="e96c9-158">**Bulk**</span></span>

     - <span data-ttu-id="e96c9-159">**Conseguir**</span><span class="sxs-lookup"><span data-stu-id="e96c9-159">**Phish**</span></span>

     - <span data-ttu-id="e96c9-160">**Malware**</span><span class="sxs-lookup"><span data-stu-id="e96c9-160">**Malware**</span></span>

     - <span data-ttu-id="e96c9-161">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="e96c9-161">**Spam**</span></span>

     - <span data-ttu-id="e96c9-162">**Phish de confianza alta**</span><span class="sxs-lookup"><span data-stu-id="e96c9-162">**High Confidence Phish**</span></span>

   - <span data-ttu-id="e96c9-163">**Destinatario de correo electrónico**: todos los usuarios o solo los mensajes que se le envíen.</span><span class="sxs-lookup"><span data-stu-id="e96c9-163">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="e96c9-164">Los usuarios finales solo pueden administrar los mensajes en cuarentena que se les envían.</span><span class="sxs-lookup"><span data-stu-id="e96c9-164">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="e96c9-165">Para borrar el filtro, haga clic en **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-165">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="e96c9-166">Para ocultar el control flotante de filtro, haga clic de nuevo en **filtro** .</span><span class="sxs-lookup"><span data-stu-id="e96c9-166">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="e96c9-167">Use **ordenar resultados por** (el botón **identificador del mensaje** de forma predeterminada) y un valor correspondiente para buscar mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="e96c9-167">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="e96c9-168">No se admiten caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="e96c9-168">Wildcards aren't supported.</span></span> <span data-ttu-id="e96c9-169">Puede buscar por los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e96c9-169">You can search by the following values:</span></span>

   - <span data-ttu-id="e96c9-170">**Identificador del mensaje**: el identificador único global del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e96c9-170">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="e96c9-171">Por ejemplo, usó el [seguimiento de mensajes](message-trace-scc.md) para buscar un mensaje que se envió a un usuario de su organización y usted determina que el mensaje se puso en cuarentena en lugar de entregarse.</span><span class="sxs-lookup"><span data-stu-id="e96c9-171">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="e96c9-172">Asegúrese de incluir el valor completo del identificador de mensaje, que puede incluir corchetes\<\>angulares ().</span><span class="sxs-lookup"><span data-stu-id="e96c9-172">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="e96c9-173">Por ejemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="e96c9-173">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="e96c9-174">**Dirección de correo electrónico del remitente**: una sola dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="e96c9-174">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="e96c9-175">**Dirección de correo electrónico del destinatario**: dirección de correo electrónico de un único destinatario.</span><span class="sxs-lookup"><span data-stu-id="e96c9-175">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="e96c9-176">**Asunto**: usar el asunto completo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e96c9-176">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="e96c9-177">La búsqueda no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e96c9-177">The search is not case-sensitive.</span></span>

   <span data-ttu-id="e96c9-178">Una vez que haya introducido los criterios de búsqueda ![, haga](../media/scc-quarantine-refresh.png) clic en actualizar botón **Actualizar** para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="e96c9-178">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="e96c9-179">Una vez que haya encontrado un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar acciones en él (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="e96c9-179">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="e96c9-180">Exportar resultados de mensajes</span><span class="sxs-lookup"><span data-stu-id="e96c9-180">Export message results</span></span>

1. <span data-ttu-id="e96c9-181">Seleccione los mensajes que le interesan y haga clic en **exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-181">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="e96c9-182">Haga clic en **sí** en el mensaje de confirmación que le advierte de que debe mantener abierta la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="e96c9-182">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="e96c9-183">Una vez que la exportación esté lista, puede asignar un nombre y elegir la ubicación de descarga del archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="e96c9-183">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="e96c9-184">Ver los detalles de los mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-184">View quarantined message details</span></span>

<span data-ttu-id="e96c9-185">Al seleccionar un mensaje de correo electrónico en la lista, aparecen los siguientes detalles del mensaje en el panel flotante **detalles** :</span><span class="sxs-lookup"><span data-stu-id="e96c9-185">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e96c9-186">**Identificador del mensaje**: el identificador único global para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e96c9-186">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="e96c9-187">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="e96c9-187">**Sender address**</span></span>

- <span data-ttu-id="e96c9-188">**Received**: fecha y hora en que se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e96c9-188">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="e96c9-189">**Subject**</span><span class="sxs-lookup"><span data-stu-id="e96c9-189">**Subject**</span></span>

- <span data-ttu-id="e96c9-190">**Motivo de cuarentena**: muestra si un mensaje se ha identificado **como correo no deseado**, en **masa**, **phish**, coincide con una regla de flujo de correo (**regla de transporte**) o se identificó como **malware**que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="e96c9-190">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="e96c9-191">**Destinatarios**: Si el mensaje contiene varios destinatarios, debe hacer clic en **vista previa del mensaje** o **Ver encabezado de mensaje** para ver la lista completa de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="e96c9-191">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="e96c9-192">**Expires**: fecha y hora en que se eliminará el mensaje de forma automática y permanente de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="e96c9-192">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="e96c9-193">**Fecha de liberación para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.</span><span class="sxs-lookup"><span data-stu-id="e96c9-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="e96c9-194">**Todavía no se ha lanzado a**: todas las direcciones de correo electrónico (si las hay) en las que el mensaje no se ha lanzado todavía.</span><span class="sxs-lookup"><span data-stu-id="e96c9-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="e96c9-195">Realizar acciones en correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-195">Take action on quarantined email</span></span>

<span data-ttu-id="e96c9-196">Después de seleccionar un mensaje, tiene varias opciones para qué hacer con los mensajes en el panel flotante **detalles** :</span><span class="sxs-lookup"><span data-stu-id="e96c9-196">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e96c9-197">**Mensaje de liberación**: en el panel flotante que aparece, elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e96c9-197">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e96c9-198">**Notificar mensajes a Microsoft para su análisis**: esta opción está seleccionada de forma predeterminada y notifica a Microsoft el mensaje con una cuarentena incorrecta como falso positivo.</span><span class="sxs-lookup"><span data-stu-id="e96c9-198">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="e96c9-199">Si el mensaje se puso en cuarentena como correo no deseado, en masa o con suplantación de identidad o con malware, el mensaje también se notifica al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e96c9-199">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="e96c9-200">Según el análisis, las reglas de filtro de correo no deseado de todo el servicio pueden ajustarse para permitir el paso del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e96c9-200">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="e96c9-201">Elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e96c9-201">Choose one of the following options:</span></span>

    - <span data-ttu-id="e96c9-202">**Liberar mensajes para todos los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="e96c9-202">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="e96c9-203">**Liberar mensajes a destinatarios específicos**</span><span class="sxs-lookup"><span data-stu-id="e96c9-203">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="e96c9-204">**Liberar mensajes para otros usuarios**</span><span class="sxs-lookup"><span data-stu-id="e96c9-204">**Release messages to other people**</span></span>

  <span data-ttu-id="e96c9-205">Cuando haya terminado, haga clic en **liberar mensajes**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-205">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="e96c9-206">Notas sobre la liberación de mensajes:</span><span class="sxs-lookup"><span data-stu-id="e96c9-206">Notes about releasing messages:</span></span>

  - <span data-ttu-id="e96c9-207">No puede publicar un mensaje en el mismo destinatario más de una vez.</span><span class="sxs-lookup"><span data-stu-id="e96c9-207">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="e96c9-208">Solo los destinatarios que no recibieron el mensaje aparecerán en la lista de posibles destinatarios.</span><span class="sxs-lookup"><span data-stu-id="e96c9-208">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="e96c9-209">**Ver encabezado de mensaje**: haga clic en este vínculo para ver el texto del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e96c9-209">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="e96c9-210">Para analizar los campos y valores de encabezado en profundidad, copie el texto del encabezado del mensaje en el portapapeles y, a continuación, elija **analizador de encabezados de mensajes de Microsoft** para ir al analizador de conectividad remota (haga clic con el botón secundario y elija **abrir en una nueva pestaña** si no desea salir de Office 365 para completar esta tarea).</span><span class="sxs-lookup"><span data-stu-id="e96c9-210">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="e96c9-211">Pegue el encabezado del mensaje en la página en la sección analizador de encabezados de mensaje y elija **analizar encabezados**:</span><span class="sxs-lookup"><span data-stu-id="e96c9-211">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="e96c9-212">**Vista previa del mensaje**: en el panel flotante que aparece, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e96c9-212">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="e96c9-213">**Vista de código fuente**: muestra la versión HTML del cuerpo del mensaje con todos los vínculos deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="e96c9-213">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="e96c9-214">**Vista de texto**: muestra el cuerpo del mensaje en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="e96c9-214">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="e96c9-215">**Quitar de cuarentena**: después de hacer clic en **sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="e96c9-215">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="e96c9-216">**Mensaje de descarga**: en el panel flotante que aparece, seleccione entiendo **los riesgos de descargar este mensaje** para guardar una copia local del mensaje en formato. eml.</span><span class="sxs-lookup"><span data-stu-id="e96c9-216">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="e96c9-217">**Enviar mensaje**: en el panel flotante que aparece, elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e96c9-217">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e96c9-218">**Tipo de objeto**: **email** (predeterminado), **URL**o **Attachment**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-218">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="e96c9-219">**Formato de envío**: **identificador de mensaje de red** (predeterminado, con el valor correspondiente en el cuadro identificador de mensaje de **red** ) o **archivo** (busque un archivo. eml o. msg local).</span><span class="sxs-lookup"><span data-stu-id="e96c9-219">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="e96c9-220">Tenga en cuenta que si selecciona **archivo** y, a continuación, selecciona **identificador de mensaje de red**, el valor inicial desaparece.</span><span class="sxs-lookup"><span data-stu-id="e96c9-220">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="e96c9-221">**Destinatarios**: escriba la concesión un destinatario original del mensaje o haga clic en **seleccionar todo** para identificar todos los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="e96c9-221">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="e96c9-222">También puede hacer clic en **seleccionar todo** y quitar selectivamente destinatarios individuales.</span><span class="sxs-lookup"><span data-stu-id="e96c9-222">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="e96c9-223">**Motivo del envío**: **no se debe haber bloqueado** (predeterminado) o **debe haberse bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-223">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="e96c9-224">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-224">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="e96c9-225">Si no publica ni quita el mensaje, se eliminará cuando expire el período de retención de cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e96c9-225">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="e96c9-226">Realizar acciones en varios mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-226">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="e96c9-227">Al seleccionar varios mensajes en cuarentena en la lista (hasta 100), aparece el panel flotante **acciones en masa** donde puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e96c9-227">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e96c9-228">**Mensajes de liberación**: las opciones son las mismas que cuando se libera un solo mensaje, excepto que no se pueden seleccionar **mensajes de liberación a destinatarios específicos**; solo puede seleccionar **liberar mensaje para todos los destinatarios** o **mensajes de liberación a otros usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-228">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="e96c9-229">**Eliminar mensajes**: después de hacer clic en **sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="e96c9-229">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="e96c9-230">Cuando haya terminado, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-230">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="e96c9-231">Solo ATP: usar el centro de seguridad & cumplimiento para administrar los archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-231">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="e96c9-232">Los procedimientos para los archivos en cuarentena de esta sección solo están disponibles para los suscriptores de ATP plan 1 y plan 2.</span><span class="sxs-lookup"><span data-stu-id="e96c9-232">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="e96c9-233">En las organizaciones con ATP, los administradores pueden administrar los archivos en cuarentena en SharePoint Online, OneDrive para la empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e96c9-233">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="e96c9-234">Ver archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-234">View quarantined files</span></span>

1. <span data-ttu-id="e96c9-235">En el centro de seguridad y cumplimiento, vaya a **Threat Management** \> **Review** \> **Quarantine**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-235">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e96c9-236">Cambiar **vista en cuarentena** en los **archivos**de valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e96c9-236">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="e96c9-237">Puede ordenar por un campo haciendo clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="e96c9-237">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="e96c9-238">Puede ordenar los resultados haciendo clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="e96c9-238">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e96c9-239">Haga clic en **modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="e96c9-239">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e96c9-240">Las columnas predeterminadas se marcan con<sup>\*</sup>un asterisco ():</span><span class="sxs-lookup"><span data-stu-id="e96c9-240">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e96c9-241">**Usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-241">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-242">**Ubicaciones**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-242">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-243">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-243">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-244">**Dirección URL de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-244">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-245">**Tamaño de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-245">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-246">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-246">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-247">**Exento?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e96c9-247">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="e96c9-248">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="e96c9-248">**Detected by**</span></span>

   - <span data-ttu-id="e96c9-249">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="e96c9-249">**Modified by time**</span></span>

4. <span data-ttu-id="e96c9-250">Para filtrar los resultados, haga clic en **filtro**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-250">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e96c9-251">Los filtros disponibles son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e96c9-251">The available filters are:</span></span>

   - <span data-ttu-id="e96c9-252">**Expira el tiempo**: filtrar los mensajes cuando expiren de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="e96c9-252">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="e96c9-253">**Toda**</span><span class="sxs-lookup"><span data-stu-id="e96c9-253">**Today**</span></span>

     - <span data-ttu-id="e96c9-254">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="e96c9-254">**Next 2 days**</span></span>

     - <span data-ttu-id="e96c9-255">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="e96c9-255">**Next 7 days**</span></span>

     - <span data-ttu-id="e96c9-256">Un intervalo de fecha y hora personalizado.</span><span class="sxs-lookup"><span data-stu-id="e96c9-256">A custom date/time range.</span></span>

   - <span data-ttu-id="e96c9-257">**Hora de recepción**</span><span class="sxs-lookup"><span data-stu-id="e96c9-257">**Received time**</span></span>

   - <span data-ttu-id="e96c9-258">**Motivo de cuarentena**: el único valor disponible es **malware**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-258">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="e96c9-259">Una vez que haya encontrado un archivo en cuarentena específico, seleccione el archivo para ver los detalles del mismo y para realizar acciones en él (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="e96c9-259">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="e96c9-260">Resultados de la exportación de archivos</span><span class="sxs-lookup"><span data-stu-id="e96c9-260">Export file results</span></span>

1. <span data-ttu-id="e96c9-261">Seleccione los archivos que le interesan y haga clic en **exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-261">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="e96c9-262">Haga clic en **sí** en el mensaje de confirmación que le advierte de que debe mantener abierta la ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="e96c9-262">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="e96c9-263">Una vez que la exportación esté lista, puede asignar un nombre y elegir la ubicación de descarga del archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="e96c9-263">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="e96c9-264">Ver detalles de archivo en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-264">View quarantined file details</span></span>

<span data-ttu-id="e96c9-265">Al seleccionar un archivo de la lista, aparecen los siguientes detalles de archivo en el panel flotante de **detalles** :</span><span class="sxs-lookup"><span data-stu-id="e96c9-265">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e96c9-266">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="e96c9-266">**File Name**</span></span>

- <span data-ttu-id="e96c9-267">**Dirección URL del archivo**: dirección URL que define la ubicación del archivo (por ejemplo, en SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="e96c9-267">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="e96c9-268">**Contenido malintencionado detectado en** La fecha y la hora en que se puso en cuarentena el archivo.</span><span class="sxs-lookup"><span data-stu-id="e96c9-268">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="e96c9-269">**Expires**: la fecha en la que se eliminará el archivo de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="e96c9-269">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="e96c9-270">**Detectado por**: ATP (protección contra amenazas avanzada) o motor antimalware de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e96c9-270">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="e96c9-271">**Exento?**</span><span class="sxs-lookup"><span data-stu-id="e96c9-271">**Released?**</span></span>

- <span data-ttu-id="e96c9-272">**Nombre del malware**</span><span class="sxs-lookup"><span data-stu-id="e96c9-272">**Malware Name**</span></span>

- <span data-ttu-id="e96c9-273">**Identificador de documento**: un identificador único para el documento.</span><span class="sxs-lookup"><span data-stu-id="e96c9-273">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="e96c9-274">**Tamaño de archivo**: en kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="e96c9-274">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="e96c9-275">**Organización** El identificador único de su organización.</span><span class="sxs-lookup"><span data-stu-id="e96c9-275">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="e96c9-276">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="e96c9-276">**Last modified**</span></span>

- <span data-ttu-id="e96c9-277">**Modificado por**: el usuario que modificó el archivo por última vez.</span><span class="sxs-lookup"><span data-stu-id="e96c9-277">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="e96c9-278">**Algoritmo hash seguro 256-bit (SHA-256) valor**: puede usar este valor de hash para identificar el archivo en otros almacenes de reputación o en otras ubicaciones del entorno.</span><span class="sxs-lookup"><span data-stu-id="e96c9-278">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="e96c9-279">Realizar acciones en archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-279">Take action on quarantined files</span></span>

<span data-ttu-id="e96c9-280">Al seleccionar un archivo de la lista, puede realizar las siguientes acciones en el archivo del panel flotante de **detalles** :</span><span class="sxs-lookup"><span data-stu-id="e96c9-280">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e96c9-281">**Liberar archivos**: seleccione (predeterminado) o anule la selección **de archivos de informe a Microsoft para su análisis**y, a continuación, haga clic en **liberar archivos**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-281">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="e96c9-282">**Descargar archivo**</span><span class="sxs-lookup"><span data-stu-id="e96c9-282">**Download file**</span></span>

- <span data-ttu-id="e96c9-283">**Quitar archivo de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="e96c9-283">**Remove file from quarantine**</span></span>

<span data-ttu-id="e96c9-284">Si no libera ni quita los archivos, se eliminarán después de que expire el período de retención de cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e96c9-284">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="e96c9-285">Acciones en varios archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-285">Actions on multiple quarantined files</span></span>

<span data-ttu-id="e96c9-286">Al seleccionar varios archivos en cuarentena en la lista (hasta 100), aparece el panel flotante **acciones en masa** donde puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e96c9-286">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e96c9-287">**Liberar archivos**</span><span class="sxs-lookup"><span data-stu-id="e96c9-287">**Release files**</span></span>

- <span data-ttu-id="e96c9-288">**Eliminar archivos**: después de hacer clic en **sí** en la advertencia que aparece, los archivos se eliminan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="e96c9-288">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

<span data-ttu-id="e96c9-289">Cuando haya terminado, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e96c9-289">When you're finished, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="e96c9-290">Usar Exchange Online PowerShell o PowerShell independiente de Exchange Online Protection para ver y administrar los mensajes y archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e96c9-290">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="e96c9-291">Los cmdlets que se usan para ver y administrar mensajes y archivos en cuarentena son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e96c9-291">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="e96c9-292">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e96c9-292">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="e96c9-293">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e96c9-293">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="e96c9-294">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e96c9-294">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="e96c9-295">[Vista previa de QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): tenga en cuenta que este cmdlet solo es para los mensajes, no para los archivos de malware de ATP para SharePoint Online, OneDrive para la empresa o Teams.</span><span class="sxs-lookup"><span data-stu-id="e96c9-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="e96c9-296">Versión-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e96c9-296">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
