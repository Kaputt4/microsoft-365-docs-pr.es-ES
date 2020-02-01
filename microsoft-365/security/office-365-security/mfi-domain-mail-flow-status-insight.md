---
title: Información de estado de flujo de correo de dominio superior
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden obtener información sobre el conocimiento del estado del flujo de correo del dominio superior del panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 1fb22ac1543c490dcbd316464803f5393003d503
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598887"
---
# <a name="top-domain-mail-flow-status-insight"></a>Información de estado de flujo de correo de dominio superior

La información del **Estado del flujo de correo de dominio superior** le ofrece el estado actual de los dominios de su organización en términos de flujo de correo. Esta visión le ayudará a identificar y solucionar problemas de dominios que experimentan problemas de impacto en el ***flujo de correo*** (por ejemplo, no se puede recibir correo electrónico externo), en especial expiraciones de dominio o dominios con registros MX incorrectos.

![La información más detallada sobre el estado del flujo del dominio en el panel de flujo del correo en el centro de seguridad & cumplimiento](../media/domain-mail-flow-status-selected.png)

Al hacer clic en **Ver detalles** en la visión, aparecerá un control flotante que muestra más detalles sobre el estado de cada dominio.

Una marca de verificación verde para un dominio indica que el registro MX actual (cuando se ha explorado el panel de información de flujo de correo) coincide con el valor que tenemos en el registro y que el dominio ha recibido el correo electrónico durante las dos últimas horas.

Una x de color rojo para un dominio indica que se ha cambiado el registro MX y que el dominio no ha recibido ningún correo electrónico durante las 6 últimas horas. Esto probablemente indica que su dominio ha expirado o que el registro MX se ha actualizado incorrectamente. Consulte con el registrador de dominios o el servicio de hospedaje DNS para ver si el dominio ha expirado o si el registro MX del dominio es incorrecto.

![El control flotante de detalles en la información del estado del flujo superior del dominio](../media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a>Vea también

Para obtener más información acerca de otras indicaciones del flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
