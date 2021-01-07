---
title: Decisión basada en los resultados en eDiscovery avanzado
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
description: Obtenga información sobre cómo la pestaña decidir en eDiscovery avanzado proporciona datos que pueden ayudarle a determinar el tamaño correcto del conjunto de revisión de los archivos de casos.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769155"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>Decisiones basadas en los resultados de relevancia en eDiscovery avanzado
  
En el módulo de relevancia de eDiscovery avanzado, la pestaña decidir proporciona información adicional para ver y usar estadísticas de ayuda para la toma de decisiones para determinar el tamaño del conjunto de revisión de los archivos de casos.
  
## <a name="using-the-decide-tab"></a>Uso de la pestaña decidir

![Decisión de relevancia](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Esta pestaña incluye los siguientes componentes:
  
- **Problema**: desde aquí, puede seleccionar el asunto de interés de la lista.

- **Tasa de revisión-RECALL**: comparaciones de la revisión avanzada de eDiscovery según los resultados de relevancia. El punto de corte en el gráfico representa el porcentaje de archivos que se van a revisar, asignado a una puntuación de relevancia. Se usa en la fase de prueba de relevancia y como un umbral de exportación para culling. El punto de corte predeterminado, para el número de archivos que se van a revisar, es el punto en el que el equilibrio entre la recuperación y la precisión es óptimo. El punto de corte real debe estar determinado por el usuario en función de los objetivos y del equilibrio de costes (% Review) y el riesgo (% recall). Con el control deslizante, puede ajustar el punto de corte y ver el efecto en el gráfico y los parámetros, al ajustar el porcentaje de archivos relevantes que se van a recuperar y antes de validar una decisión.

- **Parámetros**: los parámetros revisión, recuperación, siguiente relevante y costo total son estadísticas calculadas acumuladas relativas a la revisión establecida en relación con la colección para todo el caso. Las definiciones de estos parámetros son las siguientes:

  - **Revisión**: porcentaje de archivos que se van a revisar en función de este límite.

  - **RECALL**: porcentaje de archivos relevantes en el conjunto de revisión.

  - **Siguiente relevante**: costo para revisar e identificar otro archivo relevante que no se encuentra actualmente en el conjunto de revisión.

  - **Costo total**: costo de revisión de este porcentaje de los archivos de casos. La configuración del parámetro costo puede definirla el administrador de casos.

  - **Distribución por puntuación de relevancia**: los archivos en la pantalla gris oscuro a la izquierda están por debajo de la puntuación límite. Una información sobre herramientas muestra la puntuación de relevancia y el porcentaje relacionado de los archivos en el archivo de revisión establecido en relación con el total de archivos.

El panel de **detalles** expandido muestra más detalles. Los archivos de las figuras de la colección no incluyen archivos vacíos o Nebulous. Las figuras de los archivos de familia representan los archivos que no se cargan en relevancia, aunque todavía se cuentan como parte de la familia.
