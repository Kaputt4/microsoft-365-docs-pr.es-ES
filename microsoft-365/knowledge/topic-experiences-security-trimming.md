---
title: Recorte de seguridad de Microsoft Viva Topics
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Información general sobre cómo se usa la seguridad para ver temas.
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939628"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Recorte de seguridad de Microsoft Viva Topics 

Los usuarios de Viva Topics no pueden ver información en temas que sus permisos de Office 365 existentes les impiden ver. Todo lo que un usuario vea en una página de tema (por ejemplo, sitios de SharePoint, documentos o archivos) será información para la cual ya esté autorizado. Temas Viva no realiza cambios en los permisos existentes.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Por qué dos usuarios pueden tener diferentes vistas del mismo tema

Cuando se crea un tema a través de IA o selección manual, puede contener una descripción, nombres alternativos, personas asociadas con el tema, así como sitios, páginas y archivos relacionados. Cuando esta información se ve en una página de tema, es posible que dos usuarios que están viendo el mismo tema no vean la misma información.
  
Por ejemplo, cuando el Usuario 1 ve la página de tema de Neptuno, es posible que tenga esta vista de la página de tema.

![Tema Neptuno para el usuario 1](../media/knowledge-management/user2-topic-view.png) </br> 

Sin embargo, cuando el usuario 2 mira la misma página de tema de Neptuno, su vista difiere del usuario 1.  El usuario 2 puede ver el archivo *DG-2000 Product Overview* en la sección Archivos anclados y páginas de la página del tema, que no aparece para el usuario 1.  

![Tema de Neptuno para el usuario 2](../media/knowledge-management/user1-topic-view.png) </br> 

La diferencia en lo que los usuarios pueden ver en el mismo tema es porque es posible que los usuarios no tengan los permisos Office 365 para ver un sitio o archivo relacionado.  Viva Topics respeta los permisos que se establecen en los elementos de un tema y no puede cambiar el acceso a ellos. En nuestro ejemplo, el usuario 1 no puede ver el archivo *DG-2000 Product Overview* en su página de tema para Neptuno porque el usuario 1 no tiene Office 365 permisos para ver el archivo.

Si un usuario no puede ver suficiente información en un tema para que sea útil, el tema no estará disponible para el usuario. Cuando esto suceda, el usuario no verá el tema resaltado. Un usuario distinto que tenga los permisos para obtener información suficiente sobre el tema como para que le resulte útil, podrá ver el tema.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Permisos de temas para administradores de conocimientos y colaboradores de temas

Los usuarios a los que se les asignan permisos para administrar temas (administradores de conocimientos) solo podrán ver la información que tienen permisos para ver en los temas.

Del mismo modo, los usuarios que tengan permisos de creación y edición de temas (colaboradores de temas) solo podrán ver la información que tienen permisos para ver en los temas. 


## <a name="ai-versus-manually-curated-topic-information"></a>Información sobre el tema de IA versus seleccionada manualmente

Los temas pueden contener información generada por la inteligencia artificial y la información agregada o editada por colaboradores de temas o administradores de conocimientos.

 - La información de un tema agregado por IA solo es visible para los usuarios que tienen acceso al contenido de origen.
 - La descripción del tema y la información de personas que ha agregado o editado manualmente un colaborador del tema o un administrador de conocimientos es visible para todos los usuarios que pueden ver el tema.
 - Los archivos, páginas y sitios solo son visibles para los usuarios que tienen permisos para el contenido de origen, ya sean agregados manualmente o agregados por AI.

En la tabla siguiente se describe lo que los usuarios (visores de temas, colaboradores y administradores de conocimientos) pueden ver en un tema determinado en función de sus permisos.

|Elemento de tema|Qué pueden ver los usuarios|
|:---------|:------------------|
|Nombre del tema|Los usuarios pueden ver el nombre del tema de los temas en el centro de temas. Es posible que algunos temas no sean visibles si los usuarios no tienen permisos para el contenido de origen o tienen una relevancia baja para el usuario.|
|Descripción del tema|Las descripciones generadas por IA solo son visibles para los usuarios que tienen permisos para el contenido de origen. Las descripciones especificadas o editadas manualmente son visibles para todos los usuarios.|
|Contactos|Los usuarios anclados son visibles para todos los usuarios. Los usuarios sugeridos solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Archivos|Los archivos solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Páginas|Las páginas solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Sitios|Los sitios solo son visibles para los usuarios que tienen permisos para el contenido de origen.|




## <a name="see-also"></a>Consulte también

