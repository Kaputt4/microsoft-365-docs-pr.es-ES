---
title: Retirada del módulo relevancia en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: El módulo relevancia en eDiscovery avanzado se retirará el 10 de marzo de 2021. En este artículo se explica qué hacer antes de retirar Relevancia. En concreto, para finalizar los modelos sin terminar, ejecute el cálculo por lotes para que pueda conservar los metadatos del modelo.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122539"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>Retirada del módulo Relevancia en eDiscovery avanzado

El 10 de marzo de 2021, retiraremos el módulo relevancia en eDiscovery avanzado. Esta retirada significa que las organizaciones ya no tendrán acceso al módulo relevancia (yendo a Administrar relevancia del conjunto de revisión en un caso de eDiscovery avanzado) ni podrán acceder a los modelos de relevancia  >   existentes. El módulo relevancia actual que se está retirando se reemplazará por una nueva solución de codificación predictiva en el segundo trimestre de CY 2021. Esta nueva funcionalidad permitirá a las organizaciones crear sus propios modelos de codificación predictiva en un flujo de trabajo más sencillo e intuitivo.

Para prepararse para esta próxima retirada, se recomienda que las organizaciones que usen el módulo Relevancia exporten los resultados de su modelo antes de la fecha de retirada mediante la ejecución de un cálculo por lotes para todos los modelos existentes. Todas las puntuaciones de relevancia del modelo se almacenarán permanentemente en el conjunto de revisión correspondiente y se podrá tener acceso a ellos cuando se exporten los documentos. Las puntuaciones de relevancia también se conservan como metadatos en el archivo de carga. Además, podrá filtrar el contenido del conjunto de revisión en función de la puntuación de relevancia y tener acceso a todos los metadatos producidos por los modelos de relevancia.

## <a name="complete-unfinished-models"></a>Modelos sin terminar completos

Para cualquier modelo de relevancia sin terminar, complete la evaluación, el aprendizaje y el cálculo por lotes para que pueda aplicar el modelo a los documentos de un conjunto de revisión. Al completar el cálculo por lotes se conservará la información después de la fecha de retirada del módulo relevancia.

Estos son los pasos para completar los modelos sin terminar:

1. Entrena el modelo hasta que esté estabilizado y listo para el cálculo por lotes. Vea [el curso de etiquetado y relevancia.](tagging-and-relevance-training-in-advanced-ediscovery.md)

   La siguiente captura de pantalla muestra un módulo que está listo para un cálculo por lotes. Observe que la evaluación y el aprendizaje se han completado y el siguiente paso es ejecutar el cálculo por lotes.

   ![Captura de pantalla del modelo listo para el cálculo por lotes](../media/ReadyForBatchCalculation.png)

2. Ejecute el cálculo por lotes. Vea [Realizar cálculos por lotes.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)

3. Compruebe que el cálculo por lotes se ha realizado correctamente. Vea los [resultados del cálculo por lotes.](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)

Para obtener ayuda con la finalización de modelos de relevancia sin terminar, póngase en contacto con el Soporte técnico de Microsoft.
