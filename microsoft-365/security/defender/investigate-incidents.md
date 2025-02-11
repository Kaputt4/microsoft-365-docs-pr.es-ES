---
title: Investigar incidentes con Microsoft 365 Defender
description: Investigue los incidentes relacionados con dispositivos, usuarios y buzones.
keywords: incident, incidents, attack story, analyze, response, machines, devices, users, identities, mail, email, mailbox, investigation, graph, evidence
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 41006d8c68eef16d09bc872ca3d8fc471812cb1c
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687724"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Investigar incidentes con Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

Microsoft 365 Defender agrega todas las alertas, recursos, investigaciones y pruebas relacionadas de todos los dispositivos, usuarios y buzones de correo en un incidente para darle una visión completa de toda la amplitud de un ataque.

Dentro de un incidente, se analizan las alertas que afectan a la red, se entiende lo que significan y se intercalan las pruebas para que pueda diseñar un plan de corrección eficaz.

## <a name="initial-investigation"></a>Investigación inicial

Antes de profundizar en los detalles, eche un vistazo a las propiedades y a toda la historia de ataque del incidente.

Para empezar, seleccione el incidente en la columna de marca de verificación. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Selección de un incidente en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-incidents/incidents-ss-incident-select.png":::

Cuando lo hace, se abre un panel de resumen con información clave sobre el incidente, como la gravedad, a quién se asigna y las categorías [MITRE ATT&CK&trade;](https://attack.mitre.org/) para el incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Panel que muestra los detalles de resumen de un incidente en el portal de Microsoft 365 Defender." lightbox="../../media/investigate-incidents/incidents-ss-incident-side-panel.png":::

Desde aquí, puede seleccionar **Abrir página de incidente**. Se abre la página principal del incidente, donde encontrará la información completa del caso de ataque y las pestañas de alertas, dispositivos, usuarios, investigaciones y pruebas.

También puede abrir la página principal de un incidente seleccionando el nombre del incidente de la cola de incidentes.

## <a name="attack-story"></a>Historia de ataque

Los casos de ataque le ayudan a revisar, investigar y corregir ataques rápidamente mientras ven la historia completa del ataque en la misma pestaña. También permite revisar los detalles de la entidad y realizar acciones de corrección, como eliminar un archivo o aislar un dispositivo sin perder contexto.

:::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="La historia de ataque de un incidente" lightbox="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png":::

En el caso de ataque, puede encontrar la página de alertas y el gráfico de incidentes.

La página de alertas de incidente tiene estas secciones:

- Historia de alertas, que incluye:

   - Qué ha pasado

   - Acciones realizadas

   - Eventos relacionados

- Propiedades de alerta en el panel derecho (estado, detalles, descripción y otros)

Tenga en cuenta que no todas las alertas tendrán todas las subsecciones enumeradas en la sección **Artículo de alerta** .

El gráfico muestra el ámbito completo del ataque, cómo se extendió a través de la red a lo largo del tiempo, dónde se inició y hasta dónde llegó el atacante. Conecta las distintas entidades sospechosas que forman parte del ataque con sus recursos relacionados, como usuarios, dispositivos y buzones.

En el gráfico, puede hacer lo siguiente:

- Reproduzca las alertas y los nodos del gráfico a medida que se produjeron con el tiempo para comprender la cronología del ataque.
  
  :::image type="content" source="../../media/investigate-incidents/play-alert-attack-story.gif" alt-text="Captura de pantalla que muestra la reproducción de las alertas y los nodos en la página del gráfico del caso de ataque.":::

- Abra un panel de entidades, lo que le permite revisar los detalles de la entidad y actuar sobre las acciones de corrección, como eliminar un archivo o aislar un dispositivo.

  :::image type="content" source="../../media/investigate-incidents/review-entity-details-attack-story.gif" alt-text="Captura de pantalla que muestra la revisión de los detalles de la entidad en la página del gráfico de historia de ataques.":::

- Resalte las alertas basadas en la entidad a la que están relacionadas.

Use la página **Resumen** para evaluar la importancia relativa del incidente y acceder rápidamente a las alertas asociadas y las entidades afectadas.

## <a name="summary"></a>Resumen

La página **Resumen** le ofrece un vistazo de instantáneas a los elementos principales para observar el incidente.

:::image type="content" source="../../media/incidents-overview/incidents-investigate-summary.png" alt-text="Captura de pantalla que muestra la información de resumen de un incidente en el portal de Microsoft 365 Defender." lightbox="../../media/incidents-overview/incidents-investigate-summary.png":::

La información se organiza en estas secciones.

| Sección | Descripción |
|:-------|:-----|
| Alertas y categorías | Una vista visual y numérica de cómo ha progresado el ataque en la cadena de eliminación. Al igual que con otros productos de seguridad de Microsoft, Microsoft 365 Defender está alineado con el marco [de TRABAJO de MITRE ATT&CK&trade;](https://attack.mitre.org/). La escala de tiempo de alertas muestra el orden cronológico en el que se produjeron las alertas y, para cada una, su estado y su nombre. |
| Ámbito |  Muestra el número de dispositivos, usuarios y buzones afectados y enumera las entidades en orden de nivel de riesgo y prioridad de investigación. |
| Evidencia | Muestra el número de entidades afectadas por el incidente. |
| Información sobre incidentes | Muestra las propiedades del incidente, como etiquetas, estado y gravedad. |
|||

## <a name="alerts"></a>Alertas

En la pestaña **Alertas** , puede ver la cola de alertas para las alertas relacionadas con el incidente y otra información sobre ellas, como:

- Severidad.
- Entidades implicadas en la alerta.
- Origen de las alertas (Microsoft Defender for Identity, Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Defender for Cloud Apps y el complemento de gobernanza de aplicaciones).
- La razón por la que se vincularon.

Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Panel Alertas de un incidente en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-incidents/incident-alerts.png":::

De forma predeterminada, las alertas se ordenan cronológicamente para que pueda ver cómo se ha realizado el ataque a lo largo del tiempo. Al seleccionar una alerta dentro de un incidente, Microsoft 365 Defender muestra la información de alerta específica del contexto del incidente general. 

Puede ver los eventos de la alerta, que otras alertas desencadenadas provocaron la alerta actual, y todas las entidades y actividades afectadas implicadas en el ataque, incluidos dispositivos, archivos, usuarios y buzones.

Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Detalles de una alerta dentro de un incidente en el portal de Microsoft 365 Defender." lightbox="../../media/investigate-incidents/incident-alert-example.png":::

Obtenga información sobre cómo usar la cola de alertas y las páginas de alertas en [la investigación de alertas](investigate-alerts.md).

## <a name="devices"></a>Dispositivos

En la pestaña **Dispositivos** se enumeran todos los dispositivos relacionados con el incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Página Dispositivos de un incidente en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-incidents/incident-devices.png":::

Puede seleccionar la marca de verificación de un dispositivo para ver los detalles del dispositivo, los datos de directorio, las alertas activas y los usuarios que han iniciado sesión. Seleccione el nombre del dispositivo para ver los detalles del dispositivo en el inventario de dispositivos de Defender para punto de conexión. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Página relacionada con la opción Inventario de dispositivos en el Microsoft Defender para punto de conexión." lightbox="../../media/investigate-incidents/incident-devices-details.png":::

En la página del dispositivo, puede recopilar información adicional sobre el dispositivo, como todas sus alertas, una escala de tiempo y recomendaciones de seguridad. Por ejemplo, desde la pestaña **Escala de tiempo** , puede desplazarse por la escala de tiempo de la máquina y ver todos los eventos y comportamientos observados en la máquina en orden cronológico, intercalados con las alertas desencadenadas.

> [!TIP]
> Puede realizar exámenes a petición en una página del dispositivo. En el portal de Microsoft 365 Defender, elija Puntos de **conexión > inventario de dispositivos**. Seleccione un dispositivo que tenga alertas y, a continuación, ejecute un examen antivirus. Se realiza un seguimiento de las acciones, como los exámenes antivirus, y se muestran en la página **Inventario de** dispositivos. Para más información, consulte [Run Microsoft Defender Antivirus scan on devices (Ejecución Microsoft Defender examen del antivirus en dispositivos](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)).

## <a name="users"></a>Usuarios

En la pestaña **Usuarios** se enumeran todos los usuarios que se han identificado para formar parte del incidente o estar relacionados con él. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="La página Usuarios del portal de Microsoft 365 Defender." lightbox="../../media/investigate-incidents/incident-users.png":::

Puede seleccionar la marca de verificación de un usuario para ver los detalles de la amenaza, la exposición y la información de contacto de la cuenta de usuario. Seleccione el nombre de usuario para ver detalles adicionales de la cuenta de usuario.

Obtenga información sobre cómo ver información adicional del usuario y administrar los usuarios de un incidente en [la investigación de usuarios](investigate-users.md).

## <a name="mailboxes"></a>Buzones

En la pestaña **Buzones** se enumeran todos los buzones que se han identificado para formar parte del incidente o estar relacionados con él. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Página Buzones de correo de un incidente en el portal de Microsoft 365 Defender." lightbox="../../media/investigate-incidents/incident-mailboxes.png":::

Puede seleccionar la marca de verificación de un buzón para ver una lista de alertas activas. Seleccione el nombre del buzón para ver detalles adicionales del buzón en la página Explorador de Defender para Office 365.

## <a name="investigations"></a>Investigaciones

En la pestaña **Investigaciones** se enumeran todas las [investigaciones automatizadas desencadenadas por las alertas](m365d-autoir.md) de este incidente. Las investigaciones automatizadas realizarán acciones de corrección o esperarán la aprobación por parte del analista de las acciones, en función de cómo haya configurado las investigaciones automatizadas para que se ejecuten en Defender para punto de conexión y Defender para Office 365.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Página Investigaciones de un incidente en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-incidents/incident-investigations.png":::

Seleccione una investigación para ir a su página de detalles para obtener información completa sobre el estado de investigación y corrección. Si hay acciones pendientes de aprobación como parte de la investigación, aparecerán en la pestaña Historial de **acciones pendientes** . Tome medidas como parte de la corrección de incidentes.

También hay una pestaña **Grafo de investigación** que muestra:

- Conexión de alertas a los recursos afectados en su organización.
- Qué entidades están relacionadas con qué alertas y cómo forman parte de la historia del ataque.
- Alertas del incidente.

El gráfico de investigación le ayuda a comprender rápidamente el ámbito completo del ataque conectando las distintas entidades sospechosas que forman parte del ataque con sus recursos relacionados, como usuarios, dispositivos y buzones de correo. 

Para obtener más información, consulte [Investigación y respuesta automatizadas en Microsoft 365 Defender](m365d-autoir.md).

## <a name="evidence-and-response"></a>Evidencia y respuesta

La pestaña **Evidencia y respuesta** muestra todos los eventos admitidos y entidades sospechosas en las alertas del incidente. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Página Evidencia y respuesta de un incidente en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-incidents/incident-evidence.png":::

Microsoft 365 Defender investiga automáticamente todos los eventos admitidos por los incidentes y las entidades sospechosas de las alertas, proporcionándole información sobre los correos electrónicos, archivos, procesos, servicios, direcciones IP importantes, etc. Esto le ayuda a detectar y bloquear rápidamente posibles amenazas en el incidente.

Cada una de las entidades analizadas se marca con un veredicto (Malintencionado, Sospechoso, Limpio) y un estado de corrección. Esto le ayuda a comprender el estado de corrección de todo el incidente y qué pasos siguientes se pueden realizar.

## <a name="next-steps"></a>Pasos siguientes

Según sea necesario:

- [Investigación de las alertas de un incidente](investigate-alerts.md)
- [Investigación de los usuarios de un incidente](investigate-users.md)

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Administrar incidentes](manage-incidents.md)
