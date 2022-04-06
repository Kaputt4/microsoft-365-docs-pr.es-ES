---
title: Información sobre el flujo de correo entrante y saliente en el panel flujo de correo
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
description: Los administradores pueden obtener información sobre el flujo de correo saliente y entrante en el panel flujo de correo en el Centro de seguridad & cumplimiento.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3bc9d6c08dfc1c232018d79e988d741505079604
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475727"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Información sobre el flujo de correo entrante y saliente en el Centro de & seguridad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La **información de flujo** de correo saliente y entrante [](mail-flow-insights-v2.md) en el panel flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) combina la información del informe [de Connector](view-mail-flow-reports.md#connector-report) y el informe de información general de **TLS** anterior en un solo lugar.

El widget muestra el cifrado TLS que se usa para la conexión cuando se entregan mensajes desde y hacia su organización. Las conexiones establecidas con otros servicios de correo electrónico se cifran mediante TLS cuando TLS se ofrece por ambas partes. El widget ofrece una instantánea de la última semana de flujo de correo.

:::image type="content" source="../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png" alt-text="El widget Flujo de correo saliente y entrante en el panel Flujo de correo del Centro de seguridad & cumplimiento" lightbox="../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png":::

La información del widget está relacionada con conectores y protección de mensajes TLS en Microsoft 365. Para obtener más información, vea estos temas:

- [Configurar un flujo de correo mediante conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Detalles de referencia técnica sobre el cifrado en Microsoft 365](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>Mensaje protegido en tránsito (por TLS)

Al hacer clic en **Ver** detalles en el widget, el control flotante Mensaje protegido en tránsito **(por TLS)** muestra la protección TLS para los mensajes que entran y salen de la organización.

:::image type="content" source="../../media/mfi-outbound-and-inbound-mail-flow-report-details.png" alt-text="El control flotante Mensajes protegidos en tránsito (por TLS) que aparece después de hacer clic en Ver detalles en el widget de correo electrónico saliente y entrante" lightbox="../../media/mfi-outbound-and-inbound-mail-flow-report-details.png":::

Actualmente, TLS 1.2 es la versión más segura de TLS que ofrece Microsoft 365. A menudo, necesitará conocer el cifrado TLS que se usa para las auditorías de cumplimiento. Probablemente no tenga una relación directa con la mayoría de los servidores de correo electrónico de origen y destino (no los posee ni Microsoft), por lo que no tiene muchas opciones para mejorar el cifrado TLS que usan esos servidores.

Sin embargo, puede usar conectores [para](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) garantizar la mejor protección TLS disponible para los mensajes que se envían entre los servidores de correo electrónico y Microsoft 365. El flujo de correo entre Microsoft 365 y sus propios servidores o servidores de correo electrónico que pertenecen a sus socios suele ser más importante y confidencial que los mensajes normales, por lo que querrá aplicar seguridad y vigilancia adicionales a esos mensajes.

Puede actualizar o corregir sus propios servidores de correo electrónico para mejorar el cifrado TLS que se está utilizando o comunicarse con sus asociados para hacer lo mismo. El **informe de conector** muestra el volumen de flujo de correo y el cifrado TLS para los mensajes que usan los conectores Microsoft 365 correo.

Puede hacer clic en el **vínculo Informe de conector** para ir al [informe de conector](view-mail-flow-reports.md#connector-report). Las siguientes perspectivas podrían estar disponibles en la **página de informe de Connector** si se ha detectado la condición asociada:

- **Conector de partner entrante que ve un flujo de correo TLS1.0 significativo**
- **Conector Entrante OnPremises que ve un flujo de correo TLS1.0 significativo**

Para las conexiones TLS 1.0, realmente necesita actualizar o solucionar el servidor de correo electrónico o el servidor de su asociado para evitar cualquier problema cuando la compatibilidad con TLS 1.0 esté en desuso en Microsoft 365.

## <a name="see-also"></a>Vea también

Para obtener información sobre otras perspectivas en el panel flujo de correo, vea Información sobre el flujo de correo en el [Centro de seguridad & cumplimiento](mail-flow-insights-v2.md).