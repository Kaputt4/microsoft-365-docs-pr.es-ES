---
title: RReport correo electrónico no deseado y de suplantación de identidad en Outlook en la web
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre las opciones integradas de correo no deseado, correo no deseado y suplantación de identidad en Outlook en la web (Outlook Web App) en Exchange Online y cómo deshabilitar estas opciones de informes para los usuarios.
ms.openlocfilehash: 1ec226259ccb3dac9a01ee8d4c5fc635c0fc5702
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206483"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="3ca1c-103">Informar del correo electrónico no deseado y de suplantación de identidad en Outlook en la web en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3ca1c-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

<span data-ttu-id="3ca1c-104">En Microsoft 365 organizaciones con buzones de correo en Exchange Online, puede usar las opciones de informes integradas en Outlook en la web (anteriormente conocido como Outlook Web App) para enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (se permite correo erróneo) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="3ca1c-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3ca1c-105">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="3ca1c-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3ca1c-106">Si es administrador de una organización con buzones de correo de Exchange Online, le recomendamos que use el portal de envíos del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="3ca1c-107">Para obtener más información, vea [usar el envío de administración para enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="3ca1c-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="3ca1c-108">Los administradores pueden deshabilitar o habilitar la capacidad de los usuarios para notificar mensajes a Microsoft en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="3ca1c-109">Para obtener más información, vea la sección [deshabilitar o habilitar la notificación de correo electrónico no deseado en Outlook en la web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) , más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="3ca1c-110">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón de correo que especifique.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="3ca1c-111">Para obtener más información, vea [especificar un buzón para los envíos de usuarios de correo no deseado y mensajes de suplantación de identidad en Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="3ca1c-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="3ca1c-112">Para obtener más información acerca de los informes de mensajes a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3ca1c-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="3ca1c-113">Notificar mensajes de correo no deseado y suplantación de identidad en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="3ca1c-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="3ca1c-114">Para los mensajes de la bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo electrónico no deseado, use cualquiera de los métodos siguientes para notificar mensajes de correo no deseado y suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="3ca1c-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="3ca1c-115">Seleccione el mensaje, haga clic en **correo no deseado** en la barra de herramientas y seleccione **correo no deseado** o **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Informar del correo electrónico no deseado o de suplantación de identidad en la cinta](../../media/owa-report-junk.png)

   - <span data-ttu-id="3ca1c-117">Seleccione uno o más mensajes, haga clic con el botón secundario y, a continuación, seleccione **marcar como correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="3ca1c-118">En el cuadro de diálogo que aparece, haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="3ca1c-119">Si cambia de opinión, haga clic en **no informar**.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-119">If you change your mind, click **Don't Report**.</span></span>

   ![Informar como cuadro de diálogo de correo no deseado](../../media/owa-report-as-junk-dialog.png)

   ![Cuadro de diálogo Notificar como phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="3ca1c-122">Los mensajes seleccionados se enviarán a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-122">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="3ca1c-123">Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-123">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="3ca1c-124">Informar de mensajes de suplantación de identidad y correo no deseado de la carpeta correo electrónico no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="3ca1c-124">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="3ca1c-125">En la carpeta correo electrónico no deseado, use cualquiera de los métodos siguientes para informar sobre falsos positivos o mensajes de suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="3ca1c-125">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="3ca1c-126">Seleccione el mensaje, haga clic en **correo deseado** en la barra de herramientas y, a continuación, seleccione **correo deseado** o **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-126">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Informar del correo electrónico no deseado o de suplantación de identidad en la cinta](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="3ca1c-128">Seleccione uno o más mensajes, haga clic con el botón secundario y, a continuación, seleccione **marcar como correo deseado**.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-128">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="3ca1c-129">En el cuadro de diálogo que aparece, lea la información y haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-129">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="3ca1c-130">Si cambia de opinión, haga clic en **no informar**.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-130">If you change your mind, click **Don't Report**.</span></span>

   ![Cuadro de diálogo informar como correo deseado](../../media/owa-report-as-not-junk-dialog.png)

   ![Cuadro de diálogo Notificar como phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="3ca1c-133">Los mensajes seleccionados se enviarán a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-133">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="3ca1c-134">Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-134">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="3ca1c-135">Deshabilitar o habilitar la notificación de correo no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="3ca1c-135">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="3ca1c-136">De forma predeterminada, los usuarios pueden notificar falsos positivos de correo no deseado, falsos negativos y mensajes de suplantación de identidad a Microsoft para su análisis en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-136">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="3ca1c-137">Los administradores pueden configurar las directivas de buzones de correo de Outlook en la web en Exchange Online PowerShell para evitar que los usuarios informen falsos positivos de correo no deseado y correo no deseado falsos negativos para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-137">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="3ca1c-138">No se puede deshabilitar la capacidad de los usuarios para notificar mensajes de suplantación de identidad a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-138">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3ca1c-139">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="3ca1c-139">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3ca1c-140">Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3ca1c-140">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="3ca1c-141">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-141">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="3ca1c-142">En concreto, necesitará los roles de **directivas de destinatarios** o **destinatarios de correo** en Exchange Online, que se asignan a los grupos de roles administración de la **organización** y **Administración de destinatarios** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-142">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="3ca1c-143">Para obtener más información acerca de los grupos de roles de Exchange Online, vea [Modify role Groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="3ca1c-143">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="3ca1c-144">Cada organización tiene una directiva predeterminada denominada OwaMailboxPolicy-default, pero puede crear directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-144">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="3ca1c-145">Las directivas personalizadas se aplican a los usuarios en el ámbito antes de la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-145">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="3ca1c-146">Para obtener más información acerca de las directivas de buzón de correo de Outlook en la web, vea [directivas de buzones de correo de Outlook en la web en Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="3ca1c-146">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="3ca1c-147">La deshabilitación de la notificación de correo no deseado no elimina la capacidad de marcar un mensaje como correo no deseado en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-147">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="3ca1c-148">Al seleccionar un mensaje en la carpeta correo electrónico no deseado y al hacer clic en **correo deseado** y \> **no deseado** , el mensaje se vuelve a mover a la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-148">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="3ca1c-149">Al seleccionar un mensaje en cualquier otra carpeta de correo electrónico y **al hacer clic en correo no** \> **deseado** todavía se mueve el mensaje a la carpeta correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-149">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="3ca1c-150">Lo que ya no está disponible es la opción de informar al mensaje a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-150">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="3ca1c-151">Usar Exchange Online PowerShell para deshabilitar o habilitar la notificación de correo electrónico no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="3ca1c-151">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="3ca1c-152">Para buscar las directivas de buzón de correo de Outlook en la Web existentes y el estado de la notificación de correo no deseado, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3ca1c-152">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="3ca1c-153">Para deshabilitar o habilitar la notificación de correo no deseado en Outlook en la web, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3ca1c-153">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="3ca1c-154">En este ejemplo se deshabilita la notificación de correo no deseado en la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-154">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="3ca1c-155">En este ejemplo se habilita la notificación de correo no deseado en la directiva personalizada denominada administradores de contoso.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-155">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="3ca1c-156">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) y [set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="3ca1c-156">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="3ca1c-157">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="3ca1c-157">How do you know this worked?</span></span>

<span data-ttu-id="3ca1c-158">Para comprobar que ha habilitado o deshabilitado correctamente la notificación de correo no deseado en Outlook en la web, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3ca1c-158">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="3ca1c-159">En Exchange Online PowerShell, ejecute el siguiente comando y compruebe el valor de la propiedad **ReportJunkEmailEnabled** :</span><span class="sxs-lookup"><span data-stu-id="3ca1c-159">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="3ca1c-160">Abrir el buzón de un usuario afectado en Outlook en la web, seleccione un mensaje en la bandeja de entrada **, haga clic en correo** no deseado \> **Junk** y compruebe que la pregunta para informar del mensaje a Microsoft es o no se muestra.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ca1c-160">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="3ca1c-161">Abrir el buzón de un usuario afectado en Outlook en la web, seleccione un mensaje en la carpeta de correo no deseado **, haga clic en correo no deseado** \> **Junk** y compruebe que la pregunta para informar del mensaje a Microsoft es o no se muestra.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ca1c-161">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="3ca1c-162"><sup>\*</sup>Los usuarios pueden ocultar el mensaje para informar del mensaje mientras están notificando el mensaje.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-162"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="3ca1c-163">Para comprobar esta configuración en Outlook en la web:</span><span class="sxs-lookup"><span data-stu-id="3ca1c-163">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="3ca1c-164">Haga clic en **configuración** ![ Outlook en el icono de configuración del Web ](../../media/owa-settings-icon.png) \> **ver todo** el \> **correo electrónico no deseado**de configuración de Outlook.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-164">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="3ca1c-165">En la sección **informes** , compruebe el valor: **preguntarme antes de enviar un informe**.</span><span class="sxs-lookup"><span data-stu-id="3ca1c-165">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Configuración de informes de correo no deseado de Outlook en la web](../../media/owa-junk-email-reporting-options.png)
