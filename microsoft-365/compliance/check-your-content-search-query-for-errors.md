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
# <a name="check-your-search-query-for-errors"></a><span data-ttu-id="908d3-103">Comprobar errores en la consulta de búsqueda</span><span class="sxs-lookup"><span data-stu-id="908d3-103">Check your search query for errors</span></span>
  
<span data-ttu-id="908d3-104">Esta es una lista de los caracteres no admitidos que buscamos en las consultas de búsqueda para búsqueda de contenido y exhibición de documentos electrónicos principales.</span><span class="sxs-lookup"><span data-stu-id="908d3-104">Here's a list of the unsupported characters that we check for in search queries for Content search and Core eDiscovery.</span></span> <span data-ttu-id="908d3-105">Los caracteres no admitidos suelen estar ocultos y normalmente causan un error de búsqueda o devuelven resultados no deseados.</span><span class="sxs-lookup"><span data-stu-id="908d3-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="908d3-106">**Comillas inteligentes:** no se admiten comillas simples y dobles inteligentes (también denominadas comillas rizado).</span><span class="sxs-lookup"><span data-stu-id="908d3-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="908d3-107">Solo pueden usarse las comillas tipográficas en una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="908d3-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="908d3-108">**Caracteres de control y** no imprimibles: los caracteres de control y no imprimibles no representan un símbolo escrito, como un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="908d3-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="908d3-109">Los ejemplos de caracteres de control no imprimibles incluyen caracteres que aplican formato al texto o que separan líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="908d3-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="908d3-110">**Marcas de** izquierda a derecha y de derecha a izquierda: estas marcas son caracteres de control que se usan para indicar la dirección del texto para los idiomas de izquierda a derecha (como inglés y español) y los idiomas de derecha a izquierda (como árabe y hebreo).</span><span class="sxs-lookup"><span data-stu-id="908d3-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="908d3-111">**Operadores booleanos** en minúsculas: si usa un operador booleano, como **AND**, **OR** y **NOT** en una consulta de búsqueda, debe estar en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="908d3-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="908d3-112">Cuando se comprueba si hay errores tipográficos en una consulta, la sintaxis de consulta a menudo indica que se está utilizando un operador booleano aunque se puedan usar operadores en minúsculas; por ejemplo,  `(WordA or WordB) and (WordC or WordD)` .</span><span class="sxs-lookup"><span data-stu-id="908d3-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="908d3-113">¿Qué sucede si una consulta tiene un carácter no compatible?</span><span class="sxs-lookup"><span data-stu-id="908d3-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="908d3-114">Si se encuentran caracteres no admitidos en la consulta, se muestra un mensaje de advertencia que indica que se encontraron caracteres no admitidos y sugiere una alternativa.</span><span class="sxs-lookup"><span data-stu-id="908d3-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="908d3-115">A continuación, tiene la opción de conservar la consulta original o reemplazarla por la consulta revisada sugerida.</span><span class="sxs-lookup"><span data-stu-id="908d3-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="908d3-116">Este es un ejemplo del mensaje de advertencia que  se muestra después de hacer clic en Comprobar la consulta para errores tipográficos para la consulta de búsqueda en la captura de pantalla anterior.</span><span class="sxs-lookup"><span data-stu-id="908d3-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="908d3-117">Tenga en cuenta que la consulta original usaba comillas inteligentes y operadores booleanos en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="908d3-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![Se muestra un mensaje de advertencia con una revisión sugerida para la consulta](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="908d3-119">Cómo evitar caracteres no admitidos en las consultas de búsqueda</span><span class="sxs-lookup"><span data-stu-id="908d3-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="908d3-120">Los caracteres no admitidos normalmente se agregan a una consulta cuando se copia la consulta o partes de la consulta desde otras aplicaciones (como Microsoft Word o Microsoft Excel) y se pegan en el cuadro de palabras clave de la página de consulta de una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="908d3-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="908d3-121">La mejor manera de evitar los caracteres no admitidos es simplemente escribir la consulta en el cuadro de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="908d3-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="908d3-122">O puede copiar una consulta de Word o Excel y, a continuación, pegarla en un editor de texto sin formato, como Microsoft Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="908d3-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="908d3-123">Guarde el archivo de texto y **seleccione ANSI** en **la** lista desplegable Codificación.</span><span class="sxs-lookup"><span data-stu-id="908d3-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="908d3-124">Esto quitará cualquier carácter no admitido y de formato.</span><span class="sxs-lookup"><span data-stu-id="908d3-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="908d3-125">Después, podrá copiar y pegar la consulta del archivo de texto en el cuadro de consulta de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="908d3-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span>
