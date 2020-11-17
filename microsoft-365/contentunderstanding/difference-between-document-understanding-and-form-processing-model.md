---
title: Diferencias entre los modelos de comprensión de documentos y los modelos de procesamiento de formularios
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Describe las diferencias clave entre los modelos de comprensión de documentos y los modelos de procesamiento de formularios
ms.openlocfilehash: e847ed9b7a00e0ff0542ad3b9ba35c314070837d
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087636"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Diferencias entre los modelos de comprensión de documentos y los modelos de procesamiento de formularios 


La comprensión de contenidos en Microsoft SharePoint Syntex le permite identificar y clasificar documentos cargados en bibliotecas de documentos de SharePoint, así como extraer información relevante de cada archivo.  Por ejemplo, a medida que se carguen los archivos en una biblioteca de documentos de SharePoint, todos los archivos identificados como *Órdenes de compra* se clasifican como tales y, a continuación, se muestran en una vista personalizada de una biblioteca de documentos. Además, puede extraer información específica de cada archivo (por ejemplo, *Número de pedido de compra* y *Total*) y mostrarlo como una columna en la vista de la biblioteca de documentos. 

La comprensión de contenidos le permite crear *modelos* para identificar y extraer la información que necesita. Los modelos ayudan a solucionar problemas de búsqueda, procesos empresariales, cumplimiento normativo y muchas otras cosas.

Hay dos tipos de modelo que puede usar:

- [Modelos de comprensión mediante documentos](document-understanding-overview.md)
- [Modelos de procesamiento de formularios](form-processing-overview.md)

Aunque los dos modelos se usan generalmente para el mismo propósito, las siguientes diferencias clave afectan a su uso.

> [!NOTE]
> Consulte la guía [Adopción de SharePoint Syntex: Introducción](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) para obtener más información sobre el procesamiento de formularios y ejemplos de escenarios de comprensión mediante documentos.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Contenido estructurado, no estructurado y semiestructurado

Use modelos de comprensión mediante documentos para identificar y extraer los datos de documentos no estructurados como, por ejemplo, cartas o contratos, donde las entidades de texto que desea extraer se encuentran en frases o regiones específicas del documento. Por ejemplo, un documento no estructurado podría ser una carta de renovación de contrato que pueda escribirse de varias maneras. Sin embargo, en el cuerpo de cada documento se encuentra habitualmente información de renovación de contrato, como la cadena de texto *Fecha de inicio de un servicio* seguida de una fecha.   

Use modelos de procesamiento de formularios para identificar archivos y extraer datos de documentos estructurados o semiestructurados, como formularios o facturas. Los modelos de procesamiento de formularios están capacitados para comprender el diseño de su formulario a partir de documentos de ejemplo y aprenden a buscar los datos que necesita extraer de ubicaciones similares, ya que los formularios tienen un diseño más estructurado en el que las entidades están en la misma ubicación (por ejemplo, un número de la seguridad social en un formulario tributario). 

> [!NOTE]
> Debe tener acceso a un sitio de centro de contenido para crear un modelo de comprensión mediante documentos o para aplicar uno a una biblioteca de documentos de SharePoint. 


## <a name="where-they-are-created"></a>Dónde se crean

Los modelos de comprensión mediante documentos se crean y administran en un sitio de centro de contenido de SharePoint. 

> [!NOTE]
> Para obtener más información sobre los documentos de entrada, consulte [Requisitos y limitaciones del modelo de procesamiento de formularios](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

Los modelos de procesamiento de formularios se crean en el generador de archivos [AI Builder](https://docs.microsoft.com/ai-builder/overview) de PowerApps, pero la creación se inicia directamente desde una Biblioteca de documentos de SharePoint. Se debe habilitar la creación del modelo de procesamiento de formularios en la biblioteca de documentos para que un usuario pueda crear un modelo de procesamiento de formularios para ella y un administrador puede hacerlo en la configuración de administrador de comprensión de contenidos. Los modelos de procesamiento de formularios usan flujos de PowerAutomate para procesar archivos cuando se cargan en la biblioteca de documentos.

Cuando se crea modelo de comprensión mediante documentos, se crea un nuevo [tipo de contenido de SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) que se guarda en la galería de tipos de contenido de SharePoint. También puede usar tipos de contenido existentes para definir el modelo, si es necesario.

Los modelos de procesamiento de formularios también crean nuevos [Tipos de contenido de SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) y se almacenan en la galería de Tipos de contenido de SharePoint.

## <a name="where-they-can-be-applied"></a>Dónde se pueden aplicar

Puede aplicar modelos de comprensión mediante documentos a las bibliotecas de documentos de SharePoint a las que tenga acceso. Use el centro de contenido para crear un modelo de comprensión mediante documentos y aplíquelo a otras bibliotecas de documentos. El centro de contenido le ofrece un control más centralizado sobre cómo se usan los modelos de comprensión mediante documentos y cómo se aplican. Nota: Esta información también debe resumirse en un centro de contenido.

Actualmente, los modelos de procesamiento de formularios solo se pueden aplicar a la biblioteca de documentos de SharePoint desde la que los creó. Esto permite a los usuarios con licencia de acceso al sitio crear un modelo de procesamiento de formularios. Tenga en cuenta que el administrador necesita habilitar el procesamiento de formularios en una biblioteca de documentos de SharePoint para que esté disponible para los usuarios con licencia.

 ## <a name="see-also"></a>Consulte también
[Aprendizaje: mejorar el rendimiento empresarial con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Información general sobre la comprensión mediante documentos](document-understanding-overview.md)

[Información general sobre el procesamiento de formularios](form-processing-overview.md)

[Introducción a SharePoint Syntex](index.md)
