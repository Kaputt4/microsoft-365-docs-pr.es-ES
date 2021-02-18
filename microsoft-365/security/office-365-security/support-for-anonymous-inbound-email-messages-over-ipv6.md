---
title: Agregar la compatibilidad para el correo electrónico entrante anónimo a través de IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: El administrador puede obtener información sobre cómo configurar la compatibilidad con el correo electrónico entrante anónimo de orígenes IPv6 en Exchange Online y Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290278"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="24c44-103">Agregar compatibilidad para correo electrónico entrante anónimo a través de IPv6 en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24c44-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="24c44-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="24c44-104">**Applies to**</span></span>
- [<span data-ttu-id="24c44-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="24c44-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="24c44-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="24c44-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="24c44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24c44-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="24c44-108">Las organizaciones de Microsoft 365 con buzones de Exchange Online y organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online admiten correo electrónico entrante anónimo a través de IPv6.</span><span class="sxs-lookup"><span data-stu-id="24c44-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="24c44-109">El servidor de correo electrónico IPv6 de origen debe cumplir los dos requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="24c44-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="24c44-110">La dirección IPv6 de origen debe tener un registro de búsqueda DNS inversa (PTR) válido que permita al destino encontrar el nombre de dominio de la dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="24c44-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="24c44-111">El remitente debe pasar la verificación SPF (definida en la norma [RFC 7208](https://tools.ietf.org/html/rfc7208)) o la [verificación de DKIM](http://dkim.org/) (definida en la norma [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="24c44-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="24c44-112">Para que su organización pueda recibir correo electrónico entrante anónimo a través de IPv6, un administrador debe ponerse en contacto con el soporte técnico de Microsoft y solicitarlo.</span><span class="sxs-lookup"><span data-stu-id="24c44-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="24c44-113">Para obtener instrucciones sobre cómo abrir una solicitud de soporte técnico, consulte Ponerse en contacto con el soporte técnico para productos [empresariales: Ayuda para administradores.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="24c44-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="24c44-114">Una vez habilitada la compatibilidad con mensajes IPv6 entrantes anónimos en la organización, el mensaje pasará por el filtrado normal de mensajes proporcionado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="24c44-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="24c44-115">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="24c44-115">Troubleshooting</span></span>

- <span data-ttu-id="24c44-116">Si el servidor de correo electrónico de origen no tiene un registro de búsqueda DNS inversa IPv6, los mensajes se rechazarán con el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="24c44-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="24c44-117">450 4.7.25 Servicio no disponible, enviar dirección IPv6 [2a01:111:f200:2004::240] debe tener registro DNS inverso.</span><span class="sxs-lookup"><span data-stu-id="24c44-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="24c44-118">Si el remitente no pasa la validación SPF o DKIM, los mensajes se rechazarán con el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="24c44-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="24c44-119">450 4.7.26 Servicio no disponible, mensaje enviado a través de IPv6 [2a01:111:f200:2004::240] debe pasar la validación SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="24c44-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="24c44-120">Si intenta recibir mensajes IPv6 anónimos antes de participar, el mensaje se rechazará con el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="24c44-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="24c44-121">El servicio 550 5.2.1 no está disponible, [contoso.com] no acepta correo electrónico a través de IPv6.</span><span class="sxs-lookup"><span data-stu-id="24c44-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="24c44-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="24c44-122">Related topics</span></span>

[<span data-ttu-id="24c44-123">Compatibilidad para la validación de mensajes firmados con DKIM</span><span class="sxs-lookup"><span data-stu-id="24c44-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
