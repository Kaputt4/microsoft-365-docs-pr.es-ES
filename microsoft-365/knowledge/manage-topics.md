---
title: Administrar temas en el centro de temas en Temas de Microsoft Viva
description: Cómo administrar temas en el Centro de temas.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: e2cbf62339e2ade240474fed9db86e68dc0b3bb4
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760127"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a>Administrar temas en el centro de temas en Temas de Microsoft Viva

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


En el Centro de temas de Viva  Topics, un administrador de conocimientos puede ver la página Administrar temas para revisar los temas que se han identificado en ubicaciones de origen de SharePoint según lo especificado por el administrador de conocimientos.  

   ![Centro de temas](../media/knowledge-management/topic-center.png) </br> 



Los administradores de conocimientos ayudan a guiar los temas descubiertos a través del ciclo de vida del tema en el que los temas son:

- **Sugerido:** AI ha identificado un tema y tiene suficientes recursos, conexiones y propiedades compatibles.
- **Confirmado:** se valida un tema sugerido por AI. La validación se realiza mediante confirmación de un administrador de conocimientos. Además, se puede confirmar un tema si al menos dos usuarios dan comentarios positivos a través de la pregunta de comentarios en la tarjeta del tema.
- **Publicado:** un tema confirmado que se ha seleccionado: se han realizado ediciones manuales para mejorar su calidad.
- **Eliminado:** un administrador de conocimientos rechaza un tema y ya no será visible para los visores. El tema puede estar en cualquier estado cuando se quita (sugerido, confirmado o publicado). Cuando se quita un tema publicado, la página con los detalles seleccionados tendrá que eliminarse manualmente a través de la Biblioteca de páginas del centro de temas.

   ![Gráfico de ciclo de vida de temas](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> En la página Administrar temas, cada administrador de conocimientos solo podrá ver los temas en los que tienen acceso a los archivos y páginas del tema. Esto se reflejará en los temas que se enumeran en  las pestañas **Sugerido**, **Confirmado,** **Eliminado** y Publicado. Sin embargo, los recuentos de temas muestran los recuentos totales de la organización.

## <a name="requirements"></a>Requisitos

Para administrar temas en el centro de temas, debe:
- Tener una licencia de Viva Topics.

- Tener el [**permiso Quién puede administrar temas.**](./topic-experiences-user-permissions.md) Los administradores de conocimientos pueden conceder a los usuarios este permiso en la configuración de permisos del tema Temas de Viva. 

No podrá ver la página Administrar temas en el centro de temas a menos que tenga el permiso **Quién puede administrar temas.**

En el centro de temas, un administrador de conocimientos puede revisar los temas que se han identificado en las ubicaciones de origen de SharePoint que especificó y puede confirmarlos o rechazarlos. Un administrador de conocimientos también puede crear y publicar nuevas páginas de temas si no se encontró una en la detección de temas o editar las existentes si es necesario actualizarlas.


## <a name="review-suggested-topics"></a>Revisar temas sugeridos

En la página Administrar temas del centro de temas, los temas que se detectaron en las ubicaciones de origen de SharePoint especificadas aparecerán en la **pestaña Sugerencias.** Si es necesario, un administrador de conocimientos puede revisar temas no confirmados y elegir confirmarlos o rechazarlos.

   ![Temas sugeridos](../media/knowledge-management/quality-score.png) </br> 

Para revisar un tema sugerido:

1. En la **página Administrar temas,** seleccione la **pestaña Sugerencia** y seleccione el tema para abrir la página del tema.</br>

2. En la página del tema, revise la página del tema y **seleccione Editar** si necesita realizar cambios en la página. La publicación de cualquier modificación moverá este tema a la **pestaña Publicado.**

3. Después de revisar el tema, vuelva a la página Administrar temas. Para el tema seleccionado, puede:

   - Seleccione la marca de verificación para confirmar el tema.
    
   - Seleccione la **x** si desea rechazar el tema.

    Los temas confirmados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **lista** Confirmados.

    Los temas rechazados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **pestaña Eliminado.**

   </br> 

### <a name="quality-score"></a>Puntuación de calidad

Cada tema que aparece en la página Temas sugeridos tiene asignada una puntuación de calidad. La puntuación de calidad es un reflejo de la cantidad de información que el usuario promedio verá para la información sobre el tema, teniendo en cuenta que cada usuario puede ver más o menos información debido a los permisos que podrían o no tener en la información de un tema. 

La puntuación de calidad puede ayudar a proporcionar información sobre los temas con más información y puede ser útil para encontrar temas que pueden necesitar editarse manualmente. Por ejemplo, un tema con una puntuación de calidad inferior puede ser el resultado de que algunos usuarios no tengan permisos de SharePoint para los archivos o sitios pertinentes que AI ha incluido en el tema. A continuación, un colaborador podría editar el tema para incluir la información (cuando corresponda), que, a continuación, se podrá ver para todos los usuarios que puedan ver el tema.

La puntuación de calidad puede oscilar entre 1 y 100. Un tema recién descubierto tendrá una puntuación de calidad de 0 hasta que dos o más usuarios lo han visto. La puntuación de calidad de cada usuario viene determinada por una serie de factores, como la cantidad de contenido que se muestra para el usuario específico, que se controla los permisos del usuario, ya que cada página de temas tiene el recorte de seguridad en su lugar para el contenido generado por la IA. La puntuación de calidad que se muestra en la **pestaña Temas** sugeridos es un promedio de cada puntuación individual de los usuarios.

### <a name="impressions"></a>Impresiones

La **columna Impresiones** muestra el número de veces que se ha mostrado un tema a los usuarios finales. Esto incluye vistas a través de tarjetas de tema en la búsqueda, a través de los resaltados de temas y a través de las vistas del centro de temas. No refleja el clic en estos temas, sino que se ha mostrado el tema. La columna Impresiones se mostrará para los temas de  las **pestañas** **Sugeridos,** Confirmados, Publicados y Eliminados de la página Administrar temas.

## <a name="confirmed-topics"></a>Temas confirmados

En la página Administrar temas, los temas detectados en las ubicaciones de origen de SharePoint especificadas y confirmados por un administrador de  conocimientos o "crowdsourced" confirmados por dos o más personas a través del mecanismo de comentarios de tarjeta se mostrarán en la pestaña Confirmado. Si es necesario, un usuario con permisos para administrar temas puede revisar los temas confirmados y elegir rechazarlos.

Para revisar un tema confirmado:

1. En la **pestaña Confirmado,** seleccione el tema para abrir la página del tema.</br>

2. En la página del tema, revise la página del tema y **seleccione Editar** si necesita realizar cambios en la página.

Tenga en cuenta que todavía puede optar por rechazar un tema confirmado. Para ello, vaya al tema seleccionado en la **pestaña** Confirmado y seleccione **la x** si desea rechazar el tema.

## <a name="published-topics"></a>Temas publicados
Los temas publicados se han editado para que la información específica siempre aparezca a quien encuentre la página. Aquí también se enumeran los temas creados manualmente.

   ![Administrar temas](../media/knowledge-management/manage-topics-new.png) </br>