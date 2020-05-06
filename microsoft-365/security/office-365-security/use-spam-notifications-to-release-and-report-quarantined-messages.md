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
description: En este artículo, obtendrá información sobre las notificaciones de correo no deseado para el usuario final para los mensajes en cuarentena.
ms.openlocfilehash: 2a865130bf1fa0c09b5b68254fb604795b204c22
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035003"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="49362-103">Usar notificaciones de correo no deseado de usuario para liberar y notificar mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="49362-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="49362-104">La cuarentena retiene los mensajes que pueden ser peligrosos o no deseados en las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="49362-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="49362-105">Para obtener más información, consulte [Cuarentena en Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="49362-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="49362-106">De forma predeterminada, las notificaciones de correo no deseado para el usuario final están deshabilitadas en las directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="49362-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="49362-107">Cuando un administrador [habilita las notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), los destinatarios recibirán notificaciones periódicas sobre sus mensajes que se pusieron en cuarentena como correo no deseado, correo electrónico masivo o (a partir de abril de 2020) suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="49362-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="49362-108">Los mensajes que se pusieron en cuarentena como suplantación de identidad de alta confianza, malware o reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores.</span><span class="sxs-lookup"><span data-stu-id="49362-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="49362-109">Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="49362-109">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="49362-110">Una notificación de correo no deseado para el usuario final contiene la siguiente información para cada mensaje en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="49362-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="49362-111">**Sender**: el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="49362-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="49362-112">**Asunto**: el texto de la línea de asunto del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="49362-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="49362-113">**Fecha**: la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="49362-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="49362-114">**Bloquear remitente**: haga clic en este vínculo para agregar el remitente a la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="49362-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="49362-115">Para obtener más información, vea [bloquear un remitente de correo en Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="49362-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="49362-116">**Liberar**: para los mensajes de correo no deseado (no phish), puede liberar el mensaje aquí sin ir a cuarentena en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="49362-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="49362-117">**Revisión**: haga clic en este vínculo para ir a cuarentena en el centro de seguridad & cumplimiento, donde puede liberar, eliminar o informar de los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="49362-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="49362-118">Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="49362-118">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)
