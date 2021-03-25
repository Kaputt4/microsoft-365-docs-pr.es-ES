---
title: Informe de no entrega en el panel flujo de correo
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
description: Los administradores pueden aprender a usar el informe de detalles de no entrega en el panel flujo de correo del Centro de cumplimiento de seguridad de & para supervisar los códigos de error encontrados con más frecuencia en los informes de no entrega (también conocidos como NDR o mensajes de rebote) de los remitentes de su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d25f11051606139c2ee8b88cade18963de599d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207291"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Informe de no entrega en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El  informe de no [](mail-flow-insights-v2.md) entrega en el panel flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra los códigos de error más encontrados en los informes de no entrega (también conocidos como NDR o mensajes de rebote) para los usuarios de su organización. Este informe muestra los detalles de las NDR para que pueda solucionar problemas de entrega de correo electrónico.

![Widget de informe de no entrega en el panel Flujo de correo del Centro de & cumplimiento](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Vista Informe para el informe de no entrega

Al hacer clic en el widget **Informe de no** entrega, se le llevará al informe de no **entrega.**

De forma predeterminada, se muestra la actividad de todos los códigos de error. Si hace clic **en Mostrar datos para**, puede seleccionar un código de error específico en el desplegable.

Si mantiene el mouse sobre un color específico (código de error) en un día específico del gráfico, verá el número total de mensajes del error.

![Vista Informe en el informe de dominio no aceptado](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Vista de tabla Detalles del informe de no entrega

Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:

- **Fecha**
- **Código de informe de no entrega**
- **Count**
- **Mensajes de** ejemplo: los IDs de mensaje de una muestra de mensajes afectados.

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.

Al seleccionar una fila de la tabla, aparece un menú desplegable con la siguiente información:

- **Fecha**
- **Código de informe de no** entrega: puede hacer clic en el vínculo para obtener más información sobre las causas y soluciones del código de error específico.
- **Count**
- **Mensajes de** ejemplo: puede hacer clic **en Ver mensajes de ejemplo** para ver los resultados del seguimiento de mensajes de una muestra de los mensajes afectados. [](message-trace-scc.md)

![El menú desplegable de detalles después de seleccionar una fila en la vista Tabla de detalles en el informe de no entrega](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Temas relacionados

Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).
