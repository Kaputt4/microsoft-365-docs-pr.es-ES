---
title: Priorizar incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo filtrar incidentes de la cola de incidentes en Microsoft 365 Defender
keywords: incidente, cola, información general, dispositivos, identidades, usuarios, buzón, correo electrónico, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929299"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender



Microsoft 365 Defender aplica análisis de correlación y agrega todas las alertas e investigaciones relacionadas de diferentes productos en un incidente. Microsoft 365 Defender también activa alertas únicas en actividades que solo se pueden identificar como malintencionadas dada la visibilidad de un extremo a otro que Microsoft 365 Defender tiene en toda la propiedad y conjunto de productos. Esta vista ofrece a su analista de operaciones de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y enfrentarse a amenazas complejas en toda la organización.


La **cola de incidentes** muestra un conjunto de incidentes que se han marcado desde diferentes dispositivos, usuarios y buzones de correo. Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.


![Imagen de cola de incidentes](../../media/incidents-queue.png) 

De forma predeterminada, la cola del Centro de seguridad de Microsoft 365 muestra los incidentes vistos en los últimos 30 días. El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.

La cola de incidentes expone columnas personalizables que le dan visibilidad de las diferentes características del incidente o las entidades contenidas. Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes que se deben controlar.

Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente.

Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

> [!NOTE]
> Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no cambiarán su nombre.

La cola de incidentes también expone varias opciones de filtrado que, cuando se aplican, le permiten realizar un barrido general de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos. Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata. 

## <a name="available-filters"></a>Filtros disponibles

### <a name="assigned-to"></a>Asignado a
Puedes elegir mostrar alertas asignadas a ti o aquellas que se controlan mediante automatización.

### <a name="categories"></a>Categorías
Elige categorías para centrarte en tácticas, técnicas o componentes de ataque específicos que se ven. 

### <a name="classification"></a>Clasificación
Filtrar incidentes en función de las clasificaciones establecidas de las alertas relacionadas. Los valores incluyen alertas verdaderas, alertas falsas o no establecidas.

### <a name="data-sensitivity"></a>Confidencialidad de datos
Algunos ataques tienen por objetivo extraer datos confidenciales o importantes. Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes.

>[!NOTE]
>Solo se aplica si se ha activado Microsoft Information Protection. 

### <a name="device-group"></a>Grupo de dispositivos
Filtra por grupos de dispositivos definidos.

### <a name="investigation-state"></a>Estado de investigación
Filtrar incidentes por el estado de la investigación automatizada. 

### <a name="multiple-categories"></a>Varias categorías 
Puede elegir ver solo los incidentes que se han asignado a varias categorías y, por lo tanto, pueden causar más daños. 

### <a name="multiple-service-sources"></a>Múltiples orígenes del servicio 
Filtra para ver solo los incidentes que contienen alertas de diferentes orígenes (Microsoft Defender para Endpoint, Microsoft Cloud App Security, Microsoft Defender para Identity, Microsoft Defender para Office 365).

### <a name="os-platform"></a>Plataforma del sistema operativo
Limitar la vista de cola de incidentes por sistema operativo.

### <a name="service-sources"></a>Orígenes del servicio
Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado. 

### <a name="severity"></a>Severity
La gravedad de un incidente indica el impacto que puede tener en los activos. Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata. 

### <a name="status"></a>Estado
Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.




## <a name="next-steps"></a>Siguientes pasos
Una vez que haya determinado qué incidente tiene mayor prioridad, puede seguir investigando.
- [Investigar incidentes](investigate-incidents.md)


## <a name="see-also"></a>Vea también
- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
