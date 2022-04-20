---
title: Importación de un modelo de comprensión de documentos de ejemplo para Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.custom: intro-get-started
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre los modelos de comprensión de documentos a través del modelo de ejemplo.
ms.openlocfilehash: 210d5865a6e3208faff16fe1ce14748ee66d63c8
ms.sourcegitcommit: dc415d784226c77549ba246601f34324c4f94e73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64916213"
---
# <a name="import-a-sample-document-understanding-model-for-microsoft-sharepoint-syntex"></a>Importación de un modelo de comprensión de documentos de ejemplo para Microsoft SharePoint Syntex

SharePoint Syntex proporciona un modelo de ejemplo que puede usar para examinar, lo que le proporciona una mejor comprensión de cómo crear sus propios modelos. El modelo de ejemplo también le permite examinar los componentes del modelo, como su clasificador, extractores y explicaciones. Además, puede usar los archivos de ejemplo para entrenar el modelo.

## <a name="import-the-sample-model"></a>Importar el modelo de ejemplo

Para obtener acceso al modelo de ejemplo, necesita importar el modelo al centro de contenido.

1. Desde el centro de contenido, seleccione **Modelos** para ver la lista de modelos.</br>
2. En la página de **Modelos**, seleccione **Importar modelo de ejemplo**.</br>

    ![Importar modelo de ejemplo.](../media/content-understanding/import-sample-model.png) </br>

3. Cuando termine la importación, se abrirá la página principal del modelo **BenefitsChangeNotice**. Si necesita abrir el modelo de ejemplo en el futuro, puede hacerlo desde la lista modelos en el centro de contenido. </br>

     ![Página principal del ejemplo.](../media/content-understanding/sample-home-page.png)</br>

No solo puede analizar el modelo de ejemplo para comprender mejor cómo se crea el modelo, sino, al ser un modelo de trabajo, puede ir más allá y llevar a cabo acciones como:

- Agregar otro extractor Por ejemplo, agregar uno que extraiga la *cuota de descuento*.
- Aplicar el modelo a una biblioteca de documentos y, a continuación, cargar algunos de los archivos de aprendizaje para ver cómo el modelo clasifica los archivos y extrae datos.

## <a name="get-sample-models"></a>Obtener modelos de ejemplo

Puede acceder al [repositorio de ejemplos de SharePoint Syntex](https://github.com/pnp/syntex-samples), que contiene ejemplos de la comunidad que muestran diferentes patrones de uso de modelos de comprensión de documentos. Los ejemplos de este repositorio contienen los archivos de modelo de comprensión de documentos y los archivos usados para entrenar el modelo. Una vez importados, puede usar estos modelos para procesar archivos y ver y editar el clasificador y los extractores.

## <a name="see-also"></a>Ver también
[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Información general sobre la comprensión de los documentos](document-understanding-overview.md)

[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)  
