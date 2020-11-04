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
ms.openlocfilehash: 15ad5c467d18ce3038bcb05db798a9b5a7c3e391
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877515"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Corrección de la información posible sobre el bucle de correo en el centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Un bucle de correo es incorrecto porque desperdicia recursos del sistema, consume la cuota del volumen de correo de su organización y envía informes de no entrega confusos (también conocidos como NDR o mensajes de devolución) a los remitentes originales.

La información de **corrección posible del bucle de correo** en el área **recomendada para** el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de [seguridad & cumplimiento](https://protection.office.com) le avisa cuando se detecta un bucle de correo en la organización. Esta información sólo aparece cuando se detecta la condición (si no tiene bucles de correo, no verá la información).

![Corrección de la información lenta reglas de flujo de correo en el área recomendada para el panel del flujo de correo](../../media/mfi-fix-possible-mail-loop.png)

Al hacer clic en **Ver detalles** en el widget, aparece un control flotante con más información:

- **Dominio**
- **Número de mensajes** : puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento de mensajes](message-trace-scc.md) para obtener una muestra de los mensajes afectados por el bucle.
- **Tipo de dominio** "por ejemplo, autoritario o no autoritativo.
- **Registro MX** : host ( **servidor de correo** ) y valores de **prioridad** del registro MX para el dominio.
- **Razón** **para el bucle y cómo corregir** : intentaremos identificar los escenarios de bucle de correo más comunes y proporcionar las acciones recomendadas (si están disponibles) para corregir el bucle.

![Control flotante de detalles después de hacer clic en ver detalles en la información de corrección posible bucle de correo](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
