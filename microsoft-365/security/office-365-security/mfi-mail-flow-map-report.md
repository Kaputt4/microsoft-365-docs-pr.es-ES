---
title: Mapa de flujo de correo
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
description: Los administradores pueden aprender a usar el mapa del flujo de correo en el panel de flujo de correo en el centro de seguridad & cumplimiento para visualizar y realizar un seguimiento de la forma en que el correo fluye hacia y desde la organización a través de conectores y sin usar conectores.
ms.openlocfilehash: d27513b905a2b6c1a7ae366040e9e29b2d67b258
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827006"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mapa de flujo de correo en el centro de seguridad & cumplimiento

El **mapa de flujo de correo** en el [Panel de flujo de correo](mail-flow-insights-v2.md) en el centro de seguridad & cumplimiento ofrece información sobre cómo fluye el correo a través de la organización. Puede usar esta información para aprender patrones, identificar anomalías y corregir problemas a medida que se produzcan.

![Widget mail Flow Map en el panel de flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-mail-flow-map-widget.png)

De forma predeterminada, el widget muestra el patrón de flujo de correo del día anterior en un gráfico conocido como diagrama de *Sankey* . Puede usar la flecha izquierda ![ y la flecha ](../../media/scc-left-arrow.png) derecha a la izquierda ![ ](../../media/scc-right-arrow.png) para mostrar información de distintos días. Cada color diferente representa el flujo de correo a través de un conector de entrada o de salida diferente (o sin usar conectores). Si pasa el mouse sobre un color específico, se muestra el número de mensajes para ese tipo de conector.

## <a name="report-view-for-the-mail-flow-map"></a>Vista informes para el mapa de flujo de correo

Al hacer clic en el widget **mapa de flujo de correo** , irá al informe de mapa de flujo de **correo** .

Los siguientes gráficos están disponibles en la vista de informe:

- **Mostrar datos para: información general**: esta es básicamente una vista más amplia del widget. Si pasa el mouse sobre un color específico, se muestra el número de mensajes para ese tipo de conector.

  ![Vista general en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-overview.png)

- **Mostrar datos para: detalles**: esta vista muestra detalles sobre los conectores y los dominios de destino. Se enumeran los principales dominios del remitente y el destinatario, y el resto se colocan en **otros**. Si pasa el mouse sobre un color y una sección específicos, se muestra el número de mensajes.

  ![Vista de detalles en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-detail.png)

Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **solicitar descarga**.

La información relacionada se muestra debajo del mapa de flujo de correo si está disponible (por ejemplo, la [revisión posible del bucle de correo](mfi-mail-loop-insight.md)).

## <a name="details-table-view-for-the-mail-flow-map"></a>Vista de tabla de detalles del mapa de flujo de correo

Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:

- **Fecha**
- **Categoría**
- **Conector/proveedor de servicios de terceros**
- **Dominio de remitente/destinatario**
- **Número de mensajes**

Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

Si selecciona una fila, se muestran detalles similares en un control flotante:

![Flotante de detalles de la tabla de detalles en el mapa de flujo de correo](../../media/mfi-mail-flow-map-view-details-table-details.png)

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **solicitar descarga**.

Para volver a la vista informes, haga clic en **Ver informe**.

## <a name="see-also"></a>Consulte también

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
