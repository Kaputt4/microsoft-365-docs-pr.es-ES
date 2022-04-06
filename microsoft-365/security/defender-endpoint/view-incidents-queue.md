---
title: Ver y organizar la cola de incidentes
ms.reviewer: ''
description: Consulta la lista de incidentes y aprende a aplicar filtros para limitar la lista y obtener una vista más centrada.
keywords: ver, organizar, incidentes, agregados, investigaciones, cola, ttp
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
ms.openlocfilehash: df5cbf5297a17dafb80a93ed49c7f7d81bc49d68
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474385"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>Ver y organizar la cola de incidentes de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

La **cola Incidentes muestra** una colección de incidentes marcados desde dispositivos de la red. Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada.

De forma predeterminada, la cola muestra incidentes vistos en los últimos 30 días, con el incidente más reciente que aparece en la parte superior de la lista, lo que le ayuda a ver primero los incidentes más recientes.

Hay varias opciones entre las que puede elegir para personalizar la vista de cola Incidentes. 

En la navegación superior puede:
- Personalizar columnas para agregar o quitar columnas 
- Modificar el número de elementos que se verán por página
- Seleccionar los elementos que se mostrarán por página
- Selección por lotes de los incidentes que se asignarán 
- Navegar entre páginas
- Aplicar filtros

:::image type="content" source="images/atp-incident-queue.png" alt-text="La cola incidentes" lightbox="images/atp-incident-queue.png":::

## <a name="sort-and-filter-the-incidents-queue"></a>Ordenar y filtrar la cola de incidentes
Puede aplicar los siguientes filtros para limitar la lista de incidentes y obtener una vista más centrada.

### <a name="severity"></a>Severity

Gravedad del incidente | Descripción
:---|:---
Alto </br>(Rojo) | Amenazas asociadas a menudo con amenazas persistentes avanzadas (APT). Estos incidentes indican un alto riesgo debido a la gravedad de los daños que pueden causar en los dispositivos.
Mediano </br>(Naranja) | Las amenazas rara vez se observan en la organización, como cambios anómalos en el Registro, ejecución de archivos sospechosos y comportamientos observados típicos de fases de ataque.
Bajo </br>(Amarillo) | Amenazas asociadas con malware y herramientas de piratería que no indican necesariamente una amenaza avanzada dirigida a la organización.
Informativo </br>(Gris) | Es posible que los incidentes informativos no se consideren perjudiciales para la red, pero podrían ser buenos para realizar un seguimiento.

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

Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

> [!NOTE]
> Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes conservarán su nombre.


## <a name="see-also"></a>Vea también
- [Cola de incidentes](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)

