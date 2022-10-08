---
title: Información de estado del flujo de correo de dominio superior en el panel Flujo de correo
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: m365-security
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información de estado del flujo de correo de dominio superior en el panel Flujo de correo del Centro de cumplimiento de seguridad & para solucionar problemas de flujo de correo relacionados con sus registros MX.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: c87262d79211f1a67b5268e56876252fc61054ab
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68054960"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Información de estado del flujo de correo de dominio superior en el Centro de cumplimiento de seguridad &

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La información **de estado del flujo de correo de dominio superior** en el [panel Flujo de correo](mail-flow-insights-v2.md) del [Centro de cumplimiento de seguridad &](https://protection.office.com) proporciona el estado actual del flujo de correo de su organización.

Esta información le ayuda a identificar y solucionar problemas de dominios que experimentan problemas de ***flujo de correo*** . Por ejemplo, el dominio no puede recibir correo electrónico externo porque el dominio ha expirado o el dominio tiene un registro MX incorrecto.

:::image type="content" source="../../media/mfi-top-domain-mail-flow-status-widget.png" alt-text="Widget de estado de flujo de dominio superior en el panel Flujo de correo del Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-top-domain-mail-flow-status-widget.png":::

Al hacer clic en **Ver detalles** en el widget, aparece un control flotante **Estado del dominio** que muestra más detalles sobre el estado de cada dominio:

- **Dominio**
- **Registro MX anterior**
- **Registro MX actual**
- **Email estado de recepción**
- **Estado del dominio**: una marca de verificación verde indica que el registro MX actual (en el momento en que se ha hecho clic en el widget) coincide con el valor que tenemos en el registro y que el dominio ha recibido correo electrónico durante las últimas dos horas.

  Una X roja indica que se ha cambiado el registro MX y que el dominio no ha recibido ningún correo electrónico durante las últimas 6 horas. Esto probablemente indica que el dominio ha expirado o que el registro MX se ha actualizado incorrectamente. Compruebe con el registrador de dominios o el servicio de hospedaje DNS para ver si el dominio ha expirado o si el registro MX del dominio es incorrecto.

Puede hacer clic en **Ver más** para ver la misma información para más dominios.

:::image type="content" source="../../media/mfi-top-domain-mail-flow-status-view-details.png" alt-text="El control flotante Detalles en la información de estado del flujo de correo del dominio superior" lightbox="../../media/mfi-top-domain-mail-flow-status-view-details.png":::

## <a name="see-also"></a>Vea también

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
