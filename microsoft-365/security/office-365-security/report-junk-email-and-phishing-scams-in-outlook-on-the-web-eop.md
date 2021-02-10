---
title: Notificar correo electrónico no deseado y de suplantación de identidad en Outlook en la Web
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre las opciones integradas de notificación de correo electrónico no deseado, correo no deseado y suplantación de identidad en Outlook en la Web (Outlook Web App) en Exchange Online y cómo deshabilitar estas opciones de informes para los usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd22e7f08ae420adf2923d4da731494a0f6af3e3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166740"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="80b6e-103">Notificar correo electrónico no deseado y de suplantación de identidad en Outlook en la Web en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="80b6e-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="80b6e-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="80b6e-104">**Applies to**</span></span>
- [<span data-ttu-id="80b6e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="80b6e-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="80b6e-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="80b6e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="80b6e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80b6e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="80b6e-108">En organizaciones de Microsoft 365 con buzones en Exchange Online, puede usar las opciones de informes integradas en Outlook en la Web (anteriormente conocida como Outlook Web App) para enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico no deseado permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="80b6e-108">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="80b6e-109">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="80b6e-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="80b6e-110">Si es administrador de una organización con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="80b6e-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="80b6e-111">Para obtener más información, vea Usar envío de administrador para enviar correos sospechosos de correo no [deseado, phishing, direcciones URL y archivos a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="80b6e-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="80b6e-112">Los administradores pueden deshabilitar o habilitar la posibilidad de que los usuarios informen de mensajes a Microsoft en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="80b6e-112">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="80b6e-113">Para obtener más información, vea la sección Deshabilitar o habilitar los informes de correo no deseado en [Outlook en la Web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="80b6e-113">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="80b6e-114">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique.</span><span class="sxs-lookup"><span data-stu-id="80b6e-114">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="80b6e-115">Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="80b6e-115">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="80b6e-116">Para obtener más información acerca de la notificación de mensajes a Microsoft, vea Notificar mensajes [y archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="80b6e-116">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="80b6e-117">Notificar mensajes de correo no deseado y de suplantación de identidad en Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="80b6e-117">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="80b6e-118">Para los mensajes de la Bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo no deseado, use uno de los siguientes métodos para informar de mensajes de correo no deseado y de suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="80b6e-118">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="80b6e-119">Seleccione el mensaje, haga clic en **Correo** no deseado en la barra de herramientas y, a continuación, seleccione **Correo** no deseado o **Suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="80b6e-119">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Notificar correo electrónico no deseado o de suplantación de identidad desde la cinta de opciones](../../media/owa-report-junk.png)

   - <span data-ttu-id="80b6e-121">Seleccione uno o más mensajes, haga clic con el botón secundario y, a continuación, **seleccione Marcar como correo no deseado.**</span><span class="sxs-lookup"><span data-stu-id="80b6e-121">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="80b6e-122">En el cuadro de diálogo que aparece, haga clic en **Informe.**</span><span class="sxs-lookup"><span data-stu-id="80b6e-122">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="80b6e-123">Si cambia de opinión, haga clic **en No informar.**</span><span class="sxs-lookup"><span data-stu-id="80b6e-123">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="80b6e-124">Correo no deseado</span><span class="sxs-lookup"><span data-stu-id="80b6e-124">Junk</span></span>|<span data-ttu-id="80b6e-125">Suplantación de identidad (phishing)</span><span class="sxs-lookup"><span data-stu-id="80b6e-125">Phishing</span></span>|
   |:---:|:---:|
   |![Cuadro de diálogo Informar como correo no deseado](../../media/owa-report-as-junk-dialog.png)|![Cuadro de diálogo Informar como suplantación de identidad (phishing)](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="80b6e-128">Los mensajes seleccionados se enviarán a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="80b6e-128">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="80b6e-129">Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="80b6e-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="80b6e-130">Notificar mensajes de correo no deseado y de suplantación de identidad de la carpeta correo no deseado en Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="80b6e-130">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="80b6e-131">En la carpeta Correo no deseado, use uno de los métodos siguientes para notificar falsos positivos de correo no deseado o mensajes de suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="80b6e-131">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="80b6e-132">Seleccione el mensaje, haga clic **en No** deseado en la barra de herramientas y, a continuación, seleccione Correo no deseado **o** **Suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="80b6e-132">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Informar de correo electrónico no deseado o no de suplantación de identidad desde la cinta de opciones](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="80b6e-134">Seleccione uno o más mensajes, haga clic con el botón secundario y, a continuación, **seleccione Marcar como correo no deseado.**</span><span class="sxs-lookup"><span data-stu-id="80b6e-134">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="80b6e-135">En el cuadro de diálogo que aparece, lea la información y haga clic en **Informe.**</span><span class="sxs-lookup"><span data-stu-id="80b6e-135">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="80b6e-136">Si cambia de opinión, haga clic **en No informar.**</span><span class="sxs-lookup"><span data-stu-id="80b6e-136">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="80b6e-137">Correo no deseado</span><span class="sxs-lookup"><span data-stu-id="80b6e-137">Not Junk</span></span>|<span data-ttu-id="80b6e-138">Suplantación de identidad (phishing)</span><span class="sxs-lookup"><span data-stu-id="80b6e-138">Phishing</span></span>|
   |:---:|:---:|
   |![Cuadro de diálogo Informar como correo no deseado](../../media/owa-report-as-not-junk-dialog.png)|![Cuadro de diálogo Informar como suplantación de identidad (phishing)](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="80b6e-141">Los mensajes seleccionados se enviarán a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="80b6e-141">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="80b6e-142">Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="80b6e-142">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="80b6e-143">Deshabilitar o habilitar los informes de correo no deseado en Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="80b6e-143">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="80b6e-144">De forma predeterminada, los usuarios pueden informar a Microsoft de falsos positivos de correo no deseado, falsos negativos y mensajes de suplantación de identidad para su análisis en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="80b6e-144">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="80b6e-145">Los administradores pueden configurar directivas de buzón de Outlook en la web en Exchange Online PowerShell para evitar que los usuarios informen a Microsoft de falsos positivos y falsos negativos de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="80b6e-145">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="80b6e-146">No puede deshabilitar la capacidad de los usuarios de notificar mensajes de suplantación de identidad a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80b6e-146">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="80b6e-147">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="80b6e-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="80b6e-148">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="80b6e-148">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="80b6e-149">Deberá tener asignados permisos en Exchange Online antes de poder realizar los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="80b6e-149">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="80b6e-150">Específicamente, necesita las  funciones **Directivas de** destinatarios o  Destinatarios de  correo, que se asignan de forma predeterminada a los grupos de roles Administración de la organización y Administración de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="80b6e-150">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="80b6e-151">Para obtener más información acerca de los grupos de roles en Exchange Online, consulte [Permisos en Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) y Modificar grupos de roles en Exchange [Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="80b6e-151">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="80b6e-152">Cada organización tiene una directiva predeterminada denominada OwaMailboxPolicy-Default, pero puede crear directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="80b6e-152">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="80b6e-153">Las directivas personalizadas se aplican a los usuarios con ámbito antes de la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="80b6e-153">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="80b6e-154">Para obtener más información acerca de las directivas de buzón de Outlook en la Web, vea Las directivas de buzón de Outlook en la [Web en Exchange Online.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="80b6e-154">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="80b6e-155">Deshabilitar los informes de correo no deseado no elimina la capacidad de marcar un mensaje como correo no deseado o no deseado en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="80b6e-155">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="80b6e-156">Al seleccionar un mensaje en la  carpeta de correo no deseado y hacer clic en No deseado, el mensaje se mueve de nuevo a \>  la Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="80b6e-156">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="80b6e-157">Al seleccionar un mensaje en cualquier  otra carpeta de correo electrónico y hacer clic en Correo no deseado, el mensaje se mueve a la carpeta \>  Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="80b6e-157">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="80b6e-158">Lo que ya no está disponible es la opción de notificar el mensaje a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80b6e-158">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="80b6e-159">Usar Exchange Online PowerShell para deshabilitar o habilitar los informes de correo no deseado en Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="80b6e-159">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="80b6e-160">Para encontrar las directivas de buzón de Outlook en la Web existentes y el estado de los informes de correo no deseado, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="80b6e-160">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="80b6e-161">Para deshabilitar o habilitar los informes de correo no deseado en Outlook en la Web, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="80b6e-161">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="80b6e-162">En este ejemplo se deshabilitan los informes de correo no deseado en la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="80b6e-162">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="80b6e-163">En este ejemplo se habilitan los informes de correo no deseado en la directiva personalizada denominada Administradores de Contoso.</span><span class="sxs-lookup"><span data-stu-id="80b6e-163">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="80b6e-164">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) y [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="80b6e-164">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="80b6e-165">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="80b6e-165">How do you know this worked?</span></span>

<span data-ttu-id="80b6e-166">Para comprobar que ha habilitado o deshabilitado correctamente los informes de correo no deseado en Outlook en la Web, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="80b6e-166">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="80b6e-167">En Exchange Online PowerShell, ejecute el siguiente comando y compruebe el valor de la propiedad **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="80b6e-167">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="80b6e-168">Abra el buzón de un usuario afectado en Outlook en la  Web, seleccione un mensaje en la Bandeja de entrada, haga clic en Correo no deseado y compruebe que la solicitud para notificar el mensaje a Microsoft está o no \>  se muestra.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="80b6e-168">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="80b6e-169">Abra el buzón de correo de un usuario afectado en Outlook en  la Web, seleccione un mensaje en la carpeta Correo no deseado, haga clic en Correo no deseado y compruebe que la solicitud para notificar el mensaje a Microsoft se muestra o \>  no.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="80b6e-169">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="80b6e-170"><sup>\*</sup> Los usuarios pueden ocultar la solicitud para informar del mensaje mientras siguen informando del mensaje.</span><span class="sxs-lookup"><span data-stu-id="80b6e-170"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="80b6e-171">Para comprobar esta configuración en Outlook en la Web:</span><span class="sxs-lookup"><span data-stu-id="80b6e-171">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="80b6e-172">Haga clic **en el** icono Configuración de Outlook en la web ![ Ver toda la configuración de ](../../media/owa-settings-icon.png) \> **Outlook** \> **correo electrónico no deseado.**</span><span class="sxs-lookup"><span data-stu-id="80b6e-172">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="80b6e-173">En la **sección Informes,** compruebe el valor: **Pregúnteme antes de enviar un informe.**</span><span class="sxs-lookup"><span data-stu-id="80b6e-173">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Configuración de informes de correo no deseado de Outlook en la web](../../media/owa-junk-email-reporting-options.png)
