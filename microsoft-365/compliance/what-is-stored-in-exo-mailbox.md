---
title: Contenido almacenado en buzones de Exchange Online
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
ROBOTS: NOINDEX, NOFOLLOW
description: Los datos producidos por aplicaciones basadas en la nube en Microsoft 365 se almacenan o asocian con el buzón de Exchange Online de un usuario.
ms.openlocfilehash: f7bd5b00e8219f382078eb2d4f8aa25bd4c54d69
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750751"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Contenido almacenado en buzones de Exchange Online

Un buzón de Exchange Online se usa principalmente para almacenar elementos relacionados con el correo electrónico, como mensajes, elementos de calendario, tareas y notas. Pero eso está cambiando a medida que más aplicaciones basadas en la nube también almacenan sus datos en el buzón de un usuario. Una ventaja de almacenar datos en un buzón es que puede usar las herramientas de búsqueda en la búsqueda de contenido, eDiscovery principal, eDiscovery avanzado para buscar, ver y exportar los datos de estas aplicaciones basadas en la nube. Los datos de algunas de estas aplicaciones se almacenan en carpetas ocultas ubicadas en un subárbol de mensaje no interpersonal (que no es IPM) del buzón. Es posible que los datos de  otras aplicaciones basadas  en la nube no se almacenen en el buzón, pero están asociados con el buzón y se devuelven en las búsquedas (si los datos coinciden con la consulta de búsqueda). Independientemente de si los datos basados en la nube se almacenan o se asocian con un buzón de usuario, los datos normalmente no son visibles en un cliente de correo electrónico cuando un usuario abre su buzón.

En la tabla siguiente se enumeran las aplicaciones que almacenan o asocian datos con un buzón basado en la nube. La tabla también describe el tipo de contenido que genera cada aplicación.

|Aplicación de Microsoft 365|Descripción|
|:---------|:---------|
|Formularios|Los formularios y las respuestas a un formulario se almacenan en archivos adjuntos a mensajes de correo electrónico y se almacenan en una carpeta oculta en el buzón del usuario que creó el formulario. Los formularios creados antes de abril de 2020 se almacenan como un archivo PDF. Los formularios creados después de 2020 se almacenan como un archivo JSON.  Las respuestas a un formulario se almacenan en un archivo CSV. Al exportar contenido de formularios en un archivo PST, estos datos se encuentran en la carpeta **ApplicationDataRoot** en una subcarpeta denominada con el siguiente GUID único global: **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Grupos de Microsoft 365|Los mensajes de correo electrónico, los elementos de calendario, los contactos (personas), las notas y las tareas se almacenan en el buzón asociado a un grupo de Microsoft 365.|
|Outlook/Exchange Online|Los mensajes de correo electrónico, los elementos de calendario, los contactos (personas), las notas y las tareas se almacenan en el buzón de un usuario.|
|Contactos|Los contactos de la aplicación Contactos (que son los mismos contactos que los accesibles en Outlook) se almacenan en el buzón de un usuario.|
|Programación de clases|Los planes creados en la programación de clase se almacenan en el buzón del grupo de Microsoft 365 correspondiente que se aprovisiona cuando se crea un nuevo plan. El alias del buzón de grupo es el nombre del plan.|
|Skype Empresarial|Las conversaciones en Skype Empresarial se almacenan en la carpeta Historial de conversaciones del buzón de un usuario. Si el buzón de un participante de una reunión de Skype se coloca en retención por juicio o se asigna a una directiva de retención, los archivos adjuntos a una reunión se conservan en el buzón de los participantes.|
|Sway|Los Sways se almacenan como un archivo HTML que se adjunta a un mensaje de correo electrónico y se almacena en una carpeta oculta en el buzón del usuario que creó el sway. Cuando exporta contenido de Sway en un archivo PST, estos datos se encuentran en la carpeta **ApplicationDataRoot** en una subcarpeta denominada con el siguiente **GUID) 905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**.|
|Tareas|Las tareas de la aplicación Tareas (que son las mismas que las que se pueden tener acceso en Outlook) se almacenan en el buzón de un usuario.|
|Teams|Las conversaciones que forman parte de un canal de Teams están asociadas con el buzón de Teams. Las conversaciones que forman parte de la lista de chat en Teams (también *denominadas 1 x N chats)* están asociadas con el buzón de los usuarios que participan en el chat. Además, la información de resumen de las reuniones y llamadas en un canal de Teams se asocia con los buzones de los usuarios que llamaron a la reunión o llamada. Por lo tanto, al buscar contenido de Teams, buscaría en el buzón de Teams contenido en conversaciones de canal y buscará contenido en los buzones de usuario en 1 x N chats.| 
|To-Do|Las tareas *(llamadas tareas pendientes,* que se guardan en listas de tareas pendientes) en To-Do aplicación se almacenan en el buzón de un usuario.|
|Yammer|Las conversaciones y los comentarios dentro de una comunidad de Yammer están asociados al buzón del grupo de Microsoft 365, así como al buzón de usuario del autor y a cualquier destinatario con nombre (usuarios de @mentioned o cc'ed). Los mensajes privados enviados fuera de una comunidad de Yammer se almacenan en el buzón de los usuarios que participan en el mensaje privado.|  
||||

> [!NOTE]
> En este momento, si se coloca una retención en un buzón (mediante retenciones en casos de eDiscovery y eDiscovery avanzado), la retención no conservará el contenido de Forms y Sway. 
