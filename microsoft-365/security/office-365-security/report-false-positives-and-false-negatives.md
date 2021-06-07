---
title: Informar de falsos positivos y falsos negativos en Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo notificar falsos positivos y falsos negativos en Outlook la característica Mensaje de informe.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 84a5b697f8a4b46cf79c542485bfafb396328f5c
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789248"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="c5f4d-103">Informar de falsos positivos y falsos negativos en Outlook</span><span class="sxs-lookup"><span data-stu-id="c5f4d-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c5f4d-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="c5f4d-104">**Applies to**</span></span>
- [<span data-ttu-id="c5f4d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c5f4d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c5f4d-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c5f4d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c5f4d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5f4d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="c5f4d-108">Si es administrador de una organización Microsoft 365 con buzones de correo Exchange Online, se recomienda usar el portal de envíos en el Centro de seguridad y & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c5f4d-109">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c5f4d-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c5f4d-110">En las organizaciones de Microsoft 365 con buzones en buzones de Exchange Online o locales mediante autenticación moderna híbrida, puede enviar falsos positivos (correo electrónico bueno bloqueado o enviado a la carpeta no deseado) y falsos negativos (correo electrónico no deseado o suplantación de identidad que se entregó a la bandeja de entrada) a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="c5f4d-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c5f4d-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="c5f4d-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c5f4d-112">Para obtener la mejor experiencia de envío de usuario, use el complemento Report Message o el complemento Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c5f4d-113">La experiencia integrada para informar de correo no deseado o suplantación de identidad en Outlook no puede usar la [directiva de envío de usuario](./user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c5f4d-113">The built-in experience for reporting junk or phishing in Outlook can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="c5f4d-114">Se recomienda usar el complemento Report Message o el complemento Report Phishing en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-114">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

- <span data-ttu-id="c5f4d-115">El complemento Report Message y el complemento Report Phishing funcionan para Outlook en todas las plataformas (Outlook en la web, iOS, Android y Escritorio).</span><span class="sxs-lookup"><span data-stu-id="c5f4d-115">The the Report Message add-in and the Report Phishing add-in work for Outlook in all platforms (Outlook on the web, iOS, Android, and Desktop).</span></span>

- <span data-ttu-id="c5f4d-116">Si es administrador de una organización con buzones de correo Exchange Online, use el portal de envíos en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-116">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c5f4d-117">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c5f4d-117">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="c5f4d-118">Puede configurar para enviar mensajes directamente a Microsoft, un buzón que especifique o ambos.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-118">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="c5f4d-119">Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c5f4d-119">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c5f4d-120">Para obtener más información sobre cómo obtener y habilitar el mensaje de informe o los complementos de suplantación de identidad de informes, vea Habilitar el mensaje de informe o los complementos de suplantación [de identidad de informe](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="c5f4d-120">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="c5f4d-121">Para obtener más información acerca de cómo notificar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c5f4d-121">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="c5f4d-122">Usar la característica Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="c5f4d-122">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="c5f4d-123">Notificar mensajes de correo no deseado y suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="c5f4d-123">Report junk and phishing messages</span></span>

<span data-ttu-id="c5f4d-124">Para los mensajes de la Bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo no deseado, use el siguiente método para notificar mensajes de correo no deseado y suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="c5f4d-124">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="c5f4d-125">Seleccione los **puntos suspensivos** Más acciones en la  esquina superior derecha del mensaje seleccionado, seleccione Informar del mensaje en el menú desplegable y, a continuación, seleccione Correo no deseado **o** **Suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-125">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   ![Mensaje de informe: más acciones](../../media/report-message-more-actions.png)
   
   ![Mensaje de informe: correo no deseado y suplantación de identidad](../../media/report-message-junk-phishing.png)

2. <span data-ttu-id="c5f4d-128">Los mensajes seleccionados se enviarán a Microsoft para su análisis y:</span><span class="sxs-lookup"><span data-stu-id="c5f4d-128">The selected messages will be sent to Microsoft for analysis and:</span></span>
   - <span data-ttu-id="c5f4d-129">Se ha movido a la carpeta correo no deseado si se han notificado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-129">Moved to the Junk Email folder if they were reported as spam.</span></span>
   - <span data-ttu-id="c5f4d-130">Se elimina si se han notificado como suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-130">Deleted if they were reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="c5f4d-131">Informar de mensajes que no son correo no deseado</span><span class="sxs-lookup"><span data-stu-id="c5f4d-131">Report messages that are not junk</span></span>

1. <span data-ttu-id="c5f4d-132">Seleccione los **puntos suspensivos** Más acciones en la  esquina superior derecha del mensaje seleccionado, seleccione Informar mensaje en el menú desplegable y, a continuación, **seleccione No deseado**.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-132">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Not Junk**.</span></span>

   ![Mensaje de informe: más acciones](../../media/report-message-more-actions.png)
   
   ![Mensaje de informe: no deseado](../../media/report-message-not-junk.png)

2. <span data-ttu-id="c5f4d-135">El mensaje seleccionado se enviará a Microsoft para su análisis y se trasladará a la Bandeja de entrada o a cualquier otra carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-135">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="c5f4d-136">Ver y revisar los mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="c5f4d-136">View and review reported messages</span></span>

<span data-ttu-id="c5f4d-137">Para revisar los mensajes que los usuarios informan a Microsoft, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="c5f4d-137">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="c5f4d-138">Use el portal de envíos de administrador.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-138">Use the Admin Submissions portal.</span></span> <span data-ttu-id="c5f4d-139">Para obtener más información, vea [Ver envíos de usuarios a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c5f4d-139">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>
- <span data-ttu-id="c5f4d-140">Cree una regla de flujo de correo (también conocida como regla de transporte) para enviar copias de los mensajes notificados.</span><span class="sxs-lookup"><span data-stu-id="c5f4d-140">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="c5f4d-141">Para obtener instrucciones, vea [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c5f4d-141">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
