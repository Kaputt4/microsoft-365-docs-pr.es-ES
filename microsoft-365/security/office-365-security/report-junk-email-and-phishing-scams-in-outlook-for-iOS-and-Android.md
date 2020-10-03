---
title: Informar del correo electrónico no deseado y de suplantación de identidad en Outlook para iOS y Android
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre las opciones integradas de correo no deseado, correo no deseado y suplantación de identidad en Outlook para iOS y Android.
ms.openlocfilehash: 23668a762301ee442bc805e62863079ee7ae6076
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350860"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="76e47-103">Informar del correo electrónico no deseado y de suplantación de identidad en Outlook para iOS y Android en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="76e47-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="76e47-104">En Microsoft 365 organizaciones con buzones de correo en Exchange online o buzones locales que usan la [autenticación moderna híbrida](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), puede usar las opciones de informes integradas en Outlook para iOS y Android para enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico incorrecto permitido) y mensajes de suplantación de identidad para Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="76e47-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="76e47-105">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="76e47-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="76e47-106">Si es administrador de una organización con buzones de correo de Exchange Online, le recomendamos que use el portal de envíos del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="76e47-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="76e47-107">Para obtener más información, vea [usar el envío de administración para enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="76e47-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="76e47-108">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón de correo que especifique.</span><span class="sxs-lookup"><span data-stu-id="76e47-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="76e47-109">Para obtener más información, consulte [directivas de envíos de usuario](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="76e47-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="76e47-110">Para obtener más información acerca de los informes de mensajes a Microsoft, vea [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="76e47-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="76e47-111">Si la notificación de correo no deseado está deshabilitada para Outlook en la Directiva de envío de usuario, los mensajes de correo no deseado o de suplantación de identidad se moverán a la carpeta de correo no deseado y no se notificará al administrador</span><span class="sxs-lookup"><span data-stu-id="76e47-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="76e47-112">Notificar mensajes de correo no deseado y suplantación de identidad en Outlook para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="76e47-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="76e47-113">Para los mensajes de la bandeja de entrada, o cualquier otra carpeta de correo electrónico excepto correo electrónico no deseado, siga estos pasos para notificar mensajes de correo no deseado y suplantación de identidad (phishing) para iOS y Android:</span><span class="sxs-lookup"><span data-stu-id="76e47-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="76e47-114">Seleccione uno o más mensajes.</span><span class="sxs-lookup"><span data-stu-id="76e47-114">Select one or more messages.</span></span>
2. <span data-ttu-id="76e47-115">En la esquina superior derecha, puntee en los tres puntos verticales.</span><span class="sxs-lookup"><span data-stu-id="76e47-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="76e47-116">Se abrirá el menú Acción.</span><span class="sxs-lookup"><span data-stu-id="76e47-116">The action menu opens.</span></span>

   ![Informar del correo no deseado o de suplantación de identidad en el menú Acción](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="76e47-118">Pulse **informar de correo no deseado** y seleccione **correo no deseado** o **suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="76e47-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Informar del correo no deseado o de suplantación de identidad](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="76e47-120">En el cuadro de diálogo que aparece, puede elegir **Informe** o **no gracias**.</span><span class="sxs-lookup"><span data-stu-id="76e47-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="76e47-121">Al seleccionar **no gracias**, si ha punteado en **correo no deseado** , el mensaje se mueve a la carpeta correo electrónico no deseado, si puntea en **suplantación de identidad** , el mensaje se mueve a la carpeta elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="76e47-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="76e47-122">Seleccione **Report** para enviar también una copia del mensaje a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76e47-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Informar sobre opciones de informes de correo no deseado o de suplantación](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="76e47-124">Si cambia de opinión, seleccione **Deshacer** en la notificación del sistema que aparece.</span><span class="sxs-lookup"><span data-stu-id="76e47-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="76e47-125">El mensaje permanece en la carpeta Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="76e47-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="76e47-126">Notificar mensajes seguros desde la carpeta correo no deseado en Outlook para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="76e47-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="76e47-127">En la carpeta de correo no deseado, siga estos pasos para notificar falsos positivos de correo no deseado:</span><span class="sxs-lookup"><span data-stu-id="76e47-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="76e47-128">Seleccione uno o más mensajes.</span><span class="sxs-lookup"><span data-stu-id="76e47-128">Select one or more messages.</span></span>
2. <span data-ttu-id="76e47-129">En la esquina superior derecha, puntee en los tres puntos verticales.</span><span class="sxs-lookup"><span data-stu-id="76e47-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="76e47-130">Se abrirá el menú Acción.</span><span class="sxs-lookup"><span data-stu-id="76e47-130">The action menu opens.</span></span>

   ![Informar de correo electrónico no deseado en el menú Acción](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="76e47-132">Puntee en **no es correo electrónico no deseado**.</span><span class="sxs-lookup"><span data-stu-id="76e47-132">Tap **Not junk**.</span></span>

<span data-ttu-id="76e47-133">Una notificación del sistema parece que el correo electrónico se ha movido a la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="76e47-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="76e47-134">Si cambia de opinión, seleccione **Deshacer** en la notificación del sistema.</span><span class="sxs-lookup"><span data-stu-id="76e47-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="76e47-135">El correo electrónico permanece en la carpeta de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="76e47-135">The email remains in the Junk folder.</span></span>
