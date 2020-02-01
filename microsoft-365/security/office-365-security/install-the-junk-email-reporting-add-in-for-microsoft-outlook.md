---
title: Instalar el complemento de notificación de correo no deseado para Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: MSFTTracyP
author: tracyp
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: En esta articleSupported LanguagesInstall el informe de correo electrónico no deseado Add-inUninstall el complemento de notificación de correo no deseado Add-inFor más información
ms.openlocfilehash: 0f7a5a3cbaddf9aef5e518db38ffb36c397cd1f0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599157"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="4edfe-103">Instalar el complemento de notificación de correo no deseado para Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="4edfe-103">Install the Junk Email Reporting Add-in for Microsoft Outlook</span></span>

<span data-ttu-id="4edfe-104">En este tema se describe cómo instalar y desinstalar el complemento de notificación de correo no deseado de Microsoft para Outlook en los equipos cliente de una organización.</span><span class="sxs-lookup"><span data-stu-id="4edfe-104">This topic describes how to install (and uninstall) the Microsoft Junk Email Reporting Add-in for Outlook on client computers in your organization.</span></span> <span data-ttu-id="4edfe-105">La versión actual del complemento (enero de 2016) incluye soporte para Outlook 2016, Outlook 2013 y Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="4edfe-105">The current version of the add-in (January 2016) includes support for Outlook 2016, Outlook 2013, and Outlook 2010.</span></span>

<span data-ttu-id="4edfe-p102">El complemento (para todos los idiomas admitidos) permite notificar el correo electrónico no deseado directamente desde la cinta de Outlook. La versión en inglés del complemento incluye opciones adicionales para notificar problemas relacionados con el correo electrónico a Microsoft, directamente desde la cinta de opciones:</span><span class="sxs-lookup"><span data-stu-id="4edfe-p102">The add-in (for all supported languages) allows you to report junk email directly from the Outlook ribbon. The English version of the add-in includes additional options for reporting email issues to Microsoft, directly from the ribbon:</span></span>

- <span data-ttu-id="4edfe-108">Notificar los correos de suplantación de identidad (phishing) recibidos</span><span class="sxs-lookup"><span data-stu-id="4edfe-108">Report phishing scam emails that you receive</span></span>

- <span data-ttu-id="4edfe-109">Notificar los correos electrónicos identificados incorrectamente como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="4edfe-109">Report email incorrectly identified as junk mail.</span></span>

## <a name="supported-languages"></a><span data-ttu-id="4edfe-110">Idiomas admitidos</span><span class="sxs-lookup"><span data-stu-id="4edfe-110">Supported Languages</span></span>
<span data-ttu-id="4edfe-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="4edfe-111"><a name="sectionSection0"> </a></span></span>

<span data-ttu-id="4edfe-112">El complemento de notificación de correo no deseado admite los siguientes idiomas:</span><span class="sxs-lookup"><span data-stu-id="4edfe-112">The Junk Email Reporting Add-in supports the following languages:</span></span>

- <span data-ttu-id="4edfe-113">chino simplificado</span><span class="sxs-lookup"><span data-stu-id="4edfe-113">Simplified Chinese</span></span>

- <span data-ttu-id="4edfe-114">chino tradicional</span><span class="sxs-lookup"><span data-stu-id="4edfe-114">Traditional Chinese</span></span>

- <span data-ttu-id="4edfe-115">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="4edfe-115">Dutch</span></span>

- <span data-ttu-id="4edfe-116">Inglés</span><span class="sxs-lookup"><span data-stu-id="4edfe-116">English</span></span>

- <span data-ttu-id="4edfe-117">Francés</span><span class="sxs-lookup"><span data-stu-id="4edfe-117">French</span></span>

- <span data-ttu-id="4edfe-118">Alemán</span><span class="sxs-lookup"><span data-stu-id="4edfe-118">German</span></span>

- <span data-ttu-id="4edfe-119">Italiano</span><span class="sxs-lookup"><span data-stu-id="4edfe-119">Italian</span></span>

- <span data-ttu-id="4edfe-120">Japonés</span><span class="sxs-lookup"><span data-stu-id="4edfe-120">Japanese</span></span>

- <span data-ttu-id="4edfe-121">Coreano</span><span class="sxs-lookup"><span data-stu-id="4edfe-121">Korean</span></span>

- <span data-ttu-id="4edfe-122">Portugués</span><span class="sxs-lookup"><span data-stu-id="4edfe-122">Portuguese</span></span>

- <span data-ttu-id="4edfe-123">Portugués (Brasil)</span><span class="sxs-lookup"><span data-stu-id="4edfe-123">Portuguese (Brazil)</span></span>

- <span data-ttu-id="4edfe-124">Español</span><span class="sxs-lookup"><span data-stu-id="4edfe-124">Spanish</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="4edfe-125">Instalar el complemento de notificación de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="4edfe-125">Install the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="4edfe-126">Puede instalar el complemento de notificación de correo no deseado:</span><span class="sxs-lookup"><span data-stu-id="4edfe-126">You can install the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="4edfe-127">Mediante la ejecución del paquete de Windows Installer, al igual que con cualquier otro archivo .msi.</span><span class="sxs-lookup"><span data-stu-id="4edfe-127">By running the Windows Installer package as you would any other .msi file.</span></span> <span data-ttu-id="4edfe-128">Al instalar el complemento, se abre una interfaz gráfica de usuario que le guía por los pasos a través de las pantallas de instalación.</span><span class="sxs-lookup"><span data-stu-id="4edfe-128">When you install the add-in, a GUI interface opens and prompts you through the installation screens.</span></span> <span data-ttu-id="4edfe-129">Para obtener más información, consulte [Instalar el complemento de notificación de correo no deseado mediante el Asistente para instalación](#install-the-junk-email-reporting-add-in-using-the-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="4edfe-129">For more information, see [Install the Junk Email Reporting Add-In using the Setup wizard](#install-the-junk-email-reporting-add-in-using-the-setup-wizard).</span></span>

<span data-ttu-id="4edfe-130">O BIEN</span><span class="sxs-lookup"><span data-stu-id="4edfe-130">OR</span></span>

- <span data-ttu-id="4edfe-p104">Mediante la ejecución de una instalación silenciosa que suprime la interfaz de usuario de la instalación. Otro método consiste en especificar las opciones de la línea de comandos que ejecutan un script de instalación. Al instalar el complemento, aparecen otras opciones de configuración que no están disponibles a través de la interfaz gráfica de usuario. Para obtener más información, consulte [Instalar el complemento de notificación de correo no deseado en modo silencioso](#install-the-junk-email-reporting-add-in-using-silent-mode).</span><span class="sxs-lookup"><span data-stu-id="4edfe-p104">By running a silent installation which suppresses the installation user interface. Instead, you specify command-line options which run an installation script. When you install the add-in, additional configuration options are available which are not available through the GUI interface. For more information, see [Install the Junk Email Reporting Add-In using Silent Mode](#install-the-junk-email-reporting-add-in-using-silent-mode).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4edfe-135">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="4edfe-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4edfe-136">Consulte los **requisitos del sistema** para el complemento de notificación de correo no [https://www.microsoft.com/download/details.aspx?id=18275](https://www.microsoft.com/download/details.aspx?id=18275)deseado en.</span><span class="sxs-lookup"><span data-stu-id="4edfe-136">See the **System Requirements** for the Junk Email Reporting Add-in at [https://www.microsoft.com/download/details.aspx?id=18275](https://www.microsoft.com/download/details.aspx?id=18275).</span></span>

> [!NOTE]
> <span data-ttu-id="4edfe-137">Debe tener permisos de administrador en el equipo en el que vaya a instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="4edfe-137">You must have administrator privileges on the computer on which you are installing the add-in.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="4edfe-138">Instalar el complemento de notificación de correo no deseado mediante el Asistente para instalación</span><span class="sxs-lookup"><span data-stu-id="4edfe-138">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="4edfe-139">En el equipo, cierre Outlook.</span><span class="sxs-lookup"><span data-stu-id="4edfe-139">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="4edfe-140">En la sección **detalles** del [complemento de notificación de correo no deseado de Microsoft para Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275), descargue el archivo. msi adecuado para su versión de Office.</span><span class="sxs-lookup"><span data-stu-id="4edfe-140">In the **Details** section at [Microsoft Junk E-mail Reporting Add-In for Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275), download the appropriate .msi file for your version of Office.</span></span>

3. <span data-ttu-id="4edfe-141">Haga doble clic en el archivo .msi.</span><span class="sxs-lookup"><span data-stu-id="4edfe-141">Double-click the .msi file.</span></span>

4. <span data-ttu-id="4edfe-142">En la página de **bienvenida a la instalación del complemento de notificación de correo no deseado de Microsoft**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4edfe-142">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="4edfe-p105">Lea el contrato de licencia y, a continuación, haga clic en **Acepto los términos del contrato de licencia** si acepta los términos de la instalación (necesario para continuar con la instalación). Haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="4edfe-p105">Review the license agreement, and then click **I accept the terms in the License Agreement** if you agree to the terms of installation (required to continue installation). Click **Next** to continue.</span></span>

6. <span data-ttu-id="4edfe-145">Cuando el asistente se haya completado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4edfe-145">When the wizard is complete, click **Finish**.</span></span>

7. <span data-ttu-id="4edfe-146">Inicie Outlook.</span><span class="sxs-lookup"><span data-stu-id="4edfe-146">Start Outlook.</span></span>

8. <span data-ttu-id="4edfe-p106">Busque el botón **Correo no deseado** en la cinta de Outlook. Ahora podrá notificar mensajes de correo no deseado a Microsoft seleccionando los mensajes de correo no deseado en la Bandeja de entrada y haciendo clic en el botón de **Informar de correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="4edfe-p106">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

9. <span data-ttu-id="4edfe-p107">Elija la flecha abajo que aparece junto a **Correo no deseado** para ver más opciones, como **Notificar como suplantación de identidad (phishing)** si desea informar a Microsoft sobre correos de suplantación de identidad (phishing). En la carpeta de correo no deseado, también puede seleccionar **Notificar como correo deseado** si un correo electrónico se ha identificado incorrectamente como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="4edfe-p107">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="4edfe-151">Instalar el complemento de notificación de correo no deseado en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="4edfe-151">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="4edfe-152">En el equipo, cierre Outlook.</span><span class="sxs-lookup"><span data-stu-id="4edfe-152">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="4edfe-153">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4edfe-153">Open a command prompt.</span></span>

3. <span data-ttu-id="4edfe-154">Si desea instalar el complemento de forma directa, sin parámetros opcionales, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4edfe-154">If you want to perform a straight installation of the add-in, without any optional parameters, specify the following:</span></span>

   - <span data-ttu-id="4edfe-155">Equipos que ejecutan Outlook x86:`msiexec /qn /i JunkReportingAdd-in.x86-en.msi`</span><span class="sxs-lookup"><span data-stu-id="4edfe-155">Computers running x86 Outlook: `msiexec /qn /i JunkReportingAdd-in.x86-en.msi`</span></span>

   - <span data-ttu-id="4edfe-156">Equipos que ejecuten Outlook x64:  `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`</span><span class="sxs-lookup"><span data-stu-id="4edfe-156">Computers running x64 Outlook:  `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`</span></span>

    <span data-ttu-id="4edfe-157">También puede especificar los parámetros opcionales MaxMessageSelection y BccEmailAddress:</span><span class="sxs-lookup"><span data-stu-id="4edfe-157">You can also specify the optional MaxMessageSelection and BccEmailAddress parameters:</span></span>

   - <span data-ttu-id="4edfe-p108">MaxMessageSelection Permite a los administradores definir el número máximo de mensajes que los usuarios pueden seleccionar para el envío con un solo clic. El intervalo oscila entre 1 y 50 mensajes, y el valor predeterminado es 10 mensajes.</span><span class="sxs-lookup"><span data-stu-id="4edfe-p108">MaxMessageSelection Allows administrators to define the maximum number of messages that can be selected by users for submission in a single click. The range is 1 to 50 messages, and the default value is 10 messages.</span></span>

     <span data-ttu-id="4edfe-160">Ejemplo: Si desea establecer el número máximo de mensajes que los usuarios pueden seleccionar para el envío con un solo clic en 16, use la siguiente opción como parte del comando de instalación:  `MaxMessageSelection=16`</span><span class="sxs-lookup"><span data-stu-id="4edfe-160">Example: If you want to set the maximum number of messages that can be selected by users for submission in a single click to 16, use the following option as part of the installation command:  `MaxMessageSelection=16`</span></span>

   - <span data-ttu-id="4edfe-p109">BccEmailAddress Permite a los administradores configurar un buzón para recibir una copia de los envíos de los usuarios mediante la especificación de una dirección de correo electrónico en el cuadro CCO. Una vez configurado el buzón, se envía una copia de todos los correos electrónicos enviados a BccEmailAddress. En caso contrario, la configuración predeterminada es no tener ninguna dirección de correo electrónico en el cuadro CCO.</span><span class="sxs-lookup"><span data-stu-id="4edfe-p109">BccEmailAddress Allows Administrators to set up a mailbox to receive a copy of all their user submissions by setting a Bcc email address. When the mailbox is set up, a copy of all submitted emails will be sent to the BccEmailAddress. Otherwise, the default setting is no Bcc email address.</span></span>

     <span data-ttu-id="4edfe-164">Ejemplo: Si desea usar junkReports@contoso.com como la dirección de correo electrónico del cuadro CCO para todos los envíos, utilice el siguiente comando:  `BccEmailAddress="junkReports@contoso.com"`</span><span class="sxs-lookup"><span data-stu-id="4edfe-164">Example: If you want to use junkReports@contoso.com as the Bcc email address for all submissions, use the following command:  `BccEmailAddress="junkReports@contoso.com"`</span></span>

     > [!NOTE]
     > <span data-ttu-id="4edfe-p110">Para establecer varias direcciones de correo electrónico CCO, sepárelas mediante punto y coma. Ejemplo:  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`</span><span class="sxs-lookup"><span data-stu-id="4edfe-p110">You can set multiple Bcc email addresses by entering them with a semicolon delimiter. Example:  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`</span></span>

     <span data-ttu-id="4edfe-167">Para agregar estos dos parámetros opcionales en función de los ejemplos anteriores, ejecutaría el comando siguiente en un equipo que ejecuta Outlook x86:</span><span class="sxs-lookup"><span data-stu-id="4edfe-167">To add both of these optional parameters based on the previous examples, you would run the following command on a computer running x86 Outlook:</span></span>

     ```
     msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
     ```

4. <span data-ttu-id="4edfe-168">Después de completar la instalación, inicie Outlook.</span><span class="sxs-lookup"><span data-stu-id="4edfe-168">After the installation is complete, start Outlook.</span></span>

5. <span data-ttu-id="4edfe-p111">Busque el botón **Correo no deseado** en la cinta de Outlook. Ahora podrá notificar mensajes de correo no deseado a Microsoft seleccionando los mensajes de correo no deseado en la Bandeja de entrada y haciendo clic en el botón de **Informar de correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="4edfe-p111">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

6. <span data-ttu-id="4edfe-p112">Elija la flecha abajo que aparece junto a **Correo no deseado** para ver más opciones, como **Notificar como suplantación de identidad (phishing)** si desea informar a Microsoft sobre correos de suplantación de identidad (phishing). En la carpeta de correo no deseado, también puede seleccionar **Notificar como correo deseado** si un correo electrónico se ha identificado incorrectamente como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="4edfe-p112">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="4edfe-173">Desinstalar el complemento de notificación de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="4edfe-173">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="4edfe-174">Use una de las opciones descritas en esta para desinstalar el complemento de notificación de correo no deseado:</span><span class="sxs-lookup"><span data-stu-id="4edfe-174">Use one of the options described in this to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="4edfe-175">Quite el complemento mediante el Panel de control de Windows.</span><span class="sxs-lookup"><span data-stu-id="4edfe-175">Remove the add-in using Windows Control Panel.</span></span>

- <span data-ttu-id="4edfe-176">Ejecute el paquete de Windows Installer y seleccione la opción de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="4edfe-176">Run the Windows installer package and select the uninstall option.</span></span>

- <span data-ttu-id="4edfe-177">Ejecute una instalación silenciosa mediante la opción de desinstalar.</span><span class="sxs-lookup"><span data-stu-id="4edfe-177">Run a silent installation using the uninstall option.</span></span>

> [!NOTE]
> <span data-ttu-id="4edfe-178">Debe tener permisos de administrador en el equipo en el que vaya a desinstalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="4edfe-178">You must have administrator privileges on the computer on which you are uninstalling the add-in.</span></span>

### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a><span data-ttu-id="4edfe-179">Desinstalar el complemento de notificación de correo no deseado desde el Panel de control</span><span class="sxs-lookup"><span data-stu-id="4edfe-179">Uninstall the Junk Email Reporting Add-in from Control Panel</span></span>

1. <span data-ttu-id="4edfe-180">En el equipo, cierre Outlook.</span><span class="sxs-lookup"><span data-stu-id="4edfe-180">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="4edfe-181">En el menú Inicio del equipo, seleccione **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="4edfe-181">From the Start menu on your computer, select **Control Panel**.</span></span>

3. <span data-ttu-id="4edfe-182">Seleccione **Programas y características**.</span><span class="sxs-lookup"><span data-stu-id="4edfe-182">Select **Programs and Features**.</span></span>

4. <span data-ttu-id="4edfe-183">Seleccione el **complemento de notificación de correo no deseado de Microsoft para Microsoft Office Outlook**.</span><span class="sxs-lookup"><span data-stu-id="4edfe-183">Select **Microsoft Junk E-mail Reporting Add-In for Microsoft Office Outlook**.</span></span>

5. <span data-ttu-id="4edfe-184">Elija **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="4edfe-184">Select **Uninstall**.</span></span>

6. <span data-ttu-id="4edfe-185">Inicie Outlook de nuevo para comprobar que el complemento ya no aparece en la cinta de Outlook.</span><span class="sxs-lookup"><span data-stu-id="4edfe-185">Start Outlook again to confirm that the add-in is no longer displayed on your Outlook ribbon.</span></span>

### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a><span data-ttu-id="4edfe-186">Desinstalar el complemento de notificación de correo no deseado mediante la ejecución del paquete de Windows Installer</span><span class="sxs-lookup"><span data-stu-id="4edfe-186">Uninstall the Junk Email Reporting Add-in by Running the Windows Installer Package</span></span>

1. <span data-ttu-id="4edfe-187">En el equipo, cierre Outlook.</span><span class="sxs-lookup"><span data-stu-id="4edfe-187">On your computer, close Outlook.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4edfe-188">Si se ejecuta Outlook durante el proceso de desinstalación, deberá reiniciarlo para que el complemento se desinstale por completo.</span><span class="sxs-lookup"><span data-stu-id="4edfe-188">If Outlook is running during the uninstall process, it will need to be restarted in order for the add-in to be completely uninstalled.</span></span>

2. <span data-ttu-id="4edfe-189">Vuelva a ejecutar el archivo .msi que ejecutó anteriormente para instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="4edfe-189">Re-run the .msi file you previously ran to install the add-in.</span></span>

   <span data-ttu-id="4edfe-190">(En la sección **detalles** del [complemento de notificación de correo no deseado de Microsoft para Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275), descargue el archivo. msi correspondiente a su versión de Office y, a continuación, haga doble clic en el archivo. msi).</span><span class="sxs-lookup"><span data-stu-id="4edfe-190">(In the **Details** section at [Microsoft Junk E-mail Reporting Add-In for Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275), download the appropriate .msi file for your version of Office, and then double-click the .msi file.)</span></span>

3. <span data-ttu-id="4edfe-191">Siga las instrucciones para desinstalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="4edfe-191">Follow the prompts to uninstall the add-in.</span></span>

4. <span data-ttu-id="4edfe-192">Inicie Outlook de nuevo para comprobar que el complemento ya no aparece en la cinta de Outlook.</span><span class="sxs-lookup"><span data-stu-id="4edfe-192">Start Outlook again to confirm that the add-in is no longer displayed on your Outlook ribbon.</span></span>

### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a><span data-ttu-id="4edfe-193">Desinstalar el complemento de notificación de correo no deseado en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="4edfe-193">Uninstall the Junk Email Reporting Add-in in Silent Mode</span></span>

1. <span data-ttu-id="4edfe-194">En el equipo, cierre Outlook.</span><span class="sxs-lookup"><span data-stu-id="4edfe-194">On your computer, close Outlook.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4edfe-195">Si se ejecuta Outlook durante el proceso de desinstalación, deberá reiniciarlo para que el complemento se desinstale por completo.</span><span class="sxs-lookup"><span data-stu-id="4edfe-195">If Outlook is running during the uninstall process, it will need to be restarted in order for the add-in to be completely uninstalled.</span></span>

2. <span data-ttu-id="4edfe-196">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4edfe-196">Open a command prompt.</span></span>

3. <span data-ttu-id="4edfe-197">Especifique el siguiente parámetro de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="4edfe-197">Specify the following command line parameter:</span></span>

   <span data-ttu-id="4edfe-198">Outlook x86:`msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`</span><span class="sxs-lookup"><span data-stu-id="4edfe-198">Outlook x86: `msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`</span></span>

   <span data-ttu-id="4edfe-199">Outlook x64:`msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`</span><span class="sxs-lookup"><span data-stu-id="4edfe-199">Outlook x64: `msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`</span></span>

4. <span data-ttu-id="4edfe-200">Inicie Outlook de nuevo para comprobar que el complemento ya no aparece en la cinta de Outlook.</span><span class="sxs-lookup"><span data-stu-id="4edfe-200">Start Outlook again to confirm that the add-in is no longer displayed on your Outlook ribbon.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="4edfe-201">Más información</span><span class="sxs-lookup"><span data-stu-id="4edfe-201">For more information</span></span>

[<span data-ttu-id="4edfe-202">Informar a Microsoft de los mensajes de correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="4edfe-202">Report junk email messages to Microsoft</span></span>](report-junk-email-messages-to-microsoft.md)

[<span data-ttu-id="4edfe-203">Solución de problemas e información de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="4edfe-203">Troubleshooting and support information</span></span>](troubleshooting-and-support-information.md)
