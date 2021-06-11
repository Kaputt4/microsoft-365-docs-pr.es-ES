---
title: Informe de dominio no aceptado en el panel flujo de correo
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
description: Los administradores pueden aprender a usar el informe de dominio no aceptado en el panel flujo de correo del Centro de seguridad y cumplimiento de & para supervisar los mensajes de la organización local donde el dominio del remitente no está configurado en Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207298"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Informe de dominio no aceptado en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El  informe de dominio [](mail-flow-insights-v2.md) no aceptado en el panel Flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra información sobre los mensajes de la organización de correo electrónico local donde el dominio del remitente no está configurado como dominio aceptado en su organización de Microsoft 365.

Microsoft 365 limitar estos mensajes si tenemos datos para demostrar que la intención de estos mensajes es malintencionada. Por lo tanto, es importante que comprenda lo que está sucediendo y solucione el problema.

![Widget de dominio no aceptado en el panel Flujo de correo del Centro de & cumplimiento](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Vista Informe para el informe de dominio no aceptado

Al hacer clic en el gráfico del widget **Dominio** no aceptado, se le llevará al **informe de dominio no** aceptado.

De forma predeterminada, se muestra la actividad de todos los conectores afectados. Si hace clic **en Mostrar datos para**, puede seleccionar un conector específico en el desplegable.

Si mantiene el mouse sobre un punto de datos (día) en el gráfico, verá el número total de mensajes para el conector.

![Vista Informe en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Vista de tabla De detalles para el informe de dominio no aceptado

Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:

- **Fecha**
- **Nombre del conector de entrada**
- **Dominio del remitente**
- **Recuento de mensajes**
- **Mensajes de** ejemplo: los IDs de mensaje de una muestra de mensajes afectados.

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.

Al seleccionar una fila de la tabla, aparece un menú desplegable con la siguiente información:

- **Fecha**
- **Nombre del conector de entrada**
- **Dominio del remitente**
- **Recuento de mensajes**
- **Mensajes de** ejemplo: puede hacer clic **en Ver mensajes de ejemplo** para ver los resultados del seguimiento de mensajes de una muestra de los mensajes afectados. [](message-trace-scc.md)

![El menú desplegable de detalles después de seleccionar una fila en la vista Tabla de detalles en el informe de dominio no aceptado](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Para volver a la vista informes, haga clic **en Ver informe**.

## <a name="related-topics"></a>Temas relacionados

Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).
