---
title: Investigar incidentes en Microsoft 365 Defender
description: Investigar incidentes relacionados con dispositivos, usuarios y buzones.
keywords: incidente, incidentes, análisis, respuesta, máquinas, dispositivos, usuarios, identidades, correo, correo electrónico, buzón, investigación, gráfico, evidencia
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 865aa9dc34a91be251d6f7772da5cc686f9641a4
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651323"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Investigar incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

Microsoft 365 Defender agrega todas las alertas, activos, investigaciones y pruebas relacionadas de todos los dispositivos, usuarios y buzones de correo en un incidente para darle una visión completa de toda la amplitud de un ataque.

Dentro de un incidente, se analizan las alertas que afectan a la red, se entiende lo que significan y se recopilan las pruebas para poder diseñar un plan de corrección eficaz.

## <a name="initial-investigation"></a>Investigación inicial

Antes de entrar en detalles, echa un vistazo a las propiedades y el resumen del incidente.

Para empezar, seleccione el incidente en la columna de marcas de verificación. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Ejemplo de selección de un incidente en la columna de marca de verificación":::

Cuando lo haga, se abrirá un panel de resumen con información clave sobre el incidente, como la gravedad, a quién está asignado, y el ATT de MITRE&categorías [de CK &trade; ](https://attack.mitre.org/) para el incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Ejemplo del panel de resumen de un incidente":::

Desde aquí, puede seleccionar **Abrir página de incidentes**. Esto abre la página principal del incidente donde encontrará más información de resumen y pestañas para alertas, dispositivos, usuarios, investigaciones y pruebas.

También puede abrir la página principal de un incidente seleccionando el nombre del incidente en la cola de incidentes.

## <a name="summary"></a>Resumen

La **página Resumen le** ofrece una vista instantánea de los aspectos principales que debe tener en cuenta sobre el incidente.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Ejemplo de la página Resumen de un incidente en el centro Microsoft 365 seguridad":::

Las categorías de ataque te dan una vista visual y numérica de lo avanzado que ha progresado el ataque en la cadena de eliminación. Al igual que con otros productos de seguridad de Microsoft, Microsoft 365 Defender se alinea con el marco de&[CK &trade; de MITRE ATT.](https://attack.mitre.org/)

La sección de ámbito ofrece una lista de los activos que se han visto afectados y que forman parte de este incidente. Si hay información específica sobre este activo, como el nivel de riesgo, la prioridad de investigación, así como cualquier etiqueta en los activos, esto también se mostrará en esta sección.

La escala de tiempo de alertas proporciona un vistazo al orden cronológico en el que se produjeron las alertas, así como los motivos por los que estas alertas están vinculadas a este incidente.

Y por último: la sección de evidencia proporciona un resumen de cuántos artefactos diferentes se incluyeron en el incidente y su estado de corrección, por lo que puede identificar inmediatamente si necesita alguna acción.

Esta introducción puede ayudar en la evaluación inicial del incidente proporcionando información sobre las características principales del incidente que debe conocer.

## <a name="alerts"></a>Alertas

En la **pestaña** Alerta, puede ver la cola de alertas de alertas relacionadas con el incidente y otra información sobre ellas, como:

- Gravedad.
- Las entidades que participaron en la alerta.
- El origen de las alertas (Microsoft Defender para identity, Microsoft Defender para endpoint, Microsoft Defender para Office 365).
- La razón por la que se vincularon.

Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Ejemplo de una página de alertas para un incidente":::

De forma predeterminada, las alertas se ordenan cronológicamente para que pueda ver cómo se produjo el incidente con el tiempo. Al seleccionar una alerta dentro de un incidente, Microsoft 365 Defender muestra la información de alerta específica del contexto del incidente general. 

Puede ver los eventos de la alerta, qué otras alertas desencadenadas provocaron la alerta actual y todas las entidades y actividades afectadas implicadas en el ataque, incluidos los archivos, los usuarios y los buzones.

Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Ejemplo de una página de detalles de alerta dentro de un incidente":::

Esta página de alerta de incidentes se compone de estas secciones:

- Artículo de alerta, que incluye un resumen de lo que ocurrió
- Alertas y eventos relacionados
- Detalles de resumen

Obtenga información sobre cómo usar la cola de alertas y las páginas de alertas en [investigar alertas](investigate-alerts.md).

## <a name="devices"></a>Dispositivos

La **pestaña Dispositivos** enumera todos los dispositivos relacionados con el incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Ejemplo de una página Dispositivos para un incidente":::

Puedes seleccionar la marca de verificación de un dispositivo para ver los detalles del dispositivo, los datos de directorio, las alertas activas y los usuarios que han iniciado sesión. Selecciona el nombre del dispositivo para ver los detalles del dispositivo en el inventario de dispositivos de Microsoft Defender para puntos de conexión.

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Ejemplo de una página de dispositivos para Microsoft Defender para puntos de conexión":::

Desde la página del dispositivo, puedes recopilar información adicional sobre el dispositivo, como todas sus alertas, una escala de tiempo y recomendaciones de seguridad. Por ejemplo,  desde la pestaña Escala de tiempo, puede desplazarse por la escala de tiempo de la máquina y ver todos los eventos y comportamientos observados en la máquina en orden cronológico, intercalados con las alertas generadas.

> [!TIP]
> Puedes realizar exámenes a petición en una página de dispositivo. En el centro Microsoft 365 seguridad, elija **Endpoints > Device inventory**. Selecciona un dispositivo que tenga alertas y, a continuación, ejecuta un examen antivirus. Las acciones, como los exámenes antivirus, se realiza un seguimiento y están visibles en la **página Inventario de** dispositivos. Para obtener más información, [consulte Run Antivirus de Microsoft Defender scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).

## <a name="users"></a>Usuarios

La **pestaña** Usuarios enumera todos los usuarios que se han identificado para formar parte o relacionados con el incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Ejemplo de una página Usuarios para un incidente":::

Puede seleccionar la marca de verificación de un usuario para ver los detalles de la amenaza, la exposición y la información de contacto de la cuenta de usuario. Seleccione el nombre de usuario para ver los detalles adicionales de la cuenta de usuario.

Obtenga información sobre cómo ver información de usuario adicional y administrar los usuarios de un incidente en [investigar usuarios](investigate-users.md).


## <a name="mailboxes"></a>Buzones

La **pestaña Buzones** enumera todos los buzones que se han identificado para formar parte o relacionados con el incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Ejemplo de una página Buzones de correo para un incidente":::

Puede seleccionar la marca de verificación de un buzón para ver una lista de alertas activas. Seleccione el nombre del buzón para ver detalles adicionales del buzón en la página Explorador de Microsoft Defender para Office 365.

## <a name="investigations"></a>Investigaciones

La **pestaña Investigaciones** enumera todas las [investigaciones automatizadas desencadenadas](m365d-autoir.md) por alertas en este incidente. Las investigaciones realizarán acciones de corrección o esperarán a que los analistas aprueben las acciones, según cómo haya configurado las investigaciones automatizadas para que se ejecuten en Microsoft Defender para Endpoint y Defender para Office 365.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Ejemplo de una página de investigaciones para un incidente":::

Seleccione una investigación para ir a la página de detalles de la investigación para obtener toda la información sobre la investigación y el estado de corrección. Si hay acciones pendientes para su aprobación como parte de la investigación, aparecerán en la pestaña Acciones pendientes. Tome medidas como parte de la corrección de incidentes.

Para obtener más información, vea [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).

## <a name="evidence-and-response"></a>Evidencia y respuesta

La **pestaña Evidencia y respuesta** muestra todos los eventos admitidos y las entidades sospechosas en las alertas del incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Ejemplo de una página de evidencia y respuesta para un incidente":::

Microsoft 365 Defender investiga automáticamente todos los eventos compatibles con incidentes y las entidades sospechosas de las alertas, lo que le proporciona información sobre los correos electrónicos, archivos, procesos, servicios, direcciones IP importantes y mucho más. Esto le ayuda a detectar y bloquear rápidamente posibles amenazas en el incidente.

Cada una de las entidades analizadas se marca con un veredicto (malintencionado, sospechoso, limpio) y un estado de corrección. Esto le ayuda a comprender el estado de corrección de todo el incidente y los siguientes pasos que se pueden seguir.

## <a name="graph-in-preview"></a>Graph (en versión preliminar)

Con la nueva **Graph** (en vista previa), puede ver:

- La conexión de alertas a los activos afectados de la organización.
- Qué entidades están relacionadas con qué alertas y cómo forman parte de la historia del ataque.
- Las alertas del incidente.

Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="Ejemplo de una página Graph para un incidente":::

El gráfico de incidentes le ayuda a comprender rápidamente el ámbito completo del ataque conectando las diferentes entidades sospechosas que forman parte del ataque con sus activos relacionados, como usuarios, dispositivos y buzones. 

Ahora puedes comprender cómo el ataque se extendió a través de la red con el tiempo, dónde se inició y hasta dónde llegó el ataque.

## <a name="next-steps"></a>Siguientes pasos

Según sea necesario:

- [Investigar las alertas de un incidente](investigate-alerts.md)
- [Investigar los usuarios de un incidente](investigate-users.md)

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Administrar incidentes](manage-incidents.md)

