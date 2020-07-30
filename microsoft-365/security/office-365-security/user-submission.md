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
ms.openlocfilehash: 0be1a4efa04d3e7a7968880b2a1cca108fdd34f9
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503096"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="56718-103">Especificar un buzón para envíos de usuarios de correo no deseado y mensajes de suplantación de identidad en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="56718-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="56718-104">En Microsoft 365 organizaciones con buzones de correo de Exchange Online, puede especificar un buzón para recibir mensajes que los usuarios notifican como malintencionados o no malintencionados.</span><span class="sxs-lookup"><span data-stu-id="56718-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="56718-105">Cuando los usuarios envían mensajes con las distintas opciones de informes, puede usar este buzón de correo para interceptar mensajes (enviar solo al buzón personalizado) o recibir copias de los mensajes (enviar al buzón de correo personalizado y Microsoft).</span><span class="sxs-lookup"><span data-stu-id="56718-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="56718-106">Esta característica funciona con las siguientes opciones de informe de mensajes:</span><span class="sxs-lookup"><span data-stu-id="56718-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="56718-107">El complemento de mensajes de informe</span><span class="sxs-lookup"><span data-stu-id="56718-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="56718-108">[Informes integrados en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conocido como Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="56718-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="56718-109">Informes integrados en Outlook para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="56718-109">Built-in reporting in Outlook for iOS and Android</span></span>

  > [!NOTE]
  > <span data-ttu-id="56718-110">Si se ha [deshabilitado la generación de informes en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), la habilitación de los envíos de usuario aquí invalidará esa configuración y permitirá a los usuarios volver a notificar los mensajes en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="56718-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="56718-111">También puede configurar herramientas de informes de mensajes de terceros para reenviar mensajes al buzón de correo que especifique.</span><span class="sxs-lookup"><span data-stu-id="56718-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="56718-112">La entrega de mensajes de usuario que se han informado a un buzón de correo personalizado, en lugar de hacerlo directamente a Microsoft, permite a los administradores informar de forma selectiva y selectiva a Microsoft mediante el [envío de administración](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="56718-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="56718-113">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="56718-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="56718-114">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="56718-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="56718-115">Para ir directamente a la página **envíos de usuarios** , use <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="56718-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="56718-116">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="56718-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="56718-117">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="56718-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="56718-118">Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:</span><span class="sxs-lookup"><span data-stu-id="56718-118">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="56718-119">Para modificar la configuración de los envíos de usuario, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="56718-119">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="56718-120">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="56718-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="56718-121">**Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="56718-121">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="56718-122">Para obtener acceso de solo lectura a los envíos de usuario, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="56718-122">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="56718-123">**Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="56718-123">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="56718-124">**Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="56718-124">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="56718-125">Usar el centro de seguridad & cumplimiento para configurar el buzón de envíos de usuarios</span><span class="sxs-lookup"><span data-stu-id="56718-125">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="56718-126">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **envíos de usuarios**de la Directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="56718-126">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="56718-127">En la página **envíos de usuarios** que aparece, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="56718-127">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="56718-128">a.</span><span class="sxs-lookup"><span data-stu-id="56718-128">a.</span></span> <span data-ttu-id="56718-129">**Habilitar la característica de mensaje de informe para Outlook (recomendado)**: Seleccione esta opción si usa el complemento de mensajes de informe o los informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="56718-129">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="56718-130">**Personalizar el mensaje de confirmación del usuario final**: haga clic en este vínculo.</span><span class="sxs-lookup"><span data-stu-id="56718-130">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="56718-131">En el control flotante **personalizar mensaje de confirmación** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="56718-131">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="56718-132">**Antes de enviar**: en los cuadros de mensaje **título** y **confirmación** , escriba el texto descriptivo que verán los usuarios antes de que informen de un mensaje mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="56718-132">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="56718-133">Puede usar la variable% Type% para incluir el tipo de envío (correo no deseado, correo deseado, phish, etc.).</span><span class="sxs-lookup"><span data-stu-id="56718-133">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="56718-134">Como se indicó, si selecciona una opción que envía los mensajes notificados a Microsoft, también se agregará el siguiente texto a la notificación:</span><span class="sxs-lookup"><span data-stu-id="56718-134">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="56718-135">El correo electrónico se enviará tal cual a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="56718-135">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="56718-136">Algunos mensajes de correo electrónico pueden contener información personal o confidencial.</span><span class="sxs-lookup"><span data-stu-id="56718-136">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="56718-137">**Después del envío**: haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="56718-137">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="56718-138">En los cuadros de texto **título** y **confirmación** , escriba el texto descriptivo que los usuarios verán después de que informen de un mensaje mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="56718-138">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="56718-139">Puede usar la variable% Type% para incluir el tipo de envío.</span><span class="sxs-lookup"><span data-stu-id="56718-139">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="56718-140">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="56718-140">When you're finished, click **Save**.</span></span> <span data-ttu-id="56718-141">Para borrar estos valores, haga clic en **restaurar** de nuevo en la página **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="56718-141">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="56718-142">**Enviar los mensajes notificados a**: realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="56718-142">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="56718-143">**Microsoft (recomendado)**: no se usa el buzón de envíos de usuario (todos los mensajes que se han informado van a Microsoft).</span><span class="sxs-lookup"><span data-stu-id="56718-143">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="56718-144">**Microsoft y un buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="56718-144">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="56718-145">No se permiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="56718-145">Distribution groups are not allowed.</span></span> <span data-ttu-id="56718-146">Los envíos de usuarios Irán a Microsoft para su análisis y al buzón de correo personalizado para que los analice el administrador o el equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="56718-146">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="56718-147">**Buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="56718-147">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="56718-148">No se permiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="56718-148">Distribution groups are not allowed.</span></span> <span data-ttu-id="56718-149">Use esta opción si desea que el mensaje solo vaya a un administrador o al equipo de operaciones de seguridad para su análisis en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="56718-149">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="56718-150">Los mensajes no pasarán a Microsoft a menos que el administrador los reenvíe por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="56718-150">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="56718-151">Las organizaciones gubernamentales de Estados Unidos (GCC, GCC-H y DoD) solo pueden configurar el **buzón personalizado**.</span><span class="sxs-lookup"><span data-stu-id="56718-151">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="56718-152">Las otras dos opciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="56718-152">The other two options are disabled.</span></span> 

      <span data-ttu-id="56718-153">Cuando haya terminado, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="56718-153">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="56718-154">Si ha [deshabilitado la notificación de correo no deseado en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) con directivas de buzón de Outlook en la web, pero configura cualquiera de las opciones anteriores para notificar mensajes a Microsoft, los usuarios podrán informar de los mensajes a Microsoft en Outlook en la web mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="56718-154">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="56718-155">**Deshabilitar la característica de mensaje de informe para Outlook**: Seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento de mensajes de informe o la creación de informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="56718-155">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="56718-156">Seleccione **usar este buzón personalizado para recibir envíos notificados por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="56718-156">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="56718-157">En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente que ya esté en Office 365.</span><span class="sxs-lookup"><span data-stu-id="56718-157">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="56718-158">Debe ser un buzón existente en Exchange online que pueda recibir correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="56718-158">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="56718-159">Cuando haya terminado, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="56718-159">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="56718-160">Formato de envío de mensajes</span><span class="sxs-lookup"><span data-stu-id="56718-160">Message submission format</span></span>

<span data-ttu-id="56718-161">Los mensajes que se envían a los buzones personalizados deben seguir un formato de correo de envío específico.</span><span class="sxs-lookup"><span data-stu-id="56718-161">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="56718-162">El asunto (título de sobre) del envío debe tener este formato:</span><span class="sxs-lookup"><span data-stu-id="56718-162">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="56718-163">se SafetyAPIAction es uno de los siguientes valores enteros:</span><span class="sxs-lookup"><span data-stu-id="56718-163">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="56718-164">1: correo no deseado</span><span class="sxs-lookup"><span data-stu-id="56718-164">1: Junk</span></span>
- <span data-ttu-id="56718-165">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="56718-165">2: NotJunk</span></span>
- <span data-ttu-id="56718-166">3: phish</span><span class="sxs-lookup"><span data-stu-id="56718-166">3: Phish</span></span>

<span data-ttu-id="56718-167">En el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="56718-167">In the following example:</span></span>

- <span data-ttu-id="56718-168">El mensaje se está notificando como phish.</span><span class="sxs-lookup"><span data-stu-id="56718-168">The message is being reported as Phish.</span></span>
- <span data-ttu-id="56718-169">El identificador de mensaje de red es 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="56718-169">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="56718-170">La IP del remitente es 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="56718-170">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="56718-171">La dirección de es test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="56718-171">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="56718-172">La línea de asunto del mensaje es "test phish Submission"</span><span class="sxs-lookup"><span data-stu-id="56718-172">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="56718-173">Los mensajes que no siguen este formato no se mostrarán correctamente en el portal de envíos.</span><span class="sxs-lookup"><span data-stu-id="56718-173">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
