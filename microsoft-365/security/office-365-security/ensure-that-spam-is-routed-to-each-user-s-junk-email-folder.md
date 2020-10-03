---
title: Configurar EOP a correo no deseado en entornos híbridos
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo enrutar correo no deseado a las carpetas de correo no deseado del usuario en un entorno híbrido de protección de Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 76003f18009ebf9159f01d916cdaf38b50a213d1
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350344"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="c2995-103">Configurar un EOP independiente para enviar correo no deseado a la carpeta de correo no deseado en entornos híbridos</span><span class="sxs-lookup"><span data-stu-id="c2995-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="c2995-104">Este tema es solo para clientes de EOP independientes en entornos híbridos.</span><span class="sxs-lookup"><span data-stu-id="c2995-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="c2995-105">Este tema no se aplica a los clientes de Microsoft 365 con buzones de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c2995-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="c2995-106">Si es cliente independiente de Exchange Online Protection (EOP) en un entorno híbrido, debe configurar la organización de Exchange local para que reconozca y traduzca los veredictos del filtrado de correo no deseado de EOP, por lo que la regla de correo no deseado del buzón local puede mover mensajes a la carpeta de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="c2995-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="c2995-107">En concreto, debe crear reglas de flujo de correo (también conocidas como reglas de transporte) en su organización de Exchange local con condiciones que encuentren mensajes con cualquiera de los siguientes valores y encabezados de correo no deseado de EOP, así como acciones que establezcan el nivel de confianza contra correo no deseado (SCL) de esos mensajes en 6:</span><span class="sxs-lookup"><span data-stu-id="c2995-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="c2995-108">`X-Forefront-Antispam-Report: SFV:SPM` (mensaje marcado como correo no deseado por el filtrado de correo no deseado)</span><span class="sxs-lookup"><span data-stu-id="c2995-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="c2995-109">`X-Forefront-Antispam-Report: SFV:SKS` (mensaje marcado como correo no deseado por reglas de flujo de correo en EOP antes del filtrado de correo no deseado)</span><span class="sxs-lookup"><span data-stu-id="c2995-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="c2995-110">`X-Forefront-Antispam-Report: SFV:SKB` (mensaje marcado como correo no deseado por el filtrado de correo no deseado debido a la dirección de correo electrónico o al dominio de correo electrónico del remitente en la lista de remitentes bloqueados o en la lista de dominios bloqueados en EOP)</span><span class="sxs-lookup"><span data-stu-id="c2995-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="c2995-111">Para obtener más información acerca de estos valores de encabezado, consulte [anti-spam Message headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="c2995-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="c2995-112">En este tema se describe cómo crear estas reglas de flujo de correo en el centro de administración de Exchange (EAC) y en el shell de administración de Exchange (Exchange PowerShell) en la organización de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="c2995-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="c2995-113">En lugar de entregar los mensajes a la carpeta de correo no deseado del usuario local, puede configurar directivas contra correo no deseado en EOP para poner en cuarentena los mensajes de correo no deseado en EOP.</span><span class="sxs-lookup"><span data-stu-id="c2995-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="c2995-114">Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c2995-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c2995-115">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="c2995-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c2995-116">Debe tener asignados permisos en el entorno local de Exchange para poder realizar estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="c2995-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="c2995-117">En concreto, debe tener asignado el rol **reglas de transporte** , que se asigna a las **funciones administración**de la organización, **Administración del cumplimiento**y administración de **registros** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c2995-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="c2995-118">Para obtener más información, vea [Agregar miembros a un grupo de funciones](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="c2995-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="c2995-119">Si un mensaje se entrega a la carpeta de correo no deseado en una organización de Exchange local y se controla mediante una combinación de las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="c2995-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="c2995-120">El valor del parámetro _SCLJunkThreshold_ en el cmdlet [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) del shell de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c2995-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="c2995-121">El valor predeterminado es 4, lo que significa que un SCL de 5 o superior debe entregar el mensaje en la carpeta de correo no deseado del usuario.</span><span class="sxs-lookup"><span data-stu-id="c2995-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="c2995-122">El valor del parámetro _SCLJunkThreshold_ en el cmdlet [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) en el shell de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c2995-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="c2995-123">El valor predeterminado está en blanco ($null), lo que significa que se usa la configuración de la organización.</span><span class="sxs-lookup"><span data-stu-id="c2995-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="c2995-124">Para obtener información detallada, consulte [umbrales de nivel de confianza contra correo no deseado (SCL) de Exchange](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span><span class="sxs-lookup"><span data-stu-id="c2995-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="c2995-125">Si la regla de correo no deseado está habilitada en el buzón (el valor del parámetro _Enabled_ se $true en el cmdlet [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) en el shell de administración de Exchange).</span><span class="sxs-lookup"><span data-stu-id="c2995-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="c2995-126">Es la regla de correo no deseado que realmente mueve el mensaje a la carpeta correo electrónico no deseado después de la entrega.</span><span class="sxs-lookup"><span data-stu-id="c2995-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="c2995-127">De forma predeterminada, la regla de correo no deseado está habilitada en los buzones.</span><span class="sxs-lookup"><span data-stu-id="c2995-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="c2995-128">Para obtener más información, consulte [configurar las opciones de correo no deseado de Exchange en buzones](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="c2995-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="c2995-129">Para abrir el EAC en un servidor de Exchange, vea [centro de administración de Exchange en Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c2995-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="c2995-130">Para abrir el shell de administración de Exchange, consulte [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span><span class="sxs-lookup"><span data-stu-id="c2995-130">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="c2995-131">Para obtener más información acerca de las reglas de flujo de correo en Exchange local, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="c2995-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="c2995-132">Reglas de flujo de correo en Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c2995-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="c2995-133">Excepciones (predicados) y condiciones de reglas de flujo de correo en Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c2995-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="c2995-134">Acciones de las reglas de flujo de correo en Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c2995-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="c2995-135">Usar el EAC para crear reglas de flujo de correo que establezcan el SCL de los mensajes de correo no deseado de EOP</span><span class="sxs-lookup"><span data-stu-id="c2995-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="c2995-136">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="c2995-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="c2995-137">Haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) y seleccione **crear una nueva regla** en la lista desplegable que aparece.</span><span class="sxs-lookup"><span data-stu-id="c2995-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="c2995-138">En la ventana **Nueva regla** que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c2995-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="c2995-139">**Name**: escriba un nombre único y descriptivo para la regla.</span><span class="sxs-lookup"><span data-stu-id="c2995-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="c2995-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c2995-140">For example:</span></span>

     - <span data-ttu-id="c2995-141">EOP SFV: SPM a SCL 6</span><span class="sxs-lookup"><span data-stu-id="c2995-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="c2995-142">EOP SFV: SKS a SCL 6</span><span class="sxs-lookup"><span data-stu-id="c2995-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="c2995-143">EOP SFV: SKB a SCL 6</span><span class="sxs-lookup"><span data-stu-id="c2995-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="c2995-144">Haga clic en **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="c2995-144">Click **More Options**.</span></span>

   - <span data-ttu-id="c2995-145">**Aplicar esta regla si**: seleccione **un encabezado** \> **de mensaje incluye alguna de estas palabras**.</span><span class="sxs-lookup"><span data-stu-id="c2995-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="c2995-146">En la frase **Escriba el encabezado de texto incluye escribir palabras** , siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c2995-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="c2995-147">Haga clic en **escribir texto**.</span><span class="sxs-lookup"><span data-stu-id="c2995-147">Click **Enter text**.</span></span> <span data-ttu-id="c2995-148">En el cuadro de diálogo **especificar nombre de encabezado** que aparece, escriba **X-Forefront-antispam-Report** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c2995-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="c2995-149">Haga clic en  **escribir palabras**.</span><span class="sxs-lookup"><span data-stu-id="c2995-149">Click  **Enter words**.</span></span> <span data-ttu-id="c2995-150">En el cuadro de diálogo **especificar palabras o frases** que aparece, escriba uno de los valores de encabezado de correo no deseado de EOP (**SFV: SPM**, **SFV: SKS**o **SFV: SKB**), haga clic en **Agregar** ![ icono Agregar ](../../media/ITPro-EAC-AddIcon.png) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c2995-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="c2995-151">**Haga lo siguiente**: seleccione **modificar las propiedades del mensaje** \> **establecer el nivel de confianza contra correo no deseado (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="c2995-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="c2995-152">En el cuadro de diálogo **especificar SCL** que aparece, seleccione **6** (el valor predeterminado es **5**).</span><span class="sxs-lookup"><span data-stu-id="c2995-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="c2995-153">Cuando haya terminado, haga clic en **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="c2995-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="c2995-154">Repita estos pasos para los demás valores de veredicto de correo no deseado de EOP (**SFV: SPM**, **SFV: SKS**o **SFV: SKB**).</span><span class="sxs-lookup"><span data-stu-id="c2995-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="c2995-155">Usar el shell de administración de Exchange para crear reglas de flujo de correo que establezcan el SCL de los mensajes de correo no deseado de EOP</span><span class="sxs-lookup"><span data-stu-id="c2995-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="c2995-156">Use la siguiente sintaxis para crear las tres reglas de flujo de correo:</span><span class="sxs-lookup"><span data-stu-id="c2995-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="c2995-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c2995-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="c2995-158">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="c2995-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c2995-159">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="c2995-159">How do you know this worked?</span></span>

<span data-ttu-id="c2995-160">Para comprobar que configuró correctamente EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en un entorno híbrido, realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="c2995-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="c2995-161">En el EAC, vaya a reglas de **flujo de correo** \> **Rules**, seleccione la regla y, a continuación, haga clic en **Editar** ![ icono ](../../media/ITPro-EAC-EditIcon.png) de edición para comprobar la configuración.</span><span class="sxs-lookup"><span data-stu-id="c2995-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="c2995-162">En el shell de administración de Exchange, reemplace \<RuleName\> por el nombre de la regla de flujo de correo y regla el siguiente comando para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="c2995-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="c2995-163">En un sistema de correo electrónico externo **que no analiza los mensajes salientes en busca de correo no deseado**, envíe una prueba genérica de mensaje de correo electrónico masivo no solicitado (GTUBE) a un destinatario afectado y confirme que se entrega a su carpeta de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="c2995-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="c2995-164">Un mensaje GTUBE es similar al archivo de texto del European Institute of Computer virus Research (EICAR) para probar la configuración de malware.</span><span class="sxs-lookup"><span data-stu-id="c2995-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="c2995-165">Para enviar un mensaje GTUBE, incluya el siguiente texto en el cuerpo de un mensaje de correo electrónico en una sola línea, sin espacios ni saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="c2995-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
