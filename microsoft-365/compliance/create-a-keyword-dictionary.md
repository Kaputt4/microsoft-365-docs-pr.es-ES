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
ms.openlocfilehash: 8d313650f298f2ab26989bec9df1260918f7dd5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300116"
---
# <a name="create-a-keyword-dictionary"></a>Crear un diccionario de palabras clave

La prevención de pérdida de datos (DLP) puede identificar, supervisar y proteger los elementos confidenciales. Para identificar elementos confidenciales, a veces es necesario buscar palabras clave, especialmente al identificar contenido genérico (como comunicaciones relacionadas con la salud) o lenguaje explícito o inadecuado. Aunque puede crear listas de palabras clave en tipos de información confidencial, las listas de palabras clave están limitadas en tamaño y es necesario modificar el código XML para crearlas o editarlas. Los diccionarios de palabras clave proporcionan una administración más sencilla de las palabras clave y a una escala mucho mayor, lo que admite hasta 1 MB de términos (después de la compresión) en el diccionario en cualquier idioma. El límite del espacio empresarial también es de 1 MB después de la compresión. 1 MB de límite después de la compresión significa que todos los diccionarios combinados en un espacio empresarial pueden tener casi 1 millón de caracteres.

## <a name="keyword-dictionary-limits"></a>Límites del diccionario de palabras clave

Existe un límite de 50 tipos de información confidencial basados en el diccionario de palabras clave que se pueden crear por espacio empresarial. Para descubrir cuántos diccionarios de palabras clave tiene en su espacio empresarial, conéctese mediante los procedimientos de [Conectarse al PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell) para conectarse a su espacio empresarial y ejecutar este script de PowerShell.

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Pasos básicos para crear un diccionario de palabras clave

Las palabras clave del diccionario pueden provenir de varios orígenes, normalmente de un archivo (como una lista en un archivo .csv o .txt) importado en el servicio o del cmdlet de PowerShell, de una lista que escriba directamente en el cmdlet de PowerShell o de un diccionario existente. Al crear un diccionario de palabras clave, siga los mismos pasos principales:
  
1. Use el **Centro de seguridad y cumplimiento** ([https://protection.office.com](https://protection.office.com)) o conéctese al **PowerShell del Centro de seguridad &amp; cumplimiento**.
    
2. **Defina o cargue las palabras clave del origen que quiera usar**. Tanto el asistente como el cmdlet aceptan una lista separada por comas de palabras clave para crear un diccionario personalizado de palabras clave, por lo que este paso variará ligeramente según el origen de las palabras clave. Una vez cargadas, se codificarán y convertirán en una matriz de bytes antes de su importación.
    
3. **Cree su diccionario**. Seleccione un nombre y una descripción y, después, cree el diccionario.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Cree un diccionario de palabras clave con el Centro de seguridad y cumplimiento

Siga estos pasos para crear e importar palabras clave para un diccionario personalizado:

1. Conéctese al Centro de seguridad y cumplimiento ([https://protection.office.com](https://protection.office.com)).

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

Con frecuencia, si necesita crear un diccionario de gran tamaño, puede usar palabras clave de un archivo o una lista exportada de otro origen. En este caso, creará un diccionario de palabras clave que contenga una lista de lenguaje inadecuado para supervisarlo en el correo electrónico externo. Primero, necesita [Conectarse al PowerShell del Centro de seguridad &amp; y cumplimiento](/powershell/exchange/connect-to-scc-powershell).
  
1. Copie las palabras clave en un archivo de texto y asegúrese de que cada palabra clave se encuentre en una línea separada.
    
2. Guarde el archivo de texto con codificación Unicode. En el Bloc de notas \> **Guardar como** \> **Codificación** \> **Unicode**.
    
3. Para leer el archivo en una variable, ejecute este cmdlet:
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. Para crear el diccionario, ejecute este cmdlet:
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Usar diccionarios de palabras clave en tipos de información confidencial personalizados y directivas DLP

Los diccionarios de palabras clave se pueden usar como parte de los requisitos de coincidencia para un tipo de información confidencial personalizado, o bien como un tipo de información confidencial en sí. En ambos casos, es necesario crear un [tipo de información confidencial personalizado](create-a-custom-sensitive-information-type-in-scc-powershell.md). Siga las instrucciones en el artículo vinculado para crear un tipo de información confidencial. Cuando tenga el archivo XML, necesitará el identificador GUID para que el diccionario lo use.
  
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


Pegue la identidad en el archivo XML del tipo de información confidencial personalizado y cárguelo. Ahora, el diccionario aparecerá en la lista de tipos de información confidencial y puede usarlo en la directiva (para hacerlo, especifique el número de palabras clave que tienen que coincidir).
  
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
> - Chino (simplificado)
> - Chino (tradicional)
> - Coreano
> - Japonés
>
>Este soporte está disponible para tipos de información confidencial. Para más información, consulte [Notas de la versión sobre la compatibilidad de Information Protection con juegos de caracteres de doble byte (vista previa)](mip-dbcs-relnotes.md).

> [!TIP]
> Para detectar patrones que contengan caracteres chinos/japoneses y caracteres de un solo byte o para detectar patrones que contengan chino/japonés e inglés, defina dos variantes de la palabra clave o regex. 
>
> Por ejemplo, para detectar una palabra clave como "机密的document", utilice dos variantes de la palabra clave; una con un espacio entre el texto japonés y el inglés y otra sin espacio entre el texto japonés y el inglés. Por lo tanto, las palabras clave que deben agregarse en el SIT deben ser "机密的document" y "机密的document". Del mismo modo, para detectar la frase "東京オリンピック2020", se deben utilizar dos variantes: "東京オリンピック 2020" y "東京オリンピック2020"".
>
> Al crear una regex que utilice un guión de doble byte o un punto de doble byte, asegúrese de escapar ambos caracteres como se escaparía un guión o un punto en una regex. A continuación le mostramos un ejemplo de regex a modo de referencia:
>
>    - (?<!\d)([４][０-９]{3}[\-?\－\t]*[０-９]{4}
>
> Se recomienda utilizar una coincidencia de cadenas en lugar de una coincidencia de palabras en una lista de palabras clave.
