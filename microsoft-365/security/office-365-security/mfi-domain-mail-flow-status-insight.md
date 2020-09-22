---
title: Información sobre el estado del flujo de correo de dominio superior en el panel flujo de correo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información más detallada sobre el estado del flujo de correo del dominio en el panel de flujo del correo en el centro de seguridad & cumplimiento para solucionar problemas del flujo de correo relacionados con los registros MX en sus dominios de correo electrónico.
ms.openlocfilehash: 24922d6ae7d2ec50e3d9383631991cf46a818c05
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197530"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Información más detallada sobre el estado del flujo de correo del dominio en el centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


La información más detallada sobre el **Estado del flujo de correo del dominio** en el panel del flujo de [correo](mail-flow-insights-v2.md) en el [centro de seguridad & cumplimiento](https://protection.office.com) le ofrece el estado actual de los dominios de su organización en términos de flujo de correo. Esta visión le ayudará a identificar y solucionar problemas de dominios que experimentan problemas de impacto en el ***flujo de correo*** (por ejemplo, no se puede recibir correo electrónico externo), en especial expiraciones de dominio o dominios con registros MX incorrectos.

![Widget de estado de flujo superior del dominio en el panel de flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-top-domain-mail-flow-status-widget.png)

Al hacer clic en **Ver detalles** en el widget, aparece un control flotante de **Estado de dominio** que muestra más detalles para el estado de cada dominio:

- **Dominio**
- **Registro MX anterior**
- **Registro MX actual**
- **Estado de recepción de correo electrónico**
- **Estado del dominio**: una marca de verificación verde indica que el registro MX actual (en el momento en que hizo clic en el widget) coincide con el valor que tenemos en el registro y que el dominio ha recibido el correo electrónico durante las dos últimas horas.

  Una X roja indica que se ha cambiado el registro MX y que el dominio no ha recibido ningún correo electrónico durante las 6 últimas horas. Esto probablemente indica que su dominio ha expirado o que el registro MX se ha actualizado incorrectamente. Consulte con el registrador de dominios o el servicio de hospedaje DNS para ver si el dominio ha expirado o si el registro MX del dominio es incorrecto.

Puede hacer clic en **Ver más** para ver la misma información de más dominios.

![Flotante de detalles en la información del estado del flujo de correo del dominio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
