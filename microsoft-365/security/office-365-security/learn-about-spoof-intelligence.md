---
title: Configurar la inteligencia de suplantación
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la suplantación de identidad en Exchange Online Protection (EOP), donde puede permitir o bloquear remitentes suplantados específicos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 482978e93325344d897fcf907b026743fc393d47
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406645"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="829f5-103">Configurar la inteligencia de suplantación en EOP</span><span class="sxs-lookup"><span data-stu-id="829f5-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="829f5-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="829f5-104">**Applies to**</span></span>
- [<span data-ttu-id="829f5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="829f5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="829f5-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="829f5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="829f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="829f5-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="829f5-108">En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes de correo electrónico entrantes se protegen automáticamente contra la suplantación por parte de EOP a partir de octubre de 2018.</span><span class="sxs-lookup"><span data-stu-id="829f5-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="829f5-109">EOP usa la inteligencia de suplantación de identidad como parte de la defensa general de su organización contra el phishing.</span><span class="sxs-lookup"><span data-stu-id="829f5-109">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="829f5-110">Para obtener más información, vea Protección contra [la suplantación en EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="829f5-110">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="829f5-111">Cuando un remitente suplanta una dirección de correo electrónico, parece que es un usuario de uno de los dominios de la organización o un usuario de un dominio externo que envía correo electrónico a su organización.</span><span class="sxs-lookup"><span data-stu-id="829f5-111">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="829f5-112">Los atacantes que suplanten remitentes para enviar correo no deseado o correo electrónico de suplantación de identidad deben bloquearse.</span><span class="sxs-lookup"><span data-stu-id="829f5-112">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="829f5-113">Pero hay escenarios en los que los remitentes legítimos están suplantando.</span><span class="sxs-lookup"><span data-stu-id="829f5-113">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="829f5-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="829f5-114">For example:</span></span>

- <span data-ttu-id="829f5-115">Escenarios legítimos para suplantar dominios internos:</span><span class="sxs-lookup"><span data-stu-id="829f5-115">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="829f5-116">Los remitentes de terceros usan su dominio para enviar correo masivo a sus propios empleados para sondeos de empresa.</span><span class="sxs-lookup"><span data-stu-id="829f5-116">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="829f5-117">Una empresa externa genera y envía actualizaciones de productos o publicidad en su nombre.</span><span class="sxs-lookup"><span data-stu-id="829f5-117">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="829f5-118">Un asistente debe enviar correo electrónico periódicamente a otra persona dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="829f5-118">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="829f5-119">Una aplicación interna envía notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="829f5-119">An internal application sends email notifications.</span></span>

- <span data-ttu-id="829f5-120">Escenarios legítimos para suplantar dominios externos:</span><span class="sxs-lookup"><span data-stu-id="829f5-120">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="829f5-121">El remitente está en una lista de correo (también conocida como lista de discusión) y la lista de correo retransmite el correo electrónico del remitente original a todos los participantes de la lista de correo.</span><span class="sxs-lookup"><span data-stu-id="829f5-121">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="829f5-122">Una empresa externa envía correo electrónico en nombre de otra compañía (por ejemplo, un informe automatizado o una compañía de software como servicio).</span><span class="sxs-lookup"><span data-stu-id="829f5-122">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="829f5-123">La inteligencia de suplantación de identidad y, específicamente, la directiva de suplantación de identidad predeterminada (y única), ayuda a garantizar que el correo electrónico suplantado enviado por remitentes legítimos no se desentraña en los filtros de correo no deseado de EOP o en los sistemas de correo electrónico externo, al tiempo que protege a los usuarios de los ataques de correo no deseado o phishing.</span><span class="sxs-lookup"><span data-stu-id="829f5-123">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="829f5-124">Puede administrar la inteligencia de suplantación en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="829f5-124">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="829f5-125">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="829f5-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="829f5-126">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="829f5-126">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="829f5-127">Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="829f5-127">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="829f5-128">Para ir directamente a la **página Anti-phishing,** use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="829f5-128">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="829f5-129">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="829f5-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="829f5-130">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="829f5-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="829f5-131">Debe tener asignados permisos en **Exchange Online** para poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="829f5-131">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="829f5-132">Para modificar la directiva de inteligencia suplantada o habilitar o deshabilitar la  inteligencia suplantada, debe ser miembro de los grupos de roles Administración de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="829f5-132">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="829f5-133">Para obtener acceso de solo lectura a la directiva de inteligencia suplantada, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="829f5-133">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="829f5-134">Para obtener más información, consulte los [permisos en Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="829f5-134">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="829f5-135">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="829f5-135">**Notes**:</span></span>

  - <span data-ttu-id="829f5-136">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos y permisos necesarios para _otras_ características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="829f5-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="829f5-137">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="829f5-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="829f5-138">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="829f5-138">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="829f5-139">Para obtener la configuración recomendada para la inteligencia de suplantación de identidad, consulte Configuración predeterminada de la directiva [contra suplantación de](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)identidad de EOP.</span><span class="sxs-lookup"><span data-stu-id="829f5-139">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="829f5-140">Usar el Centro de seguridad & cumplimiento para administrar remitentes suplantados</span><span class="sxs-lookup"><span data-stu-id="829f5-140">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="829f5-141">Si tiene una suscripción a Microsoft 365 Enterprise E5 o ha comprado por separado un complemento de Microsoft Defender para Office 365, también puede administrar remitentes que suplanta su dominio a través de [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="829f5-141">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="829f5-142">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="829f5-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="829f5-143">En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir La directiva de inteligencia de ![ ](../../media/scc-expand-icon.png) **suplantación.**</span><span class="sxs-lookup"><span data-stu-id="829f5-143">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Seleccionar la directiva de inteligencia suplantación](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="829f5-145">Realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="829f5-145">Make one of the following selections:</span></span>

   - <span data-ttu-id="829f5-146">**Revisar nuevos remitentes**</span><span class="sxs-lookup"><span data-stu-id="829f5-146">**Review new senders**</span></span>
   - <span data-ttu-id="829f5-147">**Mostrarme remitentes que ya revisé**</span><span class="sxs-lookup"><span data-stu-id="829f5-147">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="829f5-148">En decidir si estos remitentes pueden **suplantar** el control de los usuarios que aparece, seleccione una de las siguientes pestañas:</span><span class="sxs-lookup"><span data-stu-id="829f5-148">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="829f5-149">**Dominios:** remitentes que suplanta a los usuarios de los dominios internos.</span><span class="sxs-lookup"><span data-stu-id="829f5-149">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="829f5-150">**Dominios externos:** remitentes que suplanta a los usuarios en dominios externos.</span><span class="sxs-lookup"><span data-stu-id="829f5-150">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="829f5-151">Haga clic en Expandir icono en la columna ![ ](../../media/scc-expand-icon.png) **¿Permitido suplantación de identidad?**</span><span class="sxs-lookup"><span data-stu-id="829f5-151">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="829f5-152">Elija **Sí** para permitir al remitente suplantado o **elija No** para marcar el mensaje como suplantado.</span><span class="sxs-lookup"><span data-stu-id="829f5-152">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="829f5-153">La acción está controlada por la directiva anti phishing predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**).</span><span class="sxs-lookup"><span data-stu-id="829f5-153">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="829f5-154">Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="829f5-154">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Captura de pantalla que muestra el flyout de remitentes suplantados y si el remitente puede suplantar](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="829f5-156">Las columnas y valores que se muestran se explican en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="829f5-156">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="829f5-157">**Usuario suplantado:** la cuenta de usuario que se está suplantado.</span><span class="sxs-lookup"><span data-stu-id="829f5-157">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="829f5-158">Este es el remitente del mensaje en la dirección De (también conocida como la dirección) que `5322.From` se muestra en los clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="829f5-158">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="829f5-159">SPF no comprueba la validez de esta dirección.</span><span class="sxs-lookup"><span data-stu-id="829f5-159">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="829f5-160">En la **pestaña Dominios,** el valor contiene una sola dirección de correo electrónico, o si el servidor de correo electrónico de origen está suplantando varias cuentas de usuario, contiene **más de una**.</span><span class="sxs-lookup"><span data-stu-id="829f5-160">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="829f5-161">En la **pestaña Dominios externos,** el valor contiene el dominio del usuario suplantado, no la dirección de correo electrónico completa.</span><span class="sxs-lookup"><span data-stu-id="829f5-161">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="829f5-162">**Infraestructura de** envío: dominio encontrado en una búsqueda DNS inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen.</span><span class="sxs-lookup"><span data-stu-id="829f5-162">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="829f5-163">Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="829f5-163">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="829f5-164">Para obtener más información acerca de los orígenes de mensajes y los remitentes de mensajes, vea [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="829f5-164">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="829f5-165">**# de mensajes:** número de mensajes de la infraestructura de envío a la organización que contienen el remitente o remitentes suplantados especificados en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="829f5-165">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="829f5-166">**# de quejas de usuario:** quejas que los usuarios han presentado contra este remitente en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="829f5-166">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="829f5-167">Las quejas suelen estar en forma de envíos de correo no deseado a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="829f5-167">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="829f5-168">**Resultado de autenticación:** uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="829f5-168">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="829f5-169">**Pasado:** el remitente pasó las comprobaciones de autenticación de correo electrónico del remitente (SPF o DKIM).</span><span class="sxs-lookup"><span data-stu-id="829f5-169">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="829f5-170">**Error:** el remitente ha fallado las comprobaciones de autenticación del remitente EOP.</span><span class="sxs-lookup"><span data-stu-id="829f5-170">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="829f5-171">**Desconocido:** el resultado de estas comprobaciones no se conoce.</span><span class="sxs-lookup"><span data-stu-id="829f5-171">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="829f5-172">**Decisión establecida por:** muestra quién determinó si la infraestructura de envío puede suplantación de suplantación al usuario:</span><span class="sxs-lookup"><span data-stu-id="829f5-172">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="829f5-173">**Directiva de inteligencia suplantación** (automática)</span><span class="sxs-lookup"><span data-stu-id="829f5-173">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="829f5-174">**Administrador** (manual)</span><span class="sxs-lookup"><span data-stu-id="829f5-174">**Admin** (manual)</span></span>

   - <span data-ttu-id="829f5-175">**Última vista:** la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene el usuario suplantado.</span><span class="sxs-lookup"><span data-stu-id="829f5-175">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="829f5-176">**¿Se permite suplantación?**: Los valores que se ven aquí son:</span><span class="sxs-lookup"><span data-stu-id="829f5-176">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="829f5-177">**Sí:** los mensajes de la combinación de usuario suplantado y la infraestructura de envío se permiten y no se tratan como correo electrónico suplantado.</span><span class="sxs-lookup"><span data-stu-id="829f5-177">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="829f5-178">**No:** los mensajes de la combinación de usuario suplantado y la infraestructura de envío se marcan como suplantados.</span><span class="sxs-lookup"><span data-stu-id="829f5-178">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="829f5-179">La acción está controlada por la directiva anti phishing predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**).</span><span class="sxs-lookup"><span data-stu-id="829f5-179">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="829f5-180">Vea la siguiente sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="829f5-180">See the next section for more information.</span></span>

     - <span data-ttu-id="829f5-181">**Algunos usuarios** **(solo pestaña** Dominios): una infraestructura de envío está suplantando a varios usuarios, donde algunos usuarios suplantados están permitidos y otros no.</span><span class="sxs-lookup"><span data-stu-id="829f5-181">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="829f5-182">Use la **pestaña Detallado** para ver las direcciones específicas.</span><span class="sxs-lookup"><span data-stu-id="829f5-182">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="829f5-183">En la parte inferior de la página, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="829f5-183">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="829f5-184">Usar PowerShell para administrar remitentes suplantados</span><span class="sxs-lookup"><span data-stu-id="829f5-184">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="829f5-185">Para ver remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="829f5-185">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="829f5-186">En este ejemplo se devuelve información detallada sobre todos los remitentes que tienen permiso para suplantación de identidad de usuarios en los dominios.</span><span class="sxs-lookup"><span data-stu-id="829f5-186">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="829f5-187">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="829f5-187">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="829f5-188">Para configurar remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="829f5-188">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="829f5-189">Capture la lista actual de remitentes suplantados detectados escribiendo el resultado del cmdlet **Get-PhishFilterPolicy** en un archivo CSV:</span><span class="sxs-lookup"><span data-stu-id="829f5-189">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="829f5-190">Edite el archivo CSV para agregar o modificar los valores **SpoofedUser** (dirección de correo electrónico) y **AllowedToSpoof** (Sí o No).</span><span class="sxs-lookup"><span data-stu-id="829f5-190">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="829f5-191">Guarde el archivo, lea el archivo y almacene el contenido como una variable denominada `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="829f5-191">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="829f5-192">Use la `$UpdateSpoofedSenders` variable para configurar la directiva de inteligencia suplantación:</span><span class="sxs-lookup"><span data-stu-id="829f5-192">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="829f5-193">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="829f5-193">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="829f5-194">Usar el Centro de seguridad & cumplimiento para configurar la inteligencia de suplantación de seguridad</span><span class="sxs-lookup"><span data-stu-id="829f5-194">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="829f5-195">Las opciones de configuración para la inteligencia de suplantación se describen en Configuración de suplantación [de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="829f5-195">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="829f5-196">Puede configurar la configuración de suplantación de identidad en la directiva contra suplantación de identidad predeterminada y también en las directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="829f5-196">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="829f5-197">Para obtener instrucciones basadas en su suscripción, consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="829f5-197">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="829f5-198">[Configurar directivas contra suplantación de](configure-anti-phishing-policies-eop.md)identidad en EOP .</span><span class="sxs-lookup"><span data-stu-id="829f5-198">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="829f5-199">[Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="829f5-199">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="829f5-200">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="829f5-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="829f5-201">Para comprobar que ha configurado la inteligencia suplantación de identidad con remitentes a los que se les permite y no se les permite suplantación de identidad y que ha configurado la configuración de inteligencia de suplantación de identidad, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="829f5-201">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="829f5-202">En el Centro de seguridad y  cumplimiento de &, vaya a Directiva de administración de amenazas \>  \> **Antispam** \>  \>  \>    expanda Directiva de inteligencia de suplantación de identidad seleccione Mostrarme remitentes que ya revisé seleccione la pestaña Dominios o Dominios externos y compruebe el valor ¿Permitido suplantar? para el remitente.</span><span class="sxs-lookup"><span data-stu-id="829f5-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="829f5-203">En PowerShell, ejecute los siguientes comandos para ver los remitentes a los que se les permite suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="829f5-203">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="829f5-204">En PowerShell, ejecute el siguiente comando para exportar la lista de todos los remitentes suplantados a un archivo CSV:</span><span class="sxs-lookup"><span data-stu-id="829f5-204">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="829f5-205">En el Centro de seguridad &  cumplimiento, vaya a Directiva de administración de amenazas Contra suplantación de \>  \> **identidad (phishing)** o atp contra suplantación de identidad **(ATP)** y siga uno de los pasos siguientes:  </span><span class="sxs-lookup"><span data-stu-id="829f5-205">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="829f5-206">Seleccione una directiva de la lista.</span><span class="sxs-lookup"><span data-stu-id="829f5-206">Select a policy from the list.</span></span> <span data-ttu-id="829f5-207">En el menú desplegable que aparece, compruebe los valores de la **sección Suplantación.**</span><span class="sxs-lookup"><span data-stu-id="829f5-207">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="829f5-208">Haga clic **en Directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="829f5-208">Click **Default policy**.</span></span> <span data-ttu-id="829f5-209">En el menú desplegable que aparece, compruebe los valores de la **sección Suplantación.**</span><span class="sxs-lookup"><span data-stu-id="829f5-209">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="829f5-210">En Exchange Online PowerShell, reemplace por \<Name\> Office365 AntiPhish Default o el nombre de una directiva personalizada y ejecute el siguiente comando para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="829f5-210">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="829f5-211">Otras formas de administrar la suplantación de identidad y la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="829f5-211">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="829f5-212">Sea diligente con la suplantación de identidad y la protección contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="829f5-212">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="829f5-213">Estas son formas relacionadas de comprobar si los remitentes suplantan su dominio y ayudar a evitar que dañen la organización:</span><span class="sxs-lookup"><span data-stu-id="829f5-213">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="829f5-214">Compruebe el **informe de suplantación de correo**.</span><span class="sxs-lookup"><span data-stu-id="829f5-214">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="829f5-215">Puede usar este informe con frecuencia para ver y ayudar a administrar remitentes suplantados.</span><span class="sxs-lookup"><span data-stu-id="829f5-215">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="829f5-216">Para obtener información, vea [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span><span class="sxs-lookup"><span data-stu-id="829f5-216">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="829f5-217">Revise la configuración del Marco de directivas de remitente (SPF).</span><span class="sxs-lookup"><span data-stu-id="829f5-217">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="829f5-218">Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [Configuración de SPF en Microsoft 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="829f5-218">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="829f5-219">Para comprender en detalle cómo Office 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="829f5-219">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="829f5-220">Revise la configuración de Correo identificado de DomainKeys (DKIM).</span><span class="sxs-lookup"><span data-stu-id="829f5-220">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="829f5-221">Debes usar DKIM además de SPF y DMARC para ayudar a evitar que los atacantes envíen mensajes que parezcan procedentes de tu dominio.</span><span class="sxs-lookup"><span data-stu-id="829f5-221">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="829f5-222">DKIM le permite agregar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="829f5-222">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="829f5-223">Para obtener información, vea [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="829f5-223">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="829f5-224">Revise la configuración de autenticación, informes y conformidad de mensajes basada en dominio (DMARC).</span><span class="sxs-lookup"><span data-stu-id="829f5-224">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="829f5-225">Implementar DMARC con SPF y DKIM ofrece protección adicional contra el correo electrónico de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="829f5-225">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="829f5-226">DMARC permite a los sistemas que reciben los correos determinar qué hacer con los mensajes enviados desde su dominio que no superan las comprobaciones SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="829f5-226">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="829f5-227">Para obtener información, vea [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="829f5-227">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
