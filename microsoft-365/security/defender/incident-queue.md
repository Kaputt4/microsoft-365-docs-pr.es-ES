---
title: Priorizar incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo filtrar incidentes de la cola de incidentes en Microsoft 365 Defender
keywords: incidente, cola, información general, dispositivos, identidades, usuarios, buzón, correo electrónico, incidentes, análisis, respuesta
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
ms.openlocfilehash: 47d066fa20abe963f7afaa3b88cecc96fa6e87fc
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259608"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Priorizar incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft 365 Defender aplica análisis de correlación y agrega alertas relacionadas e investigaciones automatizadas de diferentes productos en un incidente. Microsoft 365 Defender también desencadena alertas únicas en actividades que solo se pueden identificar como malintencionadas dada la visibilidad de un extremo a otro que Microsoft 365 Defender tiene en todo el conjunto de productos. Esta vista ofrece a los analistas de seguridad la historia de ataques más amplia, lo que les ayuda a comprender mejor y tratar las amenazas complejas en toda la organización.

La **cola Incidentes muestra** una colección de incidentes que se crearon en dispositivos, usuarios y buzones. Le ayuda a ordenar los incidentes para asignar prioridades y crear una decisión de respuesta de ciberseguridad fundamentada. 

You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)). Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

La **sección Incidentes y alertas** más recientes muestra un gráfico del número de alertas recibidas e incidentes creados en las últimas 24 horas.

De forma predeterminada, la cola de incidentes del centro Microsoft 365 de seguridad muestra incidentes vistos en los últimos seis meses. El incidente más reciente está en la parte superior de la lista para que pueda verlo primero.

La cola de incidentes tiene columnas personalizables (seleccione **Elegir** columnas) que le dan visibilidad de distintas características del incidente o de las entidades afectadas. Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.

Para obtener visibilidad adicional de un vistazo, la nomenclatura automática de incidentes genera nombres de incidentes basados en atributos de alerta, como el número de puntos de conexión afectados, los usuarios afectados, los orígenes de detección o las categorías. Esto le permite comprender rápidamente el ámbito del incidente.

Por ejemplo: *Incidente de varias fases en varios puntos de conexión notificados por varios orígenes.*

> [!NOTE]
> Los incidentes que existían antes de la implementación de la nomenclatura automática de incidentes no tendrán su nombre cambiado.

La cola de incidentes también expone varias opciones de filtrado que, cuando se aplican, le permiten realizar un amplio barrido de todos los incidentes existentes en su entorno o decidir centrarse en un escenario o amenaza específicos. Aplicar filtros en la cola de incidentes puede ayudar a determinar qué incidente requiere atención inmediata. 

## <a name="available-filters"></a>Filtros disponibles

En la cola de incidentes  predeterminada, puede seleccionar Filtros para ver un panel Filtros, desde el que puede ver un conjunto filtrado de incidentes. Aquí le mostramos un ejemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Ejemplo del panel de filtros de la cola de incidentes":::

En esta tabla se enumeran los nombres de filtro disponibles.

| Nombre del filtro | Descripción |
|:-------|:-----|
| Asignado a | Puede elegir mostrar las alertas que se le han asignado o las que controla la automatización. |
| Categorías | Elija categorías para centrarse en tácticas, técnicas o componentes de ataque específicos vistos. |
| Clasificación | Filtrar incidentes en función de las clasificaciones establecidas de las alertas relacionadas. Los valores incluyen alertas verdaderas, alertas falsas o no establecidas. |
| Confidencialidad de datos | Algunos ataques tienen por objetivo extraer datos confidenciales o importantes. Al aplicar un filtro para ver si hay datos confidenciales implicados en el incidente, puede determinar rápidamente si la información confidencial se ha visto comprometida y así dar prioridad a estos incidentes. <br><br> Solo se aplica si se ha activado Microsoft Information Protection. |
| Grupo de dispositivos | Filtrar por grupos de dispositivos definidos. |
| Estado de investigación | Filtrar incidentes por el estado de la investigación automatizada.  |
| Varias categorías | Puede elegir ver solo incidentes que se han asignado a varias categorías y, por lo tanto, puede causar más daños. |
| Múltiples orígenes del servicio  | Filtra para ver solo incidentes que contienen alertas de diferentes orígenes (Microsoft Defender para endpoint, Microsoft Cloud App Security, Microsoft Defender para Identity, Microsoft Defender para Office 365). |
| Plataforma del sistema operativo | Limitar la vista de cola de incidentes por sistema operativo. |
| Orígenes del servicio | Al elegir un origen específico, puede concentrarse en los incidentes que contienen al menos una alerta del origen seleccionado. |
| Gravedad | La gravedad de un incidente indica el impacto que puede tener en los activos. Cuanto mayor sea la gravedad, mayor será el impacto y, por lo general, se requiere la atención más inmediata. |
| Estado | Puede limitar la lista de incidentes que se muestra en función de su estado para ver cuáles están activos o resueltos. |
|||

## <a name="next-step"></a>Paso siguiente

Después de determinar qué incidente requiere la prioridad más alta, selecciónelo e inicie el [análisis](investigate-incidents.md).

## <a name="see-also"></a>Vea también
- [Información general sobre incidentes](incidents-overview.md)
- [Analizar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
