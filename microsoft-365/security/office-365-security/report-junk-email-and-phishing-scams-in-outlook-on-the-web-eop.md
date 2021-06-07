---
title: Notificar correo electrónico no deseado y suplantación de identidad Outlook en la web
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
description: Los administradores pueden obtener información sobre las opciones de informes de correo electrónico de correo no deseado, no correo no deseado y suplantación de identidad integradas en Outlook en la web (Outlook Web App) en Exchange Online y cómo deshabilitar estas opciones de informes para los usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788312"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="673e2-103">Notificar correo electrónico no deseado y suplantación de identidad Outlook en la web en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="673e2-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="673e2-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="673e2-104">**Applies to**</span></span>
- [<span data-ttu-id="673e2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="673e2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="673e2-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="673e2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="673e2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="673e2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="673e2-108">En Microsoft 365 organizaciones con buzones de correo en buzones de Exchange Online o locales mediante autenticación moderna [híbrida,](../../enterprise/hybrid-modern-auth-overview.md)puede enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico no permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="673e2-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="673e2-109">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="673e2-109">What do you need to know before you begin?</span></span>

> [!IMPORTANT]
> <span data-ttu-id="673e2-110">Se recomienda el complemento Report Message o el complemento Report Phishing para envíos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="673e2-110">We recommend the Report Message add-in or the Report Phishing add-in for user submissions.</span></span> <span data-ttu-id="673e2-111">Para obtener más información, vea [Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). No recomendamos la experiencia de informes integrada en Outlook porque no puede usar la directiva [de envío de usuario](./user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="673e2-111">For more information, see [Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span>

- <span data-ttu-id="673e2-112">Si es administrador de una organización con buzones de correo Exchange Online, le recomendamos que use el portal de envíos en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="673e2-112">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="673e2-113">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="673e2-113">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="673e2-114">Los administradores pueden deshabilitar o habilitar la capacidad de los usuarios para notificar mensajes a Microsoft Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="673e2-114">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="673e2-115">Para obtener más información, vea la sección Deshabilitar o habilitar informes de correo no deseado [en Outlook en la web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="673e2-115">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="673e2-116">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique.</span><span class="sxs-lookup"><span data-stu-id="673e2-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="673e2-117">Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="673e2-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="673e2-118">Para obtener más información acerca de cómo notificar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="673e2-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="673e2-119">Deshabilitar o habilitar los informes de correo no deseado Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="673e2-119">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="673e2-120">De forma predeterminada, los usuarios pueden notificar falsos positivos de correo no deseado, falsos negativos y mensajes de suplantación de identidad a Microsoft para su análisis Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="673e2-120">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="673e2-121">Los administradores pueden configurar Outlook directivas de buzones de correo web en Exchange Online PowerShell para evitar que los usuarios den a Microsoft informes de falsos positivos de correo no deseado y falsos negativos de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="673e2-121">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="673e2-122">No puede deshabilitar la capacidad de los usuarios de notificar mensajes de suplantación de identidad a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="673e2-122">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="673e2-123">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="673e2-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="673e2-124">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="673e2-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="673e2-125">Debe tener asignados permisos en Exchange Online para poder realizar los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="673e2-125">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="673e2-126">Específicamente, necesita los roles **Directivas de** destinatarios o Destinatarios de correo, que están **asignados** a **los** grupos de roles Administración de la organización y **Administración** de destinatarios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="673e2-126">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="673e2-127">Para obtener más información acerca de los grupos de roles en Exchange Online, vea [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) y [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="673e2-127">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="673e2-128">Cada organización tiene una directiva predeterminada denominada OwaMailboxPolicy-Default, pero puede crear directivas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="673e2-128">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="673e2-129">Las directivas personalizadas se aplican a los usuarios con ámbito antes de la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="673e2-129">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="673e2-130">Para obtener más información acerca Outlook en las directivas de buzones de correo web, vea Outlook [en las directivas de buzón](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)web en Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="673e2-130">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="673e2-131">Deshabilitar los informes de correo no deseado no elimina la capacidad de marcar un mensaje como correo no deseado o no deseado en Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="673e2-131">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="673e2-132">Si selecciona un mensaje en la  carpeta Correo no deseado y hace clic en No deseado, el mensaje se vuelve a mover a \>  la Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="673e2-132">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="673e2-133">Al seleccionar un mensaje en cualquier  otra carpeta de correo electrónico y hacer clic en No deseado, el mensaje se mueve a \>  la carpeta Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="673e2-133">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="673e2-134">Lo que ya no está disponible es la opción de informar el mensaje a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="673e2-134">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="673e2-135">Usar Exchange Online PowerShell para deshabilitar o habilitar los informes de correo no deseado Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="673e2-135">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="673e2-136">Para buscar la información Outlook en las directivas de buzón de correo web y el estado de los informes de correo no deseado, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="673e2-136">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="673e2-137">Para deshabilitar o habilitar los informes de correo no deseado Outlook en la web, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="673e2-137">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="673e2-138">En este ejemplo se deshabilitan los informes de correo no deseado en la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="673e2-138">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="673e2-139">En este ejemplo se habilitan los informes de correo no deseado en la directiva personalizada denominada Administradores de Contoso.</span><span class="sxs-lookup"><span data-stu-id="673e2-139">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="673e2-140">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) y [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="673e2-140">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="673e2-141">¿Cómo saber si el proceso se completó correctamente?</span><span class="sxs-lookup"><span data-stu-id="673e2-141">How do you know this worked?</span></span>

<span data-ttu-id="673e2-142">Para comprobar que ha habilitado o deshabilitado correctamente los informes de correo no deseado en Outlook en la web, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="673e2-142">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="673e2-143">En Exchange Online PowerShell, ejecute el siguiente comando y compruebe el valor de la propiedad **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="673e2-143">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="673e2-144">Abra el buzón de un usuario afectado en Outlook en la web,  seleccione un mensaje en la Bandeja de entrada, haga clic en Correo no deseado y compruebe que el mensaje para notificarlo a Microsoft se muestra o \>  no.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="673e2-144">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="673e2-145">Abra el buzón de un usuario afectado en Outlook en la web, seleccione  un mensaje en la carpeta Correo no deseado, haga clic en Correo no deseado y compruebe que el mensaje para notificarlo a Microsoft está o no se \>  muestra.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="673e2-145">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="673e2-146"><sup>\*</sup> Los usuarios pueden ocultar el mensaje para informar del mensaje mientras siguen informando del mensaje.</span><span class="sxs-lookup"><span data-stu-id="673e2-146"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="673e2-147">Para comprobar esta configuración en Outlook en la web:</span><span class="sxs-lookup"><span data-stu-id="673e2-147">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="673e2-148">Haga **clic Configuración** Outlook en el icono de configuración web Ver todos los Outlook ![ ](../../media/owa-settings-icon.png) \> **configuración** correo no \> **deseado**.</span><span class="sxs-lookup"><span data-stu-id="673e2-148">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="673e2-149">En la **sección Informes,** compruebe el valor: **Pregúnteme antes de enviar un informe**.</span><span class="sxs-lookup"><span data-stu-id="673e2-149">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook configuración de informes de correo no deseado en la web](../../media/owa-junk-email-reporting-options.png)
