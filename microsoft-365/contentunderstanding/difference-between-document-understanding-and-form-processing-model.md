---
title: Comparación de modelos personalizados en Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris
audience: admin
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre las diferencias clave entre los modelos personalizados en Microsoft Syntex.
ms.openlocfilehash: 4ac3254b1351ebc9edfef744943f933a4916fe29
ms.sourcegitcommit: a88aadf5786f1bd9e5bae763f603a2b690473322
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68817529"
---
# <a name="compare-custom-models-in-microsoft-syntex"></a>Comparación de modelos personalizados en Microsoft Syntex 

Use la tabla siguiente para ver las diferencias en los modelos personalizados para ayudar a identificar el modelo más adecuado para sus necesidades.

| Característica | Procesamiento de documentos no estructurados | Procesamiento de documentos de forma libre | Procesamiento estructurado de documentos |
| ------- | ------- | ------- | ------- |
| Usar para este tipo de contenido | Formatos de archivo no estructurados o semiestructurados, por ejemplo, documentos de Office en los que hay diferencias en el diseño, pero sigue siendo información similar que se va a extraer. | Formatos de archivo no estructurados y de forma libre, por ejemplo, documentos que no tienen ninguna estructura establecida, como cartas, contratos e instrucciones de trabajo. | Formatos de archivo estructurados y semiestructurados, por ejemplo, archivos PDF para el contenido de formularios, como facturas o pedidos de compra, donde el diseño y el formato son similares. |
| Método de entrenamiento | Método de enseñanza | Método de selección de forma libre | Layout (método) |
| Creación de modelos | Modelo creado en SharePoint en un sitio nuevo, el centro de contenido.  | Modelo creado en [AI Builder](/ai-builder/overview) con acceso sin problemas desde la biblioteca de documentos de SharePoint.| Modelo creado en [AI Builder](/ai-builder/overview) con acceso sin problemas desde la biblioteca de documentos de SharePoint. |
| Tipo de clasificación | Clasificador que se puede entrenar con extractores opcionales mediante el aprendizaje automático para asignar la ubicación de documentos en los que se extraen datos. | No aplicable | No aplicable |
| Ubicaciones | Se puede aplicar a múltiples bibliotecas. | Se puede aplicar a múltiples bibliotecas. | Se puede aplicar a múltiples bibliotecas. |
| Tipos de archivo compatibles | Entrene entre 5 y 10 .pdf, Office o archivos de correo electrónico, incluidos ejemplos negativos.<br>Los archivos de Office se truncan con 64 000 caracteres. Los archivos escaneados por OCR están limitados a 20 páginas. Admite más de 20 tipos de archivo. Consulte [los tipos de archivo admitidos](requirements-and-limitations.md#unstructured-document-processing).  | Entrene en formato .pdf, .jpg o .png, en total 50 MB y 500 páginas. | Entrene en formato .pdf, .jpg o .png, en total 50 MB y 500 páginas. |
| Integración con metadatos administrados | Sí, mediante la formación del extractor de entidades que hace referencia a un campo de metadatos administrados configurados. | No | No |
| Integración de características de cumplimiento con Microsoft Purview Information Protection | Establezca etiquetas de retención publicadas.<br>Establecer etiquetas de confidencialidad publicadas. | El establecimiento de etiquetas de retención está llegando. <br>Se acerca el establecimiento de etiquetas de confidencialidad. | Establezca etiquetas de retención publicadas. <br>Se acerca el establecimiento de etiquetas de confidencialidad. |
| Regiones admitidas| Disponible en todas las regiones. | Se basa en Power Platform. Para obtener información sobre la disponibilidad global para Power Platform y AI Builder, consulta [disponibilidad de Power Platform](https://dynamics.microsoft.com/geographic-availability/). | Se basa en Power Platform. Para obtener información sobre la disponibilidad global para Power Platform y AI Builder, consulta [disponibilidad de Power Platform](https://dynamics.microsoft.com/geographic-availability/). |
| Gastos transaccionales | No aplicable | Usar créditos de AI Builder.<br>Se incluyen 3500 créditos por cada licencia de Syntex al mes.<br>1 millón de créditos permitirán el procesamiento de 2000 páginas de archivos. | Usar créditos de AI Builder.<br>Se incluyen 3500 créditos por cada licencia de Syntex al mes.<br>1 millón de créditos permitirán el procesamiento de 2000 páginas de archivos. |
| Capacidad | No hay restricciones de capacidad. | Usa el entorno de Power Platform predeterminado (entornos personalizados con soporte para la base de datos de Dataverse). | Usa el entorno de Power Platform predeterminado (entornos personalizados con soporte para la base de datos de Dataverse). |
| Idiomas admitidos| Los modelos funcionan en todos los idiomas del alfabeto latino. Además de inglés: alemán, sueco, francés, español, italiano y portugués. | La compatibilidad con el idioma actual es para inglés. | Compatibilidad con [idiomas para 73 idiomas](/ai-builder/form-processing-model-requirements.md#languages-supported). |

## <a name="see-also"></a>Vea también

[Aprendizaje: mejorar el rendimiento empresarial con AI Builder](/training/paths/improve-business-performance-ai-builder/?source=learn)


