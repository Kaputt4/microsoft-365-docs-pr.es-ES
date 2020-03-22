---
title: Grupo de entrega de alto riesgo para mensajes salientes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo se usa el grupo de entrega de alto riesgo para proteger la reputación de los servidores de correo electrónico en los centros de información de Office 365.
ms.openlocfilehash: 5d1bd2b14eb17ed74ee1cf1e44967f660f4595b8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895364"
---
# <a name="high-risk-delivery-pool-for-outbound-messages-in-office-365"></a>Grupo de entrega de alto riesgo para mensajes salientes en Office 365

Los servidores de correo electrónico de los centros de recursos de Office 365 pueden ser temporalmente culpables de enviar correo no deseado. Por ejemplo, un ataque de malware o de correo no deseado en una organización de correo electrónico local que envía correo saliente a través de Office 365 o cuentas de Office 365 comprometidas. Estos escenarios pueden dar como resultado la dirección IP de los servidores de Office 365 Datacenter Server afectados que aparecen en las listas de bloqueados de terceros. Las organizaciones de correo electrónico de destino que usen estas listas de bloqueo rechazarán el correo electrónico de esos orígenes de mensajes.

Para evitarlo, todos los mensajes salientes de los servidores de centro de [servicios](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) de Office 365 que se determine que son correo no deseado o que superen los límites de envío del servicio o [las directivas de correo no deseado salientes](configure-the-outbound-spam-policy.md) se envían a través del _grupo de entrega de alto riesgo_.

El grupo de entrega de alto riesgo es un grupo de direcciones IP secundarias para el correo electrónico saliente que solo se usa para enviar mensajes de "baja calidad" (por ejemplo, correo no deseado y [dispersión](backscatter-messages-and-eop.md)). El uso del grupo de entrega de alto riesgo ayuda a evitar que el grupo de direcciones IP normal para el correo electrónico saliente envíe correo no deseado. El grupo de direcciones IP normal para el correo electrónico saliente mantiene la reputación enviando mensajes de "alta calidad", lo que reduce la probabilidad de que esta dirección IP aparezca en las listas de direcciones IP bloqueadas.

La posibilidad muy real de que las direcciones IP en el grupo de entrega de alto riesgo se coloquen en las listas de bloqueo de IP, pero esto es así por diseño. La entrega a los destinatarios deseados no está garantizada porque muchas organizaciones de correo electrónico no aceptan mensajes del grupo de entrega de alto riesgo.

Para obtener más información, consulte [controlar el correo no deseado saliente en Office 365](outbound-spam-controls.md).

> [!NOTE]
> Los mensajes en los que el dominio de correo electrónico de origen no tiene ningún registro A y no MX definido en DNS público siempre se redirigen a través del grupo de entrega de alto riesgo, independientemente de su correo no deseado o la disposición del límite de envío.

## <a name="bounce-messages"></a>Mensajes de devolución

El grupo de entrega de alto riesgo saliente administra la entrega de todos los informes de no entrega (también conocidos como NDR, mensajes de devolución, notificaciones de estado de entrega o DSN).

Entre las posibles causas de un aumento de NDR se incluyen:

- Una campaña de suplantación de identidad que afecta a uno de los clientes que usan el servicio.

- Un ataque de recopilación de directorios.

- Un ataque de correo no deseado.

- Un servidor de correo electrónico malintencionado.

Todos estos problemas pueden dar como resultado un aumento repentino del número de NDR que procesa el servicio. Muchas veces, estos NDR parecen ser correo no deseado para otros servidores y servicios de correo electrónico (también conocido como _[redispersión](backscatter-messages-and-eop.md)_).
