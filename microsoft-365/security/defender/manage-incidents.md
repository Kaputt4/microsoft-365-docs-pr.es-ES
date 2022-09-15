---
title: Administración de incidentes en Microsoft 365 Defender
description: Obtenga información acerca de cómo asignar, actualizar el estado
keywords: incidente, incidentes, análisis, respuesta, alertas, alertas correlacionadas, asignación, actualización, estado, administración, clasificación, microsoft, 365, m365
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
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 09cc82d196110aa1dcf1e6e62e93e5945c9136b1
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67709099"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Administración de incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La administración de incidentes es fundamental para asegurarse de que los incidentes se denominan, asignan y etiquetan para optimizar el tiempo en el flujo de trabajo de incidentes y contener y abordar amenazas más rápidamente.

Puede administrar incidentes desde **alertas de incidentes & > incidentes** en el inicio rápido del portal de Microsoft 365 Defender ([security.microsoft.com](https://security.microsoft.com)). Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Página Incidentes del portal de Microsoft 365 Defender" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

Estas son las maneras de administrar los incidentes:

- [Editar el nombre del incidente](#edit-the-incident-name)
- [Agregar etiquetas de incidente](#add-incident-tags)
- [Asignar el incidente a una cuenta de usuario](#assign-an-incident)
- [Resolverlos](#resolve-an-incident)
- [Especificar su clasificación](#specify-the-classification)
- [Agregar comentarios](#add-comments)

Puede administrar incidentes desde el panel **Administrar incidentes** para un incidente. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="El panel Administrar incidente del portal de Microsoft 365 Defender" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

Puede mostrar este panel desde el vínculo **Administrar incidente** en:

- Panel De propiedades de un incidente en la cola de incidentes.
- **Página resumen** de un incidente.

En los casos en los que quiera mover alertas de un incidente a otro, también puede hacerlo desde la pestaña **Alertas** , creando así un incidente mayor o menor que incluya todas las alertas pertinentes.

## <a name="edit-the-incident-name"></a>Editar el nombre del incidente

Microsoft 365 Defender asigna automáticamente un nombre basado en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente. Por ejemplo: *incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

Puede editar el nombre del incidente desde el campo **Nombre de incidente** en el panel **Administrar incidente** .

> [!NOTE]
> Los incidentes que existían antes del lanzamiento de la característica de nomenclatura automática de incidentes conservarán su nombre.

## <a name="add-incident-tags"></a>Agregar etiquetas de incidente

Puede agregar etiquetas personalizadas a un incidente, por ejemplo, para marcar un grupo de incidencias con características comunes. Posteriormente, puede filtrar la cola de incidentes para todos los incidentes que contengan una etiqueta específica.

Al empezar a escribir, tiene la opción de seleccionar entre una lista de etiquetas usadas y seleccionadas anteriormente.

## <a name="assign-an-incident"></a>Asignación de un incidente

Si aún no se ha asignado un incidente, puede seleccionar el cuadro **Asignar a** y especificar la cuenta de usuario. Para volver a asignar un incidente, quite la cuenta de asignación actual seleccionando la "x" junto al nombre de la cuenta y, a continuación, seleccione el cuadro **Asignar a** . Al asignar la propiedad de un incidente, se asigna la misma propiedad a todas las alertas asociadas a él.

Para obtener una lista de incidentes asignados, filtre la cola de incidentes. 

1. En la cola de incidentes, seleccione **Filtros**.
2. En la sección **Asignación de incidentes** , desactive **Seleccionar todo** y seleccione **Asignado a mí**.
3. Seleccione **Aplicar** y, a continuación, cierre el panel **Filtros** .

A continuación, puede guardar la dirección URL resultante en el explorador como marcador para ver rápidamente la lista de incidentes que se le han asignado.

## <a name="resolve-an-incident"></a>Resolución de un incidente

Si el incidente se ha corregido, seleccione **Resolver incidente** para mover el botón de alternancia a la derecha. Tenga en cuenta que la resolución de un incidente también resuelve todas las alertas vinculadas y activas relacionadas con el incidente.

Un incidente que no se resuelve se muestra como **Activo**.

## <a name="specify-the-classification"></a>Especificar la clasificación

En el campo **Clasificación** , especifique si el incidente es:

- **No establecido** (valor predeterminado).
- **Verdadero positivo** con un tipo de amenaza. Use esta clasificación para incidentes que indiquen con precisión una amenaza real. La especificación del tipo de amenaza ayuda a su equipo de seguridad a ver los patrones de amenaza y a actuar para defender a su organización de ellos.
- **Actividad informativa y esperada** con un tipo de actividad. Use las opciones de esta categoría para clasificar los incidentes de las pruebas de seguridad, la actividad del equipo rojo y el comportamiento inusual esperado de aplicaciones y usuarios de confianza.
- **Los falsos positivos** para los tipos de incidentes que determine se pueden omitir porque son técnicamente inexactos o engañosos.

La clasificación de incidentes y la especificación de su estado y tipo ayuda a ajustar Microsoft 365 Defender para proporcionar una mejor determinación de la detección con el tiempo.

Vea este breve vídeo para aprender a usar la clasificación para aumentar la eficacia de las triajes.  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4LHJq]

## <a name="add-comments"></a>Agregar comentarios

Puede agregar varios comentarios a un incidente con el campo **Comentario** . Cada comentario se agrega a los eventos históricos del incidente. Puede ver los comentarios y el historial de un incidente en el vínculo **Comentarios e historial** de la página **Resumen** .

## <a name="next-steps"></a>Pasos siguientes

Para nuevos incidentes, comience la [investigación](investigate-incidents.md).

Para incidentes en proceso, continúe con la [investigación](investigate-incidents.md).

Para incidentes resueltos, realice una [revisión posterior a los incidentes](first-incident-post.md).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Investigar incidentes](investigate-incidents.md)
