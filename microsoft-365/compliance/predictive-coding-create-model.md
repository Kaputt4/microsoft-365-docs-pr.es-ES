---
title: Crear un modelo de codificación predictiva en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Obtenga información sobre cómo crear un modelo de codificación predictiva en Advanced eDiscovery. Este es el primer paso para usar las capacidades de aprendizaje automático de Advanced eDiscovery para ayudarle a identificar contenido relevante y no relevante en un conjunto de revisión.
ms.openlocfilehash: ab84f529169c780e58888cc2726fbabfef33219e
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226232"
---
# <a name="create-a-predictive-coding-model-preview"></a>Crear un modelo de codificación predictiva (versión preliminar)

El primer paso para usar las capacidades de aprendizaje automático de la codificación predictiva en Advanced eDiscovery es crear un modelo de codificación predictiva. Después de crear un modelo, puede entrenarlo para identificar el contenido relevante y no relevante de un conjunto de revisión.

Para revisar el flujo de trabajo de codificación predictiva, vea [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-create-a-model"></a>Antes de crear un modelo

- Debe haber un mínimo de 2.000 elementos en un conjunto de revisión para crear un modelo de codificación predictiva.

- Asegúrese de confirmar todas las colecciones en el conjunto de revisión antes de crear un modelo. Los elementos agregados a un conjunto de revisión después de crear el modelo no se procesarán y se les asignará una puntuación de predicción generada por el modelo.

- El modelo no procesará ningún elemento del conjunto de revisión que no contenga texto ni se le asignará una puntuación de predicción. Los elementos con texto se incluirán en el conjunto de controles o en un conjunto de aprendizaje.

## <a name="create-a-model"></a>Crear un modelo

1. En el Centro de cumplimiento de Microsoft 365, abra un Advanced eDiscovery y, a continuación, seleccione la **pestaña Conjuntos de** revisión.

2. Abra un conjunto de opiniones y, a continuación, haga clic **en Analytics Administrar**  >  **codificación predictiva (versión preliminar).**

   ![Haga clic en el menú desplegable Analizar en el conjunto de revisión para ir a la página Codificación predictiva](..\media\ManagePredictiveCoding.png)

3. En la **página Modelos de codificación predictiva (versión preliminar),** haga clic **en Nuevo modelo**.

4. En la página desplegable, escriba un nombre para el modelo y una descripción opcional.

5. Opcionalmente, puede configurar opciones avanzadas  (haciendo clic en Opciones avanzadas en la página desplegable) relacionadas con el nivel de confianza y el margen de error. Esta configuración afecta al número de elementos incluidos en el conjunto de controles. El *conjunto de controles* se usa durante el proceso de aprendizaje para evaluar las puntuaciones de predicción que el modelo asigna a los elementos con el etiquetado que se realiza durante las rondas de aprendizaje. Si su organización tiene directrices sobre el nivel de confianza y el margen de error para la revisión de documentos, es necesario especificarlas en los cuadros correspondientes. De lo contrario, use la configuración predeterminada.

6. Haga **clic en** Guardar para crear el modelo.

   El sistema tardaría un par de minutos en preparar el modelo. Después de que esté listo, puedes realizar la primera ronda de aprendizaje.

## <a name="what-happens-after-you-create-a-model"></a>Qué sucede después de crear un modelo

Después de crear un modelo, se producen lo siguiente en segundo plano durante la creación y preparación del modelo:

- El sistema calcula el número de elementos para el conjunto de controles. Este tamaño se basa en el número de elementos del conjunto de revisión y la configuración del nivel de confianza y el margen de error. Los elementos del conjunto de controles se seleccionan aleatoriamente y se designan como elementos del conjunto de controles. El sistema incluye 10 elementos del conjunto de controles de la primera ronda de aprendizaje.

- El sistema selecciona aleatoriamente 40 elementos del conjunto de opiniones que se incluirán en el conjunto de aprendizaje de la primera ronda de aprendizaje. Por lo tanto, la primera ronda de aprendizaje incluye 50 elementos para el etiquetado: 40 elementos del conjunto de aprendizaje y 10 elementos del conjunto de control.

## <a name="next-steps"></a>Siguientes pasos

Después de crear un modelo para un conjunto de revisión, el siguiente paso es realizar rondas de aprendizaje para "enseñar" el modelo para identificar el contenido que es relevante para la investigación. Para obtener más información, vea [Train a predictive coding model](predictive-coding-train-model.md).
