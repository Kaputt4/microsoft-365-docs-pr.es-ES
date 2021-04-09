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
ms.openlocfilehash: b70deed531204f2ffe85253bd9ae2073dad291ec
ms.sourcegitcommit: 58fbcfd6437bfb08966b79954ca09556e636ff4a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2021
ms.locfileid: "51632196"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="6d50c-103">Crear un diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="6d50c-103">Create a keyword dictionary</span></span>

<span data-ttu-id="6d50c-104">La prevención de pérdida de datos (DLP) puede identificar, supervisar y proteger los elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="6d50c-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="6d50c-105">Para identificar elementos confidenciales, a veces es necesario buscar palabras clave, especialmente al identificar contenido genérico (como comunicaciones relacionadas con la salud) o lenguaje explícito o inadecuado.</span><span class="sxs-lookup"><span data-stu-id="6d50c-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="6d50c-106">Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave están limitadas en tamaño y es necesario modificar el código XML para crearlas o editarlas.</span><span class="sxs-lookup"><span data-stu-id="6d50c-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="6d50c-107">Los diccionarios de palabras clave proporcionan una administración más sencilla de las palabras clave y a una escala mucho mayor, lo que admite hasta 1 MB de términos (después de la compresión) en el diccionario en cualquier idioma.</span><span class="sxs-lookup"><span data-stu-id="6d50c-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="6d50c-108">El límite del espacio empresarial también es de 1 MB después de la compresión.</span><span class="sxs-lookup"><span data-stu-id="6d50c-108">The tenant limit is also 1MB after compression.</span></span> <span data-ttu-id="6d50c-109">1 MB de límite después de la compresión significa que todos los diccionarios combinados en un espacio empresarial pueden tener casi 1 millón de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6d50c-109">1MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million character.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="6d50c-110">Límites del diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="6d50c-110">Keyword dictionary limits</span></span>

<span data-ttu-id="6d50c-111">Existe un límite de 50 tipos de información confidencial basados en el diccionario de palabras clave que se pueden crear por espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="6d50c-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="6d50c-112">Para averiguar cuántos diccionarios de palabras clave tiene en su espacio empresarial, puede ejecutar este script de PowerShell en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="6d50c-112">To find out how many keyword dictionaries you have in your tenant, you can run this PowerShell script against your tenant.</span></span>

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="6d50c-113">Pasos básicos para crear un diccionario de palabras clave</span><span class="sxs-lookup"><span data-stu-id="6d50c-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="6d50c-p103">Las palabras clave del diccionario pueden provenir de una amplia variedad de orígenes, normalmente de un archivo (como una lista en un archivo .csv o .txt), importadas en el servicio o por el cmdlet de PowerShell, de una lista que escriba directamente en el cmdlet de PowerShell o de un diccionario existente. Al crear un diccionario de palabras clave, siga los mismos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="6d50c-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="6d50c-116">Use el **Centro de seguridad y cumplimiento** ([https://protection.office.com](https://protection.office.com)) o conéctese al **PowerShell del Centro de seguridad &amp; cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="6d50c-117">**Defina o cargue las palabras clave del origen que quiera usar**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="6d50c-118">Tanto el asistente como el cmdlet aceptan una lista separada por comas de palabras clave para crear un diccionario personalizado de palabras clave, por lo que este paso variará ligeramente según el origen de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="6d50c-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="6d50c-119">Una vez cargadas, se codificarán y convertirán en una matriz de bytes antes de su importación.</span><span class="sxs-lookup"><span data-stu-id="6d50c-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="6d50c-120">**Cree su diccionario**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-120">**Create your dictionary**.</span></span> <span data-ttu-id="6d50c-121">Seleccione un nombre y una descripción y, después, cree el diccionario.</span><span class="sxs-lookup"><span data-stu-id="6d50c-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="6d50c-122">Cree un diccionario de palabras clave con el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6d50c-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="6d50c-123">Siga estos pasos para crear e importar palabras clave para un diccionario personalizado:</span><span class="sxs-lookup"><span data-stu-id="6d50c-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="6d50c-124">Conéctese al Centro de seguridad y cumplimiento ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="6d50c-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="6d50c-125">Vaya a **Clasificaciones > Tipos de información confidencial**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="6d50c-126">Seleccione **Crear** y escriba un **Nombre** y **Descripción** para el tipo de información confidencial, a continuación, seleccione **Siguiente**</span><span class="sxs-lookup"><span data-stu-id="6d50c-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="6d50c-127">Seleccione **Agregar un elemento** y seleccione **Diccionario (palabras clave grandes)** en la lista desplegable **Detectar contenido que contenga**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="6d50c-128">Seleccione **Agregar un diccionario**</span><span class="sxs-lookup"><span data-stu-id="6d50c-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="6d50c-129">En el control de Búsqueda, seleccione **Puede crear nuevos diccionarios de palabras clave aquí**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="6d50c-130">Escriba un **Nombre** para el diccionario personalizado.</span><span class="sxs-lookup"><span data-stu-id="6d50c-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="6d50c-131">Seleccione **Importar** y seleccione **Desde texto** o **Desde csv** según el tipo de archivo de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="6d50c-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="6d50c-132">En el cuadro de diálogo, seleccione el archivo de palabras clave del equipo o de los recursos compartidos de su red local y, después, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="6d50c-133">Seleccione **Guardar**, después, seleccione el diccionario personalizado de la lista **Diccionarios de palabras clave**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="6d50c-134">Seleccione **Agregar** y, después, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="6d50c-135">Revise y finalice las selecciones de tipo de información confidencial y seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="6d50c-136">Crear un diccionario de palabras clave desde un archivo con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d50c-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="6d50c-137">Con frecuencia, si necesita crear un diccionario de gran tamaño, puede usar palabras clave de un archivo o una lista exportada de otro origen.</span><span class="sxs-lookup"><span data-stu-id="6d50c-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="6d50c-138">En este caso, creará un diccionario de palabras clave que contenga una lista de lenguaje inadecuado para supervisarlo en el correo electrónico externo.</span><span class="sxs-lookup"><span data-stu-id="6d50c-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="6d50c-139">Primero, necesita [conectarse al PowerShell del Centro de seguridad &amp; cumplimiento](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="6d50c-139">You must first [connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="6d50c-140">Copie las palabras clave en un archivo de texto y asegúrese de que cada palabra clave se encuentre en una línea separada.</span><span class="sxs-lookup"><span data-stu-id="6d50c-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="6d50c-p107">Guarde el archivo de texto con codificación Unicode. En el Bloc de notas \> **Guardar como** \> **Codificación** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="6d50c-143">Para leer el archivo en una variable, ejecute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6d50c-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="6d50c-144">Para crear el diccionario, ejecute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6d50c-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="6d50c-145">Modificar un diccionario de palabras clave existente</span><span class="sxs-lookup"><span data-stu-id="6d50c-145">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="6d50c-146">Es posible que tenga que modificar palabras clave en uno de los diccionarios de palabras clave o modificar uno de los diccionarios integrados.</span><span class="sxs-lookup"><span data-stu-id="6d50c-146">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="6d50c-147">Actualmente, solo puede actualizar un diccionario personalizado de palabras clave con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d50c-147">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="6d50c-148">Por ejemplo, vamos a modificar algunos términos en PowerShell, guardar los términos localmente donde se puedan modificar en un editor y, después, actualizar los términos anteriores.</span><span class="sxs-lookup"><span data-stu-id="6d50c-148">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="6d50c-149">En primer lugar, recupere el objeto de diccionario:</span><span class="sxs-lookup"><span data-stu-id="6d50c-149">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="6d50c-150">La impresión de `$dict` mostrará las distintas variables.</span><span class="sxs-lookup"><span data-stu-id="6d50c-150">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="6d50c-151">Las palabras clave en sí se almacenan en un objeto en el back-end, pero `$dict.KeywordDictionary` contiene una representación de cadena de estas, que usará para modificar el diccionario.</span><span class="sxs-lookup"><span data-stu-id="6d50c-151">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="6d50c-152">Antes de modificar el diccionario, necesita volver a convertir la cadena de términos en una matriz con el método `.split(',')`.</span><span class="sxs-lookup"><span data-stu-id="6d50c-152">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="6d50c-153">Después, eliminará los espacios no deseados entre las palabras clave con el método `.trim()` y dejará únicamente las palabras clave con las que quiera trabajar.</span><span class="sxs-lookup"><span data-stu-id="6d50c-153">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="6d50c-p111">Ahora, quitará algunos términos del diccionario. Como el diccionario de ejemplo solo tiene unas pocas palabras clave, podría exportar fácilmente el diccionario y editarlo en el Bloc de notas, pero los diccionarios suelen contener una gran cantidad de texto, por lo que primero aprenderá esta forma de editarlos fácilmente en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d50c-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="6d50c-p112">En el último paso, guardó las palabras clave en una matriz. Hay varias formas de [quitar elementos de una matriz](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), pero un método sencillo es crear una matriz de los términos que quiera quitar del diccionario y, después, copiar en este solo los términos que no se encuentren en la lista de términos que quiera quitar.</span><span class="sxs-lookup"><span data-stu-id="6d50c-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="6d50c-p113">Ejecute el comando `$terms` para mostrar la lista de términos actual. El resultado del comando tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="6d50c-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="6d50c-160">Ejecute este comando para especificar los términos que quiera quitar:</span><span class="sxs-lookup"><span data-stu-id="6d50c-160">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="6d50c-161">Ejecute este comando para quitar los términos de la lista:</span><span class="sxs-lookup"><span data-stu-id="6d50c-161">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="6d50c-p114">Ejecute el comando `$updatedTerms` para mostrar la lista actualizada de términos. El resultado del comando será parecido a este (se quitaron los términos especificados):</span><span class="sxs-lookup"><span data-stu-id="6d50c-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="6d50c-p115">Ahora, simplemente abra el archivo, agregue los términos adicionales y guárdelo con codificación Unicode (UTF-16). Ahora, cargará los términos actualizados y actualizará el diccionario en contexto.</span><span class="sxs-lookup"><span data-stu-id="6d50c-p115">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="6d50c-p116">Ahora, el diccionario se actualizó en contexto. Tenga en cuenta que el campo `Identity` recibe el nombre del diccionario. Si también quiere cambiar el nombre del diccionario con el cmdlet `set-`, necesita agregar el parámetro `-Name` a los comandos anteriores con el nuevo nombre de diccionario.</span><span class="sxs-lookup"><span data-stu-id="6d50c-p116">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="6d50c-169">Usar diccionarios de palabras clave en tipos de información confidencial personalizados y directivas DLP</span><span class="sxs-lookup"><span data-stu-id="6d50c-169">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="6d50c-170">Los diccionarios de palabras clave se pueden usar como parte de los requisitos de coincidencia para un tipo de información confidencial personalizado, o bien como un tipo de información confidencial en sí.</span><span class="sxs-lookup"><span data-stu-id="6d50c-170">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="6d50c-171">En ambos casos, es necesario crear un [tipo de información confidencial personalizado](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6d50c-171">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="6d50c-172">Siga las instrucciones en el artículo vinculado para crear un tipo de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="6d50c-172">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="6d50c-173">Cuando tenga el archivo XML, necesitará el identificador GUID para que el diccionario lo use.</span><span class="sxs-lookup"><span data-stu-id="6d50c-173">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="6d50c-174">Para obtener la identidad del diccionario, ejecute este comando y copie el valor de la propiedad **Identity**:</span><span class="sxs-lookup"><span data-stu-id="6d50c-174">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="6d50c-175">El resultado del comando tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="6d50c-175">The output of the command looks like this:</span></span>
  
<span data-ttu-id="6d50c-176">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="6d50c-176">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="6d50c-p118">Pegue la identidad en el archivo XML del tipo de información confidencial personalizado y cárguelo. Ahora, el diccionario aparecerá en la lista de tipos de información confidencial y puede usarlo en la directiva (para hacerlo, especifique el número de palabras clave que tienen que coincidir).</span><span class="sxs-lookup"><span data-stu-id="6d50c-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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

> [!NOTE]
> <span data-ttu-id="6d50c-179">Microsoft 365 Information Protection es compatible con los idiomas del conjunto de caracteres de doble byte de vista previa para:</span><span class="sxs-lookup"><span data-stu-id="6d50c-179">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="6d50c-180">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="6d50c-180">Chinese (simplified)</span></span>
> - <span data-ttu-id="6d50c-181">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="6d50c-181">Chinese (traditional)</span></span>
> - <span data-ttu-id="6d50c-182">Coreano</span><span class="sxs-lookup"><span data-stu-id="6d50c-182">Korean</span></span>
> - <span data-ttu-id="6d50c-183">Japonés</span><span class="sxs-lookup"><span data-stu-id="6d50c-183">Japanese</span></span>
>
><span data-ttu-id="6d50c-184">Este soporte está disponible para tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="6d50c-184">This support is available for sensitive information types.</span></span> <span data-ttu-id="6d50c-185">Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="6d50c-185">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>