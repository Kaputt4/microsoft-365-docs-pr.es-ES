---
title: Introducción a los clasificadores de 365 de Microsoft (versión preliminar)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Un clasificador entrenado de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido dándole a los ejemplos positivos y negativos que debe ver. Una vez que el clasificador esté entrenado y confirme que los resultados sean correctos, úselo para buscar en el contenido de la organización, clasificarlo para aplicar etiquetas de retención o confidencialidad o incluirlo en la prevención de pérdida de datos (DLP) o en las directivas de retención.
ms.openlocfilehash: 6b8574b7c87f0b038c46894940cb8d15b152ab5c
ms.sourcegitcommit: 6dfa646b9de30336dedfd0cac7320c57ad74ae11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "38690989"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a>Introducción al entrenamiento de clasificadores (vista previa)

La clasificación y la etiqueta del contenido para que se pueda proteger y administrar correctamente es el punto de partida de la disciplina de protección de la información. Microsoft 365 tiene tres formas de clasificar el contenido.

## <a name="manually"></a>Manualmente

Esto requiere la acción y los juicios humanos. Un administrador puede usar las etiquetas preexistentes y los tipos de información confidencial, o crear los suyos propios y, a continuación, publicarlos. Los usuarios y los administradores los aplican al contenido a medida que lo encuentran. A continuación, puede proteger el contenido y administrar su disposición.

## <a name="automated-pattern-matching"></a>Coincidencia de patrones automatizada

Esta categoría de mecanismos de clasificación incluye la búsqueda de contenido por:

- Palabras clave o valores de metadatos (lenguaje de consulta de palabras clave)
- uso de patrones identificados previamente de información confidencial, como seguridad social, números de tarjeta de crédito o cuenta bancaria [(tipos de información confidencial)](what-the-sensitive-information-types-look-for.md)
- Reconocimiento de un elemento porque es una variante de una plantilla [(impresión](document-fingerprinting.md) de los dedos de los documentos)
- uso de la presencia de cadenas exactas [(coincidencia exacta de datos)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Las etiquetas de confidencialidad y retención se pueden aplicar automáticamente para que el contenido esté disponible para su uso en la [prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md) y en [las directivas de retención](retention-policies.md).

## <a name="trainable-classifiers"></a>Clasificadores capacitados

Este método de clasificación es especialmente adecuado para el contenido que, por su naturaleza, no se ha predefinido para identificarlo fácilmente por los métodos de coincidencia de patrón manuales o automatizados. Este método de clasificación es más sobre cómo entrenar a un clasificador para identificar un elemento en función de lo que es el elemento, no por los elementos que están en el elemento (coincidencia de modelos). Un clasificador aprende a identificar un tipo de contenido mediante el uso de cientos de ejemplos del contenido que le interesa clasificar. Empiece por alimentar los ejemplos que están definitivamente en la categoría y, después, una vez que los procesa, los debe probar dándole una mezcla de ejemplos coincidentes y no coincidentes. A continuación, el clasificador realiza predicciones sobre si un elemento determinado pertenece o no a la categoría que se está creando. A continuación, se confirman los resultados, por lo que se ordenan los positivos, negativos, falsos positivos y falsos negativos para ayudar a aumentar la precisión de sus predicciones. Al publicar el clasificador entrenado, los elementos se ordenan en ubicaciones, como SharePoint Online, Exchange y OneDrive y se clasifica el contenido.

> [!IMPORTANT]
> Ambos tipos de clasificadores están disponibles como condición para [aplicar automáticamente una directiva de etiqueta de retención basada en una condición y el cumplimiento de la](labels.md#applying-a-retention-label-automatically-based-on-conditions) [comunicación](communication-compliance.md).

> [!IMPORTANT]
> Los clasificadores que se pueden entrenar solo funcionan con elementos que no están cifrados y que están en inglés.

## <a name="types-of-classifiers"></a>Tipos de clasificadores

Están listos para usar clasificadores y clasificadores que se pueden entrenar. La obtención de un clasificador capacitado en un estado editable requiere una inversión de tiempo para entrenarlo. Para ayudarle a empezar a usar clasificadores, Microsoft 365 incluye unos clasificadores listos para usar.

> [!NOTE]
> Antes de usar un clasificador listo para usar en el flujo de trabajo de clasificación y etiquetado, debe probarlo con una muestra del contenido de la organización que sienta que se ajusta a la categoría para comprobar que sus predicciones de clasificación satisfacen sus expectativas.

### <a name="understanding-ready-to-use-classifiers"></a>Descripción de los clasificadores listos para usar

Microsoft 365 incluye seis clasificadores listos para usar:

- **Lenguaje ofensivo**: detecta los elementos de texto que contienen palabras soeces, Slurs, taunts y expresiones disfrazadas (que son expresiones que tienen el mismo significado que un término más ofensivo).
- **Currículos**: detecta elementos que son cuentas de texto de la cualificación personal, educativa, profesional, experiencia laboral y otros datos de identificación personal del solicitante.
- **SourceCode**: detecta elementos que contienen un conjunto de instrucciones e instrucciones escritas en lenguajes de programación de equipos ampliamente usados.
- **Acosar**: detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con la conducta ofensiva dirigida a uno o varios individuos en función de los siguientes rasgos: raza, étnico, religión, origen nacional, sexo, orientación sexual, edad, discapacidad.
- **Blasfemias**: detecta una categoría específica de elementos de texto de lenguaje ofensivo que contienen expresiones embarazosas de la mayoría de las personas
- **Amenaza**: detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con amenazas para confirmar violencia o daño físico o daño a una persona o propiedad

Estos aparecen en la vista clasificación de datos del **Centro** > de cumplimiento de Microsoft 365 **(versión preliminar)** > vista de**clasificadores** que tienen el estado de `Ready to use`.

![Clasificadores: listos para usar: clasificadores](media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Tenga en cuenta que el idioma ofensivo, el acoso, los términos blasfemos y los clasificadores de amenazas solo funcionan con texto que admite búsquedas no es exhaustivo o completo.  Además, los estándares de idioma y culturales cambian continuamente y, teniendo en cuenta estas realidades, Microsoft se reserva el derecho de actualizar estos clasificadores según su criterio. Aunque los clasificadores pueden ayudar a su organización a supervisar el uso ofensivo y otros idiomas, los clasificadores no abordan las consecuencias de dicho lenguaje y no pretenden proporcionar a los únicos medios de supervisión de la organización o responder al uso de ese idioma. Su organización, y no Microsoft o sus subsidiarias, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, la aplicación, el bloqueo, la eliminación y la retención de cualquier contenido identificado por un clasificador previamente entrenado.

#### <a name="process-flow-for-using-ready-to-use-classifiers"></a>Flujo de proceso para usar clasificadores listos para usar

No es necesario entrenar a los clasificadores listos para usar, pero debe confirmar que identificarán los tipos de contenido que los necesita antes de usarlos en las soluciones de cumplimiento. La prueba de un clasificador previamente preparado sigue este flujo.

![prueba del flujo de procesos un clasificador preconfigurado](media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a>Descripción de los clasificadores que se capacitan

Si los clasificadores listos para usar no satisfacen sus necesidades, puede crear y entrenar sus propios clasificadores. Hay mucho más trabajo relacionado con la creación de sus propios, pero estarán más adaptados a las necesidades de su organización. Para obtener más información sobre cómo usar un clasificador precapacitado, consulte [using a Ready for use Classifier](classifier-using-a-ready-to-use-classifier.md) .

> [!IMPORTANT]
> Solo el usuario que crea un clasificador capacitado puede entrenar y revisar las predicciones realizadas por ese clasificador.

#### <a name="process-flow-for-creating-trainable-classifiers"></a>Flujo de proceso para crear clasificadores que se capacitan

La creación y publicación de un clasificador capacitado para su uso en soluciones de cumplimiento, como las directivas de retención y la supervisión de comunicaciones, sigue este flujo. Para obtener más información sobre la creación de un clasificador capacitado, vea [crear un clasificador](classifier-creating-a-trainable-classifier.md)que se pudiera entrenar.

![clasificador de flujo de proceso capacitable](media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a>Vea también

- [Etiquetas de retención](labels.md)
- [directivas de retención](retention-policies.md)
- [prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [tipos de información confidencial](what-the-sensitive-information-types-look-for.md)
- [impresión de los dedos del documento](document-fingerprinting.md)
- [coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
