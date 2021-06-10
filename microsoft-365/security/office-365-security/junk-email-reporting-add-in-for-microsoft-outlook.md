---
title: Instalar y usar el complemento De informes de correo no deseado para Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo instalar y usar el complemento De informes de correo no deseado de Microsoft para notificar mensajes de correo no deseado, correo no deseado y suplantación de identidad a Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e120ceec355ffc135e00e13a89a0f29085946a3b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205469"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="f5b5b-103">Instalar y usar el complemento De informes de correo no deseado para Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="f5b5b-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f5b5b-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-104">**Applies to**</span></span>
- [<span data-ttu-id="f5b5b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f5b5b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f5b5b-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f5b5b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f5b5b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5b5b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="f5b5b-108">Si actualmente no usa el complemento De informes de correo electrónico no deseado, se recomienda el complemento Report [Message](enable-the-report-message-add-in.md) o el complemento [Report Phishing.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f5b5b-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="f5b5b-109">Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f5b5b-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="f5b5b-110">El complemento de informes de correo no deseado para Microsoft Outlook permite a los usuarios enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico no deseado permitido) y mensajes de suplantación de identidad a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="f5b5b-111">Si su organización no usa Exchange Online Protection (por ejemplo, servicios de correo electrónico o Exchange locales distintos de Exchange Online), el envío del informe de correo no deseado no afectará al filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="f5b5b-112">En este tema se explica cómo instalar y usar el complemento De informes de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f5b5b-113">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="f5b5b-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f5b5b-114">Para instalar el complemento De informes de correo no deseado, vea la sección [Instalar](#install-the-junk-email-reporting-add-in) el complemento De informes de correo no deseado más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="f5b5b-115">El complemento De informes de correo no deseado funciona con las siguientes versiones de Outlook:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="f5b5b-116">Outlook 2013 o posterior</span><span class="sxs-lookup"><span data-stu-id="f5b5b-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="f5b5b-117">Outlook se incluye con Aplicaciones Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f5b5b-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="f5b5b-118">Para obtener más información acerca de cómo notificar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f5b5b-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="f5b5b-119">Usar el complemento De informes de correo no deseado para notificar mensajes de correo no deseado y suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="f5b5b-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="f5b5b-120">Para los mensajes de la Bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo no deseado, use cualquiera de los siguientes métodos para notificar mensajes de correo no deseado y suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="f5b5b-121">Seleccione el mensaje o abra el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-121">Select the message or open the message.</span></span> <span data-ttu-id="f5b5b-122">En la pestaña **Inicio** **o** Mensaje de la  cinta de opciones, haga clic en Correo no deseado y, a continuación, seleccione Informar como correo no deseado o Informar **como suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Notificar correo electrónico no deseado o suplantación de identidad desde la cinta de opciones](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="f5b5b-124">Haga clic con el botón secundario en  el mensaje, seleccione **Correo** no deseado y, a continuación, seleccione Informar como correo no deseado **o Informar como suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Notificar correo electrónico no deseado o suplantación de identidad desde el botón secundario](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="f5b5b-126">Seleccione varios mensajes, haga clic con el botón secundario y, a continuación, seleccione **Informar** como correo no deseado **o Informar como suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Informar de varios mensajes de correo electrónico no deseado o de suplantación de identidad desde el botón secundario](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="f5b5b-128">En el cuadro de diálogo que aparece, lea la información y haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="f5b5b-129">Si cambia de opinión, haga clic **en No informar.**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-129">If you change your mind, click **Don't Report**.</span></span>

   ![Cuadro de diálogo Informar como correo no deseado](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Cuadro de diálogo Informar como suplantación de identidad](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="f5b5b-132">Los mensajes seleccionados se enviarán a Microsoft para su análisis y:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="f5b5b-133">Se ha movido a la carpeta correo no deseado si se ha notificado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="f5b5b-134">Se elimina si se ha notificado como suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="f5b5b-135">Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="f5b5b-136">Usar el complemento De informes de correo no deseado para informar de mensajes no deseados y de suplantación de identidad desde la carpeta Correo no deseado</span><span class="sxs-lookup"><span data-stu-id="f5b5b-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="f5b5b-137">En la carpeta Correo no deseado, use cualquiera de los siguientes métodos para notificar falsos positivos de correo no deseado o mensajes de suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="f5b5b-138">Seleccione el mensaje o abra el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-138">Select the message or open the message.</span></span> <span data-ttu-id="f5b5b-139">En la pestaña **Inicio** **o Mensaje** de la cinta  de opciones, haga clic en No deseado **y,** a continuación, seleccione Informar como no deseado o Informar **como suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![No informar de correo electrónico no deseado o de suplantación de identidad desde la cinta de opciones en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="f5b5b-141">Haga clic con el botón secundario en el mensaje, haga **clic** en Correo no deseado y, a continuación, seleccione Informar como no deseado **o** **Informar como suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![No informar de correo electrónico no deseado o de suplantación de identidad desde el botón secundario en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="f5b5b-143">Seleccione varios mensajes, haga clic con el botón secundario y, a continuación, **seleccione Informar como** no deseado o Informar como **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Informar de varios mensajes de correo electrónico no deseado o de suplantación de identidad desde el botón secundario en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="f5b5b-145">En el cuadro de diálogo que aparece, lea la información y haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="f5b5b-146">Si cambia de opinión, haga clic **en No informar.**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-146">If you change your mind, click **Don't Report**.</span></span>

   ![Informe como cuadro de diálogo no deseado](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Cuadro de diálogo Informar como suplantación de identidad](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="f5b5b-149">Los mensajes seleccionados se enviarán a Microsoft para su análisis y:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="f5b5b-150">Se ha movido a la carpeta correo no deseado si se ha notificado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="f5b5b-151">Se elimina si se ha notificado como suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="f5b5b-152">Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="f5b5b-153">Instalar el complemento De informes de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="f5b5b-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="f5b5b-154">Debe tener privilegios de administrador en el equipo donde va a instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="f5b5b-155">Vaya a y descargue el archivo de .msi adecuado para su versión de Office a una ubicación que <https://www.microsoft.com/download/details.aspx?id=18275> sea fácil de encontrar:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="f5b5b-156">**32 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f5b5b-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="f5b5b-157">**64 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f5b5b-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="f5b5b-158">Para Outlook 2013 o posterior, el único requisito previo es microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="f5b5b-159">En Windows 10, no se instala el .NET Framework 2.0 desde una descarga.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="f5b5b-160">Instalar el complemento de informes de correo no deseado con el Asistente para la instalación</span><span class="sxs-lookup"><span data-stu-id="f5b5b-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="f5b5b-161">En el equipo, cierre Outlook.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="f5b5b-162">En Windows 10, compruebe que el .NET Framework 2.0 está habilitado.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="f5b5b-163">Para obtener instrucciones, vea [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="f5b5b-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="f5b5b-164">Busque el .msi que descargó y haga doble clic en él.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="f5b5b-165">En la página de **bienvenida a la instalación del complemento de notificación de correo no deseado de Microsoft**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="f5b5b-166">Revise el contrato de licencia, haga clic en **Acepto** los términos del Contrato de licencia si acepta los términos y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="f5b5b-167">Cuando el asistente se haya completado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="f5b5b-168">Inicie Outlook.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-168">Start Outlook.</span></span>

<span data-ttu-id="f5b5b-p109">Busque el botón **Correo no deseado** en la cinta de Outlook. Ahora podrá notificar mensajes de correo no deseado a Microsoft seleccionando los mensajes de correo no deseado en la Bandeja de entrada y haciendo clic en el botón de **Informar de correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="f5b5b-p110">Elija la flecha abajo que aparece junto a **Correo no deseado** para ver más opciones, como **Notificar como suplantación de identidad (phishing)** si desea informar a Microsoft sobre correos de suplantación de identidad (phishing). En la carpeta de correo no deseado, también puede seleccionar **Notificar como correo deseado** si un correo electrónico se ha identificado incorrectamente como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="f5b5b-173">Instalar el complemento de notificación de correo no deseado en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="f5b5b-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="f5b5b-174">En el equipo, cierre Outlook.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="f5b5b-175">En Windows 10, instale el .NET Framework 2.0 ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="f5b5b-176">Para instalar el complemento sin ninguna interacción del usuario, abra un símbolo del sistema y use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="f5b5b-177">`MaxMessageSelection` especifica el número máximo de mensajes que puede seleccionar para un único envío.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="f5b5b-178">Los valores válidos van del 1 al 50.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="f5b5b-179">El valor predeterminado es 15.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-179">The default value is 15.</span></span>

   - <span data-ttu-id="f5b5b-180">`BccEmailAddress` especifica destinatarios CCO adicionales que recibirán una copia de todos los envíos de usuario.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="f5b5b-181">El valor predeterminado está en blanco (no hay destinatarios CCO adicionales).</span><span class="sxs-lookup"><span data-stu-id="f5b5b-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="f5b5b-182">En este ejemplo se instala la versión de 64 bits del complemento desde la ruta de acceso especificada con la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="f5b5b-183">En este ejemplo se instala la versión de 32 bits del complemento desde la ruta de acceso especificada con la siguiente configuración adicional:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="f5b5b-184">Se pueden seleccionar hasta 20 mensajes en un solo envío.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="f5b5b-185">junkreports@contoso.com y hollyd@treyresearch.net copias CCO de todos los envíos.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f5b5b-186">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="f5b5b-186">How do you know this worked?</span></span>

<span data-ttu-id="f5b5b-187">Para comprobar que ha instalado correctamente el complemento de informes de correo no deseado, siga estos pasos en Outlook:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="f5b5b-188">Seleccione el mensaje o abra el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-188">Select the message or open the message.</span></span> <span data-ttu-id="f5b5b-189">En la **pestaña Inicio** **o Mensaje** de la cinta de opciones, haga **clic** en Correo no deseado y compruebe que están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="f5b5b-190">**Informar como correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-190">**Report as Junk**</span></span>
  - <span data-ttu-id="f5b5b-191">**Informar como suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="f5b5b-192">**Opciones de informes no deseados**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="f5b5b-193">**Report Junk Online Help**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-193">**Report Junk Online Help**</span></span>

  ![Notificar correo electrónico no deseado o suplantación de identidad desde la cinta de opciones](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="f5b5b-195">Haga clic con el botón secundario en el mensaje, seleccione **Correo** no deseado y compruebe que están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="f5b5b-196">**Informar como correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-196">**Report as Junk**</span></span>
  - <span data-ttu-id="f5b5b-197">**Informar como suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="f5b5b-198">**Opciones de informes no deseados**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="f5b5b-199">**Report Junk Online Help**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-199">**Report Junk Online Help**</span></span>

  ![Notificar correo electrónico no deseado o suplantación de identidad desde el botón secundario](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="f5b5b-201">Seleccione varios mensajes, haga clic con el botón secundario y compruebe que están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="f5b5b-202">**Informar como correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-202">**Report as Junk**</span></span>
  - <span data-ttu-id="f5b5b-203">**Informar como suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-203">**Report as Phishing**</span></span>

  ![Informar de varios mensajes de correo electrónico no deseado o de suplantación de identidad desde el botón secundario](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="f5b5b-205">Realice las acciones anteriores en la carpeta  **Correo no** deseado y compruebe que las opciones de informes de correo no deseado anteriores sean ahora **No deseado**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![No informar de correo electrónico no deseado o de suplantación de identidad desde la cinta de opciones en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![No informar de correo electrónico no deseado o de suplantación de identidad desde el botón secundario en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Informar de varios mensajes de correo electrónico no deseado o de suplantación de identidad desde el botón secundario en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="f5b5b-209">Desinstalar el complemento de notificación de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="f5b5b-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="f5b5b-210">Después de cerrar Outlook, use cualquiera de los siguientes procedimientos para desinstalar el complemento de informes de correo no deseado:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="f5b5b-211">**Panel de** control: presione Windows tecla + R. En el **cuadro de** diálogo Ejecutar que se abre, escriba `control appwiz.cpl` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="f5b5b-212">Busque y seleccione **Complemento de informes** de correo no deseado de Microsoft en la lista y, a continuación, haga clic en **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="f5b5b-213">**Windows installer:** busque o descargue el archivo .msi adecuado y haga doble clic en él.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="f5b5b-214">**32 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f5b5b-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="f5b5b-215">**64 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f5b5b-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="f5b5b-216">En el cuadro de diálogo que aparece, seleccione Quitar complemento de informes de correo no deseado de Microsoft para Outlook, a **continuación,** haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="f5b5b-217">**Modo silencioso:** busque o descargue el archivo .msi archivo.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="f5b5b-218">En una ventana del símbolo del sistema, reemplace por la ubicación del \<PathToFile\> archivo .msi y ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="f5b5b-219">**32 bits:**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="f5b5b-220">**64 bits:**</span><span class="sxs-lookup"><span data-stu-id="f5b5b-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="f5b5b-221">Cuando se abre Outlook después de la desinstalación, las opciones de informes de correo no deseado, no de correo no deseado y suplantación de identidad deben haber desaparecido.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="f5b5b-222">Solución de problemas del complemento de informes de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="f5b5b-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="f5b5b-223">En ocasiones, es posible que tenga problemas Outlook después de agregar el complemento de informes de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="f5b5b-224">En esta sección se describen los problemas que puede encontrar, junto con sugerencias para resolver estos problemas.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="f5b5b-225">Solución de problemas para usuarios</span><span class="sxs-lookup"><span data-stu-id="f5b5b-225">Troubleshooting for users</span></span>

<span data-ttu-id="f5b5b-226">Tiene uno o varios de los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="f5b5b-227">Al hacer clic en **Informar de correo electrónico no deseado**, no ocurre ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="f5b5b-228">Outlook deja de responder después de seleccionar un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="f5b5b-229">El correo no deseado notificado no se puede entregar debido a una respuesta de "no se puede entregar".</span><span class="sxs-lookup"><span data-stu-id="f5b5b-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="f5b5b-230">Para solucionar este problema, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="f5b5b-231">Cierre y reinicie Outlook.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="f5b5b-232">Cree y envíe un mensaje de prueba y compruebe que el destinatario recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="f5b5b-233">Si el problema persiste, póngase en contacto con el administrador.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="f5b5b-234">Para otros métodos que puede usar para enviar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f5b5b-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="f5b5b-235">Solución de problemas para administradores</span><span class="sxs-lookup"><span data-stu-id="f5b5b-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="f5b5b-236">Problema: aparece continuamente un mensaje de error que pide a los usuarios que se pondrán en contacto con el administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="f5b5b-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="f5b5b-237">Compruebe o establezca la clave `LoggingLevel` del Registro en el valor "Verbose":</span><span class="sxs-lookup"><span data-stu-id="f5b5b-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="f5b5b-238">**32 bits Outlook de 32 bits Windows**:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="f5b5b-239">**32 bits Outlook de 64 bits Windows**:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="f5b5b-240">**64 bits Outlook**:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="f5b5b-241">Reinicie Outlook y pida a los usuarios que informen cuando vean el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="f5b5b-242">Recopile la información de registro de la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="f5b5b-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="f5b5b-243">Póngase en contacto con el soporte técnico de Protección en línea de Exchange y proporcione la información de registro.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="f5b5b-244">Problema: los usuarios seleccionados no reciben un mensaje de confirmación cuando informan de los mensajes y ahora desean que se vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="f5b5b-245">Cree la `ConfirmReportJunk` clave del Registro con el valor "True":</span><span class="sxs-lookup"><span data-stu-id="f5b5b-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="f5b5b-246">Reinicie Outlook.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-246">Restart Outlook.</span></span>