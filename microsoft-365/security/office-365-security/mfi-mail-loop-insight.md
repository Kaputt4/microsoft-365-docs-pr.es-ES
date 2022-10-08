---
title: Corrección de posible información de bucle de correo
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: m365-security
ms.localizationpriority: medium
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la información corregir posibles bucles de correo en el panel Flujo de correo del Centro de cumplimiento de seguridad & para identificar y corregir bucles de correo en su organización.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 93c623f56e9a4a7bc5dc1ee362f3e9135e3d634a
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68091771"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Corrección de la posible información del bucle de correo en el Centro de cumplimiento de seguridad &

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Los bucles de correo son incorrectos porque:

- Desperdician recursos del sistema.
- Consumen la cuota de volumen de correo de la organización.
- Envían informes confusos de no entrega (también conocidos como NDR o mensajes de rebote) a los remitentes de mensajes originales.

La **opción Corregir posible** información de bucle de correo en el área **Recomendado para usted** del [panel Flujo de correo](mail-flow-insights-v2.md) del [Centro de cumplimiento de seguridad &](https://protection.office.com) le notifica cuándo se detecta un bucle de correo en su organización.

Esta información aparece solo después de detectar la condición (si no tiene ningún bucle de correo, no verá la información).

:::image type="content" source="../../media/mfi-fix-possible-mail-loop.png" alt-text="Información sobre la corrección de reglas de flujo de correo lento en el área Recomendado para usted del panel Flujo de correo" lightbox="../../media/mfi-fix-possible-mail-loop.png":::

Al hacer clic en **Ver detalles** en el widget, aparece un control flotante con más información:

- **Dominio**
- **Número de mensajes**: puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento](message-trace-scc.md) de mensajes de un ejemplo de los mensajes afectados por el bucle.
- **Tipo de dominio**" Por ejemplo, Autoritativo o No autoritativo.
- **Registro MX**: el host (**servidor de correo**) y los valores de **prioridad** del registro MX para el dominio.
- **Motivo del bucle** y **Corrección**: identificaremos los escenarios de bucle de correo más comunes y proporcionaremos las acciones recomendadas para corregir el bucle.

:::image type="content" source="../../media/mfi-fix-possible-mail-loop-details.png" alt-text="El control flotante Detalles que aparece después de hacer clic en Ver detalles en la opción Corregir posible información del bucle de correo" lightbox="../../media/mfi-fix-possible-mail-loop-details.png":::

## <a name="see-also"></a>Vea también

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
