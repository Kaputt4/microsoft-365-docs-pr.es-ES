---
title: Contenido almacenado en buzones de correo de Exchange Online
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
description: Los datos producidos por las aplicaciones basadas en la nube en Office 365 se almacenan o asocian con el buzón de correo de un usuario de Exchange Online.
ms.openlocfilehash: 88cd2bf459ed7a50c06194b22f2ae6a999380d51
ms.sourcegitcommit: 9a4084ce2b80bac883412e0ec956b6c0cc18d0f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "42400987"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Contenido almacenado en buzones de correo de Exchange Online

Un buzón de Exchange Online se usa principalmente para almacenar elementos relacionados con el correo electrónico, como mensajes, elementos de calendario, tareas y notas. Pero esto cambia a medida que más aplicaciones de Office 365 basadas en la nube también almacenan sus datos en el buzón de un usuario. Una de las ventajas de almacenar datos en un buzón es que puede usar las herramientas de búsqueda en la búsqueda de contenido, la exhibición de documentos electrónicos principal, la exhibición avanzada de documentos electrónicos y las investigaciones de datos para buscar, ver y exportar los datos de estas aplicaciones basadas en la nube. Los datos de algunas de estas aplicaciones se almacenan en carpetas ocultas que se encuentran en un subárbol de mensajes no interpersonales (no IPM) en el buzón. Es posible que los datos de otras aplicaciones basadas en la nube no se almacenen _en_ el buzón de correo, pero están _asociados con_ el buzón de correo y se devuelven en las búsquedas (si esos datos coinciden con la consulta de búsqueda). Independientemente de si los datos basados en la nube se almacenan en un buzón de usuario o están asociados a él, los datos no suelen ser visibles en un cliente de correo electrónico cuando un usuario abre su buzón.

En la siguiente tabla se enumeran las aplicaciones de Office 365 que almacenan o asocian datos con un buzón basado en la nube. La tabla también describe el tipo de contenido que produce cada aplicación.

|Aplicación de Office 365|Description|
|:---------|:---------|
|Formularios|Los formularios (almacenados como un archivo PDF) y las respuestas a un formulario (almacenado en un archivo CSV) se adjuntan a los mensajes de correo electrónico y se almacenan en una carpeta oculta en el buzón del usuario que creó el formulario. Al exportar contenido de formularios en un archivo PST, estos datos se encuentran en la carpeta **ApplicationDataRoot** en una subcarpeta denominada con el siguiente globalmente identificado (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Grupos de Office 365|Los mensajes de correo electrónico, los elementos de calendario, los contactos (personas), las notas y las tareas se almacenan en el buzón de correo asociado con un grupo de Office 365.|
|Outlook/Exchange Online|Los mensajes de correo electrónico, los elementos de calendario, los contactos (personas), las notas y las tareas se almacenan en el buzón de un usuario.|
|Contactos|Los contactos de la aplicación contactos (que son los mismos contactos que los que son accesibles en Outlook) se almacenan en el buzón de un usuario.|
|Programación de clases|Los planes creados en el programa de clases se almacenan en el buzón del grupo de Office 365 correspondiente que se aprovisiona cuando se crea un plan nuevo. El alias para el buzón de grupo es el nombre del plan.|
|Skype Empresarial|Las conversaciones en Skype empresarial se almacenan en la carpeta Historial de conversaciones en el buzón de un usuario. Si el buzón de un participante de una reunión de Skype se coloca en retención por juicio o se asigna a una directiva de retención, los archivos adjuntos a una reunión se conservan en el buzón de participantes.|
|Sway|Los sways se almacenan como un archivo HTML que se adjunta a un mensaje de correo electrónico y se almacenan en una carpeta oculta en el buzón del usuario que creó el Sway. Al exportar contenido de Sway en un archivo PST, estos datos se encuentran en la carpeta **ApplicationDataRoot** en una subcarpeta denominada con el siguiente GUID) **905fcf26-4eb7-48A0-9ff0-8dcc7194b5ba**.|
|Tareas|Las tareas de la aplicación tareas (que son las mismas tareas que las que son accesibles en Outlook) se almacenan en el buzón de un usuario.|
|Teams|Las conversaciones que forman parte de un canal de Teams están asociadas con el buzón de correo de Microsoft Teams. Las conversaciones que forman parte de la lista de chats en Microsoft Teams (también llamadas *1 x N chats*) se asocian con el buzón de los usuarios que participan en el chat. Además, la información de Resumen de las reuniones y las llamadas en un canal de Microsoft Teams se asocia con los buzones de correo de los usuarios que marcaron la reunión o la llamada. Por lo tanto, al buscar contenido en Teams, buscará contenido en conversaciones de canal y buzones de usuario de búsqueda en el buzón de correo de Microsoft Teams en 1 x N chats.| 
|To-Do|Las tareas ( *llamadas tareas que se*guardan en listas de tareas pendientes) en la aplicación de tareas se almacenan en el buzón de un usuario.|
||||

> [!NOTE]
> En este momento, si se coloca una retención en un buzón (mediante retenciones en la exhibición de documentos electrónicos y en casos de eDiscovery avanzados), el contenido de los formularios y de Sway no se conservará en la retención. 
