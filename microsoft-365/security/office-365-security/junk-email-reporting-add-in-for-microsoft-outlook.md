---
title: Instalar y usar el complemento de notificación de correo no deseado para Microsoft Outlook
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo instalar y usar el complemento de notificación de correo no deseado de Microsoft para informar a Microsoft de mensajes de correo no deseado, de correo no deseado o de suplantación de identidad.
ms.openlocfilehash: e39fb2f4ecba806c2d26d989fbbe6ddec137adc1
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033952"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook-in-office-365"></a><span data-ttu-id="a18b8-103">Instalar y usar el complemento de notificación de correo no deseado para Microsoft Outlook en Office 365</span><span class="sxs-lookup"><span data-stu-id="a18b8-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="a18b8-104">Si no usa actualmente el complemento de notificación de correo electrónico no deseado, recomendamos el [complemento de mensajes de informe en](enable-the-report-message-add-in.md) su lugar.</span><span class="sxs-lookup"><span data-stu-id="a18b8-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span>

<span data-ttu-id="a18b8-105">El complemento de notificación de correo no deseado para Microsoft Outlook permite a los usuarios enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico incorrecto permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a18b8-105">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span> <span data-ttu-id="a18b8-106">Si su organización no usa EOP, el envío de informes de correo no deseado no afectará al filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a18b8-106">If your organization doesn't use EOP, your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="a18b8-107">En este tema se explica cómo instalar y usar el complemento de notificación de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a18b8-107">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a18b8-108">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="a18b8-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a18b8-109">Para instalar el complemento de notificación de correo no deseado, consulte la sección [instalar el complemento de notificación de correo no deseado](#install-the-junk-email-reporting-add-in) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="a18b8-109">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="a18b8-110">El complemento de notificación de correo no deseado funciona con las siguientes versiones de Outlook:</span><span class="sxs-lookup"><span data-stu-id="a18b8-110">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="a18b8-111">Outlook 2013 o posterior</span><span class="sxs-lookup"><span data-stu-id="a18b8-111">Outlook 2013 or later</span></span>
  - <span data-ttu-id="a18b8-112">Outlook incluido con Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="a18b8-112">Outlook included with Office 365 ProPlus</span></span>

- <span data-ttu-id="a18b8-113">Para obtener más información acerca de los informes de mensajes a Microsoft, vea [Informe de mensajes y archivos a Microsoft en Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="a18b8-113">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="a18b8-114">Usar el complemento de notificación de correo no deseado para notificar mensajes de correo no deseado y suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="a18b8-114">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="a18b8-115">Para los mensajes de la bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo electrónico no deseado, use cualquiera de los métodos siguientes para notificar mensajes de correo no deseado y suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="a18b8-115">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="a18b8-116">Seleccione el mensaje o abra el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a18b8-116">Select the message or open the message.</span></span> <span data-ttu-id="a18b8-117">En la pestaña **Inicio** o **mensaje** de la cinta de opciones, haga clic en **correo no deseado**y, a continuación, seleccione **informar como correo no deseado** o **notificar como suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-117">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Informar del correo electrónico no deseado o de suplantación de identidad en la cinta](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="a18b8-119">Haga clic con el botón derecho en el mensaje, seleccione **correo no deseado**y, a continuación, seleccione **informar como correo no deseado** o **notificar como phishing**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-119">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Informar del correo electrónico no deseado o de suplantación de identidad del clic](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="a18b8-121">Seleccione varios mensajes, haga clic con el botón derecho y, a continuación, seleccione **notificar como correo no deseado** o **notificar como phishing**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-121">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Informar sobre varios mensajes de correo electrónico no deseado o de suplantación de clic](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="a18b8-123">En el cuadro de diálogo que aparece, lea la información y haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-123">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="a18b8-124">Si cambia de opinión, haga clic en **no informar**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-124">If you change your mind, click **Don't Report**.</span></span>

   ![Informar como cuadro de diálogo de correo no deseado](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Cuadro de diálogo Notificar como phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="a18b8-p104">Los mensajes seleccionados se envían a Microsoft para su análisis y se mueven a la carpeta de correo no deseado. Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="a18b8-p104">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="a18b8-129">Use el complemento de notificación de correo no deseado para informar de mensajes de suplantación de identidad y de correo no deseado de la carpeta correo no deseado</span><span class="sxs-lookup"><span data-stu-id="a18b8-129">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="a18b8-130">En la carpeta correo electrónico no deseado, use cualquiera de los métodos siguientes para notificar falsos positivos de correo no deseado o mensajes de suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="a18b8-130">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="a18b8-131">Seleccione el mensaje o abra el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a18b8-131">Select the message or open the message.</span></span> <span data-ttu-id="a18b8-132">En la pestaña **Inicio** o **mensaje** de la cinta de opciones, haga clic en **correo deseado**y, a continuación, seleccione **informar como correo no deseado** o **notificar como suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-132">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Informar de correo no deseado o de suplantación de identidad en la cinta de la carpeta correo electrónico no deseado](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="a18b8-134">Haga clic con el botón derecho en el mensaje, haga clic en **correo**no deseado y seleccione **notificar como correo no deseado** o **informar como suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-134">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Informar de correo electrónico no deseado o de suplantación de identidad al hacer clic con el botón derecho en la carpeta correo no deseado](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="a18b8-136">Seleccione varios mensajes, haga clic con el botón secundario y, a continuación, seleccione **notificar como correo no deseado** o **informar como suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-136">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Informe de varios mensajes de correo electrónico no deseado o de suplantación del clic derecho en la carpeta correo electrónico no deseado](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="a18b8-138">En el cuadro de diálogo que aparece, lea la información y haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-138">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="a18b8-139">Si cambia de opinión, haga clic en **no informar**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-139">If you change your mind, click **Don't Report**.</span></span>

   ![Cuadro de diálogo informar como correo deseado](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Cuadro de diálogo Notificar como phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="a18b8-p107">Los mensajes seleccionados se envían a Microsoft para su análisis y se mueven a la carpeta de correo no deseado. Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="a18b8-p107">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="a18b8-144">Instalar el complemento de notificación de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="a18b8-144">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="a18b8-145">Debe tener privilegios de administrador en el equipo en el que vaya a instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="a18b8-145">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="a18b8-146">Vaya a <https://www.microsoft.com/download/details.aspx?id=18275> y descargue el archivo. msi adecuado para su versión de Office en una ubicación que sea fácil de encontrar:</span><span class="sxs-lookup"><span data-stu-id="a18b8-146">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="a18b8-147">**32 bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="a18b8-147">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="a18b8-148">**64 bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="a18b8-148">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="a18b8-149">Para Outlook 2013 o versiones posteriores, el único requisito previo es Microsoft .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="a18b8-149">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="a18b8-150">En Windows 10, no se instala .NET Framework 2,0 desde una descarga.</span><span class="sxs-lookup"><span data-stu-id="a18b8-150">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="a18b8-151">Instalar el complemento de notificación de correo no deseado mediante el Asistente para instalación</span><span class="sxs-lookup"><span data-stu-id="a18b8-151">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="a18b8-152">En el equipo, cierre Outlook.</span><span class="sxs-lookup"><span data-stu-id="a18b8-152">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="a18b8-153">En Windows 10, compruebe que .NET Framework 2,0 está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a18b8-153">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="a18b8-154">Para obtener instrucciones, vea [Habilitar .NET Framework 3,5 en el panel de control](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="a18b8-154">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="a18b8-155">Busque el archivo. msi que ha descargado y haga doble clic en él.</span><span class="sxs-lookup"><span data-stu-id="a18b8-155">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="a18b8-156">En la página de **bienvenida a la instalación del complemento de notificación de correo no deseado de Microsoft**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-156">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="a18b8-157">Revise el contrato de licencia, haga clic en **acepto los términos del contrato de licencia** si está de acuerdo con los términos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-157">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="a18b8-158">Cuando el asistente se haya completado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-158">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="a18b8-159">Inicie Outlook.</span><span class="sxs-lookup"><span data-stu-id="a18b8-159">Start Outlook.</span></span>

<span data-ttu-id="a18b8-p110">Busque el botón **Correo no deseado** en la cinta de Outlook. Ahora podrá notificar mensajes de correo no deseado a Microsoft seleccionando los mensajes de correo no deseado en la Bandeja de entrada y haciendo clic en el botón de **Informar de correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-p110">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="a18b8-p111">Elija la flecha abajo que aparece junto a **Correo no deseado** para ver más opciones, como **Notificar como suplantación de identidad (phishing)** si desea informar a Microsoft sobre correos de suplantación de identidad (phishing). En la carpeta de correo no deseado, también puede seleccionar **Notificar como correo deseado** si un correo electrónico se ha identificado incorrectamente como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a18b8-p111">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="a18b8-164">Instalar el complemento de notificación de correo no deseado en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="a18b8-164">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="a18b8-165">En el equipo, cierre Outlook.</span><span class="sxs-lookup"><span data-stu-id="a18b8-165">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="a18b8-166">En Windows 10, instale .NET Framework 2,0 mediante la ejecución del siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a18b8-166">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="a18b8-167">Para instalar el complemento sin interacción del usuario, abra un símbolo del sistema y use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a18b8-167">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="a18b8-168">`MaxMessageSelection`especifica el número máximo de mensajes que puede seleccionar para un único envío.</span><span class="sxs-lookup"><span data-stu-id="a18b8-168">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="a18b8-169">Los valores válidos son de 1 a 50.</span><span class="sxs-lookup"><span data-stu-id="a18b8-169">Valid values are from 1 to 50.</span></span> <span data-ttu-id="a18b8-170">El valor predeterminado es 15.</span><span class="sxs-lookup"><span data-stu-id="a18b8-170">The default value is 15.</span></span>

   - <span data-ttu-id="a18b8-171">`BccEmailAddress`especifica los destinatarios de CCO adicionales que recibirán una copia de todos los envíos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a18b8-171">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="a18b8-172">El valor predeterminado está en blanco (ninguno de los destinatarios de CCO adicionales).</span><span class="sxs-lookup"><span data-stu-id="a18b8-172">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="a18b8-173">En este ejemplo se instala la versión de 64 bits del complemento desde la ruta de acceso especificada con la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a18b8-173">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="a18b8-174">En este ejemplo se instala la versión de 32 bits del complemento desde la ruta de acceso especificada con la siguiente configuración adicional:</span><span class="sxs-lookup"><span data-stu-id="a18b8-174">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="a18b8-175">Se pueden seleccionar hasta 20 mensajes en un único envío.</span><span class="sxs-lookup"><span data-stu-id="a18b8-175">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="a18b8-176">junkreports@contoso.com y hollyd@treyresearch.net reciben copias CCO de todos los envíos.</span><span class="sxs-lookup"><span data-stu-id="a18b8-176">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a18b8-177">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="a18b8-177">How do you know this worked?</span></span>

<span data-ttu-id="a18b8-178">Para comprobar que ha instalado correctamente el complemento de notificación de correo no deseado, siga estos pasos en Outlook:</span><span class="sxs-lookup"><span data-stu-id="a18b8-178">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="a18b8-179">Seleccione el mensaje o abra el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a18b8-179">Select the message or open the message.</span></span> <span data-ttu-id="a18b8-180">En la pestaña **Inicio** o **mensaje** de la cinta de opciones, haga clic en **correo no deseado**y compruebe que están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a18b8-180">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="a18b8-181">**Informar como correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="a18b8-181">**Report as Junk**</span></span>
  - <span data-ttu-id="a18b8-182">**Informar como suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="a18b8-182">**Report as Phishing**</span></span>
  - <span data-ttu-id="a18b8-183">**Opciones de informes no deseados**</span><span class="sxs-lookup"><span data-stu-id="a18b8-183">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="a18b8-184">**Informar sobre la ayuda en línea de correo**</span><span class="sxs-lookup"><span data-stu-id="a18b8-184">**Report Junk Online Help**</span></span>

  ![Informar del correo electrónico no deseado o de suplantación de identidad en la cinta](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="a18b8-186">Haga clic con el botón derecho en el mensaje, seleccione **correo no deseado**y compruebe que están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a18b8-186">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="a18b8-187">**Informar como correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="a18b8-187">**Report as Junk**</span></span>
  - <span data-ttu-id="a18b8-188">**Informar como suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="a18b8-188">**Report as Phishing**</span></span>
  - <span data-ttu-id="a18b8-189">**Opciones de informes no deseados**</span><span class="sxs-lookup"><span data-stu-id="a18b8-189">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="a18b8-190">**Informar sobre la ayuda en línea de correo**</span><span class="sxs-lookup"><span data-stu-id="a18b8-190">**Report Junk Online Help**</span></span>

  ![Informar del correo electrónico no deseado o de suplantación de identidad del clic](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="a18b8-192">Seleccione varios mensajes, haga clic con el botón secundario y compruebe que están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a18b8-192">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="a18b8-193">**Informar como correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="a18b8-193">**Report as Junk**</span></span>
  - <span data-ttu-id="a18b8-194">**Informar como suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="a18b8-194">**Report as Phishing**</span></span>

  ![Informar sobre varios mensajes de correo electrónico no deseado o de suplantación de clic](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="a18b8-196">Realice las acciones anteriores de la carpeta **correo electrónico no** deseado y compruebe que las opciones anteriores de informes no **deseado** ya **no son correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-196">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Informar de correo no deseado o de suplantación de identidad en la cinta de la carpeta correo electrónico no deseado](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Informar de correo electrónico no deseado o de suplantación de identidad al hacer clic con el botón derecho en la carpeta correo no deseado](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Informe de varios mensajes de correo electrónico no deseado o de suplantación del clic derecho en la carpeta correo electrónico no deseado](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="a18b8-200">Desinstalar el complemento de notificación de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="a18b8-200">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="a18b8-201">Después de cerrar Outlook, use cualquiera de los siguientes procedimientos para desinstalar el complemento de notificación de correo no deseado:</span><span class="sxs-lookup"><span data-stu-id="a18b8-201">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="a18b8-202">**Panel de control**: Presione la tecla Windows + R. En el cuadro de diálogo **Ejecutar** que se `control appwiz.cpl` abre, escriba y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-202">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="a18b8-203">Busque y seleccione el **complemento de notificación de correo no deseado de Microsoft** en la lista y, a continuación, haga clic en **desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-203">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="a18b8-204">**Paquete de Windows Installer**: busque o descargue el archivo. msi correspondiente y haga doble clic en él.</span><span class="sxs-lookup"><span data-stu-id="a18b8-204">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="a18b8-205">**32 bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="a18b8-205">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="a18b8-206">**64 bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="a18b8-206">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="a18b8-207">En el cuadro de diálogo que aparece, seleccione **quitar el complemento de notificación de correo no deseado de Microsoft para Outlook** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a18b8-207">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="a18b8-208">**Modo silencioso**: busque o descargue el archivo. msi correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a18b8-208">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="a18b8-209">En una ventana del símbolo del sistema \<,\> Reemplace PathToFile por la ubicación del archivo. msi y ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="a18b8-209">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="a18b8-210">**32 bits**:</span><span class="sxs-lookup"><span data-stu-id="a18b8-210">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="a18b8-211">**64 bits**:</span><span class="sxs-lookup"><span data-stu-id="a18b8-211">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="a18b8-212">Al abrir Outlook después de la desinstalación, las opciones de informes de suplantación de identidad (correo no deseado) no deseado deberían desaparecer.</span><span class="sxs-lookup"><span data-stu-id="a18b8-212">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="a18b8-213">Solución de problemas del complemento de notificación de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="a18b8-213">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="a18b8-214">En ocasiones, es posible que experimente problemas con Outlook después de agregar el complemento de notificación de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a18b8-214">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="a18b8-215">En esta sección se describen los problemas que puede encontrar, junto con sugerencias para resolver estos problemas.</span><span class="sxs-lookup"><span data-stu-id="a18b8-215">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="a18b8-216">Solución de problemas para usuarios</span><span class="sxs-lookup"><span data-stu-id="a18b8-216">Troubleshooting for users</span></span>

<span data-ttu-id="a18b8-217">Experimenta uno o varios de los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="a18b8-217">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="a18b8-218">Al hacer clic en **Informar de correo electrónico no deseado**, no ocurre ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="a18b8-218">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="a18b8-219">Outlook deja de responder después de seleccionar un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a18b8-219">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="a18b8-220">El correo no deseado notificado no se puede entregar debido a una respuesta de "no se puede entregar".</span><span class="sxs-lookup"><span data-stu-id="a18b8-220">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="a18b8-221">Para solucionar este problema, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a18b8-221">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="a18b8-222">Cierre y reinicie Outlook.</span><span class="sxs-lookup"><span data-stu-id="a18b8-222">Close and restart Outlook.</span></span>
2. <span data-ttu-id="a18b8-223">Cree y envíe un mensaje de prueba y compruebe que el destinatario recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a18b8-223">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="a18b8-224">Si el problema continúa, póngase en contacto con el administrador.</span><span class="sxs-lookup"><span data-stu-id="a18b8-224">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="a18b8-225">Para otros métodos que puede usar para enviar mensajes a Microsoft, consulte [informes de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="a18b8-225">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="a18b8-226">Solución de problemas para administradores</span><span class="sxs-lookup"><span data-stu-id="a18b8-226">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="a18b8-227">Problema: aparece continuamente un mensaje de error que pide a los usuarios que se pongan en contacto con el administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="a18b8-227">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="a18b8-228">Compruebe o establezca la `LoggingLevel` clave del registro en el valor "verbose":</span><span class="sxs-lookup"><span data-stu-id="a18b8-228">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="a18b8-229">**Outlook de 32 bits en Windows de 32 bits**:</span><span class="sxs-lookup"><span data-stu-id="a18b8-229">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="a18b8-230">**Outlook de 32 bits en Windows de 64 bits**:</span><span class="sxs-lookup"><span data-stu-id="a18b8-230">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="a18b8-231">**Outlook de 64**bits:</span><span class="sxs-lookup"><span data-stu-id="a18b8-231">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="a18b8-232">Reinicie Outlook y pida a los usuarios que informen de nuevo cuando vean el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="a18b8-232">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="a18b8-233">Recopile la información de registro de la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="a18b8-233">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="a18b8-234">Póngase en contacto con el soporte técnico de Protección en línea de Exchange y proporcione la información de registro.</span><span class="sxs-lookup"><span data-stu-id="a18b8-234">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="a18b8-235">Problema: los usuarios seleccionaron no recibir un mensaje de confirmación cuando notifican mensajes y ahora quieren que vuelvan a aparecer la pregunta</span><span class="sxs-lookup"><span data-stu-id="a18b8-235">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="a18b8-236">Cree la `ConfirmReportJunk`clave del registro wih el valor "true":</span><span class="sxs-lookup"><span data-stu-id="a18b8-236">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="a18b8-237">Reinicie Outlook.</span><span class="sxs-lookup"><span data-stu-id="a18b8-237">Restart Outlook.</span></span>
