---
title: Respuesta a incidentes con Microsoft 365 Defender
description: Investigue los incidentes detectados entre dispositivos, usuarios y buzones en el portal de Microsoft 365 Defender.
keywords: incidentes, alertas, investigar, analizar, responder, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: d283876f8e68943d45ab2dbca4ef8455a5dce038
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66949067"
---
# <a name="incident-response-with-microsoft-365-defender"></a>Respuesta a incidentes con Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Un incidente en Microsoft 365 Defender es una colección de alertas correlacionadas y datos asociados que conforman la historia de un ataque.

Los servicios y aplicaciones de Microsoft 365 crean alertas cuando detectan un evento o actividad sospechosos o malintencionados. Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso. Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones de entrada. El resultado son varias alertas para varias entidades del espacio empresarial.

Dado que unir las alertas individuales para obtener información sobre un ataque puede ser un desafío y un consumo de tiempo, Microsoft 365 Defender agrega automáticamente las alertas y su información asociada a un incidente.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Cómo Microsoft 365 Defender correlaciona eventos de entidades en un incidente." lightbox="../../media/incidents-overview/incidents.png":::

Vea esta breve introducción a los incidentes en Microsoft 365 Defender (4 minutos).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

La agrupación de alertas relacionadas en un incidente le ofrece una vista completa de un ataque. Por ejemplo, puede ver:

- Dónde se inició el ataque.
- Qué tácticas se usaron.
- Hasta dónde ha llegado el ataque a su cuenta empresarial.
- El ámbito del ataque, como el número de dispositivos, usuarios y buzones de entrada que se vieron afectados.
- Todos los datos asociados al ataque.

Si [está habilitado](m365d-enable.md), Microsoft 365 Defender puede [investigar y resolver automáticamente](m365d-autoir.md) las alertas a través de la automatización y la inteligencia artificial. También puede realizar pasos de corrección adicionales para resolver el ataque.

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>Incidentes y alertas en el portal de Microsoft 365 Defender

Los incidentes se administran a partir de **alertas de incidentes & > incidentes** en el inicio rápido del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Página Incidentes del portal de Microsoft 365 Defender." lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

Al seleccionar un nombre de incidente se muestra un resumen del incidente y se proporciona acceso a las pestañas con información adicional. Por ejemplo:

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Página Resumen de un incidente en el portal de Microsoft 365 Defender" lightbox="../../media/incidents-overview/incidents-ss-incident-summary.png":::

Las pestañas adicionales para un incidente son:

- Alertas

  Todas las alertas relacionadas con el incidente y su información.

- Dispositivos

  Todos los dispositivos que se han identificado para formar parte o estar relacionados con el incidente.

- Usuarios

  Todos los usuarios que se han identificado para formar parte o estar relacionados con el incidente.

- Buzones

  Todos los buzones que se han identificado para formar parte del incidente o estar relacionados con él.

- Investigaciones

  Todas las [investigaciones automatizadas desencadenadas por alertas](m365d-autoir.md) en el incidente.

- Evidencia y respuesta

  Todos los eventos admitidos y las entidades sospechosas de las alertas del incidente.

- Graph (versión preliminar)

  Representación visual del ataque que conecta las distintas entidades sospechosas que forman parte del ataque con sus recursos relacionados, como usuarios, dispositivos y buzones de correo.

Esta es la relación entre un incidente y sus datos y las pestañas de un incidente en el portal de Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Relación de un incidente y sus datos con las pestañas de un incidente en el portal de Microsoft 365 Defender." lightbox="../../media/incidents-overview/incidents-security-center.png":::

> [!NOTE]
> Si ve un estado de *alerta de tipo de alerta no compatible* , significa que las funcionalidades de investigación automatizada no pueden recoger esa alerta para ejecutar una investigación automatizada. Sin embargo, puede [investigar estas alertas manualmente](investigate-incidents.md#alerts).

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Flujo de trabajo de respuesta a incidentes de ejemplo para Microsoft 365 Defender

Este es un flujo de trabajo de ejemplo para responder a incidentes en Microsoft 365 con el portal de Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Ejemplo de un flujo de trabajo de respuesta a incidentes para el portal de Microsoft 365 Defender." lightbox="../../media/incidents-overview/incidents-example-workflow.png":::

De forma continua, identifique los incidentes más prioritarios para su análisis y resolución en la cola de incidentes y prepárelos para su respuesta. Esta es una combinación de:

- [Evaluar](incident-queue.md) para determinar los incidentes de mayor prioridad mediante el filtrado y la ordenación de la cola de incidentes.
- [Administrar](manage-incidents.md) incidentes modificando su título, asignándolos a un analista y agregando etiquetas y comentarios.

Tenga en cuenta estos pasos para su propio flujo de trabajo de respuesta a incidentes:

1. Para cada incidente, comience una [investigación y análisis de ataques y alertas](investigate-incidents.md):

   1. Vea el resumen del incidente para comprender su ámbito y gravedad y qué entidades se ven afectadas con las pestañas **Resumen** y **Gráfico** (versión preliminar).

   1. Comience a analizar las alertas para comprender su origen, ámbito y gravedad con la pestaña **Alertas** .

   1. Según sea necesario, recopile información sobre dispositivos, usuarios y buzones afectados con las pestañas **Dispositivos**, **Usuarios** y **Buzones** .

   1. Vea cómo Microsoft 365 Defender ha [resuelto automáticamente algunas alertas](m365d-autoir.md) con la pestaña **Investigaciones**.

   1. Según sea necesario, use información en el conjunto de datos del incidente para obtener más información con la pestaña **Evidencia y respuesta** .

2. Después o durante el análisis, realice la contención para reducir cualquier impacto adicional del ataque y la detención de la amenaza de seguridad.

3. En la medida de lo posible, recupérese del ataque restaurando los recursos de sus cuentas empresariales al estado en que se encontraban antes del incidente.

4. [Resuelva](manage-incidents.md#resolve-an-incident) el incidente y tómese tiempo para el aprendizaje posterior al incidente para:

   - Comprender el tipo de ataque y su impacto.
   - Investigue el ataque en [Threat Analytics](threat-analytics.md) y la comunidad de seguridad para detectar una tendencia de ataque de seguridad.
   - Recordar el flujo de trabajo que se utilizó para resolver el incidente y actualizar los flujos de trabajo estándar, los procesos, las directivas y los libros de instrucciones según sea necesario.
   - Determinar si son necesarios cambios en la configuración de seguridad e implementarlos.

Si no está familiarizado con el análisis de seguridad, consulte la [introducción a la respuesta al primer incidente](incidents-overview.md) para obtener información adicional y para recorrer un incidente de ejemplo.

Para obtener más información sobre la respuesta a incidentes en los productos de Microsoft, consulte [este artículo](/security/compass/incident-response-overview).

## <a name="example-security-operations-for-microsoft-365-defender"></a>Operaciones de seguridad de ejemplo para Microsoft 365 Defender

Este es un ejemplo de operaciones de seguridad (SecOps) para Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Un ejemplo de operaciones de seguridad para Microsoft 365 Defender" lightbox="../../media/incidents-overview/incidents-example-operations.png":::

Las tareas diarias pueden incluir:

- [Administración de](manage-incidents.md) incidentes
- Revisión de las acciones [de investigación y respuesta automatizadas (AIR)](m365d-action-center.md) en el Centro de acción
- Revisión de la versión más reciente de [Threat Analytics](threat-analytics.md)
- [Respuesta a](investigate-incidents.md) incidentes

Las tareas mensuales pueden incluir:

- Revisión de la [configuración de AIR](m365d-configure-auto-investigation-response.md)
- Revisión de [la puntuación de seguridad](microsoft-secure-score-improvement-actions.md) y [la administración de vulnerabilidades de & amenazas](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Informes a la cadena de administración de seguridad de TI

Las tareas trimestrales pueden incluir un informe y un informe de los resultados de seguridad al director de seguridad de la información (CISO).

Las tareas anuales pueden incluir la realización de un ejercicio importante de incidentes o infracciones para probar el personal, los sistemas y los procesos.

Las tareas diarias, mensuales, trimestrales y anuales se pueden usar para actualizar o refinar procesos, directivas y configuraciones de seguridad.

Consulte [Integración de Microsoft 365 Defender en las operaciones de seguridad](integrate-microsoft-365-defender-secops.md) para obtener más información.

### <a name="secops-resources-across-microsoft-products"></a>Recursos de SecOps en todos los productos de Microsoft

Para obtener más información sobre SecOps en los productos de Microsoft, consulte estos recursos:

- [Capabilities](/security/compass/security-operations-capabilities)
- [Procedimientos recomendados](/security/compass/security-operations)
- [Vídeos y diapositivas](/security/compass/security-operations-videos-and-decks)

## <a name="get-incident-notifications-by-email"></a>Obtención de notificaciones de incidentes por correo electrónico

Puede configurar Microsoft 365 Defender para notificar a su personal un correo electrónico sobre nuevos incidentes o actualizaciones de incidentes existentes. Puede elegir obtener notificaciones basadas en:

- Gravedad de la alerta
- Orígenes de alerta 
- Grupo de dispositivos

**Elija recibir notificaciones por correo electrónico solo para un origen de servicio específico**: puede seleccionar fácilmente orígenes de servicio específicos para los que desea obtener notificaciones por correo electrónico.
 
**Obtener más granularidad con orígenes de detección específicos**: solo puede obtener notificaciones para un origen de detección específico. 

**Establecer la gravedad por detección o origen de servicio**: puede elegir obtener notificaciones por correo electrónico solo en gravedades específicas por origen. Por ejemplo, puede recibir notificaciones de alertas medias y altas para EDR y todas las gravedades de los expertos de Microsoft Defender.  

La notificación por correo electrónico contiene detalles importantes sobre el incidente, como el nombre del incidente, la gravedad y las categorías, entre otros. También puede ir directamente al incidente e iniciar el análisis de inmediato. Para obtener más información, consulte [Investigación de incidentes](investigate-incidents.md).

Puede agregar o quitar destinatarios en las notificaciones por correo electrónico. Los nuevos destinatarios reciben notificaciones sobre incidentes después de agregarse.

> [!NOTE]
> Necesita el permiso **Administrar configuración de seguridad** para configurar las opciones de notificación por correo electrónico. Si ha elegido usar la administración básica de permisos, los usuarios con roles administrador de seguridad o administrador global pueden configurar las notificaciones por correo electrónico. <br> <br>
Del mismo modo, si su organización usa el control de acceso basado en rol (RBAC), solo puede crear, editar, eliminar y recibir notificaciones basadas en grupos de dispositivos que pueda administrar.

### <a name="create-a-rule-for-email-notifications"></a>Creación de una regla para notificaciones por correo electrónico

Siga estos pasos para crear una nueva regla y personalizar la configuración de notificaciones por correo electrónico.

1. Vaya a [Microsoft 365 Defender](https://security.microsoft.com) en el panel de navegación y seleccione **Configuración > Microsoft 365 Defender > notificaciones por correo electrónico de incidentes**.
2. Seleccione **Agregar elemento**.
3. En la página **Aspectos básicos** , escriba el nombre de la regla y una descripción y, a continuación, seleccione **Siguiente**.
4. En la página **Configuración de notificación** , configure:
    - **Gravedad de alerta**: elija los niveles de gravedad de alerta que desencadenarán una notificación de incidente. Por ejemplo, si solo desea que se le informe sobre incidentes de gravedad alta, seleccione **Alto**.
    - **Ámbito del grupo de dispositivos**: puede especificar todos los grupos de dispositivos o seleccionarlos en la lista de grupos de dispositivos del inquilino.
    - **Enviar solo una notificación por incidente** : seleccione si desea una notificación por incidente.
    - **Incluir el nombre de la organización en el correo electrónico**: seleccione si desea que el nombre de la organización aparezca en la notificación por correo electrónico.
    - **Incluir vínculo del portal específico del inquilino**: seleccione si desea agregar un vínculo con el identificador de inquilino en la notificación de correo electrónico para acceder a un inquilino de Microsoft 365 específico.

    :::image type="content" source="../../media/get-incident-notifications/incidents-email-notification-settings.png" alt-text="Captura de pantalla de la página Configuración de notificaciones para las notificaciones por correo electrónico de incidentes en el portal de Microsoft 365 Defender." lightbox="../../media/get-incident-notifications/incidents-email-notification-settings.png":::

5. Seleccione **Siguiente**. En la página **Destinatarios** , agregue las direcciones de correo electrónico que recibirán las notificaciones de incidentes. Seleccione **Agregar** después de escribir cada nueva dirección de correo electrónico. Para probar las notificaciones y asegurarse de que los destinatarios las reciben en las bandejas de entrada, seleccione **Enviar correo electrónico de prueba**.
6. Seleccione **Siguiente**. En la página **Revisar regla** , revise la configuración de la regla y, a continuación, seleccione **Crear regla**. Los destinatarios comenzarán a recibir notificaciones de incidentes por correo electrónico en función de la configuración.

Para editar una regla existente, selecciónela en la lista de reglas. En el panel con el nombre de la regla, seleccione **Editar regla** y realice los cambios en las páginas **Aspectos básicos**, **Configuración de notificación** y **Destinatarios** .

Para eliminar una regla, selecciónela en la lista de reglas. En el panel con el nombre de la regla, seleccione **Eliminar**.

Una vez que reciba la notificación, puede ir directamente al incidente e iniciar la investigación de inmediato. Para obtener más información sobre cómo investigar incidentes, vea [Investigar incidentes en Microsoft 365 Defender](investigate-incidents.md).

## <a name="training-for-security-analysts"></a>Aprendizaje para analistas de seguridad

Use este módulo de aprendizaje de Microsoft Learn para comprender cómo usar Microsoft 365 Defender para administrar incidentes y alertas.

|Aprendizaje:|Investigar incidentes con Microsoft 365 Defender|
|---|---|
|![Investigar incidentes con Microsoft 365 Defender icono de entrenamiento.](../../media/incidents-overview/m365-defender-address-security-investigation.svg)| Microsoft 365 Defender unifica los datos de amenazas de varios servicios y usa la inteligencia artificial para combinarlos en incidentes y alertas. Obtenga información sobre cómo minimizar el tiempo entre un incidente y su administración mediante respuesta y resolución posteriores. <p> 27 min - 6 unidades |

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/defender-investigate-incidents/)

## <a name="next-steps"></a>Siguientes pasos

Use los pasos enumerados en función del nivel de experiencia o el rol del equipo de seguridad.

### <a name="experience-level"></a>Nivel de experiencia

Siga esta tabla para conocer el nivel de experiencia con el análisis de seguridad y la respuesta a incidentes.

| Nivel | Pasos |
|:-------|:-----|
| **New** | <ol><li> Consulte el [tutorial Responder a su primer incidente](first-incident-overview.md) para obtener una visita guiada de un proceso típico de análisis, corrección y revisión posterior al incidente en el portal de Microsoft 365 Defender con un ataque de ejemplo. </li><li> Vea qué incidentes deben [priorizarse](incident-queue.md) en función de la gravedad y otros factores. </li><li> [Administrar incidentes](manage-incidents.md), lo que incluye el cambio de nombre, la asignación, la clasificación y la adición de etiquetas y comentarios en función del flujo de trabajo de administración de incidentes.</li></ol> |
| **Experimentado** | <ol><li> Empiece a trabajar con la cola de incidentes desde la página **Incidentes** del portal de Microsoft 365 Defender. Desde allí, puedes hacer lo siguiente: </li> <ul><li> Vea qué incidentes deben [priorizarse](incident-queue.md) en función de la gravedad y otros factores. </li><li> [Administrar incidentes](manage-incidents.md), lo que incluye el cambio de nombre, la asignación, la clasificación y la adición de etiquetas y comentarios en función del flujo de trabajo de administración de incidentes. </li><li> Realizar [investigaciones](investigate-incidents.md) de incidentes. </li></ul> </li><li> Realice un seguimiento y responda a las amenazas emergentes con [el análisis de amenazas](threat-analytics.md). </li><li>  Busque amenazas de forma proactiva con la [búsqueda avanzada de amenazas](advanced-hunting-overview.md). </li><li> Consulte estos [cuadernos de estrategias de respuesta a incidentes](/security/compass/incident-response-playbooks) para obtener instrucciones detalladas sobre phishing, difusión de contraseñas y ataques de concesión de consentimiento de aplicaciones. </li></ol> |

### <a name="security-team-role"></a>Rol de equipo de seguridad

Siga esta tabla en función del rol de equipo de seguridad.

| Role | Pasos |
|---|---|
| Respondedor de incidentes (nivel 1) | Empiece a trabajar con la cola de incidentes desde la página **Incidentes** del portal de Microsoft 365 Defender. Desde allí, puedes hacer lo siguiente: <ul><li> Vea qué incidentes deben [priorizarse](incident-queue.md) en función de la gravedad y otros factores. </li><li> [Administrar incidentes](manage-incidents.md), lo que incluye el cambio de nombre, la asignación, la clasificación y la adición de etiquetas y comentarios en función del flujo de trabajo de administración de incidentes. </li></ul> |
| Investigador o analista de seguridad (nivel 2) | <ol><li> Realice [investigaciones](investigate-incidents.md) de incidentes desde la página **Incidentes** del portal de Microsoft 365 Defender. </li><li> Consulte estos [cuadernos de estrategias de respuesta a incidentes](/security/compass/incident-response-playbooks) para obtener instrucciones detalladas sobre phishing, difusión de contraseñas y ataques de concesión de consentimiento de aplicaciones. </li></ol> |
| Analista de seguridad avanzada o cazador de amenazas (nivel 3) | <ol><li>Realice [investigaciones](investigate-incidents.md) de incidentes desde la página **Incidentes** del portal de Microsoft 365 Defender. </li><li> Realice un seguimiento y responda a las amenazas emergentes con [el análisis de amenazas](threat-analytics.md). </li><li> Busque amenazas de forma proactiva con la [búsqueda avanzada de amenazas](advanced-hunting-overview.md). </li><li> Consulte estos [cuadernos de estrategias de respuesta a incidentes](/security/compass/incident-response-playbooks) para obtener instrucciones detalladas sobre phishing, difusión de contraseñas y ataques de concesión de consentimiento de aplicaciones. |
| Administrador de SOC | Consulte cómo [integrar Microsoft 365 Defender en Security Operations Center (SOC).](integrate-microsoft-365-defender-secops.md) |
