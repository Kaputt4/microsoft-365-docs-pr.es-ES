---
title: Corrección de posible información de bucle de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información de corregir posibles bucles de correo en el panel de flujo de correo del Centro de seguridad & y cumplimiento para identificar y corregir bucles de correo en su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029899"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Corregir posibles perspectivas del bucle de correo en el Centro de & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Los bucles de correo son malos porque:

- Desperdician recursos del sistema.
- Consumen la cuota de volumen de correo de su organización.
- Envían informes de no entrega confusos (también conocidos como NDRs o mensajes de de rebote) a los remitentes del mensaje original.

La información **de** corrección  de posibles [](mail-flow-insights-v2.md) bucles de correo en el área Recomendado para usted del panel de flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) le notifica cuándo se detecta un bucle de correo en su organización.

Esta información aparece solo después de que se detecte la condición (si no tiene bucles de correo, no verá la información).

![Corregir información de reglas de flujo de correo lentas en el área Recomendada para el panel de flujo de correo](../../media/mfi-fix-possible-mail-loop.png)

Al hacer clic **en Ver detalles** en el widget, aparece un control flotante con más información:

- **Dominio**
- **Número de mensajes:**  puede hacer clic [](message-trace-scc.md) en Ver mensajes de ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes que se vieron afectados por el bucle.
- **Tipo de dominio**" Por ejemplo, autoritativo o no autoritativo.
- **Registro MX:** el host (**servidor de correo)** y los valores **de** prioridad del registro MX para el dominio.
- **Motivo del** bucle **y cómo corregir:** identificaremos los escenarios de bucle de correo más comunes y proporcionaremos las acciones recomendadas para corregir el bucle.

![Control desplegable de detalles que aparece después de hacer clic en Ver detalles en la información corregir posible bucle de correo](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Consulta también

Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
