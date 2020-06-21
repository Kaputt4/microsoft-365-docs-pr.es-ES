---
title: Enviar mensajes a Microsoft de forma manual para su análisis
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Los administradores y los usuarios finales pueden obtener información sobre cómo realizar análisis a los mensajes de correo electrónico (se permite el correo marcado como correo incorrecto o malo) a Microsoft.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d6973330c4504bd6478265205f60798b3b7c1875
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811043"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="0f82d-103">Enviar mensajes a Microsoft de forma manual para su análisis</span><span class="sxs-lookup"><span data-stu-id="0f82d-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="0f82d-104">Si es administrador de una organización con buzones de correo de Exchange Online, le recomendamos que use el portal de envíos del centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0f82d-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="0f82d-105">Para obtener más información, vea [usar el envío de administración para enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="0f82d-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="0f82d-106">Puede resultar frustrante cuando los usuarios de la organización reciben mensajes de correo no deseado o mensajes de suplantación de identidad (phishing) en su bandeja de entrada, o si no reciben un mensaje de correo electrónico legítimo porque está marcado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="0f82d-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="0f82d-107">Estamos ajustando constantemente los filtros de correo no deseado para que sean más precisos.</span><span class="sxs-lookup"><span data-stu-id="0f82d-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="0f82d-108">Usted y sus usuarios pueden ayudar a este proceso mediante el envío de falsos positivos (correo electrónico bueno marcado como no válido), los falsos negativos (correo erróneo permitido) y los mensajes de suplantación de identidad a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="0f82d-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="0f82d-109">Debido al elevado volumen de envíos que recibimos, es posible que no podamos contestar todas las solicitudes de análisis.</span><span class="sxs-lookup"><span data-stu-id="0f82d-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="0f82d-110">Enviar falsos negativos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="0f82d-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="0f82d-111">En lugar de usar los siguientes procedimientos para informar sobre falsos negativos, los usuarios de Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) pueden usar el complemento de mensajes de informe para Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="0f82d-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="0f82d-112">Para obtener información sobre cómo instalar y usar esta herramienta, consulte [Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="0f82d-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="0f82d-113">Si recibe un mensaje que pasa a través del filtrado de correo no deseado que debería haberse identificado como correo no deseado o suplantación de identidad, puede enviar el mensaje a Microsoft spam Analysis y Microsoft phishing Analysis Teams según corresponda.</span><span class="sxs-lookup"><span data-stu-id="0f82d-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="0f82d-114">Los analistas revisarán el mensaje y lo agregarán a los filtros de todo el servicio si cumple con los criterios de clasificación.</span><span class="sxs-lookup"><span data-stu-id="0f82d-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="0f82d-115">Cree un mensaje de correo electrónico nuevo en blanco con uno de los siguientes destinatarios:</span><span class="sxs-lookup"><span data-stu-id="0f82d-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="0f82d-116">**Correo no deseado**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="0f82d-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="0f82d-117">**Suplantación de identidad**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="0f82d-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="0f82d-118">Arrastre y coloque el mensaje no deseado o de suplantación de identidad en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f82d-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="0f82d-119">Se guardará el mensaje no deseado o de suplantación de identidad (phishing) como datos adjuntos en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f82d-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="0f82d-120">No copie y pegue el contenido del mensaje o lo reenvíe (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).</span><span class="sxs-lookup"><span data-stu-id="0f82d-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="0f82d-121">Puede adjuntar varios mensajes en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f82d-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="0f82d-122">Asegúrese de que todos los mensajes sean del mismo tipo: mensajes de suplantación de identidad (phishing) o mensajes de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="0f82d-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="0f82d-123">Deje el cuerpo del nuevo mensaje en blanco.</span><span class="sxs-lookup"><span data-stu-id="0f82d-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="0f82d-124">Use cualquiera de los formatos. msg (formato predeterminado de Outlook) o. eml (formato predeterminado de Outlook en la web) para los mensajes adjuntos.</span><span class="sxs-lookup"><span data-stu-id="0f82d-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="0f82d-125">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="0f82d-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="0f82d-126">Los administradores tienen varias formas diferentes de bloquear mensajes específicos que se identifican como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="0f82d-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="0f82d-127">Para obtener más información, vea [crear listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0f82d-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="0f82d-128">Enviar falsos positivos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="0f82d-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="0f82d-129">En lugar de usar los siguientes procedimientos para notificar falsos positivos, los usuarios de Outlook y Outlook en la web pueden usar el complemento de mensajes de informe para Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="0f82d-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="0f82d-130">Para obtener información sobre cómo instalar y usar esta herramienta, consulte [Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="0f82d-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="0f82d-131">Si un mensaje se identificó incorrectamente como correo no deseado, puede enviar el mensaje al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0f82d-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="0f82d-132">Los analistas evaluarán el mensaje y (según los resultados del análisis) se pueden ajustar los filtros de todo el servicio para permitir el paso del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f82d-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="0f82d-133">Cree un nuevo mensaje de correo electrónico en blanco con `not_junk@office365.microsoft.com` como destinatario:</span><span class="sxs-lookup"><span data-stu-id="0f82d-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="0f82d-134">Arrastre y coloque el mensaje con identificación indebido en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f82d-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="0f82d-135">De este modo, se guardará el mensaje identificado indebido como datos adjuntos en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f82d-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="0f82d-136">No copie y pegue el contenido del mensaje o lo reenvíe (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).</span><span class="sxs-lookup"><span data-stu-id="0f82d-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="0f82d-137">Puede adjuntar varios mensajes en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f82d-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="0f82d-138">Asegúrese de que todos los mensajes sean del mismo tipo: mensajes de suplantación de identidad o mensajes de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="0f82d-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="0f82d-139">Deje el cuerpo del nuevo mensaje en blanco.</span><span class="sxs-lookup"><span data-stu-id="0f82d-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="0f82d-140">Use cualquiera de los formatos. msg (formato predeterminado de Outlook) o. eml (formato predeterminado de Outlook en la web) para los mensajes adjuntos.</span><span class="sxs-lookup"><span data-stu-id="0f82d-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="0f82d-141">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="0f82d-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="0f82d-142">Los administradores tienen varias formas diferentes de permitir que mensajes específicos omitan el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="0f82d-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="0f82d-143">Para obtener más información, consulte [Create Safe Sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0f82d-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="0f82d-144">Crear una regla de flujo de correo para recibir copias de mensajes que se notifican a Microsoft</span><span class="sxs-lookup"><span data-stu-id="0f82d-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="0f82d-145">Para obtener instrucciones, vea [usar reglas de flujo de correo para ver qué están notificando los usuarios a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="0f82d-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
