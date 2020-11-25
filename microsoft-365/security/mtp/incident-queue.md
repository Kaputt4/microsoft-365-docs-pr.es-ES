---
title: Priorizar incidentes en Microsoft 365 defender
description: Obtenga información sobre cómo filtrar incidentes de la cola de incidentes en Microsoft 365 defender
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
ms.openlocfilehash: e587004fbb3bc6defab985cea9b427f64b3aab35
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409260"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes en Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender



Microsoft 365 defender aplica análisis de correlación y agrega todas las alertas y investigaciones relacionadas de distintos productos en un incidente. Microsoft 365 defender también desencadena alertas únicas en actividades que solo se pueden identificar como malintencionadas dado la visibilidad de un extremo a otro que Microsoft 365 defender tiene en toda la población y en el conjunto de productos. Esta vista ofrece a los analistas de operaciones de seguridad la experiencia de ataque más amplia, lo que les ayuda a comprender mejor y tratar amenazas complejas en toda la organización.


La **cola de incidentes** muestra un conjunto de incidentes que se han marcado desde diferentes dispositivos, usuarios y buzones de correo. Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.


![Imagen de cola de incidentes](../../media/incidents-queue.png) 

De forma predeterminada, la cola del centro de seguridad 365 de Microsoft muestra los incidentes que se han visto en los últimos 30 días. El incidente más reciente se encuentra en la parte superior de la lista, por lo que puede verlo primero.

La cola de incidentes expone columnas personalizables que le proporcionan visibilidad en diferentes características del incidente o las entidades que contiene. Esto le ayudará a tomar una decisión informada sobre la priorización de incidentes para controlar.

Para obtener más visibilidad de un vistazo, la denominación automática de incidentes genera nombres de incidente en función de atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente.

Por ejemplo: *incidente de varias fases en varios puntos de conexión que han sido notificados por varios orígenes.*

> [!NOTE]
> Los incidentes que existían antes de la implementación de la asignación automática de nombres de incidentes no tendrán su nombre cambiado.

La cola de incidentes también expone varias opciones de filtrado, que cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos. Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata. 

## <a name="available-filters"></a>Filtros disponibles

### <a name="assigned-to"></a>Asignado a
Puede elegir mostrar las alertas que están asignadas a usted o a las administradas por automatización.

### <a name="categories"></a>Categorías
Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos que se ven. 

### <a name="classification"></a>Clasificación
Filtre las incidencias según las clasificaciones establecidas de las alertas relacionadas. Los valores incluyen alertas verdaderas, falsas alertas o no establecidas.

### <a name="data-sensitivity"></a>Confidencialidad de datos
Algunos ataques tienen por objetivo extraer datos confidenciales o importantes. Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes.

>[!NOTE]
>Solo se aplica si se ha activado Microsoft Information Protection. 

### <a name="device-group"></a>Grupo de dispositivos
Filtra por grupos de dispositivos definidos.

### <a name="investigation-state"></a>Estado de investigación
Filtrar incidentes por el estado de la investigación automatizada. 

### <a name="multiple-categories"></a>Varias categorías 
Puede elegir ver solo los incidentes que se han asignado a varias categorías y, por lo tanto, puede causar más daño. 

### <a name="multiple-service-sources"></a>Múltiples orígenes del servicio 
Filtrar solo para ver incidentes que contengan alertas de diferentes orígenes (Microsoft defender para extremo, Microsoft Cloud App Security, Microsoft defender para identidad, Microsoft defender para Office 365).

### <a name="os-platform"></a>Plataforma de sistema operativo
Limitar la vista de cola de incidentes por sistema operativo.

### <a name="service-sources"></a>Orígenes del servicio
Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado. 

### <a name="severity"></a>Severity
La gravedad de un incidente indica el impacto que puede tener en los activos. Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requerirá la atención más inmediata. 

### <a name="status"></a>Estado
Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.




## <a name="next-steps"></a>Siguientes pasos
Una vez que haya determinado qué incidente tiene mayor prioridad, puede seguir investigando.
- [Investigar incidentes](investigate-incidents.md)


## <a name="see-also"></a>Consulte también
- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
