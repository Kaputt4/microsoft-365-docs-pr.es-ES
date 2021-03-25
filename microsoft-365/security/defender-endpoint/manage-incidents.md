---
title: Administrar incidentes de ATP de Microsoft Defender
description: Administre los incidentes asignándolas, actualizando su estado o estableciendo su clasificación.
keywords: incidentes, administrar, asignar, estado, clasificación, alerta verdadera, alerta falsa
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b8b5e806d09f08a12c090a1055f2c165f25b7ea1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185820"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>Administrar Microsoft Defender para incidentes de punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

La administración de incidentes es una parte importante de todas las operaciones de ciberseguridad. Puede administrar incidentes seleccionando un incidente en la cola Incidentes **o** en el panel de **administración incidentes.** 


Al seleccionar un incidente de la cola **Incidentes,** se abre el panel **Administración** de incidentes, donde puede abrir la página de incidentes para obtener más información.


![Imagen del panel de administración de incidentes](images/atp-incidents-mgt-pane-updated.png)

Puedes asignar incidentes a ti mismo, cambiar el estado y la clasificación, cambiar el nombre o comentarlos para realizar un seguimiento de su progreso.

> [!TIP]
> Para obtener visibilidad adicional de un vistazo, los nombres de incidentes se generan automáticamente en función de los atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente.
>
> Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*
>
> Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes conservarán sus nombres.
>


![Imagen de la página de detalles de incidentes](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a>Asignar incidentes
Si aún no se ha asignado un incidente, puedes seleccionar **Asignarme** para asignarte el incidente. Esta asignación no incluye solo el incidente, sino también todas las alertas asociadas a él.

## <a name="set-status-and-classification"></a>Establecer estado y clasificación
### <a name="incident-status"></a>Estado del incidente
Puede categorizar los incidentes (por ejemplo, como **Activo** o **Resuelto**) cambiando su estado a medida que progresa la investigación. Esto le ayuda a organizar y administrar la forma en que su equipo puede responder a incidencias.

Por ejemplo, el analista de SoC puede revisar los incidentes **activos** urgentes del día y decidir asignarlos a sí mismo para su investigación.

Como alternativa, el analista de SoC puede establecer el incidente como **Resuelto** si se ha corregido el incidente. 

### <a name="classification"></a>Clasificación
Si lo desea, puede decidir no establecer ninguna clasificación o especificar si un incidente es verdadero o falso. Al hacerlo, su equipo podrá ver los patrones y obtener información.

### <a name="add-comments"></a>Agregar comentarios
Puede agregar comentarios y ver eventos históricos de un incidente para comprobar los cambios ya realizados.

Siempre que se realice un cambio o comentario en una alerta, esta se registra en la sección Comentarios e historial.

Los comentarios agregados aparecen al instante en el panel.



## <a name="related-topics"></a>Temas relacionados
- [Cola de incidentes](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Ver y organizar la cola incidentes](view-incidents-queue.md)
- [Investigar incidentes](investigate-incidents.md)
