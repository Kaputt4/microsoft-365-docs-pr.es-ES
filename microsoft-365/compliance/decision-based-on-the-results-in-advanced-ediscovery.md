---
title: Decisión basada en los resultados de Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Obtenga información sobre cómo la pestaña Decidir en Advanced eDiscovery proporciona datos que pueden ayudarle a determinar el tamaño correcto del conjunto de revisión de archivos de casos.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769155"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>Las decisiones basadas en relevancia se traducen en Advanced eDiscovery
  
En el módulo Relevancia de Advanced eDiscovery, la pestaña Decidir proporciona información adicional para ver y usar estadísticas de compatibilidad con decisiones para determinar el tamaño del conjunto de revisión de archivos de casos.
  
## <a name="using-the-decide-tab"></a>Uso de la pestaña Decidir

![Decisión de relevancia](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Esta pestaña incluye los siguientes componentes:
  
- **Problema:** desde aquí, puede seleccionar el problema de interés de la lista.

- **Relación revisión-recuperación:** comparaciones de Advanced eDiscovery de acuerdo con las puntuaciones de relevancia. El punto de corte del gráfico representa el porcentaje de archivos que se revisarán, asignados a una puntuación de relevancia. Esto se usa en la fase de prueba de relevancia y como umbral de exportación para la selección. El punto de corte predeterminado, para el número de archivos que se va a revisar es en el punto en el que el equilibrio entre Recall y Precision es óptimo. El usuario debe determinar el punto de límite real en función de los objetivos y la negociación de costos (%review) y el riesgo (%recall). Con el control deslizante, puede ajustar el punto de corte y ver el efecto en el gráfico y los parámetros, al ajustar el porcentaje de archivos relevantes que se recuperarán y antes de validar una decisión.

- **Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case. Las definiciones de estos parámetros son las siguientes:

  - **Review**: Percentage of files to review based on this cutoff.

  - **Recall**: Porcentaje de archivos relevantes en el conjunto de revisión.

  - **Siguiente relevante:** costo para revisar e identificar otro archivo relevante que no está actualmente en el conjunto de revisión.

  - **Costo total:** costo para revisar este porcentaje de los archivos de caso. El administrador de casos puede establecer la configuración de parámetros de costo.

  - **Distribución por puntuación de relevancia:** los archivos de la pantalla gris oscuro a la izquierda están por debajo de la puntuación de límite. Una sugerencia de herramienta muestra la puntuación relevancia y el porcentaje relacionado de archivos en el conjunto de archivos de revisión en relación con el total de archivos.

El panel **Detalles expandido** muestra más detalles. Los archivos de las figuras de colección no incluyen archivos vacíos o nebulosos. Las figuras de archivos de familia representan archivos que no se cargan en Relevancia, pero que aún se cuentan como parte de la familia.
