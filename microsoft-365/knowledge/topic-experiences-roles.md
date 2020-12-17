---
title: Tema experiencias de temas (versión preliminar)
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
description: Obtenga información sobre las funciones de usuario en experiencias de temas.
ms.openlocfilehash: ed4d40aa7bb91a85e28aba7ace99edf580c427a5
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699024"
---
# <a name="topic-experiences-roles-preview"></a>Tema experiencias de temas (versión preliminar)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).


Al usar las experiencias de los temas en el entorno de Microsoft 365, los usuarios pueden tener las siguientes funciones:
-   Visor de temas
-   Colaborador de temas
-   Administrador de conocimiento
-   Administrador de conocimiento

## <a name="topic-viewer"></a>Visor de temas

Los visores de temas son usuarios de la organización que pueden ver temas resaltados en su sitio moderno de SharePoint y en la búsqueda de SharePoint. Pueden seleccionar temas resaltados para ver más detalles en acerca de ellos en una página del tema. 

En el caso de los elementos destacados del tema y sus páginas de temas visibles para un visor de temas, el usuario debe:
-   [Se le asigna un tema licencia de experiencias](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) por parte del administrador de Microsoft 365.
-   Tener permiso de visibilidad en los temas. Esto se realiza mediante el administrador de la información en la página de configuración de experiencias del tema del centro de administración de Microsoft 365.


## <a name="topic-contributors"></a>Colaboradores de temas

Los colaboradores de temas son usuarios de la organización que no solo tienen permisos de visor de temas, sino que también pueden editar un tema existente o crear un tema nuevo. Tienen un papel importante en la "Curating" manual de la información de una página de temas (tanto AI como proporcionado manualmente) para garantizar su calidad.

Los usuarios que tengan los permisos de colaborador de temas verán un botón **Editar** que se muestra en las páginas del tema, lo que les permite realizar actualizaciones y publicar un tema.

Un colaborador de temas también puede crear y publicar un nuevo tema a través del sitio del centro de temas.

Para poder crear y editar un tema, el usuario debe:

-   [Se le asigna un tema licencia de experiencias](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) por parte del administrador de Microsoft 365.
-   [Tener asignados permisos para crear y editar temas](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center). Esto se realiza mediante el administrador de la información en la página de configuración de experiencias del tema del centro de administración de Microsoft 365.

## <a name="knowledge-managers"></a>Administradores de conocimiento

Los administradores de conocimiento son usuarios que administran temas en su organización.  La administración de temas se lleva a cabo a través de la página Administrar temas del centro de temas y solo es visible para los administradores de conocimiento.

En la página Administrar temas, los administradores del conocimiento pueden realizar las siguientes tareas:
-   Ver todos los temas de AI: sugerencias.
-   Revise los temas para confirmar que son válidos.
-   Quite los temas que no quiera que sean visibles para los usuarios.


Además, un administrador de información puede editar temas existentes o crear otros nuevos.

Para poder administrar temas, el usuario debe:
-   [Se le asigna un tema licencia de experiencias](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) por parte del administrador de Microsoft 365.
-   [Tener asignados permisos para administrar temas](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center)). Esto se realiza mediante el administrador de la información en la página de configuración de experiencias del tema del centro de administración de Microsoft 365.

Los usuarios que tienen un buen conocimiento general de su empresa pueden ser buenos candidatos para la función de administrador de conocimiento. Es posible que estas personas no solo tengan el conocimiento de saber si los temas son válidos o no, pero también podrían conocer a los usuarios de la compañía que están relacionados con esos temas.


## <a name="knowledge-admins"></a>Administradores de conocimiento

Los administradores del conocimiento son administradores que configuran y configuran experiencias de temas en su entorno de Microsoft 365. También administran la configuración de las experiencias de los temas después de que haya finalizado la configuración. El rol de administrador de conocimiento requiere que se le concentre en un administrador global o de SharePoint de Microsoft 365, ya que la configuración y la administración se realizan en el centro de administración de Microsoft 365.
Durante la instalación, los administradores de conocimiento pueden configurar las experiencias de los temas para hacer lo siguiente:

-   Seleccione los sitios de SharePoint que se rastrearán en busca de temas.
-   Seleccione qué usuarios con licencia podrán ver temas (visores de temas).
-   Seleccione los temas que se excluirán de la identificación.
-   Seleccione qué usuarios con licencia podrán crear y editar temas (colaboradores de temas).
-   Seleccione los usuarios con licencia que podrán administrar los temas (administradores de conocimiento).
-   Asigne un nombre al centro de temas.

Los administradores de la información deben poder coordinarse con todos los temas de las partes interesadas de su organización para saber cómo configurarlo. Por ejemplo, si un proyecto nuevo tiene información confidencial, el administrador de información debe estar informado para que pueda asegurarse de que el sitio de SharePoint no está rastreando los temas o que se deben excluir los nombres de temas específicos.


## <a name="see-also"></a>Consulte también

