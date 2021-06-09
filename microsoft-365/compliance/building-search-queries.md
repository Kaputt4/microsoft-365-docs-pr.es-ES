---
title: Crear consultas de búsqueda en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: Use palabras clave y condiciones para restringir el ámbito de la búsqueda al buscar datos mediante Advanced eDiscovery en Microsoft 365.
ms.openlocfilehash: e0df319257776d3995a4b8e37781d7b5dad54d82
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838490"
---
# <a name="build-search-queries-for-collections-in-advanced-ediscovery"></a>Crear consultas de búsqueda para colecciones en Advanced eDiscovery

Al configurar la consulta de [](collections-overview.md) búsqueda al crear una colección en un caso de Advanced eDiscovery, puede usar palabras clave para buscar contenido y condiciones específicas para restringir el ámbito de la búsqueda para devolver los elementos más relevantes para la investigación legal.

![Usar palabras clave y condiciones para restringir los resultados de una búsqueda](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Búsquedas de palabras clave

Escriba una consulta de palabras clave en **el cuadro Palabras clave** de la consulta de búsqueda. Puede especificar palabras clave, propiedades de mensaje de correo electrónico, como fechas enviadas y recibidas, o propiedades de documento, como nombres de archivo o la fecha en que se cambió por última vez un documento. También puede usar consultas más complejas con operadores booleanos como **Y**, **O**, **NOT** y **NEAR**. También puede buscar información confidencial (como números de seguridad social) en documentos de SharePoint y OneDrive (no en mensajes de correo electrónico) o buscar documentos que se hayan compartido externamente. Si deja el cuadro **Palabras clave** en blanco, todo el contenido de las ubicaciones de contenido especificadas aparecerá en los resultados de la búsqueda.

## <a name="keyword-list"></a>Lista de palabras clave

Como alternativa, puede activar la **casilla** Mostrar lista de palabras clave y escribir una palabra clave o frase de palabra clave en cada fila. Las palabras clave de cada fila están conectadas por un operador lógico (que se representa como *c:s* en la sintaxis de consulta de búsqueda) que es similar en funcionalidad al operador **OR** en la consulta de búsqueda que se crea. Esto significa que los elementos que contienen cualquier palabra clave en cualquier fila están en los resultados de la búsqueda. Puede agregar hasta 180 filas en la lista de palabras clave en Advanced eDiscovery de búsqueda.

![Usar la lista de palabras clave para obtener estadísticas de cada palabra clave de la consulta](../media/KeywordListSearch.png)

¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave de la lista de palabras clave. Esto puede ayudarle a identificar rápidamente las palabras clave que son más (y menos) eficaces. También puede usar una frase de palabra clave (entre paréntesis) en una fila de la lista de palabras clave. Para obtener más información acerca de las estadísticas de búsqueda, vea [Estadísticas de búsqueda](search-statistics-in-advanced-ediscovery.md).

## <a name="conditions"></a>Condiciones

Puede agregar condiciones de búsqueda para restringir el ámbito de una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crea y se ejecuta cuando se inicia la búsqueda. Una condición está conectada lógicamente a la consulta de palabras clave especificada en el cuadro de palabras clave por un operador lógico (que se representa como *c:c* en la sintaxis de consulta de búsqueda) que es similar en funcionalidad al operador **AND.** Esto significa que los elementos deben satisfacer tanto la consulta de palabras clave como una o más condiciones para incluirse en los resultados de la búsqueda. De esta manera, las condiciones permiten restringir los resultados. Para obtener una lista y una descripción de las condiciones que puede usar en una consulta de búsqueda, vea la sección "Condiciones de búsqueda" en Consultas de palabras clave y condiciones [de búsqueda.](keyword-queries-and-search-conditions.md#search-conditions)
