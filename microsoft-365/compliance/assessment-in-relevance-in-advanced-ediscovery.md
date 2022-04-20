---
title: Descripción de la evaluación en relevancia en eDiscovery (Premium)
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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Obtenga información general sobre la fase de evaluación y su rol en la determinación de la riqueza de los problemas durante el entrenamiento de relevancia en Microsoft Purview eDiscovery (Premium).
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29376b8c71947b1f09bd86de90facef6f73e0fdd
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64943961"
---
# <a name="assessment-in-the-relevance-module-in-ediscovery-premium"></a>Evaluación en el módulo Relevancia en eDiscovery (Premium)
  
Microsoft Purview eDiscovery (Premium) permite una evaluación temprana, por ejemplo, para los problemas definidos y los datos importados para un caso. eDiscovery (Premium) permite al experto tomar decisiones sobre un enfoque adoptado y aplicar estas decisiones al proyecto de revisión de documentos.
  
## <a name="understanding-assessment"></a>Descripción de la evaluación

En Evaluación, el experto revisa un conjunto aleatorio de al menos 500 archivos, que se usan para determinar la riqueza de los problemas y para generar estadísticas que reflejen los resultados del entrenamiento. La evaluación es correcta cuando se encuentran suficientes archivos pertinentes para alcanzar un nivel estadístico que ayude a eDiscovery (Premium) Relevancia para proporcionar estadísticas precisas y determinar eficazmente el punto de estabilización en el proceso de entrenamiento. 
  
Cuanto mayor sea el número de archivos pertinentes en el conjunto de evaluación, más precisas serán las estadísticas y la eficacia del algoritmo de estabilidad. El número de archivos pertinentes dentro de los archivos de evaluación depende de la riqueza del problema. La riqueza es el porcentaje estimado de archivos pertinentes en el conjunto pertinente para un problema. Los problemas con mayor riqueza alcanzarán un mayor número de archivos pertinentes más rápidamente que los problemas con menor riqueza. Los problemas con una riqueza extremadamente baja (por ejemplo, un 2 % o menos) requerirán un conjunto de evaluación muy grande para alcanzar un número significativo de archivos relevantes.
  
Las estadísticas, que se presentan en las pestañas Seguimiento y Decisión durante el entrenamiento y después del cálculo de Batch, incluyen estimaciones de recuperación para diferentes conjuntos de revisión. En las estadísticas, las estimaciones basadas en un conjunto de ejemplo (en este caso, los archivos de evaluación) incluyen el margen de error y el nivel de confianza de ese margen de error. Por ejemplo, la recuperación estimada del 80 % podría tener un margen de error de más o menos del 5 % con un nivel de confianza del 95 %. Esto significa que la recuperación estimada es realmente del 75 % al 85 % y esta estimación tiene una confianza del 95 %. Cuanto mayor sea el conjunto de evaluación, el margen de error será menor y las estadísticas serán más precisas. 
  
Después de que el experto revise un conjunto de evaluación inicial de 500 archivos, Relevancia puede determinar el margen de error actual de los valores de recuperación. La relevancia también recomendará un margen de error predeterminado para alcanzar para optimizar el conjunto de evaluación. Estos son algunos ejemplos:
  
- Si el conjunto de evaluación ya produjo un margen de error de más o menos 10 %, Relevancia recomendará pasar al entrenamiento (no se necesita ninguna revisión de evaluación adicional). 

- Si el conjunto de evaluación produjo un margen de error de más o menos el 13 %, Relevancia podría recomendar la revisión de otro conjunto de archivos de evaluación para alcanzar un margen más pequeño. 

- Si la riqueza es extremadamente baja, la relevancia podría recomendar detener la evaluación aunque el margen de error sea grande (lo que hace que las estadísticas sean poco prácticas), ya que el conjunto de evaluación necesario para alcanzar un margen de error útil es demasiado grande.

Cada problema tiene su propia riqueza, margen de error actual y, como resultado, número estimado de archivos de evaluación adicionales. El siguiente conjunto de evaluación se crea según el número máximo de archivos (hasta 1000 en un único conjunto).
  
Puede aceptar las recomendaciones de relevancia o ajustar el margen de error actual según sus necesidades. El margen de error actual predeterminado se determina para la recuperación en igual o superior al 75 %.
  
> [!NOTE]
> La fase evaluación se puede omitir, en la pestaña **Seguimiento de relevancia \>** de la vista expandida de un problema, desactivando la casilla **Evaluación** por problema y, a continuación, para "todos los problemas". Como resultado, no habrá estadísticas para este problema. La **desactivación** de la casilla Evaluación solo se puede realizar antes de realizar la evaluación. Cuando existen varios problemas en un caso, la evaluación solo se omite si la casilla está desactivada para cada problema.
