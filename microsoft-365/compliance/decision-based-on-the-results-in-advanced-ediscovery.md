---
title: Decisión basada en los resultados de eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Obtenga información sobre cómo la pestaña Decidir en eDiscovery (Premium) proporciona datos que pueden ayudarle a determinar el tamaño correcto del conjunto de revisión de archivos de casos.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 12f1dde5631283a4d0e02666ecab7267ee892225
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090991"
---
# <a name="decisions-based-on-relevance-results-in-ediscovery-premium"></a>Decisiones basadas en resultados de relevancia en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]
  
En el módulo Relevancia de eDiscovery (Premium), la pestaña Decidir proporciona información adicional para ver y usar estadísticas de compatibilidad con decisiones para determinar el tamaño del conjunto de revisión de archivos de casos.
  
## <a name="using-the-decide-tab"></a>Uso de la pestaña Decidir

![Decisión de relevancia.](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Esta pestaña incluye los siguientes componentes:
  
- **Problema**: desde aquí, puede seleccionar el problema de interés de la lista.

- **Relación de revisión y recuperación**: comparaciones de la revisión de eDiscovery (Premium) según las puntuaciones de relevancia. El punto de corte del gráfico representa el porcentaje de archivos que se van a revisar, asignados a una puntuación de relevancia. Esto se usa en la fase de prueba de relevancia y como umbral de exportación para la selección. El punto de corte predeterminado para el número de archivos que se van a revisar es en el punto en el que el equilibrio entre recuperación y precisión es óptimo. El usuario debe determinar el punto de límite real en función de los objetivos y el equilibrio de costos (%revisión) y riesgo (%recuperación). Con el control deslizante, puede ajustar el punto de corte y ver el efecto en el gráfico y los parámetros, al ajustar el porcentaje de archivos pertinentes que se van a recuperar y antes de validar una decisión.

- **Parámetros: los parámetros** Review, Recall, Next relevant y Total cost son estadísticas calculadas acumulativas relacionadas con el conjunto de revisión en relación con la colección para todo el caso. Las definiciones de estos parámetros son las siguientes:

  - **Revisión**: porcentaje de archivos que se van a revisar en función de este límite.

  - **Recuperación**: porcentaje de archivos relevantes en el conjunto de revisión.

  - **Siguiente pertinente**: costo para revisar e identificar otro archivo pertinente que no está actualmente en el conjunto de revisión.

  - **Costo total**: costo por revisar este porcentaje de los archivos de caso. El administrador de casos puede establecer la configuración del parámetro de costo.

  - **Distribución por puntuación de relevancia**: los archivos de la pantalla gris oscuro a la izquierda están por debajo de la puntuación de límite. Una sugerencia de herramienta muestra la puntuación de relevancia y el porcentaje relacionado de archivos en el conjunto de archivos de revisión en relación con el total de archivos.

El panel **Detalles** expandido muestra más detalles. Los archivos de las figuras de colección no incluyen archivos vacíos o nebulosos. Las figuras de archivos de familia representan archivos que no se cargan en relevancia, pero que todavía se cuentan como parte de la familia.
