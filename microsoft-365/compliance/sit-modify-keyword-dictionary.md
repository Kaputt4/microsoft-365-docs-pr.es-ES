---
title: Modificar un diccionario de palabras clave
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo modificar un diccionario de palabras clave en el Centro Microsoft 365 cumplimiento.
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685226"
---
# <a name="modify-a-keyword-dictionary"></a><span data-ttu-id="1bdba-103">Modificar un diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="1bdba-103">Modify a keyword dictionary</span></span>

<span data-ttu-id="1bdba-104">Es posible que tenga que modificar palabras clave en uno de los diccionarios de palabras clave o modificar uno de los diccionarios integrados.</span><span class="sxs-lookup"><span data-stu-id="1bdba-104">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="1bdba-105">Puede hacerlo a través de PowerShell o a través del Centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1bdba-105">You can do this through PowerShell or through the Compliance center.</span></span>

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a><span data-ttu-id="1bdba-106">Modificar un diccionario de palabras clave en el Centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="1bdba-106">Modify a keyword dictionary in Compliance center</span></span>

<span data-ttu-id="1bdba-107">Los diccionarios de palabras clave se pueden usar como o en patrones de tipo de información `Primary elements` `Supporting elements` confidencial (SIT).</span><span class="sxs-lookup"><span data-stu-id="1bdba-107">Keyword dictionaries can be used as `Primary elements` or `Supporting elements` in sensitive information type (SIT) patterns.</span></span> <span data-ttu-id="1bdba-108">Puede editar un diccionario de palabras clave al crear un SIT o en un SIT existente.</span><span class="sxs-lookup"><span data-stu-id="1bdba-108">You can edit a keyword dictionary while creating a SIT or in an existing SIT.</span></span> <span data-ttu-id="1bdba-109">Por ejemplo, para editar un diccionario de palabras clave existente:</span><span class="sxs-lookup"><span data-stu-id="1bdba-109">For example to edit an existing keyword dictionary:</span></span>

1. <span data-ttu-id="1bdba-110">Abra el patrón que tiene el diccionario de palabras clave que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="1bdba-110">Open the pattern that has the keyword dictionary you want to update.</span></span>
2. <span data-ttu-id="1bdba-111">Busque el diccionario de palabras clave que desea actualizar y elija editar.</span><span class="sxs-lookup"><span data-stu-id="1bdba-111">Find the keyword dictionary you want to update and choose edit.</span></span> 
3.  <span data-ttu-id="1bdba-112">Realice las ediciones con una palabra clave por línea.</span><span class="sxs-lookup"><span data-stu-id="1bdba-112">Make your edits, using one keyword per line.</span></span>

![palabras clave de edición de captura de pantalla](../media/edit-keyword-dictionary.png)

4. <span data-ttu-id="1bdba-114">Elija `Done` .</span><span class="sxs-lookup"><span data-stu-id="1bdba-114">Choose `Done`.</span></span>

## <a name="modify-a-keyword-dictionary-using-powershell"></a><span data-ttu-id="1bdba-115">Modificar un diccionario de palabras clave con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bdba-115">Modify a keyword dictionary using PowerShell</span></span> 

<span data-ttu-id="1bdba-116">Por ejemplo, vamos a modificar algunos términos en PowerShell, guardar los términos localmente donde se puedan modificar en un editor y, después, actualizar los términos anteriores.</span><span class="sxs-lookup"><span data-stu-id="1bdba-116">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="1bdba-117">En primer lugar, recupere el objeto de diccionario:</span><span class="sxs-lookup"><span data-stu-id="1bdba-117">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="1bdba-118">La impresión de `$dict` mostrará las distintas variables.</span><span class="sxs-lookup"><span data-stu-id="1bdba-118">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="1bdba-119">Las palabras clave en sí se almacenan en un objeto en el back-end, pero `$dict.KeywordDictionary` contiene una representación de cadena de estas, que usará para modificar el diccionario.</span><span class="sxs-lookup"><span data-stu-id="1bdba-119">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="1bdba-120">Antes de modificar el diccionario, necesita volver a convertir la cadena de términos en una matriz con el método `.split(',')`.</span><span class="sxs-lookup"><span data-stu-id="1bdba-120">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="1bdba-121">Después, eliminará los espacios no deseados entre las palabras clave con el método `.trim()` y dejará únicamente las palabras clave con las que quiera trabajar.</span><span class="sxs-lookup"><span data-stu-id="1bdba-121">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="1bdba-p105">Ahora, quitará algunos términos del diccionario. Como el diccionario de ejemplo solo tiene unas pocas palabras clave, podría fácilmente pasar a la exportación del diccionario y editarlo en el Bloc de notas, pero los diccionarios suelen contener una gran cantidad de texto, por lo que primero aprenderá esta forma de editarlos fácilmente en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bdba-p105">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="1bdba-p106">En el último paso, guardó las palabras clave en una matriz. Hay varias formas de [quitar elementos de una matriz](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), pero un método sencillo es crear una matriz de los términos que quiera quitar del diccionario y, después, copiar en este solo los términos que no se encuentren en la lista de términos que quiera quitar.</span><span class="sxs-lookup"><span data-stu-id="1bdba-p106">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="1bdba-p107">Ejecute el comando `$terms` para mostrar la lista de términos actual. El resultado del comando tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="1bdba-p107">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

<span data-ttu-id="1bdba-128">Ejecute este comando para especificar los términos que quiera quitar:</span><span class="sxs-lookup"><span data-stu-id="1bdba-128">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="1bdba-129">Ejecute este comando para quitar los términos de la lista:</span><span class="sxs-lookup"><span data-stu-id="1bdba-129">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="1bdba-p108">Ejecute el comando `$updatedTerms` para mostrar la lista actualizada de términos. El resultado del comando será parecido a este (se quitaron los términos especificados):</span><span class="sxs-lookup"><span data-stu-id="1bdba-p108">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="1bdba-p109">Ahora, abra el archivo, agregue los otros términos y guárdelo con la codificación Unicode (UTF-16). Ahora, cargará los términos actualizados y actualizará el diccionario en contexto.</span><span class="sxs-lookup"><span data-stu-id="1bdba-p109">Now open the file, add your other terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="1bdba-134">Ahora se ha actualizado el diccionario en contexto.</span><span class="sxs-lookup"><span data-stu-id="1bdba-134">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="1bdba-135">El campo `Identity` toma el nombre del diccionario.</span><span class="sxs-lookup"><span data-stu-id="1bdba-135">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="1bdba-136">Si también quiere cambiar el nombre del diccionario con el cmdlet `set-`, necesita agregar el parámetro `-Name` a los comandos anteriores con el nuevo nombre del diccionario.</span><span class="sxs-lookup"><span data-stu-id="1bdba-136">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 

<span data-ttu-id="1bdba-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bdba-137">See Also</span></span>
- [<span data-ttu-id="1bdba-138">Crear un diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="1bdba-138">Create a keyword dictionary</span></span>](create-a-keyword-dictionary.md)
- [<span data-ttu-id="1bdba-139">Crear un tipo personalizado de información confidencial</span><span class="sxs-lookup"><span data-stu-id="1bdba-139">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
