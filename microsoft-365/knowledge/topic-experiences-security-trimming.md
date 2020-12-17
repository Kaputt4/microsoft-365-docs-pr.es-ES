---
title: El tema experimenta el recorte de seguridad (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Información general sobre cómo se usa la seguridad para ver temas.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699060"
---
# <a name="topic-experiences-security-trimming-preview"></a>El tema experimenta el recorte de seguridad (versión preliminar)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).

El tema experiencias de los usuarios no podrá ver información en los temas que los permisos de Office 365 existentes impiden que se vean. Todo lo que un usuario ve en una página de tema (por ejemplo, sitios de SharePoint, documentos, archivos) será la información que ya se permite ver. El tema experiencias no realiza cambios en los permisos existentes.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Por qué dos usuarios pueden tener diferentes vistas del mismo tema

Cuando se crea un tema mediante AI o curation manual, puede incluir una descripción del tema, nombres alternativos, personas asociadas con el tema, así como sitios, páginas y archivos relacionados con el tema. Cuando esta información se muestra en una página de tema, es posible que dos usuarios que estén viendo el mismo tema no vean la misma información.
  
Por ejemplo, cuando el usuario 1 ve la página del tema Neptune, esto es lo que pueden ver.

![Tema de Neptune para el usuario 1](../media/knowledge-management/user2-topic-view.png) </br> 

Sin embargo, cuando el usuario 2 mira la misma página del tema de Neptune, su vista difiere del usuario 1.  El usuario 2 puede ver el archivo de *información general del producto DG-2000* en la sección **archivos y páginas ancladas** de la página del tema, que no aparece para el usuario 1. 

![Tema de Neptune para el usuario 2](../media/knowledge-management/user1-topic-view.png) </br> 

La diferencia en lo que los usuarios pueden ver en el mismo tema es porque es posible que los usuarios no dispongan de los permisos de Office 365 para ver un archivo o sitio relacionado.  El tema experiencias respeta los permisos que se establecen en los elementos de un tema y no puede cambiar el acceso a ellos. En nuestro ejemplo, el usuario 1 no puede ver el archivo de *información general del producto DG-2000* en su página del tema para Neptune porque el usuario 1 no tiene permisos de Office 365 para ver el archivo.

Si un usuario no puede ver suficiente información en un tema para que resulte útil, el tema no estará disponible para el usuario. En este caso, el usuario no verá el tema resaltado. Sin embargo, un usuario distinto que tenga permisos para obtener más información en el tema para que sea útil, podrá ver el tema.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Tema permisos para administradores del conocimiento y colaboradores del tema

Usuarios a los que se les han asignado permisos para administrar temas: administradores de conocimiento: solo podrán ver la información que tienen permisos para ver en los temas.

De forma similar, los usuarios que tienen permisos para crear y editar temas: colaboradores de tema solo podrán ver la información que tienen permisos para ver en los temas. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI frente a información del tema de creados manual

Los temas pueden contener información generada por AI e información agregada o modificada por los colaboradores de temas o los administradores de conocimientos.

 - La información de un tema agregado por AI solo es visible para los usuarios que tienen acceso al contenido de origen.
 - La información que se ha agregado o editado manualmente por un colaborador de temas o por el administrador de conocimiento es visible para todos los usuarios que puedan ver el tema.

En la tabla siguiente, se describen los visores de temas, los colaboradores y los administradores del conocimiento que pueden ver en un tema determinado en función de sus permisos.

|Elemento de tema|Qué pueden ver los usuarios|
|:---------|:------------------|
|Nombre del tema|Los usuarios pueden ver el nombre de tema de todos los temas del centro de temas. Es posible que algunos temas no estén visibles si tienen una importancia baja para el usuario.|
|Descripción del tema|Las descripciones generadas por AI solo son visibles para los usuarios que tienen permisos en el contenido de origen. Las descripciones especificadas o editadas manualmente son visibles para todos los usuarios.|
|Personas|Las personas ancladas son visibles para todos los usuarios. Los usuarios sugeridos solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Archivos|Los archivos solo están visibles para los usuarios que tienen permisos para el contenido de origen.|
|Páginas|Las páginas solo están visibles para los usuarios que tienen permisos para el contenido de origen.|
|Sitios|Los sitios solo están visibles para los usuarios que tienen permisos para el contenido de origen.|




## <a name="see-also"></a>Consulte también

