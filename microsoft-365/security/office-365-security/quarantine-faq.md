---
title: Preguntas más frecuentes sobre la cuarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Respuestas a las preguntas más frecuentes acerca de la cuarentena en Office 365.
ms.openlocfilehash: 58800d5645241c2115356bc9899ce53302d1e37e
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856910"
---
# <a name="quarantine-faq-in-office-365"></a><span data-ttu-id="49a7f-103">Preguntas más frecuentes sobre la cuarentena en Office 365</span><span class="sxs-lookup"><span data-stu-id="49a7f-103">Quarantine FAQ in Office 365</span></span>

<span data-ttu-id="49a7f-104">En este tema se proporcionan preguntas frecuentes y respuestas sobre la cuarentena para los clientes de Office 365 con buzones en Exchange online o los clientes independientes de Exchange Online Protection (EOP) sin buzones de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="49a7f-104">This topic provides frequently asked questions and answers about quarantine for Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="49a7f-105">P: ¿Cómo puedo administrar los mensajes que se pusieron en cuarentena para malware?</span><span class="sxs-lookup"><span data-stu-id="49a7f-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="49a7f-106">Solo los administradores pueden administrar los mensajes que se pusieron en cuarentena para obtener malware.</span><span class="sxs-lookup"><span data-stu-id="49a7f-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="49a7f-107">Para obtener más información, consulte [Manage Quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="49a7f-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="49a7f-108">P: ¿Cómo puedo poner en cuarentena el correo no deseado?</span><span class="sxs-lookup"><span data-stu-id="49a7f-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="49a7f-109">A.</span><span class="sxs-lookup"><span data-stu-id="49a7f-109">A.</span></span> <span data-ttu-id="49a7f-110">De forma predeterminada, los mensajes clasificados como correo no deseado o correo masivo por filtrado de correo no deseado se entregan al buzón del usuario y se mueven a la carpeta correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="49a7f-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="49a7f-111">Pero puede crear y configurar directivas contra correo no deseado para poner en cuarentena correo no deseado o mensajes de correo electrónico masivo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="49a7f-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="49a7f-112">Para obtener más información, vea [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="49a7f-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="49a7f-113">P: ¿cómo se concede a los usuarios acceso a la cuarentena?</span><span class="sxs-lookup"><span data-stu-id="49a7f-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="49a7f-114">A.</span><span class="sxs-lookup"><span data-stu-id="49a7f-114">A.</span></span> <span data-ttu-id="49a7f-115">Un usuario debe tener una cuenta válida para tener acceso a sus propios mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="49a7f-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="49a7f-116">EOP independiente requiere que los usuarios se representen como usuarios de correo en EOP (creados o creados manualmente mediante la sincronización de directorios).</span><span class="sxs-lookup"><span data-stu-id="49a7f-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="49a7f-117">Para obtener más información acerca de la administración de usuarios en entornos de EOP independientes, vea [Manage Mail Users in EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="49a7f-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="49a7f-118">P: ¿qué mensajes pueden hacer que los usuarios finales tengan acceso en cuarentena?</span><span class="sxs-lookup"><span data-stu-id="49a7f-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="49a7f-119">A.</span><span class="sxs-lookup"><span data-stu-id="49a7f-119">A.</span></span> <span data-ttu-id="49a7f-120">Los usuarios pueden tener acceso a correo no deseado, correo electrónico masivo y (a partir de abril de 2020) mensajes de suplantación de identidad (phishing) cuando son destinatarios.</span><span class="sxs-lookup"><span data-stu-id="49a7f-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="49a7f-121">Los usuarios finales no pueden acceder a malware en cuarentena, phishing de alta confianza o mensajes que se pusieron en cuarentena debido **a la entrega del mensaje a la acción de cuarentena hospedada** en reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="49a7f-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="49a7f-122">Para obtener más información sobre los usuarios que tienen acceso a los mensajes en cuarentena, vea [Find and Release Quarantined messages as a User in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="49a7f-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="49a7f-123">P: ¿Cuánto tiempo se conservan los mensajes en cuarentena?</span><span class="sxs-lookup"><span data-stu-id="49a7f-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="49a7f-124">A.</span><span class="sxs-lookup"><span data-stu-id="49a7f-124">A.</span></span> <span data-ttu-id="49a7f-125">Puede configurar el tiempo que se conservan los mensajes de correo electrónico masivo, de suplantación de identidad (phishing) y masivo en cuarentena mediante directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="49a7f-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="49a7f-126">El valor predeterminado es 30 días, que es también el máximo.</span><span class="sxs-lookup"><span data-stu-id="49a7f-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="49a7f-127">Para obtener más información, vea [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="49a7f-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="49a7f-128">Para los mensajes puestos en cuarentena por la acción de regla de flujo de correo **Enviar el mensaje a la cuarentena hospedada**, los mensajes se mantienen en cuarentena durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="49a7f-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="49a7f-129">No puede configurar esta duración.</span><span class="sxs-lookup"><span data-stu-id="49a7f-129">You can't configure this duration.</span></span>

<span data-ttu-id="49a7f-130">Una vez transcurrido el período de tiempo, los mensajes se eliminan y no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="49a7f-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="49a7f-131">P: ¿puedo liberar o informar de más de un mensaje en cuarentena a la vez?</span><span class="sxs-lookup"><span data-stu-id="49a7f-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="49a7f-132">A.</span><span class="sxs-lookup"><span data-stu-id="49a7f-132">A.</span></span> <span data-ttu-id="49a7f-133">En el centro de seguridad & cumplimiento, puede seleccionar y publicar hasta 100 mensajes a la vez.</span><span class="sxs-lookup"><span data-stu-id="49a7f-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="49a7f-134">Los administradores pueden usar los cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) y [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) en Exchange Online PowerShell o PowerShell independiente de Exchange Online Protection para buscar y liberar mensajes en cuarentena de forma masiva y para informar de falsos positivos en masa.</span><span class="sxs-lookup"><span data-stu-id="49a7f-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="49a7f-135">P: ¿se admiten caracteres comodín al buscar mensajes en cuarentena?</span><span class="sxs-lookup"><span data-stu-id="49a7f-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="49a7f-136">¿Puedo buscar mensajes en cuarentena para un dominio específico?</span><span class="sxs-lookup"><span data-stu-id="49a7f-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="49a7f-137">A.</span><span class="sxs-lookup"><span data-stu-id="49a7f-137">A.</span></span> <span data-ttu-id="49a7f-138">No se admiten caracteres comodín en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="49a7f-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="49a7f-139">Por ejemplo, al buscar un remitente, debe especificar la dirección de correo electrónico completa.</span><span class="sxs-lookup"><span data-stu-id="49a7f-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="49a7f-140">Pero, puede usar caracteres comodín en PowerShell de Exchange online o Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="49a7f-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="49a7f-141">Por ejemplo, ejecute el siguiente comando para buscar mensajes de correo no deseado en cuarentena de todos los remitentes en el dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="49a7f-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="49a7f-142">A continuación, ejecute el siguiente comando para liberar los mensajes a todos los destinatarios originales:</span><span class="sxs-lookup"><span data-stu-id="49a7f-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $CQ.Identity -ReleaseToAll}
```

<span data-ttu-id="49a7f-143">Después de liberar un mensaje, no podrá volver a publicarlo.</span><span class="sxs-lookup"><span data-stu-id="49a7f-143">After you release a message, you can't release it again.</span></span>
