---
title: Comprobar errores en la consulta de búsqueda
description: Obtenga información sobre cómo detectar errores y errores tipográficos en la consulta de palabras clave para búsquedas de exhibición de documentos electrónicos antes de ejecutar la búsqueda.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
ms.collection:
- tier1
- purview-compliance
- ediscovery
ms.openlocfilehash: 30aebce0734c7e9043516cb058fb1aceaa79c9ef
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68688047"
---
# <a name="check-your-search-query-for-errors"></a>Comprobar errores en la consulta de búsqueda
  
Esta es una lista de los caracteres no admitidos que se comprueban en las consultas de búsqueda para búsqueda de contenido y Microsoft Purview eDiscovery (estándar). Los caracteres no admitidos suelen estar ocultos y suelen provocar un error de búsqueda o devolver resultados no deseados.
  
- **Comillas inteligentes** : no se admiten comillas simples y dobles inteligentes (también denominadas comillas rizas). Solo pueden usarse las comillas tipográficas en una consulta de búsqueda.
- **Caracteres de control y no imprimibles** : los caracteres no imprimibles y de control no representan un símbolo escrito, como un carácter alfanumérico. Los ejemplos de caracteres de control no imprimibles incluyen caracteres que aplican formato al texto o que separan líneas de texto.
- **Marcas de izquierda a derecha y de derecha a izquierda** : estas marcas son caracteres de control que se usan para indicar la dirección del texto para los idiomas de izquierda a derecha (como inglés y español) y de derecha a izquierda (como árabe y hebreo).
- **Operadores booleanos en minúsculas** : si usa un operador booleano, como **AND**, **OR** y **NOT** en una consulta de búsqueda, debe estar en mayúsculas. Al comprobar si hay errores tipográficos en una consulta, la sintaxis de consulta a menudo indicará que se usa un operador booleano aunque se puedan usar operadores en minúsculas; por ejemplo,  `(WordA or WordB) and (WordC or WordD)`.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>¿Qué ocurre si una consulta tiene un carácter no admitido?

Si se encuentran caracteres no admitidos en la consulta, se muestra un mensaje de advertencia que indica que se encontraron caracteres no admitidos y sugiere una alternativa. A continuación, tiene la opción de conservar la consulta original o reemplazarla por la consulta revisada sugerida.

Este es un ejemplo del mensaje de advertencia que se muestra después de seleccionar **Comprobar la consulta de errores tipográficos** para la consulta de búsqueda en la captura de pantalla anterior. Tenga en cuenta que la consulta original usó comillas inteligentes y operadores booleanos en minúsculas.
  
![Se muestra un mensaje de advertencia con una revisión sugerida para la consulta.](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Cómo evitar caracteres no admitidos en las consultas de búsqueda

Normalmente, los caracteres no admitidos se agregan a una consulta al copiar la consulta o partes de la consulta de otras aplicaciones (como Microsoft Word o Microsoft Excel) y pegarlos en el cuadro de palabra clave de la página de consulta de una búsqueda de contenido. La mejor manera de evitar los caracteres no admitidos es simplemente escribir la consulta en el cuadro de palabras clave. O bien, puede copiar una consulta de Word o Excel y pegarla en un editor de texto sin formato, como El Bloc de notas de Microsoft. Guarde el archivo de texto y seleccione **ANSI** en la lista desplegable **Codificación** . Esto quitará cualquier carácter no admitido y de formato. Después, podrá copiar y pegar la consulta del archivo de texto en el cuadro de consulta de palabras clave.
