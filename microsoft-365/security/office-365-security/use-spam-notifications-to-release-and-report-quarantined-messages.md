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
ms.openlocfilehash: 7dd6b2d14bbb4a1771c59c8a1e654e36f0f83d3e
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208554"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="07fdc-103">Usar notificaciones de correo no deseado de usuario para liberar y notificar mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="07fdc-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="07fdc-104">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, la cuarentena contiene mensajes potencialmente peligrosos o no deseados.</span><span class="sxs-lookup"><span data-stu-id="07fdc-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="07fdc-105">Para obtener más información, vea [mensajes en cuarentena en EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="07fdc-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="07fdc-106">De forma predeterminada, las notificaciones de correo no deseado para el usuario final están deshabilitadas en las directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="07fdc-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="07fdc-107">Cuando un administrador [habilita las notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), los destinatarios recibirán notificaciones periódicas acerca de sus mensajes que se pusieron en cuarentena como correo no deseado, correo electrónico masivo o (a partir de abril de 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="07fdc-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="07fdc-108">Los mensajes que se pusieron en cuarentena como suplantación de identidad de alta confianza, malware o reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores.</span><span class="sxs-lookup"><span data-stu-id="07fdc-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="07fdc-109">Para obtener más información, vea [Manage Quarantined messages and files as a admin in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="07fdc-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="07fdc-110">Una notificación de correo no deseado para el usuario final contiene la siguiente información para cada mensaje en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="07fdc-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="07fdc-111">**Sender**: el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="07fdc-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="07fdc-112">**Asunto**: el texto de la línea de asunto del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="07fdc-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="07fdc-113">**Fecha**: la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="07fdc-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="07fdc-114">**Bloquear remitente**: haga clic en este vínculo para agregar el remitente a la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="07fdc-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="07fdc-115">Para obtener más información, vea [bloquear un remitente de correo en Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="07fdc-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="07fdc-116">**Liberar**: para los mensajes de correo no deseado (no phish), puede liberar el mensaje aquí sin ir a cuarentena en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="07fdc-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="07fdc-117">**Revisión**: haga clic en este vínculo para ir a cuarentena en el centro de seguridad & cumplimiento, donde puede liberar, eliminar o informar de los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="07fdc-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="07fdc-118">Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="07fdc-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)
