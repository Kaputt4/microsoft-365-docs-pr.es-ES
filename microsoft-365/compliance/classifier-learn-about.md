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
description: Los clasificadores que se pueden entrenar pueden reconocer varios tipos de contenido para la aplicación de etiquetas o directivas proporcionándole ejemplos positivos y negativos a los que examinar.
ms.openlocfilehash: 0c47d019b3508bdd8d8fba1f1b4303c7f4c9579d
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66621213"
---
# <a name="learn-about-trainable-classifiers"></a>Obtenga información sobre los clasificadores entrenables

Clasificar y etiquetar el contenido para que pueda protegerse y controlarse correctamente es el punto de partida para la materia de protección de la información. Microsoft 365 tiene tres maneras de clasificar el contenido.

## <a name="manually"></a>Manualmente

La clasificación manual requiere juicio y acción humanos. Los usuarios y administradores los aplican al contenido a medida que lo encuentran. Puede usar las etiquetas existentes y los tipos de información confidencial o usar las creadas de forma personalizada.  A continuación, puede proteger el contenido y administrar su eliminación.

## <a name="automated-pattern-matching"></a>Coincidencia de patrones automatizada

Esta categoría de mecanismos de clasificación incluye la búsqueda de contenido mediante:

- Palabras clave o valores de metadatos (lenguaje de consulta de palabras clave).
- Usar patrones de información confidencial identificados anteriormente, como el seguro social, la tarjeta de crédito o los números de cuenta bancaria [(definiciones de entidades de tipo información confidencial).](sensitive-information-type-entity-definitions.md)
- Reconocimiento de un elemento porque es una variación en una plantilla [(impresión con el dedo del documento).](document-fingerprinting.md)
- Uso de la presencia de cadenas [exactas que coinciden con los datos exactos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types).

Las etiquetas de confidencialidad y retención se pueden aplicar automáticamente para que el contenido esté disponible para su uso en [Información sobre Prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md) y [aplicar automáticamente directivas para etiquetas de retención](apply-retention-labels-automatically.md).

## <a name="classifiers"></a>Clasificadores

Este método de clasificación es adecuado para el contenido que no se identifica fácilmente mediante los métodos manuales o automatizados de coincidencia de patrones. Este método de clasificación consiste más en usar un clasificador para identificar un elemento en función de cuál sea el elemento, no de los elementos que están en el elemento (coincidencia de patrones). Un clasificador aprende a identificar un tipo de contenido examinando cientos de ejemplos del contenido que le interesa clasificar.

> [!NOTE]
> En versión preliminar: puede ver los clasificadores que se pueden entrenar en el explorador de contenido expandiendo **Clasificadores entrenables** en el panel de filtros. Los clasificadores que se pueden entrenar mostrarán automáticamente el número de incidentes que se encuentran en SharePoint, Teams y OneDrive, sin necesidad de etiquetar.
> Si no desea usar esta característica, debe presentar una solicitud con Soporte técnico de Microsoft. Esto deshabilitará la presentación de los datos confidenciales que no se usan en ninguna directiva de etiquetado en el Explorador de contenido. También puede deshabilitar el examen de los datos. Si el examen está desactivado, el etiquetado de confidencialidad y las directivas DLP con esos clasificadores no funcionarán.

### <a name="where-you-can-use-classifiers"></a>Donde puede usar clasificadores

Los clasificadores están disponibles para usarse como condición para el [etiquetado automático de Office con etiquetas de confidencialidad](apply-sensitivity-label-automatically.md), aplicar [automáticamente la directiva de etiquetas de retención en función de una condición](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) y en [el cumplimiento de la comunicación](communication-compliance.md).

Las etiquetas de confidencialidad pueden usar clasificadores como condiciones; consulte [Aplicación automática de una etiqueta de confidencialidad al contenido](apply-sensitivity-label-automatically.md).

> [!IMPORTANT]
> Los clasificadores solo funcionan con elementos que no están cifrados.

## <a name="types-of-classifiers"></a>Tipos de clasificadores

- **Clasificadores previamente entrenados** : Microsoft ha creado y entrenado previamente varios clasificadores que puede empezar a usar sin entrenarlos. Estos clasificadores aparecerán con el estado de `Ready to use`.
- **clasificadores entrenables personalizados** : si tiene necesidades de clasificación que se extienden más allá de lo que cubren los clasificadores previamente entrenados, puede crear y entrenar sus propios clasificadores.

### <a name="pre-trained-classifiers"></a>Clasificadores previamente entrenados

Microsoft 365 incluye varios clasificadores previamente entrenados:

- **Adulto, racy y gory**: detecta imágenes de estos tipos. Las imágenes deben tener un tamaño de entre 50 kilobytes (KB) y 4 megabytes (MB) y superar los 50 x 50 píxeles de alto x ancho. El examen y la detección son compatibles con Exchange Online mensajes de correo electrónico y los canales y chats de Microsoft Teams. Detecta contenido en archivos .jpeg, .png, .gif y .bmp.

- **Acuerdos**: detecta contenido relacionado con contratos legales como contratos de no divulgación, declaraciones de trabajo, contratos de préstamo y arrendamiento, contratos de empleo y contratos de no competencia. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.

- **Quejas de clientes**: el clasificador de quejas de clientes detecta comentarios y quejas realizadas sobre los productos o servicios de su organización. Este clasificador puede ayudarle a cumplir los requisitos normativos sobre la detección y evaluación de las quejas, como los requisitos de consumer Financial Protection Bureau y Food and Drug Administration. En cumplimiento de comunicaciones, detecta contenido en archivos .msg y .eml. En el resto de servicios de Microsoft Purview Information Protection, detecta contenido en archivos .docx, .pdf, .txt, .rtf, .jpg, .jpeg, .png, .gif, .bmp, .svg.

- **Discriminación**: detecta un lenguaje discriminatorio explícito y es sensible al lenguaje discriminatorio contra las comunidades afroamericanas y negras en comparación con otras comunidades.

- **Finanzas**: detecta contenido en las categorías de finanzas corporativas, contabilidad, economía, banca e inversión. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **Acoso**: Detecta una categoría específica de elementos de texto en lenguaje ofensivo relacionados con la conducta ofensiva dirigida a una o varias personas en función de los siguientes rasgos: raza, origen étnico, religión, origen nacional, género, orientación sexual, edad, discapacidad. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.

- **Atención sanitaria**: detecta contenido en aspectos de administración médica y sanitaria, como servicios médicos, diagnósticos, tratamientos, reclamaciones, etc. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **RR. HH**.: detecta contenido en categorías relacionadas con recursos humanos de contratación, entrevista, contratación, formación, evaluación, advertencia y terminación. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **IP**: detecta contenido en categorías relacionadas con la propiedad intelectual, como secretos comerciales e información confidencial similar. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **TI**: detecta contenido en las categorías de tecnología de la información y ciberseguridad, como la configuración de red, la seguridad de la información, el hardware y el software. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **Asuntos jurídicos**: detecta contenido en categorías relacionadas con asuntos jurídicos, como litigios, procesos legales, obligación legal, terminología legal, ley y legislación. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.

- **Adquisición**: detecta contenido en categorías de licitación, cita, compra y pago por suministro de bienes y servicios. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **Blasfemia**: detecta una categoría específica de elementos de texto en lenguaje ofensivo que contienen expresiones que avergüenzan a la mayoría de las personas. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.

- **Reanudar**: detecta docx, .pdf, .rtf, .txt elementos que son cuentas textuales de las calificaciones personales, educativas, profesionales, experiencia profesional y otra información de identificación personal de un solicitante

- **Código fuente**: detecta elementos que contienen un conjunto de instrucciones e instrucciones escritas de lenguajes de programación de equipos en GitHub: ActionScript, C, C#, C++, Clojure, CoffeeScript, Go, Haskell, Java, JavaScript, Lua, MATLAB, Objective-C, Perl, PHP, Python, R, Ruby, Scala, Shell, Swift, TeX, Vim Script. Detecta contenido en .msg, .as, .h, .c, .cs, .cc, .cpp, .hpp, .cxx, .hh, .c++, .clj, .edn, .cljc, .cljs, .coffee, .litcoffee, .go, .hs, .lhs, .java, .jar, .js, .mjs, .lua, .m, .mm, .pl, .pm, .t, .xs, .pod, .php, .phar, .php4, .pyc, . R, .r, .rda, . Archivos RData, .rds, .rb, .scala, .sc, .sh, .swift.

  > [!NOTE]
  > El código fuente se entrena para detectar cuándo la mayor parte del texto es código fuente. No detecta texto de código fuente intercalado con texto sin formato.

- **Impuestos**: detecta el contenido de la relación fiscal, como planificación fiscal, formularios fiscales, presentación de impuestos, regulaciones fiscales. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, Archivos .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, xla.

- **Amenaza**: detecta una categoría específica de elementos de texto en lenguaje ofensivo relacionados con amenazas para cometer violencia o hacer daño físico o daño a una persona o propiedad.

- **Amenaza**: detecta una categoría específica de elementos de texto en lenguaje ofensivo relacionados con amenazas para cometer violencia o hacer daño físico o daño a una persona o propiedad. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.

Estos clasificadores aparecen en la **vista Clasificadores entrenables de** **clasificación** \> de datos portal de cumplimiento Microsoft Purview  \> con el estado de .`Ready to use`

![clasificadores-clasificadores previamente entrenados.](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Tenga en cuenta que los clasificadores integrados y globales que se pueden entrenar no proporcionan una lista exhaustiva o completa de términos o idioma en estas áreas. Además, los estándares lingüísticos y culturales cambian continuamente y, a la luz de estas realidades, Microsoft se reserva el derecho de actualizar estos clasificadores a su discreción. Aunque los clasificadores pueden ayudar a su organización a detectar estas áreas, los clasificadores no están diseñados para proporcionar el único medio de su organización de detectar o abordar el uso de dicho lenguaje. Su organización, no Microsoft ni sus subsidiarias, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, el examen, el bloqueo, la eliminación y la retención de cualquier contenido identificado por un clasificador previamente entrenado, incluido el cumplimiento de la privacidad local y otras leyes aplicables. Microsoft anima a consultar con el asesor legal antes de la implementación y el uso.

Nuestros clasificadores de amenazas, blasfemias, acoso y discriminación pueden examinar el contenido en estos idiomas:

- Árabe
- Chino (simplificado)
- Chino (tradicional)
- Neerlandés
- Inglés
- Francés
- Alemán
- Italiano
- Coreano
- Japonés
- Portugués
- Español

Todos los demás son inglés sólo en este momento.

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

## <a name="see-also"></a>Vea también

- [Etiquetas de retención](retention.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Impresión con dedo del documento](document-fingerprinting.md)
- [Obtenga información sobre tipos de información confidencial basada en coincidencias de datos exactas](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
