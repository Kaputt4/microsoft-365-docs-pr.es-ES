---
title: Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 'Cuando se bloquea a un remitente en el servicio debido al envío de correo no deseado de salida, el administrador de dominio especificado al Configurar la directiva de correo no deseado saliente recibirá un correo electrónico de notificación similar al siguiente:'
ms.openlocfilehash: badcd34bc35c8cc3cdd1cd06edefb87c6818e2e3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37093560"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="c8cf8-103">Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida</span><span class="sxs-lookup"><span data-stu-id="c8cf8-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="c8cf8-104">Cuando se bloquea a un remitente en el servicio debido al envío de correo no deseado de salida, el administrador de dominio especificado al [Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md) recibirá un correo electrónico de notificación similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8cf8-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="c8cf8-105">**Dirección del remitente:** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8cf8-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="c8cf8-106">**Asunto:** Notificación de correo no deseado de salida: \<  *nombre de cuenta*  \> bloqueada para enviar correo saliente</span><span class="sxs-lookup"><span data-stu-id="c8cf8-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="c8cf8-107">**Cuerpo:** Se trata de una respuesta automática desde el sistema de análisis de correo no deseado de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="c8cf8-108">Nos ponemos en contacto con usted porque hemos detectado volúmenes elevados de correo electrónico marcado como correo no deseado, u otros comportamientos sospechosos, procedentes de su organización.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-108">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization.</span></span> <span data-ttu-id="c8cf8-109">Las siguientes cuentas de correo electrónico han sido bloqueadas para enviar correo electrónico (pueden seguir recibiendo correo electrónico):</span><span class="sxs-lookup"><span data-stu-id="c8cf8-109">The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="c8cf8-110">\< *nombre de cuenta*  \></span><span class="sxs-lookup"><span data-stu-id="c8cf8-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="c8cf8-111">Es probable que esta cuenta de correo electrónico se haya puesto en peligro.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-111">It is likely that this email account has been compromised.</span></span> <span data-ttu-id="c8cf8-112">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c8cf8-112">Please follow these steps:</span></span>
  
1. <span data-ttu-id="c8cf8-113">Resuelva este problema en su parte:</span><span class="sxs-lookup"><span data-stu-id="c8cf8-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="c8cf8-114">Cambio de la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="c8cf8-115">Determinación del modo en que la cuenta se ha puesto en peligro.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="c8cf8-116">Tomar precauciones para asegurarse de que no se pueda aprovechar esta vulnerabilidad de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="c8cf8-117">Confirmar que la cola de correo saliente se ha borrado de todos los mensajes ofensivos.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="c8cf8-118">Póngase en contacto con el soporte técnico de Microsoft con el canal de contacto habitual.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="c8cf8-119">Explique que hay un usuario que está bloqueado y no puede enviar correo y que el problema se ha solucionado.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="c8cf8-120">El agente creará un vale de soporte técnico con la información que proporcione y la escalará para que la dirección de correo electrónico o el dominio no se bloqueen.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="c8cf8-121">Una vez que se haya desbloqueado la dirección y no se hayan producido otros problemas, se le pondrá en contacto y se le enviará una alerta al desbloqueo.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="c8cf8-122">Gracias por ayudarnos a controlar el correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="c8cf8-123">Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="c8cf8-124">\*\*NOTA: no responda a este correo electrónico ya que se envía desde una dirección sin supervisar\*\*</span><span class="sxs-lookup"><span data-stu-id="c8cf8-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="c8cf8-125">También puede ponerse en contacto con el soporte técnico a través de las opciones documentadas en [Help and Support for EOP](help-and-support-for-eop.md).</span><span class="sxs-lookup"><span data-stu-id="c8cf8-125">You can also contact support via the options documented at [Help and support for EOP](help-and-support-for-eop.md).</span></span> 
  

