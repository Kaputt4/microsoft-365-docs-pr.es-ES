---
title: Información sobre el flujo de correo entrante y saliente en el panel flujo de correo
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
description: Los administradores pueden obtener información sobre el flujo de correo saliente y entrante en el panel flujo de correo en el Centro de seguridad & cumplimiento.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071232"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Información sobre el flujo de correo entrante y saliente en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La **información de flujo** de [](mail-flow-insights-v2.md) correo saliente y entrante en el panel flujo de correo del Centro de seguridad [& cumplimiento](https://protection.office.com) combina la información del informe [de Conector](view-mail-flow-reports.md#connector-report) y el informe de información general de **TLS** anterior en un solo lugar.

El widget muestra el cifrado TLS que se usa para la conexión cuando se entregan mensajes desde y hacia su organización. Las conexiones establecidas con otros servicios de correo electrónico se cifran mediante TLS cuando TLS se ofrece por ambas partes. El widget ofrece una instantánea de la última semana de flujo de correo.

![Widget de flujo de correo entrante y saliente en el panel Flujo de correo del Centro de seguridad & cumplimiento](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

La información del widget está relacionada con conectores y protección de mensajes TLS en Microsoft 365. Para obtener más información, vea estos temas:

- [Configurar el flujo de correo con conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Detalles de referencia técnica sobre el cifrado en Microsoft 365](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>Mensaje protegido en tránsito (por TLS)

Al hacer clic en **Ver** detalles en el widget, el control flotante Mensaje protegido en tránsito **(por TLS)** muestra la protección TLS para los mensajes que entran y salen de la organización.

![Mensajes protegidos en tránsito (por TLS) flotante que aparecen después de hacer clic en Ver detalles en el widget de correo electrónico saliente y entrante](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Actualmente, TLS 1.2 es la versión más segura de TLS que ofrece Microsoft 365. A menudo, necesitará conocer el cifrado TLS que se usa para las auditorías de cumplimiento. Probablemente no tenga una relación directa con la mayoría de los servidores de correo electrónico de origen y destino (no los posee ni Microsoft), por lo que no tiene muchas opciones para mejorar el cifrado TLS que usan esos servidores.

Sin embargo, puede usar [conectores para](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) garantizar la mejor protección TLS disponible para los mensajes que se envían entre los servidores de correo electrónico y Microsoft 365. El flujo de correo entre Microsoft 365 y sus propios servidores o servidores de correo electrónico que pertenecen a sus socios suele ser más importante y confidencial que los mensajes normales, por lo que querrá aplicar seguridad y vigilancia adicionales a esos mensajes.

Puede actualizar o corregir sus propios servidores de correo electrónico para mejorar el cifrado TLS que se está utilizando o comunicarse con sus asociados para hacer lo mismo. El **informe del conector** muestra el volumen de flujo de correo y el cifrado TLS para los mensajes que usan los conectores de Microsoft 365.

Puede hacer clic en el **vínculo Informe de conector** para ir al informe de [Conector.](view-mail-flow-reports.md#connector-report) Las siguientes perspectivas podrían estar disponibles en la página de informe **de Connector** si se ha detectado la condición asociada:

- **Conector de partner entrante que ve un flujo de correo TLS1.0 significativo**
- **Conector Entrante OnPremises que ve un flujo de correo TLS1.0 significativo**

Para las conexiones TLS 1.0, realmente necesita actualizar o solucionar el servidor de correo electrónico o el servidor de su partner para evitar cualquier problema cuando la compatibilidad con TLS 1.0 esté en desuso en Microsoft 365.

## <a name="see-also"></a>Ver también

Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).