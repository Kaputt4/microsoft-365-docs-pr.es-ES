---
title: 'Administrar temas en el centro de temas de experiencias de temas (vista previa) '
description: Cómo administrar temas en el centro de temas.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 832067d157ed9ffcba1ed9ad514c375cbbdd752b
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699030"
---
# <a name="manage-topics-in-the-topic-center-preview"></a>Administrar temas en el centro de temas (versión preliminar)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).

En el centro de temas, un administrador de información puede ver la página **administrar temas** para revisar los temas que se han identificado en ubicaciones de origen de SharePoint según lo especificado por su administrador de conocimientos.  

   ![Centro de temas](../media/knowledge-management/topic-center.png) </br> 



Los administradores de conocimientos ayudan a guiar los temas detectados a través del ciclo de vida del tema en el que los temas son:

- Sugerido: un tema ha sido identificado por AI y tiene suficientes recursos, conexiones y propiedades auxiliares para cumplir el umbral del tema.
- Confirmado: se valida un tema sugerido por AI. La validación se realiza mediante la confirmación de un administrador de conocimiento. Además, se puede confirmar un tema si al menos dos usuarios proporcionan comentarios positivos a través de comentarios de temas que el tema es válido.
- Quitado: un administrador de conocimiento ha rechazado un tema y ya no será visible para los visores. El tema puede estar en cualquier estado cuando se quita (se sugiere o confirma). 
- Publicado: un tema confirmado que se ha actualizado manualmente.

   ![Gráfico de ciclo de vida del tema](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a>Requisitos

Para administrar temas en el centro de temas, debe:
- Tener un tema de licencia de experiencia.
- Tiene permisos para los [**usuarios que pueden administrar temas**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions). Los administradores de conocimiento pueden conceder a los usuarios este permiso en la configuración de permisos de temas de red de conocimientos. 

No podrá ver la página Administrar temas en el centro de temas a menos que tenga el permiso **quién puede administrar temas** .

En el centro de temas, un administrador de información puede revisar los temas que se han identificado en las ubicaciones de origen de SharePoint especificadas y puede confirmarlos o rechazarlos. Un administrador de información también puede crear y publicar nuevas páginas de temas si no se encuentra ninguna en la detección de temas, o editar las existentes si es necesario actualizarlas.


## <a name="review-suggested-topics"></a>Revisión de temas sugeridos

En la página centro de temas de administración de temas, los temas que se detectaron en las ubicaciones de origen de SharePoint especificadas se enumerarán en la pestaña **sugerido** . Un administrador de información puede revisar los temas no confirmados y elegir confirmarlos o rechazarlos.

Para revisar un tema sugerido:

1. En la página **administrar temas** , seleccione la pestaña **sugerido** , seleccione el tema para abrir la página del tema.</br>

2. En la página del tema, revise la página del tema y seleccione **Editar** si necesita realizar cambios en la página.

3. Después de revisar el tema, vuelva a la página Administrar temas. Para el tema seleccionado, puede:

   - Seleccione la marca de verificación para confirmar el tema.
    
   - Seleccione la **x** si desea rechazar el tema.

    Los temas confirmados se quitarán de la lista de **sugerencias** y ahora se mostrarán en la lista **confirmada** .

    Los temas rechazados se quitarán de la lista **sugerida** y ahora se mostrarán en la pestaña **eliminado** .

   </br> 

## <a name="confirmed-topics"></a>Temas confirmados

En la página Administrar temas, los temas que se detectaron en las ubicaciones de origen de SharePoint especificadas y que han sido confirmados por un administrador de conocimiento o "multitud de multitudes" confirmados por dos o más personas a través del mecanismo de comentarios de tarjetas se enumerarán en la pestaña **confirmada** . Si es necesario, un usuario con permisos para administrar temas puede revisar los temas confirmados y elegir rechazarlos.

Para revisar un tema confirmado:

1. En la pestaña **confirmada** , seleccione el tema para abrir la página del tema.</br>

2. En la página del tema, revise la página del tema y seleccione **Editar** si necesita realizar cambios en la página.

Tenga en cuenta que todavía puede rechazar un tema confirmado.  Para ello, vaya al tema seleccionado en la lista confirmada y seleccione la **x** si desea rechazar el tema.

## <a name="published-topics"></a>Temas publicados
Se han editado los temas publicados para que la información específica aparezca siempre a quien encuentre la página. Aquí se muestran los temas creados manualmente.




