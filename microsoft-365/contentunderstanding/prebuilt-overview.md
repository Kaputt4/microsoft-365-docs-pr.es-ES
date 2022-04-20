---
title: Introducción a los modelos creados previamente en Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.customer: intro-overview
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre los modelos precompilados en Microsoft SharePoint Syntex.
ms.openlocfilehash: d43a608885864f5c81a8938010a0a52a2c4998a6
ms.sourcegitcommit: dc415d784226c77549ba246601f34324c4f94e73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64916235"
---
# <a name="prebuilt-models-overview-in-microsoft-sharepoint-syntex"></a>Introducción a los modelos creados previamente en Microsoft SharePoint Syntex

Además de [documentar los modelos de comprensión](document-understanding-overview.md) y [los modelos de procesamiento de formularios](form-processing-overview.md), SharePoint Syntex proporciona modelos precompilados para automatizar la extracción de información.

Los modelos precompilados se entrenan previamente para reconocer los documentos y la información estructurada de los documentos. En lugar de tener que crear un nuevo modelo personalizado desde cero, puede iterar en un modelo previamente entrenado existente para agregar campos específicos que se ajusten a las necesidades de su organización. 

Los modelos precompilados usan el reconocimiento óptico de caracteres (OCR) combinado con modelos de aprendizaje profundo para identificar y extraer campos de datos y texto predefinidos comunes a tipos de documentos específicos. Para empezar, analice uno de los archivos en el modelo precompilado. A continuación, seleccione los campos detectados que tengan sentido para su propósito. Si el modelo no detecta los campos que necesita, puede analizarlo de nuevo mediante un archivo diferente.

Al igual que los modelos de comprensión de documentos, los modelos precompilados se crean y administran en el [centro de contenido](create-a-content-center.md). Cuando se aplica a una biblioteca de documentos SharePoint, el modelo está asociado a un tipo de contenido y tiene columnas para almacenar la información que se va a extraer. 

Después de publicar el modelo, utilice el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.  

## <a name="requirements"></a>Requisitos

- Formatos de archivo admitidos: JPEG, PNG, BMP, TIFF y PDF (texto incrustado o escaneado).

- Idiomas admitidos: actualmente solo se admiten facturas en inglés de la Estados Unidos. Se admiten los recibos de ventas en inglés de Australia, Canadá, Estados Unidos, Gran Bretaña e India.

- Los archivos PDF incrustados en texto son mejores para eliminar la posibilidad de error en la extracción y ubicación de caracteres.

- Para PDF y TIFF, se pueden procesar hasta 2000 páginas.

- El tamaño del archivo debe ser inferior a 50 MB.

- Las dimensiones de imagen deben estar entre 50 x 50 píxeles y 10 000 x 10 000 píxeles.

- Las dimensiones pdf son de hasta 17 x 17 pulgadas, correspondientes al tamaño de papel Legal o A3, o más pequeños.

- El tamaño total de los datos de entrenamiento es de 500 páginas o menos.

### <a name="file-limitations"></a>Limitaciones de archivos

Tenga en cuenta las siguientes diferencias sobre Microsoft Office archivos basados en texto y archivos escaneados con OCR (PDF, imagen o TIFF):

- Office archivos: truncados con 64 000 caracteres (cuando se ejecutan en archivos de una biblioteca de documentos).

- Archivos digitalizados con OCR: hay un límite de 20 páginas.  

## <a name="model-considerations"></a>Consideraciones sobre el modelo

- Si se aplican dos o más modelos precompilados a la misma biblioteca, el archivo se clasifica mediante el modelo que tiene la puntuación de confianza media más alta. Las entidades extraídas serán solo del modelo aplicado.

- Si un modelo precompilado se aplica a una biblioteca que tiene un modelo de comprensión de documentos, el archivo se clasifica mediante el modelo de comprensión de documentos y los extractores entrenados para ese modelo. Si hay columnas vacías que coincidan con el modelo precompilado, las columnas se rellenarán con esos valores extraídos.

- Si se aplica un modelo precompilado a una biblioteca que tiene un modelo de procesamiento de formulario personalizado, el archivo se clasifica mediante el modelo precompilado y los extractores detectados para ese modelo. Si hay columnas vacías que coincidan con el modelo de procesamiento de formularios, las columnas se rellenarán con esos valores extraídos.

- No se admite la aplicación de más de un modelo de procesamiento de formulario personalizado a una biblioteca.


## <a name="see-also"></a>Ver también

[Uso de un modelo precompilado para extraer información de facturas o recibos](prebuilt-overview.md)
 

