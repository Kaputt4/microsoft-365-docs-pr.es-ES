---
title: Comprobar errores en la consulta de búsqueda
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo detectar errores y errores tipográficos en la consulta de palabras clave para las búsquedas de exhibición de documentos electrónicos antes de ejecutar la búsqueda.
ms.openlocfilehash: 9c041ca690df3306347cbca77df3ba9639801245
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311693"
---
# <a name="check-your-search-query-for-errors"></a>Comprobar errores en la consulta de búsqueda
  
Esta es una lista de los caracteres no admitidos que buscamos en las consultas de búsqueda para búsqueda de contenido y exhibición de documentos electrónicos principales. Los caracteres no admitidos suelen estar ocultos y normalmente causan un error de búsqueda o devuelven resultados no deseados.
  
- **Comillas inteligentes:** no se admiten comillas simples y dobles inteligentes (también denominadas comillas rizado). Solo pueden usarse las comillas tipográficas en una consulta de búsqueda. 

- **Caracteres de control y** no imprimibles: los caracteres de control y no imprimibles no representan un símbolo escrito, como un carácter alfanumérico. Los ejemplos de caracteres de control no imprimibles incluyen caracteres que aplican formato al texto o que separan líneas de texto. 

- **Marcas de** izquierda a derecha y de derecha a izquierda: estas marcas son caracteres de control que se usan para indicar la dirección del texto para los idiomas de izquierda a derecha (como inglés y español) y los idiomas de derecha a izquierda (como árabe y hebreo).

- **Operadores booleanos** en minúsculas: si usa un operador booleano, como **AND**, **OR** y **NOT** en una consulta de búsqueda, debe estar en mayúsculas. Cuando se comprueba si hay errores tipográficos en una consulta, la sintaxis de consulta a menudo indica que se está utilizando un operador booleano aunque se puedan usar operadores en minúsculas; por ejemplo,  `(WordA or WordB) and (WordC or WordD)` .

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>¿Qué sucede si una consulta tiene un carácter no compatible?

Si se encuentran caracteres no admitidos en la consulta, se muestra un mensaje de advertencia que indica que se encontraron caracteres no admitidos y sugiere una alternativa. A continuación, tiene la opción de conservar la consulta original o reemplazarla por la consulta revisada sugerida.

Este es un ejemplo del mensaje de advertencia que  se muestra después de hacer clic en Comprobar la consulta para errores tipográficos para la consulta de búsqueda en la captura de pantalla anterior. Tenga en cuenta que la consulta original usaba comillas inteligentes y operadores booleanos en minúsculas.
  
![Se muestra un mensaje de advertencia con una revisión sugerida para la consulta](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Cómo evitar caracteres no admitidos en las consultas de búsqueda

Los caracteres no admitidos normalmente se agregan a una consulta cuando se copia la consulta o partes de la consulta desde otras aplicaciones (como Microsoft Word o Microsoft Excel) y se pegan en el cuadro de palabras clave de la página de consulta de una búsqueda de contenido. La mejor manera de evitar los caracteres no admitidos es simplemente escribir la consulta en el cuadro de palabras clave. O puede copiar una consulta de Word o Excel y, a continuación, pegarla en un editor de texto sin formato, como Microsoft Bloc de notas. Guarde el archivo de texto y **seleccione ANSI** en **la** lista desplegable Codificación. Esto quitará cualquier carácter no admitido y de formato. Después, podrá copiar y pegar la consulta del archivo de texto en el cuadro de consulta de palabras clave.
