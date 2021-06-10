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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo se usan los grupos de entrega para proteger la reputación de los servidores de correo electrónico en Microsoft 365 centros de datos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599916"
---
# <a name="outbound-delivery-pools"></a>Grupos de entrega de salida

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Los servidores de correo electrónico Microsoft 365 centros de datos podrían ser temporalmente responsables de enviar correo no deseado. Por ejemplo, un ataque de malware o correo no deseado malintencionado en una organización de correo electrónico local que envía correo saliente a través de Microsoft 365 o cuentas Microsoft 365 comprometidas. Los atacantes también intentan evitar la detección retransmitiendo mensajes a través Microsoft 365 reenvío.

Estos escenarios pueden dar como resultado que la dirección IP de los servidores de centros de datos Microsoft 365 de datos afectados aparezcan en listas de bloqueo de terceros. Las organizaciones de correo electrónico de destino que usan estas listas de bloqueo rechazarán el correo electrónico de esos orígenes de mensajes.

## <a name="high-risk-delivery-pool"></a>Grupo de entrega de alto riesgo
Para evitar esto, todos los mensajes salientes de servidores de centros de datos [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) de Microsoft 365 [](configure-the-outbound-spam-policy.md) que se determina que son correo no deseado o que superan los límites de envío del servicio o las directivas de correo no deseado saliente se envían a través del grupo de entrega de alto riesgo _._

El grupo de entrega de alto riesgo es un grupo de direcciones IP independiente para el correo electrónico saliente que solo se usa para enviar mensajes de "baja calidad" (por ejemplo, correo no deseado y [backscatter](backscatter-messages-and-eop.md)). El uso del grupo de entrega de alto riesgo ayuda a evitar que el grupo de direcciones IP normal para el correo saliente envíe correo no deseado. El grupo de direcciones IP normal para el correo electrónico saliente mantiene la reputación enviando mensajes de "alta calidad", lo que reduce la probabilidad de que estas direcciones IP aparezcan en listas de direcciones IP bloqueados.

La posibilidad muy real de que las direcciones IP del grupo de entrega de alto riesgo se coloquen en listas de direcciones IP bloqueados permanece, pero esto es por diseño. La entrega a los destinatarios previstos no está garantizada, ya que muchas organizaciones de correo electrónico no aceptarán mensajes del grupo de entrega de alto riesgo.

Para obtener más información, vea [Control outbound spam](outbound-spam-controls.md).

> [!NOTE]
> Los mensajes en los que el dominio de correo electrónico de origen no tiene ningún registro A y ningún registro MX definido en DNS público siempre se enrutan a través del grupo de entrega de alto riesgo, independientemente de su correo no deseado o la eliminación del límite de envío.

### <a name="bounce-messages"></a>Mensajes de rebote

El grupo de entrega de alto riesgo de salida administra la entrega de todos los informes de no entrega (también conocidos como NDR, mensajes de de rebote, notificaciones de estado de entrega o DSN).

Entre las causas posibles de un aumento de los NDR se incluyen:

- Una campaña de suplantación de dominio que afecta a uno de los clientes que usan el servicio.
- Un ataque de recolección de directorios.
- Un ataque de correo no deseado.
- Un servidor de correo electrónico no deseado.

Todos estos problemas pueden provocar un aumento repentino del número de NDR que procesa el servicio. Muchas veces, estos NDR parecen ser correo no deseado para otros servidores de correo electrónico y servicios (también conocidos como _[backscatter](backscatter-messages-and-eop.md)_).
