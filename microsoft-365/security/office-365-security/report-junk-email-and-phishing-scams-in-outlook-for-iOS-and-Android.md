---
title: Notificar correo electrónico no deseado y de suplantación de identidad en Outlook para iOS y Android
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
description: Los administradores pueden obtener información sobre las opciones integradas de notificación de correo electrónico no deseado, correo no deseado y suplantación de identidad (phishing) en Outlook para iOS y Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d702ab1d97c07c3e38430a9a7beff5f14db7b60a
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029285"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="6bfff-103">Notificar correo electrónico no deseado y de suplantación de identidad en Outlook para iOS y Android en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6bfff-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6bfff-104">En organizaciones de Microsoft 365 con buzones en Exchange Online o buzones locales mediante la autenticación moderna [híbrida,](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)puede usar las opciones de informes integradas en Outlook para iOS y Android para enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico no deseado permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="6bfff-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6bfff-105">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="6bfff-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="6bfff-106">Si es administrador de una organización con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6bfff-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="6bfff-107">Para obtener más información, vea Usar envío de administrador para enviar correos sospechosos de correo no [deseado, phishing, direcciones URL y archivos a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="6bfff-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="6bfff-108">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique.</span><span class="sxs-lookup"><span data-stu-id="6bfff-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="6bfff-109">Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="6bfff-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="6bfff-110">Para obtener más información acerca de la notificación de mensajes a Microsoft, vea Notificar mensajes [y archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="6bfff-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="6bfff-111">Si los informes de correo no deseado están deshabilitados para Outlook en la directiva de envío de usuario, los mensajes de correo no deseado o de suplantación de identidad se mueven a la carpeta de correo no deseado y no se notifican a su administrador o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6bfff-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="6bfff-112">Notificar mensajes de correo no deseado y suplantación de identidad en Outlook para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="6bfff-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="6bfff-113">Para los mensajes de la Bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo no deseado, siga estos pasos para notificar mensajes de correo no deseado y de suplantación de identidad (phishing) para iOS y Android:</span><span class="sxs-lookup"><span data-stu-id="6bfff-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="6bfff-114">Seleccione uno o más mensajes.</span><span class="sxs-lookup"><span data-stu-id="6bfff-114">Select one or more messages.</span></span>
2. <span data-ttu-id="6bfff-115">En la esquina superior derecha, pulsa en los tres puntos verticales.</span><span class="sxs-lookup"><span data-stu-id="6bfff-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="6bfff-116">Se abre el menú de acciones.</span><span class="sxs-lookup"><span data-stu-id="6bfff-116">The action menu opens.</span></span>

   ![Notificar correo no deseado o de suplantación de identidad desde el menú de acción](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="6bfff-118">Pulse **Informar de correo no** deseado y, a **continuación,** seleccione Correo no deseado o **Suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="6bfff-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Informar de correo electrónico no deseado o de suplantación de identidad](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="6bfff-120">En el cuadro de diálogo que aparece, puede elegir **Informe** o **No gracias.**</span><span class="sxs-lookup"><span data-stu-id="6bfff-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="6bfff-121">Al seleccionar No se **agradece,** si ha pulsado Correo no deseado,  el mensaje se mueve a la carpeta Correo no deseado, si pulsa suplantación de identidad, el mensaje se mueve a la carpeta Elementos eliminados. </span><span class="sxs-lookup"><span data-stu-id="6bfff-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="6bfff-122">Seleccione **Informe** para enviar también una copia del mensaje a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6bfff-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Informar sobre las opciones de notificación de correo no deseado o de suplantación de identidad](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="6bfff-124">Si cambias de opinión, selecciona **Deshacer** en la notificación del sistema que aparece.</span><span class="sxs-lookup"><span data-stu-id="6bfff-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="6bfff-125">El mensaje permanece en la carpeta Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="6bfff-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="6bfff-126">Notificar mensajes que no son correo no deseado desde la carpeta de correo no deseado en Outlook para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="6bfff-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="6bfff-127">En la carpeta Correo no deseado, siga estos pasos para notificar falsos positivos de correo no deseado:</span><span class="sxs-lookup"><span data-stu-id="6bfff-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="6bfff-128">Seleccione uno o más mensajes.</span><span class="sxs-lookup"><span data-stu-id="6bfff-128">Select one or more messages.</span></span>
2. <span data-ttu-id="6bfff-129">En la esquina superior derecha, pulsa en los tres puntos verticales.</span><span class="sxs-lookup"><span data-stu-id="6bfff-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="6bfff-130">Se abre el menú de acciones.</span><span class="sxs-lookup"><span data-stu-id="6bfff-130">The action menu opens.</span></span>

   ![Notificar correo no deseado desde el menú de acción](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="6bfff-132">Pulse **No deseado.**</span><span class="sxs-lookup"><span data-stu-id="6bfff-132">Tap **Not junk**.</span></span>

<span data-ttu-id="6bfff-133">Aparece una notificación del sistema que muestra que el correo electrónico se ha movido a la Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="6bfff-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="6bfff-134">Si cambias de opinión, selecciona **Deshacer en** la notificación del sistema.</span><span class="sxs-lookup"><span data-stu-id="6bfff-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="6bfff-135">El correo electrónico permanece en la carpeta Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="6bfff-135">The email remains in the Junk folder.</span></span>
