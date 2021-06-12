---
title: Usar Microsoft Search para buscar temas en Temas de Microsoft Viva
ms.author: chuckedmonson
author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Obtenga información sobre cómo puede buscar temas en Microsoft Viva.
ms.openlocfilehash: 3bd247bfacc6a85bb19c8f4eeedb5aad8662e60e
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908070"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Usar Microsoft Search para buscar temas en Temas de Microsoft Viva

Aunque los usuarios de Viva Topics pueden encontrar temas a través de temas destacados en sus SharePoint, también pueden encontrarlos a través de Microsoft Search. 

## <a name="topic-answer"></a>Respuesta al tema

Cuando busque un tema específico en la página de inicio de SharePoint, en Office.com o desde un sitio de SharePoint que haya sido ámbito de su organización, si existe y se encuentra un tema, mostrará el resultado en el formato de sugerencia de respuesta del tema.

La respuesta al tema mostrará:

- Nombre del tema
- Nombres alternativos: nombres alternativos o acrónimos para el tema.
- Definición: descripción del tema proporcionado por IA o agregado manualmente por una persona.
- Personas sugeridas o ancladas: personas sugeridas por AI o ancladas al tema por una persona
- Recursos sugeridos o anclados: archivos, páginas o sitios sugeridos por AI o anclados al tema por una persona. 

   ![Tema de búsqueda](../media/knowledge-management/search-topic-answer.png) 

La página del tema puede mostrarse en los resultados de búsqueda incluso si no aparece la tarjeta de respuesta del tema.

Los resultados de la búsqueda en Word, PowerPoint, Outlook y Excel también mostrarán la respuesta del tema cuando se encuentra uno.

## <a name="acronyms"></a>Acrónimos

En Temas de Viva, puede editar manualmente un tema para incluir un acrónimo para él como *un nombre alternativo*. Esto permite que un usuario que está buscando solo por las siglas del tema encuentre la respuesta del tema a través de Microsoft Search.

[Acronym Answers](/microsoftsearch/manage-acronyms) es una característica proporcionada a través de Microsoft Search y se administra por separado de Viva Topics.

## <a name="bookmarks-and-topics"></a>Marcadores y temas

[Los marcadores](/microsoftsearch/manage-bookmarks) son una característica de Microsoft Search que ayuda a los usuarios a encontrar rápidamente sitios y herramientas importantes con solo una búsqueda (por ejemplo, una herramienta de reserva de viajes en un sitio externo fuera de su inquilino de Microsoft 365). Los administradores de búsqueda los crean en el centro de administración Microsoft 365 búsqueda. 

Para los usuarios que buscan información sobre cómo reservar un viaje de trabajo:

- Si algunos usuarios conocen el nombre de la herramienta de viaje (por ejemplo, "Concur"), es más fácil crear un marcador para ir directamente al sitio externo.

- Para los usuarios que buscan generalmente "viajes", cree un tema en "Viajes" que tenga la información que esperan ver. Considere la posibilidad de agregar un vínculo al sitio externo Concur en la descripción del tema. Si el vínculo es en su lugar a un sitio de reserva de viajes interno hospedado en el espacio empresarial Microsoft 365, puede agregarlo a los "Recursos anclados".
 
### <a name="search-results-priority"></a>Prioridad de resultados de búsqueda 

En la experiencia de búsqueda del usuario, cuando un usuario busca un término como "viajes", aparecerá un marcador en lugar de un tema, si hay un marcador disponible.

## <a name="see-also"></a>Consulte también

[Introducción a Temas de Viva](topic-experiences-overview.md)
