---
title: Informe de dominio no aceptado en el panel de flujo de correo
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
description: Los administradores pueden aprender a usar el informe de dominio no aceptado en el panel de flujo de correo del Centro de seguridad & y cumplimiento para supervisar los mensajes de la organización local donde el dominio del remitente no está configurado en Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 401d566158ca3f730af94fab60c471484e244a16
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029851"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Informe de dominio no aceptado en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


El  informe de dominio [](mail-flow-insights-v2.md) no aceptado en el panel de flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra información sobre los mensajes de la organización de correo electrónico local donde el dominio del remitente no está configurado como un dominio aceptado en su organización de Microsoft 365.

Microsoft 365 puede limitar estos mensajes si tenemos datos para demostrar que la intención de estos mensajes es malintencionada. Por lo tanto, es importante que comprenda lo que está sucediendo y que solucione el problema.

![Widget dominio no aceptado en el panel flujo de correo del Centro de & cumplimiento](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Vista de informe para el informe de dominio no aceptado

Al hacer clic en el gráfico del widget **Dominio** no aceptado, se le llevará al **informe de dominio no** aceptado.

De forma predeterminada, se muestra la actividad de todos los conectores afectados. Si hace clic **en Mostrar datos para,** puede seleccionar un conector específico en la lista desplegable.

Si mantiene el puntero sobre un punto de datos (día) en el gráfico, verá el número total de mensajes para el conector.

![Vista de informe en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Vista de tabla de detalles para el informe de dominio no aceptado

Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:

- **Fecha**
- **Nombre del conector de entrada**
- **Dominio del remitente**
- **Recuento de mensajes**
- **Mensajes de** ejemplo: los iDs de mensaje de una muestra de mensajes afectados.

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **Solicitar descarga.**

Al seleccionar una fila de la tabla, aparece un menú desplegable con la siguiente información:

- **Fecha**
- **Nombre del conector de entrada**
- **Dominio del remitente**
- **Recuento de mensajes**
- **Mensajes de** ejemplo: puede hacer clic en **Ver mensajes de** ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes afectados. [](message-trace-scc.md)

![Menú desplegable De detalles después de seleccionar una fila en la vista Tabla de detalles en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Para volver a la vista informes, haga clic **en Ver informe.**

## <a name="related-topics"></a>Temas relacionados

Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
