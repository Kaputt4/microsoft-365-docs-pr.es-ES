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
ms.openlocfilehash: b80bbb747ab9a0aefebaa4dd5721370ba56a3890
ms.sourcegitcommit: f181e110cdb983788a86f30d5bb018e53c83e64d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057723"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Investigar alertas con Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

>[!Note]
>En este artículo se describen las alertas de seguridad en Microsoft 365 Defender. Sin embargo, puede usar alertas de actividad para enviar notificaciones por correo electrónico a usted mismo u otros administradores cuando los usuarios realizan actividades específicas en Microsoft 365. Para obtener más información, consulte [Creación de alertas de actividad: Microsoft Purview | Microsoft Docs](../../compliance/create-activity-alerts.md).

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

- Para los roles globales de Azure Active Directory (Azure AD):

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

   - **Verdadero positivo** con un tipo de amenaza. Use esta clasificación para las alertas que indican con precisión una amenaza real. La especificación del tipo de amenaza ayuda a su equipo de seguridad a ver los patrones de amenaza y a actuar para defender a su organización de ellos.

   - **Actividad informativa y esperada** con un tipo de actividad. Use las opciones de esta categoría para clasificar las alertas de las pruebas de seguridad, la actividad del equipo rojo y el comportamiento inusual esperado de aplicaciones y usuarios de confianza.

   - **Falso positivo** para los tipos de alertas que se crearon incluso cuando no hay ninguna actividad malintencionada. La clasificación de alertas como falsos positivos ayuda a Microsoft 365 Defender a mejorar su calidad de detección.

- Comentario sobre la alerta.

> [!NOTE]
> Una forma de administrar las alertas mediante el uso de etiquetas. La funcionalidad de etiquetado para Microsoft Defender para Office 365 se está implementando de forma incremental y se encuentra actualmente en versión preliminar. <br>
> Actualmente, los nombres de etiqueta modificados solo se aplican a las alertas creadas *después* de la actualización. Las alertas que se generaron antes de la modificación no reflejarán el nombre de etiqueta actualizado. 

Para administrar un *conjunto de alertas similar a una alerta específica*, seleccione **Ver alertas similares** en el cuadro **INSIGHT** de la sección de detalles de resumen de la página de alertas.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" alt-text="Administración de una alerta en el portal de Microsoft 365 Defender":::

En el panel **Administrar alertas** , puede clasificar todas las alertas relacionadas al mismo tiempo. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" alt-text="Administración de alertas relacionadas en el portal de Microsoft 365 Defender":::

Si ya se clasificaron alertas similares en el pasado, puede ahorrar tiempo mediante Microsoft 365 Defender recomendaciones para obtener información sobre cómo se resolvieron las otras alertas. En la sección de detalles de resumen, seleccione **Recomendaciones**.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" alt-text="Ejemplo de selección de recomendaciones para una alerta":::

La pestaña **Recomendaciones** proporciona acciones y consejos de los pasos siguientes para la investigación, corrección y prevención. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" alt-text="Ejemplo de recomendaciones de alertas":::

## <a name="resolve-an-alert"></a>Resolución de una alerta

Una vez que haya terminado de analizar una alerta y se pueda resolver, vaya al panel **Administrar alerta** para la alerta o alertas similares, marque el estado como **Resuelto** y clasifique como **Un verdadero positivo** con un tipo de amenaza, una **actividad informativa y esperada** con un tipo de actividad o un **Falso positivo**.

La clasificación de alertas ayuda a Microsoft 365 Defender a mejorar su calidad de detección.

## <a name="use-power-automate-to-triage-alerts"></a>Uso de Power Automate para evaluar las alertas

Los equipos de operaciones de seguridad modernas (SecOps) necesitan automatización para funcionar de forma eficaz. Para centrarse en la búsqueda e investigación de amenazas reales, los equipos de SecOps usan Power Automate para evaluar la lista de alertas y eliminar las que no son amenazas.  

### <a name="criteria-for-resolving-alerts"></a>Criterios para resolver alertas

- El usuario tiene el mensaje fuera de la oficina activado

- El usuario no está etiquetado como de alto riesgo

Si ambos son true, SecOps marca la alerta como viaje legítimo y la resuelve. Una notificación se publica en Microsoft Teams una vez resuelta la alerta.

### <a name="connect-power-automate-to-microsoft-defender-for-cloud-apps"></a>Conectar Power Automate a Microsoft Defender for Cloud Apps

Para crear la automatización, necesitará un token de API para poder conectar Power Automate a Microsoft Defender for Cloud Apps.

1. Haga clic **en Configuración**, seleccione **Extensiones de seguridad** y, a continuación, haga clic en **Agregar token** en la pestaña **Tokens de API**.

2. Proporcione un nombre para el token y, a continuación, haga clic en **Generar**. Guarde el token, ya que lo necesitará más adelante.

### <a name="create-an-automated-flow"></a>Creación de un flujo automatizado

Vea este breve vídeo para obtener información sobre cómo funciona la automatización de forma eficaz para crear un flujo de trabajo fluido y cómo conectar Power Automate a Defender for Cloud Apps. 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn]

## <a name="next-steps"></a>Siguientes pasos

Según sea necesario para incidentes en proceso, continúe con la [investigación](investigate-incidents.md).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
- [Investigación de incidentes de pérdida de datos](investigate-dlp.md)