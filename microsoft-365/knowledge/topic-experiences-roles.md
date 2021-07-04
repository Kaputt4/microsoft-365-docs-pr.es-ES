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
ms.openlocfilehash: 9f1d3667ee9eeb05201613c15dc360b2b006cecb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288076"
---
# <a name="microsoft-viva-topics-roles"></a>Roles de los temas de Microsoft Viva 

Al usar Temas de Viva en el Microsoft 365, los usuarios pueden tener los siguientes roles:

- Lector de temas
- Colaborador de tema
- Responsable de la información
- Administrador de la información

## <a name="topic-viewer"></a>Lector de temas

Los visores de temas son usuarios de la organización que pueden ver los temas resaltados en su sitio moderno de SharePoint, Búsqueda de Microsoft SharePoint y Office.com y el centro de temas. Pueden ver más detalles sobre un tema en la página del tema. 

Para que los momentos de temas y las páginas de temas sean visibles para un lector de temas, el usuario debe:

- [Su administrador le asignará](./set-up-topic-experiences.md#assign-licenses) una licencia Microsoft 365 de Viva Topics.
- Tener permitida la visibilidad sobre los temas. El administrador de conocimientos realiza esta tarea en la página de configuración de Temas de Viva de la Centro de administración de Microsoft 365.

## <a name="topic-contributors"></a>Colaboradores del tema

Los colaboradores de temas son usuarios de la organización que no solo tienen permisos de lector de temas, sino que también pueden editar un tema existente o crear otro tema. Tienen un rol importante en la "curación" manual de la información de una página de tema (tanto AI como proporcionada manualmente) para garantizar su calidad.

Los usuarios con permisos de  colaborador de temas verán un botón Editar que se muestra en las páginas de temas, lo que les permite realizar actualizaciones y publicar un tema.

Un colaborador de tema también puede crear y publicar un nuevo tema a través de su centro de temas.

Para crear y editar un tema, el usuario debe:

- [Su administrador le asignará](./set-up-topic-experiences.md#assign-licenses) una licencia Microsoft 365 de Viva Topics.
- [Tener asignados permisos para crear y editar temas](./topic-experiences-user-permissions.md). El administrador de conocimientos realiza esta tarea en la página de configuración de Temas de Viva de la Centro de administración de Microsoft 365.

## <a name="knowledge-managers"></a>Responsables de la información

Los responsables de la información son usuarios que administran los temas en su organización.  La administración de temas se realiza a través de la página Administrar temas del centro de temas y solo es visible para los responsables de la información.

En la página Administrar temas, los responsables de la información pueden realizar las siguientes tareas:

- Ver temas sugeridos por IA.
- Revise los temas para confirmar que son válidos.
- Quite los temas que no desee que sean visibles para los usuarios.

Además, un responsable de la información puede editar temas existentes o crear otros nuevos.

Para administrar temas, el usuario debe:

- [Su administrador le asignará](./set-up-topic-experiences.md#assign-licenses) una licencia Microsoft 365 de Viva Topics.
- [Tener asignados permisos para administrar temas](./topic-experiences-user-permissions.md)). El administrador de conocimientos realiza esta tarea en la página de configuración de Temas de Viva de la Centro de administración de Microsoft 365.

Los usuarios que tienen un buen conocimiento general de su empresa pueden ser buenos candidatos para el rol de administrador de conocimientos. Es posible que estas personas no solo tengan conocimientos para saber si los temas son válidos o no, sino que también pueden conocer a personas dentro de la empresa relacionadas con esos temas.

## <a name="knowledge-admins"></a>Administradores de información

Los administradores de conocimientos son administradores que configuran y configuran Viva Topics en su Microsoft 365 de administración. También administran la configuración de Viva Topics una vez completada la configuración. El rol de administrador del conocimiento requiere que sea un administrador Microsoft 365 global o SharePoint, ya que la configuración y la administración se realizan en el Centro de administración de Microsoft 365.
Durante la instalación, los administradores de conocimientos pueden configurar Los temas de Viva para:

- Seleccionar los sitios de SharePoint que se rastrearán para temas.
- Seleccionar los usuarios con licencia que pueden ver temas (lectores de temas).
- Seleccionar los temas que se excluirán de la identificación.
- Seleccionar los usuarios con licencia que pueden crear y editar temas (colaboradores de temas).
- Seleccionar los usuarios con licencia que pueden administrar temas (responsables de la información).
- Asigne un nombre al centro de temas.

Los responsables de la información necesitan ser capaces de coordinarse con todas las partes interesadas de Temas Viva en su organización para saber cómo configurarla. Por ejemplo, si un nuevo proyecto tiene información confidencial, el administrador de conocimientos debe estar informado para que pueda asegurarse de que el sitio de SharePoint no se rastree para los temas o que se deben excluir nombres de temas específicos.
