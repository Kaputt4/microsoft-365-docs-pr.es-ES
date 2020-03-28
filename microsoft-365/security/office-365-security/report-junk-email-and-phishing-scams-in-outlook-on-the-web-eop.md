---
title: 'Informar de correo electrónico no deseado y estafas de suplantación de identidad (phishing) en Outlook en la Web '
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
description: Office 365 los usuarios con buzones de Exchange online pueden usar Outlook en la web (Outlook Web App) para enviar mensajes de correo no deseado, mensajes de correo no deseado y suplantación de identidad a Microsoft para su análisis.
ms.openlocfilehash: c6aba9a701b23be4bbbe508825a55c6438461928
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033709"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="ad5a5-103">Informar del correo electrónico no deseado y de suplantación de identidad en Outlook en la web en Office 365</span><span class="sxs-lookup"><span data-stu-id="ad5a5-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="ad5a5-104">Si es un cliente de Office 365 con buzones de correo de Exchange Online, puede usar las opciones de informes integradas en Outlook en la web (anteriormente conocido como Outlook Web App) para enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico incorrecto permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-104">If you're an Office 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ad5a5-105">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="ad5a5-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ad5a5-106">Si es administrador de una organización de Office 365 con buzones de correo de Exchange Online, le recomendamos que use el portal de envíos del centro de seguridad & cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-106">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="ad5a5-107">Para obtener más información, vea [usar el envío de administración para enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="ad5a5-108">Los administradores pueden deshabilitar o habilitar la capacidad de los usuarios para notificar mensajes a Microsoft en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="ad5a5-109">Para obtener más información, vea la sección [deshabilitar o habilitar la notificación de correo electrónico no deseado en Outlook en la web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) , más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="ad5a5-110">Para obtener más información acerca de los informes de mensajes a Microsoft, vea [Informe de mensajes y archivos a Microsoft en Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="ad5a5-111">Notificar mensajes de correo no deseado y suplantación de identidad en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="ad5a5-111">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="ad5a5-112">Para los mensajes de la bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo electrónico no deseado, use cualquiera de los métodos siguientes para notificar mensajes de correo no deseado y suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="ad5a5-112">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="ad5a5-113">Seleccione el mensaje, haga clic en **correo no deseado** en la barra de herramientas y seleccione **correo no deseado** o **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-113">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Informar del correo electrónico no deseado o de suplantación de identidad en la cinta](../../media/owa-report-junk.png)

   - <span data-ttu-id="ad5a5-115">Seleccione uno o más mensajes, haga clic con el botón secundario y, a continuación, seleccione **marcar como correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-115">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="ad5a5-116">En el cuadro de diálogo que aparece, haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-116">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="ad5a5-117">Si cambia de opinión, haga clic en **no informar**.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-117">If you change your mind, click **Don't Report**.</span></span>

   ![Informar como cuadro de diálogo de correo no deseado](../../media/owa-report-as-junk-dialog.png)

   ![Cuadro de diálogo Notificar como phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="ad5a5-120">Los mensajes seleccionados se enviarán a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-120">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="ad5a5-121">Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-121">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="ad5a5-122">Informar de mensajes de suplantación de identidad y correo no deseado de la carpeta correo electrónico no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="ad5a5-122">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="ad5a5-123">En la carpeta correo electrónico no deseado, use cualquiera de los métodos siguientes para informar sobre falsos positivos o mensajes de suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="ad5a5-123">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="ad5a5-124">Seleccione el mensaje, haga clic en **correo deseado** en la barra de herramientas y, a continuación, seleccione **correo deseado** o **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-124">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Informar del correo electrónico no deseado o de suplantación de identidad en la cinta](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="ad5a5-126">Seleccione uno o más mensajes, haga clic con el botón secundario y, a continuación, seleccione **marcar como correo deseado**.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-126">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="ad5a5-127">En el cuadro de diálogo que aparece, lea la información y haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-127">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="ad5a5-128">Si cambia de opinión, haga clic en **no informar**.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-128">If you change your mind, click **Don't Report**.</span></span>

   ![Cuadro de diálogo informar como correo deseado](../../media/owa-report-as-not-junk-dialog.png)

   ![Cuadro de diálogo Notificar como phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="ad5a5-131">Los mensajes seleccionados se enviarán a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-131">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="ad5a5-132">Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-132">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="ad5a5-133">Deshabilitar o habilitar la notificación de correo no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="ad5a5-133">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="ad5a5-134">De forma predeterminada, los usuarios pueden notificar falsos positivos de correo no deseado, falsos negativos y mensajes de suplantación de identidad a Microsoft para su análisis en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-134">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="ad5a5-135">Los administradores pueden usar directivas de buzones de correo de Outlook en la web en Exchange Online para deshabilitar o habilitar esta capacidad, pero solo en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-135">Admins can use Outlook on the web mailbox policies in Exchange Online to disable or enable this ability, but only in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="ad5a5-136">Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ad5a5-137">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="ad5a5-138">En concreto, necesitará los roles de **directivas de destinatarios** o **destinatarios de correo** en Exchange Online, que se asignan a los grupos de roles administración de la **organización** y **Administración de destinatarios** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-138">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="ad5a5-139">Para obtener más información acerca de los grupos de roles de Exchange Online, vea [Modify role Groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-139">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="ad5a5-140">Cada organización tiene una directiva predeterminada denominada OwaMailboxPolicy-default, pero puede crear directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-140">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="ad5a5-141">Las directivas personalizadas se aplican a los usuarios en el ámbito antes de la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-141">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="ad5a5-142">Para obtener más información acerca de las directivas de buzón de correo de Outlook en la web, vea [directivas de buzones de correo de Outlook en la web en Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-142">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

1. <span data-ttu-id="ad5a5-143">Para buscar las directivas de buzón de correo de Outlook en la Web existentes y el estado de la notificación de correo no deseado, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="ad5a5-143">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="ad5a5-144">Para deshabilitar o habilitar la notificación de correo no deseado en Outlook en la web, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="ad5a5-144">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="ad5a5-145">En este ejemplo se deshabilita la notificación de correo no deseado en la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-145">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="ad5a5-146">En este ejemplo se ha habilitado la notificación de correo no deseado en la directiva personalizada denominada administradores de contoso.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-146">This example enabled junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="ad5a5-147">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) y [set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-147">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ad5a5-148">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="ad5a5-148">How do you know this worked?</span></span>

<span data-ttu-id="ad5a5-149">Para comprobar que ha habilitado o deshabilitado correctamente la notificación de correo no deseado en Outlook en la web, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ad5a5-149">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="ad5a5-150">En Exchange Online PowerShell, ejecute el siguiente comando y compruebe el valor de la propiedad **ReportJunkEmailEnabled** :</span><span class="sxs-lookup"><span data-stu-id="ad5a5-150">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="ad5a5-151">Abra el buzón de un usuario afectado en Outlook en la web y compruebe que las opciones para informar de correo electrónico no deseado, correo deseado y mensajes de suplantación de identidad estén disponibles o no disponibles.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-151">Open an affected user's mailbox in Outlook on the web, and verify the options to report junk, not junk, and phishing messages are available or not available.</span></span> <span data-ttu-id="ad5a5-152">Tenga en cuenta que el usuario todavía puede marcar los mensajes como correo no deseado, suplantación de identidad y correo electrónico no deseado, pero el usuario no puede informar de ellos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-152">Note that the user can still mark messages as junk, phishing, and not junk, but the user can't report them to Microsoft.</span></span>
