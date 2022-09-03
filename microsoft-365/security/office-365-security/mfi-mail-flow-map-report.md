---
title: Mapa de flujo de correo
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el mapa flujo de correo en el panel Flujo de correo del Centro de cumplimiento de seguridad & para visualizar y realizar un seguimiento de cómo fluye el correo hacia y desde su organización a través de conectores y sin usar conectores.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 36ab396e626f50adc2e5d420563fe100d579bbfc
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597854"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mapa de flujo de correo en el Centro de cumplimiento de seguridad &

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El **mapa Flujo de correo** del [panel Flujo de correo](mail-flow-insights-v2.md) del [Centro de cumplimiento de seguridad &](https://protection.office.com) proporciona información sobre cómo fluye el correo a través de la organización. Puede usar esta información para aprender patrones, identificar anomalías y corregir problemas a medida que se producen.

:::image type="content" source="../../media/mfi-mail-flow-map-widget.png" alt-text="Widget De mapa de flujo de correo en el panel Flujo de correo del Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-mail-flow-map-widget.png":::

De forma predeterminada, el widget muestra el patrón de flujo de correo del día anterior en un gráfico conocido como diagrama *sankey* . Puede usar la flecha ![izquierda flecha izquierda.](../../media/scc-left-arrow.png) y flecha ![derecha flecha](../../media/scc-right-arrow.png) derecha para mostrar información de diferentes días. Cada color diferente representa el flujo de correo sobre un conector de entrada o salida diferente (o sin usar conectores). Si mantiene el puntero sobre un color específico, se muestra el número de mensajes para ese tipo de conector.

## <a name="report-view-for-the-mail-flow-map"></a>Vista de informe para el mapa de flujo de correo

Al hacer clic en el widget **Mapa de flujo de correo** , se le llevará al informe **mapa de flujo de correo** .

Los siguientes gráficos están disponibles en la vista de informe:

- **Mostrar datos para: Información general**: se trata básicamente de una vista más grande del widget. Si mantiene el puntero sobre un color específico, se muestra el número de mensajes para ese tipo de conector.

    :::image type="content" source="../../media/mfi-mail-flow-map-report-overview.png" alt-text="La vista Información general del informe de mapa de flujo de correo" lightbox="../../media/mfi-mail-flow-map-report-overview.png":::

- **Mostrar datos para: Detalles:** esta vista muestra detalles sobre los conectores y los dominios de destino. Se muestran los dominios principales de remitente y destinatario y el resto se colocan en **Otros**. Si mantiene el puntero sobre un color y una sección específicos, se muestra el número de mensajes.

    :::image type="content" source="../../media/mfi-mail-flow-map-report-detail.png" alt-text="Vista Detalles del informe de mapa de flujo de correo" lightbox="../../media/mfi-mail-flow-map-report-detail.png":::

Si hace clic en **Filtros** en una vista de informe, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.

Las conclusiones relacionadas se muestran debajo del mapa flujo de correo si están disponibles (por ejemplo, corregir [la posible información del bucle de correo](mfi-mail-loop-insight.md)).

## <a name="details-table-view-for-the-mail-flow-map"></a>Vista de tabla de detalles para el mapa de flujo de correo

Si hace clic en **Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:

- **Date**
- **Categoría**
- **Conector o proveedor de servicios de terceros**
- **Dominio remitente/destinatario**
- **Recuento de mensajes**

Si hace clic en **Filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

Si selecciona una fila, se muestran detalles similares en un control flotante:

:::image type="content" source="../../media/mfi-mail-flow-map-view-details-table-details.png" alt-text="El control flotante Detalles de la tabla de detalles en el mapa de flujo de correo" lightbox="../../media/mfi-mail-flow-map-view-details-table-details.png":::

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.

Para volver a la vista de informes, haga clic en **Ver informe**.

## <a name="see-also"></a>Vea también

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
