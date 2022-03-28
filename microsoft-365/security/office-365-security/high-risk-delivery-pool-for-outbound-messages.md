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
description: Obtenga información sobre cómo se usan los grupos de entrega para proteger la reputación de los servidores de correo electrónico en los Microsoft 365 de datos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 273d105ca600face4d79d70fc1622dfce8bf9f5e
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403853"
---
# <a name="outbound-delivery-pools"></a>Grupos de entrega de salida

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Los servidores de correo electrónico Microsoft 365 centros de datos podrían ser temporalmente responsables de enviar correo no deseado. Por ejemplo, un ataque de malware o correo no deseado malintencionado en una organización de correo electrónico local que envía correo saliente a través de Microsoft 365 o cuentas Microsoft 365 comprometidas. Los atacantes también intentan evitar la detección retransmitiendo mensajes a través Microsoft 365 reenvío.

Estos escenarios pueden dar como resultado que la dirección IP de los servidores de centros de datos Microsoft 365 de datos afectados aparezcan en listas de bloqueo de terceros. Las organizaciones de correo electrónico de destino que usan estas listas de bloqueo rechazarán el correo electrónico de esos Microsoft 365 de mensajes.

## <a name="high-risk-delivery-pool"></a>Grupo de entrega de alto riesgo

Para evitar que nuestras direcciones IP se bloqueen, todos los mensajes salientes de Microsoft 365 servidores de centros de datos que se determina que son correo no deseado se envían a través del grupo _de entrega de alto riesgo_.

El grupo de entrega de alto riesgo es un grupo de direcciones IP independiente para el correo electrónico saliente que solo se usa para enviar mensajes de "baja calidad" (por ejemplo, correo no deseado y [backscatter](backscatter-messages-and-eop.md). El uso del grupo de entrega de alto riesgo ayuda a evitar que el grupo de direcciones IP normal para el correo saliente envíe correo no deseado. El grupo de direcciones IP normal para el correo electrónico saliente mantiene la reputación enviando mensajes de "alta calidad", lo que reduce la probabilidad de que estas direcciones IP aparezcan en listas de direcciones IP bloqueados.

La posibilidad muy real de que las direcciones IP del grupo de entrega de alto riesgo se coloquen en listas de direcciones IP bloqueados permanece, pero esto es por diseño. La entrega a los destinatarios previstos no está garantizada, ya que muchas organizaciones de correo electrónico no aceptarán mensajes del grupo de entrega de alto riesgo.

Para obtener más información, vea [Control outbound spam](outbound-spam-controls.md).

> [!NOTE]
> Los mensajes en los que el dominio de correo electrónico de origen no tiene ningún registro A y ningún registro MX definido en DNS público siempre se enrutan a través del grupo de entrega de alto riesgo, independientemente de su correo no deseado o la eliminación del límite de envío.
>
> Los mensajes que superan los siguientes límites se bloquean, por lo que no se envían a través del grupo de entrega de alto riesgo:
>
> - Los [límites de envío del servicio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).
> - [Directivas de correo](configure-the-outbound-spam-policy.md) no deseado salientes en las que los remitentes tienen restricciones para enviar correo.

### <a name="bounce-messages"></a>Mensajes de rebote

El grupo de entrega de alto riesgo de salida administra la entrega de todos los informes de no entrega (también conocidos como NDR, mensajes de de rebote, notificaciones de estado de entrega o DSN).

Entre las causas posibles de un aumento de los NDR se incluyen:

- Una campaña de suplantación de dominio que afecta a uno de los clientes que usan el servicio.
- Un ataque de recolección de directorios.
- Un ataque de correo no deseado.
- Un servidor de correo electrónico no deseado.

Todos estos problemas pueden provocar un aumento repentino del número de NDR que procesa el servicio. Muchas veces, estos NDR parecen ser correo no deseado para otros servidores de correo electrónico y servicios (también conocidos como _[backscatter](backscatter-messages-and-eop.md)_).

### <a name="relay-pool"></a>Grupo de retransmisión

Los mensajes que se reenván o retransmiten a través de Microsoft 365 en determinados escenarios se enviarán con un grupo de retransmisión especial, ya que el destino no debe considerar Microsoft 365 como el remitente real. Es importante aislar este tráfico de correo electrónico, ya que existen escenarios legítimos y no válidos para reenviar o retransmitir correo electrónico automáticamente fuera de Microsoft 365. Al igual que el grupo de entrega de alto riesgo, se usa un grupo de direcciones IP independiente para el correo retransmitido. Este grupo de direcciones no se publica porque puede cambiar a menudo y no forma parte del registro SPF publicado para Microsoft 365.

Microsoft 365 debe comprobar que el remitente original es legítimo para poder entregar con confianza el mensaje reenviado.

El mensaje reenviado o retransmitido debe cumplir uno de los siguientes criterios para evitar el uso del grupo de retransmisión:

- El remitente saliente está en un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- SPF pasa cuando el mensaje llega a Microsoft 365.
- DKIM en el dominio del remitente pasa cuando el mensaje llega a Microsoft 365.

Puede saber que un mensaje se envió a través del grupo de retransmisión mirando la DIRECCIÓN IP del servidor saliente (el grupo de retransmisión estará en el intervalo 40.95.0.0/16) o mirando el nombre del servidor saliente (tendrá "rly" en el nombre).

En los casos en los que podemos autenticar al remitente, usamos el esquema de reescritura de remitentes (SRS) para ayudar al sistema de correo electrónico del destinatario a saber que el mensaje reenviado es de un origen de confianza. Puede obtener más información sobre cómo funciona y qué puede hacer para asegurarse de que el dominio de envío pase la autenticación en el esquema de reescritura de [remitentes (SRS) en Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).

Para que DKIM funcione, asegúrese de habilitar DKIM para enviar dominio. Por ejemplo, fabrikam.com forma parte de contoso.com y se define en los dominios aceptados de la organización. Si el remitente del mensaje sender@fabrikam.com, DKIM debe estar habilitado para fabrikam.com. puede leer sobre cómo habilitar en [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado](use-dkim-to-validate-outbound-email.md).

Para agregar dominios personalizados, siga los pasos descritos [en Agregar un dominio a Microsoft 365](../../admin/setup/add-domain.md).

Si el registro MX del dominio apunta a un servicio de terceros o a un servidor de correo electrónico local, debe usar el filtrado mejorado [para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors). El filtrado mejorado garantiza que la validación de SPF sea correcta para el correo entrante y evitará el envío de correo electrónico a través del grupo de retransmisión.
