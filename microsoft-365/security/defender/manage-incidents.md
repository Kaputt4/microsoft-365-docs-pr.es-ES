---
title: Administrar incidentes en Microsoft 365 Defender
description: Obtenga información acerca de cómo asignar, actualizar el estado
keywords: incidente, incidentes, análisis, respuesta, alertas, alertas correlacionadas, asignar, actualizar, estado, administrar, clasificación, microsoft, 365, m365
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 14332b2787b59e2ef192741dc97e59a7c7cb5418
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499515"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Administrar incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La administración de incidentes es fundamental para garantizar que los incidentes se nombren, asignen y etiqueten para optimizar el tiempo en el flujo de trabajo de incidentes y contener y solucionar más rápidamente las amenazas.

Puede administrar incidentes desde incidentes & **alertas > incidentes** en el inicio rápido del portal de Microsoft 365 Defender ([security.microsoft.com](https://security.microsoft.com)). Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="La página Incidentes del portal de Microsoft 365 Defender web" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

Estas son las formas en que puede administrar sus incidentes:

- [Editar el nombre del incidente](#edit-the-incident-name)
- [Agregar etiquetas de incidentes](#add-incident-tags)
- [Asignar el incidente a una cuenta de usuario](#assign-an-incident)
- [Resolverlos](#resolve-an-incident)
- [Especificar su clasificación](#specify-the-classification)
- [Agregar comentarios](#add-comments)

Puede administrar incidentes desde el panel **Administrar incidentes** para un incidente. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="El panel Administrar incidentes en el Microsoft 365 Defender web" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

Puede mostrar este panel desde el vínculo **Administrar incidentes** en:

- Panel de propiedades de un incidente en la cola de incidentes.
- **Página de** resumen de un incidente.

En los casos en los que quiera mover alertas de un incidente a otro, también puede hacerlo desde  la pestaña Alertas, creando así un incidente más grande o más pequeño que incluya todas las alertas relevantes.

## <a name="edit-the-incident-name"></a>Editar el nombre del incidente

Microsoft 365 Defender asigna automáticamente un nombre en función de los atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente. Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

Puede editar el nombre del incidente desde el campo **Nombre del** incidente en el **panel Administrar** incidente.

> [!NOTE]
> Los incidentes que existían antes de la implementación de la característica de nomenclatura automática de incidentes conservarán su nombre.

## <a name="add-incident-tags"></a>Agregar etiquetas de incidente

Puede agregar etiquetas personalizadas a un incidente, por ejemplo, para marcar un grupo de incidencias con características comunes. Posteriormente, puede filtrar la cola de incidentes para todos los incidentes que contengan una etiqueta específica.

Al empezar a escribir, tiene la opción de seleccionar de una lista de etiquetas usadas previamente y seleccionadas.

## <a name="assign-an-incident"></a>Asignar un incidente

Si aún no se ha asignado un incidente, puede seleccionar el cuadro Asignar **a** y especificar la cuenta de usuario. Para volver a asignar un incidente, quite la cuenta de asignación actual seleccionando la "x" junto al nombre de la cuenta y, a continuación, seleccione el cuadro Asignar **a** . Al asignar la propiedad de un incidente, se asigna la misma propiedad a todas las alertas asociadas.

Puede obtener una lista de incidentes asignados filtrando la cola de incidentes. 

1. En la cola de incidentes, seleccione **Filtros**.
2. en la **sección Asignación de** incidentes, desactive **Seleccionar todo** y seleccione **Asignado a mí**.
3. Seleccione **Aplicar** y, a continuación, cierre el **panel** Filtros.

A continuación, puede guardar la dirección URL resultante en el explorador como marcador para ver rápidamente la lista de incidentes asignados.

## <a name="resolve-an-incident"></a>Resolver un incidente

Si el incidente se ha corregido, seleccione **Resolver incidente** para mover la alternancia a la derecha. Tenga en cuenta que la resolución de un incidente también resuelve todas las alertas vinculadas y activas relacionadas con el incidente.

Un incidente que no se resuelve se muestra como **Activo**.

## <a name="specify-the-classification"></a>Especificar la clasificación

En el **campo** Clasificación, se especifica si el incidente es:

- **No se establece** (el valor predeterminado).
- **Verdadero positivo** con un tipo de amenaza. Use esta clasificación para incidentes que indiquen con precisión una amenaza real. La especificación del tipo de amenaza ayuda a su equipo de seguridad a ver los patrones de amenaza y a actuar para defender a su organización de ellos.
- **Actividad informativo y esperada** con un tipo de actividad. Usa las opciones de esta categoría para clasificar incidentes para pruebas de seguridad, actividad roja del equipo y comportamiento inusual esperado de usuarios y aplicaciones de confianza.
- **Falso positivo** para tipos de incidentes que determine que se pueden ignorar porque son técnicamente inexactos o engañosos.

Clasificar incidentes y especificar su estado y tipo ayuda a ajustar los Microsoft 365 Defender para proporcionar una mejor determinación de detección con el tiempo.

## <a name="add-comments"></a>Agregar comentarios

Puede agregar varios comentarios a un incidente con el **campo Comentario** . Cada comentario se agrega a los eventos históricos del incidente. Puede ver los comentarios y el historial de un incidente desde el vínculo **Comentarios e** historial en la **página Resumen** .

## <a name="next-steps"></a>Pasos siguientes

Para nuevos incidentes, comience la [investigación](investigate-incidents.md).

Para incidentes en proceso, continúe con la [investigación](investigate-incidents.md).

Para los incidentes resueltos, realice una [revisión posterior al incidente](first-incident-post.md).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Investigar incidentes](investigate-incidents.md)
