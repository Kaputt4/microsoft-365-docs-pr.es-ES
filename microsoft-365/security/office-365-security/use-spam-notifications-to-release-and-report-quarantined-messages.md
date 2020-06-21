---
title: Notificaciones de correo no deseado para el usuario final en Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las notificaciones de correo no deseado para el usuario final sobre los mensajes en cuarentena de Exchange Online Protection (EOP).
ms.openlocfilehash: 14dcdfa8373e3826b23bc5574d1b5ae8ff76927b
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754789"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="75b84-103">Usar notificaciones de correo no deseado de usuario para liberar y notificar mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="75b84-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="75b84-104">En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados.</span><span class="sxs-lookup"><span data-stu-id="75b84-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="75b84-105">Para obtener más información, vea [mensajes en cuarentena en EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="75b84-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="75b84-106">De forma predeterminada, las notificaciones de correo no deseado para el usuario final están deshabilitadas en las directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="75b84-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="75b84-107">Cuando un administrador [habilita las notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), los destinatarios (incluidos los buzones compartidos) recibirán notificaciones periódicas sobre sus mensajes que se pusieron en cuarentena como correo no deseado, correo electrónico masivo o (a partir de abril de 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="75b84-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="75b84-108">Los mensajes que se pusieron en cuarentena como suplantación de identidad de alta confianza, malware o reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores.</span><span class="sxs-lookup"><span data-stu-id="75b84-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="75b84-109">Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="75b84-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="75b84-110">Una notificación de correo no deseado para el usuario final contiene la siguiente información para cada mensaje en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="75b84-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="75b84-111">**Sender**: el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="75b84-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="75b84-112">**Asunto**: el texto de la línea de asunto del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="75b84-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="75b84-113">**Fecha**: la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="75b84-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="75b84-114">**Bloquear remitente**: haga clic en este vínculo para agregar el remitente a la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="75b84-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="75b84-115">Para obtener más información, vea [bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="75b84-115">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="75b84-116">**Liberar**: para los mensajes de correo no deseado (no phish), puede liberar el mensaje aquí sin ir a cuarentena en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="75b84-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="75b84-117">**Revisión**: haga clic en este vínculo para ir a cuarentena en el centro de seguridad & cumplimiento, donde puede liberar, eliminar o informar de los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="75b84-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="75b84-118">Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="75b84-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)
