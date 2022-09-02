---
title: Administración de incidentes Microsoft Defender para punto de conexión
description: Administre los incidentes asignándolo, actualizando su estado o estableciendo su clasificación.
keywords: incidentes, administrar, asignar, estado, clasificación, alerta verdadera, alerta falsa
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 289f784bc36dcb1b17ec77fff39714ceceadd704
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521529"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>Administración de incidentes Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

La administración de incidentes es una parte importante de cada operación de ciberseguridad. Para administrar los incidentes, seleccione un incidente en la **cola Incidentes** o en el **panel Administración de incidentes**. 


Al seleccionar un incidente en la **cola Incidentes** , se abre el **panel Administración de incidentes** , donde puede abrir la página del incidente para obtener más información.

:::image type="content" source="images/atp-incidents-mgt-pane-updated.png" alt-text="Panel de administración de incidentes" lightbox="images/atp-incidents-mgt-pane-updated.png":::

Puede asignar incidentes a sí mismo, cambiar el estado y la clasificación, cambiar el nombre o comentarlos para realizar un seguimiento de su progreso.

> [!TIP]
> Para obtener visibilidad adicional de un vistazo, los nombres de incidentes se generan automáticamente en función de los atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente.
>
> Por ejemplo: *incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*
>
> Los incidentes que existían antes del lanzamiento de la nomenclatura automática de incidentes conservarán sus nombres.
>

:::image type="content" source="images/atp-incident-details-updated.png" alt-text="Página de detalles del incidente" lightbox="images/atp-incident-details-updated.png":::

## <a name="assign-incidents"></a>Asignar incidentes
Si aún no se ha asignado un incidente, puede seleccionar **Asignarme** para asignar el incidente a sí mismo. Esta asignación no incluye solo el incidente, sino también todas las alertas asociadas a él.

## <a name="set-status-and-classification"></a>Establecer estado y clasificación
### <a name="incident-status"></a>Estado del incidente
Puede categorizar los incidentes (por ejemplo, como **Activo** o **Resuelto**) cambiando su estado a medida que progresa la investigación. Esto le ayuda a organizar y administrar la forma en que su equipo puede responder a incidencias.

Por ejemplo, el analista de SoC puede revisar los incidentes **activos** urgentes del día y decidir asignarlos a sí mismo para su investigación.

Como alternativa, el analista de SoC podría establecer el incidente como **Resuelto** si el incidente se ha corregido. 

### <a name="classification"></a>Clasificación
Si lo desea, puede decidir no establecer ninguna clasificación o especificar si un incidente es verdadero o falso. Al hacerlo, su equipo podrá ver los patrones y obtener información.

### <a name="add-comments"></a>Agregar comentarios
Puede agregar comentarios y ver eventos históricos de un incidente para comprobar los cambios ya realizados.

Siempre que se realice un cambio o comentario en una alerta, esta se registra en la sección Comentarios e historial.

Los comentarios agregados aparecen al instante en el panel.



## <a name="related-topics"></a>Temas relacionados
- [Cola de incidentes](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Ver y organizar la cola de incidentes](view-incidents-queue.md)
- [Investigar incidentes](investigate-incidents.md)
