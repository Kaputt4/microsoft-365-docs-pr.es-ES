---
title: Crear un diccionario de palabras clave
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre los pasos básicos para crear un diccionario de palabras clave en el Centro de seguridad y cumplimiento de Office 365.
ms.openlocfilehash: bad95e9a5605631de3e8652e7243909f28b2abde
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282740"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="8cd7c-103">Crear un diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="8cd7c-103">Create a keyword dictionary</span></span>

<span data-ttu-id="8cd7c-104">La prevención de pérdida de datos (DLP) puede identificar, supervisar y proteger los elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="8cd7c-105">Para identificar elementos confidenciales, a veces es necesario buscar palabras clave, especialmente al identificar contenido genérico (como comunicaciones relacionadas con la salud) o lenguaje explícito o inadecuado.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="8cd7c-106">Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave están limitadas en tamaño y es necesario modificar el código XML para crearlas o editarlas.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="8cd7c-107">Los diccionarios de palabras clave proporcionan una administración más sencilla de las palabras clave y a una escala mucho mayor, lo que admite hasta 100 KB de términos (después de la compresión) en el diccionario en cualquier idioma.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100KB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="8cd7c-108">El límite del espacio empresarial también es de 100 KB después de la compresión.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-108">The tenant limit is also 100KB after compression.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8cd7c-109">Microsoft 365 Information Protection ahora es compatible con la vista previa de idiomas con conjunto de caracteres de doble byte para:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-109">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="8cd7c-110">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="8cd7c-110">Chinese (simplified)</span></span>
> - <span data-ttu-id="8cd7c-111">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="8cd7c-111">Chinese (traditional)</span></span>
> - <span data-ttu-id="8cd7c-112">Coreano</span><span class="sxs-lookup"><span data-stu-id="8cd7c-112">Korean</span></span>
> - <span data-ttu-id="8cd7c-113">Japonés</span><span class="sxs-lookup"><span data-stu-id="8cd7c-113">Japanese</span></span>
> 
><span data-ttu-id="8cd7c-114">Esta versión preliminar solo se encuentra en la nube comercial y la implementación está limitada a:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-114">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="8cd7c-115">Japón</span><span class="sxs-lookup"><span data-stu-id="8cd7c-115">Japan</span></span>
> - <span data-ttu-id="8cd7c-116">Corea</span><span class="sxs-lookup"><span data-stu-id="8cd7c-116">Korea</span></span>
> - <span data-ttu-id="8cd7c-117">China</span><span class="sxs-lookup"><span data-stu-id="8cd7c-117">China</span></span>
> - <span data-ttu-id="8cd7c-118">RAE de Hong Kong</span><span class="sxs-lookup"><span data-stu-id="8cd7c-118">Hong Kong</span></span>
> - <span data-ttu-id="8cd7c-119">RAE de Macao</span><span class="sxs-lookup"><span data-stu-id="8cd7c-119">Macau</span></span>
> - <span data-ttu-id="8cd7c-120">Taiwán</span><span class="sxs-lookup"><span data-stu-id="8cd7c-120">Taiwan</span></span>
>
><span data-ttu-id="8cd7c-121">Este soporte está disponible para tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-121">This support is available for sensitive information types.</span></span> <span data-ttu-id="8cd7c-122">Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="8cd7c-122">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="8cd7c-123">Pasos básicos para crear un diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="8cd7c-123">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="8cd7c-p103">Las palabras clave del diccionario pueden provenir de una amplia variedad de orígenes, normalmente de un archivo (como una lista en un archivo .csv o .txt), importadas en el servicio o por el cmdlet de PowerShell, de una lista que escriba directamente en el cmdlet de PowerShell o de un diccionario existente. Al crear un diccionario de palabras clave, siga los mismos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="8cd7c-126">Use el **Centro de seguridad y cumplimiento** ([https://protection.office.com](https://protection.office.com)) o conéctese al **PowerShell del Centro de seguridad &amp; cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-126">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="8cd7c-127">**Defina o cargue las palabras clave del origen que quiera usar**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-127">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="8cd7c-128">Tanto el asistente como el cmdlet aceptan una lista separada por comas de palabras clave para crear un diccionario personalizado de palabras clave, por lo que este paso variará ligeramente según el origen de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-128">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="8cd7c-129">Una vez cargadas, se codificarán y convertirán en una matriz de bytes antes de su importación.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-129">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="8cd7c-130">**Cree su diccionario**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-130">**Create your dictionary**.</span></span> <span data-ttu-id="8cd7c-131">Seleccione un nombre y una descripción y, después, cree el diccionario.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-131">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="8cd7c-132">Cree un diccionario de palabras clave con el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="8cd7c-132">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="8cd7c-133">Siga estos pasos para crear e importar palabras clave para un diccionario personalizado:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-133">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="8cd7c-134">Conéctese al Centro de seguridad y cumplimiento ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="8cd7c-134">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="8cd7c-135">Vaya a **Clasificaciones > Tipos de información confidencial**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-135">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="8cd7c-136">Seleccione **Crear** y escriba un **Nombre** y **Descripción** para el tipo de información confidencial, a continuación, seleccione **Siguiente**</span><span class="sxs-lookup"><span data-stu-id="8cd7c-136">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="8cd7c-137">Seleccione **Agregar un elemento** y seleccione **Diccionario (palabras clave grandes)** en la lista desplegable **Detectar contenido que contenga**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-137">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="8cd7c-138">Seleccione **Agregar un diccionario**</span><span class="sxs-lookup"><span data-stu-id="8cd7c-138">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="8cd7c-139">En el control de Búsqueda, seleccione **Puede crear nuevos diccionarios de palabras clave aquí**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-139">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="8cd7c-140">Escriba un **Nombre** para el diccionario personalizado.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-140">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="8cd7c-141">Seleccione **Importar** y seleccione **Desde texto** o **Desde csv** según el tipo de archivo de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-141">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="8cd7c-142">En el cuadro de diálogo, seleccione el archivo de palabras clave del equipo o de los recursos compartidos de su red local y, después, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-142">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="8cd7c-143">Seleccione **Guardar**, después, seleccione el diccionario personalizado de la lista **Diccionarios de palabras clave**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-143">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="8cd7c-144">Seleccione **Agregar** y, después, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-144">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="8cd7c-145">Revise y finalice las selecciones de tipo de información confidencial y seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-145">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="8cd7c-146">Crear un diccionario de palabras clave desde un archivo con PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cd7c-146">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="8cd7c-147">Con frecuencia, si necesita crear un diccionario de gran tamaño, puede usar palabras clave de un archivo o una lista exportada de otro origen.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-147">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="8cd7c-148">En este caso, creará un diccionario de palabras clave que contenga una lista de lenguaje inadecuado para supervisarlo en el correo electrónico externo.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-148">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="8cd7c-149">Primero, necesita [conectarse al PowerShell del Centro de seguridad &amp; cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="8cd7c-149">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="8cd7c-150">Copie las palabras clave en un archivo de texto y asegúrese de que cada palabra clave se encuentre en una línea separada.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-150">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="8cd7c-p107">Guarde el archivo de texto con codificación Unicode. En el Bloc de notas \> **Guardar como** \> **Codificación** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="8cd7c-153">Para leer el archivo en una variable, ejecute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-153">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="8cd7c-154">Para crear el diccionario, ejecute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-154">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="8cd7c-155">Modificar un diccionario de palabras clave existente</span><span class="sxs-lookup"><span data-stu-id="8cd7c-155">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="8cd7c-156">Es posible que tenga que modificar palabras clave en uno de los diccionarios de palabras clave o modificar uno de los diccionarios integrados.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-156">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="8cd7c-157">Actualmente, solo puede actualizar un diccionario personalizado de palabras clave con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-157">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="8cd7c-158">Por ejemplo, vamos a modificar algunos términos en PowerShell, guardar los términos localmente donde se puedan modificar en un editor y, después, actualizar los términos anteriores.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-158">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="8cd7c-159">En primer lugar, recupere el objeto de diccionario:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-159">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="8cd7c-160">La impresión de `$dict` mostrará las distintas variables.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-160">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="8cd7c-161">Las palabras clave en sí se almacenan en un objeto en el back-end, pero `$dict.KeywordDictionary` contiene una representación de cadena de estas, que usará para modificar el diccionario.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-161">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="8cd7c-162">Antes de modificar el diccionario, necesita volver a convertir la cadena de términos en una matriz con el método `.split(',')`.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-162">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="8cd7c-163">Después, eliminará los espacios no deseados entre las palabras clave con el método `.trim()` y dejará únicamente las palabras clave con las que quiera trabajar.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-163">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="8cd7c-p111">Ahora, quitará algunos términos del diccionario. Como el diccionario de ejemplo solo tiene unas pocas palabras clave, podría exportar fácilmente el diccionario y editarlo en el Bloc de notas, pero los diccionarios suelen contener una gran cantidad de texto, por lo que primero aprenderá esta forma de editarlos fácilmente en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="8cd7c-p112">En el último paso, guardó las palabras clave en una matriz. Hay varias formas de [quitar elementos de una matriz](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), pero un método sencillo es crear una matriz de los términos que quiera quitar del diccionario y, después, copiar en este solo los términos que no se encuentren en la lista de términos que quiera quitar.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="8cd7c-p113">Ejecute el comando `$terms` para mostrar la lista de términos actual. El resultado del comando tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="8cd7c-170">Ejecute este comando para especificar los términos que quiera quitar:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-170">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="8cd7c-171">Ejecute este comando para quitar los términos de la lista:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-171">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="8cd7c-p114">Ejecute el comando `$updatedTerms` para mostrar la lista actualizada de términos. El resultado del comando será parecido a este (se quitaron los términos especificados):</span><span class="sxs-lookup"><span data-stu-id="8cd7c-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="8cd7c-p115">Ahora, simplemente abra el archivo, agregue los términos adicionales y guárdelo con codificación Unicode (UTF-16). Ahora, cargará los términos actualizados y actualizará el diccionario en contexto.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-p115">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="8cd7c-p116">Ahora, el diccionario se actualizó en contexto. Tenga en cuenta que el campo `Identity` recibe el nombre del diccionario. Si también quiere cambiar el nombre del diccionario con el cmdlet `set-`, necesita agregar el parámetro `-Name` a los comandos anteriores con el nuevo nombre de diccionario.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-p116">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="8cd7c-179">Usar diccionarios de palabras clave en tipos de información confidencial personalizados y directivas DLP</span><span class="sxs-lookup"><span data-stu-id="8cd7c-179">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="8cd7c-180">Los diccionarios de palabras clave se pueden usar como parte de los requisitos de coincidencia para un tipo de información confidencial personalizado, o bien como un tipo de información confidencial en sí.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-180">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="8cd7c-181">En ambos casos, es necesario crear un [tipo de información confidencial personalizado](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="8cd7c-181">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="8cd7c-182">Siga las instrucciones en el artículo vinculado para crear un tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-182">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="8cd7c-183">Cuando tenga el archivo XML, necesitará el identificador GUID para que el diccionario lo use.</span><span class="sxs-lookup"><span data-stu-id="8cd7c-183">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="8cd7c-184">Para obtener la identidad del diccionario, ejecute este comando y copie el valor de la propiedad **Identity**:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-184">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="8cd7c-185">El resultado del comando tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="8cd7c-185">The output of the command looks like this:</span></span>
  
<span data-ttu-id="8cd7c-186">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="8cd7c-186">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="8cd7c-p118">Pegue la identidad en el archivo XML del tipo de información confidencial personalizado y cárguelo. Ahora, el diccionario aparecerá en la lista de tipos de información confidencial y puede usarlo en la directiva (para hacerlo, especifique el número de palabras clave que tienen que coincidir).</span><span class="sxs-lookup"><span data-stu-id="8cd7c-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```
