---
title: Módulo Retiro de relevancia en Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: El módulo relevancia en Advanced eDiscovery se retirará el 10 de marzo de 2021. En este artículo se explica qué hacer antes de retirar relevancia. En concreto, para finalizar cualquier modelo sin terminar, ejecute el cálculo por lotes para que pueda conservar los metadatos del modelo.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822002"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>Retiro del módulo Relevancia en Advanced eDiscovery

El 10 de marzo de 2021, retiraremos el módulo Relevancia en Advanced eDiscovery. Esta retirada significa que las organizaciones ya no tendrán acceso al módulo Relevancia (yendo a Administrar el conjunto de revisión Relevancia en un caso Advanced eDiscovery) ni podrán tener acceso a los modelos de  >   relevancia existentes. El módulo de relevancia actual que se está retirando se reemplazará por una nueva solución de codificación predictiva en el segundo trimestre de CY 2021. Esta nueva funcionalidad permitirá a las organizaciones crear sus propios modelos de codificación predictiva en un flujo de trabajo más fácil e intuitivo.

Para prepararse para esta próxima retirada, se recomienda que las organizaciones que usan el módulo Relevancia exporten los resultados de su modelo antes de la fecha de retiro ejecutando un cálculo por lotes para todos los modelos existentes. Todas las puntuaciones de relevancia del modelo se almacenarán permanentemente en el conjunto de revisión correspondiente y se podrá acceder a ellos cuando se exporten documentos. Las puntuaciones de relevancia también se conservan como metadatos en el archivo de carga. Además, podrás filtrar el contenido del conjunto de revisión en función de la puntuación de relevancia y tener acceso a todos los metadatos producidos por los modelos de relevancia.

## <a name="complete-unfinished-models"></a>Modelos completos sin terminar

Para cualquier modelo de relevancia sin terminar, complete la evaluación, el aprendizaje y el cálculo por lotes para que pueda aplicar el modelo a los documentos de un conjunto de revisión. Al completar el cálculo por lotes, se conservará la información después de la fecha de retiro del módulo Relevancia.

Estos son los pasos para completar cualquier modelo sin terminar:

1. Entrena el modelo hasta que esté estabilizado y listo para el cálculo por lotes. Consulte [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).

   En la siguiente captura de pantalla se muestra un módulo que está listo para un cálculo por lotes. Observe que la evaluación y el aprendizaje se han completado y el siguiente paso es ejecutar el cálculo por lotes.

   ![Captura de pantalla del modelo listo para el cálculo por lotes](../media/ReadyForBatchCalculation.png)

2. Ejecute el cálculo batch. Vea [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).

3. Compruebe que el cálculo por lotes se ha realizado correctamente. Vea [Resultados del cálculo por lotes](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).

Para obtener ayuda con la finalización de modelos de relevancia sin terminar, póngase en contacto con el Soporte técnico de Microsoft.
