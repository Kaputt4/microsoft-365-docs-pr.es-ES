---
title: Restringir el acceso a los temas
description: Cómo excluir temas para evitar que se descubran.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: f7e8406ee7090387d4500f69955330466f28c6c0
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976150"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a>Restringir el acceso a los temas de experiencias de temas

En Experiencias de temas, es posible que las partes interesadas de su organización quieran asegurarse de que no se detectan temas específicos y se exponen a los usuarios con licencia. Por ejemplo, es posible que esté trabajando en un proyecto sobre el que aún no desea exponer información. Aunque los permisos de Office 365 en sitios, archivos y otros recursos impedirán que los usuarios de experiencias de tema puedan ver información confidencial en los temas, existen medidas de seguridad adicionales para evitar que se descubran temas específicos.

Aunque los administradores de conocimientos controlan la configuración de la red de conocimiento para evitar que se descubran temas, los administradores de conocimientos y otras partes interesadas deben saber cómo hacerlo para que puedan trabajar en colaboración en esto.

> [!Important] 
> En este artículo se describen formas de evitar que los temas se identifiquen a través de la inteligencia artificial o se visualmente en su entorno como una protección de seguridad adicional. Es importante tener en cuenta que en Experiencias de tema, los usuarios no pueden ver nada en un tema al que no tienen permiso de acceso a través de los permisos de Office 365. Incluso si un usuario puede ver un tema, sus archivos, sitios y páginas que no tienen permisos de Office 365 para ver no serán visibles para ellos. Asegurarse de que los permisos de los archivos confidenciales están correctamente establecidos debe ser la protección de seguridad principal.

## <a name="prevent-topics-from-being-identified"></a>Impedir que se identifiquen los temas

El administrador del conocimiento puede restringir el acceso a temas específicos impidiendo que se encuentran en la indización inicial. Hay dos formas de hacerlo en la configuración de administración de Knowledge Network en el Centro de administración de Microsoft 365.
 
- [Seleccione sitios de SharePoint para excluirlos](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)de la detección de temas: puede usar esta configuración para evitar que determinados sitios de SharePoint se rastreen en temas.
- [Excluir temas por nombre:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)los administradores pueden usar esta configuración para evitar que determinados temas se descubran por nombre. En la configuración de administración de Knowledge Network, un administrador puede cargar una lista de temas que se excluirán en un archivo CSV. Puede excluir los temas que tengan coincidencias exactas o parciales de un nombre de tema.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Impedir que usuarios específicos puedan ver los temas

Los administradores de conocimientos [también pueden seleccionar quién puede ver los temas de su organización.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules) Esta configuración le permite seleccionar qué usuarios con licencia pueden ver todos los temas. Por ejemplo, en un entorno piloto, es posible que solo desee permitir que un pequeño grupo de usuarios pueda ver temas.

## <a name="remove-topics-from-being-viewed"></a>Quitar temas de la visualización

Los administradores de conocimientos [pueden elegir quitar temas](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) para que los usuarios ya no puedan verlos. En la **página Administrar temas** del Centro de temas, los administradores de conocimientos pueden elegir rechazar temas específicos para evitar que se puedan ver.  Los temas se pueden quitar independientemente de si están en un estado sugerido o confirmado.

Los temas eliminados se pueden volver a agregar como temas visualizables si es necesario. 


## <a name="see-also"></a>Consulte también



  






