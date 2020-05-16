---
title: Especificar un buzón para envíos de usuarios de mensajes de correo no deseado y suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar un buzón para recopilar correo electrónico no deseado y suplantación de identidad que son notificados por los usuarios.
ms.openlocfilehash: 6aa343b337139c4d81f35f78a227634d3b6a8781
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262528"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="8b6e2-103">Especificar un buzón para envíos de usuarios de correo no deseado y mensajes de suplantación de identidad en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8b6e2-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="8b6e2-104">En Microsoft 365 organizaciones con buzones de correo de Exchange Online, puede especificar un buzón para recibir mensajes que los usuarios notifican como malintencionados o no malintencionados.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="8b6e2-105">Cuando los usuarios envían mensajes con las distintas opciones de informes, puede usar este buzón de correo para interceptar mensajes (enviar solo al buzón personalizado) o recibir copias de los mensajes (enviar al buzón de correo personalizado y Microsoft).</span><span class="sxs-lookup"><span data-stu-id="8b6e2-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="8b6e2-106">Esta característica funciona con las siguientes opciones de informe de mensajes:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="8b6e2-107">El complemento de mensajes de informe</span><span class="sxs-lookup"><span data-stu-id="8b6e2-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="8b6e2-108">[Informes integrados en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conocido como Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="8b6e2-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="8b6e2-109">Si se ha [deshabilitado la generación de informes en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), la habilitación de los envíos de usuario aquí invalidará esa configuración y permitirá a los usuarios volver a notificar los mensajes en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="8b6e2-110">También puede configurar herramientas de informes de mensajes de terceros para reenviar mensajes al buzón de correo que especifique.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="8b6e2-111">La entrega de mensajes de usuario que se han informado a un buzón de correo personalizado, en lugar de hacerlo directamente a Microsoft, permite a los administradores informar de forma selectiva y selectiva a Microsoft mediante el [envío de administración](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="8b6e2-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8b6e2-112">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="8b6e2-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8b6e2-113">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8b6e2-114">Para ir directamente a la página **envíos de usuarios** , use <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="8b6e2-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="8b6e2-115">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8b6e2-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8b6e2-116">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="8b6e2-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8b6e2-117">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="8b6e2-118">Para configurar el buzón de correo para envíos de usuarios, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="8b6e2-118">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="8b6e2-119">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8b6e2-119">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="8b6e2-120">Usar el centro de seguridad & cumplimiento para configurar el buzón de envíos de usuarios</span><span class="sxs-lookup"><span data-stu-id="8b6e2-120">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="8b6e2-121">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **envíos de usuarios**de la Directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-121">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="8b6e2-122">En la página **envíos de usuarios** que aparece, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-122">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="8b6e2-123">a.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-123">a.</span></span> <span data-ttu-id="8b6e2-124">**Habilitar la característica de mensaje de informe para Outlook (recomendado)**: Seleccione esta opción si usa el complemento de mensajes de informe o los informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-124">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="8b6e2-125">**Personalizar el mensaje de confirmación del usuario final**: haga clic en este vínculo.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-125">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="8b6e2-126">En el control flotante **personalizar mensaje de confirmación** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-126">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="8b6e2-127">**Antes de enviar**: en los cuadros de mensaje **título** y **confirmación** , escriba el texto descriptivo que verán los usuarios antes de que informen de un mensaje mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-127">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="8b6e2-128">Puede usar la variable% Type% para incluir el tipo de envío (correo no deseado, correo deseado, phish, etc.).</span><span class="sxs-lookup"><span data-stu-id="8b6e2-128">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="8b6e2-129">Como se indicó, si selecciona una opción que envía los mensajes notificados a Microsoft, también se agregará el siguiente texto a la notificación:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-129">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="8b6e2-130">El correo electrónico se enviará tal cual a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-130">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="8b6e2-131">Algunos mensajes de correo electrónico pueden contener información personal o confidencial.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-131">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="8b6e2-132">**Después del envío**: haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="8b6e2-132">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="8b6e2-133">En los cuadros de texto **título** y **confirmación** , escriba el texto descriptivo que los usuarios verán después de que informen de un mensaje mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-133">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="8b6e2-134">Puede usar la variable% Type% para incluir el tipo de envío.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-134">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="8b6e2-135">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-135">When you're finished, click **Save**.</span></span> <span data-ttu-id="8b6e2-136">Para borrar estos valores, haga clic en **restaurar** de nuevo en la página **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="8b6e2-136">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="8b6e2-137">**Enviar los mensajes notificados a**: realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-137">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="8b6e2-138">**Microsoft (recomendado)**: no se usa el buzón de envíos de usuario (todos los mensajes que se han informado van a Microsoft).</span><span class="sxs-lookup"><span data-stu-id="8b6e2-138">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="8b6e2-139">**Microsoft y un buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-139">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="8b6e2-140">No se permiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-140">Distribution groups are not allowed.</span></span> <span data-ttu-id="8b6e2-141">Los envíos de usuarios Irán a Microsoft para su análisis y al buzón de correo personalizado para que los analice el administrador o el equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-141">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="8b6e2-142">**Buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-142">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="8b6e2-143">No se permiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="8b6e2-144">Use esta opción si desea que el mensaje solo vaya al administrador o al equipo de operaciones de seguridad para su análisis en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-144">Use this option if you want the message to only go to the admin or security operations team for analysis first.</span></span> <span data-ttu-id="8b6e2-145">Los mensajes no pasarán a Microsoft a menos que el administrador lo reenvíe.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-145">Messages will not go to Microsoft unless the admin forwards it.</span></span>

        <span data-ttu-id="8b6e2-146">Cuando haya terminado, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-146">When you're finished, click **Confirm**.</span></span>

        ![Enviar mensajes notificados a Microsoft y a un buzón personalizado](../../media/user-submission-enable-outlook-report-message.png)

     > [!CAUTION]
     > <span data-ttu-id="8b6e2-148">Si ha [deshabilitado la notificación de correo no deseado en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) con directivas de buzón de Outlook en la web, pero configura cualquiera de las opciones anteriores para notificar mensajes a Microsoft, los usuarios podrán informar de los mensajes a Microsoft en Outlook en la web mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-148">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="8b6e2-149">**Deshabilitar la característica de mensaje de informe para Outlook**: Seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento de mensajes de informe o la creación de informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-149">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="8b6e2-150">Seleccione **usar este buzón personalizado para recibir envíos notificados por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-150">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="8b6e2-151">En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente que ya esté en Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-151">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="8b6e2-152">Debe ser un buzón existente en Exchange online que pueda recibir correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-152">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="8b6e2-153">Cuando haya terminado, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-153">When you're finished, click **Confirm**.</span></span>

      ![Enviar mensajes de informes a un buzón personalizado con herramientas de terceros](../../media/user-submission-disable-outlook-report-message.png)
     
## <a name="message-submission-format"></a><span data-ttu-id="8b6e2-155">Formato de envío de mensajes</span><span class="sxs-lookup"><span data-stu-id="8b6e2-155">Message submission format</span></span>

<span data-ttu-id="8b6e2-156">Los mensajes que se envían a los buzones personalizados deben seguir un formato de correo de envío específico.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-156">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="8b6e2-157">El asunto (título de sobre) del envío debe tener este formato:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-157">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`{(int)safetyApiAction}|{networkId}|{senderIp}|{fromAddress}|({subject.Substring(0, Math.Min(subjectLen, subject.Length))})`

<span data-ttu-id="8b6e2-158">fueron SafetyApiAction es:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-158">were SafetyApiAction is:</span></span>

- <span data-ttu-id="8b6e2-159">Correo no deseado = 1</span><span class="sxs-lookup"><span data-stu-id="8b6e2-159">Junk = 1</span></span>
- <span data-ttu-id="8b6e2-160">NotJunk = 2</span><span class="sxs-lookup"><span data-stu-id="8b6e2-160">NotJunk = 2</span></span>
- <span data-ttu-id="8b6e2-161">Phish = 3</span><span class="sxs-lookup"><span data-stu-id="8b6e2-161">Phish = 3</span></span>

<span data-ttu-id="8b6e2-162">En el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-162">In the following example:</span></span>

- <span data-ttu-id="8b6e2-163">El mensaje se está notificando como phish.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-163">The message is being reported as Phish.</span></span>
- <span data-ttu-id="8b6e2-164">El identificador de mensaje de red es 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-164">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="8b6e2-165">La IP del remitente es 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-165">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="8b6e2-166">La dirección de es test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-166">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="8b6e2-167">El asunto del correo electrónico del mensaje es "probar el envío de phish"</span><span class="sxs-lookup"><span data-stu-id="8b6e2-167">The message's email subject is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="8b6e2-168">Los mensajes que no siguen este formato no se mostrarán correctamente en el portal de envíos.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-168">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
