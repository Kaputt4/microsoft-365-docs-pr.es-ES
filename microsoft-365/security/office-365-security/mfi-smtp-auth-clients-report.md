---
title: Información e informe de clientes de autenticación SMTP en el panel flujo de correo
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
description: Los administradores pueden aprender a usar la información y el informe de autenticación SMTP en el panel Flujo de correo del Centro de cumplimiento de seguridad & para supervisar a los remitentes de correo electrónico de su organización que usan SMTP autenticado (SMTP AUTH) para enviar mensajes de correo electrónico.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 7fdd41d0a6c8d0104c524b577ea754ec915f321c
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597357"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Información e informes de clientes de autenticación SMTP en el Centro de cumplimiento de seguridad &

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La información de **los clientes de autenticación SMTP** en el [panel flujo de correo](mail-flow-insights-v2.md) y el [informe de clientes de autenticación SMTP](#smtp-auth-clients-report) asociados en el Centro de cumplimiento [de seguridad &](https://protection.office.com) resaltan el uso del protocolo de envío de cliente SMTP AUTH por parte de usuarios o cuentas del sistema de su organización. Este protocolo heredado (que usa el punto de conexión smtp.office365.com) solo ofrece autenticación básica y es susceptible de ser utilizado por cuentas en peligro para enviar correo electrónico. La información y el informe le permiten comprobar si hay actividad inusual para envíos de correo electrónico SMTP AUTH. También muestra los datos de uso de TLS para los clientes o dispositivos que usan SMTP AUTH.

El widget indica el número de usuarios o cuentas de servicio que han usado el protocolo de autenticación SMTP en los últimos 7 días.

:::image type="content" source="../../media/mfi-smtp-auth-clients-report-widget.png" alt-text="Widget clientes de autenticación SMTP en el panel Flujo de correo del Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-smtp-auth-clients-report-widget.png":::

Si hace clic en el número de mensajes del widget, aparece un control flotante **clientes de autenticación SMTP** . El control flotante proporciona una vista agregada del uso de TLS y los volúmenes de la última semana.

:::image type="content" source="../../media/mfi-smtp-auth-clients-report-details.png" alt-text="El control flotante Detalles después de hacer clic en el widget Clientes de autenticación SMTP en el panel Flujo de correo" lightbox="../../media/mfi-smtp-auth-clients-report-details.png":::

Puede hacer clic en el vínculo **del informe clientes de autenticación SMTP** para ir al informe clientes de autenticación SMTP, tal como se describe en la sección siguiente.

## <a name="smtp-auth-clients-report"></a>Informe de clientes de autenticación SMTP

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Vista de informe para el informe de clientes de autenticación SMTP

De forma predeterminada, el informe muestra los datos de los últimos 7 días, pero los datos están disponibles durante los últimos 90 días.

La sección de información general contiene los siguientes gráficos:

- **Ver datos mediante: Envío de volumen**: de forma predeterminada, el gráfico muestra el número de mensajes de cliente de autenticación SMTP que se enviaron desde todos los dominios (**Mostrar datos para: Todos los dominios de remitente** están seleccionados de forma predeterminada). Para filtrar los resultados a un dominio de remitente específico, haga clic en **Mostrar datos para** y seleccione el dominio del remitente en la lista desplegable. Si mantiene el puntero sobre un punto de datos específico (día), se muestra el número de mensajes.

  :::image type="content" source="../../media/mfi-smtp-auth-clients-report-sending-volume-view.png" alt-text="La vista Envío de volúmenes en el informe clientes de autenticación SMTP en el Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-smtp-auth-clients-report-sending-volume-view.png":::

- **Ver datos por: Uso de TLS**: el gráfico muestra el porcentaje de uso de TLS para todos los mensajes de cliente de autenticación SMTP durante el período de tiempo seleccionado. Este gráfico le permite identificar y realizar acciones en usuarios y cuentas del sistema que todavía usan versiones anteriores de TLS.

  :::image type="content" source="../../media/mfi-smtp-auth-clients-report-tls-usage-view.png" alt-text="La vista de uso de TLS en el informe de clientes de autenticación SMTP en el Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-smtp-auth-clients-report-tls-usage-view.png":::

Si hace clic en **Filtros** en una vista de informe, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

Haga clic en **Solicitar informe** para recibir una versión más detallada del informe en un mensaje de correo electrónico. Puede especificar el intervalo de fechas y los destinatarios para recibir el informe.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Vista de tabla de detalles para el informe de clientes de autenticación SMTP

Si hace clic en **Ver tabla de detalles**, la información que se muestra depende del gráfico que esté examinando:

- **Ver datos mediante: Envío de volumen**: la siguiente información se muestra en una tabla:

  - **Dirección del remitente**
  - **Recuento de mensajes**

  Si selecciona una fila, los mismos detalles se muestran en un control flotante.

- **Ver datos mediante: Uso de TLS**: en una tabla se muestra la siguiente información:

  - **Dirección del remitente**
  - **TLS1.0%**<sup>\*</sup>
  - **TLS1.1%**<sup>\*</sup>
  - **TLS1.2%**<sup>\*</sup>
  - **Recuento de mensajes**

  <sup>\*</sup> Esta columna muestra el porcentaje y el número de mensajes del remitente.

Si hace clic en **Filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

Si selecciona una fila, se muestran detalles similares en un control flotante:

:::image type="content" source="../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png" alt-text="El control flotante Detalles de la tabla de detalles de la vista de uso de TLS en el informe clientes de autenticación SMTP" lightbox="../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png":::

Haga clic en **Solicitar informe** para recibir una versión más detallada del informe en un mensaje de correo electrónico. Puede especificar el intervalo de fechas y los destinatarios para recibir el informe.

Para volver a la vista de informes, haga clic en **Ver informe**.

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
