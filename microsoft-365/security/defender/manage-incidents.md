---
title: Administrar incidentes en Microsoft 365 Defender
description: Obtenga información acerca de cómo asignar, actualizar el estado
keywords: incidente, incidentes, análisis, respuesta, alertas, alertas correlacionadas, asignar, actualizar, estado, administrar, clasificación, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 9cb3cc67c3992773897ea8178f261d25dcd87da0
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594160"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Administrar incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La administración de incidentes es fundamental para garantizar que las amenazas se contengan y se aborde.

Puede administrar incidentes de **incidentes & alertas > incidentes en** el inicio rápido del centro de seguridad de Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)). Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

Estas son las formas en que puede administrar sus incidentes:

- [Editar el nombre del incidente](#edit-the-incident-name)
- [Agregar etiquetas de incidente](#add-incident-tags)
- [Asignar el incidente a usted mismo](#assign-incidents)
- [Resolverlos](#resolve-an-incident)
- [Establecer su clasificación y determinación](#set-the-classification-and-determination)
- [Agregar comentarios](#add-comments)

Puede administrar incidentes desde el panel **Administrar incidentes** para un incidente. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Ejemplo del panel Administrar incidentes de un incidente":::

Puede mostrar este panel desde el vínculo **Administrar incidentes** en:

- Panel de propiedades de un incidente en la cola de incidentes.
- **Página de** resumen de un incidente.

En los casos en los que quiera mover alertas de  un incidente a otro, también puede hacerlo desde la pestaña Alertas, creando así un incidente más grande o más pequeño que incluya todas las alertas relevantes.

## <a name="edit-the-incident-name"></a>Editar el nombre del incidente

Microsoft 365 Defender asigna automáticamente un nombre en función de los atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente. Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

Puede editar el nombre del incidente desde el campo **Nombre del** incidente en el **panel Administrar** incidente.

> [!NOTE]
> Los incidentes que existían antes de la implementación de la característica de nomenclatura automática de incidentes conservarán su nombre.

## <a name="add-incident-tags"></a>Agregar etiquetas de incidente

Puede agregar etiquetas personalizadas a un incidente, por ejemplo, para marcar un grupo de incidentes con una característica común. Más adelante, puede filtrar la cola de incidentes para todos los incidentes que contengan una etiqueta específica.

Al empezar a escribir, tiene la opción de seleccionar de una lista de etiquetas seleccionadas.

## <a name="assign-incidents"></a>Asignar incidentes

Para asignar un incidente, seleccione **Asignarme**. Al hacerlo, se asigna la propiedad del incidente y todas las alertas asociadas a ella a su cuenta de usuario.

Puede obtener una lista de incidentes asignados filtrando la cola de incidentes. 

1. En la cola de incidentes, seleccione **Filtros**.
2. en la **sección Asignación de** incidentes, desactive **Seleccionar todo** y seleccione Asignado **a mí**.
3. Seleccione **Aplicar** y, a continuación, cierre el **panel** Filtros.

A continuación, puede guardar la dirección URL resultante en el explorador como marcador para ver rápidamente la lista de incidentes asignados.

## <a name="resolve-an-incident"></a>Resolver un incidente

Si el incidente se ha corregido, seleccione **Resolver incidente** para mover la alternancia a la derecha. Tenga en cuenta que la resolución de un incidente también resuelve todas las alertas vinculadas y activas relacionadas con el incidente.

Un incidente que no se resuelve se muestra como **Activo**.

## <a name="set-the-classification-and-determination"></a>Establecer la clasificación y la determinación

La clasificación de incidentes es si se trata de una alerta verdadera o una alerta falsa, que se configura desde el **campo Clasificación.** 

Si se trataba de una alerta verdadera, también debe especificar qué tipo de amenaza era con el **campo Determinación.** Especificar el tipo de amenaza ayuda a su equipo de seguridad a ver patrones de amenazas y actuar para defender su organización de ellos. 

## <a name="add-comments"></a>Agregar comentarios

Puede agregar varios comentarios a un incidente con el **campo Comentario.** Cada comentario se agrega a los eventos históricos del incidente. Puede ver los comentarios y el historial de un incidente desde el vínculo **Comentarios e** historial en la **página Resumen.**

## <a name="next-steps"></a>Pasos siguientes

Para nuevos incidentes, inicie la [investigación](investigate-incidents.md).

Para incidentes en el proceso, continúe con la [investigación](investigate-incidents.md).

Para los incidentes resueltos, realice una [revisión posterior al incidente](first-incident-post.md).

## <a name="see-also"></a>Consulte también

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Investigar incidentes](investigate-incidents.md)
