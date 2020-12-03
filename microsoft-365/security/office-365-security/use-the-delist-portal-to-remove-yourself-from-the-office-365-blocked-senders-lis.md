---
title: Quitarse de la lista de remitentes bloqueados
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Microsoft 365.
ms.openlocfilehash: f4e7bcc13ac6c133880eb0ebe69ba3f724d0a84e
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561428"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="f13d0-103">Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados</span><span class="sxs-lookup"><span data-stu-id="f13d0-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f13d0-104">¿Recibe un mensaje de error cuando intenta enviar un correo electrónico a un destinatario cuya dirección de correo electrónico se encuentra en Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="f13d0-104">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="f13d0-105">Si cree que no debe recibir el mensaje de error, puede usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="f13d0-105">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="f13d0-106">¿Qué es la lista de remitentes bloqueados?</span><span class="sxs-lookup"><span data-stu-id="f13d0-106">What is the blocked senders list?</span></span>

<span data-ttu-id="f13d0-107">Microsoft usa la lista de remitentes bloqueados para proteger a sus clientes contra el spam, la suplantación de identidad y los ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="f13d0-107">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="f13d0-108">La dirección IP de su servidor de correo, es decir, la dirección que su servidor de correo usa para identificarse en Internet, se ha etiquetado como una amenaza potencial para Microsoft 365 por uno de varios motivos.</span><span class="sxs-lookup"><span data-stu-id="f13d0-108">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="f13d0-109">Cuando Microsoft 365 agrega la dirección IP a la lista, impide todas las comunicaciones entre la dirección IP y cualquiera de nuestros clientes a través de nuestros centros de recursos.</span><span class="sxs-lookup"><span data-stu-id="f13d0-109">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="f13d0-110">Sabrá que lo hemos agregado a la lista cuando reciba una respuesta a un mensaje de correo que incluya un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f13d0-110">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="f13d0-111">550 5.7.606-649 Acceso denegado, prohibido enviar IP [_IP address_]; para solicitar la eliminación de esta lista, visite <https://sender.office.com/> y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f13d0-111">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="f13d0-112">Para más información, consulte [Informes de no entrega de correo electrónico en Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="f13d0-112">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="f13d0-113">donde _dirección IP_ es la dirección IP del equipo en el que se ejecuta el servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="f13d0-113">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="f13d0-114">Para usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados</span><span class="sxs-lookup"><span data-stu-id="f13d0-114">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="f13d0-115">En un explorador web, vaya a <https://sender.office.com>.</span><span class="sxs-lookup"><span data-stu-id="f13d0-115">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="f13d0-p104">Siga las instrucciones que se indican en la página. Asegúrese de que usa la dirección de correo electrónico a la que se envió el mensaje de error, así como la dirección IP especificada en el mensaje de error. Solo se puede especificar una dirección de correo electrónico y una dirección IP por visita.</span><span class="sxs-lookup"><span data-stu-id="f13d0-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="f13d0-119">Haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="f13d0-119">Click **Submit**.</span></span>

    <span data-ttu-id="f13d0-120">El portal enviará un correo electrónico a la dirección que indique.</span><span class="sxs-lookup"><span data-stu-id="f13d0-120">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="f13d0-121">El correo electrónico tendrá un aspecto similar al siguiente: ![Captura de pantalla del correo electrónico que se recibe al enviar una solicitud mediante el portal de eliminación de la lista](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)  </span><span class="sxs-lookup"><span data-stu-id="f13d0-121">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="f13d0-122">Haga clic en el vínculo de confirmación que aparece en el correo electrónico que le ha enviado el portal de eliminación de la lista.</span><span class="sxs-lookup"><span data-stu-id="f13d0-122">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="f13d0-123">Regresará al portal de eliminación de la lista.</span><span class="sxs-lookup"><span data-stu-id="f13d0-123">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="f13d0-124">En el portal de eliminación de la lista, haga clic en **Quitar de la lista una IP**.</span><span class="sxs-lookup"><span data-stu-id="f13d0-124">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="f13d0-125">Una vez quitada la dirección IP de la lista de remitentes bloqueados, los mensajes de correo electrónico de esa dirección IP se entregarán a los destinatarios que usen Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f13d0-125">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="f13d0-126">Por lo tanto, asegúrese de que el correo electrónico enviado desde esa dirección IP no es ofensivo ni malintencionado; de lo contrario, es posible que se vuelva a bloquear la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="f13d0-126">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f13d0-127">Pueden pasar hasta 24 horas o los resultados pueden variar ampliamente antes de eliminar las restricciones.</span><span class="sxs-lookup"><span data-stu-id="f13d0-127">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="f13d0-128">Consulte [Create Safe Sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam Protection in EOP](outbound-spam-controls.md) para evitar que se bloquee una IP.</span><span class="sxs-lookup"><span data-stu-id="f13d0-128">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>
