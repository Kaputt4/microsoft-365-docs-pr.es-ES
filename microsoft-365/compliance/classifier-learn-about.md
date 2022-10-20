---
title: Obtenga información sobre los clasificadores entrenables
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- highpri
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- highpri
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: Los clasificadores que se pueden entrenar pueden reconocer varios tipos de contenido para la aplicación de etiquetas o directivas proporcionándole ejemplos positivos y negativos a los que examinar.
ms.openlocfilehash: 37dc3e1f57d4572e95eb78c9794a120f9c99d19c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68630258"
---
# <a name="learn-about-trainable-classifiers"></a>Obtenga información sobre los clasificadores entrenables

Categorizar y etiquetar el contenido para que pueda protegerse y controlarse correctamente es el punto de partida para la materia de protección de la información. Microsoft Purview tiene tres maneras de clasificar el contenido.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="manually"></a>Manualmente

La categorización manual requiere juicio y acción humanos. Los usuarios y administradores clasifican el contenido a medida que lo encuentran. Puede usar las etiquetas existentes y los tipos de información confidencial o usar las creadas de forma personalizada.  A continuación, puede proteger el contenido y administrar su eliminación.

## <a name="automated-pattern-matching"></a>Coincidencia de patrones automatizada

Estos mecanismos de categorización incluyen la búsqueda de contenido mediante:

- Palabras clave o valores de metadatos (lenguaje de consulta de palabras clave).
- Usar patrones de información confidencial identificados anteriormente, como el seguro social, la tarjeta de crédito o los números de cuenta bancaria [(definiciones de entidades de tipo información confidencial).](sensitive-information-type-entity-definitions.md)
- Reconocimiento de un elemento porque es una variación en una plantilla [(impresión con el dedo del documento).](document-fingerprinting.md)
- Uso de la presencia de cadenas [exactas que coinciden con los datos exactos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types).

Las etiquetas de confidencialidad y retención se pueden aplicar automáticamente para que el contenido esté disponible para su uso en [Información sobre Prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md) y [aplicar automáticamente directivas para etiquetas de retención](apply-retention-labels-automatically.md).

## <a name="classifiers"></a>Clasificadores

Este método de categorización es adecuado para el contenido que no se identifica fácilmente mediante los métodos manuales o automatizados de coincidencia de patrones. Este método de categorización consiste más en usar un clasificador para identificar un elemento en función de cuál sea el elemento, no de los elementos que están en el elemento (coincidencia de patrones). Un clasificador aprende a identificar un tipo de contenido examinando cientos de ejemplos del contenido que le interesa aplicar sangría.

> [!NOTE]
> En versión preliminar: puede ver los clasificadores que se pueden entrenar en el explorador de contenido expandiendo **Clasificadores entrenables** en el panel de filtros. Los clasificadores que se pueden entrenar mostrarán automáticamente el número de incidentes que se encuentran en SharePoint, Teams y OneDrive, sin necesidad de etiquetar.
> Si no desea usar esta característica, debe presentar una solicitud con soporte técnico de Microsoft. Esto deshabilitará la presentación de los datos confidenciales que no se usan en ninguna directiva de etiquetado en el Explorador de contenido. También puede deshabilitar el examen de los datos. Si el examen está desactivado, el etiquetado de confidencialidad y las directivas DLP con esos clasificadores no funcionarán.

### <a name="where-you-can-use-classifiers"></a>Donde puede usar clasificadores

Los clasificadores están disponibles para su uso como condición para:

- [Etiquetado automático de Office con etiquetas de confidencialidad](apply-sensitivity-label-automatically.md)
- [Aplicación automática de la directiva de etiquetas de retención en función de una condición](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)
- [Cumplimiento de las comunicaciones](communication-compliance.md)
- Las etiquetas de confidencialidad pueden usar clasificadores como condiciones; consulte [Aplicación automática de una etiqueta de confidencialidad al contenido](apply-sensitivity-label-automatically.md).
- [Prevención de pérdida de datos](dlp-learn-about-dlp.md)

> [!IMPORTANT]
> Los clasificadores solo funcionan con elementos que no están cifrados.

## <a name="types-of-classifiers"></a>Tipos de clasificadores

- **Clasificadores previamente entrenados** : Microsoft ha creado y entrenado previamente varios clasificadores que puede empezar a usar sin entrenarlos. Estos clasificadores aparecerán con el estado de `Ready to use`.
- **clasificadores entrenables personalizados** : si tiene necesidades de categorización y identificación de contenido que van más allá de lo que cubren los clasificadores previamente entrenados, puede crear y entrenar sus propios clasificadores.

Consulte [Definiciones de clasificadores entrenables](classifier-tc-definitions.md#trainable-classifiers-definitions) para obtener una lista completa de todos los clasificadores previamente entrenados.

### <a name="custom-classifiers"></a>Clasificadores personalizados

Cuando los clasificadores previamente entrenados no satisfacen sus necesidades, puede crear y entrenar sus propios clasificadores. Hay más trabajo relacionado con la creación de los suyos propios, pero se adaptarán mucho mejor a las necesidades de las organizaciones.

Para empezar a crear un clasificador personalizado que se puede entrenar, alimente ejemplos que definitivamente están en la categoría. Una vez que procesa esos ejemplos, se prueba proporcionándole una combinación de ejemplos coincidentes y no coincidentes. A continuación, el clasificador realiza predicciones sobre si un elemento determinado pertenece a la categoría que está compilando. A continuación, confirme sus resultados, ordenando los verdaderos positivos, los verdaderos negativos, los falsos positivos y los falsos negativos para ayudar a aumentar la precisión de sus predicciones.

Al publicar el clasificador, ordena los elementos de ubicaciones como SharePoint Online, Exchange y OneDrive, y clasifica el contenido. Después de publicar el clasificador, puede seguir entrenándolo mediante un proceso de comentarios similar al proceso de entrenamiento inicial.

Por ejemplo, podría crear clasificadores entrenables para:

- Documentos legales: como privilegios de cliente de abogado, conjuntos de cierre, declaración de trabajo
- Documentos empresariales estratégicos: como comunicados de prensa, fusiones y adquisiciones, ofertas, planes de negocio o marketing, propiedad intelectual, patentes, documentos de diseño
- Información de precios: como facturas, cotizaciones de precios, órdenes de trabajo, documentos de licitación
- Información financiera, como inversiones de la organización, resultados trimestrales o anuales

#### <a name="process-flow-for-creating-custom-classifiers"></a>Flujo de proceso para crear clasificadores personalizados

La creación y publicación de un clasificador para su uso en soluciones de cumplimiento, como directivas de retención y supervisión de comunicaciones, sigue este flujo. Para obtener más detalles sobre cómo crear un clasificador personalizado que se puede entrenar, consulte [Creación de un clasificador personalizado](classifier-get-started-with.md).

![clasificador personalizado de flujo de proceso.](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Volver a entrenar clasificadores

Puede ayudar a mejorar la precisión de todos los clasificadores entrenables personalizados y proporcionar comentarios sobre la precisión de la clasificación que realizan. Esto se denomina reentrenamiento y sigue este flujo de trabajo.

> [!NOTE]
> Los clasificadores previamente entrenados no se pueden volver a entrenar.

![flujo de trabajo de reentrenamiento del clasificador.](../media/classifier-retraining-workflow.png)

## <a name="provide-matchnot-a-match-accuracy-feedback-in-trainable-classifiers"></a>Proporcionar comentarios de coincidencia o no de precisión de coincidencia en clasificadores entrenables

Puede ver el número de coincidencias que tiene un clasificador entrenable en el **Explorador de contenido** y **en los láseres entrenables**. También puede proporcionar comentarios sobre si un elemento es realmente una coincidencia o no mediante el mecanismo de comentarios **Match**, **Not a Match** y usar esos comentarios para ajustar los clasificadores. Consulte [Aumento de la precisión del clasificador (versión preliminar)](data-classification-increase-accuracy.md) para obtener más información. 


## <a name="see-also"></a>Vea también

- [Etiquetas de retención](retention.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Impresión con dedo del documento](document-fingerprinting.md)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
