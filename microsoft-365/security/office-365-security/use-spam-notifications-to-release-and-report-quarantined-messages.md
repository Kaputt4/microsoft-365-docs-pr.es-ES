---
title: Notificaciones de correo no deseado para el usuario final en Office 36
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
description: Cuando un administrador habilita las notificaciones de correo no deseado para el usuario final en las directivas contra correo no deseado, los destinatarios del mensaje recibirán notificaciones periódicas sobre los mensajes en cuarentena.
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895064"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="1425f-103">Notificaciones de correo no deseado para el usuario final en Office 365</span><span class="sxs-lookup"><span data-stu-id="1425f-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="1425f-104">La cuarentena retiene los mensajes que pueden ser peligrosos o no deseados en las organizaciones de Office 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1425f-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="1425f-105">Para obtener más información, consulte [Cuarentena en Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="1425f-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="1425f-106">De forma predeterminada, las notificaciones de correo no deseado para el usuario final están deshabilitadas en las directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="1425f-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="1425f-107">Cuando un administrador [habilita las notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md), los destinatarios del mensaje recibirán notificaciones periódicas sobre sus mensajes que se pusieron en cuarentena como correo no deseado, correo electrónico masivo o (a partir de abril de 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="1425f-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="1425f-108">En octubre de 2019, eliminamos la capacidad de liberar los mensajes en cuarentena directamente de las notificaciones de correo no deseado para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="1425f-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="1425f-109">En su lugar, ahora los usuarios pueden ir al centro de cumplimiento de & de seguridad de Office 365 para liberar sus mensajes en cuarentena (ya sea directamente o haciendo clic en **revisar** en la notificación).</span><span class="sxs-lookup"><span data-stu-id="1425f-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="1425f-110">Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="1425f-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="1425f-111">Los mensajes que se pusieron en cuarentena como suplantación de identidad de alta confianza, malware o reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores.</span><span class="sxs-lookup"><span data-stu-id="1425f-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="1425f-112">Para obtener más información, consulte [Manage Quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="1425f-112">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="1425f-113">Una notificación de correo no deseado para el usuario final contiene la siguiente información para cada mensaje en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="1425f-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="1425f-114">**Sender**: el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="1425f-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="1425f-115">**Asunto**: el texto de la línea de asunto del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="1425f-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="1425f-116">**Fecha**: la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="1425f-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="1425f-117">**Bloquear remitente**: haga clic en este vínculo para agregar el remitente a la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="1425f-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="1425f-118">**Revisión**: haga clic en este vínculo para ir a la cuarentena en el centro de seguridad & cumplimiento, donde puede liberar, eliminar o informar de los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="1425f-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)
