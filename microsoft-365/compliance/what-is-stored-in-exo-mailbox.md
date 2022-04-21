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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
description: El contenido generado por las aplicaciones basadas en la nube en Microsoft 365 se almacena o asocia con el buzón Exchange Online de un usuario. Este contenido se puede buscar mediante las herramientas de Exhibición de documentos electrónicos de Microsoft.
ms.openlocfilehash: b5e8434f5345cda8ef4f637b3dff2d3cf704f748
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "65000804"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>Contenido almacenado en buzones de Exchange Online para eDiscovery

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Un buzón de Exchange Online se usa principalmente para almacenar elementos relacionados con el correo electrónico, como mensajes, elementos de calendario, tareas y notas. Pero eso cambia a medida que más aplicaciones basadas en la nube también almacenan sus datos en el buzón de un usuario. Una ventaja de almacenar datos en un buzón es que puede usar las herramientas de búsqueda en búsqueda de contenido, Microsoft Purview eDiscovery (Estándar) y Microsoft Purview eDiscovery (Premium) para buscar, ver y exportar los datos de estas aplicaciones basadas en la nube. Los datos de algunas de estas aplicaciones se almacenan en carpetas ocultas ubicadas en un subárbol de mensajes no predictivos (no IPM) en el buzón. Es posible que los datos de otras aplicaciones basadas en la nube no se almacenen _en_ el buzón, pero están _asociados al_ buzón y se devuelven en búsquedas (si esos datos coinciden con la consulta de búsqueda). Independientemente de si los datos basados en la nube se almacenan en o están asociados a un buzón de usuario, los datos no suelen ser visibles en un cliente de correo electrónico cuando un usuario abre su buzón.

En la tabla siguiente se enumeran las aplicaciones que almacenan o asocian datos a un buzón basado en la nube. En la tabla también se describe el tipo de contenido que genera cada aplicación.

<br>

****

|Microsoft 365 aplicación|Descripción|
|---|---|
|Formas<sup>*</sup>|Los formularios y las respuestas a un formulario se almacenan en archivos adjuntos a mensajes de correo electrónico y almacenados en una carpeta oculta en el buzón del usuario que creó el formulario. Los formularios creados antes de abril de 2020 se almacenan como un archivo PDF. Los formularios creados después de 2020 se almacenan como un archivo JSON. Las respuestas a un formulario se almacenan en un archivo CSV. Al exportar contenido de Formularios en un archivo PST, estos datos se encuentran en la carpeta **ApplicationDataRoot** de una subcarpeta denominada con el siguiente guid (IDENTIFICADOR único global): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Grupos de Microsoft 365|Los mensajes de correo electrónico, los elementos de calendario, los contactos (personas), las notas y las tareas se almacenan en el buzón asociado a un grupo de Microsoft 365.|
|Outlook/Exchange Online|Los mensajes de correo electrónico, los elementos de calendario, los contactos (personas), las notas y las tareas se almacenan en el buzón de un usuario.|
|Personas|Los contactos de la aplicación Personas (que son los mismos contactos a los que se puede acceder en Outlook) se almacenan en el buzón de un usuario.|
|Programación de clases|Los planes creados en la programación de clases se almacenan en el buzón del grupo de Microsoft 365 correspondiente que se aprovisiona cuando se crea un nuevo plan. El alias del buzón de grupo es el nombre del plan.|
|Skype Empresarial|Las conversaciones de Skype Empresarial se almacenan en la carpeta Historial de conversaciones del buzón de un usuario. Si el buzón de un participante de una reunión de Skype se coloca en suspensión por juicio o se asigna a una directiva de retención, los archivos adjuntos a una reunión se conservan en el buzón de los participantes.|
|Sway<sup>*</sup>|Los Sways se almacenan como un archivo HTML que se adjunta a un mensaje de correo electrónico y se almacenan en una carpeta oculta en el buzón del usuario que creó el sway. Al exportar contenido de Sway en un archivo PST, estos datos se encuentran en la carpeta **ApplicationDataRoot** de una subcarpeta denominada con el siguiente GUID: **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**.|
|Tareas|Las tareas de la aplicación Tareas (que son las mismas tareas a las que se puede acceder en Outlook) se almacenan en el buzón de un usuario.|
|Teams|Las conversaciones que forman parte de un canal de Teams están asociadas al buzón de Teams. Las conversaciones que forman parte de la lista chat de Teams (también *denominadas 1 x N chats) están asociadas* al buzón de los usuarios que participan en el chat. Además, la información de resumen de las reuniones y llamadas en un canal de Teams están asociadas a buzones de los usuarios que llamaron a la reunión o llamada. Por lo tanto, al buscar contenido Teams, buscaría contenido en las conversaciones de canal en el buzón de Teams y buscaría contenido en los buzones de usuario en 1 x N chats.|
|To-Do|Las tareas (llamadas *tareas pendientes*, que se guardan en listas de tareas pendientes) en la aplicación To-Do se almacenan en el buzón de un usuario.|
|Yammer|Las conversaciones y comentarios dentro de una comunidad de Yammer están asociados con el buzón de Microsoft 365 Grupo, así como el buzón de usuario del autor y los destinatarios con nombre (usuarios mencionados o cc'ed). Los mensajes privados enviados fuera de una comunidad Yammer se almacenan en el buzón de los usuarios que participan en el mensaje privado.|
|

> [!NOTE]
> <sup>*</sup>En este momento, si se coloca una suspensión en un buzón (mediante retenciones en casos de exhibición de documentos electrónicos (estándar) o eDiscovery (Premium), el contenido de esta aplicación no se conservará en la suspensión.
