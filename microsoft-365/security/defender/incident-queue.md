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
ms.openlocfilehash: 38bfde92a2988cd8bdbca770402af96a4b9c5134
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321843"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft 365 Defender aplica análisis de correlación y agrega alertas relacionadas e investigaciones automatizadas de diferentes productos en un incidente. Microsoft 365 Defender activa alertas únicas en actividades que solo se pueden identificar como malintencionadas dada la visibilidad de un extremo a otro que Microsoft 365 Defender en todo el conjunto de productos. Esta vista proporciona a los analistas de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y tratar las amenazas complejas en toda la organización.

La **cola Incidentes muestra** una colección de incidentes que se crearon en dispositivos, usuarios y buzones. Le ayuda a ordenar los incidentes para priorizar y crear una decisión de respuesta a la ciberseguridad informada, un proceso conocido como evaluación de incidentes.

Puede acceder a la cola de incidentes desde **Incidentes & alertas > incidentes** en el inicio rápido del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender incidentes</a>. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes." lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

La **sección Incidentes y alertas** más recientes muestra un gráfico del número de alertas recibidas e incidentes creados en las últimas 24 horas.

De forma predeterminada, la cola de incidentes del portal de Microsoft 365 Defender muestra los incidentes vistos en los últimos seis meses. El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.

La cola de incidentes tiene columnas personalizables (seleccione **Elegir** columnas) que le dan visibilidad de distintas características del incidente o de las entidades afectadas. Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.

Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente.

Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

> [!NOTE]
> Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no tendrán su nombre cambiado.

La cola de incidentes también proporciona varias opciones de filtrado que, cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos. Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata. 

La **lista Filtros** que se encuentra encima de la lista de incidentes muestra los filtros aplicados actualmente.

## <a name="available-filters"></a>Filtros disponibles

En la cola de incidentes predeterminada, puede seleccionar **Filtrar** para ver un  panel Filtro, desde el que se especifica un conjunto filtrado de incidentes. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Ejemplo del panel de filtros de la cola de incidentes." lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

También puede ver el panel **Filtro** seleccionando cualquiera de los filtros de la lista **Filtros encima de** la lista de incidentes.

En esta tabla se enumeran los nombres de filtro disponibles.

| Nombre del filtro | Descripción |
|:-------|:-----|
| Estado | Seleccione **Nuevo**, **En curso** o **Resuelto**. |
| Severity | La gravedad de un incidente indica el impacto que puede tener en los activos. Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata. Seleccione **High**, **Medium**, **Low** o **Informational**. |
| Asignación de incidentes | Seleccione el usuario o los usuarios asignados. |
| Múltiples orígenes del servicio  | Especifique si el filtro es para más de un origen de servicio. |
| Orígenes del servicio  | Especifique incidentes que contengan alertas de: Gobierno de aplicaciones, Microsoft 365 Defender, Microsoft Defender para Office 365, Microsoft Defender para endpoint, Microsoft Defender para identidad, Microsoft Defender para aplicaciones en la nube. |
| Etiquetas | Seleccione uno o varios nombres de etiqueta de la lista. |
| Varias categorías  | Especifique si el filtro es para más de una categoría. |
| Categorías | Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos vistos. |
| Entidades | Especifique el nombre de un activo, como un usuario, un dispositivo, un buzón o un nombre de aplicación. |
| Confidencialidad de datos | Algunos ataques tienen por objetivo extraer datos confidenciales o importantes. Al aplicar un filtro para etiquetas de confidencialidad específicas, puede determinar rápidamente si la información confidencial puede verse comprometida y priorizar la solución de esos incidentes. <br><br> Este filtro solo está disponible si Microsoft Information Protection está activado. |
| Grupos de dispositivo | Especifica un [nombre de grupo de](/windows/security/threat-protection/microsoft-defender-atp/machine-groups) dispositivos. |
| Plataforma del sistema operativo | Especificar sistemas operativos de dispositivos. |
| Clasificación | Especifique el conjunto de clasificaciones de las alertas relacionadas. |
| Estado de investigación automatizada | Especifique el estado de la investigación automatizada.  |
| Amenaza asociada | Especifique una amenaza con nombre.  |
| Actors | Especifique un actor de amenaza con nombre.  |
|||

El filtro predeterminado es mostrar todas las alertas e incidentes con el estado **New** y **In progress** y con una gravedad de **Low**, **Medium** o **High**.

Puede quitar rápidamente un filtro seleccionando la **X** en el nombre de un filtro en la **lista Filtros** . 

## <a name="save-custom-filters-as-urls"></a>Guardar filtros personalizados como direcciones URL

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

Una vez que haya compilado y almacenado la lista de vistas de filtro útiles como direcciones URL, puede usarla para procesar y priorizar rápidamente los incidentes de la cola y administrarlos para su posterior asignación y análisis.[](manage-incidents.md)

## <a name="search-for-incidents"></a>Buscar incidentes

En el **cuadro Buscar nombre o id.** encima de la lista de incidentes, puede escribir el identificador de incidente o el nombre del incidente. Al seleccionar un incidente de la lista de resultados de búsqueda, el portal de Microsoft 365 Defender abre una nueva pestaña con las propiedades del incidente, desde la que puede iniciar la [investigación](investigate-incidents.md).

## <a name="search-for-impacted-assets"></a>Búsqueda de activos afectados

Puedes nombrar un activo&mdash; como un usuario, dispositivo,&mdash; buzón o nombre de aplicación y encontrar todos los incidentes relacionados. 

## <a name="specify-a-time-range"></a>Especificar un intervalo de tiempo

La lista predeterminada de incidentes es para los que se produjeron en los últimos seis meses. Puede especificar un nuevo intervalo de tiempo en el cuadro desplegable situado junto al icono del calendario seleccionando:

 - 1 día
 - 3 días
 - 1 semana
 - 30 días
 - 30 días
 - 6 meses
 - Un intervalo personalizado en el que puede especificar fechas y horas

## <a name="next-steps"></a>Siguientes pasos

Después de determinar qué incidente requiere la prioridad más alta, selecciónelo y:

- [Administrar](manage-incidents.md) las propiedades del incidente para etiquetas, asignación, resolución inmediata de incidentes falsos positivos y comentarios.
- Comience las [investigaciones](investigate-incidents.md).

## <a name="see-also"></a>Consulte también
- [Información general sobre incidentes](incidents-overview.md)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
