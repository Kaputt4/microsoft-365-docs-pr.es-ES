---
title: Enviar mensajes a Microsoft de forma manual para su análisis
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Usted y sus usuarios pueden enviar mensajes de correo no deseado falsos negativos y falsos positivos a Microsoft para su análisis. '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032809"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="32788-103">Enviar mensajes a Microsoft de forma manual para su análisis</span><span class="sxs-lookup"><span data-stu-id="32788-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="32788-104">Si es administrador de una organización de Office 365 con buzones de correo de Exchange Online, le recomendamos que use el portal de envíos del centro de seguridad & cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="32788-104">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="32788-105">Para obtener más información, vea [usar el envío de administración para enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="32788-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="32788-106">Puede resultar frustrante cuando los usuarios de la organización reciben mensajes de correo no deseado o mensajes de suplantación de identidad (phishing) en su bandeja de entrada, o si no reciben un mensaje de correo electrónico legítimo porque está marcado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="32788-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="32788-107">Estamos ajustando constantemente los filtros de correo no deseado para que sean más precisos.</span><span class="sxs-lookup"><span data-stu-id="32788-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="32788-108">Usted y sus usuarios pueden ayudar a este proceso mediante el envío de falsos positivos (correo electrónico bueno marcado como no válido), los falsos negativos (correo erróneo permitido) y los mensajes de suplantación de identidad a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="32788-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="32788-109">Debido al elevado volumen de envíos que recibimos, es posible que no podamos contestar todas las solicitudes de análisis.</span><span class="sxs-lookup"><span data-stu-id="32788-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="32788-110">Enviar falsos negativos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="32788-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="32788-111">En lugar de usar los siguientes procedimientos para informar sobre falsos negativos, los usuarios de Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) pueden usar el complemento de mensajes de informe para Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="32788-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="32788-112">Para obtener información sobre cómo instalar y usar esta herramienta, consulte [Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="32788-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="32788-113">Si recibe un mensaje que pasa a través del filtrado de correo no deseado que debería haberse identificado como correo no deseado o suplantación de identidad, puede enviar el mensaje a Microsoft spam Analysis y Microsoft phishing Analysis Teams según corresponda.</span><span class="sxs-lookup"><span data-stu-id="32788-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="32788-114">Los analistas revisarán el mensaje y lo agregarán a los filtros de todo el servicio si cumple con los criterios de clasificación.</span><span class="sxs-lookup"><span data-stu-id="32788-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="32788-115">Cree un mensaje de correo electrónico nuevo en blanco con uno de los siguientes destinatarios:</span><span class="sxs-lookup"><span data-stu-id="32788-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="32788-116">**Correo no deseado**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="32788-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="32788-117">**Suplantación de identidad**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="32788-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="32788-118">Arrastre y coloque el mensaje no deseado o de suplantación de identidad en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="32788-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="32788-119">Se guardará el mensaje no deseado o de suplantación de identidad (phishing) como datos adjuntos en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="32788-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="32788-120">No copie y pegue el contenido del mensaje o lo reenvíe (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).</span><span class="sxs-lookup"><span data-stu-id="32788-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="32788-121">Puede adjuntar varios mensajes en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="32788-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="32788-122">Asegúrese de que todos los mensajes sean del mismo tipo: mensajes de suplantación de identidad (phishing) o mensajes de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="32788-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="32788-123">Deje el cuerpo del nuevo mensaje en blanco.</span><span class="sxs-lookup"><span data-stu-id="32788-123">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="32788-124">Use cualquiera de los formatos. msg (formato predeterminado de Outlook) o. eml (formato predeterminado de Outlook en la web) para los mensajes adjuntos.</span><span class="sxs-lookup"><span data-stu-id="32788-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="32788-125">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="32788-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="32788-126">Los administradores tienen varias formas diferentes de bloquear mensajes específicos que se identifican como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="32788-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="32788-127">Para obtener más información, vea [crear listas de remitentes bloqueados en Office 365](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="32788-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="32788-128">Enviar falsos positivos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="32788-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="32788-129">En lugar de usar los siguientes procedimientos para notificar falsos positivos, los usuarios de Outlook y Outlook en la web pueden usar el complemento de mensajes de informe para Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="32788-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="32788-130">Para obtener información sobre cómo instalar y usar esta herramienta, consulte [Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="32788-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="32788-131">Si un mensaje se identificó incorrectamente como correo no deseado, puede enviar el mensaje al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32788-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="32788-132">Los analistas evaluarán el mensaje y (según los resultados del análisis) se pueden ajustar los filtros de todo el servicio para permitir el paso del mensaje.</span><span class="sxs-lookup"><span data-stu-id="32788-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="32788-133">Cree un nuevo mensaje de correo electrónico en `not_junk@office365.microsoft.com` blanco con como destinatario:</span><span class="sxs-lookup"><span data-stu-id="32788-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="32788-134">Arrastre y coloque el mensaje con identificación indebido en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="32788-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="32788-135">De este modo, se guardará el mensaje identificado indebido como datos adjuntos en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="32788-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="32788-136">No copie y pegue el contenido del mensaje o lo reenvíe (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).</span><span class="sxs-lookup"><span data-stu-id="32788-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="32788-137">Puede adjuntar varios mensajes en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="32788-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="32788-138">Asegúrese de que todos los mensajes sean del mismo tipo: mensajes de suplantación de identidad (phishing) o mensajes de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="32788-138">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="32788-139">Deje el cuerpo del nuevo mensaje en blanco.</span><span class="sxs-lookup"><span data-stu-id="32788-139">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="32788-140">Use cualquiera de los formatos. msg (formato predeterminado de Outlook) o. eml (formato predeterminado de Outlook en la web) para los mensajes adjuntos.</span><span class="sxs-lookup"><span data-stu-id="32788-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="32788-141">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="32788-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="32788-142">Los administradores tienen varias formas diferentes de permitir que mensajes específicos omitan el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="32788-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="32788-143">Para obtener más información, consulte [crear listas de remitentes seguros en Office 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="32788-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="32788-144">Crear una regla de flujo de correo para recibir copias de mensajes que se notifican a Microsoft</span><span class="sxs-lookup"><span data-stu-id="32788-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="32788-145">Puede crear una regla de flujo de correo (también denominada regla de transporte) que busca mensajes de correo electrónico que se notifican a Microsoft mediante los métodos descritos en este tema y puede configurar destinatarios en copia oculta para recibir copias de estos mensajes notificados.</span><span class="sxs-lookup"><span data-stu-id="32788-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="32788-146">Puede crear la regla de flujo de correo en el centro de administración de Exchange (EAC) y PowerShell (Exchange Online PowerShell para Office 365 clientes; Exchange Online Protection PowerShell para clientes independientes de EOP).</span><span class="sxs-lookup"><span data-stu-id="32788-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="32788-147">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="32788-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="32788-148">Debe tener asignados permisos en Exchange Online para poder realizar estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="32788-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="32788-149">En concreto, debe tener asignado el rol **reglas de transporte** , que se asigna a las **funciones administración**de la organización, **Administración del cumplimiento**y administración de **registros** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="32788-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="32788-150">Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="32788-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="32788-151">Para abrir el EAC en Exchange Online, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="32788-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="32788-152">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="32788-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="32788-153">Para conectarse a Exchange Online Protection PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="32788-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="32788-154">Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y EOP independiente, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="32788-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="32788-155">Reglas de flujo de correo (reglas de transporte) en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="32788-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="32788-156">Excepciones (predicados) y condiciones de reglas de flujo de correo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="32788-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="32788-157">Acciones de las reglas de flujo de correo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="32788-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="32788-158">Usar el EAC para crear una regla de flujo de correo para recibir copias de mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="32788-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="32788-159">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="32788-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="32788-160">Haga **Add** ![clic en agregar](../../media/ITPro-EAC-AddIcon.png) icono Agregar y, a continuación, seleccione **crear una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="32788-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="32788-161">En la ventana **Nueva regla** que se abre, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="32788-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="32788-162">**Name**: escriba un nombre único y descriptivo para la regla.</span><span class="sxs-lookup"><span data-stu-id="32788-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="32788-163">Por ejemplo, los mensajes CCO que se notifican a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32788-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="32788-164">Haga clic en **Más opciones**.</span><span class="sxs-lookup"><span data-stu-id="32788-164">Click **More Options**.</span></span>

   - <span data-ttu-id="32788-165">**Aplicar esta regla si**: seleccione **la dirección del destinatario** \> **incluye cualquiera de estas palabras**: en el cuadro de diálogo **especificar palabras o frases** que aparece, escriba uno de los siguientes valores, haga](../../media/ITPro-EAC-AddIcon.png)clic en **Agregar** ![icono Agregar y repita el procedimiento hasta que haya introducido todos los valores.</span><span class="sxs-lookup"><span data-stu-id="32788-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="32788-166">Para editar una entrada, selecciónela y haga clic en **Editar** ![icono](../../media/ITPro-EAC-EditIcon.png)de edición.</span><span class="sxs-lookup"><span data-stu-id="32788-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="32788-167">Para quitar una entrada, selecciónela y haga clic en **quitar** ![icono](../../media/ITPro-EAC-DeleteIcon.png)quitar.</span><span class="sxs-lookup"><span data-stu-id="32788-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="32788-168">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="32788-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="32788-169">**Haga lo siguiente**: seleccione **agregar destinatarios** \> **en el cuadro CCO**.</span><span class="sxs-lookup"><span data-stu-id="32788-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="32788-170">En el cuadro de diálogo que aparece, busque y seleccione los destinatarios que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="32788-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="32788-171">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="32788-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="32788-172">Puede realizar selecciones adicionales para auditar la regla, probarla, activar la regla durante un período de tiempo específico y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="32788-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="32788-173">Se recomienda probar la regla antes de aplicarla.</span><span class="sxs-lookup"><span data-stu-id="32788-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="32788-174">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="32788-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="32788-175">Usar PowerShell para crear una regla de flujo de correo para recibir copias de mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="32788-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="32788-176">En este ejemplo se crea una nueva regla de flujo de correo denominada BCC mensajes enviados a Microsoft que busca mensajes de correo electrónico que se notifican a Microsoft mediante los métodos descritos en este tema y agrega los usuarios laura@contoso.com y julia@contoso.com como destinatarios CCO.</span><span class="sxs-lookup"><span data-stu-id="32788-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="32788-177">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="32788-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="32788-178">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="32788-178">How do you know this worked?</span></span>

<span data-ttu-id="32788-179">Para comprobar que ha configurado una regla de flujo de correo para recibir copias de mensajes enviados, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="32788-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="32788-180">En el EAC, vaya a **Mail flow** \> **reglas** \> de flujo de correo Seleccione \> la regla haga clic](../../media/ITPro-EAC-EditIcon.png)en **Editar** ![icono de edición y Compruebe la configuración.</span><span class="sxs-lookup"><span data-stu-id="32788-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="32788-181">En PowerShell, ejecute el siguiente comando para comprobar la configuración:</span><span class="sxs-lookup"><span data-stu-id="32788-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="32788-182">Envíe mensajes de prueba a una de las direcciones de correo electrónico de informes y compruebe los resultados.</span><span class="sxs-lookup"><span data-stu-id="32788-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
