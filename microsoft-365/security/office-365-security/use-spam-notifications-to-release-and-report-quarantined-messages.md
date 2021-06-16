---
title: Notificaciones de correo no deseado del usuario final en Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: Los administradores pueden obtener información sobre las notificaciones de correo no deseado del usuario final para mensajes en cuarentena en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 30f82abc245a2f6022bd1a75b57e9d20e3e32a32
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929892"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="50110-103">Usar notificaciones de correo no deseado de usuario para liberar e informar de mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="50110-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="50110-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="50110-104">**Applies to**</span></span>
- [<span data-ttu-id="50110-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="50110-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="50110-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="50110-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="50110-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50110-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="50110-108">En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados.</span><span class="sxs-lookup"><span data-stu-id="50110-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="50110-109">Para obtener más información, vea [Mensajes en cuarentena en EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="50110-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="50110-110">De forma predeterminada, las notificaciones de correo no deseado del usuario final están deshabilitadas en las directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="50110-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="50110-111">Cuando un administrador habilita las notificaciones de [correo](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)no deseado del usuario final, los destinatarios (incluidos los buzones compartidos con automapping habilitado) recibirán notificaciones periódicas sobre sus mensajes que se han puesto en cuarentena como correo no deseado, correo electrónico masivo o suplantación de identidad (a partir de abril de 2020).</span><span class="sxs-lookup"><span data-stu-id="50110-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="50110-112">En el caso de los buzones compartidos, las notificaciones de correo no deseado del usuario final solo se admiten para los usuarios a los que se les concede permiso FullAccess para el buzón compartido.</span><span class="sxs-lookup"><span data-stu-id="50110-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="50110-113">Para obtener más información, [vea Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span><span class="sxs-lookup"><span data-stu-id="50110-113">For more information, see [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="50110-114">La notificación de correo no deseado del usuario final no es compatible con los grupos.</span><span class="sxs-lookup"><span data-stu-id="50110-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="50110-115">Los mensajes que se han puesto en cuarentena como phishing de elevada confianza, malware o por reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores.</span><span class="sxs-lookup"><span data-stu-id="50110-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="50110-116">Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="50110-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="50110-117">Una notificación de correo no deseado del usuario final contiene la siguiente información para cada mensaje en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="50110-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="50110-118">**Remitente:** el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="50110-118">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="50110-119">**Asunto:** el texto de la línea de asunto del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="50110-119">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="50110-120">**Fecha:** la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="50110-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="50110-121">**Bloquear remitente:** haga clic en este vínculo para agregar el remitente a la lista Remitentes bloqueados del buzón.</span><span class="sxs-lookup"><span data-stu-id="50110-121">**Block Sender**: Click this link to add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="50110-122">Para más información, consulte [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="50110-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="50110-123">**Versión:** para mensajes de correo no deseado (no suplantación de identidad), puede liberar el mensaje aquí sin ir a Cuarentena del portal de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="50110-123">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Microsoft 365 Defender portal.</span></span>

- <span data-ttu-id="50110-124">**Review**: Click this link to go to Quarantine in the Microsoft 365 Defender portal, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span><span class="sxs-lookup"><span data-stu-id="50110-124">**Review**: Click this link to go to Quarantine in the Microsoft 365 Defender portal, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="50110-125">Para obtener más información, vea Buscar y liberar mensajes [en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="50110-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Ejemplo de notificación de correo no deseado para el usuario final](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="50110-127">Un remitente bloqueado aún puede enviarle correo.</span><span class="sxs-lookup"><span data-stu-id="50110-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="50110-128">Los mensajes de este remitente que se envían a su buzón se mueven inmediatamente a la carpeta Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="50110-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="50110-129">Los mensajes futuros de este remitente irán a la carpeta correo no deseado o a la cuarentena del usuario final.</span><span class="sxs-lookup"><span data-stu-id="50110-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="50110-130">Si desea eliminar estos mensajes al llegar en lugar de anularlos, use reglas de flujo de correo [(también](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) conocidas como reglas de transporte) para eliminar los mensajes al llegar.</span><span class="sxs-lookup"><span data-stu-id="50110-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>