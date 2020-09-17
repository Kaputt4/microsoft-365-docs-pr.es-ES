---
title: Diferencia entre los modelos de comprensión de documentos y procesamiento de formularios (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Describe la diferencia clave entre los modelos de procesamiento de formularios y la comprensión de documentos.
ms.openlocfilehash: ceea3a6e7898d8971ea458222d6164b496fcb8b7
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950065"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>Diferencia entre los modelos de comprensión de documentos y procesamiento de formularios (versión preliminar)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

La comprensión del contenido en Project Cortex permite identificar y clasificar los documentos que se cargan en bibliotecas de documentos de SharePoint, así como extraer información relevante de cada archivo.  Por ejemplo, a medida que los archivos se cargan en una biblioteca de documentos de SharePoint, todos los archivos que se identifican como *pedidos de compra* se clasifican como tales y se muestran en una vista de biblioteca de documentos personalizada en la que se muestran. Además, puede extraer información específica de cada archivo (por ejemplo, *número de PC* y *total*) y mostrarla en una columna en la vista de la biblioteca de documentos. 


El conocimiento del contenido le permite crear *modelos* para identificar y extraer la información que necesita.  Hay dos tipos de modelos que se pueden usar:

- [Documento sobre modelos](document-understanding-overview.md)
- [Modelos de procesamiento de formularios](form-processing-overview.md)

Aunque ambos modelos se usan por lo general, hay diferencias clave que afectarán a la opción que se puede elegir usar.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Contenido estructurado en lugar de contenido semiestructurado.

Use Document que comprenda los modelos para identificar y extraer datos de documentos no estructurados, como cartas o contratos, donde las entidades de texto que desea extraer residen en oraciones o regiones específicas del documento. Por ejemplo, un documento sin estructurar podría ser una carta de renovación de contrato que puede escribirse de varias formas. Sin embargo, hay información que es coherente en el cuerpo de cada documento de renovación de contrato, como la cadena de texto "fecha de inicio del servicio" seguida de una fecha real.   

Use modelos de procesamiento de formularios para identificar archivos y extraer datos de documentos estructurados o semiestructurados, como formularios o facturas, donde tiene pares clave-valor claros (por ejemplo, *Date: 10/1/2020*) * o datos de tabla. Por ejemplo, un buen candidato para el procesamiento de formularios sería el formulario de solicitud de pedido de una compañía en el que los clientes necesitan proporcionar su información para campos específicos que se encuentran en la misma área del diseño del documento, como *el nombre, el* *número de teléfono*, el *costo total*, etc.  Un formulario de impuestos es un buen ejemplo de un documento estructurado. 

## <a name="where-they-are-created"></a>Dónde se crean

Document: los modelos se crean y administran en un sitio del centro de contenido de SharePoint. Debe tener acceso a un sitio del centro de contenido para crear un documento que comprenda el modelo o para aplicar uno a una biblioteca de documentos de SharePoint. 

Al crear un documento que comprenda el modelo, se crea un nuevo [tipo de contenido de SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) que se guarda en la galería de tipos de contenido de SharePoint. Opcionalmente, puede usar los tipos de contenido existentes para definir el modelo si es necesario.

Los modelos de procesamiento de formularios se crean en PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), pero la creación se inicia directamente desde una biblioteca de documentos de SharePoint. El modelo de procesamiento de formularios debe estar habilitado en la biblioteca de documentos para que un usuario pueda crear un modelo de procesamiento de formularios para el mismo, y un administrador puede hacer esto en el contenido que comprenda la configuración de administración. Los modelos de procesamiento de formularios usan flujos de PowerAutomate para procesar archivos cuando se cargan en la biblioteca de documentos.

Los modelos de procesamiento de formularios también crean nuevos [tipos de contenido de SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), que también se almacenan en la galería de tipos de contenido de SharePoint.

## <a name="where-they-can-be-applied"></a>Dónde se pueden aplicar

Document: los modelos se pueden aplicar a diferentes bibliotecas de documentos de SharePoint a las que tiene acceso. Puede usar el centro de contenido no solo para crear un documento que comprenda el modelo, sino también para aplicarlo a diferentes bibliotecas de documentos. El centro de contenido ofrece un control más central sobre cómo se usan los modelos de comprensión de los modelos y dónde se aplican, ya que esta información debe acumularse en un centro de contenido.

Actualmente, los modelos de procesamiento de formularios solo se pueden aplicar a la biblioteca de documentos de SharePoint desde la que se crearon. Esto permite que cualquier usuario con licencia que tenga acceso al sitio cree un modelo de procesamiento de formularios.




 ## <a name="see-also"></a>Vea también
[Aprendizaje: mejorar el rendimiento empresarial con el generador de AI](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Crear un clasificador](create-a-classifier.md)</br>
[Crear un extractor](create-an-extractor.md)</br>
[Aplicación de un documento con información sobre el modelo](apply-a-model.md)</br>
[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)</br>



  
  



