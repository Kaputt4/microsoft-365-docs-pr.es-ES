---
title: Información sobre el flujo de correo entrante y saliente en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Los administradores pueden obtener información sobre el flujo de correo entrante y saliente en el panel flujo de correo en el Centro de & cumplimiento.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e46a0ebf0c14e31462d1e86d8a8d8c08486337af
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029827"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Información sobre el flujo de correo entrante y saliente en el Centro de & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


La **información del** flujo de [](mail-flow-insights-v2.md) correo entrante y saliente en el panel de flujo [](view-mail-flow-reports.md#connector-report) de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) combina la información del informe del conector y el anterior informe de información general de **TLS** en un solo lugar.

El widget muestra el cifrado TLS que se usa para la conexión cuando los mensajes se entregan a y desde la organización. Las conexiones establecidas con otros servicios de correo electrónico se cifran mediante TLS cuando ambos lados ofrecen TLS. El widget ofrece una instantánea de la última semana de flujo de correo.

![Widget Flujo de correo entrante y saliente en el panel flujo de correo en el Centro de & cumplimiento](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

La información del widget está relacionada con los conectores y la protección de mensajes TLS en Microsoft 365. Para obtener más información, consulte estos temas:

- [Configurar el flujo de correo mediante conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Detalles de referencia técnica sobre el cifrado en Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>Mensaje protegido en tránsito (por TLS)

Al hacer clic **en Ver** detalles en el widget, el control flotante Mensaje protegido en tránsito **(por TLS)** muestra la protección TLS para los mensajes que entran y salen de la organización.

![Mensajes protegidos en tránsito (por TLS) que aparecen después de hacer clic en Ver detalles en el widget Correo electrónico entrante y saliente](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Actualmente, TLS 1.2 es la versión más segura de TLS que ofrece Microsoft 365. A menudo, debe conocer el cifrado TLS que se usa para las auditorías de cumplimiento. Es probable que no tenga una relación directa con la mayoría de los servidores de correo electrónico de origen y de destino (no es el propietario y tampoco Microsoft), por lo que no tiene muchas opciones para mejorar el cifrado TLS que usan esos servidores.

Pero puede usar conectores [para](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) garantizar la mejor protección TLS disponible para los mensajes que se envían entre los servidores de correo electrónico y Microsoft 365. El flujo de correo entre Microsoft 365 y sus propios servidores de correo electrónico o servidores que pertenecen a sus asociados suele ser más importante y confidencial que los mensajes normales, por lo que le será más fácil aplicar seguridad y atención adicionales a esos mensajes.

Puede actualizar o corregir sus propios servidores de correo electrónico para mejorar el cifrado TLS que se está utilizando, o comunicarse con sus asociados para hacer lo mismo. El **informe de conectores** muestra el volumen de flujo de correo y el cifrado TLS para los mensajes que usan los conectores de Microsoft 365.

Puede hacer clic en el **vínculo informe del** conector para ir al informe del [conector.](view-mail-flow-reports.md#connector-report) Las siguientes conclusiones pueden estar disponibles en la página **del informe del** conector si se ha detectado la condición asociada:

- **Conector de asociado de entrada que ve un flujo de correo TLS1.0 significativo**
- **Conector OnPremises entrante que ve un flujo de correo TLS1.0 significativo**

Para las conexiones TLS 1.0, realmente necesita actualizar o solucionar el servidor de correo electrónico o el servidor de su asociado para evitar problemas cuando el soporte técnico de TLS 1.0 finalmente está en desuso en Microsoft 365.

## <a name="see-also"></a>Consulta también

Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
