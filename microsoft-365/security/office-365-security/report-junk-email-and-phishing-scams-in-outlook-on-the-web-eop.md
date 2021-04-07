---
title: Notificar correo electrónico no deseado y suplantación de identidad en Outlook en la web
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
description: Los administradores pueden obtener información sobre las opciones integradas de informes de correo electrónico no deseado, no correo electrónico no deseado y suplantación de identidad en Outlook en la web (Outlook Web App) en Exchange Online y cómo deshabilitar estas opciones de informes para los usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615219"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="452ad-103">Notificar correo electrónico no deseado y suplantación de identidad en Outlook en la web en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="452ad-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="452ad-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="452ad-104">**Applies to**</span></span>
- [<span data-ttu-id="452ad-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="452ad-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="452ad-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="452ad-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="452ad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="452ad-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="452ad-108">En las organizaciones de Microsoft 365 con buzones en Exchange Online o buzones locales con autenticación moderna [híbrida,](../../enterprise/hybrid-modern-auth-overview.md)puede enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico no permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="452ad-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="452ad-109">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="452ad-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="452ad-110">Para obtener la mejor experiencia de envío de usuarios, se recomienda usar el mensaje de informe y los complementos de suplantación de identidad de informes. Vea [Habilitar el complemento Mensaje de informe y](./enable-the-report-message-add-in.md) Habilitar el complemento de suplantación de identidad [de informes](./enable-the-report-phish-add-in.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="452ad-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="452ad-111">Si es administrador de una organización con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="452ad-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="452ad-112">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="452ad-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="452ad-113">Los administradores pueden deshabilitar o habilitar la capacidad de los usuarios para notificar mensajes a Microsoft en Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="452ad-113">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="452ad-114">Para obtener más información, vea la sección Deshabilitar o habilitar informes de correo no deseado en [Outlook en la web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="452ad-114">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="452ad-115">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique.</span><span class="sxs-lookup"><span data-stu-id="452ad-115">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="452ad-116">Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="452ad-116">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="452ad-117">Para obtener más información acerca de cómo notificar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="452ad-117">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="452ad-118">Deshabilitar o habilitar los informes de correo no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="452ad-118">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="452ad-119">De forma predeterminada, los usuarios pueden notificar falsos positivos de correo no deseado, falsos negativos y mensajes de suplantación de identidad a Microsoft para su análisis en Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="452ad-119">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="452ad-120">Los administradores pueden configurar las directivas de buzón de correo de Outlook en la web en Exchange Online PowerShell para evitar que los usuarios informen a Microsoft de falsos positivos de correo no deseado y falsos negativos de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="452ad-120">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="452ad-121">No puede deshabilitar la capacidad de los usuarios de notificar mensajes de suplantación de identidad a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="452ad-121">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="452ad-122">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="452ad-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="452ad-123">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="452ad-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="452ad-124">Debe tener asignados permisos en Exchange Online antes de poder realizar los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="452ad-124">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="452ad-125">Específicamente, necesita los roles **Directivas de** destinatarios o Destinatarios de correo, que están **asignados** a **los** grupos de roles Administración de la organización y **Administración** de destinatarios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="452ad-125">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="452ad-126">Para obtener más información acerca de los grupos de roles en Exchange Online, vea [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) y [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="452ad-126">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="452ad-127">Cada organización tiene una directiva predeterminada denominada OwaMailboxPolicy-Default, pero puede crear directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="452ad-127">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="452ad-128">Las directivas personalizadas se aplican a los usuarios con ámbito antes de la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="452ad-128">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="452ad-129">Para obtener más información acerca de las directivas de buzones de correo de Outlook en la web, vea [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="452ad-129">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="452ad-130">Deshabilitar los informes de correo no deseado no elimina la capacidad de marcar un mensaje como correo no deseado o no deseado en Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="452ad-130">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="452ad-131">Si selecciona un mensaje en la  carpeta Correo no deseado y hace clic en No deseado, el mensaje se vuelve a mover a \>  la Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="452ad-131">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="452ad-132">Al seleccionar un mensaje en cualquier  otra carpeta de correo electrónico y hacer clic en No deseado, el mensaje se mueve a \>  la carpeta Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="452ad-132">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="452ad-133">Lo que ya no está disponible es la opción de informar el mensaje a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="452ad-133">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="452ad-134">Usar Exchange Online PowerShell para deshabilitar o habilitar los informes de correo no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="452ad-134">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="452ad-135">Para buscar las directivas existentes de outlook en el buzón de correo web y el estado de los informes de correo no deseado, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="452ad-135">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="452ad-136">Para deshabilitar o habilitar los informes de correo no deseado en Outlook en la web, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="452ad-136">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="452ad-137">En este ejemplo se deshabilitan los informes de correo no deseado en la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="452ad-137">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="452ad-138">En este ejemplo se habilitan los informes de correo no deseado en la directiva personalizada denominada Administradores de Contoso.</span><span class="sxs-lookup"><span data-stu-id="452ad-138">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="452ad-139">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) y [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="452ad-139">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="452ad-140">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="452ad-140">How do you know this worked?</span></span>

<span data-ttu-id="452ad-141">Para comprobar que ha habilitado o deshabilitado correctamente los informes de correo no deseado en Outlook en la web, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="452ad-141">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="452ad-142">En Exchange Online PowerShell, ejecute el siguiente comando y compruebe el valor de la propiedad **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="452ad-142">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="452ad-143">Abra el buzón de un usuario afectado en Outlook en la  web, seleccione un mensaje en la Bandeja de entrada, haga clic en Correo no deseado y compruebe que el mensaje que se va a notificar a Microsoft se muestra o \>  no.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="452ad-143">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="452ad-144">Abra el buzón de un usuario afectado en Outlook en la web, seleccione un mensaje en la carpeta Correo no deseado, haga clic en Correo no deseado y compruebe que el mensaje que se va a notificar a Microsoft se muestra o  \>  no.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="452ad-144">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="452ad-145"><sup>\*</sup> Los usuarios pueden ocultar el mensaje para informar del mensaje mientras siguen informando del mensaje.</span><span class="sxs-lookup"><span data-stu-id="452ad-145"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="452ad-146">Para comprobar esta configuración en Outlook en la web:</span><span class="sxs-lookup"><span data-stu-id="452ad-146">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="452ad-147">Haga **clic en Configuración** Outlook en el icono de configuración web Ver toda la configuración de ![ ](../../media/owa-settings-icon.png) \> **Outlook** Correo electrónico no \> **deseado**.</span><span class="sxs-lookup"><span data-stu-id="452ad-147">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="452ad-148">En la **sección Informes,** compruebe el valor: **Pregúnteme antes de enviar un informe**.</span><span class="sxs-lookup"><span data-stu-id="452ad-148">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Configuración de informes de correo no deseado de Outlook en la web](../../media/owa-junk-email-reporting-options.png)