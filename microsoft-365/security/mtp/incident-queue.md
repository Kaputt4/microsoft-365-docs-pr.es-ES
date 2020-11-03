---
title: Priorizar incidentes en Microsoft 365 defender
description: Obtenga información sobre cómo priorizar incidentes de la cola de incidentes en Microsoft 365 defender
keywords: incidente, cola, información general, dispositivos, identidades, usuarios, buzón, correo electrónico, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f681d02cc4af8bd56ba945a3d944798e545bf93c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846717"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes en Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender



Microsoft 365 defender aplica análisis de correlación y agrega todas las alertas y investigaciones relacionadas de distintos productos en un incidente. Microsoft 365 defender también desencadena alertas únicas en actividades que solo se pueden identificar como malintencionadas dado la visibilidad de un extremo a otro que Microsoft 365 defender tiene en toda la población y en el conjunto de productos. Al hacerlo, Microsoft 365 defender narra la historia de ataque más amplio, lo que permite a un analista de operaciones de seguridad comprender y tratar amenazas complejas en toda la organización.


La **cola de incidentes** muestra un conjunto de incidentes que se han marcado desde diferentes dispositivos, usuarios y buzones de correo. Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.


![Imagen de cola de incidentes](../../media/incidents-queue.png) 

De manera predeterminada, la cola del Centro de seguridad de Microsoft 365 muestra los incidentes encontrados en los últimos 30 días, con el incidente más reciente en la parte superior de la lista, ayudándole así a ver primero los incidentes más recientes.

La cola de incidentes expone columnas personalizables donde podrá ver las distintas características del incidente o de las entidades que contiene, lo que le permite tomar decisiones fundamentadas sobre la priorización de incidentes que debe controlar.

Para obtener más visibilidad de un vistazo, la denominación automática de incidentes genera nombres de incidente en función de atributos de alerta como el número de puntos de conexión afectados, los usuarios afectados, las fuentes o categorías de detección. Esto le permite comprender rápidamente el ámbito del incidente.

Por ejemplo: *incidente de varias fases en varios puntos de conexión que han sido notificados por varios orígenes.*

> [!NOTE]
> Los incidentes que existían antes de la implementación de la asignación automática de nombres de incidentes no tendrán su nombre cambiado.

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
Filtrar solo para ver incidentes que contienen alertas de diferentes orígenes (Microsoft defender para el extremo, Microsoft Cloud App Security, Microsoft defender para identidad, Microsoft defender para Office 365)
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
