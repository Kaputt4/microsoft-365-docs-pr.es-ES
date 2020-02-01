---
title: Cuarentena de mensajes de correo electrónico en Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Puede configurar una cuarentena para los mensajes de correo electrónico entrantes en Office 365 donde los mensajes de correo electrónico entrantes que se filtraron como correo no deseado, masivo, correo de suplantación de identidad (phishing) y malware se pueden conservar para una revisión posterior.
ms.openlocfilehash: 253e1b9e03d395f67ff1290a527e035cbf8dfc3f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598677"
---
# <a name="quarantine-email-messages-in-office-365"></a><span data-ttu-id="8f4f4-103">Cuarentena de mensajes de correo electrónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="8f4f4-103">Quarantine email messages in Office 365</span></span>

<span data-ttu-id="8f4f4-104">Puede configurar la cuarentena para los mensajes de correo electrónico entrantes en Office 365 donde los mensajes que se han filtrado como correo no deseado, correo masivo, correo de suplantación de identidad, correo que contiene malware y el correo que coinciden con una regla de flujo de correo especificada (también denominada regla trasport) se pueden conservar para más tarde. comprueba.</span><span class="sxs-lookup"><span data-stu-id="8f4f4-104">You can set up quarantine for incoming email messages in Office 365 where messages that have been filtered as spam, bulk mail, phishing mail, mail that contains malware, and mail that matched a specified mail flow rule (also known as a trasport rule) can be kept for later review.</span></span>
  
<span data-ttu-id="8f4f4-105">De forma predeterminada, los mensajes que se filtraron por suplantación de identidad, malware y reglas de flujo de correo se envían a cuarentena, mientras que los mensajes filtrados como correo no deseado y correo masivo se envían a la carpeta de correo electrónico no deseado de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="8f4f4-105">By default, messages that were filtered for phishing, malware, and mail flow rules are sent to quarantine, while messages that were filtered as spam and bulk mail are sent to the recipients' Junk Email folder.</span></span> <span data-ttu-id="8f4f4-106">Como administrador, puede configurar directivas de filtro de correo no deseado (también conocidas como directivas de filtro de contenido) para enviar correo no deseado y mensajes de correo masivo a la cuarentena en su lugar.</span><span class="sxs-lookup"><span data-stu-id="8f4f4-106">As an admin, you can set up spam filter policies (also known as content filter policies) to send spam and bulk mail messages to quarantine instead.</span></span> <span data-ttu-id="8f4f4-107">Para obtener más información, consulte [Configure sus políticas de filtro de correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8f4f4-107">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="8f4f4-108">Tanto los usuarios como los administradores pueden trabajar con los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="8f4f4-108">Both users and admins can work with quarantined messages.</span></span> <span data-ttu-id="8f4f4-109">Los usuarios pueden trabajar en cuarentena solo con sus propios mensajes filtrados.</span><span class="sxs-lookup"><span data-stu-id="8f4f4-109">Users can work with just their own filtered messages in quarantine.</span></span> <span data-ttu-id="8f4f4-110">Los administradores pueden buscar y administrar los mensajes en cuarentena para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8f4f4-110">Admins can search for and manage quarantined messages for all users.</span></span>

> [!NOTE]
> <span data-ttu-id="8f4f4-111">Mensajes de phish de confianza alta y mensajes puestos en cuarentena por acciones de reglas de flujo de correo solo están disponibles en la cuarentena de administrador.</span><span class="sxs-lookup"><span data-stu-id="8f4f4-111">High confidence phish messages and messages quarantined by mail flow rule actions are only available in the admin quarantine.</span></span> <span data-ttu-id="8f4f4-112">Los usuarios pueden tener acceso a sus propios mensajes de Phish, correo no deseado y correo masivo.</span><span class="sxs-lookup"><span data-stu-id="8f4f4-112">Users can access their own phish, spam, and bulk mail messages.</span></span> 
  
<span data-ttu-id="8f4f4-113">Obtenga más información sobre cómo trabajar con mensajes en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="8f4f4-113">Learn more about working with quarantined messages:</span></span>
  
- [<span data-ttu-id="8f4f4-114">Administrar mensajes en cuarentena como administrador</span><span class="sxs-lookup"><span data-stu-id="8f4f4-114">Manage quarantined messages as an administrator</span></span>](manage-quarantined-messages-and-files.md)

- [<span data-ttu-id="8f4f4-115">Buscar y liberar mensajes en cuarentena como usuario</span><span class="sxs-lookup"><span data-stu-id="8f4f4-115">Find and release quarantined messages as a user</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- [<span data-ttu-id="8f4f4-116">Usar notificaciones de correo no deseado de usuario para liberar y notificar mensajes de correo no deseado en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8f4f4-116">Use user spam notifications to release and report spam-quarantined messages</span></span>](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [<span data-ttu-id="8f4f4-117">Preguntas más frecuentes sobre la cuarentena</span><span class="sxs-lookup"><span data-stu-id="8f4f4-117">Quarantine FAQ</span></span>](quarantine-faq.md)
