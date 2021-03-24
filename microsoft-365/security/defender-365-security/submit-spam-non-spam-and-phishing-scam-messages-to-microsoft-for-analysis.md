---
title: Enviar mensajes manualmente a Microsoft para su análisis
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Los administradores y los usuarios finales pueden aprender a enviar mensajes de correo electrónico (correo bueno marcado como correo malo o mal permitido) a Microsoft para su análisis.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0a6f564d82750c5ab8156680854c2453cda6971
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072491"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="119ce-103">Enviar mensajes manualmente a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="119ce-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="119ce-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="119ce-104">**Applies to**</span></span>
- [<span data-ttu-id="119ce-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="119ce-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="119ce-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="119ce-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="119ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="119ce-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="119ce-108">Si es administrador de una organización con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="119ce-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="119ce-109">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="119ce-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="119ce-110">Puede ser frustrante cuando los usuarios de la organización reciben mensajes de correo no deseado o mensajes de suplantación de identidad en su Bandeja de entrada, o si no reciben un mensaje de correo electrónico legítimo porque está marcado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="119ce-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="119ce-111">Estamos ajustando constantemente nuestros filtros de correo no deseado para que sean más precisos.</span><span class="sxs-lookup"><span data-stu-id="119ce-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="119ce-112">Usted y sus usuarios pueden ayudar a este proceso enviando falsos positivos (buen correo electrónico marcado como malo), falsos negativos (correo no permitido) y mensajes de suplantación de identidad a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="119ce-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="119ce-113">Debido al gran volumen de envíos que recibimos, es posible que no podamos responder a todas las solicitudes de análisis.</span><span class="sxs-lookup"><span data-stu-id="119ce-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="119ce-114">Enviar falsos negativos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="119ce-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="119ce-115">En lugar de usar los siguientes procedimientos para notificar falsos negativos, los usuarios de Outlook y Outlook en la web (anteriormente conocidos como Outlook Web App) pueden usar el complemento Report Message o el complemento Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="119ce-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="119ce-116">Para obtener información sobre cómo instalar y usar estas herramientas, vea [Enable the Report Message add-in](enable-the-report-message-add-in.md) and Enable the Report [Phishing add-in](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="119ce-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="119ce-117">Si recibe un mensaje que pasó por el filtrado de correo no deseado que debería haber sido identificado como correo no deseado o phishing, puede enviar el mensaje a los equipos análisis de correo no deseado de Microsoft y Análisis de suplantación de identidad de Microsoft según corresponda.</span><span class="sxs-lookup"><span data-stu-id="119ce-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="119ce-118">Los analistas revisarán el mensaje y lo agregarán a los filtros de todo el servicio si cumple los criterios de clasificación.</span><span class="sxs-lookup"><span data-stu-id="119ce-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="119ce-119">Cree un nuevo mensaje de correo electrónico en blanco con uno de los siguientes destinatarios:</span><span class="sxs-lookup"><span data-stu-id="119ce-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="119ce-120">**Correo no deseado**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="119ce-120">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="119ce-121">**Phishing**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="119ce-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="119ce-122">Arrastre y coloque el mensaje de correo no deseado o suplantación de identidad en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="119ce-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="119ce-123">Esto guardará el mensaje de correo no deseado o suplantación de identidad como datos adjuntos en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="119ce-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="119ce-124">No copie y pegue el contenido del mensaje o reenvía el mensaje (necesitamos el mensaje original para poder inspeccionar los encabezados del mensaje).</span><span class="sxs-lookup"><span data-stu-id="119ce-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="119ce-125">Puede adjuntar varios mensajes en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="119ce-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="119ce-126">Asegúrese de que todos los mensajes son del mismo tipo: mensajes de suplantación de identidad (phishing) o mensajes de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="119ce-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="119ce-127">Deje el cuerpo del nuevo mensaje en blanco.</span><span class="sxs-lookup"><span data-stu-id="119ce-127">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="119ce-128">Use los formatos .msg (formato predeterminado de Outlook) o .eml (formato predeterminado de Outlook en la Web) para los mensajes adjuntos.</span><span class="sxs-lookup"><span data-stu-id="119ce-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="119ce-129">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="119ce-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="119ce-130">Los administradores tienen varias formas diferentes de bloquear mensajes específicos que se están identificación erróneamente como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="119ce-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="119ce-131">Para obtener más información, vea [Crear listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="119ce-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="119ce-132">Enviar falsos positivos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="119ce-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="119ce-133">En lugar de usar los siguientes procedimientos para notificar falsos positivos, los usuarios de Outlook y Outlook en la web (anteriormente conocidos como Outlook Web App) pueden usar el complemento Report Message o el complemento Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="119ce-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="119ce-134">Para obtener información sobre cómo instalar y usar estas herramientas, vea [Enable the Report Message add-in](enable-the-report-message-add-in.md) and Enable the Report [Phishing add-in](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="119ce-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="119ce-135">Si un mensaje se identificó incorrectamente como correo no deseado, puede enviar el mensaje al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="119ce-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="119ce-136">Los analistas evaluarán el mensaje y (según los resultados del análisis) los filtros de todo el servicio se pueden ajustar para permitir que el mensaje pase.</span><span class="sxs-lookup"><span data-stu-id="119ce-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="119ce-137">Cree un nuevo mensaje de correo electrónico en blanco `not_junk@office365.microsoft.com` con como destinatario:</span><span class="sxs-lookup"><span data-stu-id="119ce-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="119ce-138">Arrastre y coloque el mensaje no identificado en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="119ce-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="119ce-139">Esto guardará el mensaje no identificado como datos adjuntos en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="119ce-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="119ce-140">No copie y pegue el contenido del mensaje o reenvía el mensaje (necesitamos el mensaje original para poder inspeccionar los encabezados del mensaje).</span><span class="sxs-lookup"><span data-stu-id="119ce-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="119ce-141">Puede adjuntar varios mensajes en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="119ce-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="119ce-142">Asegúrese de que todos los mensajes son del mismo tipo: mensajes de suplantación de identidad (phishing) o mensajes de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="119ce-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="119ce-143">Deje el cuerpo del nuevo mensaje en blanco.</span><span class="sxs-lookup"><span data-stu-id="119ce-143">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="119ce-144">Use los formatos .msg (formato predeterminado de Outlook) o .eml (formato predeterminado de Outlook en la Web) para los mensajes adjuntos.</span><span class="sxs-lookup"><span data-stu-id="119ce-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="119ce-145">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="119ce-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="119ce-146">Los administradores tienen varias formas diferentes de permitir que mensajes específicos omitan el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="119ce-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="119ce-147">Para obtener más información, vea [Crear listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="119ce-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="119ce-148">¿Dónde se almacenan los datos de los envíos a Microsoft?</span><span class="sxs-lookup"><span data-stu-id="119ce-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="119ce-149">Los datos residen en el límite de cumplimiento de Office 365 en los centros de datos de Norteamérica.</span><span class="sxs-lookup"><span data-stu-id="119ce-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="119ce-150">Los analistas del equipo de ingeniería revisan los datos para ayudar a mejorar la eficacia de los filtros.</span><span class="sxs-lookup"><span data-stu-id="119ce-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="119ce-151">Crear una regla de flujo de correo para recibir copias de los mensajes que se notifican a Microsoft</span><span class="sxs-lookup"><span data-stu-id="119ce-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="119ce-152">Para obtener instrucciones, consulte [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="119ce-152">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
