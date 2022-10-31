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
ms.localizationpriority: high
ms.collection:
- tier1
- purview-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: Obtenga información sobre los pasos básicos para crear un diccionario de palabras clave en el portal de cumplimiento de Microsoft Purview.
ms.openlocfilehash: 7587357c8b9ce58b39f9027d56644401c6804c04
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2022
ms.locfileid: "68793816"
---
# <a name="create-a-keyword-dictionary"></a>Crear un diccionario de palabras clave

La prevención de pérdida de datos (DLP) de Microsoft Purview puede identificar, supervisar y proteger los elementos confidenciales. Para identificar elementos confidenciales, a veces es necesario buscar palabras clave, especialmente al identificar contenido genérico (como comunicaciones relacionadas con la salud) o lenguaje explícito o inadecuado. Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave están limitadas en tamaño y es necesario modificar el código XML para crearlas o editarlas. Los diccionarios de palabras clave proporcionan una administración más sencilla de las palabras clave y a una escala mucho mayor, lo que admite hasta 1 MB de términos (después de la compresión) en el diccionario en cualquier idioma. El límite del espacio empresarial también es de 1 MB después de la compresión. 1 MB de límite después de la compresión significa que todos los diccionarios combinados en un espacio empresarial pueden tener casi 1 millón de caracteres.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="keyword-dictionary-limits"></a>Límites del diccionario de palabras clave

Existe un límite de 50 tipos de información confidencial basados en el diccionario de palabras clave que se pueden crear por espacio empresarial. Para descubrir cuántos diccionarios de palabras clave tiene en su espacio empresarial, conéctese mediante los procedimientos de [Conectarse al PowerShell de Seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell) para conectarse a su espacio empresarial y ejecutar este script de PowerShell.

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
[System.IO.File]::WriteAllBytes((Resolve-Path $rawFile), $ruleCollections.SerializedClassificationRuleCollection)
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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Pasos básicos para crear un diccionario de palabras clave

The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:

1. Use el *<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Portal de cumplimiento de Microsoft Purview</a> o conéctese al **PowerShell del portal de cumplimiento de Microsoft Purview**.

2. **Define or load your keywords from your intended source**. The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from. Once loaded, they're encoded and converted to a byte array before they're imported.

3. **Cree su diccionario**. Seleccione un nombre y una descripción y, después, cree el diccionario.

## <a name="create-a-keyword-dictionary-using-the-microsoft-purview-compliance-portal"></a>Cree un diccionario de palabras clave mediante el portal de cumplimiento Microsoft Purview

Siga estos pasos para crear e importar palabras clave para un diccionario personalizado:

1. Conéctese al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento de Microsoft Purview</a>.

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

Con frecuencia, si necesita crear un diccionario de gran tamaño, puede usar palabras clave de un archivo o una lista exportada de otro origen. En este caso, creará un diccionario de palabras clave que contenga una lista de lenguaje inadecuado para supervisarlo en el correo electrónico externo. Primero debe [conectarse al PowerShell de Seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).

1. Copie las palabras clave en un archivo de texto y asegúrese de que cada palabra clave se encuentre en una línea separada.

2. Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.

3. Para leer el archivo en una variable, ejecute este cmdlet:

    ```powershell
    $fileData = [System.IO.File]::ReadAllBytes('<filename>')
    ```

4. Para crear el diccionario, ejecute este cmdlet:

    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Usar diccionarios de palabras clave en tipos de información confidencial personalizados y directivas DLP

Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves. Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md). Follow the instructions in the linked article to create a sensitive information type. Once you have the XML, you'll need the GUID identifier for the dictionary to use it.

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

> [!NOTE]
> Microsoft 365 Information Protection es compatible con los idiomas del juego de caracteres de doble byte para:
>
> - Chino (simplificado)
> - Chino (tradicional)
> - Coreano
> - Japonés
>
> Este soporte está disponible para tipos de información confidencial. Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).

> [!TIP]
> Para detectar patrones que contengan caracteres chinos/japoneses y caracteres de un solo byte o para detectar patrones que contengan chino/japonés e inglés, defina dos variantes de la palabra clave o regex.
>
> - Por ejemplo, para detectar una palabra clave como "机密的document", utilice dos variantes de la palabra clave; una con un espacio entre el texto japonés y el inglés y otra sin espacio entre el texto japonés y el inglés. Por lo tanto, las palabras clave que deben agregarse en el SIT deben ser "机密的document" y "机密的document". Del mismo modo, para detectar la frase "東京オリンピック2020", se deben utilizar dos variantes: "東京オリンピック 2020" y "東京オリンピック2020"".
>
> Junto con los caracteres chinos/japoneses y de dos bytes, si la lista de palabras clave o frases también contiene palabras no chinas o no japonesas (solo en inglés), se recomienda crear dos diccionarios o listas de palabras clave. Uno para las palabras clave que contienen caracteres chinos, japoneses o de dos bytes; y otro solo para inglés.
>
> - Por ejemplo, si desea crear una lista o diccionario de palabras clave con tres frases "Extremadamente confidencial", "機密性が高い" y "机密的document", deberá crear dos listas de teclado.
>   1. Extremadamente confidencial
>   2. 機密性が高い, 机密的document y 机密的 document
>
> While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex. Here is a sample regex for reference:
>
> - `(?<!\d)([4][0-9]{3}[\-?\-\t]*[0-9]{4}`
>
> Se recomienda utilizar una coincidencia de cadenas en lugar de una coincidencia de palabras en una lista de palabras clave.
