---
title: Comprender la evaluación en relevancia en Advanced eDiscovery
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
description: Obtenga información general sobre la fase de evaluación y su función en la determinación de la riqueza de los problemas durante el aprendizaje de relevancia en Microsoft 365 Advanced eDiscovery.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c3965d15f64559da51b2071679913f02979d89f83db6124703c0d393608effe4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53808577"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Evaluación en el módulo Relevancia en Advanced eDiscovery
  
Advanced eDiscovery permite la evaluación anticipada, por ejemplo, para los problemas definidos y los datos importados para un caso. Advanced eDiscovery permite al experto tomar decisiones sobre un enfoque adoptado y aplicar estas decisiones al proyecto de revisión de documentos.
  
## <a name="understanding-assessment"></a>Descripción de la evaluación

En Evaluación, el experto revisa un conjunto aleatorio de al menos 500 archivos, que se usan para determinar la riqueza de los problemas y para producir estadísticas que reflejen los resultados del aprendizaje. La evaluación se realiza correctamente cuando se encuentran suficientes archivos relevantes para alcanzar un nivel estadístico que ayudará a Advanced eDiscovery Relevancia a proporcionar estadísticas precisas y a determinar eficazmente el punto de estabilización en el proceso de aprendizaje. 
  
Cuanto mayor sea el número de archivos relevantes en el conjunto de evaluaciones, más precisas son las estadísticas y la eficacia del algoritmo de estabilidad. El número de archivos relevantes dentro de los archivos de evaluación depende de la riqueza del problema. La riqueza es el porcentaje estimado de archivos relevantes en el conjunto relevante para un problema. Los problemas con mayor riqueza alcanzarán un mayor número de archivos relevantes más rápidamente que los problemas con menor riqueza. Los problemas con una riqueza extremadamente baja (por ejemplo, un 2 % o menos) requerirán un conjunto de evaluaciones muy grande para alcanzar un número significativo de archivos relevantes.
  
Las estadísticas, que se presentan en las pestañas Track y Decide durante el aprendizaje y después del cálculo por lotes, incluyen estimaciones de recuperación para diferentes conjuntos de revisión. En las estadísticas, las estimaciones basadas en un conjunto de ejemplos (en este caso, los archivos de evaluación) incluyen el margen de error y el nivel de confianza de ese margen de error. Por ejemplo, la recuperación estimada del 80 % puede tener un margen de error de más o menos 5 % con un nivel de confianza del 95 %. Esto significa que la recuperación estimada es en realidad del 75%-85% y esta estimación tiene un 95 % de confianza. Cuanto mayor sea el conjunto de evaluaciones, el margen de error será menor y las estadísticas son más precisas. 
  
Después de que el experto revisa un conjunto de evaluación inicial de 500 archivos, Relevancia puede determinar el margen de error actual de los valores de recuperación. Relevancia también recomendará un margen de error predeterminado para alcanzar para optimizar el conjunto de evaluaciones. Estos son algunos ejemplos:
  
- Si el conjunto de evaluaciones ya produjo un margen de error de más o menos 10 %, Relevancia recomendará pasar al aprendizaje (no se necesita una revisión de evaluación adicional). 

- Si el conjunto de evaluaciones produjo un margen de error de más o menos 13 %, Relevancia podría recomendar la revisión de otro conjunto de archivos de evaluación para alcanzar un margen más pequeño. 

- Si la riqueza es extremadamente baja, es posible que relevancia recomiende detener la evaluación aunque el margen de error sea grande (haciendo que las estadísticas no sea práctica), ya que el conjunto de evaluaciones necesario para alcanzar un margen de error útil es demasiado grande.

Cada problema tiene su propia riqueza, margen de error actual y, como resultado, número estimado de archivos de evaluación adicionales. El siguiente conjunto de evaluación se crea según el número máximo de archivos (hasta 1.000 en un único conjunto).
  
Puede aceptar las recomendaciones de relevancia o ajustar el margen de error actual según sus necesidades. El margen de error actual predeterminado se determina para la recuperación igual o superior al 75 %.
  
> [!NOTE]
> La fase de evaluación se puede omitir, en la pestaña Pista de  relevancia de la vista expandida para un problema, desactivando la casilla Evaluación por problema y, a continuación, para "todos los problemas". **\>** Como resultado, no habrá estadísticas para este problema. La **desactivación de la casilla** Evaluación solo puede realizarse antes de realizar la evaluación. Cuando existen varios problemas en un caso, la evaluación solo se omite si la casilla está desactivada para cada problema.
