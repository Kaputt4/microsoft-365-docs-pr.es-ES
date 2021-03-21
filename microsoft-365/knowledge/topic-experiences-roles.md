---
title: Roles de los temas de Microsoft Viva
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Obtenga información sobre los roles de usuario en Temas de Viva.
ms.openlocfilehash: 6d93046a96b60779c3cd3bd6c6aa600cb443118f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917361"
---
# <a name="microsoft-viva-topics-roles"></a>Roles de los temas de Microsoft Viva 

Al usar Temas de Viva en el entorno de Microsoft 365, los usuarios pueden tener los siguientes roles:
-   Visor de temas
-   Colaborador de temas
-   Administrador de conocimientos
-   Administrador de conocimientos

## <a name="topic-viewer"></a>Visor de temas

Los visores de temas son usuarios de su organización que pueden ver los temas resaltados en su sitio moderno de SharePoint, Microsoft Search a través de SharePoint y Office.com y el centro de temas. Pueden ver más detalles sobre un tema en la página del tema. 

Para que los resaltados de temas y sus páginas de temas sean visibles para un visor de temas, el usuario debe:
-   [Su administrador de Microsoft](./set-up-topic-experiences.md#assign-licenses) 365 le asignará una licencia de Viva Topics.
-   Tenga permiso para tener visibilidad de los temas. Esta tarea la realiza el administrador de conocimientos en la página de configuración de Temas de Viva en el Centro de administración de Microsoft 365.


## <a name="topic-contributors"></a>Colaboradores de temas

Los colaboradores de temas son usuarios de la organización que no solo tienen permisos de visor de temas, sino que también pueden editar un tema existente o crear un tema nuevo. Tienen un rol importante en la "curación" manual de la información de una página de tema (tanto AI como proporcionada manualmente) para garantizar su calidad.

Los usuarios con permisos de  colaborador de temas verán un botón Editar que se muestra en las páginas de temas, lo que les permite realizar actualizaciones y publicar un tema.

Un colaborador de temas también puede crear y publicar un nuevo tema a través de su centro de temas.

Para crear y editar un tema, el usuario debe:

-   [Su administrador de Microsoft](./set-up-topic-experiences.md#assign-licenses) 365 le asignará una licencia de Viva Topics.
-   [Tener asignados permisos para crear y editar temas](./topic-experiences-user-permissions.md#change-who-has-permissions-to-do-tasks-on-the-topic-center). Esta tarea la realiza el administrador de conocimientos en la página de configuración de Temas de Viva en el Centro de administración de Microsoft 365.

## <a name="knowledge-managers"></a>Administradores de conocimientos

Los administradores de conocimientos son usuarios que administran temas de su organización.  La administración de temas se realiza a través de la página Administrar temas del centro de temas y solo es visible para los administradores de conocimientos.

En la página Administrar temas, los administradores de conocimientos pueden realizar las siguientes tareas:
-   Ver temas sugeridos por IA.
-   Revise los temas para confirmar que son válidos.
-   Quite los temas que no desee que sean visibles para los usuarios.

Además, un administrador de conocimientos puede editar temas existentes o crear otros nuevos.

Para administrar temas, el usuario debe:
-   [Su administrador de Microsoft](./set-up-topic-experiences.md#assign-licenses) 365 le asignará una licencia de Viva Topics.
-   [Tener asignados permisos para administrar temas](./topic-experiences-user-permissions.md#change-who-has-permissions-to-do-tasks-on-the-topic-center)). Esta tarea la realiza el administrador de conocimientos en la página de configuración de Temas de Viva en el Centro de administración de Microsoft 365.

Los usuarios que tienen un buen conocimiento general de su empresa pueden ser buenos candidatos para el rol de administrador de conocimientos. Es posible que estas personas no solo tengan conocimientos para saber si los temas son válidos o no, sino que también pueden conocer a personas dentro de la empresa relacionadas con esos temas.


## <a name="knowledge-admins"></a>Administradores de conocimientos

Los administradores de conocimientos son administradores que configuran y configuran Viva Topics en su entorno de Microsoft 365. También administran la configuración de Viva Topics una vez completada la configuración. El rol de administrador de conocimientos requiere que sea un administrador global o de SharePoint de Microsoft 365, ya que la configuración y la administración se realizan en el Centro de administración de Microsoft 365.
Durante la instalación, los administradores de conocimientos pueden configurar Los temas de Viva para:

-   Seleccione los sitios de SharePoint que se rastrearán para los temas.
-   Seleccione los usuarios con licencia que pueden ver temas (visores de temas).
-   Seleccione los temas que se excluirán de la identificación.
-   Seleccione qué usuarios con licencia pueden crear y editar temas (colaboradores de temas).
-   Seleccione los usuarios con licencia que pueden administrar temas (administradores de conocimientos).
-   Asigne un nombre al centro de temas.

Los administradores de conocimientos deben poder coordinarse con todas las partes interesadas de Viva Topics en su organización para saber cómo configurarlo. Por ejemplo, si un nuevo proyecto tiene información confidencial, el administrador de conocimientos debe estar informado para que pueda asegurarse de que el sitio de SharePoint no se rastree para los temas o que se deben excluir nombres de temas específicos.


## <a name="see-also"></a>Consulte también