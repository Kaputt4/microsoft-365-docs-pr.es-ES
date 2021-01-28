---
title: Información de estado del flujo de correo de dominio superior en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información de estado del flujo de correo de dominio superior en el panel de flujo de correo del Centro de seguridad & cumplimiento para solucionar problemas de flujo de correo relacionados con sus registros MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 457675e7f32cd513f5593ede53a64aaef9d54904
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029911"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Información de estado del flujo de correo de dominio superior en el Centro de & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


La información sobre el estado [](mail-flow-insights-v2.md) **del** flujo de correo de dominio superior en el panel flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) le proporciona el estado actual del flujo de correo de su organización.

Esta información le ayuda a identificar y solucionar problemas de dominios que están experimentando **_problemas de flujo de_* correo. Por ejemplo, el dominio no puede recibir correo electrónico externo porque el dominio ha expirado o el dominio tiene un registro MX incorrecto.

![Widget Estado del flujo de dominio superior en el panel flujo de correo del Centro de & cumplimiento](../../media/mfi-top-domain-mail-flow-status-widget.png)

Al hacer clic en _ Ver  *detalles** en el widget, aparece un control flotante de estado de dominio que muestra más detalles para el estado de cada dominio:

- **Dominio**
- **Registro MX anterior**
- **Registro MX actual**
- **Estado de recepción de correo electrónico**
- **Estado del** dominio: una marca de verificación verde indica que el registro MX actual (en el momento en que hizo clic en el widget) coincide con el valor que tenemos en el registro y que el dominio ha recibido correo electrónico durante las últimas dos horas.

  Una X roja indica que se ha cambiado el registro MX y que el dominio no ha recibido ningún correo electrónico durante las últimas 6 horas. Esto probablemente indica que el dominio ha expirado o que el registro MX se ha actualizado incorrectamente. Consulte con el registrador de dominios o el servicio de hospedaje DNS para ver si el dominio ha expirado o si el registro MX del dominio es incorrecto.

Puede hacer clic **en Ver más** para ver la misma información para más dominios.

![Control de detalles en la información de estado del flujo de correo de dominio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Consulta también

Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
