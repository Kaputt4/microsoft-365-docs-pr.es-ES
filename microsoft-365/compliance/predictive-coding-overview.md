---
title: Módulo de codificación predictiva para exhibición de documentos electrónicos avanzada (versión preliminar)
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
description: El nuevo módulo de codificación predictiva de eDiscovery avanzado usa el aprendizaje automático para analizar documentos en un conjunto de revisión para predictiva cuáles son los documentos relevantes para su caso o investigación.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383006"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a>Módulo de codificación predictiva para exhibición de documentos electrónicos avanzada (versión preliminar)

Con el nuevo módulo de codificación predictiva de eDiscovery avanzado, puede crear y crear un modelo para priorizar la revisión de documentos a partir de los documentos más relevantes. Para empezar, puede crear un modelo, etiquetar hasta 50 documentos y, a continuación, filtrar documentos por puntuaciones de predicción del modelo para revisar documentos relevantes no relevantes.

Este es un resumen rápido del flujo de trabajo:

1. Abra el módulo de codificación predictiva en un conjunto de revisión.

   ![Haga clic en la lista desplegable Analizar de una revisión para ir al módulo de codificación predictiva](..\media\PredictiveCoding1.png)

2. En la **página Modelos de codificación predictiva,** haga clic en **Nuevo modelo** para crear un nuevo modelo de codificación predictiva.

   ![Crear un nuevo modelo](..\media\PredictiveCoding2.png)

3. Etiquete al menos 50 documentos **como Relevantes** **o No relevantes**. Este etiquetado se usa para entrenar el sistema.

   ![Etiquetar documentos como relevantes o no relevantes para entrenar el sistema](..\media\PredictiveCoding3.png)

4. Aplica el **filtro de puntuación** de predicción del modelo al conjunto de revisión. Para ello:

   1. En el conjunto de revisión, haga clic **en Filtros**.
   2. En la **página** desplegable Filtros, expanda la sección  **Análisis/ML** y, a continuación, active la casilla Puntuación de predicción para el modelo que desee aplicar.
   3. En el **filtro Puntuación de** predicción, especifique una puntuación de predicción. El filtro mostrará los documentos del conjunto de revisión que coincidan con la puntuación de predicción.

      ![Especificar una puntuación de predicción para filtrar documentos](..\media\PredictiveCoding4.png)

5. Supervise el rendimiento, el estado y la estabilidad del modelo.

   ![Supervisar el rendimiento, el estado y la estabilidad del modelo](..\media\PredictiveCoding5.png)
