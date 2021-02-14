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
description: El etiquetado de documentos en un conjunto de revisión ayuda a quitar contenido innecesario e identificar el contenido relevante en un caso de eDiscovery avanzado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285286"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Etiquetar documentos en un conjunto de revisión en eDiscovery avanzado

Organizar el contenido de un conjunto de revisión es importante para completar varios flujos de trabajo en el proceso de exhibición de documentos electrónicos. Incluye lo siguiente:

- Selección de contenido innecesario

- Identificación de contenido relevante
 
- Identificación del contenido que debe revisar un experto o un abogado

Cuando expertos, abogados u otros usuarios revisan el contenido de un conjunto de revisión, sus opiniones relacionadas con el contenido se pueden capturar mediante etiquetas. Por ejemplo, si la intención es eliminar contenido innecesario, un usuario puede etiquetar documentos con una etiqueta como "no responde". Después de revisar y etiquetar el contenido, se puede crear una búsqueda de conjunto de revisión para excluir cualquier contenido etiquetado como "no dinámico", lo que elimina este contenido de los siguientes pasos del flujo de trabajo de exhibición de documentos electrónicos. El panel de etiquetas se puede personalizar en cada caso para que las etiquetas admitan el flujo de trabajo de revisión previsto.

## <a name="tag-types"></a>Tipos de etiquetas

EDiscovery avanzado proporciona dos tipos de etiquetas:

- **Etiquetas de opción** única: restringe a los usuarios a seleccionar una sola etiqueta dentro de un grupo. Esto puede ser útil para garantizar que los usuarios no seleccionen etiquetas conflictivas, como "responsive" y "non-responsive". Aparecerán como botones de radio.

- **Etiquetas de opción múltiple:** permitir a los usuarios seleccionar varias etiquetas dentro de un grupo. Aparecerán como casillas.

## <a name="tag-structure"></a>Estructura de etiquetas

Además de los tipos de etiquetas, la estructura de cómo se organizan las etiquetas en el panel de etiquetas se puede usar para que el etiquetado de documentos sea más intuitivo. Las etiquetas se agrupan por secciones. La búsqueda del conjunto de revisión admite la capacidad de buscar por etiqueta y por sección de etiqueta. Esto significa que puede crear una búsqueda de conjunto de revisión para recuperar documentos etiquetados con cualquier etiqueta de una sección.

![Secciones de etiquetas en el panel de etiquetas](../media/Tagtypes.png)

Las etiquetas se pueden organizar anidando dentro de una sección. Por ejemplo, si la intención es identificar y etiquetar contenido con privilegios, el anidamiento puede usarse para dejar claro que un usuario puede etiquetar un documento como "Privileged" y seleccionar el tipo de privilegio comprobando la etiqueta anidada adecuada.

![Etiquetas anidadas dentro de una sección de etiquetas](../media/Nestingtags.png)

## <a name="applying-tags"></a>Aplicar etiquetas

Hay varias formas de aplicar una etiqueta al contenido.

### <a name="tagging-a-single-document"></a>Etiquetado de un solo documento

Al ver un documento en un conjunto de revisión, puede mostrar las etiquetas que puede usar una revisión haciendo clic en **el panel de etiquetado.**

![Haga clic en Panel de etiquetas para mostrar el panel de etiquetas](../media/Singledoctag.png)

Esto le permitirá aplicar etiquetas al documento que se muestra en el visor.

### <a name="bulk-tagging"></a>Etiquetado masivo

El etiquetado masivo se puede realizar seleccionando varios archivos en la cuadrícula de resultados y, a continuación, usando las etiquetas del **panel** de etiquetado de forma similar a etiquetar documentos individuales. El des etiquetado masivo se puede realizar seleccionando etiquetas dos veces; El primer clic aplicará la etiqueta y la segunda se asegurará de que la etiqueta esté desactivada para todos los archivos seleccionados.

![Captura de pantalla de una descripción de teléfono móvil generada automáticamente](../media/Bulktag.png)

> [!NOTE]
> Al etiquetar en masa, el panel de etiquetado mostrará un recuento de archivos etiquetados para cada etiqueta del panel.

### <a name="tagging-in-other-review-panels"></a>Etiquetado en otros paneles de revisión

Al revisar documentos, puede usar los demás paneles de revisión para revisar otras características de los documentos en la cuadrícula de resultados. Esto incluye revisar otros documentos relacionados, subprocesos de correo electrónico, casi duplicados y duplicados hash. Por ejemplo, al revisar documentos relacionados (mediante  el panel de revisión de la familia de documentos), puede reducir significativamente el tiempo de revisión mediante el etiquetado masivo de documentos relacionados. Por ejemplo, si un mensaje de correo electrónico tiene varios datos adjuntos y desea asegurarse de que toda la familia se etiqueta de forma coherente.

Por ejemplo, aquí se muestra cómo mostrar el panel de etiquetado al usar el **panel** **de revisión** de la familia de documentos:

1. Con el panel de revisión abierto para un documento seleccionado  (por ejemplo,  mostrando la lista de contenido relacionado en el panel de revisión de familia de documentos, haga clic en Etiquetar documentos bajo el panel de revisión de familia de documentos.

   El panel de etiquetado se muestra como una ventana emergente.

2. Elija una o más etiquetas para aplicar el documento seleccionado. 

3. Para etiquetar todos los documentos, seleccione todos los documentos en el **panel** Familia de documentos, haga clic en Etiquetar documentos y, a continuación, elija las etiquetas que se aplicarán a toda la familia de documentos.

![Captura de pantalla de una publicación de redes sociales Generada automáticamente](../media/Relatedtag.png)
