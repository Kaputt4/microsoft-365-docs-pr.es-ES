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
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: Un clasificador Microsoft 365 es una herramienta que se puede entrenar para reconocer varios tipos de contenido para la aplicación de directivas o de la formación, ya que le proporciona ejemplos positivos y negativos que buscar.
ms.openlocfilehash: b218fea598049e8a3b621b4b6711550227e3cbd4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204472"
---
# <a name="learn-about-trainable-classifiers"></a>Obtenga información sobre los clasificadores entrenables

Clasificar y etiquetar el contenido para que pueda protegerse y controlarse correctamente es el punto de partida de la disciplina de protección de la información. Microsoft 365 tres maneras de clasificar el contenido.

## <a name="manually"></a>Manualmente

Este método requiere juicio y acción humanas. Un administrador puede usar las etiquetas existentes y los tipos de información confidencial o crear las suyas propias y, a continuación, publicarlas. Los usuarios y administradores los aplican al contenido a medida que se encuentran con él. A continuación, puede proteger el contenido y administrar su eliminación.

## <a name="automated-pattern-matching"></a>Coincidencia de patrones automatizada

Esta categoría de mecanismos de clasificación incluye la búsqueda de contenido mediante:

- Palabras clave o valores de metadatos (lenguaje de consulta de palabras clave).
- Usar patrones de información confidencial identificados anteriormente como números de cuenta bancaria, de tarjeta de crédito o de seguridad social [(definiciones](sensitive-information-type-entity-definitions.md)de entidad de tipo de información confidencial).
- Reconocer un elemento porque es una variación en una plantilla [(impresión de dedo del documento).](document-fingerprinting.md)
- Usar la presencia de cadenas exactas [(coincidencia exacta de datos)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Las etiquetas de confidencialidad y retención se pueden aplicar automáticamente para que el contenido esté disponible para su uso en [Learn about data loss prevention](dlp-learn-about-dlp.md)) y aplicar automáticamente directivas para [etiquetas de retención.](apply-retention-labels-automatically.md)

## <a name="classifiers"></a>Clasificadores

Este método de clasificación es especialmente adecuado para el contenido que no se identifica fácilmente con los métodos de coincidencia de patrones manuales o automatizados. Este método de clasificación consiste más en entrenar un clasificador para que identifique un elemento basándose en qué es el elemento y no en cuál es su contenido (coincidencia de patrones). Un clasificador aprende a identificar un tipo de contenido al ver cientos de ejemplos del contenido que le interesa clasificar. Empieza por darle ejemplos que definitivamente están en la categoría. Una vez que los procesa, se prueba con una combinación de ejemplos que coinciden y no coinciden. A continuación, el clasificador realiza previsiones sobre si algún elemento determinado entra en la categoría que está creando. A continuación, confirme sus resultados, ordenando los verdaderos positivos, verdaderos negativos, falsos positivos y falsos negativos para ayudar a aumentar la precisión de sus previsiones. 

Al publicar el clasificador, ordena los elementos en ubicaciones como SharePoint Online, Exchange y OneDrive, y clasifica el contenido. Después de publicar el clasificador, puede seguir entrenando con un proceso de comentarios similar al proceso de aprendizaje inicial.

### <a name="where-you-can-use-trainable-classifiers"></a>Dónde puede usar clasificadores entrenables
Tanto los clasificadores integrados como los clasificadores entrenables están disponibles como condición para el etiquetado automático de [Office](apply-sensitivity-label-automatically.md)con etiquetas de confidencialidad, [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automáticamente la directiva de etiquetas de retención según una condición y en el cumplimiento de las comunicaciones. [](communication-compliance.md) 

Las etiquetas de confidencialidad pueden usar clasificadores como condiciones, vea [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).

> [!IMPORTANT]
> Los clasificadores solo funcionan con elementos que no están cifrados.

## <a name="types-of-classifiers"></a>Tipos de clasificadores

- **clasificadores previamente formados:** Microsoft ha creado y formado previamente una serie de clasificadores que puede empezar a usar sin entrenarlos. Estos clasificadores aparecerán con el estado de `Ready to use` .
- **clasificadores personalizados:** si tiene necesidades de clasificación que se extienden más allá de lo que cubren los clasificadores previamente formados, puede crear y entrenar a sus propios clasificadores.

### <a name="pre-trained-classifiers"></a>Clasificadores previamente formados

Microsoft 365 viene con cinco clasificadores previamente formados:

> [!CAUTION]
> Estamos desaprobando el clasificador de lenguaje ofensivo **previamente** formado porque ha estado produciendo un gran número de falsos positivos. No lo use y, si lo está usando actualmente, debe quitar los procesos empresariales de él. Se recomienda usar los **clasificadores de** amenazas, **profanidad** y acoso **previamente** formados en su lugar.

- **Resumes:** detecta elementos que son cuentas textuales de las cualificaciones personales, educativas, profesionales, experiencia laboral y otra información de identificación personal de un solicitante
- **Código fuente:** detecta elementos que contienen un conjunto de instrucciones y instrucciones escritas en los 25 principales lenguajes de programación de equipos usados en GitHub
    - ActionScript
    - C
    - C#
    - C++
    - Clojure
    - CoffeeScript
    - Ir
    - Haskell
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - Objective-C
    - Perl
    - PHP
    - Python
    - R
    - Ruby
    - Scala
    - Consola
    - Swift
    - Tex
    - Vim Script

> [!NOTE]
> El código fuente está formado para detectar cuándo la mayor parte del texto es código fuente. No detecta texto de código fuente intercalado con texto sin formato.

- **Acoso:** detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con conductas ofensivas dirigidas a una o varias personas en función de los siguientes rasgos: raza, origen étnico, religión, origen nacional, género, orientación sexual, edad, discapacidad
- **Profanidad:** detecta una categoría específica de elementos de texto de lenguaje ofensivo que contienen expresiones que ensoñan a la mayoría de las personas
- **Amenaza:** detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con amenazas para cometer violencia o hacer daño físico o daño a una persona o propiedad
- **Discriminación:** detecta un lenguaje discriminatorio explícito y es especialmente sensible al lenguaje discriminatorio frente a las comunidades afroestadounides/negras en comparación con otras comunidades.

> [!IMPORTANT]
> El clasificador de discriminación solo está disponible como versión preliminar pública para clientes cuyas Microsoft 365 inquilinos se encuentran en centros de datos de Norteamérica. Para ver dónde se encuentra Microsoft 365 inquilino, abra el Centro de administración de Microsoft 365 y vaya **a** Configuración configuración de la organización Ficha Perfil de organización Ubicación de  >    >  [](https://go.microsoft.com/fwlink/p/?linkid=2067339)  >  **datos**. 

Aparecen en la vista **clasificadores Centro de cumplimiento de Microsoft 365** clasificación de datos  >    >  **trainable con** el estado de `Ready to use` .

![clasificadores-clasificadores previamente formados.](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Tenga en cuenta que el lenguaje ofensivo, el acoso, la profanación, la discriminación y los clasificadores de amenazas solo funcionan con texto que admite búsquedas y no son una lista exhaustiva o completa de términos o idiomas en estas áreas. Además, los estándares lingüísticos y culturales cambian continuamente y, a la luz de estas realidades, Microsoft se reserva el derecho de actualizar estos clasificadores a su discreción. Aunque los clasificadores pueden ayudar a su organización a detectar estas áreas, los clasificadores no están diseñados para proporcionar el único medio de su organización para detectar o abordar el uso de dicho idioma. Su organización, no Microsoft ni sus subsidiarias, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, el examen, el bloqueo, la eliminación y la retención de cualquier contenido identificado por un clasificador previamente formado, incluido el cumplimiento de la privacidad local y otras leyes aplicables. Microsoft anima a consultar con abogados antes de la implementación y el uso.

Los clasificadores previamente formados pueden examinar el contenido en estos idiomas:

• Chino (simplificado) • Inglés • Francés • Alemán • Italiano • Japonés • Portugués • Español

### <a name="custom-classifiers"></a>Clasificadores personalizados

Cuando los clasificadores previamente formados no satisfacen sus necesidades, puede crear y entrenar a sus propios clasificadores. Hay mucho más trabajo implicado en la creación de los suyos, pero estarán mucho mejor adaptados a las necesidades de las organizaciones. 

Por ejemplo, podría crear clasificadores que se puedan entrenar para:
 
- Documentos legales, como privilegios de cliente de abogado, conjuntos de cierre, declaración de trabajo
- Documentos de negocio estratégicos: como comunicados de prensa, fusiones y adquisiciones, acuerdos, planes de negocio o marketing, propiedad intelectual, patentes, documentos de diseño
- Información de precios: como facturas, cotizaciones de precios, pedidos de trabajo, documentos de ofertas 
- Información financiera, como inversiones organizativas, resultados trimestrales o anuales    

#### <a name="process-flow-for-creating-custom-classifiers"></a>Flujo de proceso para crear clasificadores personalizados

La creación y publicación de un clasificador para su uso en soluciones de cumplimiento, como directivas de retención y supervisión de comunicaciones, sigue este flujo. Para obtener más información sobre cómo crear un clasificador personalizado, vea [Creating a custom classifier](classifier-get-started-with.md).

![clasificador personalizado de flujo de proceso.](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Reentrenamiento de clasificadores

Puede ayudar a mejorar la precisión de todos los clasificadores personalizados y algunos clasificadores previamente formados al proporcionarles comentarios sobre la precisión de la clasificación que realizan. Esto se denomina reciclaje y seguir este flujo de trabajo.

![flujo de trabajo de reciclaje de clasificadores.](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Consulte también

- [Etiquetas de retención](retention.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Impresión de dedo de documento](document-fingerprinting.md)
- [Coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
