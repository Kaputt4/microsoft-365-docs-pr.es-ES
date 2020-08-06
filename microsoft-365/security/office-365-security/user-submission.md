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
ms.openlocfilehash: ae6088a0eab214b4e160b85a278e1160c2845ed9
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577131"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="d6039-103">Especificar un buzón para envíos de usuarios de correo no deseado y mensajes de suplantación de identidad en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d6039-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="d6039-104">En Microsoft 365 organizaciones con buzones de correo de Exchange Online, puede especificar un buzón para recibir mensajes que los usuarios notifican como malintencionados o no malintencionados.</span><span class="sxs-lookup"><span data-stu-id="d6039-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="d6039-105">Cuando los usuarios envían mensajes con las distintas opciones de informes, puede usar este buzón de correo para interceptar mensajes (enviar solo al buzón personalizado) o recibir copias de los mensajes (enviar al buzón de correo personalizado y Microsoft).</span><span class="sxs-lookup"><span data-stu-id="d6039-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="d6039-106">Esta característica funciona con las siguientes opciones de informe de mensajes:</span><span class="sxs-lookup"><span data-stu-id="d6039-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="d6039-107">El complemento de mensajes de informe</span><span class="sxs-lookup"><span data-stu-id="d6039-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="d6039-108">[Informes integrados en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conocido como Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="d6039-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="d6039-109">Informes integrados en Outlook para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="d6039-109">Built-in reporting in Outlook for iOS and Android</span></span>

  > [!NOTE]
  > <span data-ttu-id="d6039-110">Si se ha [deshabilitado la generación de informes en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), la habilitación de los envíos de usuario aquí invalidará esa configuración y permitirá a los usuarios volver a notificar los mensajes en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="d6039-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="d6039-111">También puede configurar herramientas de informes de mensajes de terceros para reenviar mensajes al buzón de correo que especifique.</span><span class="sxs-lookup"><span data-stu-id="d6039-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="d6039-112">La entrega de mensajes de usuario que se han informado a un buzón de correo personalizado, en lugar de hacerlo directamente a Microsoft, permite a los administradores informar de forma selectiva y selectiva a Microsoft mediante el [envío de administración](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="d6039-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d6039-113">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="d6039-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d6039-114">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d6039-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d6039-115">Para ir directamente a la página **envíos de usuarios** , use <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="d6039-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="d6039-116">Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:</span><span class="sxs-lookup"><span data-stu-id="d6039-116">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="d6039-117">Para modificar la configuración de los envíos de usuario, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="d6039-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d6039-118">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d6039-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d6039-119">**Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d6039-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="d6039-120">Para obtener acceso de solo lectura a los envíos de usuario, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="d6039-120">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d6039-121">**Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d6039-121">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d6039-122">**Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d6039-122">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="d6039-123">Usar el centro de seguridad & cumplimiento para configurar el buzón de envíos de usuarios</span><span class="sxs-lookup"><span data-stu-id="d6039-123">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="d6039-124">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **envíos de usuarios**de la Directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d6039-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="d6039-125">En la página **envíos de usuarios** que aparece, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d6039-125">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="d6039-126">a.</span><span class="sxs-lookup"><span data-stu-id="d6039-126">a.</span></span> <span data-ttu-id="d6039-127">**Habilitar la característica de mensaje de informe para Outlook (recomendado)**: Seleccione esta opción si usa el complemento de mensajes de informe o los informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d6039-127">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="d6039-128">**Personalizar el mensaje de confirmación del usuario final**: haga clic en este vínculo.</span><span class="sxs-lookup"><span data-stu-id="d6039-128">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="d6039-129">En el control flotante **personalizar mensaje de confirmación** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d6039-129">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="d6039-130">**Antes de enviar**: en los cuadros de mensaje **título** y **confirmación** , escriba el texto descriptivo que verán los usuarios antes de que informen de un mensaje mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="d6039-130">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="d6039-131">Puede usar la variable% Type% para incluir el tipo de envío (correo no deseado, correo deseado, phish, etc.).</span><span class="sxs-lookup"><span data-stu-id="d6039-131">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="d6039-132">Como se indicó, si selecciona una opción que envía los mensajes notificados a Microsoft, también se agregará el siguiente texto a la notificación:</span><span class="sxs-lookup"><span data-stu-id="d6039-132">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="d6039-133">El correo electrónico se enviará tal cual a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="d6039-133">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="d6039-134">Algunos mensajes de correo electrónico pueden contener información personal o confidencial.</span><span class="sxs-lookup"><span data-stu-id="d6039-134">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="d6039-135">**Después del envío**: haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="d6039-135">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="d6039-136">En los cuadros de texto **título** y **confirmación** , escriba el texto descriptivo que los usuarios verán después de que informen de un mensaje mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="d6039-136">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="d6039-137">Puede usar la variable% Type% para incluir el tipo de envío.</span><span class="sxs-lookup"><span data-stu-id="d6039-137">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="d6039-138">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6039-138">When you're finished, click **Save**.</span></span> <span data-ttu-id="d6039-139">Para borrar estos valores, haga clic en **restaurar** de nuevo en la página **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="d6039-139">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="d6039-140">**Enviar los mensajes notificados a**: realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="d6039-140">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="d6039-141">**Microsoft (recomendado)**: no se usa el buzón de envíos de usuario (todos los mensajes que se han informado van a Microsoft).</span><span class="sxs-lookup"><span data-stu-id="d6039-141">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="d6039-142">**Microsoft y un buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="d6039-142">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="d6039-143">No se permiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="d6039-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="d6039-144">Los envíos de usuarios Irán a Microsoft para su análisis y al buzón de correo personalizado para que los analice el administrador o el equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d6039-144">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="d6039-145">**Buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="d6039-145">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="d6039-146">No se permiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="d6039-146">Distribution groups are not allowed.</span></span> <span data-ttu-id="d6039-147">Use esta opción si desea que el mensaje solo vaya a un administrador o al equipo de operaciones de seguridad para su análisis en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="d6039-147">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="d6039-148">Los mensajes no pasarán a Microsoft a menos que el administrador los reenvíe por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="d6039-148">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d6039-149">Las organizaciones gubernamentales de Estados Unidos (GCC, GCC-H y DoD) solo pueden configurar el **buzón personalizado**.</span><span class="sxs-lookup"><span data-stu-id="d6039-149">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="d6039-150">Las otras dos opciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="d6039-150">The other two options are disabled.</span></span> 

      <span data-ttu-id="d6039-151">Cuando haya terminado, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d6039-151">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="d6039-152">Si ha [deshabilitado la notificación de correo no deseado en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) con directivas de buzón de Outlook en la web, pero configura cualquiera de las opciones anteriores para notificar mensajes a Microsoft, los usuarios podrán informar de los mensajes a Microsoft en Outlook en la web mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="d6039-152">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="d6039-153">**Deshabilitar la característica de mensaje de informe para Outlook**: Seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento de mensajes de informe o la creación de informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d6039-153">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="d6039-154">Seleccione **usar este buzón personalizado para recibir envíos notificados por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="d6039-154">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="d6039-155">En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente que ya esté en Office 365.</span><span class="sxs-lookup"><span data-stu-id="d6039-155">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="d6039-156">Debe ser un buzón existente en Exchange online que pueda recibir correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d6039-156">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="d6039-157">Cuando haya terminado, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d6039-157">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="d6039-158">Formato de envío de mensajes</span><span class="sxs-lookup"><span data-stu-id="d6039-158">Message submission format</span></span>

<span data-ttu-id="d6039-159">Los mensajes que se envían a los buzones personalizados deben seguir un formato de correo de envío específico.</span><span class="sxs-lookup"><span data-stu-id="d6039-159">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="d6039-160">El asunto (título de sobre) del envío debe tener este formato:</span><span class="sxs-lookup"><span data-stu-id="d6039-160">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="d6039-161">se SafetyAPIAction es uno de los siguientes valores enteros:</span><span class="sxs-lookup"><span data-stu-id="d6039-161">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="d6039-162">1: correo no deseado</span><span class="sxs-lookup"><span data-stu-id="d6039-162">1: Junk</span></span>
- <span data-ttu-id="d6039-163">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="d6039-163">2: NotJunk</span></span>
- <span data-ttu-id="d6039-164">3: phish</span><span class="sxs-lookup"><span data-stu-id="d6039-164">3: Phish</span></span>

<span data-ttu-id="d6039-165">En el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d6039-165">In the following example:</span></span>

- <span data-ttu-id="d6039-166">El mensaje se está notificando como phish.</span><span class="sxs-lookup"><span data-stu-id="d6039-166">The message is being reported as Phish.</span></span>
- <span data-ttu-id="d6039-167">El identificador de mensaje de red es 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="d6039-167">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="d6039-168">La IP del remitente es 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="d6039-168">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="d6039-169">La dirección de es test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d6039-169">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="d6039-170">La línea de asunto del mensaje es "test phish Submission"</span><span class="sxs-lookup"><span data-stu-id="d6039-170">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="d6039-171">Los mensajes que no siguen este formato no se mostrarán correctamente en el portal de envíos.</span><span class="sxs-lookup"><span data-stu-id="d6039-171">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
