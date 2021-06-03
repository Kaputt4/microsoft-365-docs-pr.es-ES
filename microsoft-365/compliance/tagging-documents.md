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
description: Etiquetar documentos en un conjunto de revisión ayuda a quitar contenido innecesario e identificar contenido relevante en un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736308"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>Etiquetar documentos en un conjunto de revisión en Advanced eDiscovery

Organizar el contenido en un conjunto de revisión es importante para completar varios flujos de trabajo en el proceso de exhibición de documentos electrónicos. Esto incluye:

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

![Secciones de etiquetas en el panel de etiquetas](../media/TagTypes.png)

Puede organizar aún más las etiquetas anidandolas dentro de una sección. Por ejemplo, si el objetivo es identificar y etiquetar contenido con privilegios, se puede usar el anidamiento para dejar claro que un revisor puede etiquetar un documento como "Privileged" y seleccionar el tipo de privilegio comprobando la etiqueta anidada adecuada.

![Etiquetas anidadas dentro de una sección de etiquetas](../media/NestingTags.png)

## <a name="create-tags"></a>Crear etiquetas

Antes de aplicar etiquetas a documentos en el conjunto de revisión, debe crear una estructura de etiquetas.

1. Abra un conjunto de revisión y navegue a la barra de comandos y seleccione **Etiquetar por consulta**.

2. En el panel de etiquetado, seleccione **Administrar opciones de etiquetas**

3. Seleccione **Agregar sección de etiqueta**.

4. Escriba un título de grupo de etiquetas y una descripción opcional y, a continuación, haga clic en **Guardar**.

5. Seleccione el menú desplegable de triple punto junto al título del grupo de etiquetas y haga clic en **Agregar** casilla de verificación o **en El botón de opción Agregar**.

6. Escriba un nombre y una descripción para la casilla o el botón de opción.

7. Repita este proceso para crear nuevas secciones de etiquetas, opciones de etiquetas y casillas de verificación.

   ![Configurar la estructura de etiquetas](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a>Aplicación de etiquetas

Con la estructura de etiquetas en su lugar, los revisores pueden aplicar etiquetas a los documentos de un conjunto de revisión. Hay dos formas diferentes de aplicar etiquetas:

- Archivos de etiqueta

- Etiqueta por consulta

### <a name="tag-files"></a>Archivos de etiqueta

Tanto si selecciona un solo elemento como varios elementos de un conjunto de revisión, puede aplicar etiquetas a su selección haciendo clic en **Etiquetar archivos** en la barra de comandos. En el panel de etiquetado, puede seleccionar una etiqueta y se aplica automáticamente a los documentos seleccionados.

![Etiquetar archivos seleccionados](../media/TagFile2.png)

> [!NOTE]
> Las etiquetas solo se aplicarán a los elementos seleccionados de la lista de elementos.

### <a name="tag-by-query"></a>Etiqueta por consulta

El etiquetado por consulta le permite aplicar etiquetas a todos los elementos mostrados por una consulta de filtro que se aplica actualmente en el conjunto de revisión.

1. Anule la selección de todos los elementos del conjunto de revisión y vaya a la barra de comandos y **seleccione Etiquetar por consulta**.

2. En el panel de etiquetado, seleccione la etiqueta que desea aplicar.

3. En el **desplegable Selección de** etiquetas, hay tres opciones que determinan a qué elementos aplicar la etiqueta.

   - **Elementos que coinciden con la consulta aplicada:** aplica etiquetas a elementos específicos que coinciden con las condiciones de consulta de filtro.

   - **Incluir elementos de familia asociados:** aplica etiquetas a elementos específicos que coinciden con las condiciones de consulta de filtro y sus elementos de familia asociados. *Los elementos de* familia son elementos que comparten el mismo valor de metadatos de FamilyId.  

   - **Incluir elementos de conversación asociados:** aplica etiquetas a los elementos que coinciden con las condiciones de consulta de filtro y sus elementos de conversación asociados. *Los elementos de* conversación son elementos que comparten los mismos valores de metadatos de ConversationId.

   ![Selección de etiquetas](../media/TagByQuery2.png)

4. Haga **clic en Iniciar trabajo de etiquetado** para desencadenar el trabajo de etiquetado.

## <a name="tag-filter"></a>Filtro de etiquetas

Use el filtro de etiquetas en el conjunto de revisión para buscar o excluir rápidamente elementos de los resultados de la consulta en función de cómo se etiqueta un elemento. 

1. Seleccione **Filtros** para expandir el panel de filtro.

2. Seleccione y expanda **Propiedades de elemento**.

3. Desplácese hacia abajo para buscar el filtro denominado **Tag**, seleccione la casilla y, a continuación, haga clic en **Listo**.

4. Para incluir o excluir elementos con una etiqueta específica de una consulta, realice una de las siguientes acciones:

   - **Incluir elementos:** seleccione el valor de la etiqueta y **seleccione Igual a cualquiera en** el menú desplegable.

      O bien:

   - **Excluir elementos:** seleccione el valor de la etiqueta y **seleccione No es** igual a ninguno en el menú desplegable.

     ![Elementos de exclusión de filtro de etiquetas](../media/TagFilterExclude.png)

> [!NOTE]
> Asegúrese de actualizar la página para asegurarse de que el filtro de etiquetas muestra los cambios más recientes en la estructura de etiquetas.
