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
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 262c68e517bb088af7ca3fa814a788c9303adf22
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58548695"
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

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Ejemplo de selección de un incidente en la columna de marca de verificación.":::

Cuando lo haga, se abrirá un panel de resumen con información clave sobre el incidente, como la gravedad, a quién está asignado, y el ATT de MITRE&categorías [de CK &trade; ](https://attack.mitre.org/) para el incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Ejemplo del panel de resumen de un incidente.":::

Desde aquí, puede seleccionar **Abrir página de incidentes**. Esto abre la página principal del incidente donde encontrará más información de resumen y pestañas para alertas, dispositivos, usuarios, investigaciones y pruebas.

También puede abrir la página principal de un incidente seleccionando el nombre del incidente en la cola de incidentes.

## <a name="summary"></a>Resumen

La **página Resumen le** ofrece una vista instantánea de los aspectos principales que debe tener en cuenta sobre el incidente.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Ejemplo de la página Resumen de un incidente en el portal Microsoft 365 Defender web":::

La información se organiza en estas secciones.

| Sección | Description |
|:-------|:-----|
| Alertas y categorías | Una vista visual y numérica de lo avanzado que ha progresado el ataque en la cadena de eliminación. Al igual que con otros productos de seguridad de Microsoft, Microsoft 365 Defender se alinea con el marco de&[CK &trade; de MITRE ATT.](https://attack.mitre.org/) La escala de tiempo de alertas muestra el orden cronológico en el que se produjeron las alertas y, para cada una, su estado y nombre. |
| Ámbito |  Muestra el número de dispositivos, usuarios y buzones afectados y enumera las entidades en orden de nivel de riesgo y prioridad de investigación. |
| Evidencia | Muestra el número de entidades afectadas por el incidente. |
| Información sobre incidentes | Muestra las propiedades del incidente, como las etiquetas, el estado y la gravedad. |
|||

Use la **página Resumen para** evaluar la importancia relativa del incidente y acceder rápidamente a las alertas asociadas y las entidades afectadas.

## <a name="alerts"></a>Alertas

En la **pestaña** Alertas, puede ver la cola de alertas de alertas relacionadas con el incidente y otra información sobre ellas, como:

- Gravedad.
- Las entidades que participaron en la alerta.
- El origen de las alertas (Microsoft Defender para identity, Microsoft Defender para endpoint, Microsoft Defender para Office 365).
- La razón por la que se vincularon.

Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Ejemplo de una página de alertas para un incidente.":::

De forma predeterminada, las alertas se ordenan cronológicamente para que pueda ver cómo se ha desarrollado el ataque con el tiempo. Al seleccionar una alerta dentro de un incidente, Microsoft 365 Defender muestra la información de alerta específica del contexto del incidente general. 

Puede ver los eventos de la alerta, qué otras alertas desencadenadas provocaron la alerta actual y todas las entidades y actividades afectadas implicadas en el ataque, incluidos dispositivos, archivos, usuarios y buzones.

Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Ejemplo de una página de detalles de alerta dentro de un incidente.":::

La página de alerta de incidentes tiene estas secciones:

- Artículo de alerta, que incluye:

   - Qué ha pasado

   - Acciones realizadas

   - Eventos relacionados

- Propiedades de alerta en el panel derecho (estado, detalles, descripción y otros)

No todas las alertas tendrán todas las subsecciones enumeradas en la **sección Artículo de** alerta.

Obtenga información sobre cómo usar la cola de alertas y las páginas de alertas en [investigar alertas](investigate-alerts.md).

## <a name="devices"></a>Dispositivos

La **pestaña Dispositivos** enumera todos los dispositivos relacionados con el incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Ejemplo de una página Dispositivos para un incidente.":::

Puedes seleccionar la marca de verificación de un dispositivo para ver los detalles del dispositivo, los datos de directorio, las alertas activas y los usuarios que han iniciado sesión. Selecciona el nombre del dispositivo para ver los detalles del dispositivo en el inventario de dispositivos de Microsoft Defender para puntos de conexión. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Ejemplo de una página de dispositivos para Microsoft Defender para puntos de conexión.":::

Desde la página del dispositivo, puedes recopilar información adicional sobre el dispositivo, como todas sus alertas, una escala de tiempo y recomendaciones de seguridad. Por ejemplo,  desde la pestaña Escala de tiempo, puede desplazarse por la escala de tiempo de la máquina y ver todos los eventos y comportamientos observados en la máquina en orden cronológico, intercalados con las alertas generadas.

> [!TIP]
> Puedes realizar exámenes a petición en una página de dispositivo. En el portal Microsoft 365 Defender, elija **Endpoints > Device inventory**. Selecciona un dispositivo que tenga alertas y, a continuación, ejecuta un examen antivirus. Las acciones, como los exámenes antivirus, se realiza un seguimiento y están visibles en la **página Inventario de** dispositivos. Para obtener más información, [consulte Run Antivirus de Microsoft Defender scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).

## <a name="users"></a>Usuarios

La **pestaña** Usuarios enumera todos los usuarios que se han identificado para formar parte o relacionados con el incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Ejemplo de una página Usuarios para un incidente.":::

Puede seleccionar la marca de verificación de un usuario para ver los detalles de la amenaza, la exposición y la información de contacto de la cuenta de usuario. Seleccione el nombre de usuario para ver los detalles adicionales de la cuenta de usuario.

Obtenga información sobre cómo ver información de usuario adicional y administrar los usuarios de un incidente en [investigar usuarios](investigate-users.md).


## <a name="mailboxes"></a>Buzones

La **pestaña Buzones** enumera todos los buzones que se han identificado para formar parte o relacionados con el incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Ejemplo de una página Buzones de correo para un incidente.":::

Puede seleccionar la marca de verificación de un buzón para ver una lista de alertas activas. Seleccione el nombre del buzón para ver detalles adicionales del buzón en la página Explorador de Microsoft Defender para Office 365.

## <a name="investigations"></a>Investigaciones

La **pestaña Investigaciones** enumera todas las [investigaciones automatizadas desencadenadas](m365d-autoir.md) por alertas en este incidente. Las investigaciones automatizadas realizarán acciones de corrección o esperarán a que los analistas aprueben las acciones, según cómo haya configurado las investigaciones automatizadas para que se ejecuten en Microsoft Defender para Endpoint y Defender para Office 365.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Ejemplo de una página de investigaciones para un incidente.":::

Seleccione una investigación para navegar a su página de detalles para obtener información completa sobre el estado de investigación y corrección. Si hay acciones pendientes para su aprobación como parte de la investigación, aparecerán en la **pestaña Historial de acciones pendientes.** Tome medidas como parte de la corrección de incidentes.

También hay una pestaña **Gráfico de investigación** que muestra:

- La conexión de alertas a los activos afectados de la organización.
- Qué entidades están relacionadas con qué alertas y cómo forman parte de la historia del ataque.
- Las alertas del incidente.

El gráfico de investigación le ayuda a comprender rápidamente el ámbito completo del ataque conectando las diferentes entidades sospechosas que forman parte del ataque con sus activos relacionados, como usuarios, dispositivos y buzones. 

Para obtener más información, vea [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).

## <a name="evidence-and-response"></a>Evidencia y respuesta

La **pestaña Evidencia y respuesta** muestra todos los eventos admitidos y las entidades sospechosas en las alertas del incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Ejemplo de una página de evidencia y respuesta para un incidente.":::

Microsoft 365 Defender investiga automáticamente todos los eventos compatibles con incidentes y las entidades sospechosas de las alertas, lo que le proporciona información sobre los correos electrónicos, archivos, procesos, servicios, direcciones IP importantes, etc. Esto le ayuda a detectar y bloquear rápidamente posibles amenazas en el incidente.

Cada una de las entidades analizadas se marca con un veredicto (malintencionado, sospechoso, limpio) y un estado de corrección. Esto le ayuda a comprender el estado de corrección de todo el incidente y los siguientes pasos que se pueden seguir.

## <a name="next-steps"></a>Pasos siguientes

Según sea necesario:

- [Investigar las alertas de un incidente](investigate-alerts.md)
- [Investigar los usuarios de un incidente](investigate-users.md)

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Administrar incidentes](manage-incidents.md)

