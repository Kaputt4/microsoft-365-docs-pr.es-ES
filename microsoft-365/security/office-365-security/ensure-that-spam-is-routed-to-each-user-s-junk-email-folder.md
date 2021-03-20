---
title: Configurar EOP para correo no deseado en entornos híbridos
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a enrutar el correo no deseado a las carpetas de correo no deseado del usuario en un entorno híbrido de Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910863"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="7dcaa-103">Configurar EOP independiente para entregar correo no deseado a la carpeta correo no deseado en entornos híbridos</span><span class="sxs-lookup"><span data-stu-id="7dcaa-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7dcaa-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="7dcaa-104">**Applies to**</span></span>
-  [<span data-ttu-id="7dcaa-105">Exchange Online Protection independiente</span><span class="sxs-lookup"><span data-stu-id="7dcaa-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

> [!IMPORTANT]
> <span data-ttu-id="7dcaa-106">Este tema es solo para clientes independientes de EOP en entornos híbridos.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="7dcaa-107">Este tema no se aplica a los clientes de Microsoft 365 con buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="7dcaa-108">Si es un cliente independiente de Exchange Online Protection (EOP) en un entorno híbrido, debe configurar su organización de Exchange local para reconocer y traducir los veredictos de filtrado de correo no deseado de EOP, de modo que la regla de correo no deseado del buzón local pueda mover los mensajes a la carpeta correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="7dcaa-109">En concreto, debe crear reglas de flujo de correo (también conocidas como reglas de transporte) en su organización de Exchange local con condiciones que encuentren mensajes con cualquiera de los siguientes encabezados y valores de correo no deseado de EOP, y acciones que establezcan el nivel de confianza de correo no deseado (SCL) de esos mensajes en 6:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="7dcaa-110">`X-Forefront-Antispam-Report: SFV:SPM` (mensaje marcado como correo no deseado por el filtrado de correo no deseado)</span><span class="sxs-lookup"><span data-stu-id="7dcaa-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="7dcaa-111">`X-Forefront-Antispam-Report: SFV:SKS` (mensaje marcado como correo no deseado por las reglas de flujo de correo en EOP antes del filtrado de correo no deseado)</span><span class="sxs-lookup"><span data-stu-id="7dcaa-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="7dcaa-112">`X-Forefront-Antispam-Report: SFV:SKB` (Mensaje marcado como correo no deseado por el filtrado de correo no deseado debido a que la dirección de correo electrónico o el dominio de correo electrónico del remitente están en la lista de remitentes bloqueados o en la lista de dominios bloqueados en EOP)</span><span class="sxs-lookup"><span data-stu-id="7dcaa-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="7dcaa-113">Para obtener más información acerca de estos valores de encabezado, vea [Encabezados de mensaje contra correo no deseado](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="7dcaa-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="7dcaa-114">En este tema se describe cómo crear estas reglas de flujo de correo en el Centro de administración de Exchange (EAC) y en el Shell de administración de Exchange (Exchange PowerShell) en la organización local de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="7dcaa-115">En lugar de entregar los mensajes a la carpeta correo no deseado del usuario local, puede configurar directivas contra correo no deseado en EOP para poner en cuarentena los mensajes de correo no deseado en EOP.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="7dcaa-116">Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7dcaa-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7dcaa-117">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="7dcaa-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7dcaa-118">Debe tener asignados permisos en el entorno de Exchange local antes de poder realizar estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="7dcaa-119">En concreto, debe tener  asignado el rol Reglas de transporte, que se  asigna a los roles Administración de la **organización,** Administración de cumplimiento y Administración de registros de forma predeterminada. </span><span class="sxs-lookup"><span data-stu-id="7dcaa-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="7dcaa-120">Para obtener más información, vea [Agregar miembros a un grupo de roles](/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="7dcaa-120">For more information, see [Add members to a role group](/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="7dcaa-121">Si y cuando se entrega un mensaje a la carpeta correo no deseado de una organización de Exchange local, se controla mediante una combinación de la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="7dcaa-122">Valor _del parámetro SCLJunkThreshold_ en el cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) en el Shell de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="7dcaa-123">El valor predeterminado es 4, lo que significa que un SCL de 5 o superior debe entregar el mensaje a la carpeta de correo electrónico no deseado del usuario.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="7dcaa-124">Valor _del parámetro SCLJunkThreshold_ en el cmdlet [Set-Mailbox](/powershell/module/exchange/set-mailbox) en el Shell de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="7dcaa-125">El valor predeterminado está en blanco ($null), lo que significa que se usa la configuración de la organización.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="7dcaa-126">Para obtener más información, vea Umbrales de nivel de confianza de correo no deseado [(SCL) de Exchange.](/Exchange/antispam-and-antimalware/antispam-protection/scl)</span><span class="sxs-lookup"><span data-stu-id="7dcaa-126">For details, see [Exchange spam confidence level (SCL) thresholds](/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="7dcaa-127">Si la regla de correo no deseado está habilitada en el buzón (el valor del parámetro _Enabled_ $true en el cmdlet [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) en el Shell de administración de Exchange).</span><span class="sxs-lookup"><span data-stu-id="7dcaa-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="7dcaa-128">Es la regla de correo no deseado la que mueve el mensaje a la carpeta correo no deseado después de la entrega.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="7dcaa-129">De forma predeterminada, la regla de correo no deseado está habilitada en los buzones.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="7dcaa-130">Para obtener más información, vea [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="7dcaa-130">For more information, see [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="7dcaa-131">Para abrir el EAC en un Exchange Server, vea Centro de [administración de Exchange en Exchange Server](/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="7dcaa-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="7dcaa-132">Para abrir el Shell de administración de Exchange, consulte [Abrir el Shell de administración de Exchange](/powershell/exchange/open-the-exchange-management-shell).</span><span class="sxs-lookup"><span data-stu-id="7dcaa-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="7dcaa-133">Para obtener más información acerca de las reglas de flujo de correo en Exchange local, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="7dcaa-134">Reglas de flujo de correo en Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7dcaa-134">Mail flow rules in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="7dcaa-135">Condiciones y excepciones de reglas de flujo de correo (predicados) en Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7dcaa-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="7dcaa-136">Acciones de regla de flujo de correo en Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7dcaa-136">Mail flow rule actions in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="7dcaa-137">Usar el EAC para crear reglas de flujo de correo que establezcan el SCL de mensajes de correo no deseado de EOP</span><span class="sxs-lookup"><span data-stu-id="7dcaa-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="7dcaa-138">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="7dcaa-139">Haga **clic en** Agregar icono Agregar y seleccione Crear una nueva ![ ](../../media/ITPro-EAC-AddIcon.png) **regla** en la lista desplegable que aparece.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="7dcaa-140">En la ventana **Nueva regla** que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="7dcaa-141">**Nombre:** escriba un nombre descriptivo único para la regla.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="7dcaa-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-142">For example:</span></span>

     - <span data-ttu-id="7dcaa-143">EOP SFV:SPM a SCL 6</span><span class="sxs-lookup"><span data-stu-id="7dcaa-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="7dcaa-144">EOP SFV:SKS a SCL 6</span><span class="sxs-lookup"><span data-stu-id="7dcaa-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="7dcaa-145">EOP SFV:SKB a SCL 6</span><span class="sxs-lookup"><span data-stu-id="7dcaa-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="7dcaa-146">Haga clic en **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-146">Click **More Options**.</span></span>

   - <span data-ttu-id="7dcaa-147">**Aplique esta regla si**: Select **A message header** includes any of \> **these words**.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="7dcaa-148">En el **encabezado de texto Entrar incluye Escribir oración** de palabras que aparece, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="7dcaa-149">Haga **clic en Escribir texto**.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-149">Click **Enter text**.</span></span> <span data-ttu-id="7dcaa-150">En el **cuadro de diálogo** Especificar nombre de encabezado que aparece, escriba **X-Forefront-Antispam-Report** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="7dcaa-151">Haga  **clic en Escribir palabras**.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-151">Click  **Enter words**.</span></span> <span data-ttu-id="7dcaa-152">En  el cuadro de diálogo Especificar palabras o frases que aparece, escriba uno de los valores de encabezado de correo  no deseado de EOP (**SFV:SPM**, **SFV:SKS** o **SFV:SKB**), haga clic en Agregar icono y, a continuación, haga clic en ![ ](../../media/ITPro-EAC-AddIcon.png) **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="7dcaa-153">**Haga lo siguiente:** Seleccione **Modificar las propiedades del mensaje** Establecer el nivel de confianza de correo no deseado \> **(SCL).**</span><span class="sxs-lookup"><span data-stu-id="7dcaa-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="7dcaa-154">En el cuadro de diálogo Especificar **SCL** que aparece, seleccione **6** (el valor predeterminado es **5**).</span><span class="sxs-lookup"><span data-stu-id="7dcaa-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="7dcaa-155">Cuando haya terminado, haga clic en **Guardar**</span><span class="sxs-lookup"><span data-stu-id="7dcaa-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="7dcaa-156">Repita estos pasos para los valores de veredicto de correo no deseado de EOP restantes (**SFV:SPM**, **SFV:SKS** o **SFV:SKB**).</span><span class="sxs-lookup"><span data-stu-id="7dcaa-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="7dcaa-157">Usar el Shell de administración de Exchange para crear reglas de flujo de correo que establezcan el SCL de los mensajes de correo no deseado de EOP</span><span class="sxs-lookup"><span data-stu-id="7dcaa-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="7dcaa-158">Use la siguiente sintaxis para crear las tres reglas de flujo de correo:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="7dcaa-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="7dcaa-160">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="7dcaa-160">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7dcaa-161">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="7dcaa-161">How do you know this worked?</span></span>

<span data-ttu-id="7dcaa-162">Para comprobar que ha configurado correctamente EOP independiente para entregar correo no deseado a la carpeta correo no deseado en un entorno híbrido, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="7dcaa-163">En el EAC, vaya a **Flujo** de correo Reglas , seleccione la regla y, a continuación, haga clic \>  **en Editar** icono Editar para comprobar ![ la ](../../media/ITPro-EAC-EditIcon.png) configuración.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="7dcaa-164">En el Shell de administración de Exchange, reemplace por el nombre de la regla de flujo de correo y rul el \<RuleName\> siguiente comando para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="7dcaa-165">En un sistema de correo electrónico externo que no analiza los mensajes salientes en busca de **correo** no deseado, envíe un mensaje de prueba genérica para correo electrónico masivo no solicitado (GTUBE) a un destinatario afectado y confirme que se ha entregado a su carpeta correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="7dcaa-166">Un mensaje GTUBE es similar al archivo de texto del European Institute of Computer virus Research (EICAR) para probar la configuración de malware.</span><span class="sxs-lookup"><span data-stu-id="7dcaa-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="7dcaa-167">Para enviar un mensaje de GTUBE, incluya el siguiente texto en el cuerpo de un mensaje de correo electrónico en una sola línea, sin espacios ni saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="7dcaa-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```