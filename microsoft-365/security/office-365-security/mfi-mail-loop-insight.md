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
description: Los administradores pueden aprender a usar la información sobre corregir posibles bucles de correo en el panel flujo de correo del Centro de seguridad y cumplimiento de & para identificar y corregir bucles de correo en su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207302"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Corregir posibles perspectivas de bucle de correo en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Los bucles de correo son malos porque:

- Desperdician recursos del sistema.
- Consumen la cuota de volumen de correo de la organización.
- Envían informes confusos de no entrega (también conocidos como NDR o mensajes de rebote) a los remitentes de mensajes originales.

Fix **possible mail loop** insight in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance [Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.

Esta información aparece solo después de que se detecte la condición (si no tiene bucles de correo, no verá la información).

![Corregir la información de reglas de flujo de correo lento en el área Recomendado para usted del panel flujo de correo](../../media/mfi-fix-possible-mail-loop.png)

Al hacer clic **en Ver detalles** en el widget, aparece un control flotante con más información:

- **Dominio**
- **Número de mensajes:** puede hacer clic [](message-trace-scc.md) en **Ver** mensajes de ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes que se vieron afectados por el bucle.
- **Tipo de dominio**" Por ejemplo, Autoritativo o no autoritativo.
- **Registro MX:** el host (**servidor de correo**) y los valores **de** prioridad del registro MX para el dominio.
- **Motivo del** bucle **y Cómo corregir:** identificaremos los escenarios de bucle de correo más comunes y proporcionaremos acciones recomendadas para corregir el bucle.

![Control de detalles que aparece después de hacer clic en Ver detalles en la información de corregir posibles bucles de correo](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Consulte también

Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).
