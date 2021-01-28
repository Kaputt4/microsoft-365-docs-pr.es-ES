---
title: Informe de no entrega en el panel de flujo de correo
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
description: Los administradores pueden aprender a usar el informe de detalles de no entrega en el panel de flujo de correo del Centro de seguridad & y cumplimiento para supervisar los códigos de error encontrados con más frecuencia en los informes de no entrega (también conocidos como NDRs o mensajes de de retorno) de remitentes de su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbd27fc818a46a983874a04f0e313c622e047ea5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029839"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Informe de no entrega en el Centro de & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


El  informe de no [](mail-flow-insights-v2.md) entrega en el panel de flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra los códigos de error más encontrados en los informes de no entrega (también conocidos como NDRs o mensajes de de retorno) para los usuarios de su organización. Este informe muestra los detalles de los NDRs para que pueda solucionar problemas de entrega de correo electrónico.

![Widget Informe de no entrega en el panel flujo de correo del Centro de & cumplimiento](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Vista de informe para el informe de no entrega

Al hacer clic en el widget **Informe de no** entrega, se le llevará al informe de no **entrega.**

De forma predeterminada, se muestra la actividad de todos los códigos de error. Si hace clic **en Mostrar datos para,** puede seleccionar un código de error específico en la lista desplegable.

Si mantiene el puntero sobre un color específico (código de error) en un día específico del gráfico, verá el número total de mensajes del error.

![Vista de informe en el informe de dominio no aceptado](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Vista de tabla de detalles para el informe de no entrega

Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:

- **Fecha**
- **Código de informe de no entrega**
- **Count**
- **Mensajes de** ejemplo: los iDs de mensaje de una muestra de mensajes afectados.

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o más destinatarios, haga clic en **Solicitar descarga.**

Al seleccionar una fila de la tabla, aparece un menú desplegable con la siguiente información:

- **Fecha**
- **Código de informe de no** entrega: puede hacer clic en el vínculo para obtener más información sobre las causas y soluciones del código de error específico.
- **Count**
- **Mensajes de** ejemplo: puede hacer clic en **Ver mensajes de** ejemplo para ver los resultados del seguimiento de mensajes de una muestra de los mensajes afectados. [](message-trace-scc.md)

![Menú desplegable Detalles después de seleccionar una fila en la vista Tabla de detalles en el informe de no entrega](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Temas relacionados

Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
