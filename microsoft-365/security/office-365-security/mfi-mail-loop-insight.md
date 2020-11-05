---
title: Corrección de posible información de bucle de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información sobre cómo solucionar posibles bucles de correo en el panel de flujo de correo en el centro de seguridad & cumplimiento para identificar y corregir bucles de correo en su organización.
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920575"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Corrección de la información posible sobre el bucle de correo en el centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Los bucles de correo son incorrectos porque:

- Desperdician recursos del sistema.
- Consumen la cuota del volumen de correo de su organización.
- Envían informes de no entrega confusos (también conocidos como NDR o mensajes de devolución) a los remitentes de mensajes originales.

La información de **corrección posible del bucle de correo** en el área **recomendada para** el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de [seguridad & cumplimiento](https://protection.office.com) le avisa cuando se detecta un bucle de correo en la organización.

Esta información sólo aparece cuando se detecta la condición (si no tiene bucles de correo, no verá la información).

![Corrección de la información lenta reglas de flujo de correo en el área recomendada para el panel del flujo de correo](../../media/mfi-fix-possible-mail-loop.png)

Al hacer clic en **Ver detalles** en el widget, aparece un control flotante con más información:

- **Dominio**
- **Número de mensajes** : puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento de mensajes](message-trace-scc.md) para obtener una muestra de los mensajes afectados por el bucle.
- **Tipo de dominio** "por ejemplo, autoritario o no autoritativo.
- **Registro MX** : host ( **servidor de correo** ) y valores de **prioridad** del registro MX para el dominio.
- **Razón** **para el bucle y cómo corregir** : identificaremos los escenarios de bucle de correo más comunes y proporcionaremos las acciones recomendadas para corregir el bucle.

![Control flotante de detalles después de hacer clic en ver detalles en la información de corrección posible bucle de correo](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Vea también

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
