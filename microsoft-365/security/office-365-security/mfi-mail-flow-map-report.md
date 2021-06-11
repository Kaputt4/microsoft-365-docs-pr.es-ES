---
title: Mapa de flujo de correo
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
description: Los administradores pueden aprender a usar el mapa de flujo de correo en el panel flujo de correo del Centro de seguridad y cumplimiento de & para visualizar y realizar un seguimiento de cómo fluye el correo hacia y desde su organización a través de conectores y sin usar conectores.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207547"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mapa de flujo de correo en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El **mapa de flujo de correo** en el panel [Flujo](mail-flow-insights-v2.md) de correo del Centro de seguridad [& cumplimiento](https://protection.office.com) proporciona información sobre cómo fluye el correo a través de la organización. Puede usar esta información para aprender patrones, identificar anomalías y solucionar problemas a medida que se producen.

![Widget de mapa de flujo de correo en el panel Flujo de correo del Centro de seguridad & cumplimiento](../../media/mfi-mail-flow-map-widget.png)

De forma predeterminada, el widget muestra el patrón de flujo de correo del día anterior en un gráfico conocido como diagrama *de Sankey.* Puede usar la flecha izquierda flecha izquierda y flecha derecha flecha ![ derecha para mostrar información de diferentes ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) días. Cada color diferente representa el flujo de correo sobre un conector entrante o saliente diferente (o sin conectores). Si mantiene el mouse sobre un color específico, se muestra el número de mensajes para ese tipo de conector.

## <a name="report-view-for-the-mail-flow-map"></a>Vista Informe para el mapa de flujo de correo

Hacer clic en el widget **Mapa de flujo de** correo le llevará al informe de mapa de flujo **de** correo.

Los gráficos siguientes están disponibles en la vista informe:

- **Mostrar datos para: Información general:** Se trata básicamente de una vista más grande del widget. Si mantiene el mouse sobre un color específico, se muestra el número de mensajes para ese tipo de conector.

  ![Vista introducción en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-overview.png)

- **Mostrar datos para: Detalle:** esta vista muestra detalles sobre los conectores y los dominios de destino. Los dominios principales de remitente y destinatario se enumeran y el resto se ponen en **Otros**. Si mantiene el mouse sobre un color y una sección específicos, se muestra el número de mensajes.

  ![Vista de detalles en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-detail.png)

Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.

Los conocimientos relacionados se muestran debajo del mapa de flujo de correo si están disponibles (por ejemplo, [fix possible mail loop insight](mfi-mail-loop-insight.md)).

## <a name="details-table-view-for-the-mail-flow-map"></a>Vista de tabla Detalles para el mapa de flujo de correo

Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:

- **Fecha**
- **Categoría**
- **Conector /proveedor de servicios de terceros**
- **Dominio de remitente/destinatario**
- **Recuento de mensajes**

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**

Si selecciona una fila, se muestran detalles similares en un menú desplegable:

![Control desplegable de detalles de la tabla de detalles en el mapa de flujo de correo](../../media/mfi-mail-flow-map-view-details-table-details.png)

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.

Para volver a la vista informes, haga clic **en Ver informe**.

## <a name="see-also"></a>Consulte también

Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).
