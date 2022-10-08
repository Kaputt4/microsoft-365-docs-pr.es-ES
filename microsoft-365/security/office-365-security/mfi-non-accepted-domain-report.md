---
title: Informe de dominio no aceptado en el panel flujo de correo
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: m365-security
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el informe de dominio no aceptado en el panel Flujo de correo del Centro de cumplimiento de seguridad & para supervisar los mensajes de la organización local donde el dominio del remitente no está configurado en Microsoft 365.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 4073014a3266891832a1b0b18cea40df71b80b6d
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68083965"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Informe de dominio no aceptado en el Centro de cumplimiento de seguridad &

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El informe de **dominio no aceptado** en el [panel Flujo de correo](mail-flow-insights-v2.md) del [Centro de cumplimiento de seguridad &](https://protection.office.com) muestra información sobre los mensajes de la organización de correo electrónico local donde el dominio del remitente no está configurado como un dominio aceptado en su organización de Microsoft 365.

Microsoft 365 podría limitar estos mensajes si tenemos datos para demostrar que la intención de estos mensajes es malintencionada. Por lo tanto, es importante que comprenda lo que sucede y corrija el problema.

:::image type="content" source="../../media/mfi-non-accepted-domain-report-widget.png" alt-text="Widget de dominio no aceptado en el panel Flujo de correo del Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-non-accepted-domain-report-widget.png":::

## <a name="report-view-for-the-non-accepted-domain-report"></a>Vista de informe para el informe de dominio no aceptado

Al hacer clic en el gráfico del widget Dominio **no aceptado** , se le llevará al informe Dominio **no aceptado** .

De forma predeterminada, se muestra la actividad de todos los conectores afectados. Si hace clic en **Mostrar datos para**, puede seleccionar un conector específico en la lista desplegable.

Si mantiene el puntero sobre un punto de datos (día) en el gráfico, verá el número total de mensajes para el conector.

:::image type="content" source="../../media/mfi-non-accepted-domain-report-overview-view.png" alt-text="Vista Informe en el informe de dominio no aceptado" lightbox="../../media/mfi-non-accepted-domain-report-overview-view.png":::

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Vista de tabla de detalles para el informe de dominio no aceptado

Si hace clic en **Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:

- **Date**
- **Nombre del conector de entrada**
- **Dominio del remitente**
- **Recuento de mensajes**
- **Mensajes de ejemplo**: identificadores de mensaje de un ejemplo de mensajes afectados.

Si hace clic en **Filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.

Al seleccionar una fila de la tabla, aparece un control flotante con la siguiente información:

- **Date**
- **Nombre del conector de entrada**
- **Dominio del remitente**
- **Recuento de mensajes**
- **Mensajes de ejemplo**: puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento](message-trace-scc.md) de mensajes de un ejemplo de los mensajes afectados.

:::image type="content" source="../../media/mfi-non-accepted-domain-report-details-flyout.png" alt-text="El control flotante Detalles después de seleccionar una fila en la vista de tabla Detalles en el informe de dominio no aceptado" lightbox="../../media/mfi-non-accepted-domain-report-details-flyout.png":::

Para volver a la vista de informes, haga clic en **Ver informe**.

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
