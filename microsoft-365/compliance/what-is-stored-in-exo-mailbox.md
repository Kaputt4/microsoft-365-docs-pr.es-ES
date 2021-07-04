---
title: Contenido almacenado en Exchange Online buzones de correo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
description: El contenido producido por aplicaciones basadas en la nube en Microsoft 365 se almacena o se asocia con el buzón de correo Exchange Online usuario. Este contenido se puede buscar con herramientas de exhibición de documentos electrónicos de Microsoft.
ms.openlocfilehash: 975f4ac8be8c2cdeed8dea1d73699607662a1ce9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288148"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>Contenido almacenado en Exchange Online buzones de correo para eDiscovery

Un buzón de Exchange Online se usa principalmente para almacenar elementos relacionados con el correo electrónico, como mensajes, elementos de calendario, tareas y notas. Pero eso está cambiando a medida que más aplicaciones basadas en la nube también almacenan sus datos en el buzón de un usuario. Una ventaja de almacenar datos en un buzón es que puede usar las herramientas de búsqueda en búsqueda de contenido, exhibición de documentos electrónicos principales y Advanced eDiscovery para buscar, ver y exportar los datos de estas aplicaciones basadas en la nube. Los datos de algunas de estas aplicaciones se almacenan en carpetas ocultas ubicadas en un subárbol de mensaje no interpersonal (que no es IPM) en el buzón. Es posible que los datos de  otras aplicaciones basadas  en la nube no se almacenen en el buzón, pero están asociados con el buzón y se devuelven en las búsquedas (si los datos coinciden con la consulta de búsqueda). Independientemente de si los datos basados en la nube se almacenan en o están asociados con un buzón de usuario, los datos normalmente no son visibles en un cliente de correo electrónico cuando un usuario abre su buzón.

En la tabla siguiente se enumeran las aplicaciones que almacenan o asocian datos a un buzón basado en la nube. La tabla también describe el tipo de contenido que genera cada aplicación.

<br>

****

|Microsoft 365 aplicación|Descripción|
|---|---|
|Formularios<sup>*</sup>|Los formularios y las respuestas a un formulario se almacenan en archivos adjuntos a mensajes de correo electrónico y se almacenan en una carpeta oculta en el buzón del usuario que creó el formulario. Los formularios creados antes de abril de 2020 se almacenan como un archivo PDF. Los formularios creados después de 2020 se almacenan como un archivo JSON. Las respuestas a un formulario se almacenan en un archivo CSV. Al exportar contenido de formularios en un archivo PST, estos datos se encuentran en la carpeta **ApplicationDataRoot** en una subcarpeta denominada con el siguiente identificador único global (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Grupos de Microsoft 365|Los mensajes de correo electrónico, los elementos de calendario, los contactos (personas), las notas y las tareas se almacenan en el buzón asociado a un grupo Microsoft 365 correo.|
|Outlook/Exchange Online|Los mensajes de correo electrónico, los elementos de calendario, los contactos (personas), las notas y las tareas se almacenan en el buzón de un usuario.|
|Personas|Los contactos de la aplicación Contactos (que son los mismos contactos que los accesibles en Outlook) se almacenan en el buzón de un usuario.|
|Programación de clases|Los planes creados en la programación de clases se almacenan en el buzón del grupo de Microsoft 365 correspondiente que se aprovisiona cuando se crea un nuevo plan. El alias del buzón de grupo es el nombre del plan.|
|Skype Empresarial|Las conversaciones Skype Empresarial se almacenan en la carpeta Historial de conversaciones en el buzón de un usuario. Si el buzón de un participante de una reunión de Skype se coloca en retención por juicio o se asigna a una directiva de retención, los archivos adjuntos a una reunión se conservan en el buzón de los participantes.|
|Sway<sup>*</sup>|Los Sways se almacenan como un archivo HTML que se adjunta a un mensaje de correo electrónico y se almacenan en una carpeta oculta en el buzón del usuario que creó el sway. Al exportar contenido de Sway en un archivo PST, estos datos se encuentran en la carpeta **ApplicationDataRoot** en una subcarpeta denominada con el siguiente GUID: **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**.|
|Tareas|Las tareas de la aplicación Tareas (que son las mismas tareas a las que se puede acceder en Outlook) se almacenan en el buzón de un usuario.|
|Teams|Las conversaciones que forman parte de un canal Teams están asociadas con el buzón Teams correo. Las conversaciones que forman parte de la lista chat de Teams (también denominadas *1 x N chats)* están asociadas con el buzón de los usuarios que participan en el chat. Además, la información de resumen de reuniones y llamadas en un canal de Teams están asociadas con buzones de los usuarios que marcaron en la reunión o llamada. Por lo tanto, al buscar Teams contenido, buscaría contenido en el buzón de Teams en conversaciones de canal y buscaría contenido en los buzones de usuario en chats de 1 x N.|
|To-Do|Las tareas (llamadas *a tareas* pendientes, que se guardan en listas de tareas pendientes) en la aplicación To-Do se almacenan en el buzón de un usuario.|
|Yammer|Las conversaciones y los comentarios dentro de una comunidad de Yammer están asociados con el buzón de grupo de Microsoft 365, así como con el buzón de usuario del autor y los destinatarios con nombre (usuarios @ mencionados o cc'ed). Los mensajes privados enviados fuera de una Yammer se almacenan en el buzón de los usuarios que participan en el mensaje privado.|
|

> [!NOTE]
> <sup>*</sup>En este momento, si se coloca una retención en un buzón (mediante retenciones en los casos principales de exhibición de documentos electrónicos o Advanced eDiscovery), el contenido de esta aplicación no se conservará mediante la retención.
