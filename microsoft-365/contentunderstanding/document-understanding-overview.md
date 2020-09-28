---
title: Información general sobre el documento
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información general sobre la descripción de los documentos en Microsoft SharePoint Syntex.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294765"
---
# <a name="document-understanding-overview"></a>Información general sobre el documento


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Document Understanding utiliza modelos de inteligencia artificial (AI) para automatizar la clasificación de archivos y la extracción de información. Funciona mejor con documentos no estructurados, como cartas o contratos. Estos documentos deben tener texto que pueda identificarse en función de frases o patrones. El texto identificado designa tanto el tipo de archivo (su clasificación) como el que desea extraer (sus extractores).

Document: los modelos se crean y se administran en un tipo de sitio de SharePoint denominado *centro de contenido*. Cuando se aplica a una biblioteca de documentos de SharePoint, el modelo está asociado a un tipo de contenido que tiene columnas para almacenar la información que se va a extraer. El tipo de contenido que cree se almacena en la galería de tipos de contenido de SharePoint. También puede optar por usar los tipos de contenido existentes para usar su esquema.

Agregue *clasificadores* y *extractores* a su documento que comprenda los modelos para hacer lo siguiente: 

- Los clasificadores se usan para identificar y clasificar los documentos que se cargan en la biblioteca de documentos. Por ejemplo, un clasificador se puede "entrenar" para identificar todos los documentos de *renovación de contratos* que se cargan en la biblioteca. El tipo de contenido de renovación del contrato lo define el usuario al crear el clasificador.

- Los extractores extraen información de estos documentos. Por ejemplo, para todos los documentos de renovación de contratos identificados en la biblioteca de documentos, las columnas se muestran en la vista que también muestran la *fecha de inicio del servicio* y el  *cliente* para cada documento de renovación de contrato. 

Puede usar archivos de ejemplo para entrenar y probar los clasificadores y los extractores en el modelo. Los archivos de ejemplo proporcionan ejemplos de modelo que deben buscarse al intentar identificar y extraer datos de los archivos. Por ejemplo, puede entrenar a sus clasificadores y extractores de renovación de contratos con muestras de documentos de renovación de contratos con los que trabaja su empresa. También puede usar archivos de ejemplo para probar la eficacia del modelo.

Después de publicar el modelo, use el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.  


## <a name="see-also"></a>Consulte también
[Crear un clasificador](create-a-classifier.md)</br>
[Crear un extractor](create-an-extractor.md)</br>
[Crear un centro](create-a-content-center.md) 
 de contenido [Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)</br>
[Aplicar un modelo](apply-a-model.md)   
[Diferencia entre una comprensión de documento y un modelo de procesamiento de formularios](difference-between-document-understanding-and-form-processing-model.md)  
[Introducción al procesamiento de formularios](form-processing-overview.md)
