---
title: Restringir el acceso a los temas
description: Cómo excluir temas para evitar que se detecten.
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
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699066"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a>Restringir el acceso a temas en experiencias de temas

En las experiencias de los temas, es posible que las partes interesadas de la organización deseen asegurarse de que no se detecten temas específicos y que se expongan a los usuarios con licencia. Por ejemplo, puede estar trabajando en un proyecto en el que no desea exponer información todavía. Aunque los permisos de Office 365 en sitios, archivos y otros recursos impiden que los usuarios vean información confidencial en los temas, existen protecciones adicionales para evitar que se detecten temas específicos.

Mientras que los administradores de conocimientos controlan la configuración de la red de conocimiento para evitar que se detecten temas, los administradores de conocimiento y otras partes interesadas deben saber cómo se realiza esta tarea para que puedan trabajar en colaboración.

> [!Important] 
> En este artículo se describen formas de evitar que los temas se identifiquen a través de AI o que se vean en el entorno como protección de seguridad adicional. Es importante tener en cuenta que en las experiencias de los temas, los usuarios no tienen permiso para ver nada en un tema que no tienen permiso de acceso a través de los permisos de Office 365. Incluso si un usuario puede ver un tema, los archivos, los sitios y las páginas que no tienen permisos de Office 365 para ver no serán visibles para los usuarios. Asegurarse de que los permisos para los archivos confidenciales se establezcan correctamente debe ser la protección de seguridad principal.

## <a name="prevent-topics-from-being-identified"></a>Impedir la identificación de los temas

El administrador de conocimiento puede restringir el acceso a temas específicos evitando que se encuentren en la indización inicial. Hay dos formas de hacerlo en la configuración de administración de la red de conocimientos en el centro de administración de Microsoft 365.
 
- [Seleccione sitios de SharePoint para excluirlos del descubrimiento de](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)temas: puede usar esta opción para evitar que se rastreen sitios específicos de SharePoint en busca de temas.
- [Excluir temas por nombre](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): los administradores pueden usar esta configuración para evitar que se detecten temas específicos por nombre. En la configuración de administración de la red de conocimiento, un administrador puede cargar una lista de temas que se excluirán en un archivo CSV. Puede excluir los temas que contengan coincidencias exactas o parciales de un nombre de tema.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Impedir que determinados usuarios vean los temas

Los administradores del conocimiento también pueden [seleccionar quién puede ver los temas de la organización](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules). Esta opción le permite seleccionar qué usuarios con licencia pueden ver todos los temas. Por ejemplo, en un entorno piloto, es posible que quiera permitir que un pequeño grupo de usuarios pueda ver temas.

## <a name="remove-topics-from-being-viewed"></a>Quitar temas que se van a ver

Los administradores de conocimiento pueden elegir [quitar temas](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) para que los usuarios ya no puedan verlos. En la página **administrar temas** del **Centro** de temas, los administradores de conocimiento pueden rechazar temas específicos para evitar que se vean. Los temas se pueden quitar independientemente de si están en un estado sugerido o confirmado.

Los temas eliminados se pueden volver a agregar posteriormente como temas visibles si es necesario. 


## <a name="see-also"></a>Consulte también



  






