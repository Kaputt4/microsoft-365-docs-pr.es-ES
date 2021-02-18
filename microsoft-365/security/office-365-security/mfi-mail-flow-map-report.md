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
description: Los administradores pueden aprender a usar el mapa de flujo de correo en el panel de flujo de correo del Centro de seguridad y cumplimiento de & para visualizar y realizar un seguimiento de cómo fluye el correo hacia y desde su organización a través de conectores y sin usar conectores.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f507f7f01999492d17e168a2a56da906bfcb52d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290590"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mapa de flujo de correo en el Centro de & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

El **mapa de flujo de correo** en el panel [flujo](mail-flow-insights-v2.md) de correo del Centro de seguridad & [cumplimiento](https://protection.office.com) ofrece información sobre cómo fluye el correo a través de la organización. Puedes usar esta información para aprender patrones, identificar anomalías y solucionar problemas a medida que se producen.

![Widget Mapa de flujo de correo en el panel flujo de correo en el Centro de & cumplimiento](../../media/mfi-mail-flow-map-widget.png)

De forma predeterminada, el widget muestra el patrón de flujo de correo del día anterior en un gráfico conocido como diagrama *Sankey.* Puede usar la flecha izquierda flecha izquierda y flecha derecha flecha ![ derecha para mostrar información de diferentes ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) días. Cada color diferente representa el flujo de correo sobre un conector entrante o saliente diferente (o sin conectores). Si mantiene el puntero sobre un color específico, se muestra el número de mensajes para ese tipo de conector.

## <a name="report-view-for-the-mail-flow-map"></a>Vista de informe para el mapa de flujo de correo

Al hacer clic en el widget **Mapa de flujo de** correo, se le llevará al informe de mapa de flujo **de** correo.

Los siguientes gráficos están disponibles en la vista de informe:

- **Mostrar datos para: Información general:** Básicamente se trata de una vista más grande del widget. Si mueve el puntero sobre un color específico, se muestra el número de mensajes para ese tipo de conector.

  ![Vista de información general en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-overview.png)

- **Mostrar datos para: Detalle:** esta vista muestra detalles sobre los conectores y los dominios de destino. Se enumeran los dominios principales de remitente y destinatario, y el resto se ponen en **Otros**. Si mantiene el puntero sobre un color y una sección específicos, se muestra el número de mensajes.

  ![Vista de detalles en el informe de mapa de flujo de correo](../../media/mfi-mail-flow-map-report-detail.png)

Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con fecha **de inicio** y fecha **de finalización.**

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **Solicitar descarga.**

Las conclusiones relacionadas se muestran debajo del mapa de flujo de correo si están disponibles (por ejemplo, la posible corrección de la información del [bucle de correo).](mfi-mail-loop-insight.md)

## <a name="details-table-view-for-the-mail-flow-map"></a>Vista de tabla de detalles para el mapa de flujo de correo

Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:

- **Fecha**
- **Categoría**
- **Conector/proveedor de servicios de terceros**
- **Dominio de remitente o destinatario**
- **Recuento de mensajes**

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**

Si seleccionas una fila, se muestran detalles similares en un menú desplegable:

![Control de detalles de la tabla de detalles en el mapa de flujo de correo](../../media/mfi-mail-flow-map-view-details-table-details.png)

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **Solicitar descarga.**

Para volver a la vista informes, haga clic **en Ver informe.**

## <a name="see-also"></a>Vea también

Para obtener información sobre otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
