---
title: Introducción a los modelos precompilado en Microsoft SharePoint Syntex
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
ms.openlocfilehash: 1146e4947392ce0e0848632e55f22e5b8b8d2d91
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569056"
---
# <a name="prebuilt-models-overview-in-microsoft-sharepoint-syntex"></a>Introducción a los modelos precompilado en Microsoft SharePoint Syntex

Además de comprender [los modelos de](document-understanding-overview.md) documentos y los modelos de procesamiento de [formularios,](form-processing-overview.md) SharePoint Syntex modelos precompilado para automatizar la extracción de información.

Los modelos precompilados están previamente entrenados para reconocer documentos y la información estructurada de los documentos. En lugar de tener que crear un nuevo modelo personalizado desde cero, puede iterar en un modelo preentrenado existente para agregar campos específicos que se ajusten a las necesidades de su organización. 

Los modelos precompilado usan el reconocimiento óptico de caracteres (OCR) combinado con modelos de aprendizaje profundo para identificar y extraer campos de datos y texto predefinidos comunes a tipos de documentos específicos. Para empezar, analice uno de los archivos en el modelo precompilado. A continuación, seleccione los campos detectados que tienen sentido para su propósito. Si el modelo no detecta los campos que necesita, puede analizar de nuevo mediante un archivo diferente.

Al igual que los modelos de descripción de documentos, los modelos precompilado se crean y administran en el [centro de contenido](create-a-content-center.md). Cuando se aplica a una SharePoint de documentos, el modelo está asociado con un tipo de contenido y tiene columnas para almacenar la información que se extrae. 

Después de publicar el modelo, utilice el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.  

## <a name="requirements"></a>Requirements

- Formatos de archivo compatibles: JPEG, PNG, BMP, TIFF y PDF (incrustados en texto o escaneados).

- Idiomas admitidos: actualmente solo se admiten las facturas en inglés Estados Unidos de la cuenta. Se admiten los recibos de ventas en inglés de Australia, Canadá, Estados Unidos, Gran Bretaña e India.

- Los ARCHIVOS PDF incrustados en texto son los mejores para eliminar la posibilidad de error en la extracción y ubicación de caracteres.

- Para PDF y TIFF, se pueden procesar hasta 2.000 páginas.

- El tamaño del archivo debe ser inferior a 50 MB.

- Las dimensiones de la imagen deben estar entre 50 x 50 píxeles y 10 000 x 10 000 píxeles.

- Las dimensiones de PDF son de hasta 17 x 17 pulgadas, correspondientes al tamaño de papel Legal o A3, o menor.

- El tamaño total de los datos de aprendizaje es de 500 páginas o menos.

### <a name="file-limitations"></a>Limitaciones de archivos

Tenga en cuenta las siguientes diferencias Microsoft Office archivos basados en texto y archivos examinados por OCR (PDF, imagen o TIFF):

- Office: truncados a 64.000 caracteres (cuando se ejecutan en archivos de una biblioteca de documentos).

- Archivos digitalizados con OCR: hay un límite de 20 páginas.  

## <a name="model-considerations"></a>Consideraciones del modelo

- Si se aplican dos o más modelos precompilados a la misma biblioteca, el archivo se clasifica con el modelo que tiene la puntuación de confianza media más alta. Las entidades extraídas solo serán del modelo aplicado.

- Si se aplica un modelo precompilado a una biblioteca que tiene un modelo de comprensión de documentos, el archivo se clasifica mediante el modelo de comprensión de documentos y los extractores capacitados para ese modelo. Si hay columnas vacías que coincidan con el modelo precompilado, las columnas se rellenarán con esos valores extraídos.

- Si se aplica un modelo precompilado a una biblioteca que tiene un modelo de procesamiento de formulario personalizado, el archivo se clasifica mediante el modelo precompilado y los extractores detectados para ese modelo. Si hay columnas vacías que coincidan con el modelo de procesamiento de formularios, las columnas se rellenarán con esos valores extraídos.

- No se admite la aplicación de más de un modelo de procesamiento de formularios personalizado a una biblioteca.


## <a name="see-also"></a>Consulta también

[Usar un modelo precompilado para extraer información de facturas o recibos](prebuilt-overview.md)
 

