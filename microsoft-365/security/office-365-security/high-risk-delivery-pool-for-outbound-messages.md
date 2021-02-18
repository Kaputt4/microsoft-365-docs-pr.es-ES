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
ms.openlocfilehash: 89aac1478d3e5840df4379b9f49832b79d0e133a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289810"
---
# <a name="outbound-delivery-pools"></a>Grupos de entrega de salida

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Es posible que los servidores de correo electrónico de los centros de datos de Microsoft 365 no puedan enviar correo no deseado temporalmente. Por ejemplo, un ataque de malware o correo no deseado malintencionado en una organización de correo electrónico local que envía correo saliente a través de Microsoft 365 o cuentas de Microsoft 365 en peligro. Los atacantes también intentan evitar la detección retransmitiendo mensajes a través del reenvío de Microsoft 365.

Estos escenarios pueden hacer que la dirección IP de los servidores de centros de datos de Microsoft 365 afectados aparezca en listas de bloqueados de terceros. Las organizaciones de correo electrónico de destino que usen estas listas de bloqueados rechazarán el correo electrónico de esos orígenes de mensajes.

## <a name="high-risk-delivery-pool"></a>Grupo de entrega de alto riesgo
Para evitarlo, todos los mensajes salientes de servidores de centros de datos de [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) Microsoft 365 que se determinen como correo no deseado o que superen los límites de envío del servicio o las directivas de correo no deseado saliente se envían a través del grupo de entrega de alto _riesgo._ [](configure-the-outbound-spam-policy.md)

El grupo de entrega de alto riesgo es un grupo de direcciones IP independiente para el correo electrónico saliente que solo se usa para enviar mensajes de "baja calidad" (por ejemplo, correo no deseado y correo [electrónico no deseado).](backscatter-messages-and-eop.md) El uso del grupo de entrega de alto riesgo ayuda a evitar que el grupo de direcciones IP normal para el correo electrónico saliente envíe correo no deseado. El grupo de direcciones IP normal para el correo electrónico saliente mantiene la reputación de enviar mensajes de "alta calidad", lo que reduce la probabilidad de que estas direcciones IP aparezcan en listas de direcciones IP no válidas.

La posibilidad muy real de que las direcciones IP del grupo de entrega de alto riesgo se coloquen en listas de direcciones IP no válidas permanece, pero esto es por diseño. No se garantiza la entrega a los destinatarios previstos, ya que muchas organizaciones de correo electrónico no aceptarán mensajes del grupo de entrega de alto riesgo.

Para obtener más información, vea [Control de correo no deseado saliente.](outbound-spam-controls.md)

> [!NOTE]
> Los mensajes en los que el dominio de correo electrónico de origen no tiene ningún registro A y ningún registro MX definido en dns público siempre se enrutan a través del grupo de entrega de alto riesgo, independientemente de su correo no deseado o de la eliminación del límite de envío.

### <a name="bounce-messages"></a>Mensajes de de rebote

El grupo de entrega de alto riesgo saliente administra la entrega de todos los informes de no entrega (también conocidos como NDRs, mensajes de de rebote, notificaciones de estado de entrega o DSN).

Entre las causas posibles de un aumento de los NDR se incluyen:

- Una campaña de suplantación de nombre que afecta a uno de los clientes que usan el servicio.
- Un ataque de recolección de directorios.
- Un ataque de correo no deseado.
- Un servidor de correo electrónico no deseado.

Todos estos problemas pueden provocar un aumento repentino en el número de NDRs que procesa el servicio. Muchas veces, estos NDR parecen correo no deseado para otros servidores y servicios de correo electrónico (también conocidos como _[correo electrónico no deseado).](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>Grupo de retransmisión

Los mensajes reenviados o retransmitido desde Microsoft 365 se envían mediante un grupo de retransmisión especial, ya que el destino final no debe considerar a Microsoft 365 como el remitente real. También es importante que aíslemos este tráfico, ya que existen escenarios legítimos e no válidos para el envío automático o la retransmisión de correo electrónico desde Microsoft 365. Al igual que el grupo de entrega de alto riesgo, se usa un grupo de direcciones IP independiente para el correo retransmitido. Este grupo de direcciones no se publica, ya que puede cambiar con frecuencia.

Microsoft 365 debe comprobar que el remitente original es legítimo para poder entregar con confianza el mensaje reenviado. Para ello, la autenticación de correo electrónico (SPF, DKIM y DMARC) debe pasarse cuando el mensaje llegue a nosotros. En los casos en los que podemos autenticar al remitente, usamos la reescritura de remitentes para ayudar al receptor a saber que el mensaje reenviado es de un origen de confianza. Puede obtener más información sobre cómo funciona y qué puede hacer para ayudar a asegurarse de que el dominio remitente pasa la autenticación en el esquema de reescritura de [remitentes (SRS).](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)
