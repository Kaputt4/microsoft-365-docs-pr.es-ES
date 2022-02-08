---
title: Obtenga información sobre los clasificadores entrenables
f1.keywords:
  - NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: null
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
description: 'Los clasificadores capacitados pueden reconocer varios tipos de contenido para el etiquetado o la aplicación de directivas, ya que le dan ejemplos positivos y negativos que se deben analizar.'
---

# <a name="learn-about-trainable-classifiers"></a>Obtenga información sobre los clasificadores entrenables

Clasificar y etiquetar el contenido para que pueda protegerse y controlarse correctamente es el punto de partida de la disciplina de protección de la información. Microsoft 365 tres maneras de clasificar el contenido.

## <a name="manually"></a>Manualmente

La clasificación manual requiere juicio y acción humanas. Los usuarios y administradores los aplican al contenido a medida que se encuentran con él. Puede usar las etiquetas preexistentes y los tipos de información confidencial o usar las creadas de forma personalizada.  A continuación, puede proteger el contenido y administrar su eliminación.

## <a name="automated-pattern-matching"></a>Coincidencia de patrones automatizada

Esta categoría de mecanismos de clasificación incluye la búsqueda de contenido mediante:

- Palabras clave o valores de metadatos (lenguaje de consulta de palabras clave).
- Usar patrones de información confidencial identificados anteriormente como números de cuenta bancaria, tarjeta de crédito o seguridad social [(definiciones de entidades de tipo de información confidencial).](sensitive-information-type-entity-definitions.md)
- Reconocer un elemento porque es una variación en una plantilla [(impresión de dedo de documento).](document-fingerprinting.md).
- Uso de la presencia de cadenas exactas [exactas de coincidencia de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types).

Las [etiquetas](dlp-learn-about-dlp.md) de confidencialidad y retención se pueden aplicar automáticamente para que el contenido esté disponible para su uso en Obtenga información sobre la prevención de pérdida de datos y aplique automáticamente directivas para [etiquetas de retención](apply-retention-labels-automatically.md).

## <a name="classifiers"></a>Clasificadores

Este método de clasificación es adecuado para el contenido que no se identifica fácilmente mediante los métodos manuales o automatizados de coincidencia de patrones. Este método de clasificación consiste más en usar un clasificador para identificar un elemento en función de lo que es el elemento, no de los elementos que están en el elemento (coincidencia de patrones). Un clasificador aprende a identificar un tipo de contenido al ver cientos de ejemplos del contenido que le interesa clasificar.

> [!NOTE]
> En Vista previa: puede ver los clasificadores que se pueden entrenar en el explorador de contenido expandiendo **Clasificadores** de formación en el panel filtros. Los clasificadores que se pueden entrenar mostrarán automáticamente el número de incidentes que se encuentran en SharePoint, Teams y OneDrive, sin necesidad de ningún etiquetado.
> Si no desea usar esta característica, debe presentar una solicitud al Soporte técnico de Microsoft para deshabilitar la clasificación lista para usar. Esto deshabilitará el examen del contenido confidencial y etiquetado antes de crear directivas de etiquetado.

### <a name="where-you-can-use-classifiers"></a>Dónde puede usar clasificadores

Los clasificadores están disponibles para su uso como condición para Office etiquetas automáticas con etiquetas de [confidencialidad, aplicar](apply-sensitivity-label-automatically.md) automáticamente la directiva de etiquetas de retención según una condición y en el cumplimiento de [las comunicaciones](communication-compliance.md). [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) 

Las etiquetas de confidencialidad pueden usar clasificadores como condiciones, consulta [Aplicar automáticamente una etiqueta de confidencialidad al contenido](apply-sensitivity-label-automatically.md).

> [!IMPORTANT]
> Los clasificadores solo funcionan con elementos que no están cifrados.

## <a name="types-of-classifiers"></a>Tipos de clasificadores

- **clasificadores previamente formados** : Microsoft ha creado y formado previamente varios clasificadores que puede empezar a usar sin entrenarlos. Estos clasificadores aparecerán con el estado de `Ready to use`.
- **clasificadores personalizados entrenables** : si tiene necesidades de clasificación que se extienden más allá de lo que cubren los clasificadores previamente formados, puede crear y entrenar a sus propios clasificadores.

### <a name="pre-trained-classifiers"></a>Clasificadores previamente formados

Microsoft 365 viene con varios clasificadores previamente formados:

> [!CAUTION]
> Estamos desaprobando el clasificador preentrenado de **Lenguaje ofensivo** porque ha estado produciendo un alto número de falsos positivos. No lo use y, si lo está usando actualmente, debe quitar los procesos empresariales de él. En su **lugar, se** recomienda usar clasificadores de amenazas, **profanidad** y hostigamiento.

- **Resumes**: detecta docx, .pdf, .rtf, .txt elementos que son cuentas textuales de las cualificaciones personales, educativas, profesionales, experiencia laboral y otra información de identificación personal de un solicitante
- Código **fuente: detecta** elementos que contienen un conjunto de instrucciones y instrucciones escritas en los 25 principales lenguajes de programación de equipos usados en GitHub: ActionScript, C, C#, C++, Clojure, CoffeeScript, Go, Haskell, Java, JavaScript, Lua, MATLAB, Objective-C, Perl, PHP, Python, R, Ruby, Scala, Shell, Swift, TeX, Vim Script.

> [!NOTE]
> El código fuente está formado para detectar cuándo la mayor parte del texto es código fuente. No detecta texto de código fuente intercalado con texto sin formato.

- **Acuerdos**: detecta contenido relacionado con acuerdos legales, como contratos de no divulgación, declaraciones de trabajo, contratos de préstamo y arrendamiento, contratos de trabajo y contratos de no competencia. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.
- **Discriminación**: detecta un lenguaje discriminatorio explícito y es sensible al lenguaje discriminatorio frente a las comunidades afroestadounides/negras en comparación con otras comunidades.
- **Finanzas**: detecta contenido en las categorías de finanzas corporativas, contabilidad, economía, banca e inversión. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla files.
- **Acoso**: detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con conductas ofensivas dirigidas a uno o varios individuos en función de los siguientes rasgos: raza, origen étnico, religión, origen nacional, género, orientación sexual, edad, discapacidad. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.
- **Salud**: detecta contenido en aspectos de administración médica y sanitaria, como servicios médicos, diagnósticos, tratamiento, notificaciones, etc. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla files.
- **RECURSOS** HUMANOS: detecta contenido en categorías relacionadas con recursos humanos de contratación, entrevista, contratación, formación, evaluación, advertencia y terminación. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla files.
- **IP**: detecta contenido en categorías relacionadas con la propiedad intelectual, como secretos comerciales e información confidencial similar. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla files.
- **IT**: detecta contenido en las categorías de tecnología de la información y ciberseguridad, como la configuración de red, la seguridad de la información, el hardware y el software. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla files.
- **Asuntos legales**: detecta contenido en categorías relacionadas con asuntos legales, como litigios, procesos legales, obligaciones legales, terminología legal, ley y legislación. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.
- **Adquisiciones**: detecta contenido en categorías de ofertas, cotización, compra y pago de suministro de bienes y servicios. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla files.
- **Profanidad**: detecta una categoría específica de elementos de texto de lenguaje ofensivo que contienen expresiones que ensoñan a la mayoría de las personas. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.
- **Impuestos**: detecta contenido de relación fiscal como planeación fiscal, formularios fiscales, declaración de impuestos, reglamentos fiscales. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, xla files.
- **Amenaza**: detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con amenazas para cometer violencia o hacer daño físico o daño a una persona o propiedad. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.

Aparecen en la **vista Centro de cumplimiento de Microsoft 365** >  **Clasificadores** **de clasificación de** >  Centro de cumplimiento de Microsoft 365 Data Con el estado de `Ready to use`.

![clasificadores-clasificadores previamente formados.](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Tenga en cuenta que el lenguaje ofensivo, el acoso, la profanación, la discriminación y los clasificadores de amenazas solo funcionan con texto que admite búsquedas y no son una lista exhaustiva o completa de términos o idiomas en estas áreas. Además, los estándares lingüísticos y culturales cambian continuamente y, a la luz de estas realidades, Microsoft se reserva el derecho de actualizar estos clasificadores a su discreción. Aunque los clasificadores pueden ayudar a su organización a detectar estas áreas, los clasificadores no están diseñados para proporcionar el único medio de su organización para detectar o abordar el uso de dicho idioma. Su organización, no Microsoft ni sus subsidiarias, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, el examen, el bloqueo, la eliminación y la retención de cualquier contenido identificado por un clasificador previamente formado, incluido el cumplimiento de la privacidad local y otras leyes aplicables. Microsoft anima a consultar con abogados antes de la implementación y el uso.

Los clasificadores previamente formados pueden examinar el contenido en estos idiomas:

• Chino (simplificado) • Inglés • Francés • Alemán • Italiano • Japonés • Portugués • Español

### <a name="custom-classifiers"></a>Clasificadores personalizados

Cuando los clasificadores previamente formados no satisfacen sus necesidades, puede crear y entrenar a sus propios clasificadores. Hay mucho más trabajo implicado en la creación de los suyos, pero estarán mucho mejor adaptados a las necesidades de las organizaciones.

Para empezar a crear un clasificador personalizado, alimentándolo de ejemplos que definitivamente están en la categoría. Una vez que procesa esos ejemplos, se prueba al darle una combinación de ejemplos que coincidan y que no coincidan. A continuación, el clasificador realiza previsiones sobre si algún elemento determinado entra en la categoría que está creando. A continuación, confirme sus resultados, ordenando los verdaderos positivos, verdaderos negativos, falsos positivos y falsos negativos para ayudar a aumentar la precisión de sus previsiones. 

Al publicar el clasificador, ordena los elementos en ubicaciones como SharePoint Online, Exchange y OneDrive, y clasifica el contenido. Después de publicar el clasificador, puede seguir entrenando con un proceso de comentarios similar al proceso de aprendizaje inicial.

Por ejemplo, podría crear clasificadores que se puedan entrenar para:

- Documentos legales, como privilegios de cliente de abogado, conjuntos de cierre, declaración de trabajo
- Documentos de negocio estratégicos: como comunicados de prensa, fusiones y adquisiciones, acuerdos, planes de negocio o marketing, propiedad intelectual, patentes, documentos de diseño
- Información de precios: como facturas, cotizaciones de precios, pedidos de trabajo, documentos de ofertas
- Información financiera, como inversiones organizativas, resultados trimestrales o anuales

#### <a name="process-flow-for-creating-custom-classifiers"></a>Flujo de proceso para crear clasificadores personalizados

La creación y publicación de un clasificador para su uso en soluciones de cumplimiento, como directivas de retención y supervisión de comunicaciones, sigue este flujo. Para obtener más información sobre cómo crear un clasificador personalizado, consulte [Creating a custom classifier](classifier-get-started-with.md).

![clasificador personalizado de flujo de proceso.](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Reentrenamiento de clasificadores

Puede ayudar a mejorar la precisión de todos los clasificadores personalizados y proporcionarles comentarios sobre la precisión de la clasificación que realizan. Esto se denomina reentrenamiento y se sigue a este flujo de trabajo.

> [!NOTE]
> Los clasificadores previamente formados no se pueden volver a entrenar.

![flujo de trabajo de reciclaje de clasificadores.](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Vea también

- [Etiquetas de retención](retention.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Impresión de dedo de documento](document-fingerprinting.md)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
