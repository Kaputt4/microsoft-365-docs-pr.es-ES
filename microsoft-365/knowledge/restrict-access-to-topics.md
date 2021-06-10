---
title: Restringir el acceso a los temas de Temas de Microsoft Viva
description: Cómo excluir temas para evitar que se descubran.
author: efrene
ms.author: efrene
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
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500880"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Restringir el acceso a los temas de Temas de Microsoft Viva

En Microsoft Viva, es posible que las partes interesadas de la organización quieran asegurarse de que los temas específicos no se descubran y se exponan a los usuarios con licencia. Por ejemplo, es posible que esté trabajando en un proyecto sobre el que aún no desea exponer ninguna información. Aunque Office 365 permisos en sitios, archivos y otros recursos impedirán que los usuarios de Experiencias de tema puedan ver información confidencial en los temas, existen medidas de seguridad adicionales para evitar que se descubran temas específicos.

Aunque los administradores de conocimientos controlan la configuración para evitar que se descubran los temas, los administradores de conocimientos y otras partes interesadas necesitan saber cómo se hace para que puedan trabajar en colaboración.

> [!Important] 
> En este artículo se describen maneras de evitar que los temas se identifiquen a través de la IA o se visualizó en su entorno como una protección de seguridad adicional. Es importante tener en cuenta que, en Temas de Viva, los usuarios no pueden ver nada en un tema al que no se les permite acceder a través de Office 365 permisos. Incluso si un usuario es capaz de ver un tema, sus archivos, sitios y páginas que no tienen Office 365 permisos para ver no serán visibles para ellos. Asegurarse de que los permisos de los archivos confidenciales están configurados correctamente debe ser la protección de seguridad principal.

## <a name="prevent-topics-from-being-identified"></a>Impedir que los temas se identifiquen

El administrador de conocimientos puede restringir el acceso a temas específicos impidiendo que se puedan encontrar en la indización inicial. Hay dos maneras de realizar esta tarea en la configuración de administración de Temas de Viva en el centro Microsoft 365 administración.
 
- [Seleccione SharePoint sitios para excluir](./topic-experiences-discovery.md#select-sharepoint-topic-sources)de la detección de temas: puede usar esta configuración para evitar que sitios de SharePoint específicos se rastreen para los temas.
- [Excluir temas por nombre:](./topic-experiences-discovery.md#exclude-topics-by-name)los administradores pueden usar esta configuración para evitar que determinados temas se descubran por su nombre. En la configuración de administración de Temas de Viva, un administrador puede cargar una lista de temas que se excluirán en un archivo CSV. Puede excluir temas que tengan coincidencias exactas o parciales de un nombre de tema.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Impedir que los usuarios específicos puedan ver temas

Los administradores de conocimientos también [pueden seleccionar quién puede ver los temas de su organización.](./topic-experiences-knowledge-rules.md) Esta configuración le permite seleccionar qué usuarios con licencia pueden ver todos los temas. Por ejemplo, en un entorno piloto, es posible que solo desee permitir que un pequeño grupo de usuarios pueda ver temas.

## <a name="remove-topics-from-being-viewed"></a>Quitar temas de visualización

Los administradores de conocimientos pueden [elegir quitar temas](./manage-topics.md) para que los usuarios ya no puedan verlos. En la **página Administrar temas** del Centro de temas, los administradores de conocimientos pueden optar por rechazar temas específicos para evitar que se puedan ver.  Los temas se pueden quitar independientemente de si están en un estado sugerido o confirmado.

Los temas eliminados se pueden agregar más adelante como temas que se pueden ver si es necesario. 


## <a name="see-also"></a>Consulte también



