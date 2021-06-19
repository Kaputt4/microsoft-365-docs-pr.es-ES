---
title: Administrar remitentes suplantados mediante la directiva de inteligencia suplantada y la información de inteligencia suplantada
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar la directiva de inteligencia suplantada y la información de inteligencia suplantada para permitir o bloquear remitentes suplantados detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a683ed93e4e483e63fe01281b32661f0b803d1ce
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029302"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a><span data-ttu-id="4df1e-103">Administrar remitentes suplantados con la directiva de inteligencia suplantada y la información de inteligencia suplantada en EOP</span><span class="sxs-lookup"><span data-stu-id="4df1e-103">Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4df1e-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="4df1e-104">**Applies to**</span></span>
- [<span data-ttu-id="4df1e-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="4df1e-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4df1e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4df1e-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="4df1e-107">En este artículo se describe la experiencia de administración de remitentes suplantada anterior que se está reemplazando.</span><span class="sxs-lookup"><span data-stu-id="4df1e-107">This article describes the older spoofed sender management experience that's being replaced.</span></span> <span data-ttu-id="4df1e-108">Para obtener más información sobre la nueva experiencia, vea [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="4df1e-108">For more information about the new experience, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span></span>

<span data-ttu-id="4df1e-109">En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, los mensajes de correo electrónico entrantes se protegen automáticamente contra la suplantación de correo electrónico por parte de EOP a partir de octubre de 2018.</span><span class="sxs-lookup"><span data-stu-id="4df1e-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="4df1e-110">EOP usa **la inteligencia de** suplantación de identidad como parte de la defensa general de su organización contra el phishing.</span><span class="sxs-lookup"><span data-stu-id="4df1e-110">EOP uses **spoof intelligence** as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="4df1e-111">Para obtener más información, vea Protección contra [la suplantación en EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="4df1e-111">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="4df1e-112">La directiva de inteligencia de suplantación de identidad predeterminada (y **única)** ayuda a garantizar que el correo electrónico suplantado enviado por remitentes legítimos no se desentraña en los filtros de correo no deseado de EOP mientras protege a los usuarios de ataques de correo no deseado o suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="4df1e-112">The default (and only) **spoof intelligence policy** helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters while protecting your users from spam or phishing attacks.</span></span> <span data-ttu-id="4df1e-113">También puede usar  la información de inteligencia de suplantación de identidad para determinar rápidamente qué remitentes externos le envían legítimamente correo electrónico no autenticado (mensajes de dominios que no pasan comprobaciones de SPF, DKIM o DMARC).</span><span class="sxs-lookup"><span data-stu-id="4df1e-113">You can also use the **Spoof intelligence insight** to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="4df1e-114">Puede administrar la inteligencia de suplantación en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de correo Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="4df1e-114">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4df1e-115">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="4df1e-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4df1e-116">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4df1e-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span>
  - <span data-ttu-id="4df1e-117">Para ir directamente a la página **Configuración contra correo no** deseado de la directiva de inteligencia suplantación de dominio, use <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="4df1e-117">To go directly to the **Anti-spam settings** page for the spoof intelligence policy, use <https://protection.office.com/antispam>.</span></span>
  - <span data-ttu-id="4df1e-118">Para ir directamente a la página **Panel de seguridad** para la información de inteligencia suplantación, use <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="4df1e-118">To go directly to the **Security dashboard** page for the spoof intelligence insight, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

- <span data-ttu-id="4df1e-119">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4df1e-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4df1e-120">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="4df1e-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4df1e-121">Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="4df1e-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4df1e-122">Para modificar la directiva de inteligencia suplantada o habilitar o deshabilitar la  inteligencia suplantada, debe ser miembro de los grupos de roles Administración de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="4df1e-122">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4df1e-123">Para obtener acceso de solo lectura a la directiva de inteligencia suplantada, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="4df1e-123">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4df1e-124">Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="4df1e-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="4df1e-125">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="4df1e-125">**Notes**:</span></span>

  - <span data-ttu-id="4df1e-126">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4df1e-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4df1e-127">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="4df1e-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="4df1e-128">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="4df1e-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="4df1e-129">Las opciones de inteligencia suplantación de identidad se describen en [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="4df1e-129">The options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="4df1e-130">Puede habilitar, deshabilitar y configurar la configuración de la suplantación de identidad en las directivas contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="4df1e-130">You can enable, disable, and configure the spoof intelligence settings in anti-phishing policies.</span></span> <span data-ttu-id="4df1e-131">Para obtener instrucciones basadas en su suscripción, consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="4df1e-131">For instructions based on your subscription, see one of the following topics:</span></span>

  - <span data-ttu-id="4df1e-132">[Configurar directivas contra suplantación de](configure-anti-phishing-policies-eop.md)identidad en EOP .</span><span class="sxs-lookup"><span data-stu-id="4df1e-132">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>
  - <span data-ttu-id="4df1e-133">[Configurar directivas contra suplantación de](configure-mdo-anti-phishing-policies.md)identidad en Microsoft Defender para Office 365 .</span><span class="sxs-lookup"><span data-stu-id="4df1e-133">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="4df1e-134">Para obtener la configuración recomendada para la inteligencia de suplantación de identidad, consulte Configuración de directiva [contra suplantación de identidad](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)de EOP .</span><span class="sxs-lookup"><span data-stu-id="4df1e-134">For our recommended settings for spoof intelligence, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

## <a name="manage-spoofed-senders"></a><span data-ttu-id="4df1e-135">Administrar remitentes suplantados</span><span class="sxs-lookup"><span data-stu-id="4df1e-135">Manage spoofed senders</span></span>

<span data-ttu-id="4df1e-136">Hay dos maneras de permitir y bloquear remitentes suplantados:</span><span class="sxs-lookup"><span data-stu-id="4df1e-136">There are two ways to allow and block spoofed senders:</span></span>

- [<span data-ttu-id="4df1e-137">Usar la directiva de inteligencia suplantación</span><span class="sxs-lookup"><span data-stu-id="4df1e-137">Use the spoof intelligence policy</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [<span data-ttu-id="4df1e-138">Usar la información de inteligencia suplantación</span><span class="sxs-lookup"><span data-stu-id="4df1e-138">Use the spoof intelligence insight</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a><span data-ttu-id="4df1e-139">Administrar remitentes suplantados en la directiva de inteligencia suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="4df1e-139">Manage spoofed senders in the spoof intelligence policy</span></span>

1. <span data-ttu-id="4df1e-140">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="4df1e-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="4df1e-141">En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir La directiva de inteligencia de ![ ](../../media/scc-expand-icon.png) **suplantación.**</span><span class="sxs-lookup"><span data-stu-id="4df1e-141">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Seleccionar la directiva de inteligencia suplantación](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="4df1e-143">Realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="4df1e-143">Make one of the following selections:</span></span>

   - <span data-ttu-id="4df1e-144">**Revisar nuevos remitentes**</span><span class="sxs-lookup"><span data-stu-id="4df1e-144">**Review new senders**</span></span>
   - <span data-ttu-id="4df1e-145">**Mostrarme remitentes que ya revisé**</span><span class="sxs-lookup"><span data-stu-id="4df1e-145">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="4df1e-146">En decidir si estos remitentes pueden **suplantar** el control de los usuarios que aparece, seleccione una de las siguientes pestañas:</span><span class="sxs-lookup"><span data-stu-id="4df1e-146">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="4df1e-147">**Dominios:** remitentes que suplanta a los usuarios de los dominios internos.</span><span class="sxs-lookup"><span data-stu-id="4df1e-147">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="4df1e-148">**Dominios externos:** remitentes que suplanta a los usuarios en dominios externos.</span><span class="sxs-lookup"><span data-stu-id="4df1e-148">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="4df1e-149">Haga clic en Expandir icono en la columna ![ ](../../media/scc-expand-icon.png) **¿Permitido suplantación de identidad?**</span><span class="sxs-lookup"><span data-stu-id="4df1e-149">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="4df1e-150">Elija **Sí** para permitir al remitente suplantado o **elija No** para marcar el mensaje como suplantado.</span><span class="sxs-lookup"><span data-stu-id="4df1e-150">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="4df1e-151">La acción está controlada por la directiva anti phishing predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**).</span><span class="sxs-lookup"><span data-stu-id="4df1e-151">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="4df1e-152">Para obtener más información, consulte [Configuración de suplantación de identidad en las directivas contra phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="4df1e-152">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Captura de pantalla que muestra el flyout de remitentes suplantados y si el remitente puede suplantar](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="4df1e-154">Las columnas y valores que se muestran se explican en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="4df1e-154">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="4df1e-155">**Usuario suplantado:** la cuenta de usuario que se está suplantado.</span><span class="sxs-lookup"><span data-stu-id="4df1e-155">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="4df1e-156">Este es el remitente del mensaje en la dirección De (también conocida como la dirección) que `5322.From` se muestra en los clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4df1e-156">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="4df1e-157">SPF no comprueba la validez de esta dirección.</span><span class="sxs-lookup"><span data-stu-id="4df1e-157">The validity of this address is not checked by SPF.</span></span>
     - <span data-ttu-id="4df1e-158">En la **pestaña Dominios,** el valor contiene una sola dirección de correo electrónico, o si el servidor de correo electrónico de origen está suplantando varias cuentas de usuario, contiene **más de una**.</span><span class="sxs-lookup"><span data-stu-id="4df1e-158">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>
     - <span data-ttu-id="4df1e-159">En la **pestaña Dominios externos,** el valor contiene el dominio del usuario suplantado, no la dirección de correo electrónico completa.</span><span class="sxs-lookup"><span data-stu-id="4df1e-159">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="4df1e-160">**Infraestructura de** envío: dominio encontrado en una búsqueda DNS inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen.</span><span class="sxs-lookup"><span data-stu-id="4df1e-160">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="4df1e-161">Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="4df1e-161">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="4df1e-162">Para obtener más información acerca de los orígenes de mensajes y los remitentes de mensajes, vea [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="4df1e-162">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="4df1e-163">**# de mensajes:** número de mensajes de la infraestructura de envío a la organización que contienen el remitente o remitentes suplantados especificados en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="4df1e-163">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="4df1e-164">**# de quejas de usuario:** quejas que los usuarios han presentado contra este remitente en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="4df1e-164">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="4df1e-165">Las quejas suelen estar en forma de envíos de correo no deseado a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4df1e-165">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="4df1e-166">**Resultado de autenticación:** uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="4df1e-166">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="4df1e-167">**Pasado:** el remitente pasó las comprobaciones de autenticación de correo electrónico del remitente (SPF o DKIM).</span><span class="sxs-lookup"><span data-stu-id="4df1e-167">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="4df1e-168">**Error:** el remitente ha fallado las comprobaciones de autenticación del remitente EOP.</span><span class="sxs-lookup"><span data-stu-id="4df1e-168">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="4df1e-169">**Desconocido:** el resultado de estas comprobaciones no se conoce.</span><span class="sxs-lookup"><span data-stu-id="4df1e-169">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="4df1e-170">**Decisión establecida por:** muestra quién determinó si la infraestructura de envío puede suplantación de suplantación al usuario:</span><span class="sxs-lookup"><span data-stu-id="4df1e-170">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="4df1e-171">**Directiva de inteligencia suplantación** (automática)</span><span class="sxs-lookup"><span data-stu-id="4df1e-171">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="4df1e-172">**Administrador** (manual)</span><span class="sxs-lookup"><span data-stu-id="4df1e-172">**Admin** (manual)</span></span>

   - <span data-ttu-id="4df1e-173">**Última vista:** la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene el usuario suplantado.</span><span class="sxs-lookup"><span data-stu-id="4df1e-173">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="4df1e-174">**¿Se permite suplantación?**: Los valores que se ven aquí son:</span><span class="sxs-lookup"><span data-stu-id="4df1e-174">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="4df1e-175">**Sí:** los mensajes de la combinación de usuario suplantado y la infraestructura de envío se permiten y no se tratan como correo electrónico suplantado.</span><span class="sxs-lookup"><span data-stu-id="4df1e-175">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="4df1e-176">**No:** los mensajes de la combinación de usuario suplantado y la infraestructura de envío se marcan como suplantados.</span><span class="sxs-lookup"><span data-stu-id="4df1e-176">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="4df1e-177">La acción está controlada por la directiva anti phishing predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**).</span><span class="sxs-lookup"><span data-stu-id="4df1e-177">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="4df1e-178">Vea la siguiente sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4df1e-178">See the next section for more information.</span></span>

     - <span data-ttu-id="4df1e-179">**Algunos usuarios** **(solo pestaña** Dominios): una infraestructura de envío está suplantando a varios usuarios, donde algunos usuarios suplantados están permitidos y otros no.</span><span class="sxs-lookup"><span data-stu-id="4df1e-179">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="4df1e-180">Use la **pestaña Detallado** para ver las direcciones específicas.</span><span class="sxs-lookup"><span data-stu-id="4df1e-180">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="4df1e-181">En la parte inferior de la página, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4df1e-181">At the bottom of the page, click **Save**.</span></span>

#### <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="4df1e-182">Usar PowerShell para administrar remitentes suplantados</span><span class="sxs-lookup"><span data-stu-id="4df1e-182">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="4df1e-183">Para ver remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="4df1e-183">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="4df1e-184">En este ejemplo se devuelve información detallada sobre todos los remitentes que tienen permiso para suplantación de identidad de usuarios en los dominios.</span><span class="sxs-lookup"><span data-stu-id="4df1e-184">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="4df1e-185">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="4df1e-185">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="4df1e-186">Para configurar remitentes permitidos y bloqueados en la inteligencia de suplantación de identidad, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4df1e-186">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="4df1e-187">Capture la lista actual de remitentes suplantados detectados escribiendo el resultado del cmdlet **Get-PhishFilterPolicy** en un archivo CSV ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4df1e-187">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file by running the following command:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="4df1e-188">Edite el archivo CSV para agregar o modificar los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="4df1e-188">Edit the CSV file to add or modify the following values:</span></span>
   - <span data-ttu-id="4df1e-189">**Remitente** (dominio en el registro PTR del servidor de origen o dirección IP/24)</span><span class="sxs-lookup"><span data-stu-id="4df1e-189">**Sender** (domain in source server's PTR record or IP/24 address)</span></span>
   - <span data-ttu-id="4df1e-190">**SpoofedUser:** uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="4df1e-190">**SpoofedUser**: One of the following values:</span></span>
     - <span data-ttu-id="4df1e-191">Dirección de correo electrónico del usuario interno.</span><span class="sxs-lookup"><span data-stu-id="4df1e-191">The internal user's email address.</span></span>
     - <span data-ttu-id="4df1e-192">Dominio de correo electrónico del usuario externo.</span><span class="sxs-lookup"><span data-stu-id="4df1e-192">The external user's email domain.</span></span>
     - <span data-ttu-id="4df1e-193">Un valor en blanco que indica que desea bloquear o permitir todos los mensajes suplantados del **remitente** especificado, independientemente de la dirección de correo electrónico suplantada.</span><span class="sxs-lookup"><span data-stu-id="4df1e-193">A blank value that indicates you want to block or allow any and all spoofed messages from the specified **Sender**, regardless of the spoofed email address.</span></span>
   - <span data-ttu-id="4df1e-194">**AllowedToSpoof** (Sí o No)</span><span class="sxs-lookup"><span data-stu-id="4df1e-194">**AllowedToSpoof** (Yes or No)</span></span>
   - <span data-ttu-id="4df1e-195">**SpoofType** (interno o externo)</span><span class="sxs-lookup"><span data-stu-id="4df1e-195">**SpoofType** (Internal or External)</span></span>

   <span data-ttu-id="4df1e-196">Guarde el archivo, lea el archivo y almacene el contenido como una variable denominada `$UpdateSpoofedSenders` ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4df1e-196">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders` by running the following command:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="4df1e-197">Use la variable para configurar la directiva de inteligencia de `$UpdateSpoofedSenders` suplantación ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4df1e-197">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy by running the following command:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="4df1e-198">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="4df1e-198">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a><span data-ttu-id="4df1e-199">Administrar remitentes suplantados en la información de inteligencia suplantada</span><span class="sxs-lookup"><span data-stu-id="4df1e-199">Manage spoofed senders in the spoof intelligence insight</span></span>

1. <span data-ttu-id="4df1e-200">En el Centro de & cumplimiento, vaya al Panel **de administración de** \> **amenazas.**</span><span class="sxs-lookup"><span data-stu-id="4df1e-200">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard**.</span></span>

2. <span data-ttu-id="4df1e-201">En la **Ideas,** busque uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="4df1e-201">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="4df1e-202">**Probable suplantación** de dominio en los últimos siete días: esta información indica que la inteligencia suplantada está habilitada (está habilitada de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="4df1e-202">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="4df1e-203">**Habilitar protección contra** suplantación: esta información indica que la inteligencia de suplantación está deshabilitada y hacer clic en la información le permite habilitar la inteligencia de suplantación.</span><span class="sxs-lookup"><span data-stu-id="4df1e-203">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="4df1e-204">La información del panel muestra información como esta:</span><span class="sxs-lookup"><span data-stu-id="4df1e-204">The insight on the dashboard shows you information like this:</span></span>

   ![Captura de pantalla de información de inteligencia suplantación](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="4df1e-206">Esta información tiene dos modos:</span><span class="sxs-lookup"><span data-stu-id="4df1e-206">This insight has two modes:</span></span>

   - <span data-ttu-id="4df1e-207">**Modo de información:** si la suplantación de inteligencia está habilitada, la información muestra cuántos mensajes se han afectado por nuestras capacidades de inteligencia suplantada en los últimos siete días.</span><span class="sxs-lookup"><span data-stu-id="4df1e-207">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="4df1e-208">**Modo de** suplantación: si la inteligencia suplantada está  deshabilitada, la información muestra cuántos mensajes se habrían visto afectados por nuestras capacidades de inteligencia suplantada en los últimos siete días.</span><span class="sxs-lookup"><span data-stu-id="4df1e-208">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="4df1e-209">En cualquier caso, los dominios suplantados que se muestran en la información se separan en dos categorías: **dominios** sospechosos y **dominios no sospechosos.**</span><span class="sxs-lookup"><span data-stu-id="4df1e-209">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="4df1e-210">**Dominios sospechosos**:</span><span class="sxs-lookup"><span data-stu-id="4df1e-210">**Suspicious domains**:</span></span>
     - <span data-ttu-id="4df1e-211">Suplantación de confianza **alta:** en función de los patrones de envío históricos y la puntuación de reputación de los dominios, estamos muy seguros de que los dominios están suplantando la suplantación y es más probable que los mensajes de estos dominios sean malintencionados.</span><span class="sxs-lookup"><span data-stu-id="4df1e-211">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>
     - <span data-ttu-id="4df1e-212">**Suplantación** de confianza moderada: en función de los patrones de envío históricos y la puntuación de reputación de los dominios, estamos moderadamente seguros de que los dominios están suplantando y que los mensajes enviados desde estos dominios son legítimos.</span><span class="sxs-lookup"><span data-stu-id="4df1e-212">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="4df1e-213">Los falsos positivos son más probables en esta categoría que la suplantación de confianza alta.</span><span class="sxs-lookup"><span data-stu-id="4df1e-213">False positives are more likely in this category than high-confidence spoof.</span></span>
   - <span data-ttu-id="4df1e-214">**Dominios no sospechosos:** el dominio no pudo comprobar la autenticación explícita de correo [electrónico SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="4df1e-214">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="4df1e-215">Sin embargo, el dominio pasó nuestras comprobaciones implícitas de autenticación de correo electrónico ([autenticación compuesta](email-validation-and-authentication.md#composite-authentication)).</span><span class="sxs-lookup"><span data-stu-id="4df1e-215">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="4df1e-216">Como resultado, no se ha realizado ninguna acción contra la suplantación en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4df1e-216">As a result, no anti-spoofing action was taken on the message.</span></span>

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a><span data-ttu-id="4df1e-217">Ver información detallada sobre dominios sospechosos y no sospechosos</span><span class="sxs-lookup"><span data-stu-id="4df1e-217">View detailed information about suspicious and nonsuspicious domains</span></span>

1. <span data-ttu-id="4df1e-218">En la información de inteligencia suplantada, haga clic en **Dominios** sospechosos o Dominios no sospechosos para ir a la **página Spoof intelligence insight.** </span><span class="sxs-lookup"><span data-stu-id="4df1e-218">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="4df1e-219">La **página Spoof Intelligence insight** contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="4df1e-219">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="4df1e-220">**Dominio suplantado:** dominio del usuario suplantado que se muestra en el **cuadro** De de los clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4df1e-220">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="4df1e-221">Esta dirección también se conoce como `5322.From` la dirección.</span><span class="sxs-lookup"><span data-stu-id="4df1e-221">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="4df1e-222">**Infraestructura:** también conocida como la _infraestructura de envío_.</span><span class="sxs-lookup"><span data-stu-id="4df1e-222">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="4df1e-223">El dominio encontrado en una búsqueda DNS inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen.</span><span class="sxs-lookup"><span data-stu-id="4df1e-223">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="4df1e-224">Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="4df1e-224">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="4df1e-225">**Recuento de** mensajes: el número de mensajes de la infraestructura de envío a la organización que contienen el dominio suplantado especificado en los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="4df1e-225">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="4df1e-226">**Vista por última** vez: la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene el dominio suplantado.</span><span class="sxs-lookup"><span data-stu-id="4df1e-226">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="4df1e-227">**Tipo de suplantación:** este valor es **Externo**.</span><span class="sxs-lookup"><span data-stu-id="4df1e-227">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="4df1e-228">**¿Se permite suplantación?**: Los valores que se ven aquí son:</span><span class="sxs-lookup"><span data-stu-id="4df1e-228">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="4df1e-229">**Sí:** los mensajes de la combinación del dominio del usuario suplantado y la infraestructura de envío se permiten y no se tratan como correo electrónico suplantado.</span><span class="sxs-lookup"><span data-stu-id="4df1e-229">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="4df1e-230">**No:** los mensajes de la combinación del dominio del usuario suplantado y la infraestructura de envío se marcan como suplantados.</span><span class="sxs-lookup"><span data-stu-id="4df1e-230">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="4df1e-231">La acción está controlada por la directiva anti phishing predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**).</span><span class="sxs-lookup"><span data-stu-id="4df1e-231">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

2. <span data-ttu-id="4df1e-232">Seleccione un elemento de la lista para ver detalles sobre el par de infraestructura de dominio y envío en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="4df1e-232">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="4df1e-233">La información incluye:</span><span class="sxs-lookup"><span data-stu-id="4df1e-233">The information includes:</span></span>
   - <span data-ttu-id="4df1e-234">Por qué lo capturamos.</span><span class="sxs-lookup"><span data-stu-id="4df1e-234">Why we caught this.</span></span>
   - <span data-ttu-id="4df1e-235">Lo que necesita hacer.</span><span class="sxs-lookup"><span data-stu-id="4df1e-235">What you need to do.</span></span>
   - <span data-ttu-id="4df1e-236">Un resumen de dominio.</span><span class="sxs-lookup"><span data-stu-id="4df1e-236">A domain summary.</span></span>
   - <span data-ttu-id="4df1e-237">WhoIs datos sobre el remitente.</span><span class="sxs-lookup"><span data-stu-id="4df1e-237">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="4df1e-238">Mensajes similares que hemos visto en el inquilino del mismo remitente.</span><span class="sxs-lookup"><span data-stu-id="4df1e-238">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="4df1e-239">Desde aquí, también puede elegir agregar o quitar el par de infraestructura dominio/envío de la lista permitido para **suplantación** de remitente.</span><span class="sxs-lookup"><span data-stu-id="4df1e-239">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="4df1e-240">Simplemente establece la alternancia según corresponda.</span><span class="sxs-lookup"><span data-stu-id="4df1e-240">Simply set the toggle accordingly.</span></span>

   ![Captura de pantalla de un dominio en el panel de detalles de Spoof intelligence insight](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4df1e-242">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="4df1e-242">How do you know these procedures worked?</span></span>

<span data-ttu-id="4df1e-243">Para comprobar que ha configurado la inteligencia suplantación de identidad con remitentes a los que se les permite y no se les permite suplantación de identidad, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4df1e-243">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, use any of the following steps:</span></span>

- <span data-ttu-id="4df1e-244">En el Centro de seguridad y  cumplimiento de &, vaya a Directiva de administración de amenazas \>  \> **Antispam** \>  \>  \>    expanda Directiva de inteligencia de suplantación de identidad seleccione Mostrarme remitentes que ya revisé seleccione la pestaña Dominios o Dominios externos y compruebe el valor ¿Permitido suplantar? para el remitente.</span><span class="sxs-lookup"><span data-stu-id="4df1e-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="4df1e-245">En PowerShell, ejecute los siguientes comandos para ver los remitentes a los que se les permite suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="4df1e-245">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="4df1e-246">En PowerShell, ejecute el siguiente comando para exportar la lista de todos los remitentes suplantados a un archivo CSV:</span><span class="sxs-lookup"><span data-stu-id="4df1e-246">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
