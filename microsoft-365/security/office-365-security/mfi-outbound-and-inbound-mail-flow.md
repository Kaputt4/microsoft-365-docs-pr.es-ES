---
title: Información de flujo de correo saliente y entrante en el panel Flujo de correo
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Los administradores pueden obtener información sobre la información de flujo de correo saliente y entrante en el panel Flujo de correo del Centro de cumplimiento de seguridad &.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: f9e6cc058ff479ea13253f0e6b4ecd7c28281eda
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597424"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Información de flujo de correo saliente y entrante en el Centro de cumplimiento de seguridad &

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La información de **flujo de correo saliente y entrante** en el [panel Flujo de correo](mail-flow-insights-v2.md) del [Centro de cumplimiento de seguridad &](https://protection.office.com) combina la información del [informe del conector](view-mail-flow-reports.md#connector-report) y del anterior **informe de información general de TLS** en un solo lugar.

El widget muestra el cifrado TLS que se usa para la conexión cuando se entregan mensajes hacia y desde su organización. Las conexiones que se establecen con otros servicios de correo electrónico se cifran mediante TLS cuando TLS se ofrece por ambos lados. El widget ofrece una instantánea de la última semana de flujo de correo.

:::image type="content" source="../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png" alt-text="Widget Flujo de correo saliente y entrante en el panel Flujo de correo del Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png":::

La información del widget está relacionada con los conectores y la protección de mensajes TLS en Microsoft 365. Para obtener más información, consulte estos temas:

- [Configurar un flujo de correo mediante conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Detalles de referencia técnica sobre el cifrado en Microsoft 365](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>Mensaje protegido en tránsito (mediante TLS)

Al hacer clic en **Ver detalles** en el widget, el control flotante **Mensaje protegido en tránsito (por TLS)** muestra la protección TLS para los mensajes que entran y salen de la organización.

:::image type="content" source="../../media/mfi-outbound-and-inbound-mail-flow-report-details.png" alt-text="El control flotante Mensajes protegidos en tránsito (por TLS) que aparece después de hacer clic en Ver detalles en el widget de correo electrónico saliente y entrante" lightbox="../../media/mfi-outbound-and-inbound-mail-flow-report-details.png":::

Actualmente, TLS 1.2 es la versión más segura de TLS que ofrece Microsoft 365. A menudo, necesitará conocer el cifrado TLS que se usa para las auditorías de cumplimiento. Probablemente no tenga una relación directa con la mayoría de los servidores de correo electrónico de origen y de destino (no los posee ni Microsoft), por lo que no tiene muchas opciones para mejorar el cifrado TLS que usan esos servidores.

Sin embargo, puede usar [conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para garantizar la mejor protección TLS disponible para los mensajes que se envían entre los servidores de correo electrónico y Microsoft 365. El flujo de correo entre Microsoft 365 y sus propios servidores de correo electrónico o servidores que pertenecen a sus asociados suele ser más importante y confidencial que los mensajes normales, por lo que querrá aplicar seguridad adicional y vigilancia a esos mensajes.

Puede actualizar o corregir sus propios servidores de correo electrónico para mejorar el cifrado TLS que se usa, o ponerse en contacto con sus asociados para hacer lo mismo. El **informe del conector** muestra el volumen de flujo de correo y el cifrado TLS para los mensajes que usan los conectores de Microsoft 365.

Puede hacer clic en el vínculo **Informe del conector** para ir al [informe del conector](view-mail-flow-reports.md#connector-report). La siguiente información podría estar disponible en la página **del informe del conector** si se ha detectado la condición asociada:

- **Conector de asociado de entrada que ve un flujo de correo TLS1.0 significativo**
- **Conector OnPremises entrante que ve un flujo de correo TLS1.0 significativo**

En el caso de las conexiones TLS 1.0, es preciso actualizar o corregir el servidor de correo electrónico o el servidor de su asociado para evitar cualquier problema cuando la compatibilidad con TLS 1.0 finalmente esté en desuso en Microsoft 365.

## <a name="see-also"></a>Vea también

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
