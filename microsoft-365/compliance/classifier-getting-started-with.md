---
title: Introducción al entrenamiento de clasificadores (vista previa)
f1.keywords:
- NOCSH
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
description: Un clasificador entrenado de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido dándole a los ejemplos positivos y negativos que debe ver. Una vez que se ha entrenado al clasificador, confirme que los resultados son correctos. A continuación, se usa para buscar en el contenido de la organización y clasificarlo para aplicar etiquetas de retención o confidencialidad o incluirlo en la prevención de pérdida de datos (DLP) o en las directivas de retención.
ms.openlocfilehash: 7cad27112597bcdbdce6aeb33fef66f24bdd8819
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502977"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a>Introducción al entrenamiento de clasificadores (vista previa)

La clasificación y la etiqueta del contenido para que se pueda proteger y administrar correctamente es el punto de partida de la disciplina de protección de la información. Microsoft 365 tiene tres formas de clasificar el contenido.

## <a name="manually"></a>Manualmente

Este método requiere la intervención humana y la acción. Un administrador puede usar las etiquetas preexistentes y los tipos de información confidencial, o crear los suyos propios y, a continuación, publicarlos. Los usuarios y los administradores los aplican al contenido a medida que lo encuentran. A continuación, puede proteger el contenido y administrar su disposición.

## <a name="automated-pattern-matching"></a>Coincidencia de patrones automatizada

Esta categoría de mecanismos de clasificación incluye la búsqueda de contenido por:

- Palabras clave o valores de metadatos (lenguaje de consulta de palabras clave).
- Uso de patrones identificados anteriormente de información confidencial, como seguridad social, números de tarjeta de crédito o cuenta bancaria [(definiciones de entidad de tipo información confidencial)](sensitive-information-type-entity-definitions.md).
- Reconocimiento de un elemento porque es una variante de una plantilla [(impresión](document-fingerprinting.md)de los dedos de los documentos).
- Uso de la presencia de cadenas exactas [(coincidencia exacta de datos)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Las etiquetas de confidencialidad y retención se pueden aplicar automáticamente para que el contenido esté disponible para su uso en las directivas de [prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md) y de [aplicación automática para las etiquetas de retención](apply-retention-labels-automatically.md).

## <a name="trainable-classifiers"></a>Clasificadores capacitados

Este método de clasificación es especialmente adecuado para el contenido que no se identifica fácilmente por los métodos de coincidencia de patrón manuales o automatizados. Este método de clasificación es más sobre cómo entrenar a un clasificador para identificar un elemento en función de lo que es el elemento, no por los elementos que están en el elemento (coincidencia de modelos). Un clasificador aprende a identificar un tipo de contenido mirando cientos de ejemplos del contenido que le interesa clasificar. Empiece por alimentar los ejemplos que están en la categoría de forma indefinida. Una vez que los procesa, lo prueba mediante una combinación de ambos ejemplos que coinciden y no coinciden. A continuación, el clasificador crea predicciones sobre si un elemento determinado pertenece a la categoría que se está creando. A continuación, se confirman los resultados, se ordenan los positivos, negativos, falsos positivos y falsos negativos para ayudar a aumentar la precisión de sus predicciones. Al publicar el clasificador entrenado, los elementos se ordenan en lugares como SharePoint Online, Exchange y OneDrive, y clasifican el contenido.

### <a name="where-you-can-use-trainable-classifiers"></a>Dónde puede usar clasificadores interexperto
Tanto los clasificadores integrados como los clasificadores entrenados están disponibles como condición para el [etiquetado automático de Office con etiquetas de confidencialidad](apply-sensitivity-label-automatically.md), [aplicar automáticamente una directiva de etiqueta de retención basada en una condición](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) y en el cumplimiento de la [comunicación](communication-compliance.md). 

Las etiquetas de confidencialidad pueden usar clasificadores integrados y de creación propia como condiciones, vea [aplicar una etiqueta de confidencialidad a los contenidos automáticamente](apply-sensitivity-label-automatically.md).

> [!IMPORTANT]
> Los clasificadores que se pueden entrenar solo funcionan con elementos que no están cifrados y que están en inglés.

### <a name="licensing-requirements"></a>Requisitos de licencia

Los clasificadores que se pueden entrenar son una característica de cumplimiento de Microsoft 365 E5 o E5. Debe tener una de estas suscripciones para poder usarla.

### <a name="pre-requisites"></a>Requisitos previos

Para acceder a los clasificadores que se puedan entrenar en la interfaz de usuario: 
- el administrador global debe participar en el inquilino.
- Se necesita el rol de administrador de cumplimiento o el administrador de datos de cumplimiento para entrenar un clasificador

Necesitará cuentas con estos permisos para usar clasificadores que se puedan entrenar en estos escenarios:

- Escenario de directiva de etiqueta de retención: RecordManagement y roles de administración de retención 
- Escenario de directiva de etiqueta de confidencialidad: administrador de seguridad, administrador de cumplimiento, administrador de datos de cumplimiento
- Escenario de directiva de cumplimiento de comunicaciones: administrador de administración de riesgos de Insider, administrador de revisión de supervisión 

## <a name="types-of-classifiers"></a>Tipos de clasificadores

Hay clasificadores integrados y clasificadores que se pueden entrenar. La obtención de un clasificador capacitado en un estado editable requiere una inversión de tiempo para entrenarlo. Para ayudarle a empezar a usar clasificadores, Microsoft 365 incluye algunos clasificadores integrados.

> [!NOTE]
> Antes de usar un clasificador integrado en el flujo de trabajo de clasificación y etiquetado, debe probarlo con una muestra del contenido de la organización que considere que la categoría para comprobar que sus predicciones de clasificación satisfacen sus expectativas.

### <a name="understanding-built-in-classifiers"></a>Descripción de los clasificadores integrados

Microsoft 365 incluye cinco clasificadores integrados recomendados:

> [!CAUTION]
> Estamos desaprobando el clasificador incorporado de **Lenguaje ofensivo** porque ha estado produciendo un alto número de falsos positivos. No lo use y, si actualmente lo está usando, debería mover sus procesos de negocio fuera de él. En su lugar, se recomienda usar los clasificadores de **amenaza**, **blasfemia**y **acoso** integrados.

- **Currículos**: detecta los elementos que son cuentas de texto de la cualificación personal, educativa, profesional, experiencia laboral y otra información de identificación personal del solicitante.
- **Código de origen**: detecta elementos que contienen un conjunto de instrucciones e instrucciones escritas en los 25 principales lenguajes de programación usados del equipo en github

  |nombre del idioma|||||
  |---------|---------|---------|---------|---------|
  |Código|C        |C#       |+     |Clojure  |
  |CoffeeScript|CSS     |Ir       |Haskell |HTML     |
  |Java     |JavaScript|Lua      |MATLAB   |Objective-C|
  |Perl     |PHP      |Python   |R        |Ruby     |
  |Scala    |Consola    |Rápido    |Tex      |Script de VIM|

> [!NOTE]
> El código fuente está entrenado para detectar cuando la mayor parte del texto es código fuente. No detecta texto de código fuente intercalado con texto sin formato.

- **Acosar**: detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con la conducta ofensiva dirigida a uno o varios individuos en función de los siguientes rasgos: raza, étnico, religión, origen nacional, sexo, orientación sexual, edad, discapacidad
- **Blasfemias**: detecta una categoría específica de elementos de texto de lenguaje ofensivo que contiene expresiones que avergonzan a la mayoría de las personas
- **Amenaza**: detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con amenazas para confirmar violencia o daño físico o daño a una persona o propiedad

Estos aparecen en la vista clasificación de datos del **centro de cumplimiento de Microsoft 365**  >  **(versión preliminar)**  >  vista de**clasificadores** que tienen el estado de `Ready to use` .

![Clasificadores: listos para usar: clasificadores](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Tenga en cuenta que el idioma ofensivo, el acoso, los términos blasfemos y los clasificadores de amenazas solo funcionan con texto que admite búsquedas no es exhaustivo o completo.  Además, los estándares de idioma y culturales cambian continuamente y, teniendo en cuenta estas realidades, Microsoft se reserva el derecho de actualizar estos clasificadores según su criterio. Aunque los clasificadores pueden ayudar a su organización a supervisar el uso ofensivo y otros idiomas, los clasificadores no abordan las consecuencias de ese lenguaje y no pretenden proporcionar a los únicos medios de supervisar o responder al uso de ese lenguaje en su organización. Su organización, y no Microsoft o sus subsidiarias, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, la aplicación, el bloqueo, la eliminación y la retención de cualquier contenido identificado por un clasificador previamente entrenado.

#### <a name="process-flow-for-using-built-in-classifiers"></a>Flujo de proceso para usar clasificadores integrados

No es necesario entrenar a los clasificadores integrados, pero debe confirmar que identificarán los tipos de contenido que necesita antes de usarlos en las soluciones de cumplimiento. La prueba de un clasificador previamente preparado sigue este flujo.

![prueba del flujo de procesos un clasificador preconfigurado](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a>Descripción de los clasificadores que se capacitan

Si los clasificadores integrados no satisfacen sus necesidades, puede crear y entrenar sus propios clasificadores. Hay mucho más trabajo en lo que se refiere a la creación de los suyos, pero estarán más adaptados a las necesidades de su organización. Para obtener más información sobre cómo usar un clasificador precapacitado, vea [usar un clasificador integrado](classifier-using-a-ready-to-use-classifier.md)

> [!IMPORTANT]
> Solo el usuario que crea un clasificador capacitado puede entrenar y revisar las predicciones realizadas por ese clasificador.

#### <a name="process-flow-for-creating-trainable-classifiers"></a>Flujo de proceso para crear clasificadores que se capacitan

La creación y publicación de un clasificador capacitable para su uso en las soluciones de cumplimiento, como las directivas de retención y la supervisión de la comunicación, sigue este flujo. Para obtener más información sobre la creación de un clasificador capacitado, vea [crear un clasificador](classifier-creating-a-trainable-classifier.md)que se pudiera entrenar.

![clasificador de flujo de proceso capacitable](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a>Vea también


- [Etiquetas de retención](retention.md)
- [Prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Impresión de los dedos del documento](document-fingerprinting.md)
- [Coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
