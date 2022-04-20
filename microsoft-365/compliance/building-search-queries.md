---
title: Compilación de consultas de búsqueda en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: Use palabras clave y condiciones para restringir el ámbito de la búsqueda al buscar datos mediante eDiscovery (Premium) en Microsoft 365.
ms.openlocfilehash: cceac6974bacb066201120ac4972393f2323353c
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64995016"
---
# <a name="build-search-queries-for-collections-in-ediscovery-premium"></a>Compilación de consultas de búsqueda para colecciones en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Al configurar la consulta de búsqueda al crear una [colección](collections-overview.md) en un caso de exhibición de documentos electrónicos (Premium), puede usar palabras clave para buscar contenido y condiciones específicos para restringir el ámbito de la búsqueda y devolver los elementos más relevantes para la investigación legal.

![Use palabras clave y condiciones para restringir los resultados de una búsqueda.](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Búsquedas de palabras clave

Escriba una consulta de palabra clave en el cuadro **Palabras clave** de la consulta de búsqueda. Puede especificar palabras clave, propiedades de mensaje de correo electrónico, como fechas de envío y recepción, o propiedades de documento, como nombres de archivo o la fecha en que se cambió por última vez un documento. También puede usar consultas más complejas con operadores booleanos como **Y**, **O**, **NOT** y **NEAR**. También puede buscar información confidencial (como números de seguridad social) en documentos de SharePoint y OneDrive (no en mensajes de correo electrónico) o buscar documentos que se hayan compartido externamente. Si deja el cuadro **Palabras clave** en blanco, todo el contenido de las ubicaciones de contenido especificadas aparecerá en los resultados de la búsqueda.

## <a name="keyword-list"></a>Lista de palabras clave

Como alternativa, puede activar la casilla **Mostrar lista de palabras clave** y escribir una palabra clave o frase de palabra clave en cada fila. Las palabras clave de cada fila están conectadas por un operador lógico (que se representa como *c:s* en la sintaxis de consulta de búsqueda) que es similar en funcionalidad al operador **OR** de la consulta de búsqueda que se crea. Esto significa que los elementos que contienen cualquier palabra clave en cualquier fila están en los resultados de la búsqueda. Puede agregar hasta 180 filas en la lista de palabras clave en consultas de búsqueda de eDiscovery (Premium).

![Use la lista de palabras clave para obtener estadísticas sobre cada palabra clave de la consulta.](../media/KeywordListSearch.png)

¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestren cuántos elementos coinciden con cada palabra clave de la lista de palabras clave. Esto puede ayudarle a identificar rápidamente las palabras clave que son más (y menos) eficaces. También puede usar una frase de palabra clave (rodeada de paréntesis) en una fila de la lista de palabras clave. Para obtener más información sobre las estadísticas de búsqueda, consulte [Estadísticas e informes de recopilación](collection-statistics-reports.md).

## <a name="conditions"></a>Condiciones

Puede agregar condiciones de búsqueda para restringir el ámbito de una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crea y se ejecuta cuando se inicia la búsqueda. Una condición está conectada lógicamente a la consulta de palabra clave especificada en el cuadro de palabra clave por un operador lógico (que se representa como *c:c* en la sintaxis de consulta de búsqueda) que es similar en funcionalidad al operador **AND** . Esto significa que los elementos deben cumplir la consulta de palabra clave y una o varias condiciones que se incluirán en los resultados de la búsqueda. De esta manera, las condiciones permiten restringir los resultados. Para obtener una lista y una descripción de las condiciones que puede usar en una consulta de búsqueda, consulte la sección "Condiciones de búsqueda" en [Consultas de palabras clave y condiciones de búsqueda](keyword-queries-and-search-conditions.md#search-conditions).
