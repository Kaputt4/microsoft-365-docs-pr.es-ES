---
title: Informes y información sobre los clientes de autenticación SMTP en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el informe de conocimiento de autenticación de SMTP en el panel de flujo de correo en el centro de seguridad & cumplimiento para supervisar los remitentes de correo electrónico de su organización que usan SMTP autenticado (autenticación SMTP) para enviar mensajes de correo electrónico.
ms.openlocfilehash: afdcf01260dd6dfcaf6b53d107e5addd007b1fb3
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577258"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Informes y información sobre los clientes de autenticación SMTP en el centro de seguridad & cumplimiento

La introducción a los **clientes de autenticación SMTP** en el [Panel de flujo de correo](mail-flow-insights-v2.md) y en el informe de clientes de [autenticación SMTP](#smtp-auth-clients-report) asociados resalta el uso del Protocolo de envío de cliente de autenticación SMTP por parte de los usuarios o las cuentas del sistema de la organización. Este protocolo heredado (que usa el punto de conexión smtp.office365.com) solo ofrece autenticación básica y es vulnerable a su uso por parte de cuentas comprometidas para enviar correo electrónico. La información y el informe permiten buscar actividades inusuales para los envíos de correo electrónico de autenticación SMTP. También muestra los datos de uso de TLS para clientes o dispositivos que usan SMTP AUTH.

El widget indica el número de usuarios o cuentas de servicio que han usado el protocolo de autenticación SMTP en los últimos 7 días.

![Widget SMTP AUTH clients en el panel de flujo de correo del centro de seguridad & cumplimiento](../../media/mfi-smtp-auth-clients-report-widget.png)

Si hace clic en el número de mensajes del widget, aparece un control flotante **clientes de autenticación SMTP** . El control flotante proporciona una vista agregada de los volúmenes y el uso de TLS para la semana pasada.

![Flotante de detalles después de hacer clic en el widget de clientes de autenticación SMTP en el panel de flujo de correo](../../media/mfi-smtp-auth-clients-report-details.png)

Puede hacer clic en el vínculo de **Informe clientes de autenticación SMTP** para ir al informe de clientes de autenticación SMTP, como se describe en la siguiente sección.

## <a name="smtp-auth-clients-report"></a>Informe de clientes de autenticación SMTP

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Vista informes para el informe de clientes de autenticación SMTP

De forma predeterminada, el informe muestra los datos de los últimos 7 días, pero los datos están disponibles para los últimos 90 días.

La sección información general contiene los siguientes gráficos:

- **Ver datos por: volumen de envío**: de forma predeterminada, el gráfico muestra el número de mensajes de cliente de autenticación SMTP que se enviaron desde todos los dominios (**Mostrar datos para: todos los dominios de remite** están seleccionados de forma predeterminada). Puede filtrar los resultados a un dominio de remitente específico haciendo clic en **Mostrar datos para** y seleccionando el dominio del remitente en la lista desplegable. Si pasa por un punto de datos específico (día), se muestra el número de mensajes.

  ![Envío de la vista de volumen en el informe de clientes de autenticación SMTP en el centro de seguridad & cumplimiento](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Ver datos por: uso de TLS**: el gráfico muestra el porcentaje de uso de TLS para todos los mensajes de cliente de autenticación SMTP durante el período de tiempo seleccionado. Este gráfico permite identificar y realizar acciones en usuarios y cuentas del sistema que todavía usan versiones anteriores de TLS.

  ![Vista de uso de TLS en el informe de clientes de autenticación SMTP en el centro de seguridad & cumplimiento](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

Haga clic en **Solicitar informe** para recibir una versión más detallada del informe en un mensaje de correo electrónico. Puede especificar el intervalo de fechas y los destinatarios que recibirán el informe.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Vista de tabla de detalles para el informe de clientes de autenticación SMTP

Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:

- **Ver datos por: volumen de envío**: la siguiente información se muestra en una tabla:

  - **Dirección del remitente**
  - **Número de mensajes**

  Si selecciona una fila, se muestran los mismos detalles en un control flotante.

- **Ver datos por: uso de TLS**: la siguiente información se muestra en una tabla:

  - **Dirección del remitente**
  - **TLS 1.0%**<sup>\*</sup>
  - **TLS 1.1%**<sup>\*</sup>
  - **TLS 1.2%**<sup>\*</sup>
  - **Número de mensajes**

  <sup>\*</sup>Esta columna muestra el porcentaje y el número de mensajes del remitente.

Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

Si selecciona una fila, se muestran detalles similares en un control flotante:

![Flotante de detalles de la tabla de detalles de la vista uso de TLS en el informe de clientes de autenticación SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Haga clic en **Solicitar informe** para recibir una versión más detallada del informe en un mensaje de correo electrónico. Puede especificar el intervalo de fechas y los destinatarios que recibirán el informe.

Para volver a la vista informes, haga clic en **Ver informe**.

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
