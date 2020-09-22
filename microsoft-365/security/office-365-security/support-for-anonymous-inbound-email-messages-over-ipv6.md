---
title: Agregar la compatibilidad para el correo electrónico entrante anónimo a través de IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: El administrador puede aprender a configurar la compatibilidad con el correo electrónico entrante anónimo desde orígenes IPv6 en Exchange Online y Exchange Online Protection.
ms.openlocfilehash: be226bf9814b0fcfadaaeb5b4bdda0ff133dd0c8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202154"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="d39a7-103">Agregar compatibilidad para el correo electrónico entrante anónimo sobre IPv6 en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d39a7-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d39a7-104">Microsoft 365 organizaciones con buzones de Exchange Online y organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online admiten el correo electrónico entrante anónimo a través de IPv6.</span><span class="sxs-lookup"><span data-stu-id="d39a7-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="d39a7-105">El servidor de correo electrónico IPv6 de origen debe cumplir con los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="d39a7-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="d39a7-106">La dirección IPv6 de origen debe tener un registro de búsqueda DNS inversa (PTR) válido que permita al destino buscar el nombre de dominio de la dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="d39a7-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="d39a7-107">El remitente debe pasar la verificación SPF (definida en la norma [RFC 7208](https://tools.ietf.org/html/rfc7208)) o la [verificación de DKIM](http://dkim.org/) (definida en la norma [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="d39a7-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="d39a7-108">Para que su organización pueda recibir correo electrónico entrante anónimo a través de IPv6, un administrador debe ponerse en contacto con el soporte técnico de Microsoft y solicitarlo.</span><span class="sxs-lookup"><span data-stu-id="d39a7-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="d39a7-109">Para obtener instrucciones sobre cómo abrir una solicitud de soporte técnico, consulte [Contact Support for Business Products: ayuda de administración](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="d39a7-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="d39a7-110">Una vez habilitada la compatibilidad de mensajes IPv6 entrantes anónimos en la organización, el mensaje pasará por el filtrado de mensajes normal proporcionado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="d39a7-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d39a7-111">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="d39a7-111">Troubleshooting</span></span>

- <span data-ttu-id="d39a7-112">Si el servidor de correo electrónico de origen no tiene un registro de búsqueda DNS inversa IPv6, los mensajes se rechazarán con el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="d39a7-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="d39a7-113">450 4.7.25 servicio no disponible, enviar dirección IPv6 [2a01:111: F200:2004:: 240] debe tener el registro DNS inverso.</span><span class="sxs-lookup"><span data-stu-id="d39a7-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="d39a7-114">Si el remitente no pasa la validación de SPF o DKIM, los mensajes se rechazarán con el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="d39a7-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="d39a7-115">450 4.7.26 servicio no disponible, mensaje enviado a través de IPv6 [2a01:111: F200:2004:: 240] debe pasar la validación SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="d39a7-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="d39a7-116">Si intenta recibir mensajes IPv6 anónimos antes de participar en el, el mensaje se rechazará con el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="d39a7-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="d39a7-117">550 5.2.1 servicio no disponible, [contoso.com] no acepta correo electrónico a través de IPv6.</span><span class="sxs-lookup"><span data-stu-id="d39a7-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d39a7-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d39a7-118">Related topics</span></span>

[<span data-ttu-id="d39a7-119">Compatibilidad para la validación de mensajes firmados con DKIM</span><span class="sxs-lookup"><span data-stu-id="d39a7-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
