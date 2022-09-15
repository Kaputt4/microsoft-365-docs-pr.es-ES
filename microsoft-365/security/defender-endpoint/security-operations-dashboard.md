---
title: panel de operaciones de seguridad de Centro de seguridad de Microsoft Defender
description: Use el panel para identificar los dispositivos en riesgo, realizar un seguimiento del estado del servicio y ver estadísticas e información sobre dispositivos y alertas.
keywords: dashboard, alerts, new, in progress, resolved, risk, devices at risk, infections, reporting, statistics, charts, graphs, health, active malware detections, threat category, categories, password stealer, ransomware, exploit, threat, low severity, active malware
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: be52ed0d0c4ac2d2388f4d8dd3009e56ee6dbcab
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67693981"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a>panel de operaciones de seguridad de Centro de seguridad de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-abovefoldlink)

El **panel Operaciones de seguridad** es donde se exponen las funcionalidades de detección y respuesta de puntos de conexión. Proporciona información general de alto nivel sobre dónde se han visto las detecciones y los aspectos destacados en los que se necesitan acciones de respuesta.

El panel muestra una instantánea de:

- Alertas activas
- Dispositivos en riesgo
- Estado del sensor
- Estado del servicio
- Informes de dispositivos diarios
- Investigaciones automatizadas activas
- Estadísticas de investigaciones automatizadas
- Usuarios en riesgo
- Actividades sospechosas

:::image type="content" source="images/atp-sec-ops-dashboard.png" alt-text="Panel operaciones de seguridad" lightbox="images/atp-sec-ops-dashboard.png":::

Puede explorar e investigar alertas y dispositivos para determinar rápidamente si, dónde y cuándo se produjeron actividades sospechosas en la red para ayudarle a comprender el contexto en el que aparecieron.

En el **panel Operaciones de seguridad** verá eventos agregados para facilitar la identificación de eventos o comportamientos significativos en un dispositivo. También puede explorar en profundidad los eventos granulares y los indicadores de bajo nivel.

También tiene iconos en los que se pueden hacer clic que proporcionan indicaciones visuales sobre el estado general de mantenimiento de la organización. Cada icono abre una vista detallada de la información general correspondiente.

## <a name="active-alerts"></a>Alertas activas

Puede ver el número total de alertas activas de los últimos 30 días en la red desde el icono. Las alertas se agrupan en **Nuevo** y **En curso**.

:::image type="content" source="images/active-alerts-tile.png" alt-text="Página Alertas activas" lightbox="images/active-alerts-tile.png":::

Cada grupo se subcategoriza en sus niveles de gravedad de alerta correspondientes. Haga clic en el número de alertas dentro de cada anillo de alertas para ver una vista ordenada de la cola de esa categoría (**Nuevo** o **En curso**).

Para obtener más información, consulte [Introducción a las alertas](alerts-queue.md).

Cada fila incluye una categoría de gravedad de alerta y una breve descripción de la alerta. Puede hacer clic en una alerta para ver su vista detallada. Para obtener más información, vea [Investigar alertas de Microsoft Defender para punto de conexión](investigate-alerts.md) e [Información general sobre alertas](alerts-queue.md).

## <a name="devices-at-risk"></a>Dispositivos en riesgo

En este icono se muestra una lista de dispositivos con el mayor número de alertas activas. El número total de alertas para cada dispositivo se muestra en un círculo junto al nombre del dispositivo y, a continuación, se clasifica por niveles de gravedad en el extremo lejano del icono (mantenga el puntero sobre cada barra de gravedad para ver su etiqueta).

:::image type="content" source="images/devices-at-risk-tile.png" alt-text="Página Dispositivos en riesgo" lightbox="images/devices-at-risk-tile.png":::

Haga clic en el nombre del dispositivo para ver los detalles sobre ese dispositivo. Para obtener más información, consulte [Investigar dispositivos en la lista dispositivos de Microsoft Defender para punto de conexión](investigate-machines.md).

También puede hacer clic en **Lista de dispositivos** en la parte superior del icono para ir directamente a la **lista Dispositivos**, ordenada por el número de alertas activas. Para obtener más información, consulte [Investigar dispositivos en la lista dispositivos de Microsoft Defender para punto de conexión](investigate-machines.md).

## <a name="devices-with-sensor-issues"></a>Dispositivos con problemas de sensor

El icono **Dispositivos con problemas de sensor** proporciona información sobre la capacidad del dispositivo individual para proporcionar datos de sensor al servicio de Microsoft Defender para punto de conexión. Notifica cuántos dispositivos requieren atención y le ayuda a identificar dispositivos problemáticos.

:::image type="content" source="images/atp-tile-sensor-health.png" alt-text="Icono Dispositivos con problemas de sensor" lightbox="images/atp-tile-sensor-health.png":::

Hay dos indicadores de estado que proporcionan información sobre el número de dispositivos que no informan correctamente al servicio:

- **Mal configurados**: estos dispositivos podrían estar notificando parcialmente los datos del sensor al servicio Microsoft Defender para punto de conexión y pueden tener errores de configuración que deben corregirse.
- **Inactivo**: los dispositivos que han dejado de informar al servicio de Microsoft Defender para punto de conexión durante más de siete días en el último mes.

Al hacer clic en cualquiera de los grupos, se le dirigirá a la lista de dispositivos, filtrados según su elección. Para obtener más información, consulte [Comprobación del estado del sensor](check-sensor-status.md) e [Investigación de dispositivos](investigate-machines.md).

## <a name="service-health"></a>Estado del servicio

El **icono Estado del servicio** le informa si el servicio está activo o si hay problemas.

:::image type="content" source="images/status-tile.png" alt-text="Página de Estado del servicio" lightbox="images/status-tile.png":::

Para obtener más información sobre el estado del servicio, vea [Comprobar el estado del servicio Microsoft Defender para punto de conexión](service-status.md).

## <a name="daily-devices-reporting"></a>Informes de dispositivos diarios

El icono Informes de **dispositivos diarios** muestra un gráfico de barras que representa el número de dispositivos que notifican diariamente en los últimos 30 días. Mantenga el puntero sobre las barras individuales del gráfico para ver el número exacto de dispositivos que informan en cada día.

:::image type="content" source="images/atp-daily-devices-reporting.png" alt-text="Icono de informes de dispositivos diarios" lightbox="images/atp-daily-devices-reporting.png":::

## <a name="active-automated-investigations"></a>Investigaciones automatizadas activas

Puede ver el número total de investigaciones automatizadas de los últimos 30 días en la red desde el icono **Active automated investigations (Investigaciones automatizadas activas** ). Las investigaciones se agrupan en **acción Pendiente**, **Esperando dispositivo** y **En ejecución**.

:::image type="content" source="images/atp-active-investigations-tile.png" alt-text="Las investigaciones automatizadas activas" lightbox="images/atp-active-investigations-tile.png":::

## <a name="automated-investigations-statistics"></a>Estadísticas de investigaciones automatizadas

En este icono se muestran estadísticas relacionadas con las investigaciones automatizadas de los últimos siete días. Muestra el número de investigaciones completadas, el número de investigaciones corregidas correctamente, el promedio de tiempo pendiente que tarda en iniciarse una investigación, el promedio de tiempo necesario para corregir una alerta, el número de alertas investigadas y el número de horas de automatización guardadas de una investigación manual típica. 

:::image type="content" source="images/atp-automated-investigations-statistics.png" alt-text="Estadísticas de investigaciones automatizadas" lightbox="images/atp-automated-investigations-statistics.png":::

Puede hacer clic en **Investigaciones automatizadas**, **investigaciones corregidas** y **Alertas investigadas** para ir a la página **Investigaciones** , filtrada por la categoría adecuada. Esto le permite ver un desglose detallado de las investigaciones en contexto.

## <a name="users-at-risk"></a>Usuarios en riesgo

El icono muestra una lista de cuentas de usuario con las alertas más activas y el número de alertas que se ven en alertas altas, medianas o bajas. 

:::image type="content" source="images/atp-users-at-risk.png" alt-text="Página Usuarios en riesgo" lightbox="images/atp-users-at-risk.png":::

Haga clic en la cuenta de usuario para ver detalles sobre la cuenta de usuario. Para obtener más información, consulte [Investigación de una cuenta de usuario](investigate-user.md).

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados

- [Descripción del portal de Microsoft Defender para punto de conexión](use.md)
- [Introducción al portal](portal-overview.md)
- [Ver el panel de Administración de vulnerabilidades de Microsoft Defender](tvm-dashboard-insights.md)
- [Ver el panel de análisis de amenazas y realizar las acciones de mitigación recomendadas](threat-analytics.md)
