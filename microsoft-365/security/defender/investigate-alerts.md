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
ms.technology: m365d
ms.openlocfilehash: 2dcc7e57182df3fe0a06bb1713b3a0786f35e144
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2022
ms.locfileid: "62156141"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Investigar alertas en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Las alertas son la base de todos los incidentes e indican la aparición de eventos malintencionados o sospechosos en su entorno. Las alertas suelen formar parte de un ataque más amplio y proporcionan pistas sobre un incidente.

En Microsoft 365 Defender, las alertas relacionadas se agregan juntas para formar [incidentes](incidents-overview.md). Los incidentes siempre proporcionarán el contexto más amplio de un ataque, sin embargo, el análisis de alertas puede ser útil cuando se requiere un análisis más profundo. 

La **cola De alertas** muestra el conjunto actual de alertas. You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal</a>.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Ejemplo de la cola de alertas en Microsoft 365 Defender portal.":::

Las alertas de diferentes soluciones de seguridad de Microsoft como Microsoft Defender para endpoint, Microsoft Defender para Office 365 y Microsoft 365 Defender aparecen aquí.

De forma predeterminada, la cola de alertas del portal de Microsoft 365 Defender muestra las alertas nuevas y en curso de los últimos 30 días. La alerta más reciente está en la parte superior de la lista para que pueda verla primero. 

En la cola de alertas predeterminada, puede seleccionar Filtros **para** ver un panel **Filtros,** desde el que puede especificar un subconjunto de las alertas. Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Ejemplo del panel de filtros para la cola de alertas en el portal Microsoft 365 Defender web.":::

Puede filtrar alertas según estos criterios:

- Severity
- Estado
- Orígenes del servicio
- Activos afectados
- Estado de investigación automatizada

## <a name="required-roles-for-defender-for-office-365-alerts"></a>Roles necesarios para Defender para Office 365 alertas

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

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Ejemplo de la página de detalles de una alerta en Microsoft 365 Defender portal.":::

También puede seleccionar la acción **Abrir la página de alerta** principal en el panel **Administrar** alerta.

Una página de alerta se compone de estas secciones: 

- Historia de alertas, que es la cadena de eventos y alertas relacionadas con esta alerta en orden cronológico
- Detalles de resumen

A lo largo de una página de alerta, puede seleccionar los puntos suspensivos (**...**) junto a cualquier entidad para ver las acciones disponibles, como abrir la página de alerta o vincular la alerta a otro incidente.

### <a name="alert-sources"></a>Orígenes de alertas

Microsoft 365 Defender alertas pueden venir de soluciones como Microsoft Defender para endpoint, Microsoft Defender para Office 365, Microsoft Defender para aplicaciones en la nube y el complemento de gobierno de aplicaciones para Microsoft Defender para aplicaciones en la nube. Es posible que observe alertas con caracteres anteponer en la alerta. En la tabla siguiente se proporcionan instrucciones que le ayudarán a comprender la asignación de orígenes de alerta en función del carácter anteponer a la alerta.

> [!NOTE]
> - Los GUID antediados son específicos solo para experiencias unificadas, como la cola de alertas unificadas, la página de alertas unificadas, la investigación unificada y el incidente unificado.
> - El carácter anteponer no cambia el GUID de la alerta. El único cambio en el GUID es el componente anteponer.

| Origen de alertas | Carácter anteponer |
| :---|:--- |
| Microsoft Defender para Office 365 | `fa{GUID}` <br> Ejemplo: `fa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender para punto de conexión | `da` o `ed` para alertas de detección personalizadas <br> |
| Microsoft Defender for Identity | `aa{GUID}` <br> Ejemplo: `aa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Cloud Apps |`ca{GUID}` <br> Ejemplo: `ca123a456b-c789-1d2e-12f1g33h445h6i` |

### <a name="analyze-affected-assets"></a>Analizar activos afectados

La **sección Acciones realizadas** tiene una lista de activos afectados, como buzones, dispositivos y usuarios afectados por esta alerta. 

También puede seleccionar Ver **en el centro** de  acciones para ver la pestaña Historial del centro de acciones en el portal Microsoft 365 Defender acción.  

### <a name="trace-an-alerts-role-in-the-alert-story"></a>Seguimiento del rol de una alerta en el artículo de alerta

El artículo de alerta muestra todos los activos o entidades relacionados con la alerta en una vista de árbol de proceso. La alerta del título es la que está en foco cuando se aterriza por primera vez en la página de la alerta seleccionada. Los activos del artículo de alerta se pueden expandir y hacer clic. Proporcionan información adicional y aceleran la respuesta, ya que permiten realizar acciones directamente en el contexto de la página de alerta. 

> [!NOTE]
> La sección de artículo de alerta puede contener más de una alerta, con alertas adicionales relacionadas con el mismo árbol de ejecución que aparecen antes o después de la alerta seleccionada.

### <a name="view-more-alert-information-on-the-details-page"></a>Ver más información de alerta en la página de detalles

La página de detalles muestra los detalles de la alerta seleccionada, con detalles y acciones relacionadas con ella. Si selecciona cualquiera de los activos o entidades afectados en el artículo de alerta, la página de detalles cambia para proporcionar información contextual y acciones para el objeto seleccionado.

Una vez que haya seleccionado una entidad de interés, la página de detalles cambia para mostrar información sobre el tipo de entidad seleccionada, información histórica cuando está disponible y opciones para realizar acciones en esta entidad directamente desde la página de alerta.

## <a name="manage-alerts"></a>Administrar alertas

Para administrar una alerta, seleccione la alerta en la cola de alertas de su fila para ver un **panel Administrar alertas.** Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Ejemplo del panel de resumen de una alerta en el portal Microsoft 365 Defender web.":::

El **panel Administrar alerta** le permite ver o especificar:

- Estado de alerta (Nuevo, Resuelto, En curso).
- Cuenta de usuario a la que se ha asignado la alerta.
- Clasificación de la alerta (No establecido, Alerta verdadera, Alerta falsa).
- Para la clasificación como una alerta verdadera, el tipo de amenaza de la alerta en **el campo Determinación.**
- Un comentario sobre la alerta.

> [!NOTE]
> Una forma de administrar alertas mediante el uso de etiquetas. La funcionalidad de etiquetado para Microsoft Defender para Office 365 se está ejecutando de forma incremental y actualmente está en versión preliminar. <br>
> Actualmente, los nombres de etiqueta modificados solo se aplican a las alertas *creadas después de* la actualización. Las alertas que se generaron antes de la modificación no reflejarán el nombre de la etiqueta actualizada. 

Desde este panel, también puede realizar estas acciones adicionales: 

- Abrir la página de alerta principal
- Consultar a un experto en amenazas de Microsoft
- Ver envío
- Vincular a otro incidente
- Ver la alerta en una escala de tiempo
- Crear una regla de supresión

Por ejemplo:

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Ejemplo de las acciones de una alerta en el portal de Microsoft 365 Defender web":::

La lista de acciones adicionales depende del tipo de alerta.

## <a name="resolve-an-alert"></a>Resolver una alerta

Una vez que haya terminado de analizar una alerta  y se pueda resolver, vaya al  panel Administrar alerta de la alerta y marque el estado de la alerta como Resuelto y clasifique como alerta **False** o **Alerta True**. Para las alertas true, especifique el tipo de amenaza de la alerta en el **campo Determinación.**

Clasificar alertas y especificar su determinación ayuda a ajustar Microsoft 365 Defender para proporcionar alertas más verdaderas y menos falsas.

## <a name="use-power-automate-to-triage-alerts"></a>Usar Power Automate para triage alerts

Los equipos de operaciones de seguridad modernas (SecOps) necesitan automatización para funcionar eficazmente. Para centrarse en la búsqueda e investigación de amenazas reales, los equipos de SecOps usan Power Automate para obtener información sobre la lista de alertas y eliminar las que no son amenazas.  

### <a name="criteria-for-resolving-alerts"></a>Criterios para resolver alertas

- El usuario tiene el mensaje de fuera de la oficina activado

- El usuario no está etiquetado como de alto riesgo

Si ambos son true, SecOps marca la alerta como viaje legítimo y la resuelve. Una notificación se publica en Microsoft Teams una vez resuelta la alerta.

### <a name="connect-power-automate-to-microsoft-defender-for-cloud-apps"></a>Conectar Power Automate a Microsoft Defender para aplicaciones en la nube

Para crear la automatización, necesitarás un token de API antes de conectarte Power Automate a Microsoft Defender para aplicaciones en la nube.

1. Haga **clic Configuración**, seleccione Extensiones de **seguridad** y, a continuación, haga clic en **Agregar token** en la pestaña Tokens de **API.**

2. Proporcione un nombre para el token y, a continuación, haga clic **en Generar**. Guarde el token como lo necesitará más adelante.

### <a name="create-an-automated-flow"></a>Crear un flujo automatizado

Para ver el proceso detallado paso a paso, vea el vídeo [aquí](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn).

En este vídeo también se describe cómo conectar power automate a Defender for Cloud Apps.

## <a name="next-steps"></a>Siguientes pasos

Según sea necesario para incidentes en el proceso, continúe con la [investigación](investigate-incidents.md).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
