---
title: 'Trabajar con temas en el centro de temas (versión preliminar) '
description: Cómo trabajar con temas en el centro de temas.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 464a926b99cceeb652756ad6d1456c5e17d2a925
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988743"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a>Trabajar con temas en el centro de temas (versión preliminar)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).


En el centro de temas, un administrador de información puede revisar temas que se han reconocido y descubierto en las ubicaciones de origen de SharePoint que ha especificado y puede confirmarlos o rechazarlos. Un administrador de información también puede crear y publicar nuevas páginas de temas si no se encuentra ninguna en la detección de temas, o editar las existentes si es necesario actualizarlas.

## <a name="requirements"></a>Requirements

Para poder trabajar en el centro de temas, necesita tener los permisos necesarios. Su administrador puede agregarlo durante la configuración de la administración de la [información](set-up-topic-experiences.md)o [posteriormente](give-user-permissions-to-the-topic-center.md)se pueden agregar nuevos usuarios.

Los usuarios del centro de temas pueden recibir dos conjuntos de permisos:

- Crear y editar temas: cree nuevos temas o actualice el contenido de los temas, como la descripción, documentos y personas asociadas.

- Administración de temas: Use el panel de administración de temas para revisar los temas en la organización. Los usuarios pueden realizar acciones como confirmar y rechazar temas.


## <a name="review-suggested-topics"></a>Revisión de temas sugeridos

En la Página principal del centro de temas, los temas que se detectaron en las ubicaciones de origen de SharePoint especificadas se mostrarán en la pestaña **sugerido** . Un usuario con permisos para administrar temas puede revisar los temas no confirmados y elegir confirmarlos o rechazarlos.


Para revisar un tema sugerido:

1. En la pestaña **sugerido** , seleccione el tema para abrir la página del tema.</br>

2. En la página del tema, revise la página del tema y seleccione **Editar** si necesita realizar cambios en la página.

3. En la Página principal del centro de conocimiento, para el tema seleccionado, puede:

    1. Seleccione la comprobación para confirmar que desea conservar el tema.
    
    1. Seleccione la **x** si desea rechazar el tema.

    Los temas confirmados se quitarán de la lista sin **confirmar** y se mostrarán ahora en la pestaña **confirmada** .

    Los temas rechazados se quitarán de la lista sin **confirmar** y ahora se mostrarán en la pestaña **rechazado o excluido** .

## <a name="review-confirmed-topics"></a>Revisar los temas confirmados

En la Página principal del centro de temas, los temas que se detectaron en las ubicaciones de origen de SharePoint especificadas y que han sido confirmados por un administrador de información o crowdsourced confirmado por dos o más personas a través del mecanismo de comentarios de tarjeta aparecerán en la pestaña **confirmado** . Un usuario con permisos para administrar temas puede revisar los temas confirmados y elegir rechazarlos.


Para revisar un tema confirmado:

1. En la pestaña **confirmada** , seleccione el tema para abrir la página del tema.</br>

2. En la página del tema, revise la página del tema y seleccione **Editar** si necesita realizar cambios en la página.

3. También puede rechazarla.

## <a name="review-published-topics"></a>Revisar los temas publicados
Se han editado los temas publicados para que la información específica aparezca siempre a quien encuentre la página. Los temas creados manualmente se muestran aquí.

   
## <a name="create-a-new-topic"></a>Crear un tema nuevo

Un usuario con los permisos crear o editar tema puede crear un nuevo tema si es necesario. Es posible que deba hacerlo si no se ha descubierto el tema a través de la detección o si la tecnología de AI no ha encontrado suficientes pruebas para establecerlo como tema.

Para crear un nuevo tema:

1. En la página centro de temas, seleccione **nuevo** y, a continuación, seleccione **Página de tema**.

    ![Tema nuevo](../media/content-understanding/k-new-topic.png)

2. En la página nuevo tema, puede rellenar la información de la nueva plantilla de tema:

    1. En la sección **nombre este tema** , escriba el nombre del nuevo tema.
    
    1. En la sección **Nombres alternativos** , escriba nombres o acrónimos que también se usan para hacer referencia al tema.
    
    1. En la sección **Descripción breve** , escriba una descripción de una o dos frases del tema. Este texto se utilizará para la tarjeta de temas asociada.
    
    1. En la sección **personas** , escriba los nombres de los expertos en la materia para el tema.
    
    1. En la sección **archivos y páginas** , seleccione **Agregar** y, a continuación, en la página siguiente, puede seleccionar archivos de OneDrive asociados o páginas de SharePoint Online.
    
    1. En la sección **sitios** , seleccione **Agregar**. En el panel  **sitios** que se muestra, seleccione los sitios asociados al tema.

    ![Nueva página del tema](../media/content-understanding/k-new-topic-page.png)
    
3. Si necesita agregar otros componentes a la página, como texto, imágenes, elementos Web, vínculos, etc., seleccione el icono de lienzo en la parte central de la página para buscarlos y agregarlos.

    ![Agregar elementos a la página](../media/content-understanding/static-icon.png)

4. Cuando haya terminado, seleccione **publicar** para publicar la página del tema. Las páginas de temas publicadas se mostrarán en la ficha **páginas** .

> [!Note] 
> La página del nuevo tema se compone de elementos Web compatibles con la *red de conocimiento*. Esto significa que, a medida que AI recopila más información sobre el tema, la información de estos elementos Web se actualizará con sugerencias para hacer que la página sea más útil para los usuarios.


## <a name="edit-an-existing-topic-page"></a>Editar una página de tema existente

Las páginas de temas existentes se pueden encontrar en la página **páginas** . 

1. En la página centro de temas, seleccione **páginas**.

2. En la página **páginas** , verá una lista de páginas de temas. Use el cuadro de búsqueda para buscar la página del tema que desee actualizar. Haga clic en el nombre de la página del tema que desea editar.

3. En la página del tema, seleccione **Editar**.

4. Realice los cambios necesarios en la página. Esto incluye actualizaciones para los siguientes campos:

    1. Nombres alternativos
    1. Description
    1. Personas
    1. Archivos y páginas
    1. Sitios
    1. También puede agregar elementos estáticos a la página (por ejemplo, texto, imágenes o vínculo) seleccionando el icono lienzo.

5. Seleccione **volver a publicar** para guardar los cambios.

<!--## See also-->


