---
title: Informe de dominio no aceptado en el panel de flujo de correo
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
description: Los administradores pueden aprender a usar el informe de dominio no aceptado en el panel de flujo de correo en el centro de seguridad & cumplimiento para supervisar los mensajes de la organización local donde el dominio del remitente no está configurado en Microsoft 365.
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826946"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Informe de dominio no aceptado en el centro de seguridad & cumplimiento

El informe de **dominio no aceptado** del [Panel de flujo de correo](mail-flow-insights-v2.md) en el centro de seguridad & cumplimiento muestra información sobre los mensajes de la organización de correo electrónico local donde el dominio del remitente no está configurado como un dominio aceptado en la organización de Microsoft 365.

Microsoft 365 puede limitar estos mensajes si tenemos datos para probar que la intención de estos mensajes es malintencionada. Por lo tanto, es importante que comprenda lo que está sucediendo y que solucione el problema.

![Widget de dominio no aceptado en el panel de flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Vista informes para el informe de dominio no aceptado

Al hacer clic en el gráfico en el widget de **dominio no aceptado** , irá al informe de **dominio no aceptado** .

De forma predeterminada, se muestra la actividad de todos los conectores afectados. Si hace clic en **Mostrar datos de**, puede seleccionar un conector específico en la lista desplegable.

Si desplaza el puntero sobre un punto de datos (día) del gráfico, verá el número total de mensajes para el conector.

![Vista informes en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Vista de tabla de detalles para el informe de dominio no aceptado

Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:

- **Fecha**
- **Nombre del conector de entrada**
- **Dominio del remitente**
- **Número de mensajes**
- **Mensajes de ejemplo**: los identificadores de mensaje de una muestra de mensajes afectados.

Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **solicitar descarga**.

Cuando se selecciona una fila de la tabla, aparece un control flotante con la siguiente información:

- **Fecha**
- **Nombre del conector de entrada**
- **Dominio del remitente**
- **Número de mensajes**
- **Mensajes de ejemplo**: puede hacer clic en **Ver mensajes de muestra** para ver los resultados de [seguimiento de mensajes](message-trace-scc.md) para obtener una muestra de los mensajes afectados.

![Flotante de detalles después de seleccionar una fila en la vista de tabla de detalles en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Para volver a la vista informes, haga clic en **Ver informe**.

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
