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
description: Obtenga información sobre cómo se usan los grupos de entrega para proteger la reputación de los servidores de correo electrónico en los centros de datos de Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b35474c4d2b00c70e02f6f0127c3191a1e459bc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910731"
---
# <a name="outbound-delivery-pools"></a>Grupos de entrega de salida

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Los servidores de correo electrónico de los centros de datos de Microsoft 365 podrían ser temporalmente responsables de enviar correo no deseado. Por ejemplo, un ataque de malware o correo no deseado malintencionado en una organización de correo electrónico local que envía correo saliente a través de Microsoft 365 o cuentas de Microsoft 365 comprometidas. Los atacantes también intentan evitar la detección retransmitiendo mensajes a través del reenvío de Microsoft 365.

Estos escenarios pueden dar como resultado que la dirección IP de los servidores de centros de datos de Microsoft 365 afectados aparezcan en listas de bloqueo de terceros. Las organizaciones de correo electrónico de destino que usan estas listas de bloqueo rechazarán el correo electrónico de esos orígenes de mensajes.

## <a name="high-risk-delivery-pool"></a>Grupo de entrega de alto riesgo
Para evitar esto, todos los mensajes salientes de los servidores de centros de datos [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) de Microsoft 365 que se determina que son correo no deseado o que superan los límites de envío del servicio o las directivas de [correo](configure-the-outbound-spam-policy.md) no deseado saliente se envían a través del grupo de entrega de alto _riesgo._

El grupo de entrega de alto riesgo es un grupo de direcciones IP independiente para el correo electrónico saliente que solo se usa para enviar mensajes de "baja calidad" (por ejemplo, correo no deseado y [backscatter](backscatter-messages-and-eop.md)). El uso del grupo de entrega de alto riesgo ayuda a evitar que el grupo de direcciones IP normal para el correo saliente envíe correo no deseado. El grupo de direcciones IP normal para el correo electrónico saliente mantiene la reputación enviando mensajes de "alta calidad", lo que reduce la probabilidad de que estas direcciones IP aparezcan en listas de direcciones IP bloqueados.

La posibilidad real de que las direcciones IP del grupo de entrega de alto riesgo se coloquen en listas de direcciones IP bloqueados permanece, pero esto es por diseño. La entrega a los destinatarios previstos no está garantizada, ya que muchas organizaciones de correo electrónico no aceptarán mensajes del grupo de entrega de alto riesgo.

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

## <a name="relay-pool"></a>Grupo de retransmisión

Los mensajes que se reenvía o retransmiten fuera de Microsoft 365 se envían mediante un grupo de retransmisión especial, ya que el destino final no debe considerar Microsoft 365 como el remitente real. También es importante aislar este tráfico, ya que existen escenarios legítimos e inválidos para la desaforación automática o la retransmisión de correo electrónico fuera de Microsoft 365. Al igual que el grupo de entrega de alto riesgo, se usa un grupo de direcciones IP independiente para el correo retransmitido. Este grupo de direcciones no se publica, ya que puede cambiar con frecuencia.

Microsoft 365 debe comprobar que el remitente original es legítimo para poder entregar con confianza el mensaje reenviado. Para ello, la autenticación de correo electrónico (SPF, DKIM y DMARC) debe pasar cuando el mensaje llegue a nosotros. En los casos en que podemos autenticar al remitente, usamos Reescritura del remitente para ayudar al receptor a saber que el mensaje reenviado es de un origen de confianza. Puede obtener más información sobre cómo funciona y qué puede hacer para asegurarse de que el dominio de envío pase la autenticación en el esquema de reescritura de [remitentes (SRS).](/office365/troubleshoot/antispam/sender-rewriting-scheme)