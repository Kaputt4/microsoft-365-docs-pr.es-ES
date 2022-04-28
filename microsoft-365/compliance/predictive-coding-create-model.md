---
title: Creación de un modelo de codificación predictiva en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Obtenga información sobre cómo crear un modelo de codificación predictiva en eDiscovery (Premium). Este es el primer paso para usar las funcionalidades de aprendizaje automático en eDiscovery (Premium) para ayudarle a identificar contenido relevante y no relevante en un conjunto de revisión.
ms.openlocfilehash: 4542ffbf8be3c7a5c0193f3c0372e3c19e91f02e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099661"
---
# <a name="create-a-predictive-coding-model-preview"></a>Creación de un modelo de codificación predictiva (versión preliminar)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

El primer paso para usar las funcionalidades de aprendizaje automático de la codificación predictiva en eDiscovery (Premium) es crear un modelo de codificación predictiva. Después de crear un modelo, puede entrenarlo para identificar el contenido relevante y no relevante de un conjunto de revisión.

Para revisar el flujo de trabajo de codificación predictiva, consulte [Información sobre la codificación predictiva en eDiscovery (Premium)](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-create-a-model"></a>Antes de crear un modelo

- Debe haber un mínimo de 2000 elementos en un conjunto de revisión para crear un modelo de codificación predictiva.

- Asegúrese de confirmar todas las colecciones en el conjunto de revisión antes de crear un modelo. Los elementos agregados a un conjunto de revisión después de crear el modelo no se procesarán y se les asignará una puntuación de predicción generada por el modelo.

- El modelo no procesará ningún elemento del conjunto de revisión que no contenga texto ni se le asignará una puntuación de predicción. Los elementos con texto se incluirán en el conjunto de control o en un conjunto de entrenamiento.

## <a name="create-a-model"></a>Crear un modelo

1. En el portal de cumplimiento de Microsoft Purview, abra un caso de exhibición de documentos electrónicos (Premium) y, a continuación, seleccione la pestaña **Conjuntos de revisión**.

2. Abra un conjunto de revisión y, a continuación, haga clic en **AnálisisAdministrar** >  **codificación predictiva (versión preliminar).**

   ![Haga clic en el menú desplegable Analizar del conjunto de revisión para ir a la página Codificación predictiva.](..\media\ManagePredictiveCoding.png)

3. En la página **Modelos de codificación predictiva (versión preliminar),** haga clic en **Nuevo modelo**.

4. En la página de control flotante, escriba un nombre para el modelo y una descripción opcional.

5. Opcionalmente, puede configurar opciones avanzadas (haciendo clic en **Opciones avanzadas** en la página de control flotante) relacionadas con el nivel de confianza y el margen de error. Esta configuración afecta al número de elementos incluidos en el conjunto de controles. El *conjunto de controles* se usa durante el proceso de entrenamiento para evaluar las puntuaciones de predicción que el modelo asigna a los elementos con el etiquetado que se realiza durante las rondas de entrenamiento. Si su organización tiene instrucciones sobre el nivel de confianza y el margen de error para la revisión de documentos, especifíquelos en los cuadros adecuados. De lo contrario, use la configuración predeterminada.

6. Haga clic en **Guardar** para crear el modelo.

   El sistema tardará un par de minutos en preparar el modelo. Una vez listo, puede realizar la primera ronda de entrenamiento.

## <a name="what-happens-after-you-create-a-model"></a>Qué ocurre después de crear un modelo

Después de crear un modelo, se producen las siguientes cosas en segundo plano durante la creación y preparación del modelo:

- El sistema calcula el número de elementos para el conjunto de control. Este tamaño se basa en el número de elementos del conjunto de revisión y en la configuración del nivel de confianza y el margen de error. Los elementos del conjunto de controles se seleccionan aleatoriamente y se designan como elementos del conjunto de controles. El sistema incluye 10 elementos del conjunto de control en la primera ronda de entrenamiento.

- El sistema selecciona aleatoriamente 40 elementos del conjunto de revisión que se incluirán en el conjunto de entrenamiento para la primera ronda de entrenamiento. Por lo tanto, la primera ronda de entrenamiento incluye 50 elementos para el etiquetado: 40 elementos del conjunto de entrenamiento y 10 elementos del conjunto de control.

## <a name="next-steps"></a>Siguientes pasos

Después de crear un modelo para un conjunto de revisión, el siguiente paso es realizar rondas de entrenamiento para "enseñar" el modelo a fin de identificar el contenido que es relevante para la investigación. Para obtener más información, consulte [Entrenamiento de un modelo de codificación predictiva](predictive-coding-train-model.md).
