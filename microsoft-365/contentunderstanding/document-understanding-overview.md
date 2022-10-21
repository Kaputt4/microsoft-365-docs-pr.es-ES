---
title: Introducción al procesamiento de documentos no estructurados en Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.custom: intro-overview
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre el modelo de procesamiento de documentos no estructurados en Microsoft Syntex.
ms.openlocfilehash: 93ca7e2900098f9067f8c63ea9eae857f61bb7a0
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662366"
---
# <a name="overview-of-unstructured-document-processing-in-microsoft-syntex"></a>Introducción al procesamiento de documentos no estructurados en Microsoft Syntex

> [!NOTE]
> *El procesamiento de documentos no estructurados* se conocía como *comprensión de documentos* en versiones anteriores.

<!---
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7]

</br>
--->

Use el modelo de procesamiento de documentos no estructurado ([método de entrenamiento](create-syntex-model.md#train-a-custom-model)) para clasificar automáticamente los archivos y extraer información. Funciona mejor para documentos no estructurados, como cartas o contratos. 

El modelo de procesamiento de documentos no estructurado (anteriormente conocido como modelo de comprensión de documentos) usa inteligencia artificial (IA) para procesar documentos. Estos documentos deben tener texto que pueda identificarse en función de frases o patrones. El texto identificado designa tanto el tipo de archivo (su clasificación) como lo que le gustaría extraer (sus extractores).

> [!NOTE]
> Para obtener más información sobre cómo usar Syntex y ejemplos de escenarios, consulte [Introducción a la adopción de Microsoft Syntex](./adoption-getstarted.md) y [Escenarios y casos de uso para Microsoft Syntex](./adoption-scenarios.md).

Los modelos de procesamiento de documentos no estructurados se crean y administran en un tipo de sitio de SharePoint denominado [centro de contenido](create-a-content-center.md). Cuando se aplica a una biblioteca de documentos de SharePoint, el modelo está asociado a un tipo de contenido que tiene columnas para almacenar la información que se va a extraer. El tipo de contenido que cree se almacena en la galería de tipo de contenido de SharePoint. También puede optar por usar tipos de contenido existentes para usar su esquema.

> [!NOTE]
> Los tipos de contenido de solo lectura o sellado no se pueden actualizar, por lo que no se pueden usar en un modelo.

Agregue [clasificadores](create-a-classifier.md) y [extractores a los](create-an-extractor.md) modelos de procesamiento de documentos no estructurados para realizar las siguientes acciones:

- Los clasificadores se usan para identificar y clasificar documentos cargados en la biblioteca de documentos. Por ejemplo, un clasificador puede ser "entrenado" para identificar todos los documentos de *renovación de contrato* que se carguen en la biblioteca. El tipo de contenido de renovación de contrato lo define el usuario al crear el clasificador.

- Los extractores extraen información de estos documentos. Por ejemplo, para cada documento de renovación de contrato identificado en la biblioteca de documentos, se mostrarán columnas que muestran la *fecha de inicio del servicio* y *el cliente* de cada documento. 

Puede usar archivos de ejemplo para entrenarlos y probarlos en el modelo. Los archivos de ejemplo proporcionan ejemplos al modelo de lo que debe buscar al intentar identificar y extraer datos de archivos. Por ejemplo, entrenaría los clasificadores y extracciones de renovación de contrato con ejemplos de documentos de renovación de contratos con los que trabaja su empresa. También puede usar archivos de ejemplo para probar la efectividad del modelo.

Después de publicar el modelo, utilice el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.  

## <a name="requirements"></a>Requisitos

Para obtener información sobre los requisitos que se deben tener en cuenta al elegir este modelo, consulte [Requisitos y limitaciones de los modelos de Microsoft Syntex](requirements-and-limitations.md#unstructured-document-processing).

## <a name="see-also"></a>Vea también

[Comparación de modelos personalizados](difference-between-document-understanding-and-form-processing-model.md)

