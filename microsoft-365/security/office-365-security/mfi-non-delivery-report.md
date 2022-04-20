---
title: Informe de no entrega en el panel flujo de correo
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
description: Los administradores pueden aprender a usar el informe Detalles de no entrega en el panel Flujo de correo del Centro de cumplimiento de seguridad & para supervisar los códigos de error que se encuentran con más frecuencia en los informes de no entrega (también conocidos como NDR o mensajes de rebote) de los remitentes de su organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 663e145bcf9d6dc95f0f71b3b0b50a78419ed989
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64973517"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Informe de no entrega en el Centro de cumplimiento de seguridad &

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El **informe No entrega** del [panel Flujo de correo](mail-flow-insights-v2.md) del Centro de [cumplimiento de seguridad &](https://protection.office.com) muestra los códigos de error más encontrados en los informes de no entrega (también conocidos como NDR o mensajes de rebote) para los usuarios de su organización. En este informe se muestran los detalles de los NDR para que pueda solucionar problemas de entrega de correo electrónico.

:::image type="content" source="../../media/mfi-non-delivery-report-widget.png" alt-text="Widget Informe de no entrega en el panel Flujo de correo del Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-non-delivery-report-widget.png":::

## <a name="report-view-for-the-non-delivery-report"></a>Vista de informe para el informe de no entrega

Al hacer clic en el widget **Informe de no entrega** , se le llevará al **informe de no entrega**.

De forma predeterminada, se muestra la actividad de todos los códigos de error. Si hace clic en **Mostrar datos para**, puede seleccionar un código de error específico en la lista desplegable.

Si mantiene el puntero sobre un color específico (código de error) en un día específico del gráfico, verá el número total de mensajes para el error.

:::image type="content" source="../../media/mfi-non-delivery-report-overview-view.png" alt-text="Vista Informe en el informe de dominio no aceptado" lightbox="../../media/mfi-non-delivery-report-overview-view.png":::

## <a name="details-table-view-for-the-non-delivery-report"></a>Vista de tabla de detalles para el informe de no entrega

Si hace clic en **Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:

- **Date**
- **Código del informe de no entrega**
- **Count**
- **Mensajes de ejemplo**: identificadores de mensaje de un ejemplo de mensajes afectados.

Si hace clic en **Filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

Para enviar por correo electrónico el informe de un intervalo de fechas específico a uno o varios destinatarios, haga clic en **Solicitar descarga**.

Al seleccionar una fila de la tabla, aparece un control flotante con la siguiente información:

- **Date**
- **Código del informe de no entrega**: puede hacer clic en el vínculo para buscar más información sobre las causas y las soluciones del código de error específico.
- **Count**
- **Mensajes de ejemplo**: puede hacer clic en **Ver mensajes de ejemplo** para ver los resultados del [seguimiento](message-trace-scc.md) de mensajes de un ejemplo de los mensajes afectados.

:::image type="content" source="../../media/mfi-non-delivery-report-details-flyout.png" alt-text="El control flotante Detalles después de seleccionar una fila en la vista de tabla Detalles en el informe de no entrega" lightbox="../../media/mfi-non-delivery-report-details-flyout.png":::

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
