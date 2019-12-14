---
title: Priorizar incidentes con la Protección contra amenazas de Microsoft
description: Obtenga información acerca de cómo priorizar los incidentes de la cola de incidentes con la Protección contra amenazas de Microsoft
keywords: incidente, cola, información general, dispositivos, identidades, usuarios, buzón, correo electrónico, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 0c4231fa6284d967bcc49e4d46b0869c57733443
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911637"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>Priorizar incidentes con la Protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!include[Prerelease information](prerelease.md)]

La Protección contra amenazas de Microsoft aplica análisis de correlación y agrega todas las alertas y las investigaciones relacionadas de diferentes productos en un incidente. La Protección contra amenazas de Microsoft también activa alertas exclusivas en actividades que solo se pueden identificar como malintencionadas, y esto es posible gracias a que la Protección contra amenazas de Microsoft tiene visibilidad de un extremo a otro en todo el conjunto de productos de Microsoft. Al hacerlo, la Protección contra amenazas de Microsoft narra una historia más amplia del ataque, lo que permite que el analista de operaciones de seguridad entienda y se ocupe de las amenazas complejas en toda la organización.


La **cola de incidentes** muestra un conjunto de incidentes que se han marcado desde diferentes dispositivos, usuarios y buzones de correo. Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.


![Imagen de cola de incidentes](../images/incidents-queue.png) 

De manera predeterminada, la cola del Centro de seguridad de Microsoft 365 muestra los incidentes encontrados en los últimos 30 días, con el incidente más reciente en la parte superior de la lista, ayudándole así a ver primero los incidentes más recientes.

La cola de incidentes expone columnas personalizables donde podrá ver las distintas características del incidente o de las entidades que contiene, lo que le permite tomar decisiones fundamentadas sobre la priorización de incidentes que debe controlar. 

La cola de incidentes también muestra opciones de filtrado que, al aplicarlas, le permiten decidir si limpiar todos los incidentes existentes en su entorno o enfocarse en un escenario o amenaza específica. Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata. 

## <a name="available-filters"></a>Filtros disponibles

### <a name="status"></a>Estado
Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.

### <a name="severity"></a>Gravedad
La gravedad de un incidente indica el impacto que puede tener en sus activos. Cuanto mayor sea el nivel de gravedad, mayor será el impacto y, por lo general, requerirá atención más inmediata. 

### <a name="assigned-to-owner"></a>Asignado a (propietario)
Puede filtrar la lista seleccionando los incidentes asignados a cualquiera o solo los asignados a su usuario.

### <a name="multiple-alerts"></a>Más de una alerta 
Filtre para ver solo los incidentes que contienen más de una alerta. Esto podría ser una indicación para un ataque que es más complejo o que progresa en la cadena de eliminación. 


### <a name="multiple-service-sources"></a>Múltiples orígenes del servicio 
Filtre solo para ver los incidentes que contienen alertas de orígenes diferentes (ATP de Microsoft Defender, Microsoft Cloud App Security, Azure ATP, ATP de Office 365)
### <a name="service-sources"></a>Orígenes del servicio
Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado. 

### <a name="multiple-categories"></a>Varias categorías 
Puede elegir ver solo los incidentes que se han asignado a varias categorías de la cadena de eliminación y que pueden provocar más daño. 

### <a name="categories"></a>Categorías
Elija categorías específicas para concentrarse en un paso específico de la cadena de eliminación

### <a name="data-sensitivity"></a>Confidencialidad de datos
Algunos ataques tienen por objetivo extraer datos confidenciales o importantes. Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes.

>[!NOTE]
>Solo se aplica si se ha activado Microsoft Information Protection. 


## <a name="next-steps"></a>Siguientes pasos
Una vez que haya determinado qué incidente tiene mayor prioridad, puede seguir investigando.
- [Investigar incidentes](investigate-incidents.md)


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)