---
title: Administrar listas de remitentes seguros para troyanos de envío masivo de correo electrónico
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Si quiere usar listas de remitentes seguros, debe saber que Exchange Online Protection (EOP) y Outlook llevan a cabo el procesamiento de manera diferente. El servicio respeta los remitentes y los dominios seguros al inspeccionar la dirección RFC 5321.MailFrom y la dirección RFC 5322.From, mientras que Outlook agrega la dirección RFC 5322.From a la lista de remitentes seguros de un usuario. (Nota: El servicio inspecciona tanto la dirección 5321.MailFrom como la dirección 5322.From en busca de remitentes y dominios bloqueados).'
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598947"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="dfe66-105">Administrar listas de remitentes seguros para troyanos de envío masivo de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="dfe66-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="dfe66-106">Si quiere usar listas de remitentes seguros, debe saber que Exchange Online Protection (EOP) y Outlook llevan a cabo el procesamiento de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="dfe66-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="dfe66-107">El servicio de Office 365 respeta a los remitentes y dominios seguros mediante `RFC 5321.MailFrom` la inspección de `RFC 5322.From` la dirección y la dirección, `RFC 5322.From` mientras que Outlook agrega la dirección a la lista de remitentes seguros de un usuario.</span><span class="sxs-lookup"><span data-stu-id="dfe66-107">The Office 365 service respects safe senders and domains by inspecting the `RFC 5321.MailFrom` address and the `RFC 5322.From` address, while Outlook adds the `RFC 5322.From` address to a user's safe sender list.</span></span> <span data-ttu-id="dfe66-108">(Nota: el servicio inspecciona tanto la dirección `5321.MailFrom` como `5322.From` la dirección para los remitentes y dominios bloqueados).</span><span class="sxs-lookup"><span data-stu-id="dfe66-108">(Note: The service inspects both the `5321.MailFrom` address and `5322.From` address for blocked senders and domains.)</span></span>

<span data-ttu-id="dfe66-109">La `SMTP MAIL FROM` dirección, que también se conoce `RFC 5321.MailFrom address`como, es la dirección de correo electrónico que se usa para realizar comprobaciones de SPF y, si no se puede entregar el correo, la ruta de acceso a la que se entrega el mensaje resaltado.</span><span class="sxs-lookup"><span data-stu-id="dfe66-109">The `SMTP MAIL FROM` address, otherwise known as the `RFC 5321.MailFrom address`, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="dfe66-110">Esta es la dirección `Return-Path` de correo electrónico que se coloca de forma predeterminada en los encabezados de los mensajes, aunque es posible que el remitente designe una dirección diferente `Return-Path` .</span><span class="sxs-lookup"><span data-stu-id="dfe66-110">It's this email address that is placed into the `Return-Path` in the message headers by default, though it's possible for the sender to designate a different `Return-Path` address.</span></span>

<span data-ttu-id="dfe66-111">La `From:` dirección que aparece en los encabezados del mensaje, que también `RFC 5322.From` se denomina dirección, es la dirección de correo electrónico que se muestra en el cliente de correo, como Outlook.</span><span class="sxs-lookup"><span data-stu-id="dfe66-111">The `From:` address in the message headers, otherwise known as the `RFC 5322.From` address, is the email address that is displayed in the mail client such as Outlook.</span></span>

<span data-ttu-id="dfe66-112">La mayoría de las veces, `5321.MailFrom` las `5322.From` direcciones y son las mismas.</span><span class="sxs-lookup"><span data-stu-id="dfe66-112">Much of the time, the `5321.MailFrom` and `5322.From` addresses are the same.</span></span> <span data-ttu-id="dfe66-113">Esto es típico para la comunicación de persona a persona.</span><span class="sxs-lookup"><span data-stu-id="dfe66-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="dfe66-114">No obstante, cuando el correo electrónico se envía en nombre de otra persona, las direcciones son frecuentemente diferentes.</span><span class="sxs-lookup"><span data-stu-id="dfe66-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="dfe66-115">Esto generalmente ocurre con mucha frecuencia en mensajes de correo masivos.</span><span class="sxs-lookup"><span data-stu-id="dfe66-115">This usually happens most often for bulk email messages.</span></span>

<span data-ttu-id="dfe66-116">Por ejemplo, supongamos que Blue Yonder Airlines ha contratado el viaje de Ana para enviar su publicidad por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="dfe66-116">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="dfe66-117">Luego, obtiene un mensaje en su bandeja de entrada del remitente blueyonder@news.blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="dfe66-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="dfe66-118">En este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dfe66-118">In this example:</span></span>

- <span data-ttu-id="dfe66-119">La `5321.MailFrom` dirección es blueyonder.Airlines@margiestravel.com.</span><span class="sxs-lookup"><span data-stu-id="dfe66-119">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="dfe66-120">La `5322.From` dirección es blueyonder@news.blueyonderairlines.com, que es lo que verá en Outlook.</span><span class="sxs-lookup"><span data-stu-id="dfe66-120">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="dfe66-121">Para evitar que se filtre este mensaje, puede:</span><span class="sxs-lookup"><span data-stu-id="dfe66-121">To prevent this message from being filtered, you can:</span></span>

- <span data-ttu-id="dfe66-122">**Como usuario**: Agregue la `RFC 5322.From` dirección como un remitente seguro en Outlook.</span><span class="sxs-lookup"><span data-stu-id="dfe66-122">**As a user**: Add the `RFC 5322.From` address as a Safe Sender in Outlook.</span></span>

- <span data-ttu-id="dfe66-123">**Como administrador**: configurar una regla de [flujo de correo](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (también denominada regla de transporte).</span><span class="sxs-lookup"><span data-stu-id="dfe66-123">**As an admin**: Set up a [mail flow rule](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (also known as a transport rule).</span></span>
