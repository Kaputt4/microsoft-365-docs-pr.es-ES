---
title: Comprender la evaluación de relevancia en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Obtenga información general sobre la fase de evaluación y su rol en la determinación de la gran variedad de problemas durante la formación de relevancia en eDiscovery avanzado de Microsoft 365.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769281"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Evaluación en el módulo Relevancia en eDiscovery avanzado
  
EDiscovery avanzado permite la evaluación anticipada, por ejemplo, para los problemas definidos y los datos importados para un caso. La exhibición avanzada de documentos electrónicos permite al experto tomar decisiones sobre un enfoque adoptado y aplicar estas decisiones al proyecto de revisión de documentos.
  
## <a name="understanding-assessment"></a>Descripción de la evaluación

En la evaluación, el experto revisa un conjunto aleatorio de al menos 500 archivos, que se usan para determinar la gran variedad de problemas y para generar estadísticas que reflejen los resultados de la formación. La evaluación se realiza correctamente cuando se encuentran suficientes archivos relevantes para alcanzar un nivel estadístico que ayudará a relevancia avanzada de exhibición de documentos electrónicos a proporcionar estadísticas precisas y a determinar de forma eficaz el punto de estabilización en el proceso de aprendizaje. 
  
Cuanto mayor sea el número de archivos relevantes en el conjunto de evaluaciones, más precisas son las estadísticas y la eficacia del algoritmo de estabilidad. El número de archivos relevantes dentro de los archivos de evaluación depende de la variedad del problema. Richness es el porcentaje estimado de archivos relevantes en el conjunto relevante para un problema. Los problemas con mayor enriquecimiento alcanzarán un mayor número de archivos relevantes más rápidamente que los problemas con menor enriquecimiento. Los problemas con una gran cantidad de información extremadamente baja (por ejemplo, un 2 % o menos) requerirán un conjunto de evaluaciones muy grande para alcanzar un número significativo de archivos relevantes.
  
Las estadísticas, que se presentan en las pestañas Track y Decide durante el aprendizaje y después del cálculo por lotes, incluyen estimaciones de recuperación para diferentes conjuntos de revisión. En las estadísticas, las estimaciones basadas en un conjunto de muestras (en este caso, los archivos de evaluación) incluyen el margen de error y el nivel de confianza de ese margen de error. Por ejemplo, la recuperación estimada del 80 % podría tener un margen de error de más o menos 5 % con un nivel de confianza del 95 %. Esto significa que la recuperación estimada es en realidad del 75%-85% y esta estimación tiene un 95 % de confianza. Cuanto mayor sea el conjunto de evaluaciones, el margen de error se hace más pequeño y las estadísticas son más precisas. 
  
Después de que el experto revisa un conjunto de evaluación inicial de 500 archivos, Relevancia puede determinar el margen de error actual de los valores de recuperación. La relevancia también recomendará un margen de error predeterminado para optimizar el conjunto de evaluaciones. Aquí le mostramos otros ejemplos:
  
- Si el conjunto de evaluaciones ya produjo un margen de error de más o menos 10 %, Relevancia recomienda pasar a la formación (no se necesita una revisión de evaluación adicional). 

- Si el conjunto de evaluaciones produjo un margen de error de más o menos 13%, Relevancia podría recomendar la revisión de otro conjunto de archivos de evaluación para alcanzar un margen más pequeño. 

- Si la eficacia es extremadamente baja, relevancia puede recomendar detener la evaluación aunque el margen de error sea grande (lo que hace que las estadísticas no sea práctica), ya que el conjunto de evaluaciones necesario para alcanzar un margen de error útil es demasiado grande.

Cada problema tiene su propia variedad, margen actual de error y, como resultado, número estimado de archivos de evaluación adicionales. El siguiente conjunto de evaluaciones se crea según el número máximo de archivos (hasta 1.000 en un único conjunto).
  
Puede aceptar las recomendaciones de relevancia o ajustar el margen de error actual según sus necesidades. El margen de error actual predeterminado se determina para recuperarse igual o superior al 75 %.
  
> [!NOTE]
> La fase de evaluación se puede omitir, en la pestaña Seguimiento de  relevancia en la vista expandida de un problema, desactivando la casilla evaluación por problema y, a continuación, para "todos los problemas". **\>** Como resultado, no habrá estadísticas para este problema. La **desactivación de la** casilla evaluación solo puede realizarse antes de que se realice la evaluación. Cuando existen varios problemas en un caso, la evaluación se omite solo si la casilla está desactivada para cada problema.
