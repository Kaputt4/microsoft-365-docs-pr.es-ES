---
title: Etiquetar documentos en un conjunto de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: La etiquetación de documentos en un conjunto de revisiones ayuda a quitar contenido innecesario e identificar contenido relevante en un caso avanzado de eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285286"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Etiquetar documentos en un conjunto de revisión en eDiscovery avanzado

La organización de contenido en un conjunto de revisión es importante para completar varios flujos de trabajo en el proceso de exhibición de documentos electrónicos. Incluye lo siguiente:

- Selección de contenido innecesario

- Identificación del contenido relevante
 
- Identificación de contenido que debe ser revisado por un experto o un abogado

Cuando expertos, abogados u otros usuarios revisan el contenido de un conjunto de revisión, se pueden capturar sus opiniones relacionadas con el contenido mediante el uso de etiquetas. Por ejemplo, si la intención es deseleccionar contenido innecesario, un usuario puede etiquetar documentos con una etiqueta como "sin respuesta". Una vez que se ha revisado y etiquetado el contenido, se puede crear una búsqueda de conjunto de revisión para excluir cualquier Contenido etiquetado como "sin respuesta", lo que elimina este contenido de los pasos siguientes en el flujo de trabajo de eDiscovery. El panel de etiquetas se puede personalizar para cada caso, de modo que las etiquetas puedan admitir el flujo de trabajo de revisión previsto.

## <a name="tag-types"></a>Tipos de etiquetas

La exhibición avanzada de documentos electrónicos proporciona dos tipos de etiquetas:

- **Etiquetas de opción única** : limita a los usuarios a seleccionar una sola etiqueta dentro de un grupo. Esto puede ser útil para asegurarse de que los usuarios no seleccionan etiquetas conflictivas como "receptivo" y "sin respuesta". Se mostrarán como botones de opción.

- **Etiquetas de varias opciones** : permite a los usuarios seleccionar varias etiquetas dentro de un grupo. Se mostrarán como casillas de verificación.

## <a name="tag-structure"></a>Estructura de etiquetas

Además de los tipos de etiqueta, la estructura de la forma en que se organizan las etiquetas en el panel etiqueta puede usarse para que los documentos de etiquetado sean más intuitivos. Las etiquetas se agrupan por secciones. Revisión Set Search admite la capacidad de buscar por etiqueta y por etiqueta. Esto significa que puede crear una búsqueda de conjunto de revisión para recuperar documentos etiquetados con cualquier etiqueta en una sección.

![Secciones de etiquetas en el panel etiqueta](../media/Tagtypes.png)

Las etiquetas se pueden organizar en mayor profundidad si se anidan dentro de una sección. Por ejemplo, si la intención es identificar y etiquetar contenido privilegiado, se puede usar la anidación para dejar claro que un usuario puede etiquetar un documento como "privilegiado" y seleccionar el tipo de privilegio comprobando la etiqueta anidada adecuada.

![Etiquetas anidadas dentro de una sección de etiqueta](../media/Nestingtags.png)

## <a name="applying-tags"></a>Aplicar etiquetas

Hay varias formas de aplicar una etiqueta al contenido.

### <a name="tagging-a-single-document"></a>Etiquetado de un solo documento

Al ver un documento en un conjunto de revisiones, puede mostrar las etiquetas que puede usar una revisión haciendo clic en **Panel de etiquetado**.

![Haga clic en el panel de etiquetas para mostrar el panel de etiquetas](../media/Singledoctag.png)

Esto le permitirá aplicar etiquetas al documento que se muestra en el visor.

### <a name="bulk-tagging"></a>Etiquetado masivo

La etiquetación en masa se puede realizar seleccionando varios archivos en la cuadrícula de resultados y, a continuación, usando las etiquetas en el **Panel de etiquetado** , de forma similar a la etiqueta de un único documento. Para realizar un etiquetado masivo, puede seleccionar las etiquetas dos veces; el primer clic aplicará la etiqueta y la segunda se asegurará de que la etiqueta se borre para todos los archivos seleccionados.

![Una captura de pantalla de una descripción de teléfono móvil generada automáticamente](../media/Bulktag.png)

> [!NOTE]
> Cuando se realiza un etiquetado masivo, el panel etiquetado muestra un recuento de archivos que se etiquetan para cada etiqueta del panel.

### <a name="tagging-in-other-review-panels"></a>Etiquetado en otros paneles de revisión

Al revisar los documentos, puede usar los otros paneles de revisión para revisar otras características de los documentos en la cuadrícula de resultados. Esto incluye la revisión de otros documentos relacionados, subprocesos de correo electrónico, Near duplicados y duplicados de hash. Por ejemplo, cuando está revisando documentos relacionados (mediante el panel revisión de **familia de documentos** ), puede reducir significativamente el tiempo de revisión mediante el etiquetado en masa de los documentos relacionados. Por ejemplo, si un mensaje de correo electrónico tiene varios datos adjuntos y desea asegurarse de que toda la familia se etiquete de forma coherente.

Por ejemplo, aquí se muestra cómo mostrar el **Panel de etiquetado** al usar el panel de revisión de la **familia de documentos** :

1. Con el panel revisión abierto para un documento seleccionado (por ejemplo, Mostrar la lista de contenido relacionado en el panel revisión de **familia de documentos** , haga clic en **etiquetar documentos** en el panel revisión de familia de documentos.

   El panel de etiquetado se muestra como una ventana emergente.

2. Elija una o más etiquetas para aplicar el documento seleccionado. 

3. Para etiquetar todos los documentos, seleccione todos los documentos en el panel de la **familia de documentos** , haga clic en **etiquetar documentos**y, a continuación, elija las etiquetas que se aplicarán a toda la familia de documentos.

![Captura de pantalla de una descripción de post de medio social generada automáticamente](../media/Relatedtag.png)
