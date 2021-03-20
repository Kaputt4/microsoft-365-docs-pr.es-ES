---
title: Información general sobre la comprensión de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Obtenga información general sobre la comprensión des documentos en Microsoft SharePoint Syntex.
ms.openlocfilehash: e3b239260953837f70663bb6f7e2dba1676c49eb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911203"
---
# <a name="document-understanding-overview"></a>Información general sobre la comprensión de documentos


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

La comprensión de documentos usa modelos de inteligencia artificial (IA) para automatizar la clasificación de archivos y extraer la información. Funciona mejor con documentos sin estructura, como cartas o contratos. Estos documentos deben tener texto que pueda identificarse en función de frases o patrones. El texto identificado designa tanto el tipo de archivo (su clasificación) como lo que le gustaría extraer (sus extractores).

> [!NOTE]
> Consulte [Adopción de SharePoint Syntex: Guía de introducción](./adoption-getstarted.md#document-understanding-scenario-example) para obtener más información sobre ejemplos de escenarios de comprensión mediante documentos.

Los modelos de comprensión mediante documentos se crean y se administran en un tipo de sitio de SharePoint denominado *centro de contenido*. Cuando se aplica a una biblioteca de documentos de SharePoint, el modelo está asociado a un tipo de contenido que tiene columnas para almacenar la información que se va a extraer. El tipo de contenido que cree se almacena en la galería de tipo de contenido de SharePoint. También puede optar por usar tipos de contenido existentes para usar su esquema.

> [!NOTE]
> Los tipos de contenido de solo lectura o sellado no pueden ser actualizados, de manera que no pueden ser usados en un modelo.

Agregue *clasificadores* y *extractores* a los modelos de comprensión del documento para hacer lo siguiente: 

- Los clasificadores se usan para identificar y clasificar documentos cargados en la biblioteca de documentos. Por ejemplo, un clasificador puede ser "entrenado" para identificar todos los documentos de *renovación de contrato* que se carguen en la biblioteca. El tipo de contenido de renovación de contrato lo define el usuario al crear el clasificador.

- Los extractores extraen información de estos documentos. Por ejemplo, para todos los documentos de renovación de contratos identificados en la biblioteca de documentos, las columnas se muestran en la vista que también muestra la *Fecha de inicio del servicio* y el *Cliente* por cada documento de renovación de contrato. 

Puede usar archivos de ejemplo para entrenarlos y probarlos en el modelo. Los archivos de ejemplo proporcionan ejemplos al modelo de lo que debe buscar al intentar identificar y extraer datos de archivos. Por ejemplo, entrenaría los clasificadores y extracciones de renovación de contrato con ejemplos de documentos de renovación de contratos con los que trabaja su empresa. También puede usar archivos de ejemplo para probar la efectividad del modelo.

Después de publicar el modelo, utilice el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.  

### <a name="file-limitations"></a>Limitaciones de archivos

En los modelos de comprensión mediante documentos se usa la tecnología de reconocimiento óptico de caracteres (OCR) para digitalizar archivos PDF, imágenes y archivos TIFF, tanto al entrenar un modelo con archivos de ejemplo como al ejecutar el modelo en archivos de una biblioteca de documentos.

Tenga en cuenta las siguientes diferencias en relación con los archivos de texto basados en Microsoft Office y los archivos digitalizados con OCR (PDF, imagen o TIFF):

- Archivos de Office: el límite para truncar archivos es 64 000 caracteres (durante el entrenamiento y cuando se ejecuta en archivos de una biblioteca de documentos).
- Archivos digitalizados con OCR: hay un límite de 20 páginas.  

#### <a name="supported-file-types"></a>Tipos de archivo compatibles

Los modelos de comprensión mediante documentos admiten los siguientes tipos de archivo:

- doc
- docx
- eml
- heic
- heif
- htm
- html
- jpeg
- jpg
- markdown
- md
- msg
- pdf
- png
- ppt
- pptx
- rtf
- tif
- tiff
- txt
- xls
- xlsx



## <a name="see-also"></a>Consulte también
[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Crear un centro de contenido](create-a-content-center.md)

[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)

[Aplicar un modelo](apply-a-model.md)   

[Diferencia entre un modelo de comprensión de documentos y un modelo de procesamiento de formularios](difference-between-document-understanding-and-form-processing-model.md)
  
[Información general del procesamiento de formularios](form-processing-overview.md)

[Modo de accesibilidad de SharePoint Syntex](accessibility-mode.md)