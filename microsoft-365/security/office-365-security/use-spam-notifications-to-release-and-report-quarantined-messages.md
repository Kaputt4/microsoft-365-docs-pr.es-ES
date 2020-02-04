---
title: Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
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
description: Si el administrador habilita las notificaciones para los usuarios, recibirá un mensaje de notificación que enumera los mensajes enviados a su buzón que se identificaron como correo no deseado, en masa o de suplantación de identidad. Puede liberar o informar de los mensajes después de recibir la notificación.
ms.openlocfilehash: 51fcdefc08987b153d045994927f56df3b670fd0
ms.sourcegitcommit: 836bd8135cc49d6db37e78a7cfeb7d2cc4159e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722041"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="472d9-104">Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365</span><span class="sxs-lookup"><span data-stu-id="472d9-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="472d9-105">Si el administrador habilita las notificaciones de correo no deseado para los usuarios, recibirá un mensaje de notificación que enumera los mensajes dirigidos a su buzón que se identificaron como correo no deseado, en masa o de phish y se pusieron en cuarentena en su lugar.</span><span class="sxs-lookup"><span data-stu-id="472d9-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam, bulk, or phish and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="472d9-106">Si es administrador y desea habilitar esta característica, puede elegir la opción cuando [modifique una directiva contra correo no deseado predeterminada](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="472d9-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="472d9-107">El mensaje que recibe incluye el número de mensajes de correo no deseado en cuarentena que tiene, y la fecha y la hora (en UTC universal coordinada o UTC) del último mensaje de la lista.</span><span class="sxs-lookup"><span data-stu-id="472d9-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="472d9-108">En la lista se incluyen los siguientes elementos para cada mensaje:</span><span class="sxs-lookup"><span data-stu-id="472d9-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="472d9-109">**Remitente** El nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="472d9-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="472d9-110">**Asunto** El texto de la línea de asunto del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="472d9-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="472d9-111">**Fecha** La fecha y hora (en UTC) en que el mensaje fue colocado en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="472d9-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="472d9-112">Estas son las acciones que puede llevar a cabo con un mensaje en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="472d9-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="472d9-113">**Bloquear remitente** si desea que Office 365 agregue el remitente a la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="472d9-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="472d9-114">**Release** si el mensaje no es correo no deseado y desea que Office 365 envíe el mensaje al buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="472d9-114">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="472d9-115">**Revise** para navegar al portal de cuarentena en el centro de seguridad y cumplimiento si desea realizar otras acciones, como la versión preliminar o la versión.</span><span class="sxs-lookup"><span data-stu-id="472d9-115">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="472d9-116">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="472d9-116">Be aware of the following:</span></span>

- <span data-ttu-id="472d9-117">Malware y mensajes de suplantación de identidad de alta confianza que se ponen en cuarentena porque coinciden con una regla de flujo de correo no se incluyen en las notificaciones de correo no deseado del usuario.</span><span class="sxs-lookup"><span data-stu-id="472d9-117">Malware and high confidence phishing messages and messages that are quarantined because they matched a mail flow rule are not included in user spam notifications.</span></span> 

- <span data-ttu-id="472d9-118">Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.</span><span class="sxs-lookup"><span data-stu-id="472d9-118">You can only release a message and report it as a false positive (not junk) once.</span></span>
