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
description: Los administradores pueden aprender a usar el mapa de flujo de correo en el panel flujo de correo del Centro de cumplimiento de seguridad & para visualizar y realizar un seguimiento de cómo fluye el correo hacia y desde su organización a través de conectores y sin usar conectores.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 53c86584680f14c68b8d69ac0a0c2fc51933db28
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680146"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mapa de flujo de correo en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El **mapa flujo de correo** en el panel [Flujo](mail-flow-insights-v2.md) de correo del [Centro de seguridad & cumplimiento](https://protection.office.com) proporciona información sobre cómo fluye el correo a través de la organización. Puede usar esta información para aprender patrones, identificar anomalías y solucionar problemas a medida que se producen.

![Widget de mapa de flujo de correo en el panel Flujo de correo del Centro de & cumplimiento.](../../media/mfi-mail-flow-map-widget.png)

De forma predeterminada, el widget muestra el patrón de flujo de correo del día anterior en un gráfico conocido como diagrama *de Sankey* . Puede usar la flecha izquierda flecha ![izquierda.](../../media/scc-left-arrow.png) y flecha derecha flecha ![derecha para](../../media/scc-right-arrow.png) mostrar información de diferentes días. Cada color diferente representa el flujo de correo sobre un conector entrante o saliente diferente (o sin conectores). Si mantiene el mouse sobre un color específico, se muestra el número de mensajes para ese tipo de conector.

## <a name="report-view-for-the-mail-flow-map"></a>Vista Informe para el mapa de flujo de correo

Hacer clic en el widget **Mapa de flujo de** correo le llevará al informe **de mapa de flujo de** correo.

Los gráficos siguientes están disponibles en la vista informe:

- **Mostrar datos para: Overview**: This is basically a larger view of the widget. Si mantiene el mouse sobre un color específico, se muestra el número de mensajes para ese tipo de conector.

  ![Vista Introducción en el informe de mapa de flujo de correo.](../../media/mfi-mail-flow-map-report-overview.png)

- **Mostrar datos para: Detalle**: esta vista muestra detalles sobre los conectores y los dominios de destino. Los dominios principales de remitente y destinatario aparecen en la lista y el resto se ponen en **Otros**. Si mantiene el mouse sobre un color y una sección específicos, se muestra el número de mensajes.

  ![Vista de detalles en el informe de mapa de flujo de correo.](../../media/mfi-mail-flow-map-report-detail.png)

Si hace clic **en Filtros en** una vista de informe, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.

Los conocimientos relacionados se muestran debajo del mapa de flujo de correo si están disponibles (por ejemplo, [fix possible mail loop insight](mfi-mail-loop-insight.md)).

## <a name="details-table-view-for-the-mail-flow-map"></a>Vista de tabla Detalles para el mapa de flujo de correo

Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:

- **Date**
- **Categoría**
- **Conector /proveedor de servicios de terceros**
- **Dominio de remitente/destinatario**
- **Recuento de mensajes**

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

Si selecciona una fila, se muestran detalles similares en un menú desplegable:

![Los detalles se desván de la tabla de detalles en el mapa de flujo de correo.](../../media/mfi-mail-flow-map-view-details-table-details.png)

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.

Para volver a la vista informes, haga clic **en Ver informe**.

## <a name="see-also"></a>Consulte también

Para obtener información sobre otras perspectivas en el panel flujo de correo, vea Información sobre el flujo de correo en el [Centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
