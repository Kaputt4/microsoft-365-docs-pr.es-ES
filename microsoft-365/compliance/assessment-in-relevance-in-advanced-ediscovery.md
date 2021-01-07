---
title: Descripción de la evaluación en relevancia en eDiscovery avanzado
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
description: Obtenga información general sobre la fase de evaluación y su rol a la hora de determinar la riqueza de los problemas durante la formación de relevancia en la exhibición avanzada de documentos electrónicos de Microsoft 365.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769281"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Evaluación en el módulo de relevancia en eDiscovery avanzado
  
La exhibición avanzada de documentos electrónicos permite una evaluación temprana, por ejemplo, para los problemas definidos y los datos importados para un caso. EDiscovery avanzado permite al experto tomar decisiones sobre un enfoque adoptado y aplicar estas decisiones al proyecto de revisión del documento.
  
## <a name="understanding-assessment"></a>Descripción de la evaluación

En la evaluación, el experto revisa un conjunto aleatorio de al menos 500 archivos, que se usan para determinar la riqueza de los problemas y para producir estadísticas que reflejen los resultados de la formación. La evaluación se realiza correctamente cuando se encuentran archivos relevantes para llegar a un nivel estadístico que ayude a la relevancia avanzada de eDiscovery a proporcionar estadísticas precisas y a determinar eficazmente el punto de estabilización en el proceso de formación. 
  
Cuanto mayor sea el número de archivos relevantes en el conjunto de evaluación, más precisos serán las estadísticas y la eficacia del algoritmo de estabilidad. El número de archivos relevantes dentro de los archivos de evaluación depende de la riqueza del problema. La riqueza es el porcentaje estimado de los archivos relevantes en el conjunto correspondiente a un problema. Los problemas con la riqueza más alta alcanzarán un número más alto de archivos relevantes más rápido que los problemas con la riqueza menor. Los problemas con la riqueza extremadamente baja (por ejemplo, un 2% o menos) requerirán un conjunto de evaluación muy grande para llegar a un número significativo de archivos relevantes.
  
Las estadísticas, que se presentan en las pestañas realizar seguimiento y decidir durante la formación y después del cálculo por lotes, incluyen los cálculos de la recuperación de los distintos conjuntos de revisión. En las estadísticas, las estimaciones basadas en un conjunto de muestra (en este caso, los archivos de evaluación) incluyen el margen de error y el nivel de confianza de ese margen de error. Por ejemplo, una recuperación de 80% estimada puede tener un margen de error de más o menos un 5% con un nivel de confianza de 95%. Esto significa que la recuperación estimada es en realidad del 75%-85% y esta estimación tiene un 95% de confianza. Cuanto mayor sea el conjunto de evaluación, el margen de error será más pequeño y las estadísticas serán más exactas. 
  
Una vez que el experto revisa un conjunto de evaluación inicial de 500 archivos, la relevancia puede determinar el margen actual de error de los valores de recuperación. La relevancia también recomienda un margen de error predeterminado para llegar a la optimización del conjunto de evaluación. Aquí le mostramos otros ejemplos:
  
- Si el conjunto de evaluación ya ha dado como resultado un margen de error de más o menos el 10%, la relevancia le recomendará pasar a la formación (no es necesaria ninguna revisión de evaluación adicional). 

- Si el conjunto de evaluación produjo un margen de error de más o menos el 13%, la relevancia puede recomendar la revisión de otro conjunto de archivos de evaluación para alcanzar un margen más pequeño. 

- Si la riqueza es extremadamente baja, la relevancia podría recomendar la detención de la evaluación, aunque el margen de error sea grande (lo que no resulta práctico), ya que el conjunto de evaluación necesario para alcanzar un margen de error útil es demasiado grande.

Cada problema tiene su propia riqueza, el margen actual de error y, como resultado, el número estimado de archivos de evaluación adicionales. El siguiente conjunto de evaluación se crea de acuerdo con el número máximo de archivos (hasta 1.000 en un único conjunto).
  
Puede aceptar las recomendaciones de relevancia o ajustar el margen de error actual de acuerdo con sus necesidades. El margen actual predeterminado del error se determina para la recuperación como igual o superior al 75%.
  
> [!NOTE]
> La fase de evaluación se puede omitir, en la pestaña **\> seguimiento de relevancia** de la vista expandida para un problema, desactivando la casilla de verificación **evaluación** por problema y, a continuación, "todos los problemas". Como resultado, no habrá estadísticas para este problema. Sólo se puede desactivar la casilla de verificación **evaluación** antes de realizar la evaluación. Cuando hay varios problemas en un caso, la evaluación se omite solo si la casilla de verificación está desactivada para cada problema.
