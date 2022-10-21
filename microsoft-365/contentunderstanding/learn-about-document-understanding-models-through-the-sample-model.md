---
title: Importación de un modelo de ejemplo para Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.custom: intro-get-started
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre los modelos de procesamiento de documentos no estructurados en Microsoft Syntex mediante el modelo de ejemplo.
ms.openlocfilehash: 1cc865ba121be342821999924a31d1ba8082bd94
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68659573"
---
# <a name="import-a-sample-model-for-microsoft-syntex"></a>Importación de un modelo de ejemplo para Microsoft Syntex

Microsoft Syntex le proporciona un modelo de procesamiento de documentos no estructurado de ejemplo que puede usar para examinar, lo que le proporciona una mejor comprensión de cómo crear sus propios modelos. El modelo de ejemplo también le permite examinar los componentes del modelo, como su clasificador, extractores y explicaciones. Además, puede usar los archivos de ejemplo para entrenar el modelo.

## <a name="import-the-sample-model"></a>Importar el modelo de ejemplo

Para obtener acceso al modelo de ejemplo, necesita importar el modelo al centro de contenido.

1. Desde el centro de contenido, seleccione **Modelos** para ver la lista de modelos.

2. En la página de **Modelos**, seleccione **Importar modelo de ejemplo**.

    ![Importar modelo de ejemplo.](../media/content-understanding/import-sample-model.png) 

3. Cuando termine la importación, se abrirá la página principal del modelo **BenefitsChangeNotice**. Si necesita abrir el modelo de ejemplo en el futuro, puede abrirlo desde la lista de modelos en el centro de contenido.

    ![Página principal del ejemplo.](../media/content-understanding/sample-home-page.png)

No solo puede examinar el análisis del modelo de ejemplo para comprender mejor cómo se construye el modelo, sino que, como modelo de trabajo, puede ir más allá y hacer cosas como:

- Agregue otro extractor. Por ejemplo, agregar uno que extraiga la *cuota de descuento*.

- Aplicar el modelo a una biblioteca de documentos y, a continuación, cargar algunos de los archivos de aprendizaje para ver cómo el modelo clasifica los archivos y extrae datos.

## <a name="get-sample-models"></a>Obtener modelos de ejemplo

Puede acceder al [repositorio de ejemplos de Syntex](https://github.com/pnp/syntex-samples), que contiene ejemplos de la comunidad que muestran diferentes patrones de uso de modelos de procesamiento de documentos no estructurados. Los ejemplos de este repositorio contienen los archivos de modelo y los archivos usados para entrenar el modelo. Una vez importados, puede usar estos modelos para procesar archivos y ver y editar el clasificador y los extractores.

## <a name="see-also"></a>Vea también

[Introducción al procesamiento de documentos no estructurados](document-understanding-overview.md)

[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)