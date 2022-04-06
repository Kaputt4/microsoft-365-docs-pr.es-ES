---
title: Centro de seguridad de Microsoft Defender de operaciones de seguridad
description: Use el panel para identificar dispositivos en riesgo, realizar un seguimiento del estado del servicio y ver estadísticas e información sobre dispositivos y alertas.
keywords: panel, alertas, nuevas, en curso, resuelto, riesgo, dispositivos en riesgo, infecciones, informes, estadísticas, gráficos, gráficos, estado, detecciones de malware activo, categoría de amenazas, categorías, robo de contraseñas, ransomware, exploit, amenaza, baja gravedad, malware activo
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: c08f592ac72be10bb4b967521e7e504a9ae70a86
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472647"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a>Centro de seguridad de Microsoft Defender de operaciones de seguridad

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-abovefoldlink)

El **panel de operaciones de seguridad** es donde se detección y respuesta de puntos de conexión funcionalidades de seguridad. Proporciona una introducción de alto nivel de dónde se han visto las detecciones y resalta dónde se necesitan acciones de respuesta.

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

:::image type="content" source="images/atp-sec-ops-dashboard.png" alt-text="Panel de operaciones de seguridad" lightbox="images/atp-sec-ops-dashboard.png":::

Puedes explorar e investigar alertas y dispositivos para determinar rápidamente si, dónde y cuándo se produjeron actividades sospechosas en la red para ayudarte a comprender el contexto en el que aparecieron.

Desde el **panel de operaciones de** seguridad verás eventos agregados para facilitar la identificación de eventos o comportamientos significativos en un dispositivo. También puede profundizar en eventos granulares e indicadores de bajo nivel.

También tiene iconos en los que se puede hacer clic que dan indicaciones visuales sobre el estado general de mantenimiento de la organización. Cada icono abre una vista detallada de la información general correspondiente.

## <a name="active-alerts"></a>Alertas activas

Puede ver el número total de alertas activas de los últimos 30 días en la red desde el icono. Las alertas se agrupan **en Nuevo** **y En curso**.

:::image type="content" source="images/active-alerts-tile.png" alt-text="La página Alertas activas" lightbox="images/active-alerts-tile.png":::

Cada grupo se subcategorizó aún más en sus niveles de gravedad de alerta correspondientes. Haga clic en el número de alertas dentro de cada anillo de alerta para ver una vista ordenada de la cola de esa categoría (**Nuevo** o **En curso**).

Para obtener más información, vea Información [general sobre alertas](alerts-queue.md).

Cada fila incluye una categoría de gravedad de alerta y una breve descripción de la alerta. Puede hacer clic en una alerta para ver su vista detallada. Para obtener más información, consulte  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).

## <a name="devices-at-risk"></a>Dispositivos en riesgo

Este icono muestra una lista de dispositivos con el mayor número de alertas activas. El número total de alertas para cada dispositivo se muestra en un círculo junto al nombre del dispositivo y, a continuación, se clasifica por niveles de gravedad en el extremo del icono (mantenga el puntero sobre cada barra de gravedad para ver su etiqueta).

:::image type="content" source="images/devices-at-risk-tile.png" alt-text="La página Dispositivos en riesgo" lightbox="images/devices-at-risk-tile.png":::

Haz clic en el nombre del dispositivo para ver detalles sobre ese dispositivo. Para obtener más información, consulta [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md).

También puedes hacer clic en **Lista** de dispositivos en la parte superior del icono para ir directamente a la lista Dispositivos **, ordenada** por el número de alertas activas. Para obtener más información, consulta [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md).

## <a name="devices-with-sensor-issues"></a>Dispositivos con problemas de sensor

El **icono Dispositivos con problemas de sensor** proporciona información sobre la capacidad del dispositivo individual para proporcionar datos del sensor al servicio de Microsoft Defender para puntos de conexión. Informa de cuántos dispositivos requieren atención y le ayuda a identificar dispositivos problemáticos.

:::image type="content" source="images/atp-tile-sensor-health.png" alt-text="Icono Dispositivos con problemas de sensor" lightbox="images/atp-tile-sensor-health.png":::

Hay dos indicadores de estado que proporcionan información sobre el número de dispositivos que no están informando correctamente al servicio:

- **Configuración errónea**: estos dispositivos podrían estar informando parcialmente los datos del sensor al servicio de Microsoft Defender para endpoints y podrían tener errores de configuración que deben corregirse.
- **Inactivo**: dispositivos que han dejado de informar al servicio Microsoft Defender para endpoints durante más de siete días en el último mes.

Cuando hagas clic en cualquiera de los grupos, se te dirigirá a la lista de dispositivos, filtrada según tu elección. Para obtener más información, consulta [Comprobar el estado del sensor](check-sensor-status.md) e [Investigar dispositivos](investigate-machines.md).

## <a name="service-health"></a>Estado del servicio

El **icono Estado** del servicio le informa si el servicio está activo o si hay problemas.

:::image type="content" source="images/status-tile.png" alt-text="La página Estado del servicio" lightbox="images/status-tile.png":::

Para obtener más información sobre el estado del servicio, consulte [Check the Microsoft Defender for Endpoint service health](service-status.md).

## <a name="daily-devices-reporting"></a>Informes de dispositivos diarios

El **icono Informes de dispositivos** diarios muestra un gráfico de barras que representa el número de dispositivos que informan diariamente en los últimos 30 días. Mantenga el mouse sobre barras individuales en el gráfico para ver el número exacto de dispositivos que se informan en cada día.

:::image type="content" source="images/atp-daily-devices-reporting.png" alt-text="Icono de informes de dispositivos diarios" lightbox="images/atp-daily-devices-reporting.png":::

## <a name="active-automated-investigations"></a>Investigaciones automatizadas activas

Puede ver el número total de investigaciones automatizadas de los últimos 30 días en la red desde el icono Investigaciones **automatizadas activas** . Las investigaciones se agrupan en **Pending action**, **Waiting for device y** **Running**.

:::image type="content" source="images/atp-active-investigations-tile.png" alt-text="Las investigaciones automatizadas activas" lightbox="images/atp-active-investigations-tile.png":::

## <a name="automated-investigations-statistics"></a>Estadísticas de investigaciones automatizadas

Este icono muestra estadísticas relacionadas con investigaciones automatizadas en los últimos siete días. Muestra el número de investigaciones completadas, el número de investigaciones correctamente subsanadas, el promedio de tiempo pendiente que tarda en iniciarse una investigación, el tiempo promedio que se tarda en corregir una alerta, el número de alertas investigadas y el número de horas de automatización guardadas de una investigación manual típica. 

:::image type="content" source="images/atp-automated-investigations-statistics.png" alt-text="Estadísticas de investigaciones automatizadas" lightbox="images/atp-automated-investigations-statistics.png":::

Puede hacer clic en **Investigaciones automatizadas**, investigaciones  **subsanadas** y **Alertas** investigadas para navegar a la página Investigaciones, filtrada por la categoría correspondiente. Esto le permite ver un desglose detallado de las investigaciones en contexto.

## <a name="users-at-risk"></a>Usuarios en riesgo

El icono muestra una lista de cuentas de usuario con las alertas más activas y el número de alertas vistas en alertas altas, medianas o bajas. 

:::image type="content" source="images/atp-users-at-risk.png" alt-text="La página Usuarios en riesgo" lightbox="images/atp-users-at-risk.png":::

Haga clic en la cuenta de usuario para ver detalles sobre la cuenta de usuario. Para obtener más información, [vea Investigar una cuenta de usuario](investigate-user.md).

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados

- [Comprender el portal de Microsoft Defender para puntos de conexión](use.md)
- [Introducción al portal](portal-overview.md)
- [Ver el panel de administración & vulnerabilidades](tvm-dashboard-insights.md)
- [Ver el panel análisis de amenazas y realizar acciones de mitigación recomendadas](threat-analytics.md)
