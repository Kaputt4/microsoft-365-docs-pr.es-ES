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
ms.openlocfilehash: e848595035501f5da7b6099efd2700ebac6f17e3
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291168"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="e0420-103">Informar de falsos positivos y falsos negativos en Outlook</span><span class="sxs-lookup"><span data-stu-id="e0420-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e0420-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="e0420-104">**Applies to**</span></span>
- [<span data-ttu-id="e0420-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e0420-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e0420-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0420-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e0420-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0420-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="e0420-108">Si es administrador de una organización Microsoft 365 con buzones de correo Exchange Online, se recomienda usar el portal de envíos en el Centro de seguridad y & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e0420-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e0420-109">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e0420-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="e0420-110">En las organizaciones de Microsoft 365 con buzones en buzones de Exchange Online o locales mediante autenticación moderna híbrida, puede enviar falsos positivos (correo electrónico bueno bloqueado o enviado a la carpeta no deseado) y falsos negativos (correo electrónico no deseado o suplantación de identidad que se entregó a la bandeja de entrada) a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="e0420-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e0420-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="e0420-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e0420-112">Para obtener la mejor experiencia de envío de usuario, use el complemento Report Message o el complemento Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="e0420-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="e0420-113">Tenga en cuenta que este complemento funciona Outlook en todas las plataformas: en la web, iOS, Android y Escritorio.</span><span class="sxs-lookup"><span data-stu-id="e0420-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="e0420-114">Si es administrador de una organización con buzones de correo Exchange Online, use el portal de envíos en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e0420-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e0420-115">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e0420-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="e0420-116">Puede configurar para enviar mensajes directamente a Microsoft, un buzón que especifique o ambos.</span><span class="sxs-lookup"><span data-stu-id="e0420-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="e0420-117">Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e0420-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="e0420-118">Para obtener más información sobre cómo obtener y habilitar el mensaje de informe o los complementos de suplantación de identidad de informes, vea Habilitar el mensaje de informe o los complementos de suplantación [de identidad de informe](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="e0420-118">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="e0420-119">Para obtener más información acerca de cómo notificar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e0420-119">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="e0420-120">Usar la característica Mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="e0420-120">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="e0420-121">Notificar mensajes de correo no deseado y suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="e0420-121">Report junk and phishing messages</span></span>

<span data-ttu-id="e0420-122">Para los mensajes de la Bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo no deseado, use el siguiente método para notificar mensajes de correo no deseado y suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="e0420-122">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="e0420-123">Haga clic en **los** puntos suspensivos Más acciones  de la esquina superior derecha  del mensaje seleccionado, haga clic en Informar mensaje en el menú desplegable y, a continuación, seleccione Correo no deseado o **Suplantación de identidad**.</span><span class="sxs-lookup"><span data-stu-id="e0420-123">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0420-124">![Mensaje de informe: más acciones](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="e0420-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0420-125">![Mensaje de informe: correo no deseado y suplantación de identidad](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="e0420-125">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="e0420-126">Los mensajes seleccionados se enviarán a Microsoft para su análisis y:</span><span class="sxs-lookup"><span data-stu-id="e0420-126">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="e0420-127">Se ha movido a la carpeta correo no deseado si se ha notificado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="e0420-127">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="e0420-128">Se elimina si se ha notificado como suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e0420-128">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="e0420-129">Informar de mensajes que no son correo no deseado</span><span class="sxs-lookup"><span data-stu-id="e0420-129">Report messages that are not junk</span></span>

1. <span data-ttu-id="e0420-130">Haga clic **en los** puntos suspensivos Más acciones  de la esquina superior derecha del mensaje seleccionado, haga clic en Informar mensaje en el menú desplegable y, a continuación, haga clic en **No deseado**.</span><span class="sxs-lookup"><span data-stu-id="e0420-130">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0420-131">![Mensaje de informe: más acciones](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="e0420-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0420-132">![Mensaje de informe: no deseado](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="e0420-132">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="e0420-133">El mensaje seleccionado se enviará a Microsoft para su análisis y se trasladará a la Bandeja de entrada o a cualquier otra carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="e0420-133">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="e0420-134">Ver y revisar los mensajes notificados</span><span class="sxs-lookup"><span data-stu-id="e0420-134">View and review reported messages</span></span>

<span data-ttu-id="e0420-135">Para revisar los mensajes que los usuarios informan a Microsoft, tiene estas opciones:</span><span class="sxs-lookup"><span data-stu-id="e0420-135">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="e0420-136">Use el portal de envíos de administrador.</span><span class="sxs-lookup"><span data-stu-id="e0420-136">Use the Admin Submissions portal.</span></span> <span data-ttu-id="e0420-137">Para obtener más información, vea [Ver envíos de usuarios a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="e0420-137">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="e0420-138">Cree una regla de flujo de correo (también conocida como regla de transporte) para enviar copias de los mensajes notificados.</span><span class="sxs-lookup"><span data-stu-id="e0420-138">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="e0420-139">Para obtener instrucciones, consulte [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e0420-139">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>