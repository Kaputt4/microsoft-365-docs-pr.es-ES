---
title: Priorizar incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo filtrar incidentes de la cola de incidentes en Microsoft 365 Defender
keywords: incident, queue, overview, devices, identities, users, mailbox, email, incidents, analyze, response, triage
search.product: eADQiWindows 10XVcnh
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4dfb54c5149c83e936c7a4b50a00106df4bba280
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68087045"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft 365 Defender aplica análisis de correlación y agrega alertas relacionadas e investigaciones automatizadas de diferentes productos en un incidente. Microsoft 365 Defender también desencadena alertas únicas sobre actividades que solo se pueden identificar como malintencionadas dada la visibilidad de un extremo a otro en Microsoft 365 Defender tiene en todo el conjunto de productos. Esta vista proporciona a los analistas de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y tratar las amenazas complejas en toda la organización.

La **cola de incidentes** muestra una colección de incidentes que se crearon entre dispositivos, usuarios y buzones. Le ayuda a ordenar los incidentes para priorizar y crear una decisión de respuesta de ciberseguridad informada, un proceso conocido como evaluación de incidentes.

Puede acceder a la cola de **incidentes desde las alertas de Incidentes & > Incidentes** en el inicio rápido del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="La sección Incidente que muestra la cola de incidentes en el portal de Microsoft 365 Defender." lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

En la sección **Incidentes y alertas más recientes** se muestra un gráfico del número de alertas recibidas e incidentes creados en las últimas 24 horas.

De forma predeterminada, la cola de incidentes del portal de Microsoft 365 Defender muestra los incidentes detectados en los últimos seis meses. El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.

La cola de incidentes tiene columnas personalizables (seleccione **Elegir columnas**) que proporcionan visibilidad sobre las distintas características del incidente o las entidades afectadas. Esto le ayuda a tomar una decisión informada con respecto a la priorización de incidentes para su análisis.

Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente.

Por ejemplo: *incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

> [!NOTE]
> Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no tendrán que cambiar su nombre.

La cola de incidentes también proporciona varias opciones de filtrado que, cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en el entorno o decidir centrarse en un escenario o una amenaza específicos. Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata. 

La lista **Filtros** situada encima de la lista de incidentes muestra los filtros aplicados actualmente.

## <a name="available-filters"></a>Filtros disponibles

En la cola de incidentes predeterminada, puede seleccionar **Filtrar** para ver un panel **Filtro** , desde el que se especifica un conjunto filtrado de incidentes. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="El panel Filtros de la cola de incidentes en el portal de Microsoft 365 Defender." lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

También puede ver el panel **Filtro** seleccionando cualquiera de los filtros de la lista **Filtros** situada encima de la lista de incidentes.

En esta tabla se enumeran los nombres de filtro que están disponibles.

| Nombre del filtro | Descripción |
|:-------|:-----|
| Estado | Seleccione **Nuevo**, **En curso** o **Resuelto**. |
| Severity | La gravedad de un incidente indica el impacto que puede tener en los recursos. Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata. Seleccione **Alto**, **Medio**, **Bajo** o **Informativo**. |
| Asignación de incidentes | Seleccione el usuario o los usuarios asignados. |
| Múltiples orígenes del servicio  | Especifique si el filtro es para más de un origen de servicio. |
| Orígenes del servicio  | Especificar incidentes que contengan alertas de: Gobernanza de aplicaciones, Microsoft 365 Defender, Microsoft Defender para Office 365, Microsoft Defender para punto de conexión, Microsoft Defender for Identity, Microsoft Defender for Cloud Apps. |
| Etiquetas | Seleccione uno o varios nombres de etiqueta de la lista. |
| Varias categorías  | Especifique si el filtro es para más de una categoría. |
| Categories | Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos vistos. |
| Entidades | Especifique el nombre de un recurso, como un usuario, dispositivo, buzón o nombre de aplicación. |
| Confidencialidad de datos | Algunos ataques tienen por objetivo extraer datos confidenciales o importantes. Al aplicar un filtro para etiquetas de confidencialidad específicas, puede determinar rápidamente si la información confidencial potencialmente se ha puesto en peligro y dar prioridad a abordar esos incidentes. <br><br> Este filtro solo muestra información cuando se han aplicado [etiquetas de confidencialidad desde Microsoft Purview Information Protection](../../compliance/sensitivity-labels.md). |
| Grupos de dispositivo | Especifique un nombre [de grupo de dispositivos](/windows/security/threat-protection/microsoft-defender-atp/machine-groups) . |
| Plataforma del sistema operativo | Especifique los sistemas operativos del dispositivo. |
| Clasificación | Especifique el conjunto de clasificaciones de las alertas relacionadas. |
| Estado de investigación automatizado | Especifique el estado de la investigación automatizada.  |
| Amenaza asociada | Especifique una amenaza con nombre.  |
| Actors | Especifique un actor de amenaza con nombre.  |
|||

El filtro predeterminado es mostrar todas las alertas e incidentes con un estado **nuevo** y **en curso** y con una gravedad **baja**, **media** o **alta**.

Para quitar rápidamente un filtro, seleccione la **X** en el nombre de un filtro en la lista **Filtros** . 

## <a name="save-custom-filters-as-urls"></a>Guardar filtros personalizados como direcciones URL

Una vez que haya configurado un filtro útil en la cola de incidentes, puede marcar la dirección URL de la pestaña del explorador o guardarla como un vínculo en una página web, un documento de Word o un lugar de su elección. Esto le dará acceso con un solo clic a las vistas clave de la cola de incidentes, como:

- Nuevos incidentes
- Incidentes de gravedad alta
- Incidentes sin asignar
- Incidentes sin asignar de gravedad alta
- Incidentes asignados a mí
- Incidentes asignados a mí y a Microsoft Defender para punto de conexión
- Incidentes con etiquetas o etiquetas específicas
- Incidentes con una categoría de amenaza específica
- Incidentes con una amenaza asociada específica
- Incidentes con un actor específico

Una vez que haya compilado y almacenado la lista de vistas de filtro útiles como direcciones URL, puede usarla para procesar y priorizar rápidamente los incidentes en la cola y [administrarlos](manage-incidents.md) para su asignación y análisis posteriores.

## <a name="search-for-incidents"></a>Búsqueda de incidentes

En el cuadro **Buscar nombre o identificador** situado encima de la lista de incidentes, puede escribir el identificador de incidente o el nombre del incidente. Al seleccionar un incidente de la lista de resultados de búsqueda, el portal de Microsoft 365 Defender abre una nueva pestaña con las propiedades del incidente, desde la que puede iniciar la [investigación](investigate-incidents.md).

## <a name="search-for-impacted-assets"></a>Búsqueda de recursos afectados

Puede asignar un nombre a un recurso&mdash;, como un usuario, un dispositivo, un buzón o un nombre&mdash;de aplicación, y buscar todos los incidentes relacionados. 

## <a name="specify-a-time-range"></a>Especificar un intervalo de tiempo

La lista predeterminada de incidentes es para los que se han producido en los últimos seis meses. Puede especificar un nuevo intervalo de tiempo en el cuadro desplegable situado junto al icono de calendario seleccionando:

 - 1 día
 - 3 días
 - 1 semana
 - 30 días
 - 30 días
 - 6 meses
 - Intervalo personalizado en el que puede especificar fechas y horas

## <a name="next-steps"></a>Pasos siguientes

Después de determinar qué incidente requiere la prioridad más alta, selecciónelo y:

- [Administre](manage-incidents.md) las propiedades del incidente para etiquetas, asignación, resolución inmediata para incidentes falsos positivos y comentarios.
- Comience sus [investigaciones](investigate-incidents.md).

## <a name="see-also"></a>Vea también
- [Información general sobre incidentes](incidents-overview.md)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
