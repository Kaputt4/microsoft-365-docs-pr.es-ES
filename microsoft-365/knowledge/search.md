---
title: Usar Microsoft Search para buscar temas en Temas de Microsoft Viva
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: Obtenga información sobre cómo puede buscar temas en Microsoft Viva.
ms.openlocfilehash: 484d2477f7e4dbef096a4b8a2d30095708c6cc3f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50108315"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>Usar Microsoft Search para buscar temas en Temas de Microsoft Viva

Aunque los usuarios de Temas Viva pueden encontrar temas a través de temas destacados en sus sitios de SharePoint, también pueden encontrarlos a través de Microsoft Search. 

## <a name="topic-answer"></a>Respuesta al tema

Cuando busque un tema específico en Microsoft Search (por ejemplo, "Saturno"), si existe un tema y se encuentra, mostrará el resultado en el formato de sugerencia de respuestas.

Se mostrará la respuesta al tema:
- Nombre del tema
- Nombres alternativos: nombres alternativos o acrónimos del tema.
- Definición: descripción del tema proporcionado por AI o agregado manualmente por una persona.
- Personas sugeridas o ancladas: personas sugeridas por AI o ancladas al tema por una persona
- Recursos sugeridos o anclados: archivos, páginas o sitios sugeridos por una IA o anclados al tema por una persona. 

   ![Tema de la búsqueda](../media/knowledge-management/search-topic-answer.png) 

La página del tema puede mostrarse en los resultados de la búsqueda incluso si no aparece la tarjeta de respuesta del tema.


## <a name="acronyms"></a>Acrónimos

En Temas de Viva, puede editar manualmente un tema para incluir un acrónimo como <b>nombre alternativo.</b> Esto permite que un usuario que está buscando solo por el acrónimo del tema encuentre la respuesta del tema a través de Microsoft Search.

[Acronym Answers](https://docs.microsoft.com/microsoftsearch/manage-acronyms) es una característica proporcionada a través de Microsoft Search y se administra por separado de Viva Topics.

## <a name="bookmarks-and-topics"></a>Marcadores y temas

Los [marcadores](https://docs.microsoft.com/microsoftsearch/manage-bookmarks) son una característica de Búsqueda de Microsoft que ayuda a los usuarios a encontrar rápidamente sitios y herramientas importantes con solo una búsqueda (por ejemplo, una herramienta de reserva de viajes en un sitio externo fuera de su espacio empresarial de Microsoft 365). Los administradores de búsqueda los crean en el Centro de administración de Microsoft 365. 

Para los usuarios que buscan información sobre cómo reservar un viaje para el trabajo:

- Si algunos usuarios conocen el nombre de la herramienta de viajes (por ejemplo, "Concur"), es más fácil crear un marcador para ir directamente al sitio externo.
- Para los usuarios que buscan generalmente "viajes", cree un tema sobre "Viajes" que tenga la información que esperan ver. Considere la posibilidad de agregar un vínculo al sitio externo Concur en la descripción del tema. Si el vínculo es en su lugar a un sitio de reserva de viajes interno hospedado en el inquilino de Microsoft 365, puede agregarlo a los "Recursos anclados".
 
### <a name="search-results-priority"></a>Prioridad de los resultados de la búsqueda 
 
En la experiencia de búsqueda de usuarios, cuando un usuario busca un término como "viajes", los resultados de la búsqueda se mostrarán con la siguiente prioridad en Microsoft Search
1. Temas publicados o confirmados 
2. Marcadores
3. Temas sugeridos 



