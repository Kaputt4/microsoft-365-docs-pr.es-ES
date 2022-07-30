---
title: Investigar alertas con Microsoft 365 Defender
description: Investigue las alertas que se ven en dispositivos, usuarios y buzones.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365
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
ms.technology: m365d
ms.openlocfilehash: 6da9ec9f0d59d04d61d4a957f5a914b06b140fac
ms.sourcegitcommit: e4882e3c66166ea7b834ad2e8fafeab42293e07d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2022
ms.locfileid: "67099225"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Investigar alertas con Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

>[!Note]
>En este artículo se describen las alertas de seguridad en Microsoft 365 Defender. Sin embargo, puede usar alertas de actividad para enviar notificaciones por correo electrónico a usted mismo u otros administradores cuando los usuarios realicen actividades específicas en Microsoft 365. Para obtener más información, consulte [Creación de alertas de actividad: Microsoft Purview | Microsoft Docs](../../compliance/create-activity-alerts.md).

Las alertas son la base de todos los incidentes e indican la aparición de eventos malintencionados o sospechosos en su entorno. Las alertas suelen formar parte de un ataque más amplio y proporcionan pistas sobre un incidente.

En Microsoft 365 Defender, las alertas relacionadas se agregan juntas para formar [incidentes](incidents-overview.md). Los incidentes siempre proporcionarán el contexto más amplio de un ataque; sin embargo, el análisis de alertas puede ser útil cuando se requiere un análisis más profundo.

La **cola Alertas** muestra el conjunto actual de alertas. Puede acceder a la cola de **alertas desde Incidentes & alertas > Alertas** en el inicio rápido del [portal de Microsoft 365 Defender](https://go.microsoft.com/fwlink/p/?linkid=2077139).

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="La sección Alertas del portal de Microsoft 365 Defender" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png":::

Aquí aparecen alertas de diferentes soluciones de seguridad de Microsoft, como Microsoft Defender para punto de conexión, Microsoft Defender para Office 365 y Microsoft 365 Defender.

De forma predeterminada, la cola de alertas del portal de Microsoft 365 Defender muestra las alertas nuevas y en curso de los últimos 30 días. La alerta más reciente está en la parte superior de la lista para que pueda verla primero. 

En la cola de alertas predeterminada, puede seleccionar **Filtrar** para ver un panel **Filtro** , desde el que puede especificar un subconjunto de las alertas. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="La sección Filtros del portal de Microsoft 365 Defender." lightbox="../../media/investigate-alerts/alerts-ss-alerts-filter.png":::

Puede filtrar las alertas según estos criterios:

- Severity
- Estado
- Orígenes del servicio
- Entidades (los recursos afectados)
- Estado de investigación automatizado

## <a name="required-roles-for-defender-for-office-365-alerts"></a>Roles necesarios para las alertas de Defender para Office 365

Tendrá que tener cualquiera de los siguientes roles para acceder a Microsoft Defender para Office 365 alertas:

- Para roles globales de Azure Active Directory (Azure AD):

   - Administrador global

   - Administrador de seguridad

   - Operador de seguridad

   - Lector global

   - Lector de seguridad

- Grupos de roles de cumplimiento de & seguridad de Office 365

   - Administrador de cumplimiento

   - Administración de la organización 

- Un [rol personalizado](custom-roles.md)

## <a name="analyze-an-alert"></a>Análisis de una alerta

Para ver la página de alerta principal, seleccione el nombre de la alerta. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Detalles de una alerta en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png":::

También puede seleccionar la acción **Abrir la página de alerta principal** en el panel **Administrar alertas** .

Una página de alerta se compone de estas secciones: 

- Historia de alertas, que es la cadena de eventos y alertas relacionadas con esta alerta en orden cronológico
- Detalles de resumen

A lo largo de una página de alerta, puede seleccionar los puntos suspensivos (**...**) junto a cualquier entidad para ver las acciones disponibles, como vincular la alerta a otro incidente. La lista de acciones disponibles depende del tipo de alerta.

### <a name="alert-sources"></a>Orígenes de alerta

Microsoft 365 Defender alertas pueden provenir de soluciones como Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Cloud Apps y el complemento de gobernanza de aplicaciones para Microsoft Defender for Cloud Apps. Es posible que observe alertas con caracteres antepuestos en la alerta. En la tabla siguiente se proporcionan instrucciones que le ayudarán a comprender la asignación de orígenes de alertas en función del carácter antepuesto de la alerta.

> [!NOTE]
> - Los GUID antepuestos solo son específicos de experiencias unificadas, como la cola de alertas unificadas, la página de alertas unificadas, la investigación unificada y el incidente unificado.
> - El carácter antepuesto no cambia el GUID de la alerta. El único cambio en el GUID es el componente antepuesto.

| Origen de alerta | Carácter antepuesto |
| :---|:--- |
| Microsoft Defender para Office 365 | `fa{GUID}` <br> Ejemplo: `fa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender para punto de conexión | `da` o `ed` para alertas de detección personalizadas <br> |
| Microsoft Defender for Identity | `aa{GUID}` <br> Ejemplo: `aa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Cloud Apps |`ca{GUID}` <br> Ejemplo: `ca123a456b-c789-1d2e-12f1g33h445h6i` |

### <a name="analyze-affected-assets"></a>Análisis de los recursos afectados

La sección **Acciones realizadas** tiene una lista de recursos afectados, como buzones, dispositivos y usuarios afectados por esta alerta. 

También puede seleccionar **Ver en el centro de acciones** para ver la pestaña **Historial** del **Centro de acciones** en el portal de Microsoft 365 Defender.

### <a name="trace-an-alerts-role-in-the-alert-story"></a>Seguimiento del rol de una alerta en el artículo de alertas

El artículo de alertas muestra todos los recursos o entidades relacionados con la alerta en una vista de árbol de procesos. La alerta del título es la que se centra cuando llega por primera vez a la página de la alerta seleccionada. Los recursos del artículo de alertas se pueden expandir y hacer clic. Proporcionan información adicional y aceleran la respuesta, ya que le permiten realizar acciones correctas en el contexto de la página de alertas. 

> [!NOTE]
> La sección del artículo de alertas puede contener más de una alerta, con alertas adicionales relacionadas con el mismo árbol de ejecución que aparecen antes o después de la alerta que ha seleccionado.

### <a name="view-more-alert-information-on-the-details-page"></a>Ver más información de alertas en la página de detalles

La página de detalles muestra los detalles de la alerta seleccionada, con detalles y acciones relacionadas con ella. Si selecciona cualquiera de los recursos o entidades afectados en el artículo de alertas, la página de detalles cambia para proporcionar información contextual y acciones para el objeto seleccionado.

Una vez seleccionada una entidad de interés, la página de detalles cambia para mostrar información sobre el tipo de entidad seleccionado, información histórica cuando está disponible y opciones para realizar acciones en esta entidad directamente desde la página de alertas.

## <a name="manage-alerts"></a>Administrar alertas

Para administrar una alerta, seleccione **Administrar alerta** en la sección de detalles de resumen de la página de alertas. Para una única alerta, este es un ejemplo del panel **Administrar alertas** .

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="La sección Administrar alerta del portal de Microsoft 365 Defender" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage.png":::

El panel **Administrar alertas** permite ver o especificar:

- Estado de la alerta (Nuevo, Resuelto, En curso).
- La cuenta de usuario a la que se ha asignado la alerta.
- Clasificación de la alerta:
     - **No establecido** (valor predeterminado).
     - **Verdadero positivo** con un tipo de amenaza. Use esta clasificación para las alertas que indican con precisión una amenaza real. Al especificar este tipo de amenaza, el equipo de seguridad verá patrones de amenazas y actuará para defender su organización de ellos.
     - **Actividad informativa y esperada** con un tipo de actividad. Use esta opción para las alertas que sean técnicamente precisas, pero que representen un comportamiento normal o una actividad de amenaza simulada. Por lo general, quiere omitir estas alertas, pero esperarlas para actividades similares en el futuro, donde las actividades las desencadenan atacantes o malware reales. Use las opciones de esta categoría para clasificar las alertas de las pruebas de seguridad, la actividad del equipo rojo y el comportamiento inusual esperado de aplicaciones y usuarios de confianza.
     - **Falso positivo** para los tipos de alertas que se crearon incluso cuando no hay ninguna actividad malintencionada o para una falsa alarma. Use las opciones de esta categoría para clasificar las alertas que se identifican erróneamente como eventos o actividades normales como malintencionados o sospechosos. A diferencia de las alertas de "Actividad informativa y esperada", que también puede ser útil para detectar amenazas reales, por lo general no quiere volver a ver estas alertas. La clasificación de alertas como falsos positivos ayuda a Microsoft 365 Defender a mejorar su calidad de detección.
- Comentario sobre la alerta.

>[!NOTE]
> Alrededor del 29 de agosto de 2022, los valores de determinación de alertas admitidos anteriormente ("Apt" y "SecurityPersonnel") quedarán en desuso y ya no estarán disponibles a través de la API.

> [!NOTE]
> Una forma de administrar las alertas mediante el uso de etiquetas. La funcionalidad de etiquetado para Microsoft Defender para Office 365 se está implementando de forma incremental y se encuentra actualmente en versión preliminar. <br>
> Actualmente, los nombres de etiqueta modificados solo se aplican a las alertas creadas *después* de la actualización. Las alertas que se generaron antes de la modificación no reflejarán el nombre de etiqueta actualizado. 

Para administrar un *conjunto de alertas similar a una alerta específica*, seleccione **Ver alertas similares** en el cuadro **INSIGHT** de la sección de detalles de resumen de la página de alertas.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" alt-text="Administración de una alerta en el portal de Microsoft 365 Defender":::

En el panel **Administrar alertas** , puede clasificar todas las alertas relacionadas al mismo tiempo. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" alt-text="Administración de alertas relacionadas en el portal de Microsoft 365 Defender":::

Si ya se clasificaron alertas similares en el pasado, puede ahorrar tiempo mediante Microsoft 365 Defender recomendaciones para obtener información sobre cómo se resolvieron las otras alertas. En la sección de detalles de resumen, seleccione **Recomendaciones**.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" alt-text="Ejemplo de selección de recomendaciones para una alerta":::

En **la pestaña Recomendaciones** se proporcionan acciones y consejos de los pasos siguientes para la investigación, corrección y prevención. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" alt-text="Ejemplo de recomendaciones de alertas":::

 
## <a name="suppress-an-alert"></a>Suprimir una alerta

Como analista del Centro de operaciones de seguridad (SOC), uno de los principales problemas es evaluar el gran número de alertas que se desencadenan diariamente. En el caso de las alertas de prioridad inferior, un analista sigue siendo necesario para evaluar y resolver la alerta, que tiende a ser un proceso manual. El tiempo de un analista de SOC es valioso, ya que solo quiere centrarse en alertas de alta gravedad y prioridad alta.

La supresión de alertas proporciona la capacidad de optimizar y administrar las alertas de antemano. Esto simplifica la cola de alertas y ahorra tiempo de evaluación de prioridades ocultando o resolviendo alertas automáticamente, cada vez que se produce un determinado comportamiento organizativo esperado y se cumplen las condiciones de regla. 

Puede crear condiciones de regla basadas en "tipos de evidencia", como archivos, procesos, tareas programadas y muchos otros tipos de evidencia que desencadenan la alerta. Después de crear la regla, el usuario puede aplicar la regla en la alerta seleccionada o en cualquier tipo de alerta que cumpla las condiciones de regla para suprimir la alerta. 

> [!NOTE]
> No se recomienda la supresión de alertas. Sin embargo, en determinadas situaciones, una aplicación empresarial interna conocida o pruebas de seguridad desencadenan una actividad esperada y no desea ver estas alertas. Por lo tanto, puede crear una regla de supresión para la alerta. 

### <a name="create-rule-conditions-to-suppress-alerts"></a>Creación de condiciones de regla para suprimir alertas

Para crear una regla de supresión para las alertas:

1. Seleccione la alerta investigada. En la página de alerta principal, seleccione **Crear regla de supresión** en la sección de detalles de resumen de la página de alertas. 

    :::image type="content" source="../../media/investigate-alerts/suppression-click.png" lightbox="../../media/investigate-alerts/suppression-click.png" alt-text="Captura de pantalla de la acción Crear regla de separación.":::

2. En el panel **Crear regla de supresión** , seleccione **Solo este tipo de alerta** para aplicar la regla en la alerta seleccionada.

    Sin embargo, para aplicar la regla en cualquier tipo de alerta que cumpla las condiciones de regla, seleccione **Cualquier tipo de alerta en función de las condiciones de IOC**.
 
    Los IOC son indicadores como archivos, procesos, tareas programadas y otros tipos de evidencia que desencadenan la alerta.
     
3. En la sección **IOC** , seleccione **Any IOC (Cualquier IOC** ) para suprimir la alerta, independientemente de la "evidencia" que haya causado la alerta. 

    Para establecer varias condiciones de regla, seleccione **Elegir IOC**. Use **AND**, **OR** y las opciones de agrupación para crear una relación entre estos varios "tipos de evidencia" que provocan la alerta.
 
    1. Por ejemplo, en la sección **Condiciones** , seleccione la evidencia desencadenante **Entity Role: Triggering**, **Equals** y seleccione el tipo de evidencia en la lista desplegable. 

    :::image type="content" source="../../media/investigate-alerts/evidence-types-drop-down-list.png" alt-text="Captura de pantalla de la lista desplegable de tipos de evidencia." lightbox="../../media/investigate-alerts/evidence-types-drop-down-list.png":::

    2. Todas las propiedades de esta "evidencia" se rellenarán automáticamente como un nuevo subgrupo en los campos respectivos siguientes.
    :::image type="content" source="../../media/investigate-alerts/properties-evidence.png" alt-text="Captura de pantalla de las propiedades de la rellenación automática de evidencias." lightbox="../../media/investigate-alerts/properties-evidence.png" :::

    > [!NOTE]
    > Los valores de condición no distinguen mayúsculas de minúsculas. 

    3. Puede editar o eliminar propiedades de esta "evidencia" según sus necesidades (con caracteres comodín, cuando se admiten).

    4. Aparte de los archivos y procesos, el script de AMSI, el evento WMI y las tareas programadas son algunos de los tipos de evidencia recién agregados que puede seleccionar en la lista desplegable tipos de evidencia.
    :::image type="content" source="../../media/investigate-alerts/other-evidence-types.png" alt-text="Captura de pantalla de otros tipos de pruebas." lightbox="../../media/investigate-alerts/other-evidence-types.png":::

    5. Para agregar otro IOC, haga clic en **Agregar filtro**. 
    > [!NOTE]
    > Es necesario agregar al menos un IOC a la condición de regla para suprimir cualquier tipo de alerta.
    
4. Como alternativa, puede seleccionar **Rellenar automáticamente todas las E/S relacionadas con la alerta 7** en la sección **IOC** para agregar todos los tipos de evidencia relacionados con alertas y sus propiedades a la vez en la sección **Condiciones** .
    :::image type="content" source="../../media/investigate-alerts/autofill-iocs.png" alt-text="Captura de pantalla del relleno automático de todas las IOC relacionadas con alertas." lightbox="../../media/investigate-alerts/autofill-iocs.png":::

5. En la sección **Ámbito** , establezca el ámbito en la subsesión **Condiciones** seleccionando dispositivo específico, varios dispositivos, grupos de dispositivos, toda la organización o por usuario.
    > [!NOTE]
    > Debe tener Administración permiso cuando el **ámbito** solo se establece para **El usuario**. Administración permiso no es necesario cuando el **ámbito** se establece para **el usuario** junto con **dispositivos**, **grupos de dispositivos**.

:::image type="content" source="../../media/investigate-alerts/suppression-choose-scope.png" lightbox="../../media/investigate-alerts/suppression-choose-scope.png" alt-text="Captura de pantalla del panel crear regla de supresión: Condiciones, Ámbito, Acción.":::
 
6. En la sección **Acción** , realice la acción adecuada de **Ocultar alerta** o **Resolver alerta**.
    Escriba **Nombre**, **Comentario** y haga clic en **Guardar**.

7. **Evite que las IOC se bloqueen en el futuro:**<br>
Una vez guardada la regla de supresión, en la página **Creación correcta de la regla de supresión** que aparece, puede agregar las IOC seleccionadas como indicadores a la "lista de permitidos" y evitar que se bloqueen en el futuro. <br>
Todos los IOC relacionados con alertas se mostrarán en la lista. <br>
Las IOC que se seleccionaron en las condiciones de supresión se seleccionarán de forma predeterminada.
      1. Por ejemplo, puede agregar archivos para que puedan usarse en la **opción Seleccionar evidencia (IOC) que se va a permitir**. De forma predeterminada, se selecciona el archivo que desencadenó la alerta.
      1. Escriba el ámbito en seleccionar el **ámbito al que se va a aplicar**. De forma predeterminada, se selecciona el ámbito de la alerta relacionada.
      1. Haga clic en **Guardar**. Ahora el archivo no está bloqueado como está en la lista de permitidos.

    :::image type="content" source="../../media/investigate-alerts/suppression-2-choose-iocs.png" lightbox="../../media/investigate-alerts/suppression-2-choose-iocs.png" alt-text="Captura de pantalla de la creación correcta de reglas de supresión. ":::

8.  La nueva funcionalidad de alerta de supresión está disponible de forma predeterminada. <br> Sin embargo, puede volver a la experiencia anterior en Microsoft 365 Defender portal; para ello, vaya a **Configuración > Puntos de conexión > Supresión de alertas** y desactive el botón de alternancia **Nueva creación de reglas de supresión habilitada**. 
 
    :::image type="content" source="../../media/investigate-alerts/suppression-toggle.png" lightbox="../../media/investigate-alerts/suppression-toggle.png" alt-text="Captura de pantalla de alternancia para activar o desactivar la característica de creación de reglas de supresión.":::

9.  **Editar reglas existentes:** <br> Siempre puede agregar o cambiar las condiciones de regla y el ámbito de las reglas nuevas o existentes en el portal de Microsoft Defender; para ello, seleccione la regla pertinente y haga clic en **Editar regla**.    
    Para editar las reglas existentes, asegúrese de que el botón de alternancia **Nueva creación de reglas de supresión habilitada** esté habilitado.         

    :::image type="content" source="../../media/investigate-alerts/suppression-toggle-on-edit.png" lightbox="../../media/investigate-alerts/suppression-toggle-on-edit.png" alt-text="Captura de pantalla de la regla de eliminación de edición.":::
  
## <a name="resolve-an-alert"></a>Resolución de una alerta

Una vez que haya terminado de analizar una alerta y se pueda resolver, vaya al panel **Administrar alerta** para la alerta o alertas similares, marque el estado como **Resuelto** y clasifique como **Un verdadero positivo** con un tipo de amenaza, una **actividad informativa y esperada** con un tipo de actividad o un **Falso positivo**.

La clasificación de alertas ayuda a Microsoft 365 Defender a mejorar su calidad de detección.

## <a name="use-power-automate-to-triage-alerts"></a>Uso de Power Automate para evaluar las alertas

Los equipos de operaciones de seguridad modernas (SecOps) necesitan automatización para funcionar de forma eficaz. Para centrarse en la búsqueda e investigación de amenazas reales, los equipos de SecOps usan Power Automate para evaluar la lista de alertas y eliminar las que no son amenazas.  

### <a name="criteria-for-resolving-alerts"></a>Criterios para resolver alertas

- El usuario tiene el mensaje fuera de la oficina activado

- El usuario no está etiquetado como de alto riesgo

Si ambos son true, SecOps marca la alerta como viaje legítimo y la resuelve. Una notificación se publica en Microsoft Teams una vez resuelta la alerta.

### <a name="connect-power-automate-to-microsoft-defender-for-cloud-apps"></a>Conexión de Power Automate a Microsoft Defender for Cloud Apps

Para crear la automatización, necesitará un token de API para poder conectar Power Automate a Microsoft Defender for Cloud Apps.

1. Haga clic en **Configuración**, seleccione **Extensiones de seguridad** y, a continuación, haga clic en **Agregar token** en la pestaña **Tokens de API** .

2. Proporcione un nombre para el token y, a continuación, haga clic en **Generar**. Guarde el token, ya que lo necesitará más adelante.

### <a name="create-an-automated-flow"></a>Creación de un flujo automatizado

Vea este breve vídeo para obtener información sobre cómo funciona la automatización de forma eficaz para crear un flujo de trabajo fluido y cómo conectar Power Automate a Defender for Cloud Apps. 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn]

## <a name="next-steps"></a>Siguientes pasos

Según sea necesario para incidentes en proceso, continúe con la [investigación](investigate-incidents.md).

## <a name="see-also"></a>Consulte también

- [Información general sobre incidentes](incidents-overview.md)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
- [Investigación de incidentes de pérdida de datos](investigate-dlp.md)