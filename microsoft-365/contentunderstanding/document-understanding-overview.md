---
title: Introducción a la descripción de los documentos (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información general sobre la descripción de los documentos en Project Cortex.
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537405"
---
# <a name="document-understanding-overview-preview"></a>Introducción a la descripción de los documentos (versión preliminar)
> [!Note] 
> Project Cortex se encuentra actualmente en versión preliminar. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Document Understanding utiliza modelos AI para automatizar la clasificación de archivos y la extracción de información. Funciona mejor con documentos no estructurados, como cartas o contratos. Los documentos deben tener texto que pueda identificarse en función de frases o patrones. El texto identificado puede designar tanto el tipo de archivo que es (su clasificación) como el que quiere extraer (sus extractores).

Document: los modelos se crean y se administran en un tipo de sitio de SharePoint denominado Centro de contenido. Cuando se aplica a una biblioteca de documentos de SharePoint, el modelo está asociado a un tipo de contenido que tiene columnas para almacenar la información extraída. El tipo de contenido que cree se almacena en la galería de tipos de contenido de SharePoint. También puede optar por usar los tipos de contenido existentes para usar su esquema.

Puede agregar *clasificadores* y *extractores* a su documento que comprenda los modelos para hacer lo siguiente: 

- Los clasificadores se usan para identificar y clasificar los documentos que se cargan en la biblioteca de documentos. Por ejemplo, un clasificador se puede "entrenar" para identificar todos los documentos de *renovación de contratos* que se cargan en la biblioteca. El tipo de contenido de renovación del contrato lo define el usuario al crear el clasificador.

- Los extractores extraen información de estos documentos. Por ejemplo, para todos los documentos de renovación de contratos que se identifican en la biblioteca de documentos, se mostrarán columnas en la vista que también mostrarán la *fecha de inicio del servicio* y el *cliente* para cada documento de renovación de contrato. 

Los archivos de ejemplo se usan para entrenar y probar los clasificadores y los extractores en el modelo. Los archivos de ejemplo proporcionan ejemplos de modelo que deben buscarse al intentar identificar y extraer datos de los archivos. Por ejemplo, puede entrenar a sus clasificadores y extractores de renovación de contratos con ejemplos de documentos de renovación de contratos con los que trabaja su empresa. También puede usar archivos de ejemplo para probar la eficacia del modelo.

Después de publicar el modelo, use el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.  


## <a name="see-also"></a>Consulta también
[Crear un clasificador](create-a-classifier.md)</br>
[Crear un extractor](create-an-extractor.md)</br>
[Crear un centro](create-a-content-center.md) 
 de contenido [Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)</br>
[Aplicar un modelo](apply-a-model.md)   
[Diferencia entre una comprensión de documento y un modelo de procesamiento de formularios](difference-between-document-understanding-and-form-processing-model.md)  
[Introducción al procesamiento de formularios](form-processing-overview.md)




