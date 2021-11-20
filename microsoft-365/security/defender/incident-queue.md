---
title: Priorizar incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo filtrar incidentes de la cola de incidentes en Microsoft 365 Defender
keywords: incident, queue, overview, devices, identities, users, mailbox, email, incidents, analyze, response, triage
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
ms.openlocfilehash: 0705424080f58d58f8c45b4a403fae01beb53373
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2021
ms.locfileid: "61128837"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft 365 Defender aplica análisis de correlación y agrega alertas relacionadas e investigaciones automatizadas de diferentes productos en un incidente. Microsoft 365 Defender activa alertas únicas en actividades que solo se pueden identificar como malintencionadas dada la visibilidad de un extremo a otro que Microsoft 365 Defender en todo el conjunto de productos. Esta vista ofrece a los analistas de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y tratar las amenazas complejas en toda la organización.

La **cola Incidentes muestra** una colección de incidentes que se crearon en dispositivos, usuarios y buzones. Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada. Esto también se conoce como triaje de incidentes.

You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes." lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

La **sección Incidentes y alertas** más recientes muestra un gráfico del número de alertas recibidas e incidentes creados en las últimas 24 horas.

De forma predeterminada, la cola de incidentes del portal de Microsoft 365 Defender muestra los incidentes vistos en los últimos seis meses. El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.

La cola de incidentes tiene columnas personalizables (seleccione **Elegir** columnas) que le dan visibilidad de distintas características del incidente o de las entidades afectadas. Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.

Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente.

Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

> [!NOTE]
> Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no tendrán su nombre cambiado.

La cola de incidentes también expone varias opciones de filtrado que, cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos. Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata. 

## <a name="available-filters"></a>Filtros disponibles

En la cola de incidentes  predeterminada, puede seleccionar Filtros para ver un panel Filtros, desde el que puede ver un conjunto filtrado de incidentes. Aquí le mostramos un ejemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Ejemplo del panel de filtros de la cola de incidentes." lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

El filtro predeterminado es mostrar todas las alertas e incidentes con un **estado nuevo** **y en** curso.

En esta tabla se enumeran los nombres de filtro disponibles.

| Nombre del filtro | Descripción |
|:-------|:-----|
| Estado | Seleccione **Nuevo**, **En curso** o **Resuelto**. |
| Severity | La gravedad de un incidente indica el impacto que puede tener en los activos. Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata. Seleccione **High**, **Medium,** **Low** o **Informational**. |
| Asignación de incidentes | Seleccione Asignado a cualquier persona, Asignado a mí o Sin asignar. |
| Múltiples orígenes del servicio  | Especifique si el filtro es para más de un origen de servicio. |
| Orígenes del servicio  | Filtra para ver solo incidentes que contienen alertas de: Gobierno de aplicaciones, Microsoft 365 Defender, Microsoft Defender para Office 365, Microsoft Defender para endpoint, Microsoft Defender para identidad, Microsoft Defender para aplicaciones en la nube. |
| Etiquetas | Seleccione uno o varios nombres de etiqueta de la lista. |
| Varias categorías  | Especifique si el filtro es para más de una categoría. |
| Categorías | Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos vistos. |
| Plataforma del sistema operativo | Limitar la vista de cola de incidentes por sistema operativo. |
| Clasificación | Filtrar incidentes en función de las clasificaciones establecidas de las alertas relacionadas. Seleccione **Alerta true**, **Alertas falsas** o **No establecer**. |
| Estado de investigación | Filtrar incidentes por el estado de la investigación automatizada.  |
| Amenaza asociada | Filtrar incidentes por una amenaza con nombre.  |
| Actors | Filtrar incidentes por un actor de amenazas con nombre.  |
| Confidencialidad de datos | Algunos ataques tienen por objetivo extraer datos confidenciales o importantes. Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes. <br><br>Este filtro solo está disponible si Microsoft Information Protection está activado.|
|||

## <a name="save-defined-filters-as-urls"></a>Guardar filtros definidos como direcciones URL

Una vez que haya configurado un filtro útil en la cola de incidentes, puede marcar la dirección URL de la pestaña del explorador o guardarla como un vínculo en una página web, un documento de Word o un lugar de su elección. Esto le dará acceso con un solo clic a las vistas clave de la cola de incidentes, como:

- Nuevos incidentes
- Incidentes de alta gravedad
- Incidentes sin firma
- Incidentes de gravedad alta y sin firma
- Incidentes asignados a mí
- Incidentes asignados a mí y a Microsoft Defender para endpoint
- Incidentes con una etiqueta o etiquetas específicas
- Incidentes con una categoría de amenaza específica
- Incidentes con una amenaza asociada específica
- Incidentes con un actor específico

Una vez que haya compilado y almacenado la lista de vistas de filtro útiles como direcciones URL, puede usarla para procesar y priorizar rápidamente los incidentes de la cola y administrarlos para su posterior asignación y análisis. [](manage-incidents.md)

## <a name="next-steps"></a>Pasos siguientes

Después de determinar qué incidente requiere la prioridad más alta, selecciónelo y:

- [Administrar](manage-incidents.md) las propiedades del incidente para etiquetas, asignación, resolución inmediata de incidentes falsos positivos y comentarios.
- Comience las [investigaciones](investigate-incidents.md).

## <a name="see-also"></a>Consulte también
- [Información general sobre incidentes](incidents-overview.md)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
