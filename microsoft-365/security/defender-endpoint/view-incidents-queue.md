---
title: Ver y organizar la cola de incidentes
ms.reviewer: ''
description: Consulte la lista de incidentes y obtenga información sobre cómo aplicar filtros para limitar la lista y obtener una vista más centrada.
keywords: ver, organizar, incidentes, agregado, investigaciones, cola, ttp
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a2d75b935c19a20c37ecdbdb77feff73bbed4a79
ms.sourcegitcommit: 9fdb5c5b9eaf0c8a8d62b579a5fb5a5dc2d29fa9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2022
ms.locfileid: "66714649"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>Ver y organizar la cola de incidentes de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

La **cola Incidentes** muestra una colección de incidentes marcados desde dispositivos de la red. Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.

De forma predeterminada, la cola muestra los incidentes vistos en los últimos 30 días, con el incidente más reciente en la parte superior de la lista, lo que le ayuda a ver primero los incidentes más recientes.

Hay varias opciones entre las que puede elegir para personalizar la vista de cola incidentes. 

En la navegación superior, puede hacer lo siguiente:
- Personalización de columnas para agregar o quitar columnas 
- Modificar el número de elementos que se van a ver por página
- Seleccionar los elementos que se van a mostrar por página
- Seleccione por lotes los incidentes que se van a asignar. 
- Navegar entre páginas
- Aplicar filtros
- Personalización y aplicación de intervalos de fechas

:::image type="content" source="images/atp-incident-queue.png" alt-text="Cola de incidentes" lightbox="images/atp-incident-queue.png":::

## <a name="sort-and-filter-the-incidents-queue"></a>Ordenar y filtrar la cola de incidentes
Puede aplicar los filtros siguientes para limitar la lista de incidentes y obtener una vista más centrada.

### <a name="severity"></a>Severity

Gravedad del incidente | Descripción
:---|:---
Alto </br>(Rojo) | Las amenazas a menudo asociadas a amenazas persistentes avanzadas (APT). Estos incidentes indican un alto riesgo debido a la gravedad de los daños que pueden infligir en los dispositivos.
Medio </br>(Naranja) | Las amenazas rara vez observadas en la organización, como el cambio anómalo del Registro, la ejecución de archivos sospechosos y los comportamientos observados típicos de las fases de ataque.
Bajo </br>(Amarillo) | Amenazas asociadas con malware frecuente y herramientas de hack que no indican necesariamente una amenaza avanzada destinada a la organización.
Informativo </br>(Gris) | Es posible que los incidentes informativos no se consideren dañinos para la red, pero podrían ser buenos para realizar un seguimiento de ellos.

## <a name="assigned-to"></a>Asignado a
Puede filtrar la lista seleccionando los incidentes asignados a cualquiera o solo los asignados a su usuario.

### <a name="category"></a>Categoría
Los incidentes se clasifican en función de la descripción de la fase en la que se encuentra la cadena de eliminación de ciberseguridad. Esta vista ayuda al analista de amenazas a determinar la prioridad, la urgencia y la estrategia de respuesta correspondiente para implementar en función del contexto.

### <a name="status"></a>Estado
Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos.

### <a name="data-sensitivity"></a>Confidencialidad de datos
Use este filtro para mostrar incidentes que contienen etiquetas de confidencialidad.

## <a name="incident-naming"></a>Nomenclatura de incidentes

Para comprender el ámbito del incidente de un vistazo, los nombres de incidentes se generan automáticamente en función de los atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías.

Por ejemplo: *incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

> [!NOTE]
> Los incidentes que existían antes del lanzamiento de la nomenclatura automática de incidentes conservarán su nombre.


## <a name="see-also"></a>Vea también
- [Cola de incidentes](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)

