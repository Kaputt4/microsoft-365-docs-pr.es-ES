---
title: Enviar manualmente mensajes a Microsoft para su análisis
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
description: Los administradores y los usuarios finales pueden aprender a enviar mensajes de correo electrónico (correo bueno marcado como correo no deseado o no permitido) a Microsoft para su análisis.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5d3b7a51c39b85af8a6fae84f525da6d806789c
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029589"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="b0193-103">Enviar manualmente mensajes a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="b0193-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="b0193-104">Si es administrador de una organización con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b0193-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="b0193-105">Para obtener más información, vea Usar envío de administrador para enviar correos sospechosos de correo no [deseado, phishing, direcciones URL y archivos a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="b0193-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="b0193-106">Puede resultar frustrante cuando los usuarios de su organización reciben mensajes de correo no deseado o mensajes de suplantación de identidad en su Bandeja de entrada, o si no reciben un mensaje de correo electrónico legítimo porque está marcado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b0193-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="b0193-107">Estamos ajustando constantemente nuestros filtros de correo no deseado para que sean más precisos.</span><span class="sxs-lookup"><span data-stu-id="b0193-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="b0193-108">Usted y sus usuarios pueden ayudar a este proceso enviando falsos positivos (correo electrónico bueno marcado como falso), falsos negativos (correo no deseado permitido) y mensajes de suplantación de identidad a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="b0193-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="b0193-109">Debido al gran volumen de envíos que recibimos, es posible que no podamos responder a todas las solicitudes de análisis.</span><span class="sxs-lookup"><span data-stu-id="b0193-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="b0193-110">Enviar falsos negativos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0193-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="b0193-111">En lugar de usar los siguientes procedimientos para informar de falsos negativos, los usuarios de Outlook y Outlook en la Web (anteriormente conocidos como Outlook Web App) pueden usar el complemento de mensaje de informe o el complemento de suplantación de identidad de informes.</span><span class="sxs-lookup"><span data-stu-id="b0193-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="b0193-112">Para obtener información acerca de cómo [](enable-the-report-message-add-in.md) instalar y usar estas herramientas, vea Habilitar el complemento De informe de mensajes y Habilitar el complemento de suplantación de identidad [de informes.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="b0193-112">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="b0193-113">Si recibe un mensaje que pasó por el filtrado de correo no deseado que debería haber sido identificado como correo no deseado o suplantación de identidad, puede enviar el mensaje a los equipos de análisis de correo no deseado de Microsoft y análisis de suplantación de identidad de Microsoft según corresponda.</span><span class="sxs-lookup"><span data-stu-id="b0193-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="b0193-114">Los analistas revisarán el mensaje y lo agregarán a los filtros de todo el servicio si cumplen los criterios de clasificación.</span><span class="sxs-lookup"><span data-stu-id="b0193-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="b0193-115">Cree un nuevo mensaje de correo electrónico en blanco con uno de los siguientes destinatarios:</span><span class="sxs-lookup"><span data-stu-id="b0193-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="b0193-116">**Correo no deseado:**`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="b0193-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="b0193-117">**Suplantación de identidad**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="b0193-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="b0193-118">Arrastre y coloque el mensaje de correo no deseado o de suplantación de identidad en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="b0193-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="b0193-119">Esto guardará el mensaje de correo no deseado o de suplantación de identidad (phishing) como datos adjuntos en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="b0193-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="b0193-120">No copie ni pegue el contenido del mensaje ni reenvía el mensaje (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).</span><span class="sxs-lookup"><span data-stu-id="b0193-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="b0193-121">Puede adjuntar varios mensajes en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="b0193-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="b0193-122">Asegúrese de que todos los mensajes son del mismo tipo: mensajes de suplantación de identidad o mensajes de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b0193-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="b0193-123">Deje el cuerpo del nuevo mensaje en blanco.</span><span class="sxs-lookup"><span data-stu-id="b0193-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="b0193-124">Use los formatos .msg (formato predeterminado de Outlook) o .eml (formato predeterminado de Outlook en la Web) para los mensajes adjuntos.</span><span class="sxs-lookup"><span data-stu-id="b0193-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="b0193-125">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b0193-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="b0193-126">Los administradores tienen varias formas diferentes de bloquear mensajes específicos que se están identificar erróneamente como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b0193-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="b0193-127">Para obtener más información, vea [Crear listas de remitentes bloqueados en EOP.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="b0193-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="b0193-128">Enviar falsos positivos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0193-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="b0193-129">En lugar de usar los siguientes procedimientos para informar de falsos positivos, los usuarios de Outlook y Outlook en la Web (anteriormente conocidos como Outlook Web App) pueden usar el complemento de mensaje de informe o el complemento de suplantación de identidad de informes.</span><span class="sxs-lookup"><span data-stu-id="b0193-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="b0193-130">Para obtener información acerca de cómo [](enable-the-report-message-add-in.md) instalar y usar estas herramientas, vea Habilitar el complemento Mensaje de informe y Habilitar el complemento de suplantación de identidad [de informes.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="b0193-130">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="b0193-131">Si un mensaje se identificó incorrectamente como correo no deseado, puede enviarlo al equipo de análisis de correo no deseado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0193-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="b0193-132">Los analistas evaluarán el mensaje y, según los resultados del análisis, los filtros de todo el servicio se pueden ajustar para permitir que pase el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b0193-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="b0193-133">Cree un nuevo mensaje de correo electrónico en blanco `not_junk@office365.microsoft.com` con el destinatario:</span><span class="sxs-lookup"><span data-stu-id="b0193-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="b0193-134">Arrastre y coloque el mensaje identificado erróneamente en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="b0193-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="b0193-135">Esto guardará el mensaje identificado erróneamente como datos adjuntos en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="b0193-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="b0193-136">No copie ni pegue el contenido del mensaje ni reenvía el mensaje (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).</span><span class="sxs-lookup"><span data-stu-id="b0193-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="b0193-137">Puede adjuntar varios mensajes en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="b0193-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="b0193-138">Asegúrese de que todos los mensajes son del mismo tipo: mensajes de suplantación de identidad o mensajes de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b0193-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="b0193-139">Deje el cuerpo del nuevo mensaje en blanco.</span><span class="sxs-lookup"><span data-stu-id="b0193-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="b0193-140">Use los formatos .msg (formato predeterminado de Outlook) o .eml (formato predeterminado de Outlook en la Web) para los mensajes adjuntos.</span><span class="sxs-lookup"><span data-stu-id="b0193-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="b0193-141">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b0193-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="b0193-142">Los administradores tienen varias formas diferentes de permitir que mensajes específicos omitan el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b0193-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="b0193-143">Para obtener más información, [vea Crear listas de remitentes seguros en EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="b0193-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="b0193-144">¿Dónde se almacenan los datos de los envíos a Microsoft?</span><span class="sxs-lookup"><span data-stu-id="b0193-144">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="b0193-145">Los datos residen en el límite de cumplimiento de Office 365 en los centros de datos de Norteamérica.</span><span class="sxs-lookup"><span data-stu-id="b0193-145">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="b0193-146">Los analistas del equipo de ingeniería revisan los datos para ayudar a mejorar la eficacia de los filtros.</span><span class="sxs-lookup"><span data-stu-id="b0193-146">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="b0193-147">Crear una regla de flujo de correo para recibir copias de los mensajes que se notifican a Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0193-147">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="b0193-148">Para obtener instrucciones, consulte Usar reglas de flujo de correo para ver lo que los [usuarios están informando a Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="b0193-148">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
