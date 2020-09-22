---
title: Grupos de entrega de salida
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo se usan los grupos de entrega para proteger la reputación de los servidores de correo electrónico en los centros de información de Microsoft 365.
ms.openlocfilehash: b3016be7c1887536fe3e742b5ab4ec598b6a5f89
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201494"
---
# <a name="outbound-delivery-pools"></a>Grupos de entrega de salida

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Los servidores de correo electrónico de los centros de recursos de Microsoft 365 pueden ser temporalmente culpables de enviar correo no deseado. Por ejemplo, un ataque de malware o de correo no deseado en una organización de correo electrónico local que envía correo saliente a través de Microsoft 365 o cuentas comprometidas de Microsoft 365. Los atacantes también intentan evitar la detección mediante la retransmisión de mensajes a través del reenvío de Microsoft 365.

Estos escenarios pueden dar como resultado la dirección IP de los servidores de centro de recursos de Microsoft 365 afectados que aparecen en las listas de bloqueados de terceros. Las organizaciones de correo electrónico de destino que usen estas listas de bloqueo rechazarán el correo electrónico de esos orígenes de mensajes.

## <a name="high-risk-delivery-pool"></a>Grupo de entrega de alto riesgo
Para evitarlo, todos los mensajes salientes de servidores de centro de [servicios](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) de Microsoft 365 que se determine que son correo no deseado o que superan los límites de envío del servicio o [las directivas de correo no deseado salientes](configure-the-outbound-spam-policy.md) se envían a través del _grupo de entrega de alto riesgo_.

El grupo de entrega de alto riesgo es un grupo de direcciones IP independiente para el correo electrónico saliente que solo se usa para enviar mensajes de "baja calidad" (por ejemplo, correo no deseado y [dispersión](backscatter-messages-and-eop.md)). El uso del grupo de entrega de alto riesgo ayuda a evitar que el grupo de direcciones IP normal para el correo electrónico saliente envíe correo no deseado. El grupo de direcciones IP normal para el correo electrónico saliente mantiene la reputación enviando mensajes de "alta calidad", lo que reduce la probabilidad de que esta dirección IP aparezca en las listas de direcciones IP bloqueadas.

La posibilidad muy real de que las direcciones IP en el grupo de entrega de alto riesgo se coloquen en las listas de bloqueo de IP, pero esto es así por diseño. La entrega a los destinatarios deseados no está garantizada porque muchas organizaciones de correo electrónico no aceptan mensajes del grupo de entrega de alto riesgo.

Para obtener más información, consulte [controlar el correo no deseado saliente](outbound-spam-controls.md).

> [!NOTE]
> Los mensajes en los que el dominio de correo electrónico de origen no tiene ningún registro A y no MX definido en DNS público siempre se redirigen a través del grupo de entrega de alto riesgo, independientemente de su correo no deseado o la disposición del límite de envío.

### <a name="bounce-messages"></a>Mensajes de devolución

El grupo de entrega de alto riesgo saliente administra la entrega de todos los informes de no entrega (también conocidos como NDR, mensajes de devolución, notificaciones de estado de entrega o DSN).

Entre las posibles causas de un aumento de NDR se incluyen:

- Una campaña de suplantación de identidad que afecta a uno de los clientes que usan el servicio.
- Un ataque de recopilación de directorios.
- Un ataque de correo no deseado.
- Un servidor de correo electrónico malintencionado.

Todos estos problemas pueden dar como resultado un aumento repentino del número de NDR que procesa el servicio. Muchas veces, estos NDR parecen ser correo no deseado para otros servidores y servicios de correo electrónico (también conocido como _[redispersión](backscatter-messages-and-eop.md)_).

## <a name="relay-pool"></a>Grupo de retransmisión

Los mensajes que se reenvían o retransmiten desde Microsoft 365 se envían mediante un grupo de retransmisión especial, ya que el destino final no debe tener en cuenta a Microsoft 365 como el remitente real. También es importante para aislar este tráfico, porque hay escenarios legítimos y no válidos para el reenvío o retransmisión de correo electrónico fuera de Microsoft 365. De forma similar al grupo de entrega de alto riesgo, se usa un grupo de direcciones IP independiente para el correo retransmitido. Este grupo de direcciones no se publica porque puede cambiar con frecuencia.

Microsoft 365 necesita comprobar que el remitente original es legítimo, de modo que pueda entregar con confianza el mensaje reenviado. Para ello, la autenticación de correo electrónico (SPF, DKIM y DMARC) debe pasar cuando el mensaje nos llegue. En los casos en que podamos autenticar al remitente, usamos la reconfiguración del remitente para ayudar al receptor a saber que el mensaje reenviado proviene de un origen de confianza. Puede obtener más información sobre cómo funciona y qué puede hacer para asegurarse de que el dominio remitente pasa la autenticación en el [esquema de reescritura del remitente (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).
