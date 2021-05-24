---
title: Administrar temas en el centro de temas en Temas de Microsoft Viva
description: Cómo administrar temas en el centro de temas.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: ba8f27c90f9c84729a10f461e85b2e1441b49549
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625406"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a>Administrar temas en el centro de temas en Temas de Microsoft Viva

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

En el Centro de temas de Viva  Topics, un administrador de conocimientos puede ver la página Administrar temas para revisar los temas que se han identificado en las ubicaciones de origen según lo especificado por el administrador de conocimientos.  

   ![Centro de temas](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a>Fases del tema

Los administradores de conocimientos ayudan a guiar los temas detectados a través de las distintas fases del ciclo de vida del tema: **Sugerido** **,** **Confirmado**, Publicado y **Eliminado.**

   ![Gráfico de ciclo de vida de temas](../media/knowledge-management/topic-lifecycle.png) 

- **Sugerido**: se ha identificado un tema en AI y tiene suficientes recursos compatibles, conexiones y propiedades. (Se marcan como **un tema sugerido** en la interfaz de usuario).

- **Confirmado:** un tema que ha sido detectado por AI y que se ha validado. La validación del tema se produce cuando:

   - Un administrador de conocimientos confirma un tema. Un administrador de [conocimientos confirma un tema en](manage-topics.md#confirmed-topics) la página Administrar **temas.**

   - Varios usuarios confirman un tema. Debe haber una red de dos votos positivos recibidos de usuarios que votaron mediante el mecanismo de comentarios en la tarjeta de tema. Por ejemplo, si un usuario votó positivo y un usuario votó negativo para un tema en particular, aún necesitará dos votos positivos más para confirmar el tema.
 
- **Publicado:** tema que se ha seleccionado. Se han realizado modificaciones manuales para mejorar su calidad o ha sido creada por un usuario.

- **Eliminado:** un tema que se ha rechazado y que ya no será visible para los visores. Un tema se puede quitar en cualquier estado (sugerido, confirmado o publicado). La eliminación del tema se produce cuando:

   - Un administrador de conocimientos quita un tema. Un administrador de conocimientos quita un tema de la **página Administrar temas.**

   - Varios usuarios emitirán votos negativos mediante el mecanismo de comentarios en la tarjeta de tema. Para que se quite un tema, debe haber una red de dos votos negativos recibidos de los usuarios. Por ejemplo, si un usuario votó negativo y un usuario votó positivo para un tema en particular, aún necesitará dos votos negativos más para que se elimine el tema.

  Cuando se quita un tema publicado, la página con los detalles seleccionados tendrá que eliminarse manualmente a través de la Biblioteca de páginas del centro de temas.

> [!Note] 
> En la página Administrar **temas,** cada administrador de conocimientos solo podrá ver temas en los que tengan acceso a los archivos y páginas subyacentes conectados al tema. Este recorte de permisos se reflejará en la lista de temas que aparecen en las pestañas **Sugerido,** **Confirmado,** Publicado **y** Eliminado. Sin embargo, los recuentos de temas muestran los recuentos totales de la organización independientemente de los permisos.

## <a name="requirements"></a>Requirements

Para administrar temas en el centro de temas, debe:
- Tener una licencia de Temas Microsoft Viva.

- Tenga el [**Quién puede administrar permisos de temas.**](./topic-experiences-user-permissions.md) Los administradores del conocimientos pueden conceder a los usuarios este permiso en la configuración de permisos del tema de Temas Viva. 

No podrá ver la  página Administrar temas en el centro de temas a menos que tenga el permiso **Quién administrar temas.**

En el centro de temas, un administrador de conocimientos puede revisar los temas que se han identificado en las ubicaciones de origen especificadas y puede confirmarlos o quitarlos. Un administrador de conocimientos también puede crear y publicar nuevas páginas de temas si no se encontró una en la detección de temas o editar las existentes si es necesario actualizarlas.

## <a name="review-suggested-topics"></a>Revisar temas sugeridos

En la **página Administrar temas,** los temas que se detectaron en las ubicaciones SharePoint de origen especificadas se mostrarán en la **pestaña Sugerencias.** Si es necesario, un administrador de conocimientos puede revisar temas no confirmados y elegir confirmarlos o quitarlos.

   ![Temas sugeridos](../media/knowledge-management/quality-score.png) 

Para revisar un tema sugerido:

1. En la **página Administrar temas,** seleccione la **pestaña Sugerencia** y, a continuación, seleccione el tema para abrir la página del tema.

2. En la página del tema, revise la página del tema y **seleccione Editar** si necesita realizar cambios en la página. La publicación de cualquier modificación moverá este tema a la **pestaña Publicado.**

3. Después de revisar el tema, vuelva a la **página Administrar temas.** Para el tema seleccionado, puede:

   - Seleccionar la marca de verificación para confirmar el tema.
    
   - Seleccione la **x** si desea quitar el tema.

    Los temas confirmados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **lista** Confirmados.

    Los temas eliminados se quitarán de la **lista Sugeridos** y ahora se mostrarán en la **pestaña** Eliminado.

### <a name="quality-score"></a>Puntuación de calidad

Cada tema que aparece en la **página Temas** sugeridos tiene asignada una puntuación de calidad. La puntuación de calidad es un reflejo de la cantidad de información que el usuario promedio verá para la información sobre el tema, teniendo en cuenta que cada usuario puede ver más o menos información debido a los permisos que podrían o no tener en la información de un tema. 

La puntuación de calidad puede ayudar a proporcionar información sobre los temas con más información y puede ser útil para encontrar temas que pueden necesitar editarse manualmente. Por ejemplo, un tema con una puntuación de calidad inferior puede ser el resultado de que algunos usuarios no tengan permisos SharePoint los archivos o sitios pertinentes que AI ha incluido en el tema. A continuación, un colaborador podría editar el tema para incluir la información (cuando sea necesaria), lo que estará visible para todos los usuarios que puedan verlo.

### <a name="impressions"></a>Impresiones

La **columna Impresiones** muestra el número de veces que se ha mostrado un tema a los usuarios finales. Esto incluye vistas a través de las tarjetas de respuesta del tema en la búsqueda y a través de los aspectos destacados del tema. No refleja el clic en estos temas, sino que se ha mostrado el tema. La **columna Impresiones se** mostrará para los temas de  las pestañas **Sugeridos,**  **Confirmados,** Publicados y Eliminados de la página Administrar **temas.**

## <a name="confirmed-topics"></a>Temas confirmados

En  la página Administrar temas, los temas detectados en las ubicaciones de origen de SharePoint especificadas y confirmados por un administrador de conocimientos o "crowdsourced" confirmados por una  red de dos o más personas (equilibrando los votos negativos del usuario con los votos positivos de los usuarios) a través del mecanismo de comentarios de tarjeta se mostrarán en la pestaña Confirmado. Si es necesario, un usuario con permisos para administrar temas puede revisar los temas confirmados y elegir rechazarlos.

Para revisar un tema confirmado:

1. En la pestaña **Confirmado**, seleccione el tema para abrir la página de tema.

2. En la página del tema, revise la página del tema y **seleccione Editar** si necesita realizar cambios en la página.

Tenga en cuenta que todavía puede optar por rechazar un tema confirmado. Para ello, vaya al tema seleccionado en la **pestaña** Confirmado y seleccione **la x** si desea rechazar el tema.

## <a name="published-topics"></a>Temas publicados

Los temas publicados se han editado para que la información específica siempre aparezca a quien encuentre la página. Aquí también se muestran los temas creados manualmente.

   ![Administrar temas](../media/knowledge-management/manage-topics-new.png)
