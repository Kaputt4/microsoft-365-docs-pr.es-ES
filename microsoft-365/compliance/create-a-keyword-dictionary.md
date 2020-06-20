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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre los pasos básicos para crear un diccionario de palabras clave en el centro de seguridad & cumplimiento de Office 365.
ms.openlocfilehash: 38a92aaf7e72ab79243c547ff48fa156e26b6ee6
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818059"
---
# <a name="create-a-keyword-dictionary"></a>Crear un diccionario de palabras clave

La prevención de pérdida de datos (DLP) puede identificar, supervisar y proteger la información confidencial. La identificación de información confidencial a veces requiere la búsqueda de palabras clave, especialmente al identificar contenido genérico (como la comunicación relacionada con el cuidado de la salud) o un lenguaje inadecuado o explícito. Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave tienen un tamaño limitado y requieren modificar el XML para crearlas o editarlas. Los diccionarios de palabras clave proporcionan una administración más sencilla de las palabras clave y en una escala mucho mayor, que admiten hasta 100.000 términos por Diccionario.
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Pasos básicos para crear un diccionario de palabras clave

The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:
  
1. Use el **centro de seguridad & cumplimiento** ( [https://protection.office.com](https://protection.office.com) ) o conéctese a **PowerShell del centro de seguridad y &amp; cumplimiento**.
    
2. **Defina o cargue las palabras clave del origen deseado**. El asistente y el cmdlet aceptan una lista separada por comas de palabras clave para crear un diccionario de palabras clave personalizado, por lo que este paso variará ligeramente en función de la procedencia de las palabras clave. Una vez cargadas, se codificarán y convertirán en una matriz de bytes antes de su importación.
    
3. **Cree su Diccionario**. Elija un nombre y una descripción y cree su Diccionario.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Crear un diccionario de palabras clave mediante el centro de seguridad & cumplimiento

Siga estos pasos para crear e importar palabras clave para un diccionario personalizado:

1. Conéctese al centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ).

2. Vaya a **Clasificaciones > Tipos de información confidencial**.

3. Seleccione **Crear** y escriba un **Nombre** y **Descripción** para el tipo de información confidencial, a continuación, seleccione **Siguiente**

4. Seleccione **Agregar un elemento** y seleccione **Diccionario (palabras clave grandes)** en la lista desplegable **Detectar contenido que contenga**.

5. Seleccione **Agregar un diccionario**

6. En el control de Búsqueda, seleccione **Puede crear nuevos diccionarios de palabras clave aquí**.

7. Escriba un **Nombre** para el diccionario personalizado.

8. Seleccione **Importar** y seleccione **Desde texto** o **Desde csv** según el tipo de archivo de palabras clave.

9. En el cuadro de diálogo, seleccione el archivo de palabras clave del equipo o de los recursos compartidos de su red local y, después, seleccione **Abrir**.

10. Seleccione **Guardar**, después, seleccione el diccionario personalizado de la lista **Diccionarios de palabras clave**.

11. Seleccione **Agregar** y, después, seleccione **Siguiente**.

12. Revise y finalice las selecciones de tipo de información confidencial y seleccione **Finalizar**.
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>Crear un diccionario de palabras clave desde un archivo con PowerShell

Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. Copie las palabras clave en un archivo de texto y asegúrese de que cada palabra clave se encuentre en una línea separada.
    
2. Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.
    
3. Para leer el archivo en una variable, ejecute este cmdlet:
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. Para crear el diccionario, ejecute este cmdlet:
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a>Modificar un diccionario de palabras clave existente

Es posible que tenga que modificar palabras clave en uno de los diccionarios de palabras clave o modificar uno de los diccionarios integrados. Actualmente, solo puede actualizar un diccionario personalizado de palabras clave con PowerShell. 

Por ejemplo, modificaremos algunos términos en PowerShell, guardaremos los términos localmente donde podrá modificarlos en un editor y, a continuación, actualizar los términos anteriores en su lugar. 

En primer lugar, recupere el objeto de diccionario:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

La impresión mostrará `$dict` las distintas variables. Las palabras clave en sí se almacenan en un objeto en el back-end, pero `$dict.KeywordDictionary` contienen una representación de cadena de ellas que usará para modificar el diccionario. 

Antes de modificar el diccionario, debe volver a convertir la cadena de términos en una matriz con el `.split(',')` método. A continuación, limpiará los espacios no deseados entre las palabras clave con el `.trim()` método, dejando solo las palabras clave con las que trabajar. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.
  
In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.
  
Run the command  `$terms` to show the current list of terms. The output of the command looks like this: 
  
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

Ejecute este comando para especificar los términos que quiera quitar:
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

Ejecute este comando para quitar los términos de la lista:
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed): 
  
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

Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Usar diccionarios de palabras clave en tipos de información confidencial personalizados y directivas DLP

Los diccionarios de palabras clave se pueden usar como parte de los requisitos de coincidencia de un tipo personalizado de información confidencial, o bien como un tipo de información confidencial. Ambos requieren que se cree un [tipo personalizado de información confidencial](create-a-custom-sensitive-information-type-in-scc-powershell.md). Siga las instrucciones del artículo vinculado para crear un tipo de información confidencial. Una vez que tenga el XML, necesitará el identificador de GUID para que el Diccionario lo use.
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

Para obtener la identidad del diccionario, ejecute este comando y copie el valor de la propiedad **Identity**: 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

El resultado del comando tiene este aspecto:
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.
  
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
