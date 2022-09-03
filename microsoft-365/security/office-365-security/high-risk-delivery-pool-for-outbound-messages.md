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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo se usan los grupos de entrega para proteger la reputación de los servidores de correo electrónico en los centros de datos de Microsoft 365.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 0d56f1cb69134da2d0ebe2594a8507ef7e0f5c37
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598437"
---
# <a name="outbound-delivery-pools"></a>Grupos de entrega de salida

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Email servidores de los centros de datos de Microsoft 365 podrían ser temporalmente culpables de enviar correo no deseado. Por ejemplo, un malware o un ataque de correo no deseado malintencionado en una organización de correo electrónico local que envía correo saliente a través de Microsoft 365 o cuentas de Microsoft 365 en peligro. Los atacantes también intentan evitar la detección retransmitiendo mensajes a través del reenvío de Microsoft 365.

Estos escenarios pueden dar lugar a que la dirección IP de los servidores del centro de datos de Microsoft 365 afectados aparezca en listas de bloqueo de terceros. Las organizaciones de correo electrónico de destino que usan estas listas de bloqueo rechazarán el correo electrónico de esos orígenes de mensajes de Microsoft 365.

## <a name="high-risk-delivery-pool"></a>Grupo de entrega de alto riesgo

Para evitar que nuestras direcciones IP se bloqueen, todos los mensajes salientes de los servidores del centro de datos de Microsoft 365 que se determinan como correo no deseado se envían a través del _grupo de entrega de alto riesgo_.

El grupo de entrega de alto riesgo es un grupo de direcciones IP independiente para el correo electrónico saliente que solo se usa para enviar mensajes de "baja calidad" (por ejemplo, correo no deseado y [backscatter](backscatter-messages-and-eop.md)). El uso del grupo de entrega de alto riesgo ayuda a evitar que el grupo de direcciones IP normal para el correo electrónico saliente envíe correo no deseado. El grupo de direcciones IP normal para el correo electrónico saliente mantiene la reputación de enviar mensajes de "alta calidad", lo que reduce la probabilidad de que estas direcciones IP aparezcan en listas de bloqueo de IP.

La posibilidad real de que las direcciones IP del grupo de entregas de alto riesgo se coloquen en listas de bloqueo de IP permanece, pero esto es así por diseño. No se garantiza la entrega a los destinatarios previstos, ya que muchas organizaciones de correo electrónico no aceptan mensajes del grupo de entrega de alto riesgo.

Para obtener más información, consulte [Control del correo no deseado saliente](outbound-spam-controls.md).

> [!NOTE]
> Los mensajes en los que el dominio de correo electrónico de origen no tiene ningún registro A y ningún registro MX definido en DNS público siempre se enrutan a través del grupo de entrega de alto riesgo, independientemente de su eliminación del límite de envío o correo no deseado.
>
> Los mensajes que superan los límites siguientes se bloquean, por lo que no se envían a través del grupo de entrega de alto riesgo:
>
> - [Límites de envío del servicio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).
> - [Directivas de correo no deseado saliente](configure-the-outbound-spam-policy.md) en las que los remitentes tienen restringido el envío de correo.

### <a name="bounce-messages"></a>Mensajes de rebote

El grupo de entrega de alto riesgo de salida administra la entrega de todos los informes de no entrega (también conocidos como NDR, mensajes de rebote, notificaciones de estado de entrega o DSN).

Entre las posibles causas de un aumento de los NDR se incluyen las siguientes:

- Una campaña de suplantación de identidad que afecta a uno de los clientes que usan el servicio.
- Un ataque de recopilación de directorios.
- Un ataque de correo no deseado.
- Un servidor de correo electrónico no autorizado.

Todos estos problemas pueden dar lugar a un aumento repentino del número de NDR que procesa el servicio. Muchas veces, estos NDR parecen ser correo no deseado para otros servidores de correo electrónico y servicios (también _[conocidos como backscatter](backscatter-messages-and-eop.md)_).

### <a name="relay-pool"></a>Grupo de retransmisiones

Los mensajes que se reenvíen o retransmitan a través de Microsoft 365 en determinados escenarios se enviarán mediante un grupo de retransmisión especial, ya que el destino no debe considerar Microsoft 365 como el remitente real. Es importante que aíslemos este tráfico de correo electrónico, ya que hay escenarios legítimos y no válidos para el reenvío automático o la retransmisión de correo electrónico fuera de Microsoft 365. De forma similar al grupo de entrega de alto riesgo, se usa un grupo de direcciones IP independiente para el correo retransmitido. Este grupo de direcciones no se publica porque puede cambiar con frecuencia y no forma parte del registro SPF publicado para Microsoft 365.

Microsoft 365 debe comprobar que el remitente original es legítimo para poder entregar con confianza el mensaje reenviado.

El mensaje reenviado o retransmitido debe cumplir uno de los siguientes criterios para evitar el uso del grupo de retransmisión:

- El remitente saliente está en un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- SPF pasa cuando el mensaje llega a Microsoft 365.
- DKIM en el dominio del remitente pasa cuando el mensaje llega a Microsoft 365.

Puede indicar que se envió un mensaje a través del grupo de retransmisión examinando la dirección IP del servidor saliente (el grupo de retransmisión estará en el intervalo 40.95.0.0/16) o examinando el nombre del servidor saliente (tendrá "rly" en el nombre).

En los casos en los que podemos autenticar al remitente, usamos el esquema de reescritura del remitente (SRS) para ayudar al sistema de correo electrónico del destinatario a saber que el mensaje reenviado procede de un origen de confianza. Puede obtener más información sobre cómo funciona y qué puede hacer para asegurarse de que el dominio de envío pasa la autenticación en [esquema de reescritura de remitentes (SRS) en Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).

Para que DKIM funcione, asegúrese de habilitar DKIM para enviar dominio. Por ejemplo, fabrikam.com forma parte de contoso.com y se define en los dominios aceptados de la organización. Si el remitente del mensaje está sender@fabrikam.com, DKIM debe estar habilitado para fabrikam.com. puede leer cómo habilitar en [Uso de DKIM para validar el correo electrónico saliente enviado desde el dominio personalizado](use-dkim-to-validate-outbound-email.md).

Para agregar dominios personalizados, siga los pasos descritos en [Agregar un dominio a Microsoft 365](../../admin/setup/add-domain.md).

Si el registro MX del dominio apunta a un servicio de terceros o a un servidor de correo electrónico local, debe usar [el filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors). El filtrado mejorado garantiza que la validación de SPF es correcta para el correo entrante y evitará el envío de correo electrónico a través del grupo de retransmisión.
