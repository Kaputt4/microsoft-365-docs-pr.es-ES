---
title: Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365
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
ms.openlocfilehash: 7042f847dbc8df9d60efc694a07a258eff411f6d
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772214"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="12d3b-104">Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365</span><span class="sxs-lookup"><span data-stu-id="12d3b-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="12d3b-105">Si su administrador habilita las notificaciones de correo no deseado para los usuarios, recibirá un mensaje de notificación que enumera los mensajes dirigidos a su buzón que se identificaron como correo no deseado y que se ponen en cuarentena en su lugar.</span><span class="sxs-lookup"><span data-stu-id="12d3b-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="12d3b-106">Si es administrador y desea habilitar esta característica, puede elegir la opción cuando [modifique una directiva contra correo no deseado predeterminada](https://go.microsoft.com/fwlink/?LinkId=800313).</span><span class="sxs-lookup"><span data-stu-id="12d3b-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="12d3b-107">El mensaje que recibe incluye el número de mensajes de correo no deseado en cuarentena que tiene, y la fecha y la hora (en UTC universal coordinada o UTC) del último mensaje de la lista.</span><span class="sxs-lookup"><span data-stu-id="12d3b-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="12d3b-108">En la lista se incluyen los siguientes elementos para cada mensaje:</span><span class="sxs-lookup"><span data-stu-id="12d3b-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="12d3b-109">**Remitente** El nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="12d3b-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="12d3b-110">**Asunto** El texto de la línea de asunto del mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="12d3b-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="12d3b-111">**Fecha** La fecha y hora (en UTC) en que el mensaje fue colocado en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="12d3b-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>     
  
<span data-ttu-id="12d3b-112">Estas son las acciones que puede llevar a cabo con un mensaje en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="12d3b-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="12d3b-113">**Bloquear remitente** si desea que Office 365 agregue el remitente a la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="12d3b-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="12d3b-114">**Revise** para navegar al portal de cuarentena en el centro de seguridad y cumplimiento si desea realizar otras acciones, como la versión preliminar o la versión.</span><span class="sxs-lookup"><span data-stu-id="12d3b-114">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="12d3b-115">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="12d3b-115">Be aware of the following:</span></span>
  
- <span data-ttu-id="12d3b-116">Los mensajes que se ponen en cuarentena debido a que coinciden con una regla de flujo de correo no se incluyen en los mensajes de usuario en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="12d3b-116">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="12d3b-117">Solo se enumeran los mensajes en cuarentena de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="12d3b-117">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="12d3b-118">Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.</span><span class="sxs-lookup"><span data-stu-id="12d3b-118">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

