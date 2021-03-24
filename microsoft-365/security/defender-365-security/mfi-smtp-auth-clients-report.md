---
title: Información e informe de clientes de autenticación SMTP en el panel flujo de correo
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
description: Los administradores pueden aprender a usar la información y el informe de autenticación SMTP en el panel flujo de correo del Centro de seguridad y cumplimiento de & para supervisar los remitentes de correo electrónico de su organización que usan SMTP autenticado (AUTH SMTP) para enviar mensajes de correo electrónico.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a979f0e80fc303868bf2572974563323035fc4bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070016"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Información e informes de clientes de autenticación SMTP en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La información de los [](mail-flow-insights-v2.md) clientes de autenticación **SMTP** en el panel flujo de correo y el informe de clientes de autenticación [SMTP](#smtp-auth-clients-report) asociados en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) resaltan el uso del protocolo de envío de cliente AUTH SMTP por parte de los usuarios o cuentas del sistema de su organización. Este protocolo heredado (que usa el punto de conexión smtp.office365.com) solo ofrece autenticación básica y es susceptible de ser usado por cuentas comprometidas para enviar correo electrónico. La información y el informe permiten comprobar si hay actividad inusual en los envíos de correo electrónico smtp AUTH. También muestra los datos de uso de TLS para clientes o dispositivos que usan autenticación SMTP.

El widget indica el número de usuarios o cuentas de servicio que han usado el protocolo de autenticación SMTP en los últimos 7 días.

![Widget de clientes de autenticación SMTP en el panel flujo de correo del Centro de seguridad & cumplimiento](../../media/mfi-smtp-auth-clients-report-widget.png)

Si hace clic en el número de mensajes del widget, aparecerá un control flotante de **clientes de autenticación SMTP.** El menú desplegable proporciona una vista agregada del uso y los volúmenes de TLS de la última semana.

![Control flotante de detalles después de hacer clic en el widget Clientes de autenticación SMTP en el panel flujo de correo](../../media/mfi-smtp-auth-clients-report-details.png)

Puede hacer clic en el vínculo Informe de clientes **de autenticación SMTP** para ir al informe de clientes de autenticación SMTP, tal como se describe en la sección siguiente.

## <a name="smtp-auth-clients-report"></a>Informe de clientes de autenticación SMTP

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Vista Informe para el informe de clientes de autenticación SMTP

De forma predeterminada, el informe muestra los datos de los últimos 7 días, pero los datos están disponibles para los últimos 90 días.

La sección de información general contiene los siguientes gráficos:

- **Ver datos por: Enviar** volumen: De forma predeterminada, el gráfico muestra el número de mensajes de cliente de autenticación SMTP que se enviaron desde todos los dominios ( Mostrar datos **para:** Todos los dominios de remitente están seleccionados de forma predeterminada). Puede filtrar los resultados a un dominio de remitente específico haciendo clic en Mostrar **datos** para y seleccionando el dominio del remitente en la lista desplegable. Si mantiene el puntero sobre un punto de datos específico (día), se muestra el número de mensajes.

  ![Vista de envío de volumen en el informe de clientes de autenticación SMTP en el Centro de seguridad & cumplimiento](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Ver datos por: Uso de TLS:** el gráfico muestra el porcentaje de uso de TLS para todos los mensajes de cliente de autenticación SMTP durante el período de tiempo seleccionado. Este gráfico le permite identificar y realizar acciones en usuarios y cuentas del sistema que siguen usando versiones anteriores de TLS.

  ![Vista de uso de TLS en el informe de clientes de autenticación SMTP en el Centro de seguridad & cumplimiento](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**

Haga **clic en** Solicitar informe para recibir una versión más detallada del informe en un mensaje de correo electrónico. Puede especificar el intervalo de fechas y los destinatarios para recibir el informe.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Vista de tabla De detalles para el informe de clientes de autenticación SMTP

Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba mirando:

- **Ver datos por: Volumen de envío:** la siguiente información se muestra en una tabla:

  - **Dirección del remitente**
  - **Recuento de mensajes**

  Si selecciona una fila, los mismos detalles se muestran en un menú desplegable.

- **Ver datos por: Uso de TLS:** la siguiente información se muestra en una tabla:

  - **Dirección del remitente**
  - **TLS1,0%**<sup>\*</sup>
  - **TLS1,1%**<sup>\*</sup>
  - **TLS1,2%**<sup>\*</sup>
  - **Recuento de mensajes**

  <sup>\*</sup> Esta columna muestra el porcentaje y el número de mensajes del remitente.

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**

Si selecciona una fila, se muestran detalles similares en un menú desplegable:

![Los detalles se desván de la tabla de detalles de la vista de uso de TLS en el informe de clientes de autenticación SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Haga **clic en** Solicitar informe para recibir una versión más detallada del informe en un mensaje de correo electrónico. Puede especificar el intervalo de fechas y los destinatarios para recibir el informe.

Para volver a la vista informes, haga clic **en Ver informe**.

## <a name="related-topics"></a>Temas relacionados

Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).
