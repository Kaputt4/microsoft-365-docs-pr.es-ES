---
title: Respuesta a incidentes con Microsoft 365 Defender
description: Investigar incidentes vistos en dispositivos, usuarios y buzones en el portal de Microsoft 365 Defender web.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ac908a03aad2ccbe203877250a84185cb6c8da16
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2022
ms.locfileid: "62904378"
---
# <a name="incident-response-with-microsoft-365-defender"></a>Respuesta a incidentes con Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de laboratorio](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).
>

Un incidente en Microsoft 365 Defender es una colección de alertas correlacionadas y datos asociados que son la historia de un ataque. 

Los servicios y aplicaciones de Microsoft 365 crean alertas cuando detectan un evento o actividad sospechosos o malintencionados. Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso. Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones de entrada. El resultado son varias alertas para varias entidades del espacio empresarial. 

Dado que unir las alertas individuales para obtener información sobre un ataque puede ser un desafío y un consumo de tiempo, Microsoft 365 Defender agrega automáticamente las alertas y su información asociada a un incidente.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Cómo Microsoft 365 Defender los eventos de las entidades en un incidente." lightbox="../../media/incidents-overview/incidents.png":::

Vea esta breve introducción a los incidentes en Microsoft 365 Defender (4 minutos).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

La agrupación de alertas relacionadas en un incidente le ofrece una vista completa de un ataque. Por ejemplo, puede ver:

- Dónde se inició el ataque.
- Qué tácticas se usaron.
- Hasta dónde ha llegado el ataque a su cuenta empresarial.
- El ámbito del ataque, como el número de dispositivos, usuarios y buzones de entrada que se vieron afectados. 
- Todos los datos asociados al ataque.

Si [está](m365d-enable.md) habilitada, Microsoft 365 Defender investigar [y](m365d-autoir.md) resolver alertas automáticamente a través de la automatización y la inteligencia artificial. También puedes realizar pasos de corrección adicionales para resolver el ataque. 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>Incidentes y alertas en el portal Microsoft 365 Defender web

Puede administrar incidentes de incidentes **& alertas > incidentes en** el inicio rápido del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender web</a>. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="La página Incidentes del portal de Microsoft 365 Defender datos." lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

Al seleccionar un nombre de incidente, se muestra un resumen del incidente y se proporciona acceso a las pestañas con información adicional. He aquí un ejemplo.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Ejemplo de la página Resumen de un incidente en el portal Microsoft 365 Defender web" lightbox="../../media/incidents-overview/incidents-ss-incident-summary.png":::

Las pestañas adicionales para un incidente son:

- Alertas 

  Todas las alertas relacionadas con el incidente y su información.

- Dispositivos

  Todos los dispositivos que se han identificado para formar parte o relacionados con el incidente.

- Usuarios

  Todos los usuarios identificados para formar parte del incidente o relacionados con ellos.

- Buzones

  Todos los buzones que se han identificado para formar parte o relacionados con el incidente.

- Investigaciones

  Todas las [investigaciones automatizadas desencadenadas](m365d-autoir.md) por alertas en el incidente.

- Evidencia y respuesta

  Todos los eventos admitidos y las entidades sospechosas en las alertas del incidente.

- Graph (versión preliminar)

  Una representación visual del ataque que conecta las distintas entidades sospechosas que forman parte del ataque con sus activos relacionados, como usuarios, dispositivos y buzones.

Esta es la relación entre un incidente y sus datos y las pestañas de un incidente en Microsoft 365 Defender portal.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="La relación de un incidente y sus datos con las pestañas de un incidente en el portal Microsoft 365 Defender web." lightbox="../../media/incidents-overview/incidents-security-center.png":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Flujo de trabajo de respuesta a incidentes de ejemplo para Microsoft 365 Defender

Este es un flujo de trabajo de ejemplo para responder a incidentes en Microsoft 365 con el portal Microsoft 365 Defender web.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Ejemplo de flujo de trabajo de respuesta a incidentes para Microsoft 365." lightbox="../../media/incidents-overview/incidents-example-workflow.png":::

De forma continua, identifique los incidentes más prioritarios para su análisis y resolución en la cola de incidentes y prepárelos para su respuesta. Esta es una combinación de:

- [Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.
- [Administrar](manage-incidents.md) incidentes modificando su título, asignándolos a un analista y agregando etiquetas y comentarios.

Tenga en cuenta estos pasos para su propio flujo de trabajo de respuesta a incidentes:

1. Para cada incidente, inicie una investigación y análisis de ataques y [alertas](investigate-incidents.md):
 
   1. Vea el resumen del incidente para comprender su ámbito y gravedad y qué entidades se ven afectadas con las pestañas  Resumen y **Graph** (vista previa).

   1. Comience a analizar las alertas para comprender su origen, ámbito y gravedad con la **pestaña Alertas** .

   1. Según sea necesario, recopila información sobre dispositivos, usuarios y buzones afectados con las pestañas Dispositivos **, Usuarios** y **Buzones**.

   1. Vea cómo Microsoft 365 Defender [ha resuelto automáticamente algunas alertas](m365d-autoir.md) con la **pestaña** Investigaciones.
   
   1. Según sea necesario, use la información del conjunto de datos para el incidente para obtener más información con la **pestaña Evidencia y** respuesta.

2. Después o durante el análisis, realice la contención para reducir cualquier impacto adicional del ataque y la detención de la amenaza de seguridad.

3. En la medida de lo posible, recupérese del ataque restaurando los recursos de sus cuentas empresariales al estado en que se encontraban antes del incidente.

4. [Resuelva](manage-incidents.md#resolve-an-incident) el incidente y tome tiempo para aprender después del incidente a:

   - Comprender el tipo de ataque y su impacto.
   - Investigue el ataque en [Análisis de amenazas](threat-analytics.md) y la comunidad de seguridad para obtener una tendencia de ataque de seguridad.
   - Recordar el flujo de trabajo que se utilizó para resolver el incidente y actualizar los flujos de trabajo estándar, los procesos, las directivas y los libros de instrucciones según sea necesario.
   - Determinar si son necesarios cambios en la configuración de seguridad e implementarlos.

Si es nuevo en el análisis de seguridad, vea [](incidents-overview.md) la introducción para responder al primer incidente para obtener información adicional y para pasar por un incidente de ejemplo.

Para obtener más información acerca de la respuesta a incidentes en todos los productos de Microsoft, vea [este artículo](/security/compass/incident-response-overview).

## <a name="example-security-operations-for-microsoft-365-defender"></a>Operaciones de seguridad de ejemplo para Microsoft 365 Defender

Este es un ejemplo de operaciones de seguridad (SecOps) para Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Un ejemplo de operaciones de seguridad para Microsoft 365 Defender." lightbox="../../media/incidents-overview/incidents-example-operations.png":::

Las tareas diarias pueden incluir:

- [Administración](manage-incidents.md) de incidentes
- Revisión [de acciones de investigación y respuesta automatizadas (AIR)](m365d-action-center.md) en el Centro de acciones
- Revisión de los análisis [de amenazas más recientes](threat-analytics.md)
- [Responder a](investigate-incidents.md) incidentes

Las tareas mensuales pueden incluir:

- Revisión de [la configuración de AIR](m365d-configure-auto-investigation-response.md)
- Revisión [de la puntuación segura](microsoft-secure-score-improvement-actions.md) [y la administración & vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Informes en la cadena de administración de seguridad de IT

Las tareas trimestrales pueden incluir un informe y un informe de los resultados de seguridad al director de seguridad de la información (CISO).

Las tareas anuales pueden incluir llevar a cabo un ejercicio importante de incidentes o infracciones para probar el personal, los sistemas y los procesos. 

Las tareas diarias, mensuales, trimestrales y anuales se pueden usar para actualizar o refinar procesos, directivas y configuraciones de seguridad.

Consulte [ Integración de Microsoft 365 Defender en las operaciones de seguridad](integrate-microsoft-365-defender-secops.md) para obtener más información.

### <a name="secops-resources-across-microsoft-products"></a>Recursos de SecOps en productos de Microsoft

Para obtener más información acerca de SecOps en todos los productos de Microsoft, vea estos recursos:

- [Capabilities](/security/compass/security-operations-capabilities)
- [Procedimientos recomendados](/security/compass/security-operations)
- [Vídeos y diapositivas](/security/compass/security-operations-videos-and-decks)


## <a name="get-incident-notifications-by-email"></a>Obtener notificaciones de incidentes por correo electrónico

Puede configurar Microsoft 365 Defender para notificar a su personal con un correo electrónico sobre nuevos incidentes o actualizaciones de incidentes existentes. Puede elegir obtener notificaciones en función de:

- Gravedad del incidente.
- Grupo de dispositivos.
- Solo en la primera actualización por incidente.

La notificación por correo electrónico contiene detalles importantes sobre el incidente, como el nombre del incidente, la gravedad y las categorías, entre otras. También puede ir directamente al incidente e iniciar el análisis de inmediato. Para obtener más información, vea [Investigar incidentes](investigate-incidents.md).

Puede agregar o quitar destinatarios en las notificaciones de correo electrónico. Los nuevos destinatarios reciben notificaciones sobre incidentes después de agregarse. 

>[!NOTE]
>Necesita el permiso **Administrar la configuración de seguridad** para configurar las opciones de notificación de correo electrónico. Si ha elegido usar la administración de permisos básicos, los usuarios con roles de administrador de seguridad o administrador global pueden configurar las notificaciones de correo electrónico. <br> <br>
Del mismo modo, si tu organización usa el control de acceso basado en roles (RBAC), solo puedes crear, editar, eliminar y recibir notificaciones en función de los grupos de dispositivos que puedas administrar.

### <a name="create-a-rule-for-email-notifications"></a>Crear una regla para notificaciones por correo electrónico

Siga estos pasos para crear una nueva regla y personalizar la configuración de notificaciones por correo electrónico.

1. En el panel de navegación, **seleccione Configuración > Microsoft 365 Defender > notificaciones de correo electrónico de incidentes**.
2. Seleccione **Agregar elemento**.
3. En la **página Conceptos básicos** , escriba el nombre de la regla y una descripción y, a continuación, **seleccione Siguiente**.
4. En la **página Configuración de** notificaciones, configure:
    - **Gravedad de alerta**: elija los niveles de gravedad de alerta que desencadenarán una notificación de incidente. Por ejemplo, si solo desea que se le informe sobre incidentes de alta gravedad, seleccione **Alto**.
    - **Ámbito del grupo de dispositivos**: puede especificar todos los grupos de dispositivos o seleccionarlos en la lista de grupos de dispositivos del inquilino.
    - **Notificar solo la primera aparición por incidente**: seleccione si desea una notificación solo en la primera alerta que coincida con las demás selecciones. Las actualizaciones o alertas posteriores relacionadas con el incidente no enviarán notificaciones adicionales.
    - **Incluir el nombre de la organización en el correo electrónico**: seleccione si desea que el nombre de la organización aparezca en la notificación por correo electrónico.
    - **Incluir vínculo del portal específico del inquilino**: seleccione si desea agregar un vínculo con el identificador de inquilino en la notificación de correo electrónico para acceder a un inquilino de Microsoft 365 específico.

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Configuración de notificaciones para notificaciones de correo electrónico de incidentes." lightbox="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png":::

5. Seleccione **Siguiente**. En la **página Destinatarios** , agregue las direcciones de correo electrónico que recibirán las notificaciones de incidentes. Seleccione **Agregar después** de escribir cada nueva dirección de correo electrónico. Para probar las notificaciones y asegurarse de que los destinatarios las reciben en las bandejas de entrada, seleccione **Enviar correo electrónico de prueba**. 
6. Seleccione **Siguiente**. En la **página Revisar regla** , revise la configuración de la regla y, a continuación, seleccione **Crear regla**. Los destinatarios empezarán a recibir notificaciones de incidentes a través del correo electrónico en función de la configuración.

Para editar una regla existente, selecciónelo en la lista de reglas. En el panel con el nombre de regla, seleccione **Editar** regla y realice los cambios en las páginas **Conceptos** **básicos, Configuración** de notificación y **Destinatarios** .

Para eliminar una regla, selecciónelo en la lista de reglas. En el panel con el nombre de regla, seleccione **Eliminar**.


## <a name="training-for-security-analysts"></a>Aprendizaje para analistas de seguridad

Use este módulo de aprendizaje de Microsoft Learn para comprender cómo usar Microsoft 365 Defender para administrar incidentes y alertas.

|Aprendizaje:|Investigar incidentes con Microsoft 365 Defender|
|---|---|
|![Investigar incidentes con Microsoft 365 Defender de aprendizaje.](../../media/incidents-overview/m365-defender-address-security-investigation.svg)| Microsoft 365 Defender unifica los datos de amenazas de varios servicios y usa la inteligencia artificial para combinarlos en incidentes y alertas. Obtenga información sobre cómo minimizar el tiempo entre un incidente y su administración mediante respuesta y resolución posteriores. <p> 27 min - 6 unidades |

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/defender-investigate-incidents/)

## <a name="next-steps"></a>Siguientes pasos

Use los pasos enumerados en función del nivel de experiencia o el rol del equipo de seguridad.

### <a name="experience-level"></a>Nivel de experiencia

Siga esta tabla para obtener su nivel de experiencia con el análisis de seguridad y la respuesta a incidentes.

| Nivel | Pasos |
|:-------|:-----|
| **New** | <ol><li> Consulte [el tutorial](first-incident-overview.md) Responder al primer incidente para obtener una visita guiada a un proceso típico de análisis, corrección y revisión posterior al incidente en el portal de Microsoft 365 Defender con un ataque de ejemplo. </li><li> Vea qué incidentes deben [priorizarse en](incident-queue.md) función de la gravedad y otros factores. </li><li> [Administrar incidentes, que](manage-incidents.md) incluye cambiar el nombre, asignar, clasificar y agregar etiquetas y comentarios en función del flujo de trabajo de administración de incidentes.</li></ol> |
| **Experimentado** | <ol><li> Introducción a la cola de incidentes desde **la página Incidentes** del portal Microsoft 365 Defender incidentes. Desde allí, puedes hacer lo siguiente: </li> <ul><li> Vea qué incidentes deben [priorizarse en](incident-queue.md) función de la gravedad y otros factores. </li><li> [Administrar incidentes, que](manage-incidents.md) incluye cambiar el nombre, asignar, clasificar y agregar etiquetas y comentarios en función del flujo de trabajo de administración de incidentes. </li><li> Realizar [investigaciones](investigate-incidents.md) de incidentes. </li></ul> </li><li> Realice un seguimiento y responda a las amenazas emergentes con [análisis de amenazas](threat-analytics.md). </li><li>  Búsqueda proactiva de amenazas con búsqueda [avanzada de amenazas](advanced-hunting-overview.md). </li><li> Consulta estos [libros de reproducción de respuesta a](/security/compass/incident-response-playbooks) incidentes para obtener instrucciones detalladas sobre los ataques de suplantación de identidad (phishing), el uso de contraseñas y la concesión de consentimiento de la aplicación. </li></ol> |


### <a name="security-team-role"></a>Rol de equipo de seguridad

Siga esta tabla en función del rol de equipo de seguridad.

| Rol | Pasos |
|:-------|:-----|
| Respondedor de incidentes (nivel 1) | Introducción a la cola de incidentes desde **la página Incidentes** del portal Microsoft 365 Defender incidentes. Desde allí, puedes hacer lo siguiente: <ul><li> Vea qué incidentes deben [priorizarse en](incident-queue.md) función de la gravedad y otros factores. </li><li> [Administrar incidentes, que](manage-incidents.md) incluye cambiar el nombre, asignar, clasificar y agregar etiquetas y comentarios en función del flujo de trabajo de administración de incidentes. </li></ul> |
| Investigador o analista de seguridad (nivel 2) | <ol><li> Realice [investigaciones de](investigate-incidents.md) incidentes desde la **página Incidentes** del portal Microsoft 365 Defender web. </li><li> Consulta estos [libros de reproducción de respuesta a](/security/compass/incident-response-playbooks) incidentes para obtener instrucciones detalladas sobre los ataques de suplantación de identidad (phishing), el uso de contraseñas y la concesión de consentimiento de la aplicación. </li></ol> |
| Analista de seguridad avanzado o cazador de amenazas (nivel 3) | <ol><li>Realice [investigaciones de](investigate-incidents.md) incidentes desde la **página Incidentes** del portal Microsoft 365 Defender web. </li><li> Realice un seguimiento y responda a las amenazas emergentes con [análisis de amenazas](threat-analytics.md). </li><li> Búsqueda proactiva de amenazas con búsqueda [avanzada de amenazas](advanced-hunting-overview.md). </li><li> Consulta estos [libros de reproducción de respuesta a](/security/compass/incident-response-playbooks) incidentes para obtener instrucciones detalladas sobre los ataques de suplantación de identidad (phishing), el uso de contraseñas y la concesión de consentimiento de la aplicación. |
| Administrador de SOC | Vea cómo [integrar Microsoft 365 Defender en el Centro de operaciones de seguridad (SOC).](integrate-microsoft-365-defender-secops.md). |

