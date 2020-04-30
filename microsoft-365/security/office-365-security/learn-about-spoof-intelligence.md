---
title: Configurar la inteligencia de suplantación
f1.keywords:
- NOCSH
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
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo configurar los remitentes suplantados para permitir o no permitir y otras opciones de configuración de inteligencia de falsificaciones en Exchange Online y Exchange Online Protection (EOP).
ms.openlocfilehash: e2aeefbd90a7ed66699778fab54a76a33293e4bb
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949242"
---
# <a name="configure-spoof-intelligence-in-microsoft-365"></a><span data-ttu-id="f1a98-103">Configurar inteligencia de suplantación de identidad en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1a98-103">Configure spoof intelligence in Microsoft 365</span></span>

<span data-ttu-id="f1a98-104">Si es un cliente de Microsoft 365 con buzones en Exchange online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes de correo electrónico entrantes se protegen automáticamente contra la suplantación de identidad mediante EOP a partir del 2018 de octubre.</span><span class="sxs-lookup"><span data-stu-id="f1a98-104">If you're an Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="f1a98-105">EOP usa inteligencia simulada como parte de la defensa general de la organización contra el phishing.</span><span class="sxs-lookup"><span data-stu-id="f1a98-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="f1a98-106">Para obtener más información, vea [protección contra la suplantación de identidad en Microsoft 365](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="f1a98-106">For more information, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="f1a98-107">Cuando un remitente suplanta una dirección de correo electrónico, parece ser un usuario en uno de los dominios de la organización o un usuario de un dominio externo que envía correo electrónico a su organización.</span><span class="sxs-lookup"><span data-stu-id="f1a98-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="f1a98-108">Es necesario bloquear a los intrusos que suplantan a los remitentes para enviar correo no deseado o de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="f1a98-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="f1a98-109">Pero hay escenarios en los que los remitentes legítimos son imitación.</span><span class="sxs-lookup"><span data-stu-id="f1a98-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="f1a98-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f1a98-110">For example:</span></span>

- <span data-ttu-id="f1a98-111">Escenarios legítimos para la suplantación de dominios internos:</span><span class="sxs-lookup"><span data-stu-id="f1a98-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="f1a98-112">Los remitentes de terceros usan el dominio para enviar correo masivo a sus propios empleados para los sondeos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="f1a98-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>

  - <span data-ttu-id="f1a98-113">Una compañía externa genera y envía actualizaciones de productos o publicidad en su nombre.</span><span class="sxs-lookup"><span data-stu-id="f1a98-113">An external company generates and sends advertising or product updates on your behalf.</span></span>

  - <span data-ttu-id="f1a98-114">Un asistente necesita regularmente enviar correo electrónico a otra persona de la organización.</span><span class="sxs-lookup"><span data-stu-id="f1a98-114">An assistant regularly needs to send email for another person within your organization.</span></span>

  - <span data-ttu-id="f1a98-115">Una aplicación interna envía notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f1a98-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="f1a98-116">Escenarios legítimos para imitar dominios externos:</span><span class="sxs-lookup"><span data-stu-id="f1a98-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="f1a98-117">El remitente está en una lista de correo (también denominada lista de discusión) y la lista de distribución retransmite el correo electrónico del remitente original a todos los participantes de la lista de distribución de correo.</span><span class="sxs-lookup"><span data-stu-id="f1a98-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>

  - <span data-ttu-id="f1a98-118">Una compañía externa envía un correo electrónico en nombre de otra empresa (por ejemplo, un informe automatizado o una compañía de software como servicio).</span><span class="sxs-lookup"><span data-stu-id="f1a98-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="f1a98-119">Inteligencia de identidad suplantada, y concretamente la Directiva de inteligencia de identidad falsa predeterminada (y únicamente), ayuda a garantizar que el correo electrónico falso enviado por remitentes legítimos no se quede atrapado en los filtros de correo no deseado en Microsoft 365 o en sistemas de correo electrónico externos, a la vez que protege a los usuarios de los ataques de phishing</span><span class="sxs-lookup"><span data-stu-id="f1a98-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in spam filters in Microsoft 365 or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="f1a98-120">Puede administrar la inteligencia de identidad en el centro de cumplimiento de & de seguridad de Microsoft 365 o en PowerShell (Exchange Online PowerShell para los clientes de Microsoft 365; Exchange Online Protection PowerShell para clientes independientes de EOP).</span><span class="sxs-lookup"><span data-stu-id="f1a98-120">You can manage spoof intelligence in the Microsoft 365 Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f1a98-121">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="f1a98-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f1a98-122">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f1a98-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f1a98-123">Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="f1a98-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="f1a98-124">Para ir directamente a la página de **contra la suplantación de identidad (phishing** ), use. <https://protection.office.com/antiphishing></span><span class="sxs-lookup"><span data-stu-id="f1a98-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="f1a98-125">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f1a98-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f1a98-126">Para conectarse a Exchange Online Protection PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f1a98-126">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f1a98-127">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="f1a98-127">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="f1a98-128">Para modificar la Directiva de inteligencia de suplantación o habilitar o deshabilitar la inteligencia de identidad, debe ser miembro de los grupos de funciones administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="f1a98-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f1a98-129">Para obtener acceso de solo lectura a la Directiva de inteligencia empresarial, debe ser miembro del grupo de roles **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="f1a98-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="f1a98-130">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f1a98-130">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f1a98-131">Para conocer la configuración recomendada para inteligencia de falsificación, [configuración predeterminada de la Directiva de EOP contra el phishing](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="f1a98-131">For our recommended settings for spoof intelligence, [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="f1a98-132">Usar el centro de seguridad & cumplimiento para administrar los remitentes suplantados</span><span class="sxs-lookup"><span data-stu-id="f1a98-132">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="f1a98-133">Si tiene una suscripción de Office 365 Enterprise E5 o ha comprado por separado y un complemento de protección contra amenazas avanzada (ATP), también puede administrar a los remitentes que están suplantando su dominio mediante el [conocimiento de inteligencia](walkthrough-spoof-intelligence-insight.md)de ti falso.</span><span class="sxs-lookup"><span data-stu-id="f1a98-133">If you have an Office 365 Enterprise E5 subscription or have separately purchased and Advanced Threat Protection (ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="f1a98-134">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="f1a98-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f1a98-135">En la página **configuración contra correo no deseado** , ![haga clic](../../media/scc-expand-icon.png) en expandir icono para expandir la **Directiva de inteligencia empresarial de suplantación**.</span><span class="sxs-lookup"><span data-stu-id="f1a98-135">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Seleccionar la Directiva de inteligencia de suplantación](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="f1a98-137">Realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="f1a98-137">Make one of the following selections:</span></span>

   - <span data-ttu-id="f1a98-138">**Revisión de los nuevos remitentes**</span><span class="sxs-lookup"><span data-stu-id="f1a98-138">**Review new senders**</span></span>
   - <span data-ttu-id="f1a98-139">**Mostrar los remitentes que ya he revisado**</span><span class="sxs-lookup"><span data-stu-id="f1a98-139">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="f1a98-140">En el control flotante **decidir si estos remitentes pueden suplantar a los usuarios** que aparecen, seleccione una de las siguientes pestañas:</span><span class="sxs-lookup"><span data-stu-id="f1a98-140">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="f1a98-141">**Sus dominios**: los remitentes suplantan a los usuarios de los dominios internos.</span><span class="sxs-lookup"><span data-stu-id="f1a98-141">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="f1a98-142">**Dominios externos**: remitentes de suplantación de usuarios en dominios externos.</span><span class="sxs-lookup"><span data-stu-id="f1a98-142">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="f1a98-143">Haga ![clic en](../../media/scc-expand-icon.png) expandir icono en la columna **¿se permite la suplantación?** .</span><span class="sxs-lookup"><span data-stu-id="f1a98-143">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="f1a98-144">Elija **sí** para permitir el remitente suplantado o elija **no** para marcar el mensaje como falsificado.</span><span class="sxs-lookup"><span data-stu-id="f1a98-144">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="f1a98-145">La acción se controla mediante la Directiva antiphishing predeterminada o las directivas antiphishing personalizadas de ATP (el valor predeterminado es **mover mensaje a la carpeta de correo no deseado**).</span><span class="sxs-lookup"><span data-stu-id="f1a98-145">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="f1a98-146">Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f1a98-146">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Captura de pantalla que muestra el control flotante de remitentes suplantados y si se permite que el remitente suplante](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="f1a98-148">En la lista siguiente se explican las columnas y los valores que se ven:</span><span class="sxs-lookup"><span data-stu-id="f1a98-148">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="f1a98-149">**Usuario suplantado**: la cuenta de usuario que se va a imitar.</span><span class="sxs-lookup"><span data-stu-id="f1a98-149">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="f1a98-150">Este es el remitente del mensaje en la dirección de (también denominada `5322.From` dirección) que se muestra en los clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f1a98-150">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="f1a98-151">SPF no comprueba la validez de esta dirección.</span><span class="sxs-lookup"><span data-stu-id="f1a98-151">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="f1a98-152">En la ficha **sus dominios** , el valor contiene una sola dirección de correo electrónico o, si el servidor de correo electrónico de origen imita varias cuentas de usuario, contiene **más de una**.</span><span class="sxs-lookup"><span data-stu-id="f1a98-152">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="f1a98-153">En la ficha **dominios externos** , el valor contiene el dominio del usuario falso, no la dirección de correo electrónico completa.</span><span class="sxs-lookup"><span data-stu-id="f1a98-153">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="f1a98-154">**Infraestructura de envío**: el dominio que se encuentra en una búsqueda DNS inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen o en la dirección IP si el origen no tiene registro PTR.</span><span class="sxs-lookup"><span data-stu-id="f1a98-154">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="f1a98-155">Para obtener más información acerca de los orígenes de mensajes y los remitentes de mensajes, vea [información general sobre los estándares de mensajes de correo electrónico](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="f1a98-155">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="f1a98-156">**n.º de mensajes**: el número de mensajes de la infraestructura de envío a su organización que contienen los remitentes suplantados que se han especificado en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="f1a98-156">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="f1a98-157">**número de quejas del usuario**: quejas archivadas por los usuarios con este remitente en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="f1a98-157">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="f1a98-158">Las quejas suelen estar en forma de envíos de correo no deseado a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1a98-158">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="f1a98-159">**Resultado de autenticación**: uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f1a98-159">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="f1a98-160">**Passed**: el remitente ha superado las comprobaciones de autenticación de correo electrónico del remitente (SPF o DKIM).</span><span class="sxs-lookup"><span data-stu-id="f1a98-160">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="f1a98-161">**Error**: el remitente no pudo realizar comprobaciones de autenticación de remitente de EOP.</span><span class="sxs-lookup"><span data-stu-id="f1a98-161">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="f1a98-162">**Desconocido**: no se conoce el resultado de estas comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="f1a98-162">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="f1a98-163">**Decisión definida por**: muestra quién ha determinado si la infraestructura de envío tiene permiso para suplantar al usuario:</span><span class="sxs-lookup"><span data-stu-id="f1a98-163">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="f1a98-164">**Directiva de inteligencia de identidad** (automática)</span><span class="sxs-lookup"><span data-stu-id="f1a98-164">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="f1a98-165">**Administrador** (manual)</span><span class="sxs-lookup"><span data-stu-id="f1a98-165">**Admin** (manual)</span></span>

   - <span data-ttu-id="f1a98-166">**Último visto**: la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene al usuario suplantado.</span><span class="sxs-lookup"><span data-stu-id="f1a98-166">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="f1a98-167">¿Se **permite la suplantación?**: los valores que aparecen aquí son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1a98-167">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="f1a98-168">**Sí**: los mensajes de la combinación de usuario falsificado y la infraestructura de envío están permitidos y no se tratan como correo electrónico falsificado.</span><span class="sxs-lookup"><span data-stu-id="f1a98-168">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="f1a98-169">**No**: los mensajes de la combinación de usuario falsificado y infraestructura de envío se marcan como falseados.</span><span class="sxs-lookup"><span data-stu-id="f1a98-169">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="f1a98-170">La acción se controla mediante la Directiva antiphishing predeterminada o las directivas antiphishing personalizadas de ATP (el valor predeterminado es **mover mensaje a la carpeta de correo no deseado**).</span><span class="sxs-lookup"><span data-stu-id="f1a98-170">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="f1a98-171">Vea la sección siguiente para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1a98-171">See the next section for more information.</span></span>

     - <span data-ttu-id="f1a98-172">**Algunos usuarios** (**la ficha dominios** solamente): una infraestructura de envío imita a varios usuarios, donde se permiten algunos usuarios suplantados y otros no.</span><span class="sxs-lookup"><span data-stu-id="f1a98-172">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="f1a98-173">Use la pestaña **detalles** para ver las direcciones específicas.</span><span class="sxs-lookup"><span data-stu-id="f1a98-173">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="f1a98-174">En la parte inferior de la página, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f1a98-174">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="f1a98-175">Usar PowerShell para administrar los remitentes suplantados</span><span class="sxs-lookup"><span data-stu-id="f1a98-175">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="f1a98-176">Para ver los remitentes permitidos y bloqueados en inteligencia de suplantación de identidad, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f1a98-176">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="f1a98-177">En este ejemplo se devuelve información detallada sobre todos los remitentes a los que se les permite suplantar usuarios en los dominios.</span><span class="sxs-lookup"><span data-stu-id="f1a98-177">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilter -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="f1a98-178">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f1a98-178">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).</span></span>

<span data-ttu-id="f1a98-179">Para configurar los remitentes permitidos y bloqueados en inteligencia de identidad, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f1a98-179">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="f1a98-180">Para capturar la lista actual de los remitentes suplantados detectados, escriba el resultado del cmdlet **Get-PhishFilterPolicy** en un archivo CSV:</span><span class="sxs-lookup"><span data-stu-id="f1a98-180">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="f1a98-181">Edite el archivo CSV para agregar o modificar los valores de **SpoofedUser** (dirección de correo electrónico) y **AllowedToSpoof** (sí o no).</span><span class="sxs-lookup"><span data-stu-id="f1a98-181">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="f1a98-182">Guarde el archivo, lea el archivo y almacene el contenido como una variable llamada `$UpdateSpoofedSenders`:</span><span class="sxs-lookup"><span data-stu-id="f1a98-182">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="f1a98-183">Use la `$UpdateSpoofedSenders` variable para configurar la Directiva de inteligencia de suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="f1a98-183">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="f1a98-184">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f1a98-184">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="f1a98-185">Usar el centro de seguridad & cumplimiento para configurar la inteligencia de identidad</span><span class="sxs-lookup"><span data-stu-id="f1a98-185">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="f1a98-186">Las opciones de configuración para inteligencia de suplantación se describen en configuración de suplantación [de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f1a98-186">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="f1a98-187">Puede configurar las opciones de inteligencia contra la suplantación de identidad en la Directiva de antiphishing predeterminada y también en las directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f1a98-187">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="f1a98-188">Para obtener instrucciones basadas en su suscripción, consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="f1a98-188">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="f1a98-189">[Configure las directivas contra la suplantación de identidad en EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f1a98-189">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="f1a98-190">[Configure las directivas antiphishing de ATP en Microsoft 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f1a98-190">[Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f1a98-191">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="f1a98-191">How do you know these procedures worked?</span></span>

<span data-ttu-id="f1a98-192">Para comprobar que ha configurado inteligencia de suplantación con remitentes a los que se permite y no se permite la suplantación, y que ha configurado la configuración de inteligencia de suplantación de identidad, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f1a98-192">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="f1a98-193">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-spam** \> expanda \> la **Directiva inteligencia empresarial** seleccionar **Mostrar los remitentes que ya he revisado** \> seleccione la pestaña **dominios** o dominios **externos** y compruebe el valor **se permite la suplantación de identidad** para el remitente.</span><span class="sxs-lookup"><span data-stu-id="f1a98-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="f1a98-194">En PowerShell, ejecute los siguientes comandos para ver los remitentes a los que se les permite la suplantación:</span><span class="sxs-lookup"><span data-stu-id="f1a98-194">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilter -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="f1a98-195">En PowerShell, ejecute el siguiente comando para exportar la lista de todos los remitentes suplantados a un archivo CSV:</span><span class="sxs-lookup"><span data-stu-id="f1a98-195">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="f1a98-196">En Microsoft 365 organizaciones con buzones de correo de Exchange Online, realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1a98-196">In Microsoft 365 organizations with Exchange Online mailboxes, do either of the following steps:</span></span>

  - <span data-ttu-id="f1a98-197">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing** \> haga clic en **directiva predeterminada** y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="f1a98-197">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

  - <span data-ttu-id="f1a98-198">En Exchange Online PowerShell, ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="f1a98-198">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
    ```

- <span data-ttu-id="f1a98-199">En las organizaciones de Microsoft 365 ATP, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f1a98-199">In Microsoft 365 ATP organizations, do either of the following steps:</span></span>

  - <span data-ttu-id="f1a98-200">En el centro de seguridad & cumplimiento, vaya a **Directiva** \> de **Administración** \> de amenazas **ATP anti-phishing** y siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f1a98-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** and do either of the following steps:</span></span>

    - <span data-ttu-id="f1a98-201">Seleccione una directiva de la lista.</span><span class="sxs-lookup"><span data-stu-id="f1a98-201">Select a policy from the list.</span></span> <span data-ttu-id="f1a98-202">En el control flotante que aparece, compruebe los valores de la sección **suplantación de identidad** .</span><span class="sxs-lookup"><span data-stu-id="f1a98-202">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
    - <span data-ttu-id="f1a98-203">Haga clic en **directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="f1a98-203">Click **Default policy**.</span></span> <span data-ttu-id="f1a98-204">En el control flotante que aparece, compruebe los valores de la sección **suplantación de identidad** .</span><span class="sxs-lookup"><span data-stu-id="f1a98-204">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

  - <span data-ttu-id="f1a98-205">En Exchange Online PowerShell, reemplace \<name\> con el valor predeterminado de Office365 ANTIPHISH o el nombre de una directiva de antiphishing de ATP personalizada, y ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="f1a98-205">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom ATP anti-phishing policy, and run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "<Name>"
    ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="f1a98-206">Otras formas de administrar la suplantación de identidad (phishing)</span><span class="sxs-lookup"><span data-stu-id="f1a98-206">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="f1a98-207">Sea Diligent sobre la suplantación de identidad y la protección contra phishing.</span><span class="sxs-lookup"><span data-stu-id="f1a98-207">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="f1a98-208">A continuación, se incluyen formas relacionadas de comprobar si los remitentes suplantan el dominio y ayudar a evitar que dañen la organización:</span><span class="sxs-lookup"><span data-stu-id="f1a98-208">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="f1a98-209">Compruebe el **Informe de correo falsificado**.</span><span class="sxs-lookup"><span data-stu-id="f1a98-209">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="f1a98-210">Puede usar este informe con frecuencia para ver y ayudar a administrar los remitentes suplantados.</span><span class="sxs-lookup"><span data-stu-id="f1a98-210">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="f1a98-211">Para obtener información, consulte [Informe de detecciones de suplantación de identidad](view-email-security-reports.md#spoof-detections-report).</span><span class="sxs-lookup"><span data-stu-id="f1a98-211">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="f1a98-212">Revise la configuración del marco de directivas de remitente (SPF).</span><span class="sxs-lookup"><span data-stu-id="f1a98-212">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="f1a98-213">Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [Configuración de SPF en Microsoft 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="f1a98-213">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="f1a98-214">Para comprender en detalle cómo Office 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="f1a98-214">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="f1a98-215">Revise la configuración de DomainKeys Identified Mail (DKIM).</span><span class="sxs-lookup"><span data-stu-id="f1a98-215">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="f1a98-216">Debe usar DKIM además de SPF y DMARC para ayudar a evitar que los atacantes envíen mensajes que parecen provenir de su dominio.</span><span class="sxs-lookup"><span data-stu-id="f1a98-216">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="f1a98-217">DKIM le permite agregar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f1a98-217">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="f1a98-218">Para obtener más información, vea [usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="f1a98-218">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="f1a98-219">Revise la configuración de autenticación de mensajes basada en el dominio, informes y conformidad (DMARC).</span><span class="sxs-lookup"><span data-stu-id="f1a98-219">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="f1a98-220">Implementar DMARC con SPF y DKIM ofrece protección adicional contra el correo electrónico de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="f1a98-220">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="f1a98-221">DMARC permite a los sistemas que reciben los correos determinar qué hacer con los mensajes enviados desde su dominio que no superan las comprobaciones SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="f1a98-221">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="f1a98-222">Para obtener más información, vea [usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="f1a98-222">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>