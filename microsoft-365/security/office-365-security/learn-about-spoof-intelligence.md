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
description: Los administradores pueden obtener información sobre la inteligencia de suplantación de identidad en Exchange Online Protection (EOP), donde puede permitir o bloquear remitentes suplantados específicos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55a744cf2d226e72e8d84f6eb125f2baf9b9d3a0
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167268"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="36ae4-103">Configurar la inteligencia de suplantación de seguridad en EOP</span><span class="sxs-lookup"><span data-stu-id="36ae4-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="36ae4-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="36ae4-104">**Applies to**</span></span>
- [<span data-ttu-id="36ae4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="36ae4-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="36ae4-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="36ae4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="36ae4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36ae4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="36ae4-108">En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones de Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, los mensajes de correo electrónico entrantes se protegen automáticamente contra la suplantación por parte de EOP a partir de octubre de 2018.</span><span class="sxs-lookup"><span data-stu-id="36ae4-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="36ae4-109">EOP usa la inteligencia de suplantación de identidad como parte de la defensa general de su organización contra la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="36ae4-109">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="36ae4-110">Para obtener más información, vea [Protección contra la suplantación en EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="36ae4-110">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="36ae4-111">Cuando un remitente suplanta una dirección de correo electrónico, parece que es un usuario de uno de los dominios de su organización o un usuario de un dominio externo que envía correo electrónico a su organización.</span><span class="sxs-lookup"><span data-stu-id="36ae4-111">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="36ae4-112">Los atacantes que suplanten a los remitentes para enviar correo no deseado o correo de suplantación de identidad deben bloquearse.</span><span class="sxs-lookup"><span data-stu-id="36ae4-112">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="36ae4-113">Sin embargo, existen escenarios en los que los remitentes legítimos están suplantando la identidad.</span><span class="sxs-lookup"><span data-stu-id="36ae4-113">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="36ae4-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="36ae4-114">For example:</span></span>

- <span data-ttu-id="36ae4-115">Escenarios legítimos para suplantar dominios internos:</span><span class="sxs-lookup"><span data-stu-id="36ae4-115">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="36ae4-116">Los remitentes de terceros usan su dominio para enviar correo masivo a sus propios empleados para los sondeos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="36ae4-116">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="36ae4-117">Una empresa externa genera y envía actualizaciones de publicidad o productos en tu nombre.</span><span class="sxs-lookup"><span data-stu-id="36ae4-117">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="36ae4-118">Un asistente debe enviar periódicamente correo electrónico a otra persona de la organización.</span><span class="sxs-lookup"><span data-stu-id="36ae4-118">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="36ae4-119">Una aplicación interna envía notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="36ae4-119">An internal application sends email notifications.</span></span>

- <span data-ttu-id="36ae4-120">Escenarios legítimos para suplantar dominios externos:</span><span class="sxs-lookup"><span data-stu-id="36ae4-120">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="36ae4-121">El remitente se encuentra en una lista de distribución de correo (también conocida como lista de discusión) y la lista de distribución retransmite el correo electrónico del remitente original a todos los participantes de la lista de distribución de correo.</span><span class="sxs-lookup"><span data-stu-id="36ae4-121">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="36ae4-122">Una compañía externa envía correo electrónico en nombre de otra compañía (por ejemplo, un informe automatizado o una compañía de software como servicio).</span><span class="sxs-lookup"><span data-stu-id="36ae4-122">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="36ae4-123">La inteligencia de suplantación de identidad y, específicamente, la directiva de inteligencia de suplantación de identidad predeterminada (y única), ayuda a garantizar que el correo electrónico suplantado enviado por remitentes legítimos no se detecta en filtros de correo no deseado de EOP o sistemas de correo electrónico externos, a la vez que protege a los usuarios contra ataques de correo no deseado o de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="36ae4-123">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="36ae4-124">Puede administrar la inteligencia de suplantación en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="36ae4-124">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="36ae4-125">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="36ae4-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="36ae4-126">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="36ae4-126">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="36ae4-127">Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="36ae4-127">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="36ae4-128">Para ir directamente a la **página contra la suplantación** de identidad, use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="36ae4-128">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="36ae4-129">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="36ae4-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="36ae4-130">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="36ae4-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="36ae4-131">Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="36ae4-131">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="36ae4-132">Para modificar la directiva de inteligencia de suplantación o habilitar o deshabilitar  la inteligencia de suplantación de seguridad, debe ser miembro de los grupos de roles Administración de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="36ae4-132">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="36ae4-133">Para obtener acceso de solo lectura a la directiva de inteligencia de suplantación, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="36ae4-133">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="36ae4-134">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="36ae4-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="36ae4-135">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="36ae4-135">**Notes**:</span></span>

  - <span data-ttu-id="36ae4-136">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36ae4-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="36ae4-137">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="36ae4-137">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="36ae4-138">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="36ae4-138">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="36ae4-139">Para obtener la configuración recomendada para la inteligencia de suplantación de identidad, vea la configuración predeterminada de la directiva [contra suplantación de identidad de EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="36ae4-139">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="36ae4-140">Usar el Centro de & cumplimiento para administrar remitentes suplantados</span><span class="sxs-lookup"><span data-stu-id="36ae4-140">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="36ae4-141">Si tiene una suscripción a Microsoft 365 Enterprise E5 o ha adquirido por separado un complemento de Microsoft Defender para Office 365, también puede administrar los remitentes que están suplantando su dominio a través de la información de inteligencia de suplantación de [identidad.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="36ae4-141">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="36ae4-142">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="36ae4-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="36ae4-143">En la página **Configuración contra correo no** deseado, haga clic en el icono Expandir para expandir la directiva de inteligencia de ![ ](../../media/scc-expand-icon.png) **suplantación de seguridad.**</span><span class="sxs-lookup"><span data-stu-id="36ae4-143">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Seleccionar la directiva de inteligencia de suplantación de seguridad](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="36ae4-145">Realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="36ae4-145">Make one of the following selections:</span></span>

   - <span data-ttu-id="36ae4-146">**Revisar nuevos remitentes**</span><span class="sxs-lookup"><span data-stu-id="36ae4-146">**Review new senders**</span></span>
   - <span data-ttu-id="36ae4-147">**Mostrarme los remitentes que ya he revisado**</span><span class="sxs-lookup"><span data-stu-id="36ae4-147">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="36ae4-148">En el menú Decidir si estos remitentes pueden **suplantar** la identidad de los usuarios en el control desplegable que aparece, seleccione una de las siguientes pestañas:</span><span class="sxs-lookup"><span data-stu-id="36ae4-148">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="36ae4-149">**Dominios:** remitentes que suplanta a los usuarios en sus dominios internos.</span><span class="sxs-lookup"><span data-stu-id="36ae4-149">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="36ae4-150">**Dominios externos:** remitentes que suplanta a los usuarios en dominios externos.</span><span class="sxs-lookup"><span data-stu-id="36ae4-150">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="36ae4-151">Haga clic en el icono Expandir de la columna ¿Se ![ ](../../media/scc-expand-icon.png) permite **suplantación de identidad?**</span><span class="sxs-lookup"><span data-stu-id="36ae4-151">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="36ae4-152">Elija **Sí** para permitir al remitente suplantado o **elija No** para marcar el mensaje como suplantado.</span><span class="sxs-lookup"><span data-stu-id="36ae4-152">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="36ae4-153">La acción se controla mediante la directiva contra suplantación de identidad predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado).**</span><span class="sxs-lookup"><span data-stu-id="36ae4-153">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="36ae4-154">Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="36ae4-154">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Captura de pantalla que muestra el desplegable de remitentes suplantados y si el remitente puede suplantar la identidad](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="36ae4-156">Las columnas y los valores que ve se explican en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="36ae4-156">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="36ae4-157">**Usuario suplantado:** la cuenta de usuario suplantada.</span><span class="sxs-lookup"><span data-stu-id="36ae4-157">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="36ae4-158">Este es el remitente del mensaje en la dirección De (también conocida como dirección) que `5322.From` se muestra en los clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="36ae4-158">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="36ae4-159">SPF no comprueba la validez de esta dirección.</span><span class="sxs-lookup"><span data-stu-id="36ae4-159">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="36ae4-160">En la **pestaña Dominios,** el valor contiene una sola dirección de correo electrónico, o si el servidor de correo electrónico de origen está suplantando varias cuentas de usuario, contiene **más de una.**</span><span class="sxs-lookup"><span data-stu-id="36ae4-160">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="36ae4-161">En la **pestaña Dominios externos,** el valor contiene el dominio del usuario suplantado, no la dirección de correo electrónico completa.</span><span class="sxs-lookup"><span data-stu-id="36ae4-161">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="36ae4-162">**Infraestructura de** envío: dominio encontrado en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen.</span><span class="sxs-lookup"><span data-stu-id="36ae4-162">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="36ae4-163">Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="36ae4-163">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="36ae4-164">Para obtener más información acerca de los orígenes de mensajes y los remitentes de mensajes, consulte Información general sobre los estándares de [mensajes de correo electrónico.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="36ae4-164">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="36ae4-165">**# de mensajes:** el número de mensajes de la infraestructura de envío a la organización que contienen el remitente o remitentes suplantados especificados en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="36ae4-165">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="36ae4-166">**# de quejas de usuario:** quejas presentada por los usuarios contra este remitente en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="36ae4-166">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="36ae4-167">Las quejas suelen estar en forma de envíos de correo no deseado a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36ae4-167">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="36ae4-168">**Resultado de la** autenticación: uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="36ae4-168">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="36ae4-169">**Pasado:** el remitente superó las comprobaciones de autenticación de correo electrónico del remitente (SPF o DKIM).</span><span class="sxs-lookup"><span data-stu-id="36ae4-169">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="36ae4-170">**Error:** el remitente no pudo comprobar la autenticación del remitente de EOP.</span><span class="sxs-lookup"><span data-stu-id="36ae4-170">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="36ae4-171">**Desconocido:** no se conoce el resultado de estas comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="36ae4-171">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="36ae4-172">**Decisión establecida por:** muestra quién determinó si la infraestructura de envío tiene permiso para suplantación de nombre del usuario:</span><span class="sxs-lookup"><span data-stu-id="36ae4-172">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="36ae4-173">**Directiva de inteligencia de suplantación** de seguridad (automática)</span><span class="sxs-lookup"><span data-stu-id="36ae4-173">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="36ae4-174">**Administrador** (manual)</span><span class="sxs-lookup"><span data-stu-id="36ae4-174">**Admin** (manual)</span></span>

   - <span data-ttu-id="36ae4-175">**Última vez** que se vio: la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene el usuario suplantado.</span><span class="sxs-lookup"><span data-stu-id="36ae4-175">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="36ae4-176">**¿Se permite la suplantación?**: Los valores que ve aquí son:</span><span class="sxs-lookup"><span data-stu-id="36ae4-176">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="36ae4-177">**Sí:** los mensajes de la combinación de usuario suplantado y la infraestructura de envío se permiten y no se tratan como correo electrónico suplantado.</span><span class="sxs-lookup"><span data-stu-id="36ae4-177">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="36ae4-178">**No:** los mensajes de la combinación de usuario suplantado y la infraestructura de envío se marcan como suplantados.</span><span class="sxs-lookup"><span data-stu-id="36ae4-178">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="36ae4-179">La acción se controla mediante la directiva contra suplantación de identidad predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado).**</span><span class="sxs-lookup"><span data-stu-id="36ae4-179">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="36ae4-180">Vea la sección siguiente para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="36ae4-180">See the next section for more information.</span></span>

     - <span data-ttu-id="36ae4-181">**Algunos usuarios** **(solo la** pestaña Dominios): una infraestructura de envío está suplantando a varios usuarios, donde algunos usuarios suplantados están permitidos y otros no.</span><span class="sxs-lookup"><span data-stu-id="36ae4-181">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="36ae4-182">Use la **pestaña Detallado** para ver las direcciones específicas.</span><span class="sxs-lookup"><span data-stu-id="36ae4-182">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="36ae4-183">En la parte inferior de la página, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="36ae4-183">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="36ae4-184">Usar PowerShell para administrar remitentes suplantados</span><span class="sxs-lookup"><span data-stu-id="36ae4-184">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="36ae4-185">Para ver remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="36ae4-185">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="36ae4-186">En este ejemplo se devuelve información detallada sobre todos los remitentes que tienen permiso para suplantación de identidad de usuarios en sus dominios.</span><span class="sxs-lookup"><span data-stu-id="36ae4-186">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="36ae4-187">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="36ae4-187">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="36ae4-188">Para configurar remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="36ae4-188">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="36ae4-189">Capture la lista actual de remitentes suplantados detectados escribiendo el resultado del cmdlet **Get-PhishFilterPolicy** en un archivo CSV:</span><span class="sxs-lookup"><span data-stu-id="36ae4-189">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="36ae4-190">Edite el archivo CSV para agregar o modificar los valores **SpoofedUser** (dirección de correo electrónico) y **AllowedToSpoof** (Sí o No).</span><span class="sxs-lookup"><span data-stu-id="36ae4-190">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="36ae4-191">Guarde el archivo, lea el archivo y almacene el contenido como una variable denominada `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="36ae4-191">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="36ae4-192">Use la `$UpdateSpoofedSenders` variable para configurar la directiva de inteligencia de suplantación de nombres:</span><span class="sxs-lookup"><span data-stu-id="36ae4-192">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="36ae4-193">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="36ae4-193">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="36ae4-194">Usar el Centro de seguridad & cumplimiento para configurar la inteligencia de suplantación de seguridad</span><span class="sxs-lookup"><span data-stu-id="36ae4-194">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="36ae4-195">Las opciones de configuración para la inteligencia de suplantación de identidad se describen en la configuración de suplantación de identidad [en las directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="36ae4-195">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="36ae4-196">Puede configurar las opciones de inteligencia de suplantación de identidad en la directiva contra suplantación de identidad predeterminada y también en las directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="36ae4-196">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="36ae4-197">Para obtener instrucciones basadas en su suscripción, consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="36ae4-197">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="36ae4-198">[Configurar directivas contra la suplantación de identidad en EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="36ae4-198">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="36ae4-199">[Configurar directivas contra la suplantación de identidad en Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="36ae4-199">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="36ae4-200">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="36ae4-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="36ae4-201">Para comprobar que ha configurado la inteligencia de suplantación de identidad con remitentes que tienen permiso y no pueden suplantación de identidad y que ha configurado la configuración de inteligencia de suplantación de identidad, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="36ae4-201">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="36ae4-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** select Show me \> **senders I already reviewed** \> select the Your **Domains** or **External Domains** tab, and verify the Allowed **to spoof?** value for the sender.</span><span class="sxs-lookup"><span data-stu-id="36ae4-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="36ae4-203">En PowerShell, ejecute los siguientes comandos para ver los remitentes que tienen permiso y no pueden suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="36ae4-203">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="36ae4-204">En PowerShell, ejecute el siguiente comando para exportar la lista de todos los remitentes suplantados a un archivo CSV:</span><span class="sxs-lookup"><span data-stu-id="36ae4-204">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="36ae4-205">En el Centro de seguridad &  cumplimiento, vaya a Directiva de administración de amenazas contra suplantación de identidad o protección contra suplantación de identidad de ATP y siga uno de \>  \>  estos pasos:   </span><span class="sxs-lookup"><span data-stu-id="36ae4-205">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="36ae4-206">Seleccione una directiva de la lista.</span><span class="sxs-lookup"><span data-stu-id="36ae4-206">Select a policy from the list.</span></span> <span data-ttu-id="36ae4-207">En el menú desplegable que aparece, compruebe los valores de la **sección Suplantación de** identidad.</span><span class="sxs-lookup"><span data-stu-id="36ae4-207">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="36ae4-208">Haga clic **en Directiva predeterminada.**</span><span class="sxs-lookup"><span data-stu-id="36ae4-208">Click **Default policy**.</span></span> <span data-ttu-id="36ae4-209">En el menú desplegable que aparece, compruebe los valores de la **sección Suplantación de** identidad.</span><span class="sxs-lookup"><span data-stu-id="36ae4-209">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="36ae4-210">En Exchange Online PowerShell, reemplace por Office365 AntiPhish Default o el nombre de una directiva personalizada y ejecute el siguiente comando \<Name\> para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="36ae4-210">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="36ae4-211">Otras formas de administrar la suplantación de identidad y la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="36ae4-211">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="36ae4-212">Sé cuidadoso sobre la protección contra la suplantación de identidad y la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="36ae4-212">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="36ae4-213">Estas son las formas relacionadas de comprobar si los remitentes suplantan su dominio y ayudar a evitar que dañen la organización:</span><span class="sxs-lookup"><span data-stu-id="36ae4-213">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="36ae4-214">Compruebe el **informe de suplantación de correo.**</span><span class="sxs-lookup"><span data-stu-id="36ae4-214">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="36ae4-215">Puede usar este informe a menudo para ver y ayudar a administrar remitentes suplantados.</span><span class="sxs-lookup"><span data-stu-id="36ae4-215">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="36ae4-216">Para obtener información, vea [el informe de detecciones de suplantación de seguridad.](view-email-security-reports.md#spoof-detections-report)</span><span class="sxs-lookup"><span data-stu-id="36ae4-216">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="36ae4-217">Revise la configuración del marco de directivas de remitente (SPF).</span><span class="sxs-lookup"><span data-stu-id="36ae4-217">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="36ae4-218">Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [Configuración de SPF en Microsoft 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="36ae4-218">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="36ae4-219">Para comprender en detalle cómo Office 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="36ae4-219">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="36ae4-220">Revise la configuración de DomainKeys Identified Mail (DKIM).</span><span class="sxs-lookup"><span data-stu-id="36ae4-220">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="36ae4-221">Debe usar DKIM además de SPF y DMARC para ayudar a evitar que los atacantes envíen mensajes que parezcan procedentes de su dominio.</span><span class="sxs-lookup"><span data-stu-id="36ae4-221">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="36ae4-222">DKIM le permite agregar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="36ae4-222">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="36ae4-223">Para obtener información, vea Usar DKIM para validar el correo electrónico saliente [enviado desde su dominio personalizado en Office 365.](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="36ae4-223">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="36ae4-224">Revise la configuración de autenticación, informes y conformidad de mensajes (DMARC) basada en dominio.</span><span class="sxs-lookup"><span data-stu-id="36ae4-224">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="36ae4-225">Implementar DMARC con SPF y DKIM ofrece protección adicional contra el correo electrónico de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="36ae4-225">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="36ae4-226">DMARC permite a los sistemas que reciben los correos determinar qué hacer con los mensajes enviados desde su dominio que no superan las comprobaciones SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="36ae4-226">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="36ae4-227">Para obtener información, [vea Usar DMARC para validar el correo electrónico en Office 365.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="36ae4-227">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
