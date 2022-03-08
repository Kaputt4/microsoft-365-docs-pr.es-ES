---
title: Investigar alertas en Microsoft 365 Defender
description: Investigar las alertas que se ven en dispositivos, usuarios y buzones.
keywords: incidentes, alertas, investigar, analizar, responder, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365
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
ms.openlocfilehash: ce75fff753acfa9d5e183154e09805b04d7523da
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321461"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Investigar alertas en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Las alertas son la base de todos los incidentes e indican la aparición de eventos malintencionados o sospechosos en su entorno. Las alertas suelen formar parte de un ataque más amplio y proporcionan pistas sobre un incidente.

En Microsoft 365 Defender, las alertas relacionadas se agregan juntas para formar [incidentes](incidents-overview.md). Los incidentes siempre proporcionarán el contexto más amplio de un ataque, sin embargo, el análisis de alertas puede ser útil cuando se requiere un análisis más profundo. 

La **cola De alertas** muestra el conjunto actual de alertas. Puede acceder a la cola de **alertas desde Incidentes & alertas > alertas en** el inicio rápido del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender web</a>.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Ejemplo de la cola de alertas en el Microsoft 365 Defender web":::

Las alertas de diferentes soluciones de seguridad de Microsoft como Microsoft Defender para endpoint, Microsoft Defender para Office 365 y Microsoft 365 Defender aparecen aquí.

De forma predeterminada, la cola de alertas del portal de Microsoft 365 Defender muestra las alertas nuevas y en curso de los últimos 30 días. La alerta más reciente está en la parte superior de la lista para que pueda verla primero. 

En la cola de alertas predeterminada, puede seleccionar **Filtrar** para ver un panel **Filtro** , desde el que puede especificar un subconjunto de las alertas. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Ejemplo del panel de filtros de la cola de alertas en el portal Microsoft 365 Defender web":::

Puede filtrar alertas según estos criterios:

- Severity
- Estado
- Orígenes del servicio
- Entidades (los activos afectados)
- Estado de investigación automatizada

## <a name="required-roles-for-defender-for-office-365-alerts"></a>Roles obligatorios para Defender para Office 365 alertas

Tendrás que tener cualquiera de los siguientes roles para tener acceso a Microsoft Defender para obtener Office 365 alertas:

- Para Azure Active Directory (Azure AD) roles globales:

   - Administrador global

   - Administrador de seguridad

   - Operador de seguridad

   - Lector global

   - Lector de seguridad

- Office 365 de roles de & seguridad

   - Administrador de cumplimiento

   - Administración de la organización 

- Un [rol personalizado](custom-roles.md)

## <a name="analyze-an-alert"></a>Analizar una alerta

Para ver la página de alerta principal, seleccione el nombre de la alerta. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Ejemplo de la página de detalles de una alerta en el portal de Microsoft 365 Defender datos":::

Una página de alerta se compone de estas secciones: 

- Historia de alertas, que es la cadena de eventos y alertas relacionadas con esta alerta en orden cronológico
- Detalles de resumen

A lo largo de una página de alerta, puede seleccionar los puntos suspensivos (**...**) junto a cualquier entidad para ver acciones disponibles, como vincular la alerta a otro incidente. La lista de acciones disponibles depende del tipo de alerta.

### <a name="alert-sources"></a>Orígenes de alertas

Microsoft 365 Defender alertas pueden venir de soluciones como Microsoft Defender para endpoint, Microsoft Defender para Office 365, Microsoft Defender para aplicaciones en la nube y el complemento de gobierno de aplicaciones para Microsoft Defender para aplicaciones en la nube. Es posible que observe alertas con caracteres anteponer en la alerta. En la tabla siguiente se proporcionan instrucciones que le ayudarán a comprender la asignación de orígenes de alerta en función del carácter anteponer a la alerta.

> [!NOTE]
> - Los GUID antediados son específicos solo para experiencias unificadas, como la cola de alertas unificadas, la página de alertas unificadas, la investigación unificada y el incidente unificado.
> - El carácter anteponer no cambia el GUID de la alerta. El único cambio en el GUID es el componente anteponer.

| Origen de alertas | Carácter anteponer |
| :---|:--- |
| Microsoft Defender para Office 365 | `fa{GUID}` <br> Ejemplo: `fa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender para punto de conexión | `da` o para `ed` alertas de detección personalizadas <br> |
| Microsoft Defender for Identity | `aa{GUID}` <br> Ejemplo: `aa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Cloud Apps |`ca{GUID}` <br> Ejemplo: `ca123a456b-c789-1d2e-12f1g33h445h6i` |

### <a name="analyze-affected-assets"></a>Analizar activos afectados

La **sección Acciones realizadas** tiene una lista de activos afectados, como buzones, dispositivos y usuarios afectados por esta alerta. 

También puede seleccionar **Ver en el centro de** acciones para ver  la pestaña Historial del  centro de acciones en el portal Microsoft 365 Defender acción. 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>Seguimiento del rol de una alerta en el artículo de alerta

El artículo de alerta muestra todos los activos o entidades relacionados con la alerta en una vista de árbol de proceso. La alerta del título es la que está en foco cuando se aterriza por primera vez en la página de la alerta seleccionada. Los activos del artículo de alerta se pueden expandir y hacer clic. Proporcionan información adicional y aceleran la respuesta, ya que permiten realizar acciones directamente en el contexto de la página de alerta. 

> [!NOTE]
> La sección de artículo de alerta puede contener más de una alerta, con alertas adicionales relacionadas con el mismo árbol de ejecución que aparecen antes o después de la alerta seleccionada.

### <a name="view-more-alert-information-on-the-details-page"></a>Ver más información de alerta en la página de detalles

La página de detalles muestra los detalles de la alerta seleccionada, con detalles y acciones relacionadas con ella. Si selecciona cualquiera de los activos o entidades afectados en el artículo de alerta, la página de detalles cambia para proporcionar información contextual y acciones para el objeto seleccionado.

Una vez que haya seleccionado una entidad de interés, la página de detalles cambia para mostrar información sobre el tipo de entidad seleccionada, información histórica cuando está disponible y opciones para realizar acciones en esta entidad directamente desde la página de alerta.

## <a name="manage-alerts"></a>Administrar alertas

Para administrar una alerta, seleccione **Administrar alerta en** la sección detalles de resumen de la página de alerta. Para una sola alerta, este es un ejemplo del panel **Administrar alerta** .

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Ejemplo del panel Administrar alertas en el portal de Microsoft 365 Defender web":::

El **panel Administrar alerta** le permite ver o especificar:

- Estado de alerta (Nuevo, Resuelto, En curso).
- Cuenta de usuario a la que se ha asignado la alerta.
- Clasificación de la alerta:

   - **No se establece** (el valor predeterminado).

   - **Verdadero positivo** con un tipo de amenaza. Use esta clasificación para alertas que indiquen con precisión una amenaza real. La especificación del tipo de amenaza ayuda a su equipo de seguridad a ver los patrones de amenaza y a actuar para defender a su organización de ellos.

   - **Actividad informativo y esperada** con un tipo de actividad. Usa las opciones de esta categoría para clasificar alertas para pruebas de seguridad, actividad de equipo rojo y comportamiento inusual esperado de usuarios y aplicaciones de confianza.

   - **Falso positivo** para tipos de alertas que se crearon incluso cuando no hay ninguna actividad malintencionada. Clasificar alertas como falso positivo ayuda Microsoft 365 Defender mejorar su calidad de detección.

- Un comentario sobre la alerta.

> [!NOTE]
> Una forma de administrar alertas mediante el uso de etiquetas. La funcionalidad de etiquetado de Microsoft Defender para Office 365 se está ejecutando de forma incremental y actualmente está en versión preliminar. <br>
> Actualmente, los nombres de etiqueta modificados solo se aplican a las alertas *creadas después de* la actualización. Las alertas que se generaron antes de la modificación no reflejarán el nombre de la etiqueta actualizada. 

Para administrar un *conjunto de alertas similar a una alerta* específica, seleccione **Ver alertas similares** en el cuadro **INSIGHT** de la sección detalles de resumen de la página de alertas.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" alt-text="Administrar una alerta en el portal Microsoft 365 Defender web":::

En el **panel Administrar alertas** , puede clasificar todas las alertas relacionadas al mismo tiempo. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" alt-text="Administración de alertas relacionadas en el portal Microsoft 365 Defender web":::

Si ya se clasificaron alertas similares en el pasado, puede ahorrar tiempo usando Microsoft 365 Defender recomendaciones para obtener información sobre cómo se resolvieron las otras alertas. En la sección detalles de resumen, **seleccione Recomendaciones**.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" alt-text="Ejemplo de selección de recomendaciones para una alerta":::

La **pestaña Recomendaciones** proporciona acciones y consejos para investigación, corrección y prevención en el siguiente paso. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" alt-text="Ejemplo de recomendaciones de alerta":::

## <a name="resolve-an-alert"></a>Resolver una alerta

Una vez que haya terminado de analizar una alerta y se pueda resolver, vaya al panel Administrar  alerta para la alerta o alertas similares y marque el estado como **Resuelto** y, a continuación, clasifique como True **positivo** con un tipo de amenaza, una actividad **informational,** esperada con un tipo de actividad o un **falso** positivo.

Clasificar alertas ayuda Microsoft 365 Defender mejorar su calidad de detección.

## <a name="use-power-automate-to-triage-alerts"></a>Usar Power Automate para triage alerts

Los equipos de operaciones de seguridad modernas (SecOps) necesitan automatización para funcionar eficazmente. Para centrarse en la búsqueda e investigación de amenazas reales, los equipos de SecOps usan Power Automate para obtener información sobre la lista de alertas y eliminar las que no son amenazas.  

### <a name="criteria-for-resolving-alerts"></a>Criterios para resolver alertas

- El usuario tiene el mensaje de fuera de la oficina activado

- El usuario no está etiquetado como de alto riesgo

Si ambos son true, SecOps marca la alerta como viaje legítimo y la resuelve. Una notificación se publica en Microsoft Teams una vez resuelta la alerta.

### <a name="connect-power-automate-to-microsoft-defender-for-cloud-apps"></a>Conectar Power Automate a Microsoft Defender para aplicaciones en la nube

Para crear la automatización, necesitarás un token de API antes de conectarte Power Automate a Microsoft Defender para aplicaciones en la nube.

1. Haga **clic Configuración**, seleccione **Extensiones de seguridad** y, a continuación, haga clic **en Agregar token** en la pestaña **Tokens de API**.

2. Proporcione un nombre para el token y, a continuación, haga clic en **Generar**. Guarde el token como lo necesitará más adelante.

### <a name="create-an-automated-flow"></a>Crear un flujo automatizado

Para ver el proceso detallado paso a paso, vea el vídeo [aquí](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn).

En este vídeo también se describe cómo conectar power automate a Defender for Cloud Apps.

## <a name="next-steps"></a>Siguientes pasos

Según sea necesario para incidentes en el proceso, continúe con la [investigación](investigate-incidents.md).

## <a name="see-also"></a>Consulte también

- [Información general sobre incidentes](incidents-overview.md)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
