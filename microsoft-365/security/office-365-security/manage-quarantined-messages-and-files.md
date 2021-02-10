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
description: Los administradores pueden aprender a ver y administrar mensajes en cuarentena para todos los usuarios en Exchange Online Protection (EOP). Los administradores de organizaciones con Microsoft Defender para Office 365 también pueden administrar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a91f53f8efe4fa6944f0debff472da87b7f17e0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167496"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="4423a-104">Administración de mensajes en cuarentena y archivos como administrador en EOP</span><span class="sxs-lookup"><span data-stu-id="4423a-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4423a-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="4423a-105">**Applies to**</span></span>
- [<span data-ttu-id="4423a-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4423a-106">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="4423a-107">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="4423a-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="4423a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4423a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="4423a-109">En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados.</span><span class="sxs-lookup"><span data-stu-id="4423a-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="4423a-110">Para obtener más información, vea [Mensajes de correo electrónico en cuarentena en EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="4423a-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="4423a-111">Los administradores pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4423a-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="4423a-112">Solo los administradores pueden administrar mensajes que se han puesto en cuarentena como malware, suplantación de identidad de confianza alta o como resultado de reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="4423a-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="4423a-113">Los administradores también pueden notificar falsos positivos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4423a-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="4423a-114">Los administradores de organizaciones con Microsoft Defender para Office 365 también pueden ver, descargar y eliminar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4423a-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="4423a-115">Puede ver y administrar los mensajes en cuarentena en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="4423a-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4423a-116">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="4423a-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4423a-117">Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="4423a-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="4423a-118">Para abrir directamente la página de Cuarentena, vaya a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="4423a-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="4423a-119">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4423a-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4423a-120">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="4423a-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4423a-121">Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="4423a-121">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4423a-122">Para realizar acciones en los mensajes en cuarentena para todos los usuarios, debe  ser miembro de los grupos de roles Administración de la **organización,** Administrador de seguridad o Administrador <sup>\*</sup> de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4423a-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="4423a-123">Para obtener acceso de solo lectura a los mensajes en cuarentena para todos los usuarios, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="4423a-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4423a-124">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4423a-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="4423a-125">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="4423a-125">**Notes**:</span></span>

  - <span data-ttu-id="4423a-126">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4423a-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4423a-127">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="4423a-127">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="4423a-128">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="4423a-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="4423a-129"><sup>\*</sup> Los miembros del grupo **de** roles Administrador de cuarentena también deben ser miembros del grupo de roles **Administración** de higiene en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) para poder realizar procedimientos de cuarentena en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4423a-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="4423a-130">Los mensajes en cuarentena se conservan durante un período de tiempo predeterminado antes de que se eliminen automáticamente:</span><span class="sxs-lookup"><span data-stu-id="4423a-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="4423a-131">30 días para los mensajes en cuarentena por directivas contra correo no deseado (correo no deseado, suplantación de identidad y correo electrónico masivo).</span><span class="sxs-lookup"><span data-stu-id="4423a-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="4423a-132">Este es el valor predeterminado y máximo.</span><span class="sxs-lookup"><span data-stu-id="4423a-132">This is the default and maximum value.</span></span> <span data-ttu-id="4423a-133">Para configurar (inferior) este valor, consulte [Configurar directivas contra correo no deseado.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4423a-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="4423a-134">15 días para los mensajes que contienen malware.</span><span class="sxs-lookup"><span data-stu-id="4423a-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="4423a-135">15 días para los archivos en cuarentena por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams en Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="4423a-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="4423a-136">Cuando un mensaje expira de la cuarentena, no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="4423a-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="4423a-137">Usar el Centro de seguridad & cumplimiento para administrar mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="4423a-138">Ver el correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-138">View quarantined email</span></span>

1. <span data-ttu-id="4423a-139">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="4423a-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="4423a-140">Compruebe que **La vista en cuarentena** está establecida en el valor predeterminado correo **electrónico.**</span><span class="sxs-lookup"><span data-stu-id="4423a-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="4423a-141">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="4423a-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="4423a-142">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="4423a-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="4423a-143">Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="4423a-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="4423a-144">**Recibido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-145">**Remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-146">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-147">**Motivo de la cuarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-148">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-149">**Tipo de directiva**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-150">**Expires**</span><span class="sxs-lookup"><span data-stu-id="4423a-150">**Expires**</span></span>
   - <span data-ttu-id="4423a-151">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="4423a-151">**Recipient**</span></span>
   - <span data-ttu-id="4423a-152">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="4423a-152">**Message ID**</span></span>
   - <span data-ttu-id="4423a-153">**Nombre de la directiva**</span><span class="sxs-lookup"><span data-stu-id="4423a-153">**Policy name**</span></span>
   - <span data-ttu-id="4423a-154">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="4423a-154">**Size**</span></span>
   - <span data-ttu-id="4423a-155">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="4423a-155">**Direction**</span></span>

   <span data-ttu-id="4423a-156">Cuando haya terminado, haga clic en **Guardar** o en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="4423a-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="4423a-157">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="4423a-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4423a-158">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="4423a-158">The available filters are:</span></span>

   - <span data-ttu-id="4423a-159">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="4423a-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="4423a-160">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="4423a-160">**Today**</span></span>
     - <span data-ttu-id="4423a-161">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="4423a-161">**Next 2 days**</span></span>
     - <span data-ttu-id="4423a-162">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="4423a-162">**Next 7 days**</span></span>
     - <span data-ttu-id="4423a-163">**Personalizado**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="4423a-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4423a-164">**Hora de recepción**: Introduzca **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="4423a-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4423a-165">**Motivo de la cuarentena**:</span><span class="sxs-lookup"><span data-stu-id="4423a-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="4423a-166">**Directiva:** el mensaje coincidía con las condiciones de una regla de flujo de correo (también conocida como regla de transporte).</span><span class="sxs-lookup"><span data-stu-id="4423a-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="4423a-167">**Correo masivo**</span><span class="sxs-lookup"><span data-stu-id="4423a-167">**Bulk**</span></span>
     - <span data-ttu-id="4423a-168">**Phish:** el veredicto del filtro de correo no deseado [](set-up-anti-phishing-policies.md#spoof-settings) era correo electrónico de suplantación de identidad **(phishing)** o protección contra suplantación de identidad (protección contra suplantación [de](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)identidad).</span><span class="sxs-lookup"><span data-stu-id="4423a-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="4423a-169">**Malware**</span><span class="sxs-lookup"><span data-stu-id="4423a-169">**Malware**</span></span>
     - <span data-ttu-id="4423a-170">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="4423a-170">**Spam**</span></span>
     - <span data-ttu-id="4423a-171">**Suplantación de identidad de confianza alta**</span><span class="sxs-lookup"><span data-stu-id="4423a-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="4423a-172">**Tipo de directiva**: Filtrar mensajes por tipo de directiva:</span><span class="sxs-lookup"><span data-stu-id="4423a-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="4423a-173">**Directiva antimalware**</span><span class="sxs-lookup"><span data-stu-id="4423a-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="4423a-174">**Directiva de datos adjuntos seguros**</span><span class="sxs-lookup"><span data-stu-id="4423a-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="4423a-175">**Política Antiphishing**</span><span class="sxs-lookup"><span data-stu-id="4423a-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="4423a-176">**Directiva de filtro de contenido alojado** (directiva anti-spam)</span><span class="sxs-lookup"><span data-stu-id="4423a-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="4423a-177">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="4423a-177">**Transport rule**</span></span>

   - <span data-ttu-id="4423a-178">**Destinatario de correo** electrónico: todos los usuarios o solo los mensajes que se le envíen.</span><span class="sxs-lookup"><span data-stu-id="4423a-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="4423a-179">Los usuarios finales solo pueden administrar los mensajes en cuarentena que se les envían.</span><span class="sxs-lookup"><span data-stu-id="4423a-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="4423a-180">Para borrar el filtro, haga clic en **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="4423a-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="4423a-181">Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="4423a-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="4423a-182">Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="4423a-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="4423a-183">No se admiten los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="4423a-183">Wildcards aren't supported.</span></span> <span data-ttu-id="4423a-184">Puede buscar según los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="4423a-184">You can search by the following values:</span></span>

   - <span data-ttu-id="4423a-185">**Id. de mensaje**: El identificador único global del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4423a-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="4423a-186">Por ejemplo, [](message-trace-scc.md) usó el seguimiento de mensajes para buscar un mensaje que se envió a un usuario de su organización y determinar que el mensaje se ha puesto en cuarentena en lugar de entregarse.</span><span class="sxs-lookup"><span data-stu-id="4423a-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="4423a-187">Asegúrese de incluir el valor completo del identificador de mensaje, que puede incluir corchetes angulares ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="4423a-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="4423a-188">Por ejemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="4423a-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="4423a-189">**Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.</span><span class="sxs-lookup"><span data-stu-id="4423a-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="4423a-190">**Nombre de directiva**: Use el nombre de la Directiva completa del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4423a-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="4423a-191">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4423a-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="4423a-192">**Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.</span><span class="sxs-lookup"><span data-stu-id="4423a-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="4423a-193">**Asunto**: Use el asunto completo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4423a-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="4423a-194">La búsqueda no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4423a-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="4423a-195">**Nombre de** la directiva: el nombre de la directiva responsable de la anulación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4423a-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="4423a-196">Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="4423a-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="4423a-197">Cuando encuentre un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar una acción (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="4423a-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="4423a-198">Ver detalles de mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-198">View quarantined message details</span></span>

<span data-ttu-id="4423a-199">Cuando selecciona un mensaje de correo electrónico de la lista, aparecen los detalles de mensaje siguientes en el panel flotante **Detalles**:</span><span class="sxs-lookup"><span data-stu-id="4423a-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4423a-200">**Id. de mensaje**: El identificador único global para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4423a-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="4423a-201">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="4423a-201">**Sender address**</span></span>

- <span data-ttu-id="4423a-202">**Recibido**: La fecha/hora en que se ha recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4423a-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="4423a-203">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="4423a-203">**Subject**</span></span>

- <span data-ttu-id="4423a-204">**Motivo de la** cuarentena: muestra si un mensaje se ha identificado como correo no deseado **,** masivo **,** suplantación de identidad **,** coincide con una regla de flujo de correo **(** regla de transporte ) o se identificó como que contiene **malware**.</span><span class="sxs-lookup"><span data-stu-id="4423a-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="4423a-205">**Número de destinatarios**</span><span class="sxs-lookup"><span data-stu-id="4423a-205">**Recipient count**</span></span>

- <span data-ttu-id="4423a-206">**Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="4423a-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="4423a-207">**Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4423a-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="4423a-208">**Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.</span><span class="sxs-lookup"><span data-stu-id="4423a-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="4423a-209">**Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.</span><span class="sxs-lookup"><span data-stu-id="4423a-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="4423a-210">Llevar a cabo una acción en un correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-210">Take action on quarantined email</span></span>

<span data-ttu-id="4423a-211">Después de seleccionar un mensaje, tiene varias opciones para  saber qué hacer con los mensajes en el panel desplegable Detalles:</span><span class="sxs-lookup"><span data-stu-id="4423a-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4423a-212">**Mensaje de versión:** en el panel desplegable que aparece, elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4423a-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="4423a-213">**Notificar mensajes a Microsoft para su** análisis: esta opción está seleccionada de forma predeterminada e informa de que el mensaje en cuarentena erróneamente a Microsoft es un falso positivo.</span><span class="sxs-lookup"><span data-stu-id="4423a-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="4423a-214">Si el mensaje se ha puesto en cuarentena como correo no deseado, masivo, suplantación de identidad (phishing) o que contiene malware, el mensaje también se notifica al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4423a-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="4423a-215">Según su análisis, las reglas de filtro de correo no deseado de todo el servicio podrían ajustarse para permitir que pase el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4423a-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="4423a-216">Elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4423a-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="4423a-217">**Liberar mensajes para todos los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="4423a-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="4423a-218">**Liberar mensajes a destinatarios específicos**</span><span class="sxs-lookup"><span data-stu-id="4423a-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="4423a-219">**Liberar mensajes a otras personas:** tenga en cuenta que no se admite liberar mensajes de malware para personas que no son destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="4423a-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="4423a-220">Cuando haya terminado, haga clic en **Liberar mensajes**.</span><span class="sxs-lookup"><span data-stu-id="4423a-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="4423a-221">Notas sobre la publicación de mensajes:</span><span class="sxs-lookup"><span data-stu-id="4423a-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="4423a-222">No puede liberar un mensaje para el mismo destinatario más de una vez.</span><span class="sxs-lookup"><span data-stu-id="4423a-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="4423a-223">Solo los destinatarios que no hayan recibido el mensaje aparecerán en la lista de posibles destinatarios.</span><span class="sxs-lookup"><span data-stu-id="4423a-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="4423a-224">**Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4423a-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="4423a-225">Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Microsoft 365 complete esta tarea).</span><span class="sxs-lookup"><span data-stu-id="4423a-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="4423a-226">Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:</span><span class="sxs-lookup"><span data-stu-id="4423a-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="4423a-227">**Vista previa del mensaje**: En el panel flotante que aparece, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4423a-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="4423a-228">**Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.</span><span class="sxs-lookup"><span data-stu-id="4423a-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="4423a-229">**Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="4423a-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="4423a-230">**Quitar de cuarentena:** después de hacer clic **en** Sí en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="4423a-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="4423a-231">**Descargar mensaje**: En el panel de flotante que aparece, seleccione **Entiendo los riesgos de descargar este mensaje** para guardar una copia local del mensaje en formato .eml.</span><span class="sxs-lookup"><span data-stu-id="4423a-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="4423a-232">**Enviar mensaje:** en el panel desplegable que aparece, elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4423a-232">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="4423a-233">**Tipo de objeto**: **Correo** electrónico (predeterminado), **DIRECCIÓN URL** o **Datos adjuntos.**</span><span class="sxs-lookup"><span data-stu-id="4423a-233">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="4423a-234">**Formato de** envío: **Id.** de mensaje de  red (predeterminado, con el valor correspondiente en el cuadro Id. de mensaje de red) o **Archivo** (vaya a un archivo .eml o .msg local).</span><span class="sxs-lookup"><span data-stu-id="4423a-234">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="4423a-235">Tenga en cuenta que si selecciona **Archivo** y, a continuación, selecciona **Id.** de mensaje de red, el valor inicial se ha perdido.</span><span class="sxs-lookup"><span data-stu-id="4423a-235">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="4423a-236">**Destinatarios:** escriba al concesión un destinatario original del mensaje o haga clic en Seleccionar todo **para** identificar a todos los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="4423a-236">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="4423a-237">También puede hacer clic **en Seleccionar todo** y, a continuación, quitar destinatarios individuales de forma selectiva.</span><span class="sxs-lookup"><span data-stu-id="4423a-237">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="4423a-238">**Motivo del envío:** **no debería haber sido bloqueado** (predeterminado) o debería haber sido **bloqueado.**</span><span class="sxs-lookup"><span data-stu-id="4423a-238">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="4423a-239">Cuando haya terminado, haga clic en **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="4423a-239">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="4423a-240">Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4423a-240">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="4423a-241">Realice una acción en varios mensajes de correo electrónico en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-241">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="4423a-242">Al seleccionar varios mensajes en cuarentena de la lista (hasta 100), se mostrará el panel de control flotante **Acciones en masa**, donde puede realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4423a-242">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="4423a-243">**Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar **Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.</span><span class="sxs-lookup"><span data-stu-id="4423a-243">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4423a-244">Tenga en cuenta el siguiente escenario: john@gmail.com un mensaje a faith@contoso.com y john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4423a-244">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="4423a-245">Gmail bifurca este mensaje en dos copias que se enruta a cuarentena como suplantación de identidad en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4423a-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="4423a-246">Un administrador libera estos dos mensajes para admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4423a-246">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="4423a-247">Se entrega el primer mensaje publicado que llega al buzón de administrador.</span><span class="sxs-lookup"><span data-stu-id="4423a-247">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="4423a-248">El segundo mensaje publicado se identifica como entrega duplicada y se omite.</span><span class="sxs-lookup"><span data-stu-id="4423a-248">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="4423a-249">Los mensajes se identifican como duplicados si tienen el mismo identificador de mensaje y la misma hora de recibido.</span><span class="sxs-lookup"><span data-stu-id="4423a-249">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="4423a-250">**Eliminar mensajes:** después de hacer clic en **Sí** en la advertencia que aparece, los mensajes se eliminan inmediatamente sin que se envíen a los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="4423a-250">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="4423a-251">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4423a-251">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="4423a-252">Solo Microsoft Defender para Office 365: Usar el Centro de seguridad & cumplimiento para administrar archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-252">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="4423a-253">Los procedimientos para archivos en cuarentena de esta sección solo están disponibles para suscriptores de Microsoft Defender para Office 365 Plan 1 y Plan 2.</span><span class="sxs-lookup"><span data-stu-id="4423a-253">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="4423a-254">En organizaciones con Defender para Office 365, los administradores pueden administrar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4423a-254">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="4423a-255">Para habilitar la protección de estos archivos, vea Activar datos adjuntos seguros [para SharePoint, OneDrive y Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4423a-255">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="4423a-256">Ver archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-256">View quarantined files</span></span>

1. <span data-ttu-id="4423a-257">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="4423a-257">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="4423a-258">Cambiar **vista en cuarentena a** los archivos de **valor.**</span><span class="sxs-lookup"><span data-stu-id="4423a-258">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="4423a-259">Puede ordenar un campo haciendo clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="4423a-259">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="4423a-260">Para ordenar los resultados, haga clic en un encabezado de columna disponible.</span><span class="sxs-lookup"><span data-stu-id="4423a-260">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="4423a-261">Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas.</span><span class="sxs-lookup"><span data-stu-id="4423a-261">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="4423a-262">Las columnas predeterminadas se marcan con un asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="4423a-262">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="4423a-263">**Usuario**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-263">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-264">**Ubicación**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-264">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-265">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-265">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-266">**Dirección URL del archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-266">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-267">**Tamaño de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-267">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-268">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-268">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-269">**¿Liberado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4423a-269">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="4423a-270">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="4423a-270">**Detected by**</span></span>
   - <span data-ttu-id="4423a-271">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="4423a-271">**Modified by time**</span></span>

4. <span data-ttu-id="4423a-272">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="4423a-272">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4423a-273">Los filtros disponibles son:</span><span class="sxs-lookup"><span data-stu-id="4423a-273">The available filters are:</span></span>

   - <span data-ttu-id="4423a-274">**Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:</span><span class="sxs-lookup"><span data-stu-id="4423a-274">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="4423a-275">**Hoy**</span><span class="sxs-lookup"><span data-stu-id="4423a-275">**Today**</span></span>
     - <span data-ttu-id="4423a-276">**Próximos 2 días**</span><span class="sxs-lookup"><span data-stu-id="4423a-276">**Next 2 days**</span></span>
     - <span data-ttu-id="4423a-277">**Próximos 7 días**</span><span class="sxs-lookup"><span data-stu-id="4423a-277">**Next 7 days**</span></span>
     - <span data-ttu-id="4423a-278">Un intervalo de fecha y hora personalizado.</span><span class="sxs-lookup"><span data-stu-id="4423a-278">A custom date/time range.</span></span>
   - <span data-ttu-id="4423a-279">**Tiempo de recibido**</span><span class="sxs-lookup"><span data-stu-id="4423a-279">**Received time**</span></span>
   - <span data-ttu-id="4423a-280">**Motivo de la** cuarentena: el único valor disponible es **Malware**.</span><span class="sxs-lookup"><span data-stu-id="4423a-280">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="4423a-281">**Tipo de directiva**</span><span class="sxs-lookup"><span data-stu-id="4423a-281">**Policy type**</span></span>

<span data-ttu-id="4423a-282">Después de encontrar un archivo en cuarentena específico, seleccione el archivo para ver los detalles sobre él y para realizar acciones en él (por ejemplo, ver, liberar, descargar o eliminar el mensaje).</span><span class="sxs-lookup"><span data-stu-id="4423a-282">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="4423a-283">Ver detalles del archivo en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-283">View quarantined file details</span></span>

<span data-ttu-id="4423a-284">Al seleccionar un archivo en la lista, los siguientes detalles del archivo aparecen en el **panel** desplegable Detalles:</span><span class="sxs-lookup"><span data-stu-id="4423a-284">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4423a-285">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="4423a-285">**File Name**</span></span>
- <span data-ttu-id="4423a-286">**Dirección URL del** archivo: dirección URL que define la ubicación del archivo (por ejemplo, en SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="4423a-286">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="4423a-287">**Contenido malintencionado detectado en** La fecha y hora en que el archivo se ha puesto en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4423a-287">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="4423a-288">**Expira:** la fecha en la que el archivo se eliminará de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4423a-288">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="4423a-289">**Detectado por**: Defender para Office 365 o el motor antimalware de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4423a-289">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="4423a-290">**¿Liberado?**</span><span class="sxs-lookup"><span data-stu-id="4423a-290">**Released?**</span></span>
- <span data-ttu-id="4423a-291">**Nombre de malware**</span><span class="sxs-lookup"><span data-stu-id="4423a-291">**Malware Name**</span></span>
- <span data-ttu-id="4423a-292">**Identificador de** documento: identificador único del documento.</span><span class="sxs-lookup"><span data-stu-id="4423a-292">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="4423a-293">**Tamaño de archivo:** en kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="4423a-293">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="4423a-294">**Organización** Identificador único de su organización.</span><span class="sxs-lookup"><span data-stu-id="4423a-294">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="4423a-295">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="4423a-295">**Last modified**</span></span>
- <span data-ttu-id="4423a-296">**Modificado por:** el usuario que modificó por última vez el archivo.</span><span class="sxs-lookup"><span data-stu-id="4423a-296">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="4423a-297">Valor de algoritmo hash seguro de **256 bits (SHA-256):** puede usar este valor hash para identificar el archivo en otros almacenes de reputación o en otras ubicaciones de su entorno.</span><span class="sxs-lookup"><span data-stu-id="4423a-297">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="4423a-298">Realizar acciones en archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-298">Take action on quarantined files</span></span>

<span data-ttu-id="4423a-299">Al seleccionar un archivo en la lista, puede realizar las siguientes acciones en el archivo en el **panel** desplegable Detalles:</span><span class="sxs-lookup"><span data-stu-id="4423a-299">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4423a-300">**Archivos de versión:** seleccione (predeterminado) o anule la selección de archivos de informe a **Microsoft** para su análisis y, a continuación, haga clic **en Liberar archivos**.</span><span class="sxs-lookup"><span data-stu-id="4423a-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="4423a-301">**Descargar archivo**</span><span class="sxs-lookup"><span data-stu-id="4423a-301">**Download file**</span></span>
- <span data-ttu-id="4423a-302">**Quitar archivo de cuarentena**</span><span class="sxs-lookup"><span data-stu-id="4423a-302">**Remove file from quarantine**</span></span>

<span data-ttu-id="4423a-303">Si no libera o quita los archivos, se eliminarán después de que expire el período de retención de cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4423a-303">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="4423a-304">Acciones en varios archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-304">Actions on multiple quarantined files</span></span>

<span data-ttu-id="4423a-305">Cuando selecciona varios archivos en cuarentena en la lista (hasta 100), aparece el panel desplegable Acciones masivas, donde puede realizar las siguientes acciones: </span><span class="sxs-lookup"><span data-stu-id="4423a-305">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="4423a-306">**Liberar archivos**</span><span class="sxs-lookup"><span data-stu-id="4423a-306">**Release files**</span></span>
- <span data-ttu-id="4423a-307">**Eliminar archivos:** después de hacer clic en **Sí** en la advertencia que aparece, los archivos se eliminan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="4423a-307">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="4423a-308">Usar Exchange Online PowerShell o EOP PowerShell independiente para ver y administrar mensajes y archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4423a-308">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="4423a-309">Los cmdlets que usa para ver y administrar mensajes y archivos en cuarentena son:</span><span class="sxs-lookup"><span data-stu-id="4423a-309">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="4423a-310">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4423a-310">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="4423a-311">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4423a-311">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="4423a-312">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4423a-312">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="4423a-313">[Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)tenga en cuenta que este cmdlet solo es para mensajes, no archivos de malware de datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4423a-313">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="4423a-314">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="4423a-314">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
