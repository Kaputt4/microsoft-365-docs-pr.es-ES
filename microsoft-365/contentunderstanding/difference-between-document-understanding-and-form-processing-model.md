---
title: Diferencias entre los modelos de comprensión de documentos y los modelos de procesamiento de formularios
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
description: Describe las diferencias clave entre los modelos de comprensión de documentos y los modelos de procesamiento de formularios
ms.openlocfilehash: 555dfa7d76335a3b943e860e5f41ed64c9d3e874
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50596985"
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

Use modelos de comprensión mediante documentos para identificar y extraer los datos de documentos no estructurados, como cartas o contratos, donde las entidades de texto que quiere extraer se encuentran en frases o regiones específicas del documento. Por ejemplo, un documento no estructurado podría ser una carta de renovación de contrato que pueda escribirse de varias maneras. Sin embargo, en el cuerpo de cada documento se encuentra habitualmente información de renovación de contrato, como la cadena de texto *Fecha de inicio de un servicio* seguida de una fecha.

Use modelos de procesamiento de formularios para identificar archivos y extraer datos de documentos estructurados o semiestructurados, como formularios o facturas. Los modelos de procesamiento de formularios están capacitados para comprender el diseño de su formulario a partir de documentos de ejemplo y aprenden a buscar los datos que necesita extraer de ubicaciones similares. Los formularios habitualmente tienen un diseño más estructurado en el que las entidades están en la misma ubicación (por ejemplo, un número de la seguridad social en un formulario tributario).

> [!NOTE]
> Debe tener acceso a un sitio de centro de contenido para crear un modelo de comprensión mediante documentos o para aplicar uno a una biblioteca de documentos de SharePoint. 


## <a name="where-models-are-created"></a>Dónde se crean los modelos 

Los modelos de comprensión mediante documentos se crean y administran en un sitio de centro de contenido de SharePoint. 

> [!NOTE]
> Para obtener más información sobre los documentos de entrada, consulte [Requisitos y limitaciones del modelo de procesamiento de formularios](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

Los modelos de procesamiento de formularios se crean en el generador de IA [AI Builder](https://docs.microsoft.com/ai-builder/overview) de PowerApps, pero la creación se inicia directamente desde una biblioteca de documentos de SharePoint. Una biblioteca de documentos debe tener habilitada la creación de un modelo de procesamiento de formularios antes de que un usuario pueda crear un modelo de procesamiento de formularios para ella. Los administradores pueden habilitar la creación de modelos de procesamiento de formularios en la configuración de administrador de comprensión de contenido. Los modelos de procesamiento de formularios usan flujos de PowerAutomate para procesar archivos cuando se cargan en la biblioteca de documentos.

Cuando se crea modelo de comprensión mediante documentos, se crea un nuevo [tipo de contenido de SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) que se guarda en la galería de tipos de contenido de SharePoint. También puede usar tipos de contenido existentes para definir el modelo, si es necesario.

Los modelos de procesamiento de formularios también crean nuevos [Tipos de contenido de SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) y se almacenan en la galería de Tipos de contenido de SharePoint.

## <a name="where-they-can-be-applied"></a>Dónde se pueden aplicar

Puede aplicar modelos de comprensión mediante documentos a las bibliotecas de documentos de SharePoint a las que tenga acceso. Use el centro de contenido para crear un modelo de comprensión mediante documentos y aplíquelo a otras bibliotecas de documentos. El centro de contenido le ofrece un control más centralizado sobre cómo se usan los modelos de comprensión mediante documentos y cómo se aplican. Nota: Esta información también debe resumirse en un centro de contenido.

Actualmente, los modelos de procesamiento de formularios solo se pueden aplicar a la biblioteca de documentos de SharePoint desde la que los creó. Esto permite a los usuarios con licencia y acceso al sitio crear un modelo de procesamiento de formularios. Tenga en cuenta que un administrador necesita habilitar el procesamiento de formularios en una biblioteca de documentos de SharePoint para que esté disponible para los usuarios con licencia.

## <a name="comparison-of-forms-processing-and-document-understanding"></a>Comparación del procesamiento de formularios y la comprensión mediante documentos

Use la siguiente tabla para comprender cuándo se usa el procesamiento de formularios y cuándo, la comprensión mediante documentos:

| Característica | Procesamiento de formularios | Comprensión mediante documentos |
| ------- | ------- | ------- |
| Tipo de modelo según cuándo se usa cada uno | Se utilizaba para formatos de archivo semiestructurados, por ejemplo documentos de Office en los que hay diferencias en el diseño pero del que se extrae igualmente información parecida. | Se utilizaba para formatos de archivo no estructurados, por ejemplo PDF con contenido de formularios como facturas u órdenes de encargo en los que el diseño y el formato son parecidos. |
| Creación de modelos | Modelo creado en AI Builder con un acceso directo desde la biblioteca de documentos de SharePoint.| Modelo creado en una compilación de interfaz nativa en el Centro de contenido de SharePoint.|
| Tipo de clasificación| Clasificador configurable en el que el aprendizaje automático se usa para proporcionar sugerencias a los sistemas en el que se extraen datos.| Clasificador que se puede entrenar con extractores opcionales mediante el aprendizaje automático para diseñar la ubicación de documentos en los que se extrae datos.|
| Ubicaciones | Restringido a una única biblioteca de documentos simple al menos que se use Power Platform para recuperar del CDS.| Se puede aplicar a múltiples bibliotecas.|
| Tipos de archivo compatibles| Entrenado en formatos PDF, JPG y PNG, 50 MB y 500 páginas.| Entrenado en 5-10 archivos de PDF, Office o correo electrónico, incluyendo ejemplos negativos.<br>Los archivos de Office están truncados a 64 k caracteres. Los archivos escaneados por OCR están limitados a 20 páginas.|
| Integrar con Metadatos administrados | No | Sí, a través de la configuración de las columnas de la biblioteca de documentos antes del modelo de aprendizaje.|
| Integración de las características de cumplimiento cuando Microsoft Information Protection está habilitado | Conjunto de etiquetas de retención<br>El conjunto de etiquetas de confidencialidad estará disponible próximamente | Conjunto de etiquetas de retención<br>El conjunto de etiquetas de confidencialidad estará disponible próximamente |
| Regiones compatibles| Procesamiento de formularios basado en Power Platform. Para obtener información sobre la disponibilidad global para Power Platform y AI Builder, consulta [disponibilidad de Power Platform](https://dynamics.microsoft.com/geographic-availability/). | Disponible en todas las regiones.|
| Gastos transaccionales | Usar créditos de AI Builder.<br>Los créditos se pueden comprar en los de 1 M.<br>Los créditos de 1 M están incluidos en la compra de más de 300 licencias de SharePoint Syntex.<br>Los créditos de 1 M permitirán procesar 2000 páginas de archivos.| N/D |
| Capacidad | Aprovisionado contra el entorno de servicios predeterminado de los datos comunes.| No hay restricciones de capacidad.|
| Idiomas admitidos| Inglés <br>Próximamente, en 2021: español, alemán, francés e italiano| Trabajo de modelos en todos los lenguajes con alfabeto latino. Además de inglés: alemán, sueco, francés, español, italiano y portugués.|

## <a name="see-also"></a>Consulte también
[Aprendizaje: mejorar el rendimiento empresarial con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Información general sobre la comprensión mediante documentos](document-understanding-overview.md)

[Información general sobre el procesamiento de formularios](form-processing-overview.md)

[Introducción a SharePoint Syntex](index.md)
