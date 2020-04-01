---
title: Agregar compatibilidad para el correo electrónico entrante anónimo a través de IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: El administrador puede aprender a configurar la compatibilidad con el correo electrónico entrante anónimo desde orígenes IPv6 en Exchange Online y Exchange Online Protection.
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083646"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a><span data-ttu-id="9c4d4-103">Agregar compatibilidad para el correo electrónico entrante anónimo sobre IPv6 en Office 365</span><span class="sxs-lookup"><span data-stu-id="9c4d4-103">Add support for anonymous inbound email over IPv6 in Office 365</span></span>

<span data-ttu-id="9c4d4-104">Office 365 organizaciones con buzones de Exchange Online y organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online admiten el correo electrónico entrante anónimo a través de IPv6.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="9c4d4-105">El servidor de correo electrónico IPv6 de origen debe cumplir con los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="9c4d4-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="9c4d4-106">La dirección IPv6 de origen debe tener un registro de búsqueda DNS inversa (PTR) válido que permita al destino buscar el nombre de dominio de la dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="9c4d4-107">El remitente debe pasar la verificación SPF (definida en la norma [RFC 7208](https://tools.ietf.org/html/rfc7208)) o la [verificación de DKIM](https://dkim.org/) (definida en la norma [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="9c4d4-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="9c4d4-108">Para que su organización pueda recibir correo electrónico entrante anónimo a través de IPv6, un administrador debe ponerse en contacto con el soporte técnico de Microsoft y solicitarlo:</span><span class="sxs-lookup"><span data-stu-id="9c4d4-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it:</span></span>

1. <span data-ttu-id="9c4d4-109">Abra el centro de administración de 365 <https://admin.microsoft.com/adminportal/home> de Microsoft en y haga clic en **ayuda** (?).</span><span class="sxs-lookup"><span data-stu-id="9c4d4-109">Open the Microsoft 365 admin center at <https://admin.microsoft.com/adminportal/home> and click **Help** (?).</span></span>

2. <span data-ttu-id="9c4d4-110">En el control flotante **¿necesita ayuda?** , escriba algo descriptivo en el cuadro de búsqueda (por ejemplo, "solicitar correo IPv6 de entrada anónimo") y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-110">In the **Need help?** flyout that appears, type something descriptive in the search box (for example, "request anonymous inbound IPv6 email"), and then press ENTER.</span></span>

3. <span data-ttu-id="9c4d4-111">En la parte inferior de la página, haga clic en **soporte técnico**.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-111">At the bottom of the page, click **Contact support**.</span></span>

4. <span data-ttu-id="9c4d4-112">En la página **contacto de soporte técnico** que aparece, rellene y Compruebe la información (Desplácese hacia abajo si es necesario) y, a continuación, haga clic en **ponerse en contacto conmigo**.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-112">In the **Contact support** page that appears, fill out and verify the information (scroll down as necessary), and then click **Contact me**.</span></span>

<span data-ttu-id="9c4d4-113">Una vez habilitada la compatibilidad de mensajes IPv6 entrantes anónimos en la organización, el mensaje pasará por el filtrado de mensajes normal proporcionado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-113">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9c4d4-114">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="9c4d4-114">Troubleshooting</span></span>

- <span data-ttu-id="9c4d4-115">Si el servidor de correo electrónico de origen no tiene un registro de búsqueda DNS inversa IPv6, los mensajes se rechazarán con el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="9c4d4-115">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="9c4d4-116">450 4.7.25 servicio no disponible, enviar dirección IPv6 [2a01:111: F200:2004:: 240] debe tener el registro DNS inverso.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-116">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="9c4d4-117">Si el remitente no pasa la validación de SPF o DKIM, los mensajes se rechazarán con el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="9c4d4-117">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="9c4d4-118">450 4.7.26 servicio no disponible, mensaje enviado a través de IPv6 [2a01:111: F200:2004:: 240] debe pasar la validación SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-118">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="9c4d4-119">Si intenta recibir mensajes IPv6 anónimos antes de participar en el, el mensaje se rechazará con el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="9c4d4-119">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="9c4d4-120">550 5.2.1 servicio no disponible, [contoso.com] no acepta correo electrónico a través de IPv6.</span><span class="sxs-lookup"><span data-stu-id="9c4d4-120">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="9c4d4-121">Más información</span><span class="sxs-lookup"><span data-stu-id="9c4d4-121">For more information</span></span>

[<span data-ttu-id="9c4d4-122">Compatibilidad para la validación de mensajes firmados con DKIM</span><span class="sxs-lookup"><span data-stu-id="9c4d4-122">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
