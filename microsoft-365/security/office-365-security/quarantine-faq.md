---
title: Preguntas más frecuentes sobre los mensajes en cuarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
description: Los administradores pueden ver las preguntas más frecuentes y las respuestas sobre los mensajes en cuarentena en Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00768b3584c854ef0648f75f1966a8fa331b2866
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413429"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="4638d-103">Preguntas más frecuentes sobre los mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="4638d-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4638d-104">En este tema se proporcionan preguntas frecuentes y respuestas sobre los mensajes de correo electrónico en cuarentena para organizaciones de Microsoft 365 con buzones en Exchange online o con organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4638d-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="4638d-105">Para preguntas y respuestas sobre la protección contra correo no deseado, consulte [preguntas más frecuentes sobre protección contra correo no deseado](anti-spam-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="4638d-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="4638d-106">Para preguntas y respuestas sobre la protección antimalware, consulte [preguntas más frecuentes sobre la protección contra malware](anti-malware-protection-faq-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4638d-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="4638d-107">Para obtener preguntas y respuestas sobre la protección contra la suplantación de identidad, vea [preguntas más frecuentes sobre protección contra la suplantación de identidad](anti-spoofing-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="4638d-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="4638d-108">¿Cómo se administran los mensajes que se pusieron en cuarentena para malware?</span><span class="sxs-lookup"><span data-stu-id="4638d-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="4638d-109">Solo los administradores pueden administrar los mensajes que se pusieron en cuarentena para obtener malware.</span><span class="sxs-lookup"><span data-stu-id="4638d-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="4638d-110">Para obtener más información, consulte [Manage Quarantined messages and files as a admin](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="4638d-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="4638d-111">¿Cómo puedo poner en cuarentena el correo no deseado?</span><span class="sxs-lookup"><span data-stu-id="4638d-111">How do I quarantine spam?</span></span>

<span data-ttu-id="4638d-112">De forma predeterminada, los mensajes clasificados como correo no deseado o correo masivo por filtrado de correo no deseado se entregan al buzón del usuario y se mueven a la carpeta correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="4638d-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="4638d-113">Pero puede crear y configurar directivas contra correo no deseado para poner en cuarentena correo no deseado o mensajes de correo electrónico masivo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4638d-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="4638d-114">Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4638d-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="4638d-115">¿Cómo se concede a los usuarios acceso a la cuarentena?</span><span class="sxs-lookup"><span data-stu-id="4638d-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="4638d-116">Un usuario debe tener una cuenta válida para tener acceso a sus propios mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4638d-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="4638d-117">EOP independiente requiere que los usuarios se representen como usuarios de correo en EOP (creados o creados manualmente mediante la sincronización de directorios).</span><span class="sxs-lookup"><span data-stu-id="4638d-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="4638d-118">Para obtener más información acerca de la administración de usuarios en entornos de EOP independientes, vea [Manage Mail Users in EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4638d-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="4638d-119">¿Qué mensajes pueden hacer que los usuarios finales tengan acceso en cuarentena?</span><span class="sxs-lookup"><span data-stu-id="4638d-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="4638d-120">Los usuarios pueden tener acceso a correo no deseado, correo electrónico masivo y (a partir de abril de 2020) los mensajes de suplantación de identidad en los que son destinatarios.</span><span class="sxs-lookup"><span data-stu-id="4638d-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="4638d-121">Los usuarios finales no pueden acceder a malware en cuarentena, phishing de alta confianza o mensajes que se pusieron en cuarentena debido **a la entrega del mensaje a la acción de cuarentena hospedada** en reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="4638d-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="4638d-122">Para obtener más información sobre los usuarios que tienen acceso a los mensajes en cuarentena, vea [Find and Release Quarantined messages as a User](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="4638d-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="4638d-123">¿Cuánto tiempo se conservan los mensajes en cuarentena?</span><span class="sxs-lookup"><span data-stu-id="4638d-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="4638d-124">Puede configurar el tiempo que se conservan los mensajes de correo electrónico masivo, de suplantación de identidad (phishing) y masivo en cuarentena mediante directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="4638d-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="4638d-125">El valor predeterminado es 30 días, que es también el máximo.</span><span class="sxs-lookup"><span data-stu-id="4638d-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="4638d-126">Para obtener más información, vea [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="4638d-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="4638d-127">Para los mensajes puestos en cuarentena por la acción de regla de flujo de correo **Enviar el mensaje a la cuarentena hospedada**, los mensajes se mantienen en cuarentena durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="4638d-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="4638d-128">No puede configurar esta duración.</span><span class="sxs-lookup"><span data-stu-id="4638d-128">You can't configure this duration.</span></span>

<span data-ttu-id="4638d-129">Una vez transcurrido el período de tiempo, los mensajes se eliminan y no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="4638d-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="4638d-130">¿Puedo liberar o informar de más de un mensaje en cuarentena a la vez?</span><span class="sxs-lookup"><span data-stu-id="4638d-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="4638d-131">En el centro de seguridad & cumplimiento, puede seleccionar y publicar hasta 100 mensajes a la vez.</span><span class="sxs-lookup"><span data-stu-id="4638d-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="4638d-132">Los administradores pueden usar los cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) y [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) en Exchange Online PowerShell o el PowerShell independiente de EOP para buscar y liberar mensajes en cuarentena de forma masiva, así como para informar de falsos positivos en masa.</span><span class="sxs-lookup"><span data-stu-id="4638d-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="4638d-133">¿Se admiten caracteres comodín al buscar mensajes en cuarentena?</span><span class="sxs-lookup"><span data-stu-id="4638d-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="4638d-134">¿Puedo buscar mensajes en cuarentena para un dominio específico?</span><span class="sxs-lookup"><span data-stu-id="4638d-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="4638d-135">No se admiten caracteres comodín en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4638d-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="4638d-136">Por ejemplo, al buscar un remitente, debe especificar la dirección de correo electrónico completa.</span><span class="sxs-lookup"><span data-stu-id="4638d-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="4638d-137">Pero, puede usar caracteres comodín en Exchange Online PowerShell o en PowerShell de EOP independiente.</span><span class="sxs-lookup"><span data-stu-id="4638d-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="4638d-138">Por ejemplo, ejecute el siguiente comando para buscar mensajes de correo no deseado en cuarentena de todos los remitentes en el dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="4638d-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="4638d-139">A continuación, ejecute el siguiente comando para liberar los mensajes a todos los destinatarios originales:</span><span class="sxs-lookup"><span data-stu-id="4638d-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="4638d-140">Después de liberar un mensaje, no podrá volver a publicarlo.</span><span class="sxs-lookup"><span data-stu-id="4638d-140">After you release a message, you can't release it again.</span></span>
