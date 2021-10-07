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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Etiquetar documentos en un conjunto de revisión ayuda a quitar contenido innecesario e identificar contenido relevante en un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 43b0bf42bcd94f0bc3ade169ee5b41ee33dcbc5a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190718"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Etiquetar documentos en un conjunto de revisión en Advanced eDiscovery

Organizar el contenido en un conjunto de revisión es importante para completar varios flujos de trabajo en el proceso de exhibición de documentos electrónicos. Incluye lo siguiente:

- Selección de contenido innecesario

- Identificación de contenido relevante

- Identificar el contenido que debe revisar un experto o un abogado

Cuando expertos, abogados u otros usuarios revisan el contenido de un conjunto de opiniones, sus opiniones relacionadas con el contenido se pueden capturar mediante etiquetas. Por ejemplo, si el objetivo es crear contenido innecesario, un usuario puede etiquetar documentos con una etiqueta como "no responde". Después de revisar y etiquetar el contenido, se puede crear una búsqueda de conjunto de revisión para excluir cualquier contenido etiquetado como "no responde". Este proceso elimina el contenido que no responde de los siguientes pasos del flujo de trabajo de exhibición de documentos electrónicos. El panel de etiquetado de un conjunto de revisión se puede personalizar para cada caso de modo que las etiquetas admitan el flujo de trabajo de revisión previsto para el caso.

> [!NOTE]
> El ámbito de las etiquetas es Advanced eDiscovery caso. Esto significa que un caso solo puede tener un conjunto de etiquetas que los revisores pueden usar para etiquetar documentos del conjunto de revisión. No puede configurar un conjunto diferente de etiquetas para su uso en distintos conjuntos de revisión en el mismo caso.

## <a name="tag-types"></a>Tipos de etiquetas

Advanced eDiscovery proporciona dos tipos de etiquetas:

- **Etiquetas de opción** única: restringe a los revisores a seleccionar una sola etiqueta dentro de un grupo. Estos tipos de etiquetas pueden ser útiles para garantizar que los revisores no seleccionen etiquetas en conflicto como "responsive" y "non-responsive". Las etiquetas de opción única aparecen como botones de radio.

- **Etiquetas de opción múltiple:** permitir que las revisiones seleccionen varias etiquetas dentro de un grupo. Estos tipos de etiquetas aparecen como casillas de verificación.

## <a name="tag-structure"></a>Estructura de etiquetas

Además de los tipos de etiquetas, la estructura de cómo se organizan las etiquetas en el panel de etiquetas se puede usar para hacer que los documentos de etiquetado sean más intuitivos. Las etiquetas se agrupan por secciones. La búsqueda de conjunto de revisión admite la capacidad de buscar por etiqueta y por sección de etiquetas. Esto significa que puede crear una búsqueda de conjunto de revisión para recuperar documentos etiquetados con cualquier etiqueta de una sección.

![Secciones de etiquetas en el panel de etiquetas.](../media/TagTypes.png)

Puede organizar aún más las etiquetas anidandolas dentro de una sección. Por ejemplo, si el objetivo es identificar y etiquetar contenido con privilegios, se puede usar el anidamiento para dejar claro que un revisor puede etiquetar un documento como "Privileged" y seleccionar el tipo de privilegio comprobando la etiqueta anidada adecuada.

![Etiquetas anidadas dentro de una sección de etiquetas.](../media/NestingTags.png)

## <a name="creating-and-applying-tags"></a>Creación y aplicación de etiquetas

El etiquetado de elementos en conjuntos de revisión es un proceso de dos pasos. El primer paso es crear las etiquetas que luego se aplican para revisar los elementos del conjunto. Después de crear etiquetas, usted y otros revisores pueden aplicarlas a los elementos de un conjunto de revisión. Como se explicó anteriormente, un Advanced eDiscovery caso solo puede tener un conjunto de etiquetas que los revisores pueden usar para etiquetar elementos del conjunto de revisión.

### <a name="create-tags"></a>Crear etiquetas

Antes de aplicar etiquetas a los elementos de un conjunto de revisión, debe crear una estructura de etiquetas.

1. Abra un conjunto de revisión, vaya a la barra de comandos y seleccione **Etiquetar archivos**.

2. En la **página desplegable Archivos de** etiquetas, haga clic en **Crear/editar etiquetas**.

   ![Haga clic en Crear/editar etiquetas en la página desplegable.](../media/CreateAeDTags1.png)

3. En la **página Etiquetas,** seleccione **Agregar sección**.

4. Escriba un título de grupo de etiquetas y una descripción opcional y, a continuación, haga clic en **Guardar**.

5. Seleccione el menú desplegable de triple punto junto al título del grupo de etiquetas y haga clic en **Agregar** casilla de verificación o **en El botón de opción Agregar**.

6. Escriba un nombre y una descripción para la casilla o el botón de opción.

7. Repita este proceso para crear nuevas secciones de etiquetas, opciones de etiquetas y casillas de verificación. Por ejemplo, la siguiente captura de pantalla muestra un grupo de etiquetas denominado **Review**, que consta de casillas **Responsive** y **Not-responsive.**

   ![Configurar la estructura de etiquetas.](../media/ManageTagOptions3.png)

### <a name="apply-tags"></a>Apply tags

Con la estructura de etiquetas en su lugar, los revisores pueden aplicar etiquetas a los elementos de un conjunto de revisión configurando las opciones de etiquetado.

1. En la barra de comandos del conjunto de revisión, seleccione **Etiquetar** archivos para mostrar la **página** desplegable Archivos de etiqueta (también denominada *panel de etiquetado).*

   ![Haga clic en Etiquetar archivos en la barra de comandos para abrir el panel de etiquetado.](../media/TagFilesFlyoutPage.png)

2. En la **página desplegable Archivos** de etiqueta, puede establecer las siguientes opciones para configurar cómo etiquetar los elementos que se muestran en el conjunto de revisión. Las consultas de filtros o filtros aplicadas actualmente al conjunto de revisión determinan los elementos que se muestran y, por lo tanto, los elementos a los que se pueden aplicar etiquetas. Para obtener más información, vea [Consulta y filtrar contenido en un conjunto de revisión.](review-set-search.md)

   - **Elija la selección**. Elija una de las siguientes opciones para determinar el ámbito de los elementos a los que aplicar etiquetas.

      - **Etiquetar elementos seleccionados:** esta opción aplica etiquetas a los elementos seleccionados. Puede seleccionar elementos antes o después de iniciar el panel de etiquetado. Esta opción muestra (en tiempo real) el número de elementos seleccionados que se etiquetarán.

      - **Etiquetar todos los elementos de la** lista: esta opción aplica etiquetas a todos los elementos que se muestran en el conjunto de revisión. Esta opción muestra el número total de elementos que se etiquetarán.

   - **Expandir selección:** use las siguientes opciones para etiquetar elementos adicionales relacionados con elementos etiquetados en el conjunto de revisión.

      - **Incluir elementos de familia asociados:** esta opción aplica la misma etiqueta a los elementos de familia asociados de los elementos etiquetados.  *Los elementos de* familia son elementos que comparten el mismo valor de **la propiedad de metadatos FamilyId.** Por ejemplo, un documento adjunto a un mensaje de correo electrónico comparte el mismo **FamilyId** que el mensaje de correo electrónico. Por lo tanto, si esta opción está seleccionada para este ejemplo, el mensaje de correo electrónico y el documento se etiquetan, aunque es posible que el documento no se incluya en la lista de elementos del conjunto de revisión.

      - **Incluir elementos de conversación** asociados: esta opción aplica la misma etiqueta a todos los elementos que están en la misma conversación Teams o Yammer que los elementos etiquetados. *Los elementos de* conversación son elementos que comparten el mismo valor de **la propiedad de metadatos ConversationId.** Todos los mensajes, publicaciones y el archivo de transcripción correspondiente de una conversación comparten el mismo **ConversationId**. Si se selecciona esta opción, todos los elementos de la misma conversación (y archivo de transcripción) se etiquetan, aunque algunos de esos elementos de conversación podrían no incluirse en la lista de elementos del conjunto de opiniones. Para obtener más información acerca de los elementos de conversación, vea la sección "Agrupación" en Advanced eDiscovery flujo de trabajo para el contenido [de Microsoft Teams](teams-workflow-in-advanced-ediscovery.md#grouping).

      - **Ninguno:** esta opción no aplica etiquetas a elementos de familia o elementos de conversación. Solo aplica etiquetas a los elementos seleccionados o a todos los elementos de la lista de conjunto de revisión.

   > [!NOTE]
   > La inclusión de elementos de familia o conversación asociados no cambiará el número de elementos que se muestran en los elementos seleccionados Etiquetar **o** Etiquetar todos los elementos de las **opciones de** lista. En otras palabras, no se muestra el número de elementos asociados que se etiquetarán.

   - **Asignar etiquetas:** en esta sección se muestran las etiquetas (organizadas por grupos de etiquetas) que se pueden aplicar a los documentos. Solo puede aplicar una etiqueta de opción única (identificada por un botón de radio) por grupo de etiquetas. Sin embargo, puede aplicar varias etiquetas de opción múltiple (que se identifican mediante una casilla).

3. Haz clic en Aplicar **etiquetas** para aplicar las etiquetas según la configuración.

   Se **muestra el mensaje de estado** Aplicar etiquetas para cada grupo de etiquetas en el panel de etiquetado para indicar que se ha iniciado un trabajo de etiquetado. Las etiquetas para cada grupo de etiquetas de la **sección Asignar etiquetas** se en gris hasta que se complete el trabajo.

> [!TIP]
> Si estás en el proceso de configurar la configuración en el panel de etiquetado, pero quieres empezar de nuevo, haz clic en **Restablecer** asignación de etiquetas para borrar la configuración actual. Este control no se aplica a los elementos que ya están etiquetados y no cambia ni quita etiquetas de elementos etiquetados anteriormente.  

#### <a name="monitor-tagging-jobs"></a>Supervisar trabajos de etiquetado

Al etiquetar un gran número de elementos (o seleccionar la **opción Etiquetar** todos los elementos de la lista ), se crea un trabajo **de documentos** de etiquetado. En este caso, puede ver el estado de este trabajo en **la** pestaña Trabajos. Esto le ayuda a realizar un seguimiento de los trabajos de etiquetado grandes que pueden tardar mucho tiempo en completarse. En algunos casos, es posible que  se complete un trabajo de etiquetado, pero todavía se muestra el mensaje de estado Aplicar etiquetas en el panel de etiquetado. Para actualizar el estado de los trabajos de etiquetado, haga clic **en Actualizar en** la barra de comandos del conjunto de revisión.

## <a name="removing-tags"></a>Quitar etiquetas

Puede quitar etiquetas de elementos de un conjunto de revisión. Sin embargo, no puede quitar una etiqueta de opción única que se haya aplicado a un elemento de conjunto de revisión. Solo puede cambiar una etiqueta de opción única a otra etiqueta de opción única dentro del mismo grupo de etiquetas.

Para quitar una etiqueta:

1. Seleccione los elementos de los que desea quitar la etiqueta.

2. Haga **clic en Etiquetar** archivos para mostrar el panel de etiquetado.

3. En **Asignar etiquetas**, anule la selección de la etiqueta y, a continuación, haga clic **en Aplicar etiquetas**.

También puede usar el procedimiento anterior para cambiar la etiqueta aplicada a los elementos seleccionados. Después de anular la selección de la etiqueta actual, puede seleccionar una diferente.
