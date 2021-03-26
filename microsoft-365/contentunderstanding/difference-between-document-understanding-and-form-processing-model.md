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
ms.openlocfilehash: f12cc46e1ffcbc610f50ba327e22ad46a2591521
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222274"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Diferencias entre los modelos de comprensión de documentos y los modelos de procesamiento de formularios 


La comprensión de contenidos en Microsoft SharePoint Syntex le permite identificar y clasificar documentos cargados en bibliotecas de documentos de SharePoint, así como extraer información relevante de cada archivo.  Por ejemplo, a medida que se carguen los archivos en una biblioteca de documentos de SharePoint, todos los archivos identificados como *Órdenes de compra* se clasifican como tales y, a continuación, se muestran en una vista personalizada de una biblioteca de documentos. Además, puede extraer información específica de cada archivo (por ejemplo, *Número de pedido de compra* y *Total*) y mostrarlo como una columna en la vista de la biblioteca de documentos. 

La comprensión de contenidos le permite crear *modelos* para identificar y extraer la información que necesita. Los modelos ayudan a solucionar problemas de búsqueda, procesos empresariales, cumplimiento normativo y muchas otras cosas.

Hay dos tipos de modelo que puede usar:

- [Modelos de comprensión mediante documentos](document-understanding-overview.md)
- [Modelos de procesamiento de formularios](form-processing-overview.md)

Aunque los dos modelos se usan generalmente para el mismo propósito, las siguientes diferencias clave afectan a su uso.

> [!NOTE]
> Consulte la guía [Adopción de SharePoint Syntex: Introducción](./adoption-getstarted.md) para obtener más información sobre el procesamiento de formularios y ejemplos de escenarios de comprensión mediante documentos.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Contenido estructurado, no estructurado y semiestructurado

Use modelos de comprensión mediante documentos para identificar y extraer los datos de documentos no estructurados, como cartas o contratos, donde las entidades de texto que quiere extraer se encuentran en frases o regiones específicas del documento. Por ejemplo, un documento no estructurado podría ser una carta de renovación de contrato que pueda escribirse de varias maneras. Sin embargo, en el cuerpo de cada documento se encuentra habitualmente información de renovación de contrato, como la cadena de texto *Fecha de inicio de un servicio* seguida de una fecha.

Use modelos de procesamiento de formularios para identificar archivos y extraer datos de documentos estructurados o semiestructurados, como formularios o facturas. Los modelos de procesamiento de formularios están capacitados para comprender el diseño de su formulario a partir de documentos de ejemplo y aprenden a buscar los datos que necesita extraer de ubicaciones similares. Los formularios habitualmente tienen un diseño más estructurado en el que las entidades están en la misma ubicación (por ejemplo, un número de la seguridad social en un formulario tributario).

> [!NOTE]
> Debe tener acceso a un sitio de centro de contenido para crear un modelo de comprensión mediante documentos o para aplicar uno a una biblioteca de documentos de SharePoint. 


## <a name="where-models-are-created"></a>Dónde se crean los modelos 

Los modelos de comprensión mediante documentos se crean y administran en un sitio de centro de contenido de SharePoint. 

> [!NOTE]
> Para obtener más información sobre los documentos de entrada, consulte [Requisitos y limitaciones del modelo de procesamiento de formularios](/ai-builder/form-processing-model-requirements). 

Los modelos de procesamiento de formularios se crean en el generador de IA [AI Builder](/ai-builder/overview) de PowerApps, pero la creación se inicia directamente desde una biblioteca de documentos de SharePoint. Una biblioteca de documentos debe tener habilitada la creación de un modelo de procesamiento de formularios antes de que un usuario pueda crear un modelo de procesamiento de formularios para ella. Los administradores pueden habilitar la creación de modelos de procesamiento de formularios en la configuración de administrador de comprensión de contenido. Los modelos de procesamiento de formularios usan flujos de PowerAutomate para procesar archivos cuando se cargan en la biblioteca de documentos.

Cuando se crea modelo de comprensión mediante documentos, se crea un nuevo [tipo de contenido de SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) que se guarda en la galería de tipos de contenido de SharePoint. También puede usar tipos de contenido existentes para definir el modelo, si es necesario.

Los modelos de procesamiento de formularios también crean nuevos [Tipos de contenido de SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) y se almacenan en la galería de Tipos de contenido de SharePoint.

## <a name="where-they-can-be-applied"></a>Dónde se pueden aplicar

Puede aplicar modelos de comprensión mediante documentos a las bibliotecas de documentos de SharePoint a las que tenga acceso. Use el centro de contenido para crear un modelo de comprensión mediante documentos y aplíquelo a otras bibliotecas de documentos. El centro de contenido le ofrece un control más centralizado sobre cómo se usan los modelos de comprensión mediante documentos y cómo se aplican. Nota: Esta información también debe resumirse en un centro de contenido.

Actualmente, los modelos de procesamiento de formularios solo se pueden aplicar a la biblioteca de documentos de SharePoint desde la que los creó. Esto permite a los usuarios con licencia y acceso al sitio crear un modelo de procesamiento de formularios. Tenga en cuenta que un administrador necesita habilitar el procesamiento de formularios en una biblioteca de documentos de SharePoint para que esté disponible para los usuarios con licencia.

## <a name="comparison-of-forms-processing-and-document-understanding"></a>Comparación del procesamiento de formularios y la comprensión mediante documentos

Use la siguiente tabla para comprender cuándo se usa el procesamiento de formularios y cuándo, la comprensión mediante documentos:

| Característica | Procesamiento de formularios | Comprensión mediante documentos |
| ------- | ------- | ------- |
| Tipo de modelo; cuándo se usa cada uno | Se usa para formatos de archivo semiestructurados, como PDF con contenido de formularios como facturas u pedidos de compra en los que el diseño y el formato son parecidos.  | Se usa para formatos de archivo semiestructurados, como documentos de Office en los que hay diferencias en el diseño pero de los que se extrae igualmente información parecida. |
| Creación de modelos | Modelo creado en generador de IA con un acceso directo desde la biblioteca de documentos de SharePoint.| Modelo creado en SharePoint en un sitio nuevo, el centro de contenido. |
| Tipo de clasificación| El clasificador configurable se usa para proporcionar sugerencias a los sistemas sobre los datos que se extraen.| Clasificador que se puede entrenar con extractores opcionales mediante el aprendizaje automático para asignar la ubicación de documentos en los que se extraen datos.|
| Ubicaciones | Capacitado para una única biblioteca de documentos.| Se puede aplicar a múltiples bibliotecas.|
| Tipos de archivo compatibles| Entrenado en formatos PDF, JPG y PNG, 50 MB y 500 páginas.| Entrenado en 5-10 archivos de PDF, Office o correo electrónico, incluyendo ejemplos negativos.<br>Los archivos de Office están truncados a 64 k caracteres. Los archivos escaneados por OCR están limitados a 20 páginas.|
| Integrar con Metadatos administrados | No | Sí, mediante la formación del extractor de entidades que hace referencia a un campo de metadatos administrados configurados.|
| Integración de las características de cumplimiento cuando Microsoft Information Protection está habilitado | Establecer etiquetas de retención publicadas.<br>La opción de establecer etiquetas de confidencialidad estará disponible próximamente | Establecer etiquetas de retención publicadas.<br>La opción de establecer etiquetas de confidencialidad estará disponible próximamente |
| Regiones compatibles| Procesamiento de formularios basado en Power Platform. Para obtener información sobre la disponibilidad global para Power Platform y AI Builder, consulta [disponibilidad de Power Platform](https://dynamics.microsoft.com/geographic-availability/). | Disponible en todas las regiones.|
| Gastos transaccionales | Usar créditos de AI Builder.<br>Los créditos se pueden comprar en los de 1 M.<br>Los créditos de 1 M están incluidos en la compra de más de 300 licencias de SharePoint Syntex.<br>Los créditos de 1 M permitirán procesar 2000 páginas de archivos.<br>| N/D |
| Capacidad | Usa el entorno de Power Platform predeterminado (entornos personalizados con soporte para la base de datos de Dataverse). | No tiene restricciones de capacidad.|
| Idiomas admitidos| Inglés <br>Próximamente en 2021: Idiomas del alfabeto latino | Los modelos funcionan en todos los idiomas del alfabeto latino. Además de inglés: alemán, sueco, francés, español, italiano y portugués.|

## <a name="see-also"></a>Consulte también
[Aprendizaje: mejorar el rendimiento empresarial con AI Builder](/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Información general sobre la comprensión mediante documentos](document-understanding-overview.md)

[Información general sobre el procesamiento de formularios](form-processing-overview.md)

[Introducción a SharePoint Syntex](index.md)